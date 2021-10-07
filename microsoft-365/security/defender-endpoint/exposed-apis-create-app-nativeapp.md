---
title: 将 Microsoft Defender 用于终结点 API
ms.reviewer: ''
description: 了解如何设计本机 Windows 应用，无需用户即可以编程方式访问 Microsoft Defender for Endpoint。
keywords: api， 图形 api， 受支持的 api， 参与者， 警报， 设备， 用户， 域， ip， 文件， 高级搜寻， 查询
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: bcd09c1a2f828545243d1f4d56c9e2cab49356ab
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190553"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a>将 Microsoft Defender 用于终结点 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

此页面介绍如何创建应用程序以代表用户以编程方式访问 Defender for Endpoint。

如果你需要在没有用户的情况下以编程方式访问 Microsoft Defender for Endpoint，请参阅使用应用程序上下文访问[Microsoft Defender for Endpoint。](exposed-apis-create-app-webapp.md)

如果您不确定需要哪种访问权限，请阅读" [简介"页](apis-intro.md)。

Microsoft Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。 借助这些 API，你可以基于 Microsoft Defender for Endpoint 功能自动执行数据流创新。 API 访问需要 OAuth2.0 身份验证。 有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

通常，你将需要执行以下步骤来使用 API：

- 创建 AAD 应用程序
- 使用此应用程序获取访问令牌
- 使用令牌访问 Defender for Endpoint API

此页面介绍如何创建 AAD 应用程序、获取 Microsoft Defender for Endpoint 的访问令牌并验证令牌。

> [!NOTE]
> 代表用户访问 Microsoft Defender for Endpoint API 时，需要正确的应用程序权限和用户权限。
> 如果你不熟悉 Microsoft Defender for Endpoint 上的用户权限，请参阅使用基于角色的访问控制管理 [门户访问](rbac.md)。

> [!TIP]
> 如果你有权在门户中执行一个操作，则你有权在 API 中执行此操作。

## <a name="create-an-app"></a>创建应用

1. 使用具有全局管理员角色的用户帐户 **登录到** [Azure。](https://portal.azure.com)

2. 导航到 **Azure Active Directory** \> **应用注册** \> **""新注册"。**

   ![应用程序注册Microsoft Azure导航的图像。](images/atp-azure-new-app2.png)

3. 出现“**注册应用程序**”页面后，输入应用程序的注册信息：
   - **名称** - 输入一个会显示给应用用户的有意义的应用程序名称。
   - **支持的帐户类型** - 选择希望应用程序支持的具体帐户。

   <br>

   ****

   |支持的帐户类型|说明|
   |---|---|
   |**仅限此组织目录中的帐户**|若要生成业务线 (LOB) 应用程序，请选择此选项。 如果不在目录中注册应用程序，则此选项不可用。 <p> 此选项映射到仅限 Azure AD 的单租户。 <p> 这是默认选项，除非你是在目录外部注册应用。 如果在目录外部注册应用，则默认设置为 Azure AD 多租户和 Microsoft 个人帐户。|
   |**任何组织目录中的帐户**|若想要面向所有企业和教育客户，请选择此选项。 <p> 此选项映射到仅限 Azure AD 的多租户。 <p> 如果已将应用注册为仅限 Azure AD 的单租户，则可通过“**身份验证**”边栏选项卡将其更新为 Azure AD 多租户，再更新回单租户。|
   |**任何组织目录中的帐户和 Microsoft 个人帐户**|若要面向最广泛的客户，请选择此选项。 <p> 此选项映射到 Azure AD 多租户和 Microsoft 个人帐户。 <p> 如果已将应用注册为 Azure AD 多租户和 Microsoft个人 帐户，则不能在 UI 中更改此项， 而只能使用应用程序清单编辑器来更改支持的帐户类型。|
   |

   - **重定向 URI（可选）** - 选择要生成的应用的类型：“**Web**”或“**公共客户端(移动和桌面)**”，然后输入应用程序的重定向 URI（或回复 URL）。
     - 对于 Web 应用程序，请提供应用的基 URL。 例如，`http://localhost:31544` 可以是本地计算机上运行的 Web 应用的 URL。 用户将使用此 URL 登录到 Web 客户端应用程序。
     - 对于公共客户端应用程序，请提供 Azure AD 返回令牌响应时所用的 URI。 输入特定于应用程序的值，例如 `myapp://auth`。

     若要查看 Web 应用程序或本机应用程序的特定示例，请参阅[快速入门](/azure/active-directory/develop/#quickstarts)。

     完成后，选择“**注册**”。

4. 允许应用程序访问适用于终结点的 Microsoft Defender，并为其分配"读取警报"权限：

   - 在应用程序页面上，选择 **"API** 权限""添加我的组织使用的权限 \>  \> API"> **WindowsDefenderATP"，** 然后选择 **在 WindowsDefenderATP 上选择**。
   - **注意***：WindowsDefenderATP* 不会显示在原始列表中。 开始在文本框中写入其名称，以查看其显示。

     ![添加权限。](images/add-permission.png)

   - Choose **Delegated permissions** \> **Alert.Read** > select **Add permissions**

      ![应用程序权限。](images/application-permissions-public-client.png)

   - **重要说明**：选择相关权限。 阅读通知只是一个示例。

     例如，

     - 若要 [运行高级查询，请选择](run-advanced-query-api.md)"运行高级查询"权限
     - 若要 [隔离设备，](isolate-machine.md)请选择"隔离计算机"权限
     - 若要确定所需的权限，请查看 **要** 调用的 API 中的"权限"部分。

   - 选择 **"授予同意"**

      **注意**：每次添加权限时，都必须选择"授予新权限的许可"才能生效。

      ![授予权限的图像。](images/grant-consent.png)

5. 记下应用程序 ID 和租户 ID：

   - 在应用程序页上，转到" **概述"** 并复制以下信息：

   ![已创建应用 ID 的图像。](images/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>获取访问令牌

有关 AAD 令牌详细信息，请参阅 [Azure AD 教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-c"></a>使用 C\#

- 在应用程序中复制/粘贴以下类。
- 将 **AcquireUserTokenAsync** 方法与应用程序 ID、租户 ID、用户名和密码一同使用以获取令牌。

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a>验证令牌

验证以确保你收到了正确的令牌：

- 将上一步中获取的令牌复制/粘贴到 [JWT](https://jwt.ms) 中，以便解码它
- 验证是否获取具有所需应用权限的"scp"声明
- 在下面的屏幕截图中，你可以看到从本教程中的应用获取的解码令牌：

![令牌验证的图像。](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>使用令牌访问 Microsoft Defender for Endpoint API

- 选择想要使用的 API - [支持的 Microsoft Defender 终结点 API](exposed-apis-list.md)
- 将你发送的 HTTP 请求中的 Authorization 标头设置为"Bearer {token}" (Bearer 是授权方案) 
- 令牌的过期时间是 1 小时 (你可以使用相同的令牌发送多个请求) 

- 发送请求以使用请求获取警报列表 **C#**

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>另请参阅

- [适用于终结点的 Microsoft Defender API](exposed-apis-list.md)
- [使用应用程序上下文访问 Microsoft Defender for Endpoint](exposed-apis-create-app-webapp.md)
