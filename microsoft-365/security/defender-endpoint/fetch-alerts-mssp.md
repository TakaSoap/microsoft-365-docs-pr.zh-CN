---
title: 从 MSSP 客户租户提取警报
description: 了解如何从客户租户获取警报
keywords: 托管安全服务提供程序， mssp， 配置， 集成
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: e2ac36689f9f41badb2f4216198d8818e568778b
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2022
ms.locfileid: "62214173"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>从 MSSP 客户租户提取警报

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> 此操作由 MSSP 执行。

有两种方法可以提取警报：

- 使用 SIEM 方法
- 使用 API

## <a name="fetch-alerts-into-your-siem"></a>将警报提取到 SIEM 中

若要将警报提取到 SIEM 系统中，需要执行以下步骤：

- 步骤 1：创建第三方应用程序
- 步骤 2：从客户的租户获取访问和刷新令牌
- 步骤 3：允许应用程序Microsoft 365 Defender

### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>步骤 1：在 Azure Active Directory (Azure AD) 

你需要创建一个应用程序，并授予它从客户的租户获取Microsoft 365 Defender的权限。

1. 登录到 Azure AD[门户](https://aad.portal.azure.com/)。

2. 选择 **Azure Active Directory** \> **应用注册"。**

3. 单击"**新建注册"。**

4. 指定以下值：

    - 名称 \<Tenant_name\> ：SIEM MSSP 连接器 (租户Tenant_name替换为租户显示名称) 

    - 支持的帐户类型：仅此组织目录中的帐户
    - 重定向 URI：选择"Web"，然后 `https://<domain_name>/SiemMsspConnector` ("<domain_name>租户名称") 

5. 单击“**注册**”。 应用程序显示在你拥有的应用程序列表中。

6. 选择应用程序，然后单击"概述 **"。**

7. 将值从应用程序客户端 **(ID)** 复制到安全位置，下一步中将需要此值。

8. Select **Certificate & secrets** in the new application panel.

9. 单击 **"新建客户端密码"。**

    - 说明：输入密钥的说明。
    - 过期：在 **1 年后选择**

10. 单击 **"** 添加"，将客户端密码的值复制到安全位置，下一步中将需要此密码。

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>步骤 2：从客户的租户获取访问和刷新令牌

本部分指导你如何使用 PowerShell 脚本从客户的租户获取令牌。 此脚本使用上一步中的应用程序，使用 OAuth 授权代码和刷新令牌Flow。

提供凭据后，你需要同意应用程序，以便应用程序在客户的租户中预配。

1. 创建一个新文件夹，并命名它 `MsspTokensAcquisition` ：。

2. 下载 [LoginBrowser.psm1 模块](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) 并将其保存在 `MsspTokensAcquisition` 文件夹中。

    > [!NOTE]
    > 在行 30 中，将 `authorzationUrl` 替换为 `authorizationUrl` 。

3. 创建包含以下内容的文件，并将其与文件夹中的名称 `MsspTokensAcquisition.ps1` 一起保存：

    ```powershell
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " ----------------------------------- TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " ----------------------------------- REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken
    ```
4. 在 文件夹中打开提升的 PowerShell 命令 `MsspTokensAcquisition` 提示符。

5. 运行以下命令：`Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. 输入以下命令： `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`

    - 将 \<client_id\> 替换为 **上一 ()** 应用程序客户端 ID。
    - 将 \<app_key\> 替换为在上一步中创建的客户端密码。
    - 将 \<customer_tenant_id\> 替换为客户的租户 **ID。**

7. 你将被要求提供你的凭据和同意。 忽略页面重定向。

8. 在 PowerShell 窗口中，你将收到访问令牌和刷新令牌。 保存刷新令牌以配置 SIEM 连接器。

### <a name="step-3-allow-your-application-on-microsoft-365-defender"></a>步骤 3：允许应用程序Microsoft 365 Defender

你需要允许你在应用程序中创建的应用程序Microsoft 365 Defender。

你需要具有管理门户 **系统设置权限** 才能允许应用程序。 否则，你将需要请求客户允许应用。

1. 转到 `https://security.microsoft.com?tid=<customer_tenant_id>` (客户的租户 ID \<customer_tenant_id\> 替换。

2. 单击 **设置** \>  \> **终结点 API** \> **SIEM"**。

3. 选择 **"MSSP"** 选项卡。

4. 输入 **第一步** 中的应用程序 ID 和租户 **ID。**

5. 单击"**授权应用程序"。**

现在，你可以下载 SIEM 的相关配置文件并连接到 Microsoft 365 Defender API。 有关详细信息，请参阅将 [警报拉取到 SIEM 工具](configure-siem.md)。

- 在 ArcSight 配置文件/Splunk 身份验证属性文件中，通过设置密码值手动编写应用程序密钥。
- 使用上一步中的脚本获取刷新令牌， (获取刷新令牌，而不是在门户中获取刷新) 。

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>使用 API 从 MSSP 客户的租户提取警报

有关如何使用 REST API 获取警报的信息，请参阅 [从 MSSP 客户租户获取警报](fetch-alerts-mssp.md)。

## <a name="see-also"></a>另请参阅

- [授予 MSSP 对门户的访问权限](grant-mssp-access.md)
- [访问 MSSP 客户门户](access-mssp-portal.md)
- [配置警报通知](configure-mssp-notifications.md)
