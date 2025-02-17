---
title: 创建应用以在没有用户的情况下访问 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 了解如何设计 Web 应用，无需用户即可以编程方式访问 Microsoft Defender for Endpoint。
keywords: api， 图形 api， 受支持的 api， 参与者， 警报， 设备， 用户， 域， ip， 文件， 高级搜寻， 查询
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c26bc9762b76deff0dddb04f98e2630e789ee6b5
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474456"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a>创建应用以在没有用户的情况下访问 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：** 
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

此页面介绍如何创建应用程序，以在没有用户的情况下以编程方式访问 Defender for Endpoint。 如果你需要代表用户以编程方式访问 Defender for Endpoint，请参阅使用 [用户上下文获取访问权限](exposed-apis-create-app-nativeapp.md)。 如果您不确定所需的访问权限，请参阅 [入门](apis-intro.md)。

Microsoft Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。 这些 API 将帮助你自动执行基于 Defender for Endpoint 功能的工作流和创新。 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

通常，你将需要执行以下步骤来使用 API：
- 创建Azure Active Directory (Azure AD) 应用程序。
- 使用此应用程序获取访问令牌。
- 使用令牌访问 Defender for Endpoint API。

本文介绍如何创建一个 Azure AD 应用程序、获取 Microsoft Defender for Endpoint 的访问令牌以及验证令牌。

## <a name="create-an-app"></a>创建应用

1. 使用具有全局管理员角色 **的用户登录到** [Azure](https://portal.azure.com)。

2. 导航到 **Azure Active Directory** \> **应用注册""** \> **新注册"**。 

    :::image type="content" source="images/atp-azure-new-app2.png" alt-text="应用程序注册窗格" lightbox="images/atp-azure-new-app2.png":::

3. 在注册表单中，选择应用程序的名称，然后选择"注册 **"**。

4. 若要使你的应用能够访问适用于终结点的 Defender 并为其分配"读取所有警报"权限，请在应用程序页面上，选择 **"API** \>  \> 权限""添加我的组织 **使用 > 的权限** API"，键入 **WindowsDefenderATP**，然后选择 **"WindowsDefenderATP**"。

   > [!NOTE]
   > *WindowsDefenderATP* 不会显示在原始列表中。 开始在文本框中写入其名称，以查看其显示。

   :::image type="content" source="images/add-permission.png" alt-text="&quot;API 权限&quot;窗格" lightbox="images/add-permission.png":::

   选择 **"应用程序权限** \> **Alert.Read.All**"，然后选择" **添加权限"**。

   :::image type="content" source="images/application-permissions.png" alt-text="应用程序权限信息窗格" lightbox="images/application-permissions.png":::

     您需要选择相关权限。 "读取所有警报"只是一个示例。 例如：

     - 若要 [运行高级查询，](run-advanced-query-api.md)请选择"运行高级查询"权限。
     - 若要 [隔离设备，](isolate-machine.md)请选择"隔离计算机"权限。
     - 若要确定所需的权限，请查看要调用的  API 中的"权限"部分。

5. 选择 **"授予同意"**。

     > [!NOTE]
     > 每次添加权限时，都必须选择"授予 **同意** "，新权限才能生效。

    :::image type="content" source="images/grant-consent.png" alt-text="&quot;授予权限&quot;页" lightbox="images/grant-consent.png":::

6. 若要将密码添加到应用程序，请选择"证书& **密码"**，向密码添加说明，然后选择"添加 **"**。

    > [!NOTE]
    > 选择"添加 **"后**， **选择"复制生成的机密值"**。 离开后将无法检索此值。

      :::image type="content" source="images/webapp-create-key2.png" alt-text="创建应用程序选项" lightbox="images/webapp-create-key2.png":::

7. 记下应用程序 ID 和租户 ID。 在应用程序页面上，转到" **概述"** 并复制以下内容。

   :::image type="content" source="images/app-and-tenant-ids.png" alt-text="已创建的应用和租户 ID" lightbox="images/app-and-tenant-ids.png":::

8. **仅适用于适用于终结点合作伙伴的 Microsoft Defender**。 同意后，将应用设置为 (租户中可用的多租户) 。 例如 **，** 如果你创建一个旨在在多个客户的租户 (运行的应用，则第三方应用需要) 。 如果 **创建的服务仅在** 租户中运行，则无需这样做 (例如，如果创建一个应用程序供自己使用，而该应用程序仅与你自己的数据记录进行交互) 。 若要将应用设置为多租户：

    - 转到 **"身份验证**"，并添加 `https://portal.azure.com` 为 **重定向 URI**。

    - 在页面底部的 **"支持的帐户** 类型"下，选择多租户应用的任何组织目录应用程序中的"帐户"。

    你需要在打算使用应用程序的每个租户中批准你的应用程序。 这是因为应用程序代表你的客户与 Defender for Endpoint 交互。

    如果你 (需要选择同意链接并批准你的应用的第三方应用，) 或你的客户。 应在 Active Directory 中拥有管理权限的用户征得同意。

    同意链接格式如下： 

    ```https
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    其中，00000000-0000-0000-0000-0000000000000 将替换为应用程序 ID。


**完成！** 已成功注册应用程序！ 有关令牌获取和验证，请参阅以下示例。

## <a name="get-an-access-token"></a>获取访问令牌

有关令牌Azure AD，请参阅Azure AD[教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

### <a name="use-powershell"></a>使用 PowerShell

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
```

### <a name="use-c"></a>使用C#：

使用 Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 NuGet测试了以下代码。

1. 创建新的控制台应用程序。
1. 安装NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。
1. 添加以下内容：

    ```csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 在应用中复制并粘贴以下 (请不要忘记更新三个变量： ```tenantId, appId, appSecret```) ：

    ```csharp
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>使用 Python

请参阅 [使用 Python 获取令牌](run-advanced-query-sample-python.md#get-token)。

### <a name="use-curl"></a>使用时

> [!NOTE]
> 以下过程假定计算机上已安装 Windows 的一部分。

1. 打开命令提示符，CLIENT_ID Azure 应用程序 ID。
1. 将CLIENT_SECRET设置为 Azure 应用程序密码。
1. 将TENANT_ID设置为想要使用你的应用访问 Defender for Endpoint 的客户的 Azure 租户 ID。
1. 运行以下命令：

    ```console
    curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
    ```
    
    您将获得以下形式的答案：
    
    ```console
    {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
    ```
    
## <a name="validate-the-token"></a>验证令牌

确保你收到了正确的令牌：

1. 将上一步获取的令牌复制并粘贴到 [JWT](https://jwt.ms) 中，以便解码它。

1. 验证您是否获得具有所需权限的"角色"声明。

   在下图中，你可以看到从应用获取的解码令牌，该应用具有对 Endpoint 的所有 Microsoft Defender 角色的权限：

   :::image type="content" source="images/webapp-decoded-token.png" alt-text="令牌详细信息部分" lightbox="images/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>使用令牌访问 Microsoft Defender for Endpoint API

1. 选择想要使用的 API。 有关详细信息，请参阅支持的 [Defender for Endpoint API](exposed-apis-list.md)。
1. 将你发送到"Bearer {token}"的 http 请求中的授权标头 (Bearer 是授权方案) 。
1. 令牌的过期时间为一小时。 可以使用同一令牌发送多个请求。

下面是使用请求获取警报列表的一个示例 **C#：**

```csharp
var httpClient = new HttpClient();

var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

// Do something useful with the response
```

## <a name="see-also"></a>另请参阅
- [支持的 Microsoft Defender for Endpoint API](exposed-apis-list.md)
- [代表用户访问 Microsoft Defender for Endpoint](exposed-apis-create-app-nativeapp.md)
