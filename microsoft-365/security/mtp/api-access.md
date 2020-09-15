---
title: 访问 Microsoft 威胁防护 Api
description: 了解如何访问 Microsoft 威胁防护 Api
keywords: 访问、api、应用程序上下文、用户上下文、aad 应用程序、访问令牌
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
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650176"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="6dd06-104">访问 Microsoft 威胁防护 Api</span><span class="sxs-lookup"><span data-stu-id="6dd06-104">Access the Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="6dd06-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6dd06-105">**Applies to:**</span></span>
- <span data-ttu-id="6dd06-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6dd06-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="6dd06-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="6dd06-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6dd06-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6dd06-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="6dd06-109">Microsoft 威胁防护通过一组编程 Api 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="6dd06-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="6dd06-110">这些 Api 将使您能够基于 Microsoft 威胁防护功能自动执行工作流和创新。</span><span class="sxs-lookup"><span data-stu-id="6dd06-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="6dd06-111">API 访问需要 OAuth 2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6dd06-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="6dd06-112">有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="6dd06-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="6dd06-113">一般情况下，您需要执行以下步骤来使用 Api：</span><span class="sxs-lookup"><span data-stu-id="6dd06-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="6dd06-114">创建 AAD 应用程序</span><span class="sxs-lookup"><span data-stu-id="6dd06-114">Create an AAD application</span></span>
- <span data-ttu-id="6dd06-115">使用此应用程序获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="6dd06-115">Get an access token using this application</span></span>
- <span data-ttu-id="6dd06-116">使用令牌访问 Microsoft 威胁防护 API</span><span class="sxs-lookup"><span data-stu-id="6dd06-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="6dd06-117">您可以使用 **应用程序上下文** 或 **用户上下文**访问 Microsoft 威胁防护 API。</span><span class="sxs-lookup"><span data-stu-id="6dd06-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="6dd06-118">\*\*应用程序上下文： (建议的) \*\*</span><span class="sxs-lookup"><span data-stu-id="6dd06-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="6dd06-119">由在没有登录用户的情况下运行的应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="6dd06-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="6dd06-120">例如，运行为后台服务或守护程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dd06-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="6dd06-121">使用应用程序上下文访问 Microsoft 威胁防护 API 时需要执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="6dd06-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="6dd06-122">创建 AAD Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dd06-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="6dd06-123">将所需的权限分配给 applicationFor 示例： AdvancedHunting、 **all**、 **AdvancedHunting.Read.All**。</span><span class="sxs-lookup"><span data-stu-id="6dd06-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="6dd06-124">为此应用程序创建一个键。</span><span class="sxs-lookup"><span data-stu-id="6dd06-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="6dd06-125">使用应用程序及其键获取令牌。</span><span class="sxs-lookup"><span data-stu-id="6dd06-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="6dd06-126">使用令牌访问 Microsoft 威胁防护 API</span><span class="sxs-lookup"><span data-stu-id="6dd06-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="6dd06-127">有关详细信息，请参阅 [使用应用程序上下文获取访问权限](api-create-app-web.md)。</span><span class="sxs-lookup"><span data-stu-id="6dd06-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="6dd06-128">**用户上下文：**</span><span class="sxs-lookup"><span data-stu-id="6dd06-128">**User Context:**</span></span> <br>
    <span data-ttu-id="6dd06-129">用于代表用户在 API 中执行操作。</span><span class="sxs-lookup"><span data-stu-id="6dd06-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="6dd06-130">使用应用程序上下文访问 Microsoft 威胁防护 API 时需要执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="6dd06-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="6dd06-131">创建 AAD 本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dd06-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="6dd06-132">将所需的权限分配给应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dd06-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="6dd06-133">例如，AdvancedHunting、**读取、\*\*\*\*读取**。</span><span class="sxs-lookup"><span data-stu-id="6dd06-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="6dd06-134">使用具有用户凭据的应用程序获取令牌。</span><span class="sxs-lookup"><span data-stu-id="6dd06-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="6dd06-135">使用令牌访问 Microsoft 威胁防护 API</span><span class="sxs-lookup"><span data-stu-id="6dd06-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="6dd06-136">有关详细信息，请参阅 [Get access with user context](api-create-app-user-context.md)。</span><span class="sxs-lookup"><span data-stu-id="6dd06-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="6dd06-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="6dd06-137">Related topics</span></span>
- [<span data-ttu-id="6dd06-138">Microsoft 威胁防护 Api</span><span class="sxs-lookup"><span data-stu-id="6dd06-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="6dd06-139">使用应用程序上下文访问 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6dd06-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="6dd06-140">使用用户上下文访问 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6dd06-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
