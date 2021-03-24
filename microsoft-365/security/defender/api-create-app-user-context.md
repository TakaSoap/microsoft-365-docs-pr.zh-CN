---
title: 创建应用以代表用户访问 Microsoft 365 Defender API
description: 了解如何代表用户访问 Microsoft 365 Defender API。
keywords: 访问，代表用户， api， 应用程序， 用户， 访问令牌， 令牌，
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: bffe38ff5dc4c11ed25519c86081e24ff1191e94
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056559"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="61227-104">创建应用以代表用户访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="61227-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="61227-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="61227-105">**Applies to:**</span></span>

- <span data-ttu-id="61227-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61227-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61227-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="61227-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="61227-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="61227-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="61227-109">此页面介绍如何创建应用程序以代表单个用户以编程方式访问 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="61227-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="61227-110">如果你需要在未定义用户 (的情况下以编程方式访问 Microsoft 365 Defender，例如，如果你正在编写后台应用或守护程序) ，请参阅创建应用以在没有用户的情况下访问[Microsoft 365 Defender。](api-create-app-web.md)</span><span class="sxs-lookup"><span data-stu-id="61227-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="61227-111">如果你需要为多个租户提供访问权限（例如，如果你为大型组织或一组客户提供服务）请参阅创建具有 [Microsoft 365 Defender API](api-partner-access.md)合作伙伴访问权限的应用。如果你不确定需要哪种类型的访问，请参阅 [入门](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="61227-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="61227-112">Microsoft 365 Defender 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="61227-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="61227-113">这些 API 可帮助你自动化工作流和利用 Microsoft 365 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="61227-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="61227-114">此 API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="61227-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="61227-115">有关详细信息，请参阅 [OAuth 2.0 授权代码流](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="61227-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="61227-116">通常，你将需要执行以下步骤来使用这些 API：</span><span class="sxs-lookup"><span data-stu-id="61227-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="61227-117">创建 Azure Active Directory (Azure AD) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="61227-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="61227-118">使用此应用程序获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="61227-118">Get an access token using this application.</span></span>
- <span data-ttu-id="61227-119">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="61227-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="61227-120">本文介绍如何：</span><span class="sxs-lookup"><span data-stu-id="61227-120">This article explains how to:</span></span>

- <span data-ttu-id="61227-121">创建 Azure AD 应用程序</span><span class="sxs-lookup"><span data-stu-id="61227-121">Create an Azure AD application</span></span>
- <span data-ttu-id="61227-122">获取 Microsoft 365 Defender 的访问令牌</span><span class="sxs-lookup"><span data-stu-id="61227-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="61227-123">验证令牌</span><span class="sxs-lookup"><span data-stu-id="61227-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="61227-124">代表用户访问 Microsoft 365 Defender API 时，需要正确的应用程序权限和用户权限。</span><span class="sxs-lookup"><span data-stu-id="61227-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="61227-125">如果你有权在门户中执行一个操作，则你有权在 API 中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="61227-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="61227-126">创建应用</span><span class="sxs-lookup"><span data-stu-id="61227-126">Create an app</span></span>

1. <span data-ttu-id="61227-127">以具有全局管理员角色的用户 **登录** [Azure。](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="61227-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="61227-128">导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册**。</span><span class="sxs-lookup"><span data-stu-id="61227-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure 的图像和应用程序注册导航](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="61227-130">在表单中，为应用程序选择一个名称，然后输入重定向 URI 的以下信息，然后选择"注册 **"。**</span><span class="sxs-lookup"><span data-stu-id="61227-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   !["创建应用程序"窗口的图像](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="61227-132">**应用程序类型：** 公共客户端</span><span class="sxs-lookup"><span data-stu-id="61227-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="61227-133">**重定向 URI：**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="61227-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="61227-134">在应用程序页面上，选择 **"API** 权限""添加我的组织使用>  >    >   API"，键入 **"Microsoft 威胁** 防护"，然后选择 **"Microsoft 威胁防护"。**</span><span class="sxs-lookup"><span data-stu-id="61227-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="61227-135">你的应用现在可以访问 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="61227-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="61227-136">*Microsoft 威胁防护* 是 Microsoft 365 Defender 的以前名称，不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="61227-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="61227-137">你需要开始在文本框中写入其名称，以查看其显示。</span><span class="sxs-lookup"><span data-stu-id="61227-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![API 权限选择的图像](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="61227-139">选择 **"委派权限"。**</span><span class="sxs-lookup"><span data-stu-id="61227-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="61227-140">为方案选择相关权限，例如 (**Incident.Read**) ，然后选择"**添加权限"。**</span><span class="sxs-lookup"><span data-stu-id="61227-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![API 访问和 API 选择的图像](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="61227-142">您需要为方案选择相关权限。</span><span class="sxs-lookup"><span data-stu-id="61227-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="61227-143">*读取所有事件* 只是一个示例。</span><span class="sxs-lookup"><span data-stu-id="61227-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="61227-144">若要确定所需的权限，请查看要调用的 API中的"权限"部分。</span><span class="sxs-lookup"><span data-stu-id="61227-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="61227-145">例如，若要 [运行高级查询](api-advanced-hunting.md)，请选择"运行高级查询"权限;若要 [隔离设备](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)，请选择"隔离计算机"权限。</span><span class="sxs-lookup"><span data-stu-id="61227-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="61227-146">选择 **"授予管理员同意"。**</span><span class="sxs-lookup"><span data-stu-id="61227-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="61227-147">每次添加权限时，都必须选择"授予管理员 **同意** ，让权限生效"。</span><span class="sxs-lookup"><span data-stu-id="61227-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![授予权限的图像](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="61227-149">在安全的地方记录应用程序 ID 和租户 ID。</span><span class="sxs-lookup"><span data-stu-id="61227-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="61227-150">它们列在应用程序 **页面上的"** 概述"下。</span><span class="sxs-lookup"><span data-stu-id="61227-150">They're listed under **Overview** on your application page.</span></span>

   ![已创建应用 ID 的图像](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="61227-152">获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="61227-152">Get an access token</span></span>

<span data-ttu-id="61227-153">有关 Azure Active Directory 令牌详细信息，请参阅 [Azure AD 教程](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="61227-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="61227-154">使用 PowerShell 获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="61227-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="61227-155">验证令牌</span><span class="sxs-lookup"><span data-stu-id="61227-155">Validate the token</span></span>

1. <span data-ttu-id="61227-156">将令牌复制并粘贴到 [JWT](https://jwt.ms) 中以解码它。</span><span class="sxs-lookup"><span data-stu-id="61227-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="61227-157">确保解码 *令牌* 中的角色声明包含所需的权限。</span><span class="sxs-lookup"><span data-stu-id="61227-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="61227-158">在下图中，你可以看到从应用获取的解码令牌，具有 、 和 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` 权限：</span><span class="sxs-lookup"><span data-stu-id="61227-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![令牌验证图像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="61227-160">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="61227-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="61227-161">选择要用于事件或高级搜寻 () API。</span><span class="sxs-lookup"><span data-stu-id="61227-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="61227-162">有关详细信息，请参阅支持的[Microsoft 365 Defender API。](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="61227-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="61227-163">在即将发送的 http 请求中，将授权标头设置为 `"Bearer" <token>` *，Bearer* 为授权方案，令牌为经过验证的令牌。</span><span class="sxs-lookup"><span data-stu-id="61227-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="61227-164">令牌将在一小时内过期。</span><span class="sxs-lookup"><span data-stu-id="61227-164">The token will expire within one hour.</span></span> <span data-ttu-id="61227-165">在此期间，可以使用同一令牌发送多个请求。</span><span class="sxs-lookup"><span data-stu-id="61227-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="61227-166">以下示例演示如何发送请求，以使用 C# 获取 **事件列表**。</span><span class="sxs-lookup"><span data-stu-id="61227-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="61227-167">相关文章</span><span class="sxs-lookup"><span data-stu-id="61227-167">Related articles</span></span>

- [<span data-ttu-id="61227-168">Microsoft 365 Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="61227-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="61227-169">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="61227-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="61227-170">创建"Hello world"应用</span><span class="sxs-lookup"><span data-stu-id="61227-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="61227-171">创建应用以在没有用户的情况下访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61227-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="61227-172">创建具有对 Microsoft 365 Defender API 的多租户合作伙伴访问权限的应用</span><span class="sxs-lookup"><span data-stu-id="61227-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="61227-173">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="61227-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="61227-174">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="61227-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="61227-175">用户登录和 API 访问的 OAuth 2.0 授权</span><span class="sxs-lookup"><span data-stu-id="61227-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)