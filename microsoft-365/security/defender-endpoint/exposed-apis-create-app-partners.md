---
title: 创建应用程序以在没有用户的情况下访问 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 了解如何设计 Web 应用，无需用户即可以编程方式访问 Microsoft Defender for Endpoint。
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
ms.openlocfilehash: bc58241be69a1d8e1a78abc583b2c87dbef9cfa7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199362"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="bb79e-104">合作伙伴通过 Microsoft Defender 终结点 API 访问</span><span class="sxs-lookup"><span data-stu-id="bb79e-104">Partner access through Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bb79e-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bb79e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="bb79e-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="bb79e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bb79e-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="bb79e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="bb79e-108">此页面介绍如何创建 Azure AD Azure Active Directory (应用程序) 代表客户以编程方式访问 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="bb79e-108">This page describes how to create an Azure Active Directory (Azure AD) application to get programmatic access to Microsoft Defender for Endpoint on behalf of your customers.</span></span>


<span data-ttu-id="bb79e-109">Microsoft Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="bb79e-109">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="bb79e-110">这些 API 将帮助你基于 Microsoft Defender for Endpoint 功能自动执行数据流创新。</span><span class="sxs-lookup"><span data-stu-id="bb79e-110">Those APIs will help you automate work flows and innovate based on Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="bb79e-111">API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="bb79e-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="bb79e-112">有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="bb79e-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="bb79e-113">通常，你将需要执行以下步骤来使用 API：</span><span class="sxs-lookup"><span data-stu-id="bb79e-113">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="bb79e-114">创建 **多租户** Azure AD 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb79e-114">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="bb79e-115">获取 (授权) 客户管理员同意你的应用程序访问其所需的 Defender 终结点资源。</span><span class="sxs-lookup"><span data-stu-id="bb79e-115">Get authorized(consent) by your customer administrator for your application to access Defender for Endpoint resources it needs.</span></span>
- <span data-ttu-id="bb79e-116">使用此应用程序获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="bb79e-116">Get an access token using this application.</span></span>
- <span data-ttu-id="bb79e-117">使用令牌访问 Microsoft Defender for Endpoint API。</span><span class="sxs-lookup"><span data-stu-id="bb79e-117">Use the token to access Microsoft Defender for Endpoint API.</span></span>

<span data-ttu-id="bb79e-118">以下步骤将指导你如何创建 Azure AD 应用程序、获取 Microsoft Defender for Endpoint 的访问令牌并验证令牌。</span><span class="sxs-lookup"><span data-stu-id="bb79e-118">The following steps will guide you how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="bb79e-119">创建多租户应用</span><span class="sxs-lookup"><span data-stu-id="bb79e-119">Create the multi-tenant app</span></span>

1. <span data-ttu-id="bb79e-120">使用具有全局 [管理员](https://portal.azure.com) 角色的用户登录到 **Azure** 租户。</span><span class="sxs-lookup"><span data-stu-id="bb79e-120">Sign in to your [Azure tenant](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="bb79e-121">导航到 **Azure Active Directory**  >  **应用注册**  >  **""新注册"。**</span><span class="sxs-lookup"><span data-stu-id="bb79e-121">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![应用程序注册Microsoft Azure导航的图像](images/atp-azure-new-app2.png)

3. <span data-ttu-id="bb79e-123">在注册表单中：</span><span class="sxs-lookup"><span data-stu-id="bb79e-123">In the registration form:</span></span>

    - <span data-ttu-id="bb79e-124">为应用程序选择一个名称。</span><span class="sxs-lookup"><span data-stu-id="bb79e-124">Choose a name for your application.</span></span>

    - <span data-ttu-id="bb79e-125">支持的帐户类型 - 任何组织目录中的帐户。</span><span class="sxs-lookup"><span data-stu-id="bb79e-125">Supported account types - accounts in any organizational directory.</span></span>

    - <span data-ttu-id="bb79e-126">重定向 URI - 类型：Web、URI： https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="bb79e-126">Redirect URI - type: Web, URI: https://portal.azure.com</span></span>

    ![合作伙伴Microsoft Azure注册的图像](images/atp-api-new-app-partner.png)


4. <span data-ttu-id="bb79e-128">允许应用程序访问 Microsoft Defender for Endpoint，并为其分配完成集成所需的最低权限集。</span><span class="sxs-lookup"><span data-stu-id="bb79e-128">Allow your Application to access Microsoft Defender for Endpoint and assign it with the minimal set of permissions required to complete the integration.</span></span>

   - <span data-ttu-id="bb79e-129">在应用程序页面上，选择 **"API** 权限""添加我的组织使用的权限  >    >  API"> **WindowsDefenderATP"，** 然后选择 **"WindowsDefenderATP"。**</span><span class="sxs-lookup"><span data-stu-id="bb79e-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and select on **WindowsDefenderATP**.</span></span>

   - <span data-ttu-id="bb79e-130">\**注意\*\*\*：WindowsDefenderATP* 不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="bb79e-130">**Note**: *WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="bb79e-131">开始在文本框中写入其名称，以查看其显示。</span><span class="sxs-lookup"><span data-stu-id="bb79e-131">Start writing its name in the text box to see it appear.</span></span>

   ![添加权限](images/add-permission.png)
   
   ### <a name="request-api-permissions"></a><span data-ttu-id="bb79e-133">请求 API 权限</span><span class="sxs-lookup"><span data-stu-id="bb79e-133">Request API permissions</span></span>

   <span data-ttu-id="bb79e-134">若要确定所需的权限，请查看 **你** 感兴趣的 API 中的权限部分。</span><span class="sxs-lookup"><span data-stu-id="bb79e-134">To determine which permission you need, review the **Permissions** section in the API you are interested to call.</span></span> <span data-ttu-id="bb79e-135">例如：</span><span class="sxs-lookup"><span data-stu-id="bb79e-135">For instance:</span></span>

   - <span data-ttu-id="bb79e-136">若要 [运行高级查询，请选择](run-advanced-query-api.md)"运行高级查询"权限</span><span class="sxs-lookup"><span data-stu-id="bb79e-136">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
   
   - <span data-ttu-id="bb79e-137">若要 [隔离设备，](isolate-machine.md)请选择"隔离计算机"权限</span><span class="sxs-lookup"><span data-stu-id="bb79e-137">To [isolate a device](isolate-machine.md), select 'Isolate machine' permission</span></span>

   <span data-ttu-id="bb79e-138">在下面的示例中，我们将使用 **"读取所有警报"** 权限：</span><span class="sxs-lookup"><span data-stu-id="bb79e-138">In the following example we will use **'Read all alerts'** permission:</span></span>

   <span data-ttu-id="bb79e-139">选择 **应用程序权限**  >  **Alert.Read.All** >添加 **权限上选择**</span><span class="sxs-lookup"><span data-stu-id="bb79e-139">Choose **Application permissions** > **Alert.Read.All** > select on **Add permissions**</span></span>

   ![应用程序权限](images/application-permissions.png)


5. <span data-ttu-id="bb79e-141">选择 **"授予同意"**</span><span class="sxs-lookup"><span data-stu-id="bb79e-141">Select **Grant consent**</span></span>

    - <span data-ttu-id="bb79e-142">**注意**：每次添加权限时，都必须选择"授予新权限的许可"才能生效。</span><span class="sxs-lookup"><span data-stu-id="bb79e-142">**Note**: Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![授予权限的图像](images/grant-consent.png)

6. <span data-ttu-id="bb79e-144">向应用程序添加密码。</span><span class="sxs-lookup"><span data-stu-id="bb79e-144">Add a secret to the application.</span></span>

    - <span data-ttu-id="bb79e-145">选择 **"&** 密码"，将说明添加到密码，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="bb79e-145">Select **Certificates & secrets**, add description to the secret and select **Add**.</span></span>

    <span data-ttu-id="bb79e-146">**重要** 提示：单击"添加" **后，复制生成的机密值**。</span><span class="sxs-lookup"><span data-stu-id="bb79e-146">**Important**: After click Add, **copy the generated secret value**.</span></span> <span data-ttu-id="bb79e-147">离开后将无法检索！</span><span class="sxs-lookup"><span data-stu-id="bb79e-147">You won't be able to retrieve after you leave!</span></span>

    ![创建应用密钥的图像](images/webapp-create-key2.png)

7. <span data-ttu-id="bb79e-149">记下应用程序 ID：</span><span class="sxs-lookup"><span data-stu-id="bb79e-149">Write down your application ID:</span></span>

   - <span data-ttu-id="bb79e-150">在应用程序页上，转到" **概述"** 并复制以下信息：</span><span class="sxs-lookup"><span data-stu-id="bb79e-150">On your application page, go to **Overview** and copy the following information:</span></span>

   ![已创建应用 ID 的图像](images/app-id.png)

8. <span data-ttu-id="bb79e-152">将应用程序添加到客户的租户。</span><span class="sxs-lookup"><span data-stu-id="bb79e-152">Add the application to your customer's tenant.</span></span>

    <span data-ttu-id="bb79e-153">你需要在打算使用应用程序的每个客户租户中批准你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb79e-153">You need your application to be approved in each customer tenant where you intend to use it.</span></span> <span data-ttu-id="bb79e-154">这是因为应用程序代表你的客户与 Microsoft Defender for Endpoint 应用程序交互。</span><span class="sxs-lookup"><span data-stu-id="bb79e-154">This is because your application interacts with Microsoft Defender for Endpoint application on behalf of your customer.</span></span>

    <span data-ttu-id="bb79e-155">具有客户 **租户全局管理员** 的用户需要选择同意链接并批准你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb79e-155">A user with **Global Administrator** from your customer's tenant need to select the consent link and approve your application.</span></span>

    <span data-ttu-id="bb79e-156">同意链接的形式为：</span><span class="sxs-lookup"><span data-stu-id="bb79e-156">Consent link is of the form:</span></span>

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="bb79e-157">其中，00000000-0000-0000-0000-00000000000000</span><span class="sxs-lookup"><span data-stu-id="bb79e-157">Where 00000000-0000-0000-0000-000000000000 should be replaced with your Application ID</span></span>

    <span data-ttu-id="bb79e-158">单击同意链接后，与客户租户的全局管理员登录并许可应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb79e-158">After clicking on the consent link, sign in with the Global Administrator of the customer's tenant and consent the application.</span></span>

    ![同意图像](images/app-consent-partner.png)

    <span data-ttu-id="bb79e-160">此外，你将需要请求客户提供其租户 ID，并保存它供以后在获取令牌时使用。</span><span class="sxs-lookup"><span data-stu-id="bb79e-160">In addition, you will need to ask your customer for their tenant ID and save it for future use when acquiring the token.</span></span>

- <span data-ttu-id="bb79e-161">**完成！**</span><span class="sxs-lookup"><span data-stu-id="bb79e-161">**Done!**</span></span> <span data-ttu-id="bb79e-162">已成功注册应用程序！</span><span class="sxs-lookup"><span data-stu-id="bb79e-162">You have successfully registered an application!</span></span> 
- <span data-ttu-id="bb79e-163">有关令牌获取和验证，请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="bb79e-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token-example"></a><span data-ttu-id="bb79e-164">获取访问令牌示例：</span><span class="sxs-lookup"><span data-stu-id="bb79e-164">Get an access token example:</span></span>

<span data-ttu-id="bb79e-165">**注意：** 若要代表客户获取访问令牌，请使用客户的租户 ID 获取以下令牌。</span><span class="sxs-lookup"><span data-stu-id="bb79e-165">**Note:** To get access token on behalf of your customer, use the customer's tenant ID on the following token acquisitions.</span></span>

<br><span data-ttu-id="bb79e-166">有关 AAD 令牌详细信息，请参阅 [AAD 教程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="bb79e-166">For more information on AAD token, see [AAD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bb79e-167">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb79e-167">Using PowerShell</span></span>

```
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

### <a name="using-c"></a><span data-ttu-id="bb79e-168">使用C#：</span><span class="sxs-lookup"><span data-stu-id="bb79e-168">Using C#:</span></span>

><span data-ttu-id="bb79e-169">以下代码已使用 Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 进行测试</span><span class="sxs-lookup"><span data-stu-id="bb79e-169">The below code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory</span></span>

- <span data-ttu-id="bb79e-170">创建新的控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="bb79e-170">Create a new Console Application</span></span>
- <span data-ttu-id="bb79e-171">安装NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="bb79e-171">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span></span>
- <span data-ttu-id="bb79e-172">使用 添加以下内容</span><span class="sxs-lookup"><span data-stu-id="bb79e-172">Add the below using</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- <span data-ttu-id="bb79e-173">复制/粘贴应用程序中的以下代码 (请不要忘记更新三个 ```tenantId, appId, appSecret``` 变量：) </span><span class="sxs-lookup"><span data-stu-id="bb79e-173">Copy/Paste the below code in your application (do not forget to update the three variables: ```tenantId, appId, appSecret```)</span></span>

    ```
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


### <a name="using-python"></a><span data-ttu-id="bb79e-174">使用 Python</span><span class="sxs-lookup"><span data-stu-id="bb79e-174">Using Python</span></span>

<span data-ttu-id="bb79e-175">请参阅 [使用 Python 获取令牌](run-advanced-query-sample-python.md#get-token)</span><span class="sxs-lookup"><span data-stu-id="bb79e-175">Refer to [Get token using Python](run-advanced-query-sample-python.md#get-token)</span></span>

### <a name="using-curl"></a><span data-ttu-id="bb79e-176">使用百度</span><span class="sxs-lookup"><span data-stu-id="bb79e-176">Using Curl</span></span>

> [!NOTE]
> <span data-ttu-id="bb79e-177">以下过程假设计算机上Windows的一部分</span><span class="sxs-lookup"><span data-stu-id="bb79e-177">The below procedure supposed Curl for Windows is already installed on your computer</span></span>

- <span data-ttu-id="bb79e-178">打开命令窗口</span><span class="sxs-lookup"><span data-stu-id="bb79e-178">Open a command window</span></span>
- <span data-ttu-id="bb79e-179">将CLIENT_ID设置为 Azure 应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="bb79e-179">Set CLIENT_ID to your Azure application ID</span></span>
- <span data-ttu-id="bb79e-180">将CLIENT_SECRET Azure 应用程序密码</span><span class="sxs-lookup"><span data-stu-id="bb79e-180">Set CLIENT_SECRET to your Azure application secret</span></span>
- <span data-ttu-id="bb79e-181">将TENANT_ID设置为想要使用你的应用程序访问 Microsoft Defender for Endpoint 应用程序的客户的 Azure 租户 ID</span><span class="sxs-lookup"><span data-stu-id="bb79e-181">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your application to access Microsoft Defender for Endpoint application</span></span>
- <span data-ttu-id="bb79e-182">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bb79e-182">Run the below command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="bb79e-183">您将获得以下形式的答案：</span><span class="sxs-lookup"><span data-stu-id="bb79e-183">You will get an answer of the form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="bb79e-184">验证令牌</span><span class="sxs-lookup"><span data-stu-id="bb79e-184">Validate the token</span></span>

<span data-ttu-id="bb79e-185">安全检查以确保你获得正确的令牌：</span><span class="sxs-lookup"><span data-stu-id="bb79e-185">Sanity check to make sure you got a correct token:</span></span>
- <span data-ttu-id="bb79e-186">将上一步获取的令牌复制/粘贴到 [JWT](https://jwt.ms) 中，以便解码它</span><span class="sxs-lookup"><span data-stu-id="bb79e-186">Copy/paste into [JWT](https://jwt.ms) the token you get in the previous step in order to decode it</span></span>
- <span data-ttu-id="bb79e-187">验证是否获取具有所需权限的"角色"声明</span><span class="sxs-lookup"><span data-stu-id="bb79e-187">Validate you get a 'roles' claim with the desired permissions</span></span>
- <span data-ttu-id="bb79e-188">在下面屏幕截图中，你可以看到从具有 Microsoft Defender for Endpoint 的多个权限的应用程序获取的解码令牌：</span><span class="sxs-lookup"><span data-stu-id="bb79e-188">In the screenshot below, you can see a decoded token acquired from an Application with multiple permissions to  Microsoft Defender for Endpoint:</span></span>
- <span data-ttu-id="bb79e-189">"tid"声明是令牌所属的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="bb79e-189">The "tid" claim is the tenant ID the token belongs to.</span></span>

![令牌验证图像](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="bb79e-191">使用令牌访问 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="bb79e-191">Use the token to access Microsoft Defender for Endpoint API</span></span>

- <span data-ttu-id="bb79e-192">选择你想要使用的 API，有关详细信息，请参阅支持的 Microsoft [Defender 终结点 API](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="bb79e-192">Choose the API you want to use, for more information, see [Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- <span data-ttu-id="bb79e-193">将你发送到"Bearer {token}"的 Http 请求中的授权标头 (Bearer 是授权方案) </span><span class="sxs-lookup"><span data-stu-id="bb79e-193">Set the Authorization header in the Http request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="bb79e-194">令牌的过期时间为 1 小时 (你可以使用相同的令牌发送多个请求) </span><span class="sxs-lookup"><span data-stu-id="bb79e-194">The Expiration time of the token is 1 hour (you can send more than one request with the same token)</span></span>

- <span data-ttu-id="bb79e-195">发送请求以使用请求获取警报列表 **C#**</span><span class="sxs-lookup"><span data-stu-id="bb79e-195">Example of sending a request to get a list of alerts **using C#**</span></span> 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a><span data-ttu-id="bb79e-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb79e-196">See also</span></span>
- [<span data-ttu-id="bb79e-197">支持的 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="bb79e-197">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="bb79e-198">代表用户访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bb79e-198">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)
