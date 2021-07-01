---
title: 管理和 API 概述
ms.reviewer: ''
description: 了解 Microsoft Defender for Endpoint 中的管理工具和 API 类别
keywords: 载入， api， siem， rbac， 访问， 门户， 集成， 调查， 响应， 实体， 实体， 用户上下文， 应用程序上下文， 流
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 471db75102eabd4d7fce14ec42d0a47562007aae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229979"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="556bd-104">管理和 API 概述</span><span class="sxs-lookup"><span data-stu-id="556bd-104">Overview of management and APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="556bd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="556bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="556bd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="556bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="556bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="556bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="556bd-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="556bd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="556bd-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="556bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="556bd-110">Defender for Endpoint 支持多种选项，以确保客户可以轻松采用平台。</span><span class="sxs-lookup"><span data-stu-id="556bd-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span>

<span data-ttu-id="556bd-111">确认客户环境和结构可能会有所不同，创建 Defender for Endpoint 时具有灵活性和精细控制，以满足不同的客户要求。</span><span class="sxs-lookup"><span data-stu-id="556bd-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span>

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="556bd-112">终结点载入和门户访问</span><span class="sxs-lookup"><span data-stu-id="556bd-112">Endpoint onboarding and portal access</span></span>

<span data-ttu-id="556bd-113">设备载入已完全集成到 Microsoft Endpoint Manager 和 Microsoft Intune 客户端设备和适用于服务器设备的 Azure Defender 中，从而提供配置、部署和监视的完整端到端体验。</span><span class="sxs-lookup"><span data-stu-id="556bd-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Defender for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="556bd-114">此外，Microsoft Defender for Endpoint 还支持用于设备管理的组策略和其他第三方工具。</span><span class="sxs-lookup"><span data-stu-id="556bd-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="556bd-115">Defender for Endpoint 提供对具有门户访问权限的用户的精细控制，可通过基于角色的访问控制和 RBAC (查看和) 。</span><span class="sxs-lookup"><span data-stu-id="556bd-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="556bd-116">RBAC 模型支持各种安全团队结构：</span><span class="sxs-lookup"><span data-stu-id="556bd-116">The RBAC model supports all flavors of security teams structure:</span></span>

- <span data-ttu-id="556bd-117">全局分布的组织和安全团队</span><span class="sxs-lookup"><span data-stu-id="556bd-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="556bd-118">分层模型安全运营团队</span><span class="sxs-lookup"><span data-stu-id="556bd-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="556bd-119">具有单个集中式全局安全运营团队的完全隔离的部门</span><span class="sxs-lookup"><span data-stu-id="556bd-119">Fully segregated divisions with single centralized global security operations teams</span></span>

## <a name="available-apis"></a><span data-ttu-id="556bd-120">可用的 API</span><span class="sxs-lookup"><span data-stu-id="556bd-120">Available APIs</span></span>
<span data-ttu-id="556bd-121">Microsoft Defender for Endpoint 解决方案基于集成就绪平台构建。</span><span class="sxs-lookup"><span data-stu-id="556bd-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="556bd-122">Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。</span><span class="sxs-lookup"><span data-stu-id="556bd-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="556bd-123">这些 API 将使您能够基于 Defender for Endpoint 功能自动执行工作流创新。</span><span class="sxs-lookup"><span data-stu-id="556bd-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Microsoft Defender for Endpoint 中可用 API 和集成的图像](images/mdatp-apis.png)

<span data-ttu-id="556bd-125">Defender for Endpoint API 可以分为三组：</span><span class="sxs-lookup"><span data-stu-id="556bd-125">The Defender for Endpoint APIs can be grouped into three:</span></span>

- <span data-ttu-id="556bd-126">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="556bd-126">Microsoft Defender for Endpoint APIs</span></span>
- <span data-ttu-id="556bd-127">原始数据流式处理 API</span><span class="sxs-lookup"><span data-stu-id="556bd-127">Raw data streaming API</span></span>
- <span data-ttu-id="556bd-128">SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="556bd-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="556bd-129">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="556bd-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="556bd-130">Defender for Endpoint 提供分层 API 模型，在结构化、清晰且易于使用的模型中公开数据和功能，该模型通过基于 Azure AD 的标准身份验证和授权模型公开，从而允许用户或 SaaS 应用程序上下文访问。</span><span class="sxs-lookup"><span data-stu-id="556bd-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="556bd-131">API 模型旨在以一致的形式公开实体和功能。</span><span class="sxs-lookup"><span data-stu-id="556bd-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span>

<span data-ttu-id="556bd-132">观看此视频，快速概览适用于终结点的 API 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="556bd-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span>
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="556bd-133">调查 **API** 公开了适用于终结点的 Defender 的丰富功能 - 公开计算实体或"配置文件"实体 (例如设备、用户和文件) 和离散事件 (例如，进程创建和文件创建) 通常描述与实体相关的行为，从而允许通过调查界面访问数据，从而允许基于查询的数据访问。</span><span class="sxs-lookup"><span data-stu-id="556bd-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="556bd-134">有关详细信息，请参阅受支持的[API。](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="556bd-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="556bd-135">响应 **API** 公开了在服务和设备上采取操作的功能，使客户能够接收指示器、管理设置、警报状态，以及以编程方式对设备执行响应操作，如将设备与网络隔离、隔离文件和其他操作。</span><span class="sxs-lookup"><span data-stu-id="556bd-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span>

## <a name="raw-data-streaming-api"></a><span data-ttu-id="556bd-136">原始数据流式处理 API</span><span class="sxs-lookup"><span data-stu-id="556bd-136">Raw data streaming API</span></span>

<span data-ttu-id="556bd-137">Defender for Endpoint 原始数据流 API 使客户能够在单个数据流中发生时从其实例传送实时事件和警报，从而提供低延迟、高吞吐量的传送机制。</span><span class="sxs-lookup"><span data-stu-id="556bd-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="556bd-138">Defender for Endpoint 事件信息直接推送到 Azure 存储以用于长期数据保留，或推送到 Azure 事件中心，供可视化服务或其他数据处理引擎使用。</span><span class="sxs-lookup"><span data-stu-id="556bd-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span>

<span data-ttu-id="556bd-139">有关详细信息，请参阅 [Raw data streaming API](raw-data-export.md)。</span><span class="sxs-lookup"><span data-stu-id="556bd-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>

<span data-ttu-id="556bd-140">新的流式Microsoft 365 Defender API 包括电子邮件和警报事件以及设备事件。</span><span class="sxs-lookup"><span data-stu-id="556bd-140">The new Microsoft 365 Defender Streaming API includes email and alert events in addition to device events.</span></span>
<span data-ttu-id="556bd-141">有关详细信息，请参阅Microsoft 365 Defender[流式处理 API。](../defender/streaming-api.md)</span><span class="sxs-lookup"><span data-stu-id="556bd-141">For more information, see [Microsoft 365 Defender Streaming API](../defender/streaming-api.md).</span></span>

## <a name="siem-api"></a><span data-ttu-id="556bd-142">SIEM API</span><span class="sxs-lookup"><span data-stu-id="556bd-142">SIEM API</span></span>

<span data-ttu-id="556bd-143">当你使用 SIEM) 集成启用安全信息和事件 (时，它允许你使用 SIEM 解决方案或直接连接到检测 REST API 从 Microsoft Defender 安全中心 拉取检测。</span><span class="sxs-lookup"><span data-stu-id="556bd-143">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="556bd-144">这会使用预填充的值激活 SIEM 连接器访问详细信息部分，并且应用程序在 Azure Active Directory (Azure AD) 租户下创建。</span><span class="sxs-lookup"><span data-stu-id="556bd-144">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="556bd-145">有关详细信息，请参阅 [SIEM 集成](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="556bd-145">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="556bd-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="556bd-146">Related topics</span></span>

- [<span data-ttu-id="556bd-147">访问 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="556bd-147">Access the Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="556bd-148">受支持的 API</span><span class="sxs-lookup"><span data-stu-id="556bd-148">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="556bd-149">技术合作伙伴商机</span><span class="sxs-lookup"><span data-stu-id="556bd-149">Technical partner opportunities</span></span>](partner-integration.md)