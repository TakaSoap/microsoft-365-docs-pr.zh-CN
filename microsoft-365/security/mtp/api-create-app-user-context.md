---
title: 使用代表用户访问 Microsoft 365 Defender Api
description: 了解如何使用代表用户访问 Microsoft 365 Defender Api
keywords: 代表用户、api、应用程序、用户、访问令牌、令牌的访问权限
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
ms.openlocfilehash: a72bc7648045e5cc37a1d899f9e15237ce29ed37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847352"
---
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a><span data-ttu-id="db638-104">代表用户访问 Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="db638-104">Access Microsoft 365 Defender APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="db638-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="db638-105">**Applies to:**</span></span>
- <span data-ttu-id="db638-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db638-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="db638-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="db638-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="db638-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="db638-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="db638-109">本页面介绍如何创建应用程序以获取用户的对 Microsoft 365 Defender 的编程访问权限。</span><span class="sxs-lookup"><span data-stu-id="db638-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a user.</span></span>

<span data-ttu-id="db638-110">如果需要以编程方式访问 Microsoft 365 Defender 而不使用用户，请参阅 [Create a app to Access microsoft 365 defender 而无需用户](api-create-app-web.md)。</span><span class="sxs-lookup"><span data-stu-id="db638-110">If you need programmatic access Microsoft 365 Defender without a user, refer to [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="db638-111">如果您不确定所需的访问权限，请阅读 [access The Microsoft 365 Defender api](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="db638-111">If you are not sure which access you need, read the [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="db638-112">Microsoft 365 Defender 通过一组编程 Api 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="db638-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="db638-113">这些 Api 将使您能够基于 Microsoft 365 Defender 功能自动执行工作流和创新。</span><span class="sxs-lookup"><span data-stu-id="db638-113">Those APIs will enable you to automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="db638-114">API 访问需要 OAuth 2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="db638-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="db638-115">有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="db638-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="db638-116">一般情况下，您需要执行以下步骤来使用 Api：</span><span class="sxs-lookup"><span data-stu-id="db638-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="db638-117">创建 AAD 应用程序</span><span class="sxs-lookup"><span data-stu-id="db638-117">Create an AAD application</span></span>
- <span data-ttu-id="db638-118">使用此应用程序获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="db638-118">Get an access token using this application</span></span>
- <span data-ttu-id="db638-119">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="db638-119">Use the token to access Microsoft 365 Defender API</span></span>

<span data-ttu-id="db638-120">此页说明如何创建 AAD 应用程序、获取 Microsoft 365 Defender 的访问令牌并验证令牌。</span><span class="sxs-lookup"><span data-stu-id="db638-120">This page explains how to create an AAD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="db638-121">当代表用户访问 Microsoft 365 Defender API 时，您将需要正确的应用程序权限和用户权限。</span><span class="sxs-lookup"><span data-stu-id="db638-121">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="db638-122">如果您有权在门户中执行某项操作，则您有权在 API 中执行该操作。</span><span class="sxs-lookup"><span data-stu-id="db638-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="db638-123">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="db638-123">Create an app</span></span>

1. <span data-ttu-id="db638-124">使用具有 **全局管理员** 角色的用户登录到 [Azure](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="db638-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="db638-125">导航到 **Azure Active Directory**  >  **应用注册**  >  **新注册** 。</span><span class="sxs-lookup"><span data-stu-id="db638-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure 的图像和到应用程序注册的导航](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="db638-127">在 "注册来源" 中，输入以下信息，然后单击 " **注册** "。</span><span class="sxs-lookup"><span data-stu-id="db638-127">In the registration from, enter the following information then click **Register**.</span></span>

   !["创建应用程序" 窗口的图像](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="db638-129">**名称：** 您的应用程序名称</span><span class="sxs-lookup"><span data-stu-id="db638-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="db638-130">**应用程序类型：** 公共客户端</span><span class="sxs-lookup"><span data-stu-id="db638-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="db638-131">**重定向 URI：**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="db638-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="db638-132">若要使您的应用程序能够访问 Microsoft 365 Defender 并分配 it 权限，请在应用程序页上，选择 " **API 权限** "  >  **Add permission**  >  **"添加我的组织使用** > 的权限 api"，键入 **microsoft 365 Defender** ，然后选择 " **microsoft 365 defender** "。</span><span class="sxs-lookup"><span data-stu-id="db638-132">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="db638-133">Microsoft 365 Defender 不会显示在原始列表中。</span><span class="sxs-lookup"><span data-stu-id="db638-133">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="db638-134">您需要先在文本框中写入其名称，才能看到它的显示。</span><span class="sxs-lookup"><span data-stu-id="db638-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![API 访问和 API 选择的图像](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="db638-136">选择 " **委派权限** " > 选择适用于您的方案的相关权限，如 " **事件** "，然后选择 " **添加权限** "。</span><span class="sxs-lookup"><span data-stu-id="db638-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read** , and then select **Add permissions**.</span></span>

      ![API 访问和 API 选择的图像](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="db638-138">您需要选择相关权限。</span><span class="sxs-lookup"><span data-stu-id="db638-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="db638-139">若要确定所需的权限，请查看您想要调用的 API 中的 " **权限** " 部分。</span><span class="sxs-lookup"><span data-stu-id="db638-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="db638-140">单击 " **授予同意** "</span><span class="sxs-lookup"><span data-stu-id="db638-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="db638-141">每次添加权限时，都必须单击 " **授予许可** " 以使新权限生效。</span><span class="sxs-lookup"><span data-stu-id="db638-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![授予权限的图像](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="db638-143">记下应用程序 ID 和租户 ID：</span><span class="sxs-lookup"><span data-stu-id="db638-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="db638-144">在应用程序页上，转到 " **概述** " 并复制以下内容：</span><span class="sxs-lookup"><span data-stu-id="db638-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![已创建应用程序 id 的图像](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="db638-146">使用 PowerShell 获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="db638-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="db638-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="db638-147">Related topics</span></span>
- [<span data-ttu-id="db638-148">访问 Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="db638-148">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="db638-149">使用应用程序上下文访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db638-149">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
