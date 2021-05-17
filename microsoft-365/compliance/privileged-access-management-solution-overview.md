---
title: Microsoft 365 中的特权访问管理
description: 了解如何跨组织配置内部风险Microsoft 365。
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
ms.openlocfilehash: a5cd9d62670b35f7093a3d38cf9e499df407de97
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423805"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="e7e0f-104">Microsoft 365 中的特权访问管理</span><span class="sxs-lookup"><span data-stu-id="e7e0f-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="e7e0f-105">让某些用户长期访问 Microsoft Exchange Online 中的敏感信息或关键网络配置设置是一种潜在路径，用于破坏帐户或内部威胁活动。</span><span class="sxs-lookup"><span data-stu-id="e7e0f-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="e7e0f-106">特权访问管理通过限制长期访问敏感数据或关键配置设置来帮助保护组织免受泄露，并有助于符合合规性最佳做法。</span><span class="sxs-lookup"><span data-stu-id="e7e0f-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="e7e0f-107">为需要提升的权限的任务实现实时访问规则，而不是管理员具有恒定访问权限。</span><span class="sxs-lookup"><span data-stu-id="e7e0f-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="e7e0f-108">通过为 Exchange Online 中的Microsoft 365启用特权访问管理，组织可以零长期特权运行，并提供一层防御长期管理访问漏洞的防护。</span><span class="sxs-lookup"><span data-stu-id="e7e0f-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="e7e0f-109">为用户配置特权访问Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7e0f-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="e7e0f-110">使用以下步骤为组织配置特权访问管理：</span><span class="sxs-lookup"><span data-stu-id="e7e0f-110">Use the following steps to configure privileged access management for your organization:</span></span>

![内部风险解决方案特权访问管理步骤](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="e7e0f-112">了解[企业中的特权访问](privileged-access-management-overview.md)Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7e0f-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="e7e0f-113">创建 [审批者组](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="e7e0f-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="e7e0f-114">启用 [特权访问管理](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="e7e0f-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="e7e0f-115">创建 [访问策略](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="e7e0f-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="e7e0f-116">提交/ [批准特权访问请求](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="e7e0f-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="e7e0f-117">有关特权访问管理详细信息</span><span class="sxs-lookup"><span data-stu-id="e7e0f-117">More information about privileged access management</span></span>

- [<span data-ttu-id="e7e0f-118">有关特权访问管理的常见问题</span><span class="sxs-lookup"><span data-stu-id="e7e0f-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)