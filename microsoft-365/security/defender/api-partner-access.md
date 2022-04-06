---
title: 通过Microsoft 365 Defender API 进行合作伙伴访问
description: 了解如何创建应用，以代表用户以编程方式访问Microsoft 365 Defender。
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
ms.openlocfilehash: ccd92b38937bcb64fdcf738b803160119c0a025a
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665571"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>创建具有合作伙伴访问Microsoft 365 Defender API 的应用

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

本页介绍如何创建一个Azure Active Directory应用，该应用代表多个租户中的用户以编程方式访问Microsoft 365 Defender。 多租户应用可用于为大型用户组提供服务。

如果需要以编程方式代表单个用户访问Microsoft 365 Defender，请参阅["创建应用"以代表用户访问Microsoft 365 Defender API](api-create-app-user-context.md)。 例如，如果没有用户显式定义的 (需要访问权限，如果正在编写后台应用或守护程序) ，请参阅[创建一个应用，以便在没有用户的情况下访问Microsoft 365 Defender](api-create-app-web.md)。 如果不确定需要哪种访问权限，请参阅[开始](api-access.md)。

Microsoft 365 Defender通过一组编程 API 公开其大部分数据和操作。 这些 API 可帮助你自动化工作流并利用Microsoft 365 Defender的功能。 此 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请[参阅 OAuth 2.0 授权代码Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般情况下，需要执行以下步骤来使用这些 API：

- 创建Azure Active Directory (Azure AD) 应用程序。
- 使用此应用程序获取访问令牌。
- 使用令牌访问Microsoft 365 Defender API。

由于此应用是多租户的，因此还需要代表每个租户的用户征得 [管理员同意](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 。

本文介绍如何：

- 创建 **多租户** Azure AD应用程序
- 获得用户管理员的授权许可，让应用程序访问所需的资源Microsoft 365 Defender。
- 获取访问令牌以Microsoft 365 Defender
- 验证令牌

Microsoft 365 Defender通过一组编程 API 公开其大部分数据和操作。 这些 API 将帮助你自动化工作流，并基于Microsoft 365 Defender功能进行创新。 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请[参阅 OAuth 2.0 授权代码Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般情况下，需要执行以下步骤来使用 API：

- 创建 **多租户** Azure AD应用程序。
- 获取用户管理员) 的授权 (许可，让应用程序访问所需的Microsoft 365 Defender资源。
- 使用此应用程序获取访问令牌。
- 使用令牌访问Microsoft 365 Defender API。

以下步骤介绍了如何创建多租户Azure AD应用程序、获取访问令牌以Microsoft 365 Defender和验证令牌。

## <a name="create-the-multi-tenant-app"></a>创建多租户应用

1. 以具有 **全局管理员** 角色的用户身份登录 [到 Azure](https://portal.azure.com)。

2. 导航到 **Azure Active Directory** > **应用注册** > **新注册**。

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Microsoft 365 Defender门户中的应用程序注册部分" lightbox="../../media/atp-azure-new-app2.png":::

3. 在注册表单中：

   - 为应用程序选择名称。
   - 从 **支持的帐户类型** 中，选择 **任何组织目录中的帐户 (任何Azure AD目录) - 多租户**。
   - 填写 **"重定向 URI"** 部分。 选择" **Web** 类型"，并提供重定向 URI 作为 **https://portal.azure.com**。

   填写完窗体后，选择 **"注册**"。

   :::image type="content" source="../..//media/atp-api-new-app-partner.png" alt-text="Microsoft 365 Defender门户中的应用程序注册部分" lightbox="../..//media/atp-api-new-app-partner.png":::

4. 在应用程序页上，选择组织使用的 **API PermissionsAdd** >  **权限** >  **API** >，键入 **Microsoft 威胁防护**，然后选择 **Microsoft 威胁防护**。 你的应用现在可以访问Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威胁防护* 是前Microsoft 365 Defender名称，不会显示在原始列表中。 需要开始在文本框中写入其名称才能看到它出现。

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Microsoft 365 Defender门户中的 API 使用情况部分" lightbox="../../media/apis-in-my-org-tab.PNG":::

5. 选择 **应用程序权限**。 选择方案的相关权限 (例如 **Incident.Read.All**) ，然后选择 **"添加权限**"。

   :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="Microsoft 365 Defender门户中的应用程序权限窗格" lightbox="../../media/request-api-permissions.PNG":::

    > [!NOTE]
    > 需要为方案选择相关权限。 *读取所有事件* 只是一个示例。 若要确定所需的权限，请查看要调用的 API 中的" **权限** "部分。
    >
    > 例如，若要 [运行高级查询](api-advanced-hunting.md)，请选择"运行高级查询"权限：若要 [隔离设备](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)，请选择"隔离计算机"权限。

6. 选择 **"授予管理员同意**"。 每次添加权限时，都必须选择 **"授予管理员许可** "才能生效。

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="在Microsoft 365 Defender门户中授予管理员同意的部分" lightbox="../../media/grant-consent.PNG":::

7. 若要向应用程序添加机密，请选择 **"证书"&机密**，向机密添加说明，然后选择 **"添加**"。

    > [!TIP]
    > 选择 **"添加**"后，选择 **复制生成的机密值**。 离开后将无法检索机密值。

      :::image type="content" source="../../media/webapp-create-key2.png" alt-text="Microsoft 365 Defender门户中的&quot;机密添加&quot;部分" lightbox="../../media/webapp-create-key2.png":::

8. 在安全的位置记录应用程序 ID 和租户 ID。 它们在应用程序页面的 **"概述** "下列出。

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender门户中的&quot;概述&quot;窗格" lightbox="../../media/app-and-tenant-ids.png":::

9. 将应用程序添加到用户的租户。

   由于应用程序代表用户与Microsoft 365 Defender交互，因此需要为要对其使用它的每个租户批准该应用程序。

   用户租户中的 **全局管理员** 需要查看许可链接并批准应用程序。

   许可链接采用以下形式：

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   这些数字 `00000000-0000-0000-0000-000000000000` 应替换为应用程序 ID。

   单击同意链接后，请与用户租户的全局管理员登录并同意该应用程序。

   :::image type="content" source="../../media/app-consent-partner.png" alt-text="Microsoft 365 Defender门户中的许可应用程序页" lightbox="../../media/app-consent-partner.png":::

   还需要向用户询问其租户 ID。 租户 ID 是用于获取访问令牌的标识符之一。

- **做！** 你已成功注册应用程序！
- 有关令牌获取和验证的示例，请参阅下面的示例。

## <a name="get-an-access-token"></a>获取访问令牌

有关Azure AD令牌的详细信息，请参阅[Azure AD教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> 尽管本部分中的示例鼓励你粘贴机密值以进行测试，但绝不应将 **机密硬编码** 到在生产环境中运行的应用程序中。 第三方可以使用机密访问资源。 可以使用 [Azure 密钥保管库](/azure/key-vault/general/about-keys-secrets-certificates)帮助保护应用的机密。 有关如何保护应用的实际示例，请参阅使用 [Azure 密钥保管库 管理服务器应用中的机密](/learn/modules/manage-secrets-with-azure-key-vault/)。

> [!TIP]
> 在以下示例中，使用用户的租户 ID 测试脚本是否正常工作。

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
> 使用 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 测试了以下代码。

1. 创建新的控制台应用程序。
1. 安装NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。
1. 添加以下行：

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 将以下代码复制并粘贴到应用 (不要忘记更新三个变量：`tenantId`， `clientId``appSecret`) ：

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

resourceAppIdUri = 'https://api.security.microsoft.com'

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

### <a name="get-an-access-token-using-curl"></a>使用 curl 获取访问令牌

> [!NOTE]
> Curl 已在 Windows 10 版本 1803 及更高版本上预安装。 对于其他版本的Windows，请直接从[官方 curl 网站](https://curl.haxx.se/windows/)下载并安装该工具。

1. 打开命令提示符，并将CLIENT_ID设置为 Azure 应用程序 ID。
1. 将CLIENT_SECRET设置为 Azure 应用程序机密。
1. 将TENANT_ID设置为想要使用应用访问Microsoft 365 Defender的用户的 Azure 租户 ID。
1. 运行以下命令：

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

成功的响应如下所示：

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>验证令牌

1. 将令牌复制并粘贴到 [JSON Web 令牌验证程序网站 JWT 中](https://jwt.ms) 进行解码。
1. 确保解码令牌中 *的角色* 声明包含所需的权限。

在下图中，可以看到从应用```Incidents.Read.All``````Incidents.ReadWrite.All``````AdvancedHunting.Read.All```获取的具有和权限的解码令牌：

:::image type="content" source="../../media/webapp-decoded-token.png" alt-text="Microsoft 365 Defender门户中的&quot;解码令牌&quot;窗格" lightbox="../../media/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>使用令牌访问Microsoft 365 Defender API

1. 选择要使用 (事件或高级搜寻) 的 API。 有关详细信息，请参阅[支持的Microsoft 365 Defender API](api-supported.md)。
2. 在即将发送的 http 请求中，将授权标头设置为`"Bearer" <token>`*"持有者* 为授权方案"，并将 *令牌* 设置为验证令牌。
3. 令牌将在一小时内过期。 在此期间，可以使用相同的令牌发送多个请求。

以下示例演示如何发送请求以 **使用 C#** 获取事件列表。

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [访问Microsoft 365 Defender API](api-access.md)
- [创建"Hello world"应用程序](api-hello-world.md)
- [创建应用以在没有用户的情况下访问Microsoft 365 Defender](api-create-app-web.md)
- [创建应用以代表用户访问Microsoft 365 Defender API](api-create-app-user-context.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [使用 Azure 密钥保管库管理服务器应用中的机密](/learn/modules/manage-secrets-with-azure-key-vault/)
- [用户登录和 API 访问的 OAuth 2.0 授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
