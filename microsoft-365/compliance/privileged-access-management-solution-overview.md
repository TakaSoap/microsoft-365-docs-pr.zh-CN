---
title: Microsoft 365 中的特权访问管理
description: 了解如何在 Microsoft 365 中配置内幕风险功能。
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
ms.openlocfilehash: 7fecfd7088f65effd6addddc51c1236c7b2af191
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613758"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="a3b07-104">Microsoft 365 中的特权访问管理</span><span class="sxs-lookup"><span data-stu-id="a3b07-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="a3b07-105">在 Microsoft Exchange Online 中，某些用户对敏感信息或关键网络配置设置的持续访问是受到危害的帐户或内部威胁活动的潜在路径。</span><span class="sxs-lookup"><span data-stu-id="a3b07-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="a3b07-106">特权访问管理通过限制对敏感数据的访问或对关键配置设置的访问，帮助保护组织不受破坏并帮助满足合规性最佳做法。</span><span class="sxs-lookup"><span data-stu-id="a3b07-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="a3b07-107">为需要提升权限的任务实现实时访问规则，而不是具有持续访问权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="a3b07-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="a3b07-108">在 Microsoft 365 中为 Exchange Online 启用 "特权访问管理" 使组织能够以零为自主权限运行，并提供抵御受影响的管理访问漏洞的防御层。</span><span class="sxs-lookup"><span data-stu-id="a3b07-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="a3b07-109">配置 Microsoft 365 的特权访问管理</span><span class="sxs-lookup"><span data-stu-id="a3b07-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="a3b07-110">使用以下步骤为您的组织配置特权访问管理：</span><span class="sxs-lookup"><span data-stu-id="a3b07-110">Use the following steps to configure privileged access management for your organization:</span></span>

![内幕风险解决方案特权访问管理步骤](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="a3b07-112">了解 Microsoft 365 中的[特权访问管理](privileged-access-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a3b07-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="a3b07-113">创建 [审批者的组](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="a3b07-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="a3b07-114">启用 [特权访问管理](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="a3b07-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="a3b07-115">创建 [访问策略](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="a3b07-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="a3b07-116">提交/批准权限 [访问请求](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="a3b07-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="a3b07-117">有关特权访问管理的详细信息</span><span class="sxs-lookup"><span data-stu-id="a3b07-117">More information about privileged access management</span></span>

- [<span data-ttu-id="a3b07-118">有关特权访问管理的常见问题</span><span class="sxs-lookup"><span data-stu-id="a3b07-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)