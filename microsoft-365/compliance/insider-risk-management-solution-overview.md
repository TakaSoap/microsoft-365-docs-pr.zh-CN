---
title: 内部风险管理Microsoft 365
description: 了解如何在管理中心中配置内部Microsoft 365。
keywords: Microsoft 365、内部风险、合规性
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: bee4c2d01579733ff7b1c5583b00cdd48e437af2
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430536"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="f0fa2-104">内部风险管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0fa2-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="f0fa2-105">越来越多的员工能够跨各种平台和服务创建、管理和共享数据。</span><span class="sxs-lookup"><span data-stu-id="f0fa2-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="f0fa2-106">在大多数情况下，组织具有有限的资源和工具来识别和缓解组织范围内的风险，同时还满足合规性要求和员工隐私标准。</span><span class="sxs-lookup"><span data-stu-id="f0fa2-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="f0fa2-107">这些风险可能包括因离职员工而窃取数据，以及因意外泄露或恶意意图而泄露组织外部信息。</span><span class="sxs-lookup"><span data-stu-id="f0fa2-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="f0fa2-108">Microsoft 365中的内部风险管理使用整个服务和第三方指标来帮助你快速识别、会审和操作有风险的用户活动。</span><span class="sxs-lookup"><span data-stu-id="f0fa2-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="f0fa2-109">通过使用 microsoft Microsoft 365 和 Microsoft Graph 中的日志，内部风险管理允许你定义特定策略，以确定风险指标并采取措施来缓解这些风险。</span><span class="sxs-lookup"><span data-stu-id="f0fa2-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

<span data-ttu-id="f0fa2-110">观看下面的视频，了解内部风险管理如何有助于组织在确定组织价值、文化及用户体验优先级时预防、检测和包含风险：</span><span class="sxs-lookup"><span data-stu-id="f0fa2-110">Watch the videos below to learn how insider risk management can help your organization prevent, detect, and contain risks while prioritizing your organization values, culture, and user experience:</span></span>
<br>
<br>

<span data-ttu-id="f0fa2-111">**内部风险管理解决方案&开发**：</span><span class="sxs-lookup"><span data-stu-id="f0fa2-111">**Insider risk management solution & development**:</span></span>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]
<br>

<span data-ttu-id="f0fa2-112">**内部风险管理工作流**：</span><span class="sxs-lookup"><span data-stu-id="f0fa2-112">**Insider risk management workflow**:</span></span>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="f0fa2-113">配置内部风险管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0fa2-113">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="f0fa2-114">使用以下步骤为组织配置内部风险管理：</span><span class="sxs-lookup"><span data-stu-id="f0fa2-114">Use the following steps to configure insider risk management for your organization:</span></span>

![内部风险解决方案内部风险管理步骤](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="f0fa2-116">了解[企业内部风险管理](insider-risk-management.md)Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0fa2-116">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="f0fa2-117">规划 [内部风险管理并验证许可](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="f0fa2-117">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="f0fa2-118">配置 [内部风险管理设置](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f0fa2-118">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="f0fa2-119">配置[连接器](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)[的权限&先决条件](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span><span class="sxs-lookup"><span data-stu-id="f0fa2-119">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span></span>
5. <span data-ttu-id="f0fa2-120">创建和配置 [内部风险管理策略](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="f0fa2-120">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="f0fa2-121">有关内部风险管理详细信息</span><span class="sxs-lookup"><span data-stu-id="f0fa2-121">More information about insider risk management</span></span>

- [<span data-ttu-id="f0fa2-122">管理内部风险策略</span><span class="sxs-lookup"><span data-stu-id="f0fa2-122">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="f0fa2-123">调查内部风险活动</span><span class="sxs-lookup"><span data-stu-id="f0fa2-123">Investigate insider risk activities</span></span>](insider-risk-management-activities.md)
- [<span data-ttu-id="f0fa2-124">处理内部风险案例</span><span class="sxs-lookup"><span data-stu-id="f0fa2-124">Act on insider risk cases</span></span>](insider-risk-management-cases.md)