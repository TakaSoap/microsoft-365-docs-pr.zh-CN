---
title: Microsoft Defender for Endpoint 中的 API 资源管理器
ms.reviewer: ''
description: 使用 API 资源管理器构造和执行 API 查询、测试和发送任何可用 API 的请求
keywords: api， 资源管理器， 发送， 请求， 获取， 发布，
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 6a5684d71d34b3efdfe915ae674b4fcb90342154
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769793"
---
# <a name="api-explorer"></a><span data-ttu-id="a3f79-104">API 资源管理器</span><span class="sxs-lookup"><span data-stu-id="a3f79-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a3f79-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a3f79-105">**Applies to:**</span></span>
- [<span data-ttu-id="a3f79-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a3f79-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="a3f79-107">Microsoft Defender for Endpoint API Explorer 是一款工具，可帮助你以交互方式浏览各种 Defender for Endpoint API。</span><span class="sxs-lookup"><span data-stu-id="a3f79-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="a3f79-108">通过 API 资源管理器，可以轻松构造和执行 API 查询、测试和发送任何可用的 Defender for Endpoint API 终结点的请求。</span><span class="sxs-lookup"><span data-stu-id="a3f79-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="a3f79-109">使用 API 资源管理器执行操作或查找可能尚未通过用户界面提供的数据。</span><span class="sxs-lookup"><span data-stu-id="a3f79-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="a3f79-110">该工具在应用开发过程中很有用。</span><span class="sxs-lookup"><span data-stu-id="a3f79-110">The tool is useful during app development.</span></span> <span data-ttu-id="a3f79-111">它允许你执行遵守用户访问设置的 API 查询，从而减少生成访问令牌的需要。</span><span class="sxs-lookup"><span data-stu-id="a3f79-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="a3f79-112">您还可以使用该工具浏览示例查询库、复制结果代码示例并生成调试信息。</span><span class="sxs-lookup"><span data-stu-id="a3f79-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="a3f79-113">借助 API 资源管理器，你可以：</span><span class="sxs-lookup"><span data-stu-id="a3f79-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="a3f79-114">运行任意方法的请求并实时查看响应</span><span class="sxs-lookup"><span data-stu-id="a3f79-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="a3f79-115">快速浏览 API 示例并了解它们支持的参数</span><span class="sxs-lookup"><span data-stu-id="a3f79-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="a3f79-116">轻松进行 API 调用;无需在管理门户登录之外进行身份验证</span><span class="sxs-lookup"><span data-stu-id="a3f79-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="a3f79-117">Access API 资源管理器</span><span class="sxs-lookup"><span data-stu-id="a3f79-117">Access API Explorer</span></span>

<span data-ttu-id="a3f79-118">从左侧导航菜单中，选择"合作伙伴 **& API API**  >  **资源管理器"。**</span><span class="sxs-lookup"><span data-stu-id="a3f79-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="a3f79-119">受支持的 API</span><span class="sxs-lookup"><span data-stu-id="a3f79-119">Supported APIs</span></span>

<span data-ttu-id="a3f79-120">API 资源管理器支持 Defender for Endpoint 提供的所有 API。</span><span class="sxs-lookup"><span data-stu-id="a3f79-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="a3f79-121">API 文档中提供了受支持的 [API 列表](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f79-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="a3f79-122">API 资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="a3f79-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="a3f79-123">在左窗格中，有一个可以使用的示例请求列表。</span><span class="sxs-lookup"><span data-stu-id="a3f79-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="a3f79-124">按照链接操作，然后单击"**运行查询"。**</span><span class="sxs-lookup"><span data-stu-id="a3f79-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="a3f79-125">一些示例可能需要在 URL 中指定参数，例如 {machine- ID}。</span><span class="sxs-lookup"><span data-stu-id="a3f79-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="a3f79-126">常见问题</span><span class="sxs-lookup"><span data-stu-id="a3f79-126">FAQ</span></span>

<span data-ttu-id="a3f79-127">**我是否需要具有 API 令牌以使用 API 资源管理器？**</span><span class="sxs-lookup"><span data-stu-id="a3f79-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="a3f79-128">不需要访问 API 的凭据。</span><span class="sxs-lookup"><span data-stu-id="a3f79-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="a3f79-129">API 资源管理器在提出请求时使用 Defender for Endpoint 管理门户令牌。</span><span class="sxs-lookup"><span data-stu-id="a3f79-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="a3f79-130">登录的用户身份验证凭据用于验证 API 资源管理器是否有权代表你访问数据。</span><span class="sxs-lookup"><span data-stu-id="a3f79-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="a3f79-131">特定 API 请求根据 RBAC 权限受到限制。</span><span class="sxs-lookup"><span data-stu-id="a3f79-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="a3f79-132">例如，对"提交指示器"的请求仅限于安全管理员角色。</span><span class="sxs-lookup"><span data-stu-id="a3f79-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
