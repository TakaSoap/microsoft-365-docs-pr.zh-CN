---
title: 创建应用程序以在没有用户的情况下访问 Microsoft Defender for Endpoint
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
ms.openlocfilehash: 2705eb4e3010a06c707ad071a907da90dc0ec1fc
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165362"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a>合作伙伴通过 Microsoft Defender 终结点 API 访问

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：** 
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

此页面介绍如何创建一Azure Active Directory (Azure AD) 应用程序，以代表你的客户以编程方式访问 Microsoft Defender for Endpoint。

Microsoft Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。 这些 API 将帮助你基于 Microsoft Defender for Endpoint 功能自动执行数据流创新。 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

通常，你将需要执行以下步骤来使用 API：

- 创建 **多租户租户** Azure AD应用程序。
- 获取 (授权) 客户管理员同意你的应用程序访问所需的 Defender for Endpoint 资源。
- 使用此应用程序获取访问令牌。
- 使用令牌访问 Microsoft Defender for Endpoint API。

以下步骤将指导你如何创建 Azure AD 应用程序、获取 Microsoft Defender for Endpoint 的访问令牌并验证令牌。

## <a name="create-the-multi-tenant-app"></a>创建多租户应用

1. 使用具有全局 [管理员](https://portal.azure.com) 角色的用户登录到 **Azure** 租户。

2. 导航到 **Azure Active Directory** \> **应用注册** \> **""新注册"。**

   ![应用程序注册Microsoft Azure导航的图像。](images/atp-azure-new-app2.png)

3. 在注册表单中：

   - 为应用程序选择一个名称。

   - 支持的帐户类型 - 任何组织目录中的帐户。

   - 重定向 URI - 类型：Web、URI： https://portal.azure.com

   ![合作伙伴Microsoft Azure注册的图像。](images/atp-api-new-app-partner.png)

4. 允许应用程序访问 Microsoft Defender for Endpoint，并为其分配完成集成所需的最低权限集。

   - 在应用程序页面上，选择 **"API** 权限""添加我的组织使用的权限 API"> \>  \>  **WindowsDefenderATP"，** 然后选择 **"WindowsDefenderATP"。**

   - **注意***：WindowsDefenderATP* 不会显示在原始列表中。 开始在文本框中写入其名称，以查看其显示。

     ![添加权限。](images/add-permission.png)

### <a name="request-api-permissions"></a>请求 API 权限

若要确定所需的权限，请查看 **你** 感兴趣的 API 中的权限部分。 例如：

- 若要 [运行高级查询，请选择](run-advanced-query-api.md)"运行高级查询"权限
- 若要 [隔离设备，](isolate-machine.md)请选择"隔离计算机"权限

在下面的示例中，我们将使用 **"读取所有警报"** 权限：

1. 选择 **应用程序权限** \> **Alert.Read.All** >添加 **权限上选择**

   ![应用权限。](images/application-permissions.png)

2. 选择 **"授予同意"**

   - **注意**：每次添加权限时，都必须选择"授予新权限的许可"才能生效。

   ![授予权限的图像。](images/grant-consent.png)

3. 向应用程序添加密码。

   - 选择 **"&** 密码"，将说明添加到密码，然后选择"**添加"。**

    **重要** 提示：单击"添加" **后，复制生成的机密值**。 离开后将无法检索！

    ![创建应用密钥的图像。](images/webapp-create-key2.png)

4. 记下应用程序 ID：

   - 在应用程序页上，转到" **概述"** 并复制以下信息：

   ![已创建应用 ID 的图像。](images/app-id.png)

5. 将应用程序添加到客户的租户。

   你需要在打算使用应用程序的每个客户租户中批准你的应用程序。 这是因为应用程序代表你的客户与 Microsoft Defender for Endpoint 应用程序交互。

   具有客户 **租户全局管理员** 的用户需要选择同意链接并批准你的应用程序。

   同意链接的形式为：

   ```http
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   其中，00000000-0000-0000-0000-00000000000000 应替换为应用程序 ID

   单击同意链接后，与客户租户的全局管理员登录并许可应用程序。

   ![同意的图像。](images/app-consent-partner.png)

   此外，你将需要要求客户提供其租户 ID，并保存它供以后在获取令牌时使用。

6. **完成！** 已成功注册应用程序！ 有关令牌获取和验证，请参阅以下示例。

## <a name="get-an-access-token-example"></a>获取访问令牌示例

**注意：** 若要代表客户获取访问令牌，请使用客户的租户 ID 获取以下令牌。

有关令牌AAD，请参阅AAD[教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-powershell"></a>使用 PowerShell

```powershell
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

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
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="using-c"></a>使用 C#

> 以下代码已使用 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 进行测试

- 创建新的控制台应用程序
- 安装NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)
- 使用 添加以下内容

    ```console
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- 复制/粘贴应用程序中的以下代码 (请不要忘记更新三个变量：、 `tenantId` `appId` 和 `appSecret`) 

    ```console
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

### <a name="using-python"></a>使用 Python

请参阅 [使用 Python 获取令牌](run-advanced-query-sample-python.md#get-token)

### <a name="using-curl"></a>使用百度

> [!NOTE]
> 以下过程假设计算机上Windows安装有适用于该示例的一部分

- 打开命令窗口
- 将CLIENT_ID设置为 Azure 应用程序 ID
- 将CLIENT_SECRET设置为 Azure 应用程序密码
- 将TENANT_ID设置为想要使用你的应用程序访问 Microsoft Defender for Endpoint 应用程序的客户的 Azure 租户 ID
- 运行以下命令：

```curl
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

您将获得以下形式的答案：

```console
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>验证令牌

安全检查以确保你获得正确的令牌：

- 将上一步获取的令牌复制/粘贴到 [JWT](https://jwt.ms) 中，以便解码它
- 验证是否获取具有所需权限的"角色"声明
- 在下面屏幕截图中，你可以看到从具有 Microsoft Defender for Endpoint 的多个权限的应用程序获取的解码令牌：
- "tid"声明是令牌所属的租户 ID。

![令牌验证的图像。](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>使用令牌访问 Microsoft Defender for Endpoint API

- 选择你想要使用的 API，有关详细信息，请参阅支持的 Microsoft [Defender 终结点 API](exposed-apis-list.md)
- 将你发送的 Http 请求中的 Authorization 标头设置为"Bearer {token}" (Bearer 是授权方案) 
- 令牌的过期时间为 1 小时 (你可以使用相同的令牌发送多个请求) 

- 发送请求以使用请求获取警报列表 **的示例C#**

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
