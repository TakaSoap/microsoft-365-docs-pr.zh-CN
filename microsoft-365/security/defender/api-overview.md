---
title: Microsoft 365 Defender API 概述
description: 了解 Microsoft 365 Defender 中的可用 API
keywords: api， api， 概述， 事件， 事件， 威胁搜寻， microsoft 365 defender
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
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904184"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="91ec5-104">Microsoft 365 Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="91ec5-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="91ec5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="91ec5-105">**Applies to:**</span></span>

- <span data-ttu-id="91ec5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91ec5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91ec5-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="91ec5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="91ec5-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="91ec5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="91ec5-109">Microsoft 365 Defender 基于集成就绪平台构建。</span><span class="sxs-lookup"><span data-stu-id="91ec5-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="91ec5-110">使用 Microsoft 365 Defender API 根据共享事件和高级搜寻表自动执行工作流。</span><span class="sxs-lookup"><span data-stu-id="91ec5-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="91ec5-111">**[组合事件队列](api-incident.md)** - 通过按事件 API 将整个攻击范围和所有影响的资产分组在一起，重点关注关键内容。</span><span class="sxs-lookup"><span data-stu-id="91ec5-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="91ec5-112">**[跨产品威胁搜寻](api-advanced-hunting.md)** - 通过创建自己的自定义查询来筛选跨多个保护产品收集的原始数据，利用安全团队的组织知识搜寻泄露的迹象。</span><span class="sxs-lookup"><span data-stu-id="91ec5-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="91ec5-113">除了这些特定于 Microsoft 365 Defender 的 API 外，我们每个[](api-articles.md)其他安全产品都公开了其他 API，以帮助你充分利用它们的独特功能。</span><span class="sxs-lookup"><span data-stu-id="91ec5-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="91ec5-114">转换到统一门户应该不会影响基于 Microsoft Defender for Endpoint API 的 PowerBi 仪表板。</span><span class="sxs-lookup"><span data-stu-id="91ec5-114">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="91ec5-115">无论交互式门户转换如何，都可以继续使用现有 API。</span><span class="sxs-lookup"><span data-stu-id="91ec5-115">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="91ec5-116">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="91ec5-116">Learn more</span></span>

| <span data-ttu-id="91ec5-117">**了解如何访问 API**</span><span class="sxs-lookup"><span data-stu-id="91ec5-117">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="91ec5-118">了解 API 配额和许可</span><span class="sxs-lookup"><span data-stu-id="91ec5-118">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="91ec5-119">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="91ec5-119">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="91ec5-120">**构建应用程序**</span><span class="sxs-lookup"><span data-stu-id="91ec5-120">**Build apps**</span></span> |
| [<span data-ttu-id="91ec5-121">创建"Hello world"应用</span><span class="sxs-lookup"><span data-stu-id="91ec5-121">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="91ec5-122">创建应用以代表用户访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="91ec5-122">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="91ec5-123">创建应用以在没有用户的情况下访问 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91ec5-123">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="91ec5-124">创建具有对 Microsoft 365 Defender API 的多租户合作伙伴访问权限的应用</span><span class="sxs-lookup"><span data-stu-id="91ec5-124">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="91ec5-125">**对应用进行故障排除和维护**</span><span class="sxs-lookup"><span data-stu-id="91ec5-125">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="91ec5-126">了解 API 错误代码</span><span class="sxs-lookup"><span data-stu-id="91ec5-126">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="91ec5-127">使用 Azure Key Vault 管理应用中的密钥</span><span class="sxs-lookup"><span data-stu-id="91ec5-127">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="91ec5-128">为用户登录实现 OAuth 2.0 授权</span><span class="sxs-lookup"><span data-stu-id="91ec5-128">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |