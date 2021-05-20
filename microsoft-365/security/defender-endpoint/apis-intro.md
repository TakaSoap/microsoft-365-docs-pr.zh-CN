---
title: 访问 Microsoft Defender for Endpoint API
ms.reviewer: ''
description: 了解如何使用 API 根据 Microsoft Defender for Endpoint 功能自动执行工作流创新
keywords: api， api， wdatp， open api， microsoft defender for endpoint api， microsoft defender atp， 公共 api， 受支持的 api， 警报， 设备， 用户， 域， ip， 文件， 高级搜寻， 查询
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
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571825"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="35533-104">访问 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="35533-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35533-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="35533-105">**Applies to:**</span></span>
- [<span data-ttu-id="35533-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35533-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="35533-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35533-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="35533-108">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="35533-108">**Applies to:**</span></span> 
- [<span data-ttu-id="35533-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35533-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="35533-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="35533-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="35533-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="35533-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="35533-112">Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="35533-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="35533-113">这些 API 将使您能够基于 Defender for Endpoint 功能自动执行工作流创新。</span><span class="sxs-lookup"><span data-stu-id="35533-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="35533-114">API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="35533-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="35533-115">有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="35533-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="35533-116">观看此视频，快速概览适用于终结点的 API 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="35533-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="35533-117">通常，你将需要执行以下步骤来使用 API：</span><span class="sxs-lookup"><span data-stu-id="35533-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="35533-118">创建 [AAD 应用程序](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="35533-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="35533-119">使用此应用程序获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="35533-119">Get an access token using this application</span></span>
- <span data-ttu-id="35533-120">使用令牌访问 Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="35533-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="35533-121">可以使用应用程序上下文或用户 **上下文访问** Defender for Endpoint **API。**</span><span class="sxs-lookup"><span data-stu-id="35533-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="35533-122">**应用程序上下文： (推荐)**</span><span class="sxs-lookup"><span data-stu-id="35533-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="35533-123">由在没有登录用户存在的情况下运行的应用使用。</span><span class="sxs-lookup"><span data-stu-id="35533-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="35533-124">例如，作为后台服务或守护程序运行的应用。</span><span class="sxs-lookup"><span data-stu-id="35533-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="35533-125">使用应用程序上下文访问 Defender for Endpoint API 需要执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="35533-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="35533-126">创建 AAD Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="35533-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="35533-127">为应用程序分配所需的权限，例如，"读取警报"和"隔离计算机"。</span><span class="sxs-lookup"><span data-stu-id="35533-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="35533-128">为此应用程序创建密钥。</span><span class="sxs-lookup"><span data-stu-id="35533-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="35533-129">使用应用程序及其密钥获取令牌。</span><span class="sxs-lookup"><span data-stu-id="35533-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="35533-130">使用令牌访问 Microsoft Defender 终结点 API</span><span class="sxs-lookup"><span data-stu-id="35533-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="35533-131">有关详细信息，请参阅获取 [应用程序上下文的访问权限](exposed-apis-create-app-webapp.md)。</span><span class="sxs-lookup"><span data-stu-id="35533-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="35533-132">**用户上下文：**</span><span class="sxs-lookup"><span data-stu-id="35533-132">**User Context:**</span></span> <br>
    <span data-ttu-id="35533-133">用于代表用户执行 API 中的操作。</span><span class="sxs-lookup"><span data-stu-id="35533-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="35533-134">使用应用程序上下文访问 Defender for Endpoint API 要执行的步骤：</span><span class="sxs-lookup"><span data-stu-id="35533-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="35533-135">创建 AAD Native-Application。</span><span class="sxs-lookup"><span data-stu-id="35533-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="35533-136">为应用程序分配所需的权限，例如"读取警报"和"隔离计算机"等。</span><span class="sxs-lookup"><span data-stu-id="35533-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="35533-137">使用具有用户凭据的应用程序获取令牌。</span><span class="sxs-lookup"><span data-stu-id="35533-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="35533-138">使用令牌访问 Microsoft Defender 终结点 API</span><span class="sxs-lookup"><span data-stu-id="35533-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="35533-139">有关详细信息，请参阅使用 [用户上下文获取访问权限](exposed-apis-create-app-nativeapp.md)。</span><span class="sxs-lookup"><span data-stu-id="35533-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="35533-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="35533-140">Related topics</span></span>
- [<span data-ttu-id="35533-141">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="35533-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="35533-142">使用应用程序上下文访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35533-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="35533-143">使用用户上下文访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35533-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
