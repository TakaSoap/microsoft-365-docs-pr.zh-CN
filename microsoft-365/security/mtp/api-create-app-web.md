---
title: 创建在没有用户的情况下访问 Microsoft 365 Defender 的应用程序
description: 了解如何创建在没有用户的情况下访问 Microsoft 365 Defender 的应用程序
keywords: 应用、访问、api、创建
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 446db803cc47bfd519642928a4a0257c4b3d57c8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846064"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>创建在没有用户的情况下访问 Microsoft 365 Defender 的应用程序

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

本页介绍如何创建应用程序，以在没有用户的情况下获取对 Microsoft 365 Defender 的编程访问权限。 如果需要以编程方式代表用户访问 Microsoft 365 Defender，请参阅 [Get access with user context](api-create-app-user-context.md)。 如果您不确定所需的访问权限，请参阅 [入门](api-access.md)。

Microsoft 365 Defender 通过一组编程 Api 公开其大部分数据和操作。 这些 Api 将帮助您基于 Microsoft 365 Defender 功能自动执行工作流和创新。 API 访问需要 OAuth 2.0 身份验证。 有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般情况下，您需要执行以下步骤来使用 Api：
-  (Azure AD) 应用程序创建 Azure Active Directory。
- 使用此应用程序获取访问令牌。
- 使用令牌访问 Microsoft 365 Defender API。

本文介绍如何创建 Azure AD 应用程序，获取 Microsoft 365 Defender 的访问令牌，并验证令牌。

## <a name="create-an-app"></a>创建应用程序

1. 使用具有 **全局管理员** 角色的用户登录到 [Azure](https://portal.azure.com) 。

2. 导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册** 。 

   ![Microsoft Azure 的图像和到应用程序注册的导航](../../media/atp-azure-new-app2.png)

3. 在 "注册" 表单中，选择您的应用程序的名称，然后选择 " **注册** "。

4. 若要使您的应用程序能够访问 Microsoft 365 Defender 并分配 it 权限，请在应用程序页上，选择 " **API 权限** "  >  **Add permission**  >  **"添加我的组织使用** > 的权限 api"，键入 **microsoft 365 Defender** ，然后选择 " **microsoft 365 defender** "。

   > [!NOTE]
   > Microsoft 365 Defender 不会显示在原始列表中。 您需要先在文本框中写入其名称，才能看到它的显示。

   ![API 访问和 API 选择的图像](../../media/apis-in-my-org-tab.PNG)

   - 选择 " **应用程序权限** " > 选择适用于您的方案的相关权限，例如 " **Incident. 全部** "，然后选择 " **添加权限** "。

   ![API 访问和 API 选择的图像](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >您需要选择适用于您的方案的相关权限，即 **"读取所有事件"** 就是一个示例。 若要确定所需的权限，请查看您想要调用的 API 中的 " **权限** " 部分。

5. 选择 " **授予同意** "。

     > [!NOTE]
     > 每次添加权限时，您都必须选择 " **授予许可** " 以使新权限生效。

    ![授予权限的图像](../../media/grant-consent.PNG)

6. 若要将机密添加到应用程序，请选择 " **证书 & 密码** "，将说明添加到密码，然后选择 " **添加** "。

    > [!NOTE]
    > 选择 " **添加** " 后，选择 **"复制生成的机密值"** 。 离开后，将无法检索此值。

    ![创建应用程序密钥的图像](../../media/webapp-create-key2.png)

7. 记下应用程序 ID 和租户 ID。 在应用程序页上，转到 " **概述** " 并复制以下项。

   ![已创建应用程序 id 的图像](../../media/app-and-tenant-ids.png)

8. **仅适用于 Microsoft 365 Defender 合作伙伴** 。 [请按照此处的说明进行操作](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)。 将您的应用程序设置为多租用 (同意后在所有租户中可用) 。 这是第三方应用程序 **所必需** 的 (例如，如果创建一个打算在多客户租户) 中运行的应用程序。 如果创建要仅在租户中运行的服务，则不需要这样做 (例如，如果为自己的使用创建一个仅与您自己的数据) 交互的应用程序，则 **不需要** 这样做。 若要将您的应用程序设置为多租用，请执行以下操作：

    - 转到 " **身份验证** "，并添加 https://portal.azure.com 为 **重定向 URI** 。

    - 在页面底部的 " **支持的帐户类型** " 下，选择针对你的多租户应用的 **任何组织目录** 应用程序中的帐户。

    您需要在要使用的每个租户中批准您的应用程序。 这是因为您的应用程序代表您的客户交互 Microsoft 365 Defender。

    如果您正在编写第三方应用程序，则 (或您的客户) 需要选择许可链接并批准您的应用程序。 应使用在 Active Directory 中具有管理权限的用户来完成许可。

    同意链接的格式如下： 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    其中，00000000-0000-0000-0000-000000000000 替换为您的应用程序 ID。


**为了!** 已成功注册应用程序！ 有关令牌获取和验证，请参阅下面的示例。

## <a name="get-an-access-token"></a>获取访问令牌

有关 Azure AD 令牌的更多详细信息，请参阅 [AZURE ad 教程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

### <a name="use-powershell"></a>使用 PowerShell

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a>使用 c #：

以下代码使用 Nuget Microsoft.identitymodel.dll 3.19.8 进行测试。

1. 创建新的控制台应用程序。
1. 安装 Nuget [microsoft.identitymodel.dll](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。
1. 添加以下内容：

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 在应用程序中复制并粘贴以下代码 (不会忘记更新三个变量： ```tenantId, appId, appSecret```) ：

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>使用 Python 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a>使用卷

> [!NOTE]
> 以下过程假定已在您的计算机上安装了 Windows 卷。

1. 打开命令提示符，并将 CLIENT_ID 设置为您的 Azure 应用程序 ID。
1. 将 CLIENT_SECRET 设置为您的 Azure 应用程序密码。
1. 将 TENANT_ID 设置为要使用您的应用程序访问 Microsoft 365 Defender 的客户的 Azure 租户 ID。
1. 运行以下命令：

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

您将获得以下形式的答案：

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>验证令牌

确保您获得了正确的令牌：

1. 将您在上一步中获取的令牌复制并粘贴到 [JWT](https://jwt.ms) ，以便对其进行解码。
1. 验证是否获取了具有所需权限的 "roles" 声明
1. 在下图中，你可以看到从应用获取的解码令牌 ```Incidents.Read.All``` ， ```Incidents.ReadWrite.All``` 以及 ```AdvancedHunting.Read.All``` 权限：

![令牌验证的图像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a>使用令牌访问 Microsoft 365 Defender API

1. 选择要使用的 API。 有关详细信息，请参阅 [支持的 Microsoft 365 Defender api](api-supported.md)。

2. 在发送到 "持有者 {令牌}" 的 http 请求中设置授权标头， (持有者是) 的授权方案。

3. 令牌的过期时间为1小时。 您可以发送多个具有相同令牌的请求。

下面的示例演示如何 **使用 c #** 发送获取事件列表的请求： 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>相关主题
- [访问 Microsoft 365 Defender Api](api-access.md)
- [使用应用程序上下文访问 Microsoft 365 Defender](api-create-app-web.md)
- [使用用户上下文访问 Microsoft 365 Defender](api-create-app-user-context.md)
