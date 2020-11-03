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
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="2abe5-104">创建在没有用户的情况下访问 Microsoft 365 Defender 的应用程序</span><span class="sxs-lookup"><span data-stu-id="2abe5-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2abe5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2abe5-105">**Applies to:**</span></span>
- <span data-ttu-id="2abe5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2abe5-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="2abe5-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="2abe5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2abe5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="2abe5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2abe5-109">本页介绍如何创建应用程序，以在没有用户的情况下获取对 Microsoft 365 Defender 的编程访问权限。</span><span class="sxs-lookup"><span data-stu-id="2abe5-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a user.</span></span> <span data-ttu-id="2abe5-110">如果需要以编程方式代表用户访问 Microsoft 365 Defender，请参阅 [Get access with user context](api-create-app-user-context.md)。</span><span class="sxs-lookup"><span data-stu-id="2abe5-110">If you need programmatic access to Microsoft 365 Defender on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="2abe5-111">如果您不确定所需的访问权限，请参阅 [入门](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="2abe5-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="2abe5-112">Microsoft 365 Defender 通过一组编程 Api 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="2abe5-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="2abe5-113">这些 Api 将帮助您基于 Microsoft 365 Defender 功能自动执行工作流和创新。</span><span class="sxs-lookup"><span data-stu-id="2abe5-113">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="2abe5-114">API 访问需要 OAuth 2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="2abe5-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="2abe5-115">有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="2abe5-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="2abe5-116">一般情况下，您需要执行以下步骤来使用 Api：</span><span class="sxs-lookup"><span data-stu-id="2abe5-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="2abe5-117"> (Azure AD) 应用程序创建 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="2abe5-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="2abe5-118">使用此应用程序获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="2abe5-118">Get an access token using this application.</span></span>
- <span data-ttu-id="2abe5-119">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="2abe5-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="2abe5-120">本文介绍如何创建 Azure AD 应用程序，获取 Microsoft 365 Defender 的访问令牌，并验证令牌。</span><span class="sxs-lookup"><span data-stu-id="2abe5-120">This article explains how to create an Azure AD application, get an access token to Microsoft 365 Defender, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="2abe5-121">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="2abe5-121">Create an app</span></span>

1. <span data-ttu-id="2abe5-122">使用具有 **全局管理员** 角色的用户登录到 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="2abe5-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="2abe5-123">导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册** 。</span><span class="sxs-lookup"><span data-stu-id="2abe5-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的图像和到应用程序注册的导航](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="2abe5-125">在 "注册" 表单中，选择您的应用程序的名称，然后选择 " **注册** "。</span><span class="sxs-lookup"><span data-stu-id="2abe5-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="2abe5-126">若要使您的应用程序能够访问 Microsoft 365 Defender 并分配 it 权限，请在应用程序页上，选择 " **API 权限** "  >  **Add permission**  >  **"添加我的组织使用** > 的权限 api"，键入 **microsoft 365 Defender** ，然后选择 " **microsoft 365 defender** "。</span><span class="sxs-lookup"><span data-stu-id="2abe5-126">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2abe5-127">Microsoft 365 Defender 不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="2abe5-127">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="2abe5-128">您需要先在文本框中写入其名称，才能看到它的显示。</span><span class="sxs-lookup"><span data-stu-id="2abe5-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 访问和 API 选择的图像](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="2abe5-130">选择 " **应用程序权限** " > 选择适用于您的方案的相关权限，例如 " **Incident. 全部** "，然后选择 " **添加权限** "。</span><span class="sxs-lookup"><span data-stu-id="2abe5-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All** , and then select **Add permissions**.</span></span>

   ![API 访问和 API 选择的图像](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="2abe5-132">您需要选择适用于您的方案的相关权限，即 **"读取所有事件"** 就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="2abe5-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="2abe5-133">若要确定所需的权限，请查看您想要调用的 API 中的 " **权限** " 部分。</span><span class="sxs-lookup"><span data-stu-id="2abe5-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="2abe5-134">选择 " **授予同意** "。</span><span class="sxs-lookup"><span data-stu-id="2abe5-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="2abe5-135">每次添加权限时，您都必须选择 " **授予许可** " 以使新权限生效。</span><span class="sxs-lookup"><span data-stu-id="2abe5-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![授予权限的图像](../../media/grant-consent.PNG)

6. <span data-ttu-id="2abe5-137">若要将机密添加到应用程序，请选择 " **证书 & 密码** "，将说明添加到密码，然后选择 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="2abe5-137">To add a secret to the application, select **Certificates & secrets** , add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2abe5-138">选择 " **添加** " 后，选择 **"复制生成的机密值"** 。</span><span class="sxs-lookup"><span data-stu-id="2abe5-138">After you select **Add** , select **copy the generated secret value**.</span></span> <span data-ttu-id="2abe5-139">离开后，将无法检索此值。</span><span class="sxs-lookup"><span data-stu-id="2abe5-139">You won't be able to retrieve this value after you leave.</span></span>

    ![创建应用程序密钥的图像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="2abe5-141">记下应用程序 ID 和租户 ID。</span><span class="sxs-lookup"><span data-stu-id="2abe5-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="2abe5-142">在应用程序页上，转到 " **概述** " 并复制以下项。</span><span class="sxs-lookup"><span data-stu-id="2abe5-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![已创建应用程序 id 的图像](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="2abe5-144">**仅适用于 Microsoft 365 Defender 合作伙伴** 。</span><span class="sxs-lookup"><span data-stu-id="2abe5-144">**For Microsoft 365 Defender Partners only**.</span></span> <span data-ttu-id="2abe5-145">[请按照此处的说明进行操作](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)。</span><span class="sxs-lookup"><span data-stu-id="2abe5-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="2abe5-146">将您的应用程序设置为多租用 (同意后在所有租户中可用) 。</span><span class="sxs-lookup"><span data-stu-id="2abe5-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="2abe5-147">这是第三方应用程序 **所必需** 的 (例如，如果创建一个打算在多客户租户) 中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2abe5-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="2abe5-148">如果创建要仅在租户中运行的服务，则不需要这样做 (例如，如果为自己的使用创建一个仅与您自己的数据) 交互的应用程序，则 **不需要** 这样做。</span><span class="sxs-lookup"><span data-stu-id="2abe5-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="2abe5-149">若要将您的应用程序设置为多租用，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2abe5-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="2abe5-150">转到 " **身份验证** "，并添加 https://portal.azure.com 为 **重定向 URI** 。</span><span class="sxs-lookup"><span data-stu-id="2abe5-150">Go to **Authentication** , and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="2abe5-151">在页面底部的 " **支持的帐户类型** " 下，选择针对你的多租户应用的 **任何组织目录** 应用程序中的帐户。</span><span class="sxs-lookup"><span data-stu-id="2abe5-151">On the bottom of the page, under **Supported account types** , select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="2abe5-152">您需要在要使用的每个租户中批准您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2abe5-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="2abe5-153">这是因为您的应用程序代表您的客户交互 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="2abe5-153">This is because your application interacts Microsoft 365 Defender on behalf of your customer.</span></span>

    <span data-ttu-id="2abe5-154">如果您正在编写第三方应用程序，则 (或您的客户) 需要选择许可链接并批准您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2abe5-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="2abe5-155">应使用在 Active Directory 中具有管理权限的用户来完成许可。</span><span class="sxs-lookup"><span data-stu-id="2abe5-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="2abe5-156">同意链接的格式如下：</span><span class="sxs-lookup"><span data-stu-id="2abe5-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="2abe5-157">其中，00000000-0000-0000-0000-000000000000 替换为您的应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="2abe5-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="2abe5-158">**为了!**</span><span class="sxs-lookup"><span data-stu-id="2abe5-158">**Done!**</span></span> <span data-ttu-id="2abe5-159">已成功注册应用程序！</span><span class="sxs-lookup"><span data-stu-id="2abe5-159">You have successfully registered an application!</span></span> <span data-ttu-id="2abe5-160">有关令牌获取和验证，请参阅下面的示例。</span><span class="sxs-lookup"><span data-stu-id="2abe5-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="2abe5-161">获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="2abe5-161">Get an access token</span></span>

<span data-ttu-id="2abe5-162">有关 Azure AD 令牌的更多详细信息，请参阅 [AZURE ad 教程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="2abe5-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="2abe5-163">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2abe5-163">Use PowerShell</span></span>

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

### <a name="use-c"></a><span data-ttu-id="2abe5-164">使用 c #：</span><span class="sxs-lookup"><span data-stu-id="2abe5-164">Use C#:</span></span>

<span data-ttu-id="2abe5-165">以下代码使用 Nuget Microsoft.identitymodel.dll 3.19.8 进行测试。</span><span class="sxs-lookup"><span data-stu-id="2abe5-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="2abe5-166">创建新的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="2abe5-166">Create a new console application.</span></span>
1. <span data-ttu-id="2abe5-167">安装 Nuget [microsoft.identitymodel.dll](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="2abe5-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="2abe5-168">添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="2abe5-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="2abe5-169">在应用程序中复制并粘贴以下代码 (不会忘记更新三个变量： ```tenantId, appId, appSecret```) ：</span><span class="sxs-lookup"><span data-stu-id="2abe5-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

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


### <a name="use-python"></a><span data-ttu-id="2abe5-170">使用 Python</span><span class="sxs-lookup"><span data-stu-id="2abe5-170">Use Python</span></span> 

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
### <a name="use-curl"></a><span data-ttu-id="2abe5-171">使用卷</span><span class="sxs-lookup"><span data-stu-id="2abe5-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="2abe5-172">以下过程假定已在您的计算机上安装了 Windows 卷。</span><span class="sxs-lookup"><span data-stu-id="2abe5-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="2abe5-173">打开命令提示符，并将 CLIENT_ID 设置为您的 Azure 应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="2abe5-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="2abe5-174">将 CLIENT_SECRET 设置为您的 Azure 应用程序密码。</span><span class="sxs-lookup"><span data-stu-id="2abe5-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="2abe5-175">将 TENANT_ID 设置为要使用您的应用程序访问 Microsoft 365 Defender 的客户的 Azure 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="2abe5-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="2abe5-176">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2abe5-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="2abe5-177">您将获得以下形式的答案：</span><span class="sxs-lookup"><span data-stu-id="2abe5-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="2abe5-178">验证令牌</span><span class="sxs-lookup"><span data-stu-id="2abe5-178">Validate the token</span></span>

<span data-ttu-id="2abe5-179">确保您获得了正确的令牌：</span><span class="sxs-lookup"><span data-stu-id="2abe5-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="2abe5-180">将您在上一步中获取的令牌复制并粘贴到 [JWT](https://jwt.ms) ，以便对其进行解码。</span><span class="sxs-lookup"><span data-stu-id="2abe5-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="2abe5-181">验证是否获取了具有所需权限的 "roles" 声明</span><span class="sxs-lookup"><span data-stu-id="2abe5-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="2abe5-182">在下图中，你可以看到从应用获取的解码令牌 ```Incidents.Read.All``` ， ```Incidents.ReadWrite.All``` 以及 ```AdvancedHunting.Read.All``` 权限：</span><span class="sxs-lookup"><span data-stu-id="2abe5-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![令牌验证的图像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a><span data-ttu-id="2abe5-184">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="2abe5-184">Use the token to access Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="2abe5-185">选择要使用的 API。</span><span class="sxs-lookup"><span data-stu-id="2abe5-185">Choose the API you want to use.</span></span> <span data-ttu-id="2abe5-186">有关详细信息，请参阅 [支持的 Microsoft 365 Defender api](api-supported.md)。</span><span class="sxs-lookup"><span data-stu-id="2abe5-186">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="2abe5-187">在发送到 "持有者 {令牌}" 的 http 请求中设置授权标头， (持有者是) 的授权方案。</span><span class="sxs-lookup"><span data-stu-id="2abe5-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="2abe5-188">令牌的过期时间为1小时。</span><span class="sxs-lookup"><span data-stu-id="2abe5-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="2abe5-189">您可以发送多个具有相同令牌的请求。</span><span class="sxs-lookup"><span data-stu-id="2abe5-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="2abe5-190">下面的示例演示如何 **使用 c #** 发送获取事件列表的请求：</span><span class="sxs-lookup"><span data-stu-id="2abe5-190">The following is an example of sending a request to get a list of incidents **using C#** :</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="2abe5-191">相关主题</span><span class="sxs-lookup"><span data-stu-id="2abe5-191">Related topics</span></span>
- [<span data-ttu-id="2abe5-192">访问 Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="2abe5-192">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2abe5-193">使用应用程序上下文访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2abe5-193">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="2abe5-194">使用用户上下文访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2abe5-194">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
