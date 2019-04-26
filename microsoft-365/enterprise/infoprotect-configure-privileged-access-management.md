---
title: '步骤 6: 配置 Office 365 的特权访问管理'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 了解并配置 Office 365 的特权访问管理。
ms.openlocfilehash: 60b52825ead068cd0f068f78c1bbce263e8d7720
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304152"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="142a4-103">步骤 6: 配置 Office 365 的特权访问管理</span><span class="sxs-lookup"><span data-stu-id="142a4-103">Step 6: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="142a4-104">*此步骤是可选的，仅适用于 Microsoft 365 企业版的 E5 版和高级合规版*</span><span class="sxs-lookup"><span data-stu-id="142a4-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="142a4-p101">Office 365 租户中的特权访问管理可通过配置相应策略来实现，这些策略会为基于任务的活动指定实时访问权限。这种管理可为组织提供保护，防止他人使用具有长期敏感数据访问权限或关键配置设置访问权限的现有特权访问帐户。例如，你可以配置一个特权访问管理策略，要求必须经过显示审批才能访问和更改 Office 365 租户中的组织邮箱设置。</span><span class="sxs-lookup"><span data-stu-id="142a4-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="142a4-p102">在此步骤中，你将在 Office 365 租户中启用特权访问管理并配置特权访问策略，这些策略可为基于任务对组织的 Office 365 数据和配置设置进行的访问提供额外的安全性。若要开始在 Office 365 组织中使用特权访问，需要执行三个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="142a4-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="142a4-110">创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="142a4-110">Creating an approver's group</span></span>
- <span data-ttu-id="142a4-111">启用特权访问</span><span class="sxs-lookup"><span data-stu-id="142a4-111">Enabling privileged access</span></span>
- <span data-ttu-id="142a4-112">创建审批策略</span><span class="sxs-lookup"><span data-stu-id="142a4-112">Creating approval policies</span></span>

<span data-ttu-id="142a4-p103">配置完成后，特权访问管理可帮助组织实现零长期特权并针对这类长期管理访问权限造成的漏洞提供一个防御层。特权访问要求必须经过审批才能执行定义了相关审批策略的任务。用户如果需要执行某个审批策略中包含的任务，则必须提出请求并成功通过访问权限审批，以便获得执行该策略中定义的任务所需的权限。</span><span class="sxs-lookup"><span data-stu-id="142a4-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="142a4-116">若要启用 Office 365 特权访问管理，请参阅[配置 Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题。</span><span class="sxs-lookup"><span data-stu-id="142a4-116">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="142a4-117">有关详细信息，请参阅 [Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)主题。</span><span class="sxs-lookup"><span data-stu-id="142a4-117">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>

## <a name="results"></a><span data-ttu-id="142a4-118">结果</span><span class="sxs-lookup"><span data-stu-id="142a4-118">Results</span></span>

<span data-ttu-id="142a4-119">此步骤的结果是，你通过启用对组织关键数据和配置设置的实时访问控制提高了 Office 365 的安全性。</span><span class="sxs-lookup"><span data-stu-id="142a4-119">The result of this step is that you've increased the security of Office 365 by enabling just-in-time access control for key data and configuration settings for your organization.</span></span>

<span data-ttu-id="142a4-120">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step6)。</span><span class="sxs-lookup"><span data-stu-id="142a4-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="142a4-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="142a4-121">Next Step</span></span>

[<span data-ttu-id="142a4-122">信息保护基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="142a4-122">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)