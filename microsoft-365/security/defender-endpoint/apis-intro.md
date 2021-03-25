---
title: 访问适用于终结点的 Microsoft Defender API
ms.reviewer: ''
description: 了解如何使用 API 根据 Microsoft Defender ATP 功能自动执行工作流创新
keywords: api， api， wdatp， open api， microsoft defender atp api， 公共 api， 受支持的 api， 警报， 设备， 用户， 域， ip， 文件， 高级搜寻， 查询
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 70a8ba9d3ff864ca58c856714b00f0e8feba933a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164740"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="137b1-104">访问适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="137b1-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="137b1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="137b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="137b1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="137b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="137b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="137b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="137b1-108">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="137b1-108">**Applies to:**</span></span> 
- [<span data-ttu-id="137b1-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="137b1-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="137b1-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="137b1-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="137b1-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="137b1-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="137b1-112">Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="137b1-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="137b1-113">这些 API 将使您能够基于 Defender for Endpoint 功能自动执行工作流创新。</span><span class="sxs-lookup"><span data-stu-id="137b1-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="137b1-114">API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="137b1-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="137b1-115">有关详细信息，请参阅 [OAuth 2.0 授权代码流](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="137b1-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="137b1-116">观看此视频，快速概览适用于终结点的 API 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="137b1-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="137b1-117">通常，你将需要执行以下步骤来使用 API：</span><span class="sxs-lookup"><span data-stu-id="137b1-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="137b1-118">创建 AAD 应用程序</span><span class="sxs-lookup"><span data-stu-id="137b1-118">Create an AAD application</span></span>
- <span data-ttu-id="137b1-119">使用此应用程序获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="137b1-119">Get an access token using this application</span></span>
- <span data-ttu-id="137b1-120">使用令牌访问 Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="137b1-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="137b1-121">可以使用应用程序上下文或用户 **上下文访问** Defender for Endpoint **API。**</span><span class="sxs-lookup"><span data-stu-id="137b1-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="137b1-122">**应用程序上下文： (推荐)**</span><span class="sxs-lookup"><span data-stu-id="137b1-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="137b1-123">由在没有登录用户存在的情况下运行的应用使用。</span><span class="sxs-lookup"><span data-stu-id="137b1-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="137b1-124">例如，作为后台服务或守护程序运行的应用。</span><span class="sxs-lookup"><span data-stu-id="137b1-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="137b1-125">使用应用程序上下文访问 Defender for Endpoint API 需要执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="137b1-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="137b1-126">创建 AAD Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="137b1-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="137b1-127">为应用程序分配所需的权限，例如，"读取警报"和"隔离计算机"。</span><span class="sxs-lookup"><span data-stu-id="137b1-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="137b1-128">为此应用程序创建密钥。</span><span class="sxs-lookup"><span data-stu-id="137b1-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="137b1-129">使用应用程序及其密钥获取令牌。</span><span class="sxs-lookup"><span data-stu-id="137b1-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="137b1-130">使用令牌访问 Microsoft Defender ATP API</span><span class="sxs-lookup"><span data-stu-id="137b1-130">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="137b1-131">有关详细信息，请参阅获取 [应用程序上下文的访问权限](exposed-apis-create-app-webapp.md)。</span><span class="sxs-lookup"><span data-stu-id="137b1-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="137b1-132">**用户上下文：**</span><span class="sxs-lookup"><span data-stu-id="137b1-132">**User Context:**</span></span> <br>
    <span data-ttu-id="137b1-133">用于代表用户执行 API 中的操作。</span><span class="sxs-lookup"><span data-stu-id="137b1-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="137b1-134">使用应用程序上下文访问 Defender for Endpoint API 要执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="137b1-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="137b1-135">创建 AAD Native-Application。</span><span class="sxs-lookup"><span data-stu-id="137b1-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="137b1-136">为应用程序分配所需的权限，例如"读取警报"和"隔离计算机"等。</span><span class="sxs-lookup"><span data-stu-id="137b1-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="137b1-137">使用具有用户凭据的应用程序获取令牌。</span><span class="sxs-lookup"><span data-stu-id="137b1-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="137b1-138">使用令牌访问 Microsoft Defender ATP API</span><span class="sxs-lookup"><span data-stu-id="137b1-138">Use the token to access Microsoft Defender ATP API</span></span>

     <span data-ttu-id="137b1-139">有关详细信息，请参阅使用 [用户上下文获取访问权限](exposed-apis-create-app-nativeapp.md)。</span><span class="sxs-lookup"><span data-stu-id="137b1-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="137b1-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="137b1-140">Related topics</span></span>
- [<span data-ttu-id="137b1-141">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="137b1-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="137b1-142">使用应用程序上下文访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="137b1-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="137b1-143">使用用户上下文访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="137b1-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
