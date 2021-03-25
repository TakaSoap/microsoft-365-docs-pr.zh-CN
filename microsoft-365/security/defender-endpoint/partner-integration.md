---
title: Microsoft Defender ATP 合作伙伴机会和方案
ms.reviewer: ''
description: 了解如何在开放框架和丰富的 API 集上扩展现有安全产品/服务，以构建与 Microsoft Defender ATP 的扩展和集成
keywords: API， 合作伙伴， 扩展， 开放框架， api， 扩展， 集成， 检测， 管理， 响应， 漏洞， 智能
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
ms.openlocfilehash: 1db82afa06fd0b6b3d7228aaf3020c5496ed69e7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186889"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="98c0f-104">Microsoft Defender for Endpoint 合作伙伴机会和方案</span><span class="sxs-lookup"><span data-stu-id="98c0f-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98c0f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="98c0f-105">**Applies to:**</span></span>
- [<span data-ttu-id="98c0f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="98c0f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98c0f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98c0f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="98c0f-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="98c0f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98c0f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="98c0f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="98c0f-110">合作伙伴可以在开放框架和一组丰富完整的 API 上轻松扩展其现有安全产品/服务，以构建与 Defender for Endpoint 的扩展和集成。</span><span class="sxs-lookup"><span data-stu-id="98c0f-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="98c0f-111">API 跨功能区域，包括检测、管理、响应、漏洞和智能范围内用例。</span><span class="sxs-lookup"><span data-stu-id="98c0f-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="98c0f-112">根据用例和需求，合作伙伴可以从 Defender for Endpoint 流式传输或查询数据。</span><span class="sxs-lookup"><span data-stu-id="98c0f-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="98c0f-113">方案 1：外部警报关联和自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="98c0f-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="98c0f-114">Defender for Endpoint 提供独特的自动调查和修正功能，可大规模推动事件响应。</span><span class="sxs-lookup"><span data-stu-id="98c0f-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="98c0f-115">将自动调查和响应功能与其他解决方案（如网络安全产品或其他终结点安全产品）集成将有助于解决警报问题。</span><span class="sxs-lookup"><span data-stu-id="98c0f-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="98c0f-116">集成还可以最大程度地降低网络和设备信号关联的复杂性，从而有效地简化设备上调查和威胁修正操作。</span><span class="sxs-lookup"><span data-stu-id="98c0f-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="98c0f-117">Defender for Endpoint 以以下形式添加对此方案的支持：</span><span class="sxs-lookup"><span data-stu-id="98c0f-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="98c0f-118">外部警报可以推送到 Defender for Endpoint，并排显示来自 Defender for Endpoint 的其他基于设备的警报。</span><span class="sxs-lookup"><span data-stu-id="98c0f-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="98c0f-119">此视图提供警报的完整上下文 ， 以及攻击的实际过程和完整情景。</span><span class="sxs-lookup"><span data-stu-id="98c0f-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="98c0f-120">生成警报后，信号将在整个企业中受 Defender for Endpoint 保护的终结点之间共享。</span><span class="sxs-lookup"><span data-stu-id="98c0f-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="98c0f-121">Defender for Endpoint 立即自动响应或接线员协助响应，以响应警报。</span><span class="sxs-lookup"><span data-stu-id="98c0f-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="98c0f-122">方案 2：安全业务流程和自动化响应 (SOAR) 集成</span><span class="sxs-lookup"><span data-stu-id="98c0f-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="98c0f-123">业务流程解决方案可帮助构建操作手册，并集成 Defender for Endpoint API 公开用于协调响应的丰富数据模型和操作，例如查询设备数据、触发设备隔离、阻止/允许、解决警报和其他操作。</span><span class="sxs-lookup"><span data-stu-id="98c0f-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="98c0f-124">方案 3：指示器匹配</span><span class="sxs-lookup"><span data-stu-id="98c0f-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="98c0f-125">ICS (泄露) 是每个终结点保护解决方案中的重要功能。</span><span class="sxs-lookup"><span data-stu-id="98c0f-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="98c0f-126">此功能在 Defender for Endpoint 中可用，并能够设置用于预防、检测和排除实体的指示器列表。</span><span class="sxs-lookup"><span data-stu-id="98c0f-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="98c0f-127">可以定义要采取的操作以及何时应用该操作的持续时间。</span><span class="sxs-lookup"><span data-stu-id="98c0f-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="98c0f-128">上述方案用作平台扩展性的示例。</span><span class="sxs-lookup"><span data-stu-id="98c0f-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="98c0f-129">您不限于这些示例，我们当然鼓励您利用开放框架发现和探索其他方案。</span><span class="sxs-lookup"><span data-stu-id="98c0f-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="98c0f-130">按照成为 [Microsoft Defender for Endpoint 合作伙伴中的](get-started-partner-integration.md) 步骤在 Defender for Endpoint 中集成你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="98c0f-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="98c0f-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="98c0f-131">Related topic</span></span>
- [<span data-ttu-id="98c0f-132">管理和 API 概述</span><span class="sxs-lookup"><span data-stu-id="98c0f-132">Overview of management and APIs</span></span>](management-apis.md)
