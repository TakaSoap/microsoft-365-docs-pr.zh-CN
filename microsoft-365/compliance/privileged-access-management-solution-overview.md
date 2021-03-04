---
title: Microsoft 365 中的特权访问管理
description: 了解如何在 Microsoft 365 中配置内部风险功能。
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
ms.openlocfilehash: a5cd9d62670b35f7093a3d38cf9e499df407de97
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423805"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="53c26-104">Microsoft 365 中的特权访问管理</span><span class="sxs-lookup"><span data-stu-id="53c26-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="53c26-105">让某些用户长期访问安全中心中的敏感信息或Microsoft Exchange Online网络配置设置是遭到入侵的帐户或内部威胁活动的潜在途径。</span><span class="sxs-lookup"><span data-stu-id="53c26-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="53c26-106">特权访问管理通过限制长期访问敏感数据或访问关键配置设置来帮助保护组织免受泄露，并帮助满足合规性最佳做法。</span><span class="sxs-lookup"><span data-stu-id="53c26-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="53c26-107">为需要提升的权限的任务实现实时访问规则，而不是管理员具有恒定的访问权限。</span><span class="sxs-lookup"><span data-stu-id="53c26-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="53c26-108">在 Microsoft 365 中为 Exchange Online 启用特权访问管理后，组织可以零长期特权运行，并提供针对长期管理访问漏洞的一层防御。</span><span class="sxs-lookup"><span data-stu-id="53c26-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="53c26-109">为 Microsoft 365 配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="53c26-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="53c26-110">使用以下步骤为组织配置特权访问管理：</span><span class="sxs-lookup"><span data-stu-id="53c26-110">Use the following steps to configure privileged access management for your organization:</span></span>

![内部风险解决方案特权访问管理步骤](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="53c26-112">了解 Microsoft 365 [中的特权](privileged-access-management-overview.md) 访问管理</span><span class="sxs-lookup"><span data-stu-id="53c26-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="53c26-113">创建 [审批者组](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="53c26-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="53c26-114">启用 [特权访问管理](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="53c26-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="53c26-115">创建 [访问策略](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="53c26-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="53c26-116">提交/ [批准特权访问请求](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="53c26-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="53c26-117">有关特权访问管理详细信息</span><span class="sxs-lookup"><span data-stu-id="53c26-117">More information about privileged access management</span></span>

- [<span data-ttu-id="53c26-118">有关特权访问管理的常见问题</span><span class="sxs-lookup"><span data-stu-id="53c26-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)