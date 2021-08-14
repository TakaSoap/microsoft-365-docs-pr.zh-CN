---
title: 合作伙伴通过 Microsoft 365 Defender API 访问
description: 了解如何创建应用以代表用户Microsoft 365 Defender访问应用程序。
keywords: 合作伙伴， 访问， api， 多租户， 同意， 访问令牌， 应用
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a930b04db04eff491cd646634c9cbbd2595629030e7d6c5f5de095f6fc4ca9cf
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53810487"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>创建具有合作伙伴对 api Microsoft 365 Defender访问权限的应用

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

此页面介绍如何创建一个Azure Active Directory应用程序，该应用可代表多个租户中的Microsoft 365 Defender以编程方式访问应用程序。 多租户应用可用于为大型用户组服务。

如果你需要以编程方式Microsoft 365 Defender单个用户访问，请参阅创建应用以代表用户Microsoft 365 Defender [API。](api-create-app-user-context.md) 如果需要在没有用户显式定义的 (的情况下访问，例如，如果要编写后台应用或守护程序) ，请参阅创建应用以在没有用户[Microsoft 365 Defender](api-create-app-web.md)访问。 如果你不确定需要哪种类型的访问，请参阅 [入门](api-access.md)。

Microsoft 365 Defender通过一组编程 API 公开其大部分数据和操作。 这些 API 可帮助您自动化工作流，并充分利用Microsoft 365 Defender功能。 此 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

通常，你将需要执行以下步骤来使用这些 API：

- 创建 Azure AD Azure Active Directory (应用程序) 应用程序。
- 使用此应用程序获取访问令牌。
- 使用令牌访问 Microsoft 365 Defender API。

由于此应用是多租户应用，你还需要代表其用户[](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant)获得每个租户的管理员同意。

本文介绍如何：

- 创建 **多租户** Azure AD 应用程序
- 获取应用程序的用户管理员授权，以访问Microsoft 365 Defender所需的资源。
- 获取访问令牌以Microsoft 365 Defender
- 验证令牌

Microsoft 365 Defender通过一组编程 API 公开其大部分数据和操作。 这些 API 将帮助你根据功能自动化Microsoft 365 Defender创新。 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

通常，你将需要执行以下步骤来使用 API：

- 创建 **多租户** Azure AD 应用程序。
- 获取 (同意) 管理员同意应用程序访问所需的Microsoft 365 Defender资源。
- 使用此应用程序获取访问令牌。
- 使用令牌访问 Microsoft 365 Defender API。

以下步骤将指导你如何创建多租户 Azure AD 应用程序、获取访问令牌Microsoft 365 Defender并验证令牌。

## <a name="create-the-multi-tenant-app"></a>创建多租户应用

1. 以具有全局管理员角色的用户 **登录** [Azure。](https://portal.azure.com)

2. 导航到 **Azure Active Directory**  >  **应用注册**  >  **""新注册"。**

   ![应用程序注册Microsoft Azure导航的图像](../../media/atp-azure-new-app2.png)

3. 在注册表单中：

   - 为应用程序选择一个名称。
   - 从 **"支持的帐户类型"中**，选择"任何组织目录中的帐户 **(任何 Azure AD 目录) - 多租户"**。
   - 填写重定向 **URI** 部分。 选择类型 **"Web"，** 将重定向 URI 作为 **https://portal.azure.com** 提供。

   填写完表单后，选择"注册 **"。**

   !["注册应用程序"表单的图像](../..//media/atp-api-new-app-partner.png)

4. 在应用程序页面上，选择 **"API** 权限""添加我的组织使用>  >    >   API"，键入 **"Microsoft 威胁** 防护"，然后选择 **"Microsoft 威胁防护"。** 你的应用现在可以访问Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威胁防护* 是 Microsoft 威胁防护Microsoft 365 Defender名称，不会显示在原始列表中。 你需要开始在文本框中写入其名称，以查看其显示。

   ![API 权限选择的图像](../../media/apis-in-my-org-tab.PNG)

5. 选择 **"应用程序权限"。** 为方案选择相关权限 (例如 **，Incident.Read.All**) ，然后选择"**添加权限"。**

   ![API 访问和 API 选择的图像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > 您需要为方案选择相关权限。 *读取所有事件* 只是一个示例。 若要确定所需的权限，请查看要调用的 API中的"权限"部分。
    >
    > 例如，若要 [运行高级查询](api-advanced-hunting.md)，请选择"运行高级查询"权限;若要 [隔离设备](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)，请选择"隔离计算机"权限。

6. 选择 **"授予管理员同意"。** 每次添加权限时，都必须选择"授予管理员 **同意** ，让权限生效"。

    ![授予权限的图像](../../media/grant-consent.PNG)

7. 若要将密码添加到应用程序，请选择"证书&**密码"，** 向密码添加说明，然后选择"添加 **"。**

    > [!TIP]
    > 选择"添加 **"后**，**选择"复制生成的机密值"。** 离开后将无法检索密码值。

    ![创建应用密钥的图像](../../media/webapp-create-key2.png)

8. 在安全的地方记录应用程序 ID 和租户 ID。 它们列在应用程序 **页面上的"** 概述"下。

   ![已创建应用 ID 的图像](../../media/app-and-tenant-ids.png)

9. 将应用程序添加到用户的租户。

   由于应用程序代表Microsoft 365 Defender应用程序进行交互，因此需要针对要使用它的每一个租户批准该应用程序。

   **用户租户** 中的全局管理员需要查看同意链接并批准你的应用程序。

   同意链接的形式为：

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   数字 `00000000-0000-0000-0000-000000000000` 应替换为应用程序 ID。

   单击同意链接后，使用用户租户的全局管理员登录并许可应用程序。

   ![同意图像](../../media/app-consent-partner.png)

   你还需要向用户询问其租户 ID。 租户 ID 是用于获取访问令牌的标识符之一。

- **完成！** 已成功注册应用程序！
- 有关令牌获取和验证，请参阅以下示例。

## <a name="get-an-access-token"></a>获取访问令牌

有关 Azure AD 令牌详细信息，请参阅 [Azure AD 教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> 尽管本节中的示例鼓励您粘贴机密值以进行测试，但您永远不应将密码硬编码到生产中运行的应用程序。 第三方可以使用你的密码访问资源。 通过使用 Azure 密钥保管库，可帮助保护 [应用密钥的安全](/azure/key-vault/general/about-keys-secrets-certificates)。 有关如何保护应用的实际示例，请参阅使用 Azure Key Vault 管理 [服务器应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)。

> [!TIP]
> 在下面的示例中，使用用户的租户 ID 测试脚本是否正常工作。

### <a name="get-an-access-token-using-powershell"></a>使用 PowerShell 获取访问令牌

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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

### <a name="get-an-access-token-using-c"></a>使用 C 获取访问令牌\#

> [!NOTE]
> 以下代码已使用 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 进行测试。

1. 创建新的控制台应用程序。
1. 安装NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。
1. 添加以下行：

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 将以下代码复制并粘贴到应用中 (请不要忘记更新三个 `tenantId` `clientId` `appSecret` 变量：、、) ：

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a>使用 Python 获取访问令牌

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a>使用令牌获取访问令牌

> [!NOTE]
> 在版本 1803 Windows 10版本上预安装版本。 对于其他版本的 Windows，请直接从官方网站下载并[安装该工具](https://curl.haxx.se/windows/)。

1. 打开命令提示符，CLIENT_ID Azure 应用程序 ID。
1. 将CLIENT_SECRET Azure 应用程序密码。
1. 将TENANT_ID设置为想要使用你的应用访问应用的用户的 Azure Microsoft 365 Defender。
1. 运行以下命令：

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

成功的响应如下所示：

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>验证令牌

1. 将令牌复制并粘贴到 [JSON Web 令牌验证程序网站 JWT](https://jwt.ms) 中，以解码它。
1. 确保解码 *令牌* 中的角色声明包含所需的权限。

在下图中，你可以看到从应用获取的解码令牌，具有 、 和 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 权限：

![令牌验证图像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>使用令牌访问 Microsoft 365 Defender API

1. 选择要用于事件或高级搜寻 () API。 有关详细信息，请参阅受支持的[Microsoft 365 Defender API。](api-supported.md)
2. 在即将发送的 http 请求中，将授权标头设置为 `"Bearer" <token>` *，Bearer* 为授权方案，令牌为经过验证的令牌。
3. 令牌将在一小时内过期。 在此期间，可以使用同一令牌发送多个请求。

以下示例演示如何发送请求，以使用 C# 获取 **事件列表**。

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>相关文章

- [Microsoft 365 DefenderAPI 概述](api-overview.md)
- [访问Microsoft 365 Defender API](api-access.md)
- [创建"Hello world"应用程序](api-hello-world.md)
- [创建应用以在没有用户Microsoft 365 Defender访问用户](api-create-app-web.md)
- [创建应用以Microsoft 365 Defender用户访问 API](api-create-app-user-context.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [使用 Azure Key Vault 管理服务器应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)
- [用户登录和 API 访问的 OAuth 2.0 授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)