---
title: 访问 Microsoft 365 Defender Api
description: 了解如何访问 Microsoft 365 Defender Api
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
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845009"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="23076-104">访问 Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="23076-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="23076-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="23076-105">**Applies to:**</span></span>
- <span data-ttu-id="23076-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23076-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="23076-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="23076-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="23076-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="23076-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="23076-109">Microsoft 365 Defender 通过一组编程 Api 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="23076-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="23076-110">这些 Api 将使您能够自动化基于 Microsoft 365 Defender 功能的工作流和创新。</span><span class="sxs-lookup"><span data-stu-id="23076-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="23076-111">API 访问需要 OAuth 2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="23076-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="23076-112">有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="23076-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="23076-113">一般情况下，您需要执行以下步骤来使用 Api：</span><span class="sxs-lookup"><span data-stu-id="23076-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="23076-114">创建 AAD 应用程序</span><span class="sxs-lookup"><span data-stu-id="23076-114">Create an AAD application</span></span>
- <span data-ttu-id="23076-115">使用此应用程序获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="23076-115">Get an access token using this application</span></span>
- <span data-ttu-id="23076-116">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="23076-116">Use the token to access  Microsoft 365 Defender API</span></span>


<span data-ttu-id="23076-117">您可以使用 **应用程序上下文** 或 **用户上下文** 访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="23076-117">You can access Microsoft 365 Defender API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="23076-118">**应用程序上下文： (建议的)**</span><span class="sxs-lookup"><span data-stu-id="23076-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="23076-119">由在没有登录用户的情况下运行的应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="23076-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="23076-120">例如，运行为后台服务或守护程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="23076-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="23076-121">使用应用程序上下文访问 Microsoft 365 Defender API 时需要执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="23076-121">Steps that need to be taken to access  Microsoft 365 Defender API with application context:</span></span>

  1. <span data-ttu-id="23076-122">创建 AAD Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="23076-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="23076-123">将所需的权限分配给 applicationFor 示例： AdvancedHunting、 **all** 、 **AdvancedHunting.Read.All** 。</span><span class="sxs-lookup"><span data-stu-id="23076-123">Assign the desired permission to the applicationFor example, **Incident.Read.All** , **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="23076-124">为此应用程序创建一个键。</span><span class="sxs-lookup"><span data-stu-id="23076-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="23076-125">使用应用程序及其键获取令牌。</span><span class="sxs-lookup"><span data-stu-id="23076-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="23076-126">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="23076-126">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="23076-127">有关详细信息，请参阅 [使用应用程序上下文获取访问权限](api-create-app-web.md)。</span><span class="sxs-lookup"><span data-stu-id="23076-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="23076-128">**用户上下文：**</span><span class="sxs-lookup"><span data-stu-id="23076-128">**User Context:**</span></span> <br>
    <span data-ttu-id="23076-129">用于代表用户在 API 中执行操作。</span><span class="sxs-lookup"><span data-stu-id="23076-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="23076-130">要使用应用程序上下文访问 Microsoft 365 Defender API 时需要执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="23076-130">Steps that needs to be taken to access  Microsoft 365 Defender API with application context:</span></span>
  1. <span data-ttu-id="23076-131">创建 AAD 本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="23076-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="23076-132">将所需的权限分配给应用程序。</span><span class="sxs-lookup"><span data-stu-id="23076-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="23076-133">例如，AdvancedHunting、 **读取、\*\*\*\*读取** 。</span><span class="sxs-lookup"><span data-stu-id="23076-133">For example, **Incident.Read** , **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="23076-134">使用具有用户凭据的应用程序获取令牌。</span><span class="sxs-lookup"><span data-stu-id="23076-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="23076-135">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="23076-135">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="23076-136">有关详细信息，请参阅 [Get access with user context](api-create-app-user-context.md)。</span><span class="sxs-lookup"><span data-stu-id="23076-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="23076-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="23076-137">Related topics</span></span>
- [<span data-ttu-id="23076-138">Microsoft 365 Defender Api</span><span class="sxs-lookup"><span data-stu-id="23076-138">Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="23076-139">使用应用程序上下文访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23076-139">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="23076-140">使用用户上下文访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23076-140">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
