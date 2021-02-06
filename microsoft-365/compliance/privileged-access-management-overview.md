---
title: 了解特权访问管理
description: 本文概述了 Microsoft 365 中的特权访问管理，包括常见问题解答 (常见问题) 。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126601"
---
# <a name="learn-about-privileged-access-management"></a><span data-ttu-id="8370f-103">了解特权访问管理</span><span class="sxs-lookup"><span data-stu-id="8370f-103">Learn about privileged access management</span></span>

<span data-ttu-id="8370f-104">特权访问管理允许对 Office 365 中的特权管理任务进行精细的访问控制。</span><span class="sxs-lookup"><span data-stu-id="8370f-104">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="8370f-105">它可以帮助保护组织免受使用现有特权管理员帐户的漏洞，这些帐户具有对敏感数据的常访问权或关键配置设置的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8370f-105">It can help protect your organization from breaches that use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="8370f-106">特权访问管理要求用户请求实时访问权限，以通过范围和时间限制较高的审批工作流完成提升的特权任务。</span><span class="sxs-lookup"><span data-stu-id="8370f-106">Privileged access management requires users to request just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.</span></span> <span data-ttu-id="8370f-107">此配置使用户能够具有足够的访问权限来执行当前任务，而不会面临敏感数据或关键配置设置泄露的风险。</span><span class="sxs-lookup"><span data-stu-id="8370f-107">This configuration gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="8370f-108">在 Microsoft 365 中启用特权访问管理后，你的组织可以零长期特权运行，并提供一层防御长期管理访问漏洞的防御层。</span><span class="sxs-lookup"><span data-stu-id="8370f-108">Enabling privileged access management in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

<span data-ttu-id="8370f-109">有关集成的客户密码箱和特权访问管理工作流的快速概述，请参阅此客户密码箱和 [特权访问管理视频](https://go.microsoft.com/fwlink/?linkid=2066800)。</span><span class="sxs-lookup"><span data-stu-id="8370f-109">For a quick overview of the integrated Customer Lockbox and privileged access management workflow, see this [Customer Lockbox and privileged access management video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="8370f-110">保护层</span><span class="sxs-lookup"><span data-stu-id="8370f-110">Layers of protection</span></span>

<span data-ttu-id="8370f-111">特权访问管理补充了 Microsoft 365 安全体系结构内的其他数据和访问功能保护。</span><span class="sxs-lookup"><span data-stu-id="8370f-111">Privileged access management complements other data and access feature protections within the Microsoft 365 security architecture.</span></span> <span data-ttu-id="8370f-112">将特权访问管理作为集成和分层安全方法的一部分提供一种安全模型，可最大限度地保护敏感信息和 Microsoft 365 配置设置。</span><span class="sxs-lookup"><span data-stu-id="8370f-112">Including privileged access management as part of an integrated and layered approach to security provides a security model that maximizes protection of sensitive information and Microsoft 365 configuration settings.</span></span> <span data-ttu-id="8370f-113">如图所示，特权访问管理基于 Microsoft 365 数据的本机加密提供的保护以及 Microsoft 365 服务的基于角色的访问控制安全模型。</span><span class="sxs-lookup"><span data-stu-id="8370f-113">As shown in the diagram, privileged access management builds on the protection provided with native encryption of Microsoft 365 data and the role-based access control security model of Microsoft 365 services.</span></span> <span data-ttu-id="8370f-114">当与 [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)一起使用时，这两项功能为访问控制提供不同范围的实时访问权限。</span><span class="sxs-lookup"><span data-stu-id="8370f-114">When used with [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Microsoft 365 中的分层保护](../media/pam-layered-protection.png)

<span data-ttu-id="8370f-116">特权访问管理在任务级别定义和作用域，而Azure AD Privileged Identity Management 在角色级别应用保护，能够执行多个任务。</span><span class="sxs-lookup"><span data-stu-id="8370f-116">Privileged access management is defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span> <span data-ttu-id="8370f-117">Azure AD Privileged Identity Management 主要允许管理 AD 角色和角色组的访问权限，而 Microsoft 365 中的特权访问管理仅适用于任务级别。</span><span class="sxs-lookup"><span data-stu-id="8370f-117">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Microsoft 365 applies only at the task level.</span></span>

- <span data-ttu-id="8370f-118">**在已使用 Azure AD Privileged Identity Management** 的同时启用特权访问管理：添加特权访问管理为特权访问 Microsoft 365 数据提供了另一层精细的保护和审核功能。</span><span class="sxs-lookup"><span data-stu-id="8370f-118">**Enabling privileged access management while already using Azure AD Privileged Identity Management:** Adding privileged access management provides another granular layer of protection and audit capabilities for privileged access to Microsoft 365 data.</span></span>

- <span data-ttu-id="8370f-119">**在 Office 365**  中已使用特权访问管理的同时启用 Azure AD Privileged Identity Management： 将 Azure AD Privileged Identity Management 添加到特权访问管理可以扩展对 Microsoft 365 外部数据的特权访问，这些数据主要由用户角色或标识定义。</span><span class="sxs-lookup"><span data-stu-id="8370f-119">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management can extend privileged access to data outside of Microsoft 365 that's primarily defined by user roles or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="8370f-120">特权访问管理体系结构和流程</span><span class="sxs-lookup"><span data-stu-id="8370f-120">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="8370f-121">以下每个流程流概述了特权访问的体系结构及其与 Microsoft 365 底层、审核和 Exchange 管理运行空间的交互方式。</span><span class="sxs-lookup"><span data-stu-id="8370f-121">Each of the following process flows outline the architecture of privileged access and how it interacts with the Microsoft 365 substrate, auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configure-a-privileged-access-policy"></a><span data-ttu-id="8370f-122">步骤 1：配置特权访问策略</span><span class="sxs-lookup"><span data-stu-id="8370f-122">Step 1: Configure a privileged access policy</span></span>

<span data-ttu-id="8370f-123">使用 [Microsoft 365](https://admin.microsoft.com) 管理中心或 Exchange 管理 PowerShell 配置特权访问策略时，在 Microsoft 365 底层中定义策略、特权访问功能进程和策略属性。</span><span class="sxs-lookup"><span data-stu-id="8370f-123">When you configure a privileged access policy with the [Microsoft 365 admin center](https://admin.microsoft.com) or the Exchange Management PowerShell, you define the policy and the privileged access feature processes and the policy attributes in the Microsoft 365 substrate.</span></span> <span data-ttu-id="8370f-124">这些活动记录在安全合规 &amp; 中心。</span><span class="sxs-lookup"><span data-stu-id="8370f-124">The activities are logged in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="8370f-125">该策略现已启用，并已准备好处理传入的审批请求。</span><span class="sxs-lookup"><span data-stu-id="8370f-125">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![步骤 1：策略创建](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="8370f-127">步骤 2：访问请求</span><span class="sxs-lookup"><span data-stu-id="8370f-127">Step 2: Access request</span></span>

<span data-ttu-id="8370f-128">在 [Microsoft 365 管理](https://admin.microsoft.com) 中心或 Exchange 管理 PowerShell 中，用户可以请求对提升或特权任务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8370f-128">In the [Microsoft 365 admin center](https://admin.microsoft.com) or with the Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="8370f-129">特权访问功能将请求发送到 Microsoft 365 底层，以根据配置的权限访问策略进行处理，并将活动记录在安全 &amp; 合规中心日志中。</span><span class="sxs-lookup"><span data-stu-id="8370f-129">The privileged access feature sends the request to the Microsoft 365 substrate for processing against the configured privilege access policy and records the Activity in the Security &amp; Compliance Center logs.</span></span>

![步骤 2：访问请求](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="8370f-131">步骤 3：访问审批</span><span class="sxs-lookup"><span data-stu-id="8370f-131">Step 3: Access approval</span></span>

<span data-ttu-id="8370f-132">将生成审批请求，并通过电子邮件将待处理的请求通知通过电子邮件发送给审批者。</span><span class="sxs-lookup"><span data-stu-id="8370f-132">An approval request is generated and the pending request notification is emailed to approvers.</span></span> <span data-ttu-id="8370f-133">如果获得批准，特权访问请求将处理为审批，并且任务已准备好完成。</span><span class="sxs-lookup"><span data-stu-id="8370f-133">If approved, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="8370f-134">如果拒绝，则阻止该任务，并且不会向请求者授予任何访问权限。</span><span class="sxs-lookup"><span data-stu-id="8370f-134">If denied, the task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="8370f-135">通过电子邮件向请求者通知请求审批或拒绝。</span><span class="sxs-lookup"><span data-stu-id="8370f-135">The requestor is notified of the request approval or denial via email message.</span></span>

![步骤 3：访问审批](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="8370f-137">步骤 4：访问处理</span><span class="sxs-lookup"><span data-stu-id="8370f-137">Step 4: Access processing</span></span>

<span data-ttu-id="8370f-138">对于已批准的请求，任务由 Exchange 管理运行空间处理。</span><span class="sxs-lookup"><span data-stu-id="8370f-138">For an approved request, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="8370f-139">根据特权访问策略检查批准，由 Microsoft 365 底层处理。</span><span class="sxs-lookup"><span data-stu-id="8370f-139">The approval is checked against the privileged access policy and processed by the Microsoft 365 substrate.</span></span> <span data-ttu-id="8370f-140">任务的所有活动都记录在安全合规 &amp; 中心。</span><span class="sxs-lookup"><span data-stu-id="8370f-140">All activity for the task is logged in the Security &amp; Compliance Center.</span></span>

![步骤 4：访问处理](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="8370f-142">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="8370f-142">Frequently asked questions</span></span>

### <a name="what-skus-can-use-privileged-access-in-office-365"></a><span data-ttu-id="8370f-143">哪些 SUS 可以在 Office 365 中使用特权访问？</span><span class="sxs-lookup"><span data-stu-id="8370f-143">What SKUs can use privileged access in Office 365?</span></span>

<span data-ttu-id="8370f-144">特权访问管理适用于各种 Microsoft 365 和 Office 365 订阅和加载项的客户。</span><span class="sxs-lookup"><span data-stu-id="8370f-144">Privileged access management is available for customers for a wide selection of Microsoft 365 and Office 365 subscriptions and add-ons.</span></span> <span data-ttu-id="8370f-145">有关详细信息 [，请参阅特权访问管理](privileged-access-management-configuration.md) 入门。</span><span class="sxs-lookup"><span data-stu-id="8370f-145">See [Get started with privileged access management](privileged-access-management-configuration.md) for details.</span></span>

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a><span data-ttu-id="8370f-146">特权访问何时将支持 Exchange 之外的 Office 365 工作负载？</span><span class="sxs-lookup"><span data-stu-id="8370f-146">When will privileged access support Office 365 workloads beyond Exchange?</span></span>

<span data-ttu-id="8370f-147">特权访问管理将很快在其他 Office 365 工作负载中提供。</span><span class="sxs-lookup"><span data-stu-id="8370f-147">Privileged access management will be available in other Office 365 workloads soon.</span></span> <span data-ttu-id="8370f-148">有关详细信息，请访问 [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) 路线图。</span><span class="sxs-lookup"><span data-stu-id="8370f-148">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for more details.</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a><span data-ttu-id="8370f-149">我的组织需要 30 多个特权访问策略，是否将提高此限制？</span><span class="sxs-lookup"><span data-stu-id="8370f-149">My organization needs more than 30 privileged access policies, will this limit be increased?</span></span>

<span data-ttu-id="8370f-150">是的，提升每个组织当前 30 个特权访问策略的限制取决于功能路线图。</span><span class="sxs-lookup"><span data-stu-id="8370f-150">Yes, raising the current limit of 30 privileged access policies per organization is on the feature roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="8370f-151">是否需要成为全局管理员才能管理 Office 365 中的特权访问？</span><span class="sxs-lookup"><span data-stu-id="8370f-151">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>

<span data-ttu-id="8370f-152">不需要，您需要为管理 Office 365 中的特权访问的帐户分配 Exchange 角色管理角色。</span><span class="sxs-lookup"><span data-stu-id="8370f-152">No, you need the Exchange Role Management role assigned to accounts that manage privileged access in Office 365.</span></span> <span data-ttu-id="8370f-153">如果不想将角色管理角色配置为独立帐户权限，则默认情况下全局管理员角色包括此角色，并可以管理特权访问。</span><span class="sxs-lookup"><span data-stu-id="8370f-153">If you don't want to configure the Role Management role as a stand-alone account permission, the Global Administrator role includes this role by default and can manage privileged access.</span></span> <span data-ttu-id="8370f-154">审批者组中包含的用户无需是全局管理员或分配有角色管理角色，即使用 PowerShell 审阅和批准请求。</span><span class="sxs-lookup"><span data-stu-id="8370f-154">Users included in an approvers' group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests with PowerShell.</span></span>

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a><span data-ttu-id="8370f-155">特权访问管理与客户密码箱如何相关？</span><span class="sxs-lookup"><span data-stu-id="8370f-155">How is privileged access management related to Customer Lockbox?</span></span>

<span data-ttu-id="8370f-156">[当 Microsoft](/office365/admin/manage/customer-lockbox-requests) 访问数据时，客户密码箱允许组织进行一级访问控制。</span><span class="sxs-lookup"><span data-stu-id="8370f-156">[Customer Lockbox](/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations when Microsoft accesses data.</span></span> <span data-ttu-id="8370f-157">特权访问管理允许对组织中所有 Microsoft 365 特权任务进行精细访问控制。</span><span class="sxs-lookup"><span data-stu-id="8370f-157">Privileged access management allows granular access control within an organization for all Microsoft 365 privileged tasks.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="8370f-158">准备好开始了吗？</span><span class="sxs-lookup"><span data-stu-id="8370f-158">Ready to get started?</span></span>

<span data-ttu-id="8370f-159">开始 [为组织配置特权访问管理](privileged-access-management-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="8370f-159">Start [configuring your organization for privileged access management](privileged-access-management-configuration.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="8370f-160">了解更多</span><span class="sxs-lookup"><span data-stu-id="8370f-160">Learn more</span></span>

[<span data-ttu-id="8370f-161">交互式指南：使用特权访问管理监视和控制管理员任务</span><span class="sxs-lookup"><span data-stu-id="8370f-161">Interactive guide: Monitor and control administrator tasks with privileged access management</span></span>](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
