---
title: 访问 Microsoft 365 Defender API
description: 了解如何访问 Microsoft 365 Defender API
keywords: access， api， 应用程序上下文， 用户上下文， aad 应用程序， 访问令牌
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 17fa47fd9998f4097ff323e670b9e442d7126a94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903972"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="6f97b-104">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="6f97b-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6f97b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6f97b-105">**Applies to:**</span></span>

- <span data-ttu-id="6f97b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f97b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f97b-107">某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="6f97b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6f97b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6f97b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6f97b-109">Microsoft 365 Defender 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="6f97b-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="6f97b-110">这些 API 可帮助你自动化工作流并充分利用 Microsoft 365 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="6f97b-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="6f97b-111">通常，你将需要执行以下步骤来使用 API：</span><span class="sxs-lookup"><span data-stu-id="6f97b-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="6f97b-112">创建 Azure Active Directory 应用程序</span><span class="sxs-lookup"><span data-stu-id="6f97b-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="6f97b-113">使用此应用程序获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="6f97b-113">Get an access token using this application</span></span>
- <span data-ttu-id="6f97b-114">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="6f97b-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="6f97b-115">API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f97b-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="6f97b-116">有关详细信息，请参阅 [OAuth 2.0 授权代码流](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="6f97b-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="6f97b-117">完成这些步骤后，即可使用特定上下文访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="6f97b-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="6f97b-118">应用上下文 (推荐) </span><span class="sxs-lookup"><span data-stu-id="6f97b-118">Application context (Recommended)</span></span>

<span data-ttu-id="6f97b-119">对于在没有登录用户的情况下运行的应用（如后台服务或守护程序）使用此上下文。</span><span class="sxs-lookup"><span data-stu-id="6f97b-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="6f97b-120">创建 Azure Active Directory Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f97b-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="6f97b-121">向应用程序分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="6f97b-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="6f97b-122">为应用程序创建密钥。</span><span class="sxs-lookup"><span data-stu-id="6f97b-122">Create a key for the application.</span></span>
4. <span data-ttu-id="6f97b-123">使用应用程序及其密钥获取安全令牌。</span><span class="sxs-lookup"><span data-stu-id="6f97b-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="6f97b-124">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="6f97b-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="6f97b-125">有关详细信息，请参阅创建应用以在没有用户的情况下访问 **[Microsoft 365 Defender。](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="6f97b-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="6f97b-126">用户上下文</span><span class="sxs-lookup"><span data-stu-id="6f97b-126">User context</span></span>

<span data-ttu-id="6f97b-127">使用此上下文代表单个用户执行操作。</span><span class="sxs-lookup"><span data-stu-id="6f97b-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="6f97b-128">创建 Azure Active Directory 本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f97b-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="6f97b-129">向应用程序分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="6f97b-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="6f97b-130">使用应用程序的用户凭据获取安全令牌。</span><span class="sxs-lookup"><span data-stu-id="6f97b-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="6f97b-131">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="6f97b-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="6f97b-132">有关详细信息，请参阅创建应用以代表用户访问 **[Microsoft 365 Defender API。](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="6f97b-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="6f97b-133">合作伙伴上下文</span><span class="sxs-lookup"><span data-stu-id="6f97b-133">Partner context</span></span>

<span data-ttu-id="6f97b-134">当你需要向多个租户中的许多用户提供应用时， [请使用此上下文](/azure/active-directory/develop/single-and-multi-tenant-apps)。</span><span class="sxs-lookup"><span data-stu-id="6f97b-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="6f97b-135">创建 Azure Active Directory 多租户应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f97b-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="6f97b-136">向应用程序分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="6f97b-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="6f97b-137">从 [每个租户](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 获取应用的管理员同意。</span><span class="sxs-lookup"><span data-stu-id="6f97b-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="6f97b-138">使用基于客户的租户 ID 的用户凭据获取安全令牌。</span><span class="sxs-lookup"><span data-stu-id="6f97b-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="6f97b-139">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="6f97b-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="6f97b-140">有关详细信息，请参阅创建具有 Microsoft **[365 Defender API](api-partner-access.md)** 合作伙伴访问权限的应用。</span><span class="sxs-lookup"><span data-stu-id="6f97b-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6f97b-141">相关文章</span><span class="sxs-lookup"><span data-stu-id="6f97b-141">Related articles</span></span>

- [<span data-ttu-id="6f97b-142">Microsoft 365 Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="6f97b-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6f97b-143">用户登录和 API 访问的 OAuth 2.0 授权</span><span class="sxs-lookup"><span data-stu-id="6f97b-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="6f97b-144">使用 Azure Key Vault 管理服务器应用中的密钥</span><span class="sxs-lookup"><span data-stu-id="6f97b-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="6f97b-145">创建访问 Microsoft 365 API 的"Hello world"应用程序</span><span class="sxs-lookup"><span data-stu-id="6f97b-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)