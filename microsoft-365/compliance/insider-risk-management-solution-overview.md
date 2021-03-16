---
title: Microsoft 365 中的内部风险管理
description: 了解如何在 Microsoft 365 中配置内部风险管理。
keywords: Microsoft 365， 内部风险， 合规性
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
ms.openlocfilehash: 0cca5c517bf72601b469411bf83bedbbd8e50cdc
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819744"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="f2c27-104">Microsoft 365 中的内部风险管理</span><span class="sxs-lookup"><span data-stu-id="f2c27-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="f2c27-105">越来越多的员工能够跨各种平台和服务创建、管理和共享数据。</span><span class="sxs-lookup"><span data-stu-id="f2c27-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="f2c27-106">在大多数情况下，组织具有有限的资源和工具来识别和缓解组织范围内的风险，同时还满足合规性要求和员工隐私标准。</span><span class="sxs-lookup"><span data-stu-id="f2c27-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="f2c27-107">这些风险可能包括因离职员工而窃取数据，以及因意外泄露或恶意意图而泄露组织外部信息。</span><span class="sxs-lookup"><span data-stu-id="f2c27-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="f2c27-108">Microsoft 365 中的内部风险管理使用整个服务和第三方指标来帮助你快速识别、会审和操作有风险的用户活动。</span><span class="sxs-lookup"><span data-stu-id="f2c27-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="f2c27-109">通过使用 Microsoft 365 和 Microsoft Graph 中的日志，内部风险管理允许你定义特定策略，以确定风险指标并采取措施缓解这些风险。</span><span class="sxs-lookup"><span data-stu-id="f2c27-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="f2c27-110">配置 Microsoft 365 的内部风险管理</span><span class="sxs-lookup"><span data-stu-id="f2c27-110">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="f2c27-111">使用以下步骤为组织配置内部风险管理：</span><span class="sxs-lookup"><span data-stu-id="f2c27-111">Use the following steps to configure insider risk management for your organization:</span></span>

![内部风险解决方案内部风险管理步骤](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="f2c27-113">了解 Microsoft 365 [中的内部](insider-risk-management.md) 风险管理</span><span class="sxs-lookup"><span data-stu-id="f2c27-113">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="f2c27-114">规划 [内部风险管理并验证许可](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="f2c27-114">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="f2c27-115">配置 [内部风险管理设置](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f2c27-115">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="f2c27-116">配置[连接器](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)[的权限&先决条件](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span><span class="sxs-lookup"><span data-stu-id="f2c27-116">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-4-configure-prerequisites-for-policies)</span></span>
5. <span data-ttu-id="f2c27-117">创建和配置 [内部风险管理策略](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="f2c27-117">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-6-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="f2c27-118">有关内部风险管理详细信息</span><span class="sxs-lookup"><span data-stu-id="f2c27-118">More information about insider risk management</span></span>

- [<span data-ttu-id="f2c27-119">管理内部风险策略</span><span class="sxs-lookup"><span data-stu-id="f2c27-119">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="f2c27-120">调查内部风险警报</span><span class="sxs-lookup"><span data-stu-id="f2c27-120">Investigate insider risk alerts</span></span>](insider-risk-management-alerts.md)
- [<span data-ttu-id="f2c27-121">处理内部风险案例</span><span class="sxs-lookup"><span data-stu-id="f2c27-121">Act on insider risk cases</span></span>](insider-risk-management-cases.md)