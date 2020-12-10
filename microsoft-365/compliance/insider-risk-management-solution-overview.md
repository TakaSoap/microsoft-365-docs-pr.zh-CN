---
title: Microsoft 365 中的内幕风险管理
description: 了解如何在 Microsoft 365 中配置内幕风险管理。
keywords: Microsoft 365，内幕风险，合规性
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
ms.openlocfilehash: 3919523c703cb64ac443b3f0f73484efe9cea670
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613770"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="1e50f-104">Microsoft 365 中的内幕风险管理</span><span class="sxs-lookup"><span data-stu-id="1e50f-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="1e50f-105">员工们越来越多地能够在各种平台和服务上创建、管理和共享数据。</span><span class="sxs-lookup"><span data-stu-id="1e50f-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="1e50f-106">在大多数情况下，组织具有有限的资源和工具来确定和缓解组织范围的风险，同时满足合规性要求和员工隐私标准。</span><span class="sxs-lookup"><span data-stu-id="1e50f-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="1e50f-107">这些风险可能包括通过在意外 oversharing 或恶意意向的情况中，使员工和数据泄露外部信息泄露的数据被盗。</span><span class="sxs-lookup"><span data-stu-id="1e50f-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="1e50f-108">Microsoft 365 中的内幕风险管理使用全面的服务和第三方指示器来帮助您快速识别、会审和操作有风险的用户活动。</span><span class="sxs-lookup"><span data-stu-id="1e50f-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="1e50f-109">通过使用 Microsoft 365 和 Microsoft Graph 中的日志，内幕风险管理允许您定义特定策略以确定风险指示器，并采取措施来缓解这些风险。</span><span class="sxs-lookup"><span data-stu-id="1e50f-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="1e50f-110">为 Microsoft 365 配置内幕风险管理</span><span class="sxs-lookup"><span data-stu-id="1e50f-110">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="1e50f-111">使用以下步骤为您的组织配置内幕风险管理：</span><span class="sxs-lookup"><span data-stu-id="1e50f-111">Use the following steps to configure insider risk management for your organization:</span></span>

![内幕风险解决方案有问必答的风险管理步骤](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="1e50f-113">了解 Microsoft 365 中的[内幕风险管理](insider-risk-management.md)</span><span class="sxs-lookup"><span data-stu-id="1e50f-113">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="1e50f-114">规划 [内幕风险管理并验证许可](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="1e50f-114">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="1e50f-115">配置 [内幕风险管理设置](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1e50f-115">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="1e50f-116">配置 [权限](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) 和 [策略先决条件 & 连接器](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)</span><span class="sxs-lookup"><span data-stu-id="1e50f-116">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)</span></span>
5. <span data-ttu-id="1e50f-117">创建和配置 [内幕风险管理策略](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="1e50f-117">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="1e50f-118">有关内幕风险管理的详细信息</span><span class="sxs-lookup"><span data-stu-id="1e50f-118">More information about insider risk management</span></span>

- [<span data-ttu-id="1e50f-119">管理内幕风险策略</span><span class="sxs-lookup"><span data-stu-id="1e50f-119">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="1e50f-120">调查内部风险警报</span><span class="sxs-lookup"><span data-stu-id="1e50f-120">Investigate insider risk alerts</span></span>](insider-risk-management-alerts.md)
- [<span data-ttu-id="1e50f-121">对内幕风险案例执行操作</span><span class="sxs-lookup"><span data-stu-id="1e50f-121">Act on insider risk cases</span></span>](insider-risk-management-cases.md)