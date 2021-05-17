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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5e59ff75a7933cf52af857f1a41b0925aa7bb47a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198879"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="10859-104">将 Microsoft Defender 用于终结点 API</span><span class="sxs-lookup"><span data-stu-id="10859-104">Use Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="10859-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="10859-105">**Applies to:**</span></span>
- [<span data-ttu-id="10859-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="10859-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="10859-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="10859-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="10859-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="10859-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="10859-109">此页面介绍如何创建应用程序以代表用户以编程方式访问 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="10859-109">This page describes how to create an application to get programmatic access to Defender for Endpoint on behalf of a user.</span></span>

<span data-ttu-id="10859-110">如果你需要在没有用户的情况下以编程方式访问 Microsoft Defender for Endpoint，请参阅使用应用程序上下文访问[Microsoft Defender for Endpoint。](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="10859-110">If you need programmatic access Microsoft Defender for Endpoint without a user, refer to [Access Microsoft Defender for Endpoint with application context](exposed-apis-create-app-webapp.md).</span></span>

<span data-ttu-id="10859-111">如果不确定需要哪种访问权限，请阅读" [简介"页](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="10859-111">If you are not sure which access you need, read the [Introduction page](apis-intro.md).</span></span>

<span data-ttu-id="10859-112">Microsoft Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="10859-112">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="10859-113">借助这些 API，你可以基于 Microsoft Defender for Endpoint 功能自动执行数据流创新。</span><span class="sxs-lookup"><span data-stu-id="10859-113">Those APIs will enable you to automate work flows and innovate based on Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="10859-114">API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="10859-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="10859-115">有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="10859-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="10859-116">通常，你将需要执行以下步骤来使用 API：</span><span class="sxs-lookup"><span data-stu-id="10859-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="10859-117">创建 AAD 应用程序</span><span class="sxs-lookup"><span data-stu-id="10859-117">Create an AAD application</span></span>
- <span data-ttu-id="10859-118">使用此应用程序获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="10859-118">Get an access token using this application</span></span>
- <span data-ttu-id="10859-119">使用令牌访问 Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="10859-119">Use the token to access Defender for Endpoint API</span></span>

<span data-ttu-id="10859-120">此页面介绍如何创建 AAD 应用程序、获取 Microsoft Defender for Endpoint 的访问令牌并验证令牌。</span><span class="sxs-lookup"><span data-stu-id="10859-120">This page explains how to create an AAD application, get an access token to Microsoft Defender for Endpoint and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="10859-121">代表用户访问 Microsoft Defender for Endpoint API 时，需要正确的应用程序权限和用户权限。</span><span class="sxs-lookup"><span data-stu-id="10859-121">When accessing Microsoft Defender for Endpoint API on behalf of a user, you will need the correct Application permission and user permission.</span></span>
> <span data-ttu-id="10859-122">如果你不熟悉 Microsoft Defender for Endpoint 上的用户权限，请参阅使用基于角色的访问控制管理 [门户访问](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="10859-122">If you are not familiar with user permissions on Microsoft Defender for Endpoint, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="10859-123">如果你有权在门户中执行一个操作，则你有权在 API 中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="10859-123">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="10859-124">创建应用</span><span class="sxs-lookup"><span data-stu-id="10859-124">Create an app</span></span>

1. <span data-ttu-id="10859-125">使用具有全局管理员角色的用户帐户 **登录到** [Azure。](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="10859-125">Log on to [Azure](https://portal.azure.com) with a user account that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="10859-126">导航到 **Azure Active Directory**  >  **应用注册**  >  **""新注册"。**</span><span class="sxs-lookup"><span data-stu-id="10859-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![应用程序注册Microsoft Azure导航的图像](images/atp-azure-new-app2.png)

3. <span data-ttu-id="10859-128">出现“**注册应用程序**”页面后，输入应用程序的注册信息：</span><span class="sxs-lookup"><span data-stu-id="10859-128">When the **Register an application** page appears, enter your application's registration information:</span></span>

   - <span data-ttu-id="10859-129">**名称** - 输入一个会显示给应用用户的有意义的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="10859-129">**Name** - Enter a meaningful application name that will be displayed to users of the app.</span></span>
   - <span data-ttu-id="10859-130">**支持的帐户类型** - 选择希望应用程序支持的具体帐户。</span><span class="sxs-lookup"><span data-stu-id="10859-130">**Supported account types** - Select which accounts you would like your application to support.</span></span>

       | <span data-ttu-id="10859-131">支持的帐户类型</span><span class="sxs-lookup"><span data-stu-id="10859-131">Supported account types</span></span> | <span data-ttu-id="10859-132">说明</span><span class="sxs-lookup"><span data-stu-id="10859-132">Description</span></span> |
       |-------------------------|-------------|
       | <span data-ttu-id="10859-133">**仅限此组织目录中的帐户**</span><span class="sxs-lookup"><span data-stu-id="10859-133">**Accounts in this organizational directory only**</span></span> | <span data-ttu-id="10859-134">若要生成业务线 (LOB) 应用程序，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="10859-134">Select this option if you're building a line-of-business (LOB) application.</span></span> <span data-ttu-id="10859-135">如果不在目录中注册应用程序，则此选项不可用。</span><span class="sxs-lookup"><span data-stu-id="10859-135">This option is not available if you're not registering the application in a directory.</span></span><br><br><span data-ttu-id="10859-136">此选项映射到仅限 Azure AD 的单租户。</span><span class="sxs-lookup"><span data-stu-id="10859-136">This option maps to Azure AD only single-tenant.</span></span><br><br><span data-ttu-id="10859-137">这是默认选项，除非你是在目录外部注册应用。</span><span class="sxs-lookup"><span data-stu-id="10859-137">This is the default option unless you're registering the app outside of a directory.</span></span> <span data-ttu-id="10859-138">如果在目录外部注册应用，则默认设置为 Azure AD 多租户和 Microsoft 个人帐户。</span><span class="sxs-lookup"><span data-stu-id="10859-138">In cases where the app is registered outside of a directory, the default is Azure AD multi-tenant and personal Microsoft accounts.</span></span> |
       | <span data-ttu-id="10859-139">**任何组织目录中的帐户**</span><span class="sxs-lookup"><span data-stu-id="10859-139">**Accounts in any organizational directory**</span></span> | <span data-ttu-id="10859-140">若想要面向所有企业和教育客户，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="10859-140">Select this option if you would like to target all business and educational customers.</span></span><br><br><span data-ttu-id="10859-141">此选项映射到仅限 Azure AD 的多租户。</span><span class="sxs-lookup"><span data-stu-id="10859-141">This option maps to an Azure AD only multi-tenant.</span></span><br><br><span data-ttu-id="10859-142">如果已将应用注册为仅限 Azure AD 的单租户，则可通过“**身份验证**”边栏选项卡将其更新为 Azure AD 多租户，再更新回单租户。</span><span class="sxs-lookup"><span data-stu-id="10859-142">If you registered the app as Azure AD only single-tenant, you can update it to be Azure AD multi-tenant and back to single-tenant through the **Authentication** blade.</span></span> |
       | <span data-ttu-id="10859-143">**任何组织目录中的帐户和 Microsoft 个人帐户**</span><span class="sxs-lookup"><span data-stu-id="10859-143">**Accounts in any organizational directory and personal Microsoft accounts**</span></span> | <span data-ttu-id="10859-144">若要面向最广泛的客户，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="10859-144">Select this option to target the widest set of customers.</span></span><br><br><span data-ttu-id="10859-145">此选项映射到 Azure AD 多租户和 Microsoft 个人帐户。</span><span class="sxs-lookup"><span data-stu-id="10859-145">This option maps to Azure AD multi-tenant and personal Microsoft accounts.</span></span><br><br><span data-ttu-id="10859-146">如果已将应用注册为 Azure AD 多租户和 Microsoft个人 帐户，则不能在 UI 中更改此项，</span><span class="sxs-lookup"><span data-stu-id="10859-146">If you registered the app as Azure AD multi-tenant and personal Microsoft accounts, you cannot change this in the UI.</span></span> <span data-ttu-id="10859-147">而只能使用应用程序清单编辑器来更改支持的帐户类型。</span><span class="sxs-lookup"><span data-stu-id="10859-147">Instead, you must use the application manifest editor to change the supported account types.</span></span> |

   - <span data-ttu-id="10859-148">**重定向 URI（可选）** - 选择要生成的应用的类型：“**Web**”或“**公共客户端(移动和桌面)**”，然后输入应用程序的重定向 URI（或回复 URL）。</span><span class="sxs-lookup"><span data-stu-id="10859-148">**Redirect URI (optional)** - Select the type of app you're building, **Web** or **Public client (mobile & desktop)**, and then enter the redirect URI (or reply URL) for your application.</span></span>
       - <span data-ttu-id="10859-149">对于 Web 应用程序，请提供应用的基 URL。</span><span class="sxs-lookup"><span data-stu-id="10859-149">For web applications, provide the base URL of your app.</span></span> <span data-ttu-id="10859-150">例如，`http://localhost:31544` 可以是本地计算机上运行的 Web 应用的 URL。</span><span class="sxs-lookup"><span data-stu-id="10859-150">For example, `http://localhost:31544` might be the URL for a web app running on your local machine.</span></span> <span data-ttu-id="10859-151">用户将使用此 URL 登录到 Web 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="10859-151">Users would use this URL to sign in to a web client application.</span></span>
       - <span data-ttu-id="10859-152">对于公共客户端应用程序，请提供 Azure AD 返回令牌响应时所用的 URI。</span><span class="sxs-lookup"><span data-stu-id="10859-152">For public client applications, provide the URI used by Azure AD to return token responses.</span></span> <span data-ttu-id="10859-153">输入特定于应用程序的值，例如 `myapp://auth`。</span><span class="sxs-lookup"><span data-stu-id="10859-153">Enter a value specific to your application, such as `myapp://auth`.</span></span>

     <span data-ttu-id="10859-154">若要查看 Web 应用程序或本机应用程序的特定示例，请参阅[快速入门](/azure/active-directory/develop/#quickstarts)。</span><span class="sxs-lookup"><span data-stu-id="10859-154">To see specific examples for web applications or native applications, check out our [quickstarts](/azure/active-directory/develop/#quickstarts).</span></span>

     <span data-ttu-id="10859-155">完成后，选择“**注册**”。</span><span class="sxs-lookup"><span data-stu-id="10859-155">When finished, select **Register**.</span></span>

4. <span data-ttu-id="10859-156">允许应用程序访问适用于终结点的 Microsoft Defender，并为其分配"读取警报"权限：</span><span class="sxs-lookup"><span data-stu-id="10859-156">Allow your Application to access Microsoft Defender for Endpoint and assign it 'Read alerts' permission:</span></span>

    - <span data-ttu-id="10859-157">在应用程序页面上，选择 **"API** 权限""添加我的组织使用的权限  >    >  API"> **WindowsDefenderATP"，** 然后选择 **"WindowsDefenderATP"。**</span><span class="sxs-lookup"><span data-stu-id="10859-157">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and select on **WindowsDefenderATP**.</span></span>

    - <span data-ttu-id="10859-158">\**注意\*\*\*：WindowsDefenderATP* 不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="10859-158">**Note**: *WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="10859-159">开始在文本框中写入其名称，以查看其显示。</span><span class="sxs-lookup"><span data-stu-id="10859-159">Start writing its name in the text box to see it appear.</span></span>

      ![添加权限](images/add-permission.png)

    - <span data-ttu-id="10859-161">Choose **Delegated permissions**  >  **Alert.Read** > select **Add permissions**</span><span class="sxs-lookup"><span data-stu-id="10859-161">Choose **Delegated permissions** > **Alert.Read** > select **Add permissions**</span></span>

      ![应用程序权限](images/application-permissions-public-client.png)

    - <span data-ttu-id="10859-163">**重要说明**：选择相关权限。</span><span class="sxs-lookup"><span data-stu-id="10859-163">**Important note**: Select the relevant permissions.</span></span> <span data-ttu-id="10859-164">阅读通知只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="10859-164">Read alerts is only an example.</span></span>

      <span data-ttu-id="10859-165">例如，</span><span class="sxs-lookup"><span data-stu-id="10859-165">For instance,</span></span>

      - <span data-ttu-id="10859-166">若要 [运行高级查询，请选择](run-advanced-query-api.md)"运行高级查询"权限</span><span class="sxs-lookup"><span data-stu-id="10859-166">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
      - <span data-ttu-id="10859-167">若要 [隔离设备，](isolate-machine.md)请选择"隔离计算机"权限</span><span class="sxs-lookup"><span data-stu-id="10859-167">To [isolate a device](isolate-machine.md), select 'Isolate machine' permission</span></span>
      - <span data-ttu-id="10859-168">若要确定所需的权限，请查看 **要** 调用的 API 中的"权限"部分。</span><span class="sxs-lookup"><span data-stu-id="10859-168">To determine which permission you need, view the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="10859-169">选择 **"授予同意"**</span><span class="sxs-lookup"><span data-stu-id="10859-169">Select **Grant consent**</span></span>

      <span data-ttu-id="10859-170">**注意**：每次添加权限时，都必须选择"授予新权限的许可"才能生效。</span><span class="sxs-lookup"><span data-stu-id="10859-170">**Note**: Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

      ![授予权限的图像](images/grant-consent.png)

6. <span data-ttu-id="10859-172">记下应用程序 ID 和租户 ID：</span><span class="sxs-lookup"><span data-stu-id="10859-172">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="10859-173">在应用程序页上，转到" **概述"** 并复制以下信息：</span><span class="sxs-lookup"><span data-stu-id="10859-173">On your application page, go to **Overview** and copy the following information:</span></span>

   ![已创建应用 ID 的图像](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a><span data-ttu-id="10859-175">获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="10859-175">Get an access token</span></span>

<span data-ttu-id="10859-176">有关 AAD 令牌详细信息，请参阅 [Azure AD 教程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="10859-176">For more information on AAD tokens, see [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-c"></a><span data-ttu-id="10859-177">使用 C#</span><span class="sxs-lookup"><span data-stu-id="10859-177">Using C#</span></span>

- <span data-ttu-id="10859-178">在应用程序中复制/粘贴以下类。</span><span class="sxs-lookup"><span data-stu-id="10859-178">Copy/Paste the below class in your application.</span></span>
- <span data-ttu-id="10859-179">将 **AcquireUserTokenAsync** 方法与应用程序 ID、租户 ID、用户名和密码一同使用以获取令牌。</span><span class="sxs-lookup"><span data-stu-id="10859-179">Use **AcquireUserTokenAsync** method with your application ID, tenant ID, user name, and password to acquire a token.</span></span>

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

## <a name="validate-the-token"></a><span data-ttu-id="10859-180">验证令牌</span><span class="sxs-lookup"><span data-stu-id="10859-180">Validate the token</span></span>

<span data-ttu-id="10859-181">验证以确保你收到了正确的令牌：</span><span class="sxs-lookup"><span data-stu-id="10859-181">Verify to make sure you got a correct token:</span></span>
- <span data-ttu-id="10859-182">将上一步获取的令牌复制/粘贴到 [JWT](https://jwt.ms) 中，以便解码它</span><span class="sxs-lookup"><span data-stu-id="10859-182">Copy/paste into [JWT](https://jwt.ms) the token you got in the previous step in order to decode it</span></span>
- <span data-ttu-id="10859-183">验证是否获取具有所需应用权限的"scp"声明</span><span class="sxs-lookup"><span data-stu-id="10859-183">Validate you get a 'scp' claim with the desired app permissions</span></span>
- <span data-ttu-id="10859-184">在下面的屏幕截图中，你可以看到从应用获取的已解码令牌在本教程中：</span><span class="sxs-lookup"><span data-stu-id="10859-184">In the screenshot below you can see a decoded token acquired from the app in the tutorial:</span></span>

![令牌验证图像](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="10859-186">使用令牌访问 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="10859-186">Use the token to access Microsoft Defender for Endpoint API</span></span>

- <span data-ttu-id="10859-187">选择想要使用的 API - [支持的 Microsoft Defender 终结点 API](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="10859-187">Choose the API you want to use - [Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- <span data-ttu-id="10859-188">将发送的 HTTP 请求中的 Authorization 标头设置为"Bearer {token}"， (Bearer 是授权方案) </span><span class="sxs-lookup"><span data-stu-id="10859-188">Set the Authorization header in the HTTP request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="10859-189">令牌的过期时间为 1 小时 (你可以使用相同的令牌发送多个请求) </span><span class="sxs-lookup"><span data-stu-id="10859-189">The Expiration time of the token is 1 hour (you can send more than one request with the same token)</span></span>

- <span data-ttu-id="10859-190">发送请求以使用请求获取警报列表 **C#**</span><span class="sxs-lookup"><span data-stu-id="10859-190">Example of sending a request to get a list of alerts **using C#**</span></span> 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a><span data-ttu-id="10859-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10859-191">See also</span></span>
- [<span data-ttu-id="10859-192">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="10859-192">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="10859-193">使用应用程序上下文访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="10859-193">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
