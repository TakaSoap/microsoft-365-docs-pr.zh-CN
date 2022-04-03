---
title: 创建应用以在没有用户Microsoft 365 Defender访问用户
description: 了解如何创建应用以在没有用户Microsoft 365 Defender访问应用程序。
keywords: 应用， 访问， api， 创建
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
ms.openlocfilehash: 01d6a00bba5bd286e6c741dce6ec6ba3fa3625a1
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755619"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>创建应用以在没有用户Microsoft 365 Defender访问用户

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

此页面介绍如何创建应用程序，在没有定义Microsoft 365 Defender（例如，创建守护程序或后台服务时）以编程方式访问应用程序。

如果你需要代表一个或多个用户以编程方式访问 Microsoft 365 Defender，请参阅创建应用以代表用户访问 [Microsoft 365 Defender](api-create-app-user-context.md) API 和 创建具有合作伙伴对 [Microsoft 365 Defender API](api-partner-access.md) 的访问权限的应用。 如果不确定需要哪种类型的访问，请参阅 [入门](api-access.md)。

Microsoft 365 Defender通过一组编程 API 公开其大部分数据和操作。 这些 API 可帮助您自动化工作流，并充分利用Microsoft 365 Defender功能。 此 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

通常，你将需要执行以下步骤来使用这些 API：

- 创建Azure Active Directory (Azure AD) 应用程序。
- 使用此应用程序获取访问令牌。
- 使用令牌访问 Microsoft 365 Defender API。

本文介绍如何：

- 创建 Azure AD 应用程序
- 获取访问令牌以Microsoft 365 Defender
- 验证令牌。

## <a name="create-an-app"></a>创建应用

1. 以具有全局管理员角色的用户 **登录** [Azure](https://portal.azure.com)。

2. 导航到 **Azure Active Directory** >  **App 注册** > **新注册**。

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Microsoft 365 Defender门户中的&quot;新建注册&quot;选项卡" lightbox="../../media/atp-azure-new-app2.png":::

3. 在表单中，选择应用程序的名称，然后选择"注册 **"**。

4. 在应用程序页面上，选择 **"API** >  权限 **"** > "我的组织使用的 API">**"Microsoft 威胁** 防护"，然后选择 **"Microsoft 威胁防护"**。 你的应用现在可以访问Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威胁防护* 是 Microsoft 威胁防护Microsoft 365 Defender名称，不会显示在原始列表中。 你需要开始在文本框中写入其名称，以查看其显示。

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="企业门户中的组织的 API Microsoft 365 Defender选项卡" lightbox="../../media/apis-in-my-org-tab.PNG":::

5. 选择 **"应用程序权限"**。 为方案选择相关权限 (例如 **Incident.Read.All**) ，然后选择" **添加权限"**。

   :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="应用程序门户中的应用程序Microsoft 365 Defender窗格" lightbox="../../media/request-api-permissions.PNG":::

    > [!NOTE]
    > 您需要为方案选择相关权限。 *读取所有事件* 只是一个示例。 若要确定所需的权限，请查看要调用的 API 中的"权限"部分。
    >
    > 例如，若要 [运行高级查询，](api-advanced-hunting.md)请选择"运行高级查询"权限;若要 [隔离设备，](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)请选择"隔离计算机"权限。

6. 选择 **"授予管理员同意"**。 每次添加权限时，都必须选择"授予管理员 **同意** ，让权限生效"。

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="门户中与同意授予Microsoft 365 Defender窗格" lightbox="../../media/grant-consent.PNG":::

7. 若要将密码添加到应用程序，请选择"证书& **密码"**，向密码添加说明，然后选择"添加 **"**。

    > [!TIP]
    > 选择"添加 **"后**， **选择"复制生成的机密值"**。 离开后将无法检索密码值。

    :::image type="content" source="../../media/defender-endpoint/webapp-create-key2.png" alt-text="应用程序门户中的Microsoft 365 Defender窗格" lightbox="../../media/defender-endpoint/webapp-create-key2.png":::

8. 在安全的地方记录应用程序 ID 和租户 ID。 它们列在应用程序 **页面上的"** 概述"下。

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender门户中的&quot;概述&quot;窗格" lightbox="../../media/app-and-tenant-ids.png":::

9. **仅Microsoft 365 Defender** 合作伙伴：按照以下说明 [](./api-partner-access.md)通过 Microsoft 365 Defender API 访问合作伙伴，将应用设置为多租户，以便一旦收到管理员同意，它就可以在所有租户中提供。 第三 **方** 应用需要合作伙伴访问权限，例如，如果你创建一个旨在在多个客户的租户中运行的应用。 如果 **创建的** 服务仅在租户中运行（例如，供自己使用的应用程序，仅与你自己的数据交互）不需要。 若要将应用设置为多租户：

    - 转到 **"身份验证**"，并添加 https://portal.azure.com 为 **重定向 URI**。

    - 在页面底部的 **"支持的帐户** 类型"下，选择多租户应用的任何组织目录应用程序中的"帐户"。

    由于应用程序代表Microsoft 365 Defender应用程序进行交互，因此需要针对要使用它的每一个租户批准该应用程序。

    每个租户的 Active Directory 全局管理员需要选择同意链接并批准你的应用。

    同意链接具有以下结构：

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    数字应 `00000000-0000-0000-0000-000000000000` 替换为应用程序 ID。  

**完成！** 已成功注册应用程序！ 有关令牌获取和验证，请参阅以下示例。

## <a name="get-an-access-token"></a>获取访问令牌

有关令牌Azure Active Directory，请参阅Azure AD[教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> 尽管本节中的示例鼓励您粘贴机密值以进行测试，但您永远不应将密码硬编码到生产中运行的应用程序。 第三方可以使用你的密码访问资源。 通过使用 Azure 密钥保管库，可帮助保护 [应用密钥的安全](/azure/key-vault/general/about-keys-secrets-certificates)。 有关如何保护应用的实际示例，请参阅使用 Azure Key Vault 管理服务器 [应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)。

### <a name="get-an-access-token-using-powershell"></a>使用 PowerShell 获取访问令牌

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

1. 将以下代码复制并粘贴到应用中 (不要忘记更新三个变量： `tenantId``clientId``appSecret` 、、) ：

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

### <a name="get-an-access-token-using-curl"></a>使用令牌获取访问令牌

> [!NOTE]
> 在版本 1803 Windows 10版本上预安装花器。 对于其他版本的 Windows，请直接从官方网站下载并[安装该工具](https://curl.haxx.se/windows/)。

1. 打开命令提示符，CLIENT_ID Azure 应用程序 ID。

1. 将CLIENT_SECRET设置为 Azure 应用程序密码。

1. 将TENANT_ID设置为想要使用你的应用访问你的应用的客户的 Azure Microsoft 365 Defender。

1. 运行以下命令：

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   成功的响应如下所示：

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>验证令牌

1. 将令牌复制并粘贴到 [JSON Web 令牌验证程序网站 JWT](https://jwt.ms) 中，以解码它。

1. 确保解码 *令牌* 中的角色声明包含所需的权限。

   在下图中，你可以看到从应用获取的解码令牌，具有 `Incidents.Read.All``Incidents.ReadWrite.All`、 和 `AdvancedHunting.Read.All` 权限：

   :::image type="content" source="../../media/defender-endpoint/webapp-decoded-token.png" alt-text="应用程序门户中的解码Microsoft 365 Defender窗格" lightbox="../../media/defender-endpoint/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>使用令牌访问 Microsoft 365 Defender API

1. 选择要用于事件或高级 (API) 。 有关详细信息，请参阅受支持的[Microsoft 365 Defender API](api-supported.md)。

2. 在即将发送的 `"Bearer" <token>`http 请求中，将授权标头设置为 ， *Bearer* 为授权方案， *令牌为经过* 验证的令牌。

3. 令牌将在一小时内过期。 在此期间，可以使用同一令牌发送多个请求。

以下示例演示如何发送请求，以使用事件 **C#。**

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
- [创建应用以Microsoft 365 Defender访问 API](api-create-app-user-context.md)
- [创建具有对 API 的多租户合作伙伴访问权限Microsoft 365 Defender应用程序](api-partner-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [使用 Azure Key Vault 管理服务器应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/)
- [用户登录和 API 访问的 OAuth 2.0 授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)