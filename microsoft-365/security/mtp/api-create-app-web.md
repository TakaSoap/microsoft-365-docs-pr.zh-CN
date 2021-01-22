---
title: 创建应用以在没有用户的情况下访问 Microsoft 365 Defender
description: 了解如何创建应用以在没有用户的情况下访问 Microsoft 365 Defender。
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
ms.openlocfilehash: f438189b4ba9fb66124650782b3de2ee34dfee64
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928434"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>创建应用以在没有用户的情况下访问 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

此页面介绍如何创建应用程序，以在没有定义用户的情况下以编程方式访问 Microsoft 365 Defender，例如，如果你要创建守护程序或后台服务。

如果你需要代表一个或多个用户以编程方式访问 Microsoft 365 Defender，请参阅"创建应用以代表用户访问 [Microsoft 365 Defender API"](api-create-app-user-context.md) 和"创建具有 [Microsoft 365 Defender](api-partner-access.md)API 合作伙伴访问权限的应用"。 如果不确定需要哪种类型的访问，请参阅["入门"。](api-access.md)

Microsoft 365 Defender 通过一组编程 API 公开其大部分数据和操作。 这些 API 可帮助你自动化工作流并充分利用 Microsoft 365 Defender 的功能。 此 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

通常，你需要执行以下步骤才能使用这些 API：

- 创建 Azure Active Directory (Azure AD) 应用程序。
- 使用此应用程序获取访问令牌。
- 使用令牌访问 Microsoft 365 Defender API。

本文介绍如何：

- 创建 Azure AD 应用程序
- 获取 Microsoft 365 Defender 的访问令牌
- 验证令牌。

## <a name="create-an-app"></a>创建应用

1. 以具有 [全局管理员](https://portal.azure.com)角色的用户登录 **Azure。**

2. 导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册**。

   ![Microsoft Azure 的图像和到应用程序注册的导航](../../media/atp-azure-new-app2.png)

3. 在表单中，选择应用程序的名称，然后选择"注册 **"。**

4. 在应用程序页面上，选择 **"API** 权限添加我的组织使用> API，键入 Microsoft 威胁防护，然后选择  >    >  Microsoft **威胁防护**。  你的应用现在可以访问 Microsoft 365 Defender。

   > [!TIP]
   > *Microsoft 威胁防护* 是 Microsoft 365 Defender 的以前名称，不会显示在原始列表中。 你需要开始在文本框中写入其名称，以查看其显示。

   ![API 权限选择的图像](../../media/apis-in-my-org-tab.PNG)

5. 选择 **应用程序权限**。 选择方案的相关权限，例如 (**Incident.Read.All**) ，然后选择"添加 **权限"。**

   ![API 访问和 API 选择的图像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > 需要为方案选择相关权限。 *读取所有事件* 只是一个示例。 若要确定所需的权限，请查看要调用的 API中的"权限"部分。
    >
    > 例如，若要 [运行高级查询](api-advanced-hunting.md)，请选择"运行高级查询"权限;若要 [隔离设备，](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)请选择"隔离计算机"权限。

6. 选择 **"授予管理员同意"。** 每次添加权限时，都必须选择"授予 **管理员同意** "，它才能生效。

    ![授予权限的图像](../../media/grant-consent.PNG)

7. 若要向应用程序添加密码，请选择"证书&**密码，向** 密码添加说明，然后选择"添加 **"。**

    > [!TIP]
    > 选择"添加 **"** 后， **选择复制生成的密码值**。 离开后将无法检索密码值。

    ![创建应用密钥的图像](../../media/webapp-create-key2.png)

8. 将应用程序 ID 和租户 ID 记录在安全位置。 它们列在应用程序 **页上的"** 概述"下。

   ![已创建应用 ID 的图像](../../media/app-and-tenant-ids.png)

9. 仅适用于 **Microsoft 365 Defender**[合作伙伴：按照](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)以下说明通过 Microsoft 365 Defender API 访问合作伙伴，将应用设置为多租户，以便一旦收到管理员同意，它就可以在所有租户中提供。 第三 **方应用** 需要合作伙伴访问权限，例如，如果你创建一个旨在在多个客户的租户中运行的应用。 如果 **创建一** 个仅在租户中运行的服务（例如，用于你自己的用法的应用程序，该服务将仅与你自己的数据进行交互）则不需要。 若要将应用设置为多租户：

    - 转到 **身份验证**，并添加 https://portal.azure.com 为重定向 **URI。**

    - 在页面底部的"支持 **的帐户** 类型"下，选择多租户应用的任何组织 **目录应用程序许可** 中的帐户。

    由于应用程序代表用户与 Microsoft 365 Defender 进行交互，因此需要针对要使用它的每一个租户批准它。

    每个租户的 Active Directory 全局管理员需要选择同意链接并批准你的应用。

    许可链接具有以下结构：

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    数字 `00000000-0000-0000-0000-000000000000` 应替换为应用程序 ID。  

**完成！** 已成功注册应用程序！ 有关令牌获取和验证，请参阅以下示例。

## <a name="get-an-access-token"></a>获取访问令牌

有关 Azure Active Directory 令牌详细信息，请参阅 [Azure AD 教程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> 虽然本节中的示例鼓励您粘贴密码值以进行测试，但您永远不应将密码硬编码到生产中运行的应用程序。 第三方可以使用你的密码访问资源。 通过使用 Azure 密钥保管库，可帮助保护 [应用密钥的安全](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)。 有关如何保护应用的实际示例，请参阅使用 Azure Key Vault 管理服务器 [应用中的密钥](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。

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

1. 安装 NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。

1. 添加以下行：

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 将以下代码复制并粘贴到应用中 (请不要忘记更新三个变量 `tenantId` `clientId` `appSecret` ：、、) ：

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
> 在 Windows 10 版本 1803 及更高版本上预安装了百度。 对于其他版本的 Windows，请直接从官方网站下载 [并安装该工具](https://curl.haxx.se/windows/)。

1. 打开命令提示符，CLIENT_ID Azure 应用程序 ID。

1. 将CLIENT_SECRET Azure 应用程序密码。

1. 将TENANT_ID Azure 租户 ID 设置为想要使用你的应用访问 Microsoft 365 Defender 的客户的 Azure 租户 ID。

1. 运行以下命令：

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   成功的响应如下所示：

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>验证令牌

1. 将令牌复制并粘贴到 [JSON Web 令牌验证程序网站 JWT 中](https://jwt.ms) ，以解码它。

1. 确保解码 *令牌中* 的角色声明包含所需的权限。

   在下图中，你可以看到从应用获取的解码令牌，具有 `Incidents.Read.All` `Incidents.ReadWrite.All` 、 和 `AdvancedHunting.Read.All` 权限：

   ![令牌验证的图像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>使用令牌访问 Microsoft 365 Defender API

1. 选择要用于事件或高级搜寻 (API) 。 有关详细信息，请参阅支持的[Microsoft 365 Defender API。](api-supported.md)

2. 在即将发送的 http 请求中，将授权标头设置为 `"Bearer" <token>` *，Bearer* 为授权方案，令牌为经过验证的令牌。

3. 令牌将在一小时内过期。 在此期间，可以使用同一令牌发送多个请求。

以下示例演示如何发送请求，以使用 **C# 获取事件列表**。

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [访问 Microsoft 365 Defender API](api-access.md)
- [创建"Hello world"应用程序](api-hello-world.md)
- [创建应用以代表用户访问 Microsoft 365 Defender API](api-create-app-user-context.md)
- [创建具有对 Microsoft 365 Defender API 的多租户合作伙伴访问权限的应用](api-partner-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [使用 Azure Key Vault 管理服务器应用中的密钥](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [用户登录和 API 访问的 OAuth 2.0 授权](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
