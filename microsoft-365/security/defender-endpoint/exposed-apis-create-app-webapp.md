---
title: 创建应用以在没有用户的情况下访问 Microsoft Defender for Endpoint
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
ms.openlocfilehash: 8f480a148d72428c6346930a91358d1e8b674ee7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200001"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a><span data-ttu-id="f4bb7-104">创建应用以在没有用户的情况下访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4bb7-104">Create an app to access Microsoft Defender for Endpoint without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f4bb7-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f4bb7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f4bb7-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f4bb7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4bb7-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f4bb7-108">此页面介绍如何创建应用程序，以在没有用户的情况下以编程方式访问 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-108">This page describes how to create an application to get programmatic access to Defender for Endpoint without a user.</span></span> <span data-ttu-id="f4bb7-109">如果你需要代表用户以编程方式访问 Defender for Endpoint，请参阅使用 [用户上下文获取访问权限](exposed-apis-create-app-nativeapp.md)。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-109">If you need programmatic access to Defender for Endpoint on behalf of a user, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span> <span data-ttu-id="f4bb7-110">如果你不确定所需的访问权限，请参阅 [入门](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-110">If you are not sure which access you need, see [Get started](apis-intro.md).</span></span>

<span data-ttu-id="f4bb7-111">Microsoft Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-111">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="f4bb7-112">这些 API 将帮助你自动执行基于 Defender for Endpoint 功能的工作流和创新。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-112">Those APIs will help you automate work flows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="f4bb7-113">API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-113">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="f4bb7-114">有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="f4bb7-114">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="f4bb7-115">通常，你将需要执行以下步骤来使用 API：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-115">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="f4bb7-116">创建 Azure AD Azure Active Directory (应用程序) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-116">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="f4bb7-117">使用此应用程序获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-117">Get an access token using this application.</span></span>
- <span data-ttu-id="f4bb7-118">使用令牌访问 Defender for Endpoint API。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-118">Use the token to access Defender for Endpoint API.</span></span>

<span data-ttu-id="f4bb7-119">本文介绍了如何创建 Azure AD 应用程序、获取 Microsoft Defender for Endpoint 的访问令牌并验证令牌。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-119">This article explains how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="f4bb7-120">创建应用</span><span class="sxs-lookup"><span data-stu-id="f4bb7-120">Create an app</span></span>

1. <span data-ttu-id="f4bb7-121">使用具有全局管理员角色 **的用户登录到** [Azure。](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="f4bb7-121">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="f4bb7-122">导航到 **Azure Active Directory**  >  **应用注册**  >  **""新注册"。**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![应用程序注册Microsoft Azure导航的图像](images/atp-azure-new-app2.png)

3. <span data-ttu-id="f4bb7-124">在注册表单中，选择应用程序的名称，然后选择"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-124">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="f4bb7-125">若要使你的应用能够访问适用于终结点的 Defender 并为其分配"读取所有警报"权限，请在应用程序页面上，选择 **"API** 权限""添加我的组织使用 > 的权限  >    >  API"，键入 **WindowsDefenderATP，** 然后选择 **"WindowsDefenderATP"。**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-125">To enable your app to access Defender for Endpoint and assign it **'Read all alerts'** permission, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **WindowsDefenderATP**, and then select **WindowsDefenderATP**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f4bb7-126">*WindowsDefenderATP* 不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-126">*WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="f4bb7-127">开始在文本框中写入其名称，以查看其显示。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-127">Start writing its name in the text box to see it appear.</span></span>

   ![添加权限](images/add-permission.png)

   - <span data-ttu-id="f4bb7-129">选择 **"应用程序权限**  >  **""Alert.Read.All"，** 然后选择"**添加权限"。**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-129">Select **Application permissions** > **Alert.Read.All**, and then select **Add permissions**.</span></span>

   ![应用权限](images/application-permissions.png)

     <span data-ttu-id="f4bb7-131">您需要选择相关权限。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-131">You need to select the relevant permissions.</span></span> <span data-ttu-id="f4bb7-132">"读取所有警报"只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-132">'Read All Alerts' is only an example.</span></span> <span data-ttu-id="f4bb7-133">例如：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-133">For instance:</span></span>

     - <span data-ttu-id="f4bb7-134">若要 [运行高级查询](run-advanced-query-api.md)，请选择"运行高级查询"权限。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-134">To [run advanced queries](run-advanced-query-api.md), select the 'Run advanced queries' permission.</span></span>
     - <span data-ttu-id="f4bb7-135">若要 [隔离设备，](isolate-machine.md)请选择"隔离计算机"权限。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-135">To [isolate a device](isolate-machine.md), select the 'Isolate machine' permission.</span></span>
     - <span data-ttu-id="f4bb7-136">若要确定所需的权限，请查看要调用的API 中的"权限"部分。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-136">To determine which permission you need, look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="f4bb7-137">选择 **"授予同意"。**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-137">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="f4bb7-138">每次添加权限时，都必须选择"授予 **同意** "，新权限才能生效。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-138">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![授予权限](images/grant-consent.png)

6. <span data-ttu-id="f4bb7-140">若要将密码添加到应用程序，请选择"证书&**密码"，** 向密码添加说明，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-140">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4bb7-141">选择"添加 **"后**，**选择"复制生成的机密值"。**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-141">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="f4bb7-142">离开后将无法检索此值。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-142">You won't be able to retrieve this value after you leave.</span></span>

    ![创建应用密钥的图像](images/webapp-create-key2.png)

7. <span data-ttu-id="f4bb7-144">记下应用程序 ID 和租户 ID。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-144">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="f4bb7-145">在应用程序页面上，转到" **概述"** 并复制以下内容。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-145">On your application page, go to **Overview** and copy the following.</span></span>

   ![已创建应用 ID 的图像](images/app-and-tenant-ids.png)

8. <span data-ttu-id="f4bb7-147">**仅适用于适用于终结点合作伙伴的 Microsoft Defender。**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-147">**For Microsoft Defender for Endpoint Partners only**.</span></span> <span data-ttu-id="f4bb7-148">在获得同意后，将 (设置为可在所有租户中) 。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-148">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="f4bb7-149">例如 **，** 如果你创建一个旨在在多个客户的租户 (运行的应用，则第三方应用需要) 。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-149">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="f4bb7-150">如果创建的 **服务仅在** 租户中运行 (则不需要这样做，例如，如果创建一个应用程序供自己使用，而该应用程序仅与你自己的数据记录进行交互) 。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-150">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="f4bb7-151">若要将应用设置为多租户：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-151">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="f4bb7-152">转到 **身份验证**，并添加 `https://portal.azure.com` 为 **重定向 URI**。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-152">Go to **Authentication**, and add `https://portal.azure.com` as the **Redirect URI**.</span></span>

    - <span data-ttu-id="f4bb7-153">在页面底部的"支持的帐户类型"下，选择多租户应用的任何组织目录应用程序许可中的"帐户"。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-153">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="f4bb7-154">你需要在打算使用应用程序的每个租户中批准你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-154">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="f4bb7-155">这是因为应用程序代表你的客户与 Defender for Endpoint 交互。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-155">This is because your application interacts Defender for Endpoint on behalf of your customer.</span></span>

    <span data-ttu-id="f4bb7-156">如果你 (需要选择同意链接并批准你的应用的第三方应用，) 或你的客户。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-156">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="f4bb7-157">应在 Active Directory 中拥有管理权限的用户征得同意。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-157">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="f4bb7-158">同意链接格式如下：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-158">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="f4bb7-159">其中，00000000-0000-0000-0000-0000000000000 将替换为应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-159">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="f4bb7-160">**完成！**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-160">**Done!**</span></span> <span data-ttu-id="f4bb7-161">已成功注册应用程序！</span><span class="sxs-lookup"><span data-stu-id="f4bb7-161">You have successfully registered an application!</span></span> <span data-ttu-id="f4bb7-162">有关令牌获取和验证，请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-162">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="f4bb7-163">获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="f4bb7-163">Get an access token</span></span>

<span data-ttu-id="f4bb7-164">有关 Azure AD 令牌详细信息，请参阅 [Azure AD 教程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-164">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="f4bb7-165">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4bb7-165">Use PowerShell</span></span>

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

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
```

### <a name="use-c"></a><span data-ttu-id="f4bb7-166">使用C#：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-166">Use C#:</span></span>

<span data-ttu-id="f4bb7-167">使用 Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 NuGet测试了以下代码。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-167">The following code was tested with NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="f4bb7-168">创建新的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-168">Create a new console application.</span></span>
1. <span data-ttu-id="f4bb7-169">安装NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-169">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="f4bb7-170">添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-170">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="f4bb7-171">在应用中复制并粘贴以下 (请不要忘记更新三个变量 ```tenantId, appId, appSecret``` ：) ：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-171">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

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


### <a name="use-python"></a><span data-ttu-id="f4bb7-172">使用 Python</span><span class="sxs-lookup"><span data-stu-id="f4bb7-172">Use Python</span></span>

<span data-ttu-id="f4bb7-173">请参阅 [使用 Python 获取令牌](run-advanced-query-sample-python.md#get-token)。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-173">See [Get token using Python](run-advanced-query-sample-python.md#get-token).</span></span>

### <a name="use-curl"></a><span data-ttu-id="f4bb7-174">使用时</span><span class="sxs-lookup"><span data-stu-id="f4bb7-174">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="f4bb7-175">以下过程假定计算机上已安装 Windows 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-175">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="f4bb7-176">打开命令提示符，CLIENT_ID Azure 应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-176">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="f4bb7-177">将CLIENT_SECRET Azure 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-177">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="f4bb7-178">将TENANT_ID设置为想要使用你的应用访问 Defender for Endpoint 的客户的 Azure 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-178">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Defender for Endpoint.</span></span>
1. <span data-ttu-id="f4bb7-179">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-179">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="f4bb7-180">您将获得以下形式的答案：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-180">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="f4bb7-181">验证令牌</span><span class="sxs-lookup"><span data-stu-id="f4bb7-181">Validate the token</span></span>

<span data-ttu-id="f4bb7-182">确保你收到了正确的令牌：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-182">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="f4bb7-183">将上一步获取的令牌复制并粘贴到 [JWT](https://jwt.ms) 中，以便解码它。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-183">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="f4bb7-184">验证您是否获得具有所需权限的"角色"声明</span><span class="sxs-lookup"><span data-stu-id="f4bb7-184">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="f4bb7-185">在下图中，你可以看到从应用获取的解码令牌，该应用具有对 Endpoint 的所有 Microsoft Defender 角色的权限：</span><span class="sxs-lookup"><span data-stu-id="f4bb7-185">In the following image, you can see a decoded token acquired from an app with permissions to all of  Microsoft Defender for Endpoint's roles:</span></span>

![令牌验证图像](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="f4bb7-187">使用令牌访问 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="f4bb7-187">Use the token to access Microsoft Defender for Endpoint API</span></span>

1. <span data-ttu-id="f4bb7-188">选择想要使用的 API。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-188">Choose the API you want to use.</span></span> <span data-ttu-id="f4bb7-189">有关详细信息，请参阅受支持的[Defender 终结点 API。](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="f4bb7-189">For more information, see [Supported Defender for Endpoint APIs](exposed-apis-list.md).</span></span>
1. <span data-ttu-id="f4bb7-190">将你发送到"Bearer {token}"的 http 请求中的授权标头 (Bearer 是授权方案) 。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-190">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>
1. <span data-ttu-id="f4bb7-191">令牌的过期时间为一小时。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-191">The expiration time of the token is one hour.</span></span> <span data-ttu-id="f4bb7-192">可以使用同一令牌发送多个请求。</span><span class="sxs-lookup"><span data-stu-id="f4bb7-192">You can send more than one request with the same token.</span></span>

<span data-ttu-id="f4bb7-193">下面是一个通过以下方法发送请求以获取警报列表 **C#：**</span><span class="sxs-lookup"><span data-stu-id="f4bb7-193">The following is an example of sending a request to get a list of alerts **using C#**:</span></span> 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a><span data-ttu-id="f4bb7-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4bb7-194">See also</span></span>
- [<span data-ttu-id="f4bb7-195">支持的 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="f4bb7-195">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="f4bb7-196">代表用户访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4bb7-196">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)
