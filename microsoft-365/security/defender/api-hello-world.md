---
title: Hello World for Microsoft 365 Defender REST API
description: 了解如何创建应用并使用令牌访问 Microsoft 365 Defender API
keywords: 应用， 令牌， 访问， aad， 应用， 应用程序注册， powershell， 脚本， 全局管理员， 权限， microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: 3a8696a14b85374d4bcb0a8704c14b82fdd845b5
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754610"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World for Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

## <a name="get-incidents-using-a-simple-powershell-script"></a>使用简单的 PowerShell 脚本获取事件

完成此项目需要 5 到 10 分钟。 此时间估计包括注册应用程序，以及应用 PowerShell 示例脚本中的代码。

### <a name="register-an-app-in-azure-active-directory"></a>在应用商店中注册Azure Active Directory

1. 以具有全局管理员角色的用户 **登录** [Azure](https://portal.azure.com)。

2. 导航到 **Azure Active Directory** >  **App 注册** > **新注册**。

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Microsoft 365 Defender门户中的&quot;新建注册&quot;部分" lightbox="../../media/atp-azure-new-app2.png":::

3. 在注册表单中，选择应用程序的名称，然后选择"注册 **"**。 选择重定向 URI 是可选的。 完成此示例不需要一个。

4. 在应用程序页面上，选择 **"API** >  权限 **"** > "我的组织使用的 API">**"Microsoft 威胁** 防护"，然后选择 **"Microsoft 威胁防护"**。 你的应用现在可以访问Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威胁防护* 是 Microsoft 威胁防护Microsoft 365 Defender名称，不会显示在原始列表中。 你需要开始在文本框中写入其名称，以查看其显示。
   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="应用程序门户中的 API Microsoft 365 Defender部分" lightbox="../../media/apis-in-my-org-tab.PNG":::

   - 选择 **"应用程序权限** > **""Incident.Read.All** "，然后选择" **添加权限"**。

     :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="应用程序的权限窗格在 Microsoft 365 Defender 门户" lightbox="../../media/request-api-permissions.PNG":::

5. 选择 **"授予管理员同意"**。 每次添加权限时，都必须选择"授予管理员 **同意** ，让权限生效"。

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="管理员门户中的&quot;授予管理员Microsoft 365 Defender部分" lightbox="../../media/grant-consent.PNG":::

6. 向应用程序添加密码。 选择 **"&** 密码"，向密码添加说明，然后选择"添加 **"**。

    > [!TIP]
    > 选择"添加 **"后**， **选择"复制生成的机密值"**。 离开后将无法检索密码值。

    :::image type="content" source="../../media/webapp-create-key2.png" alt-text="门户中的&quot;添加密码&quot;Microsoft 365 Defender部分" lightbox="../../media/webapp-create-key2.png":::
    

7. 在安全的地方记录应用程序 ID 和租户 ID。 它们列在应用程序 **页面上的"** 概述"下。

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender门户中的概述部分" lightbox="../../media/app-and-tenant-ids.png":::

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>使用应用获取令牌并使用令牌访问 API

有关令牌Azure Active Directory，请参阅Azure AD[教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> 尽管此演示应用中的示例鼓励你为了测试目的粘贴机密值，但不应将密码硬编码到生产中运行的应用程序。 第三方可以使用你的密码访问资源。 通过使用 Azure 密钥保管库，可帮助保护 [应用密钥的安全](/azure/key-vault/general/about-keys-secrets-certificates)。 有关如何保护应用的实际示例，请参阅使用 Azure Key Vault 管理服务器 [应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)。

1. 复制下面的脚本并将其粘贴到最喜爱的文本编辑器中。 另存 **为Get-Token.ps1**。 您也可以在 PowerShell ISE 中像现在一样运行代码，但应保存它，因为我们将在下一节中使用事件提取脚本时再次运行它。

    此脚本将生成一个令牌，并将其保存在工作文件夹中的名称下， *Latest-token.txt*。

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

    $resourceAppIdUri = 'https://api.security.microsoft.com'
    $oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"
    $authBody = [Ordered] @{
      resource = $resourceAppIdUri
      client_id = $clientId
      client_secret = $appSecret
      grant_type = 'client_credentials'
    }
    $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
    $token = $authResponse.access_token
    Out-File -FilePath "./Latest-token.txt" -InputObject $token
    return $token
    ```

#### <a name="validate-the-token"></a>验证令牌

1. 将收到的令牌复制并粘贴到 [JWT](https://jwt.ms) 中以解码它。
1. *JWT* 代表 *JSON Web 令牌*。 解码的令牌将包含许多 JSON 格式的项目或声明。 确保解码 *令牌* 中的角色声明包含所需的权限。

    在下图中，你可以看到从应用获取的解码令牌，具有 ```Incidents.Read.All``````Incidents.ReadWrite.All```、 和 ```AdvancedHunting.Read.All``` 权限：

    :::image type="content" source="../../media/api-jwt-ms.png" alt-text="应用程序门户中的解码Microsoft 365 Defender部分" lightbox="../../media/api-jwt-ms.png":::

### <a name="get-a-list-of-recent-incidents"></a>获取最近事件的列表

下面的 **脚本将使用Get-Token.ps1** 访问 API。 然后，它将检索过去 48 小时内最后更新的事件列表，然后将该列表另存为 JSON 文件。

> [!IMPORTANT]
> 在保存脚本的同一文件夹中保存此 **Get-Token.ps1**。

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

全部完成！ 已成功：

- 创建并注册应用程序。
- 已授予该应用程序读取警报的权限。
- 已连接到 API。
- 使用 PowerShell 脚本返回过去 48 小时内更新的事件。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [访问Microsoft 365 Defender API](api-access.md)
- [创建应用以在没有用户Microsoft 365 Defender访问用户](api-create-app-web.md)
- [创建应用以Microsoft 365 Defender访问 API](api-create-app-user-context.md)
- [创建具有对 API 的多租户合作伙伴访问权限Microsoft 365 Defender应用程序](api-partner-access.md)
- [使用 Azure Key Vault 管理服务器应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 用户登录和 API 访问授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)