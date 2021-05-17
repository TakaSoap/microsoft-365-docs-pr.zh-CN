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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055573"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="467bc-104">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="467bc-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="467bc-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="467bc-105">**Applies to:**</span></span>

- <span data-ttu-id="467bc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="467bc-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="467bc-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="467bc-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="467bc-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="467bc-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="467bc-109">Microsoft 365Defender 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="467bc-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="467bc-110">这些 API 可帮助你自动执行工作流，并充分利用Microsoft 365 Defender 的功能。</span><span class="sxs-lookup"><span data-stu-id="467bc-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="467bc-111">通常，你将需要执行以下步骤来使用 API：</span><span class="sxs-lookup"><span data-stu-id="467bc-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="467bc-112">创建Azure Active Directory应用程序</span><span class="sxs-lookup"><span data-stu-id="467bc-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="467bc-113">使用此应用程序获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="467bc-113">Get an access token using this application</span></span>
- <span data-ttu-id="467bc-114">使用令牌访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="467bc-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="467bc-115">API 访问需要 OAuth2.0 身份验证。</span><span class="sxs-lookup"><span data-stu-id="467bc-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="467bc-116">有关详细信息，请参阅[OAuth 2.0 授权代码Flow。](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="467bc-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="467bc-117">完成这些步骤后，就可以使用特定上下文Microsoft 365 Defender API 了。</span><span class="sxs-lookup"><span data-stu-id="467bc-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="467bc-118">应用上下文 (推荐) </span><span class="sxs-lookup"><span data-stu-id="467bc-118">Application context (Recommended)</span></span>

<span data-ttu-id="467bc-119">对于在没有登录用户的情况下运行的应用（如后台服务或守护程序）使用此上下文。</span><span class="sxs-lookup"><span data-stu-id="467bc-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="467bc-120">创建Azure Active Directory Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="467bc-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="467bc-121">向应用程序分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="467bc-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="467bc-122">为应用程序创建密钥。</span><span class="sxs-lookup"><span data-stu-id="467bc-122">Create a key for the application.</span></span>
4. <span data-ttu-id="467bc-123">使用应用程序及其密钥获取安全令牌。</span><span class="sxs-lookup"><span data-stu-id="467bc-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="467bc-124">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="467bc-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="467bc-125">有关详细信息，请参阅创建 **[应用以在没有用户的情况下Microsoft 365 Defender。](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="467bc-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="467bc-126">用户上下文</span><span class="sxs-lookup"><span data-stu-id="467bc-126">User context</span></span>

<span data-ttu-id="467bc-127">使用此上下文代表单个用户执行操作。</span><span class="sxs-lookup"><span data-stu-id="467bc-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="467bc-128">创建Azure Active Directory应用程序。</span><span class="sxs-lookup"><span data-stu-id="467bc-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="467bc-129">向应用程序分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="467bc-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="467bc-130">使用应用程序的用户凭据获取安全令牌。</span><span class="sxs-lookup"><span data-stu-id="467bc-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="467bc-131">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="467bc-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="467bc-132">有关详细信息，请参阅创建 **[应用以代表Microsoft 365访问](api-create-app-user-context.md)** Defender API。</span><span class="sxs-lookup"><span data-stu-id="467bc-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="467bc-133">合作伙伴上下文</span><span class="sxs-lookup"><span data-stu-id="467bc-133">Partner context</span></span>

<span data-ttu-id="467bc-134">当你需要向多个租户中的许多用户提供应用时， [请使用此上下文](/azure/active-directory/develop/single-and-multi-tenant-apps)。</span><span class="sxs-lookup"><span data-stu-id="467bc-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="467bc-135">创建Azure Active Directory租户应用程序。</span><span class="sxs-lookup"><span data-stu-id="467bc-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="467bc-136">向应用程序分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="467bc-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="467bc-137">从 [每个租户](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 获取应用的管理员同意。</span><span class="sxs-lookup"><span data-stu-id="467bc-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="467bc-138">使用基于客户的租户 ID 的用户凭据获取安全令牌。</span><span class="sxs-lookup"><span data-stu-id="467bc-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="467bc-139">使用令牌访问 Microsoft 365 Defender API。</span><span class="sxs-lookup"><span data-stu-id="467bc-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="467bc-140">有关详细信息，请参阅 **[创建具有](api-partner-access.md)** 对 Defender API 的合作伙伴访问权限Microsoft 365应用。</span><span class="sxs-lookup"><span data-stu-id="467bc-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="467bc-141">相关文章</span><span class="sxs-lookup"><span data-stu-id="467bc-141">Related articles</span></span>

- [<span data-ttu-id="467bc-142">Microsoft 365Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="467bc-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="467bc-143">用户登录和 API 访问的 OAuth 2.0 授权</span><span class="sxs-lookup"><span data-stu-id="467bc-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="467bc-144">使用 Azure Key Vault 管理服务器应用中的密钥</span><span class="sxs-lookup"><span data-stu-id="467bc-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="467bc-145">创建访问这些 API 的"Hello world"Microsoft 365应用程序</span><span class="sxs-lookup"><span data-stu-id="467bc-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)