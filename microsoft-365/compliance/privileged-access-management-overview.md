---
title: 特权访问管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
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
ms.assetid: ''
description: 本文提供了有关 Microsoft 365 中的特权访问管理的概述，其中包括对常见问题解答)  (常见问题的解答。
ms.openlocfilehash: a1bcf1fbe767b4657be8a8ebcc8bf7b101c498d8
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341230"
---
# <a name="privileged-access-management"></a><span data-ttu-id="10e0c-103">特权访问管理</span><span class="sxs-lookup"><span data-stu-id="10e0c-103">Privileged access management</span></span>

<span data-ttu-id="10e0c-104">特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。</span><span class="sxs-lookup"><span data-stu-id="10e0c-104">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="10e0c-105">它可帮助保护您的组织免受使用现有特权管理员帐户的破坏，以访问敏感数据或访问关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="10e0c-105">It can help protect your organization from breaches that use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="10e0c-106">特权访问管理要求用户通过一个高度范围和时间限制的审批工作流请求实时访问，以完成提升的特权和特权任务。</span><span class="sxs-lookup"><span data-stu-id="10e0c-106">Privileged access management requires users to request just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.</span></span> <span data-ttu-id="10e0c-107">此配置为用户提供足够的访问权限，以便在不影响敏感数据或关键配置设置的情况下执行任务。</span><span class="sxs-lookup"><span data-stu-id="10e0c-107">This configuration gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="10e0c-108">在 Microsoft 365 中启用 "特权访问管理" 使组织能够以零为依据的权限运行，并提供了抵御受影响的管理访问漏洞的防御层。</span><span class="sxs-lookup"><span data-stu-id="10e0c-108">Enabling privileged access management in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

<span data-ttu-id="10e0c-109">有关集成客户密码箱和特权访问管理工作流的快速概述，请参阅此 [客户密码箱和特权访问管理视频](https://go.microsoft.com/fwlink/?linkid=2066800)。</span><span class="sxs-lookup"><span data-stu-id="10e0c-109">For a quick overview of the integrated Customer Lockbox and privileged access management workflow, see this [Customer Lockbox and privileged access management video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="10e0c-110">保护层</span><span class="sxs-lookup"><span data-stu-id="10e0c-110">Layers of protection</span></span>

<span data-ttu-id="10e0c-111">特权访问管理补充了 Microsoft 365 安全体系结构中的其他数据和访问功能保护。</span><span class="sxs-lookup"><span data-stu-id="10e0c-111">Privileged access management complements other data and access feature protections within the Microsoft 365 security architecture.</span></span> <span data-ttu-id="10e0c-112">在集成和分层的安全方法中包括特权访问管理提供了一种安全模型，可以最大限度地保护敏感信息和 Microsoft 365 配置设置。</span><span class="sxs-lookup"><span data-stu-id="10e0c-112">Including privileged access management as part of an integrated and layered approach to security provides a security model that maximizes protection of sensitive information and Microsoft 365 configuration settings.</span></span> <span data-ttu-id="10e0c-113">如图中所示，特权访问管理基于 Microsoft 365 数据的本机加密和 Microsoft 365 服务的基于角色的访问控制安全模型提供保护。</span><span class="sxs-lookup"><span data-stu-id="10e0c-113">As shown in the diagram, privileged access management builds on the protection provided with native encryption of Microsoft 365 data and the role-based access control security model of Microsoft 365 services.</span></span> <span data-ttu-id="10e0c-114">在与 [AZURE AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)配合使用时，这两个功能将在不同的范围内提供对实时访问的访问控制。</span><span class="sxs-lookup"><span data-stu-id="10e0c-114">When used with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Microsoft 365 中的分层保护](../media/pam-layered-protection.png)

<span data-ttu-id="10e0c-116">特权访问管理在 **任务** 级别进行定义和作用域，而 Azure AD 特权标识管理在 **角色** 级别应用保护，从而能够执行多项任务。</span><span class="sxs-lookup"><span data-stu-id="10e0c-116">Privileged access management is defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span> <span data-ttu-id="10e0c-117">Azure AD 特权身份管理主要允许管理 AD 角色和角色组的访问，而 Microsoft 365 中的特权访问管理则仅适用于任务级别。</span><span class="sxs-lookup"><span data-stu-id="10e0c-117">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Microsoft 365 applies only at the task level.</span></span>

- <span data-ttu-id="10e0c-118">**在已使用 AZURE AD 特权身份管理的同时启用特权访问管理：** 添加特权访问管理提供了另一个粒度层的保护和审核功能，用于对 Microsoft 365 数据进行特权访问。</span><span class="sxs-lookup"><span data-stu-id="10e0c-118">**Enabling privileged access management while already using Azure AD Privileged Identity Management:** Adding privileged access management provides another granular layer of protection and audit capabilities for privileged access to Microsoft 365 data.</span></span>

- <span data-ttu-id="10e0c-119">**在使用 Office 365 中的特权访问管理时启用 AZURE AD 特权标识管理：**  将 Azure AD 特权标识管理添加到特权访问管理可以扩展对 Microsoft 365 外部的数据的特权访问，这些数据主要由用户角色或标识定义。</span><span class="sxs-lookup"><span data-stu-id="10e0c-119">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management can extend privileged access to data outside of Microsoft 365 that's primarily defined by user roles or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="10e0c-120">特权访问管理体系结构和过程流</span><span class="sxs-lookup"><span data-stu-id="10e0c-120">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="10e0c-121">以下每个过程都将概述权限访问的体系结构，以及它如何与 Microsoft 365 基底、审核和 Exchange 管理运行空间进行交互。</span><span class="sxs-lookup"><span data-stu-id="10e0c-121">Each of the following process flows outline the architecture of privileged access and how it interacts with the Microsoft 365 substrate, auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configure-a-privileged-access-policy"></a><span data-ttu-id="10e0c-122">步骤1：配置特权访问策略</span><span class="sxs-lookup"><span data-stu-id="10e0c-122">Step 1: Configure a privileged access policy</span></span>

<span data-ttu-id="10e0c-123">在使用 [microsoft 365 管理中心](https://admin.microsoft.com) 或 Exchange 管理 PowerShell 配置特权访问策略时，您可以在 microsoft 365 基体中定义策略和特权访问功能进程和策略属性。</span><span class="sxs-lookup"><span data-stu-id="10e0c-123">When you configure a privileged access policy with the [Microsoft 365 admin center](https://admin.microsoft.com) or the Exchange Management PowerShell, you define the policy and the privileged access feature processes and the policy attributes in the Microsoft 365 substrate.</span></span> <span data-ttu-id="10e0c-124">这些活动将记录在安全 &amp; 合规中心中。</span><span class="sxs-lookup"><span data-stu-id="10e0c-124">The activities are logged in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="10e0c-125">现在，策略已启用，并准备好处理审批的传入请求。</span><span class="sxs-lookup"><span data-stu-id="10e0c-125">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![步骤1：策略创建](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="10e0c-127">步骤2：访问请求</span><span class="sxs-lookup"><span data-stu-id="10e0c-127">Step 2: Access request</span></span>

<span data-ttu-id="10e0c-128">在 [Microsoft 365 管理中心](https://admin.microsoft.com) 或使用 Exchange 管理 PowerShell 时，用户可以请求对提升或特权的任务进行访问。</span><span class="sxs-lookup"><span data-stu-id="10e0c-128">In the [Microsoft 365 admin center](https://admin.microsoft.com) or with the Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="10e0c-129">特权访问功能将请求发送到 Microsoft 365 基体，以针对配置的权限访问策略进行处理，并在安全 &amp; 合规中心日志中记录活动。</span><span class="sxs-lookup"><span data-stu-id="10e0c-129">The privileged access feature sends the request to the Microsoft 365 substrate for processing against the configured privilege access policy and records the Activity in the Security &amp; Compliance Center logs.</span></span>

![步骤2：访问请求](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="10e0c-131">步骤3：访问审批</span><span class="sxs-lookup"><span data-stu-id="10e0c-131">Step 3: Access approval</span></span>

<span data-ttu-id="10e0c-132">将生成审批请求，并通过电子邮件将挂起的请求通知通过电子邮件发送给审批者。</span><span class="sxs-lookup"><span data-stu-id="10e0c-132">An approval request is generated and the pending request notification is emailed to approvers.</span></span> <span data-ttu-id="10e0c-133">如果得到批准，则会将特权访问请求作为审批进行处理，并准备完成该任务。</span><span class="sxs-lookup"><span data-stu-id="10e0c-133">If approved, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="10e0c-134">如果拒绝，该任务将被阻止，并且不会向请求者授予任何访问权限。</span><span class="sxs-lookup"><span data-stu-id="10e0c-134">If denied, the task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="10e0c-135">请求者会收到请求审批或通过电子邮件的拒绝通知请求者。</span><span class="sxs-lookup"><span data-stu-id="10e0c-135">The requestor is notified of the request approval or denial via email message.</span></span>

![步骤3：访问审批](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="10e0c-137">步骤4：访问处理</span><span class="sxs-lookup"><span data-stu-id="10e0c-137">Step 4: Access processing</span></span>

<span data-ttu-id="10e0c-138">对于批准的请求，Exchange 管理运行空间将处理该任务。</span><span class="sxs-lookup"><span data-stu-id="10e0c-138">For an approved request, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="10e0c-139">根据特权访问策略检查批准，并由 Microsoft 365 基体进行处理。</span><span class="sxs-lookup"><span data-stu-id="10e0c-139">The approval is checked against the privileged access policy and processed by the Microsoft 365 substrate.</span></span> <span data-ttu-id="10e0c-140">在安全合规中心中记录任务的所有活动 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="10e0c-140">All activity for the task is logged in the Security &amp; Compliance Center.</span></span>

![步骤4：访问处理](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="10e0c-142">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="10e0c-142">Frequently asked questions</span></span>

### <a name="what-skus-can-use-privileged-access-in-office-365"></a><span data-ttu-id="10e0c-143">哪些 Sku 可以使用 Office 365 中的特权访问？</span><span class="sxs-lookup"><span data-stu-id="10e0c-143">What SKUs can use privileged access in Office 365?</span></span>

<span data-ttu-id="10e0c-144">客户可通过多种选择的 Microsoft 365 和 Office 365 订阅和加载项提供特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="10e0c-144">Privileged access management is available for customers for a wide selection of Microsoft 365 and Office 365 subscriptions and add-ons.</span></span> <span data-ttu-id="10e0c-145">有关详细信息，请参阅 [具有特权访问管理的入门](privileged-access-management-configuration.md) 信息。</span><span class="sxs-lookup"><span data-stu-id="10e0c-145">See [Get started with privileged access management](privileged-access-management-configuration.md) for details.</span></span>

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a><span data-ttu-id="10e0c-146">何时将权限访问支持 Exchange 之外的 Office 365 工作负荷？</span><span class="sxs-lookup"><span data-stu-id="10e0c-146">When will privileged access support Office 365 workloads beyond Exchange?</span></span>

<span data-ttu-id="10e0c-147">在其他 Office 365 工作负载中，将很快提供特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="10e0c-147">Privileged access management will be available in other Office 365 workloads soon.</span></span> <span data-ttu-id="10e0c-148">有关更多详细信息，请访问 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap) 。</span><span class="sxs-lookup"><span data-stu-id="10e0c-148">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for more details.</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a><span data-ttu-id="10e0c-149">我的组织需要30个以上的权限访问策略，是否会增加此限制？</span><span class="sxs-lookup"><span data-stu-id="10e0c-149">My organization needs more than 30 privileged access policies, will this limit be increased?</span></span>

<span data-ttu-id="10e0c-150">是，每个组织的最大30个特权访问策略的限制是功能路线图。</span><span class="sxs-lookup"><span data-stu-id="10e0c-150">Yes, raising the current limit of 30 privileged access policies per organization is on the feature roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="10e0c-151">我是否需要成为全局管理员才能管理 Office 365 中的特权访问？</span><span class="sxs-lookup"><span data-stu-id="10e0c-151">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>

<span data-ttu-id="10e0c-152">否，您需要分配给在 Office 365 中管理权限访问的帐户的 Exchange 角色管理角色。</span><span class="sxs-lookup"><span data-stu-id="10e0c-152">No, you need the Exchange Role Management role assigned to accounts that manage privileged access in Office 365.</span></span> <span data-ttu-id="10e0c-153">如果不希望将 Role Management 角色配置为独立帐户权限，则全局管理员角色默认情况下包括此角色，并且可以管理特权访问。</span><span class="sxs-lookup"><span data-stu-id="10e0c-153">If you don't want to configure the Role Management role as a stand-alone account permission, the Global Administrator role includes this role by default and can manage privileged access.</span></span> <span data-ttu-id="10e0c-154">包含在审批者组中的用户不需要是全局管理员，或者已分配角色管理角色以使用 PowerShell 审阅和批准请求。</span><span class="sxs-lookup"><span data-stu-id="10e0c-154">Users included in an approvers' group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests with PowerShell.</span></span>

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a><span data-ttu-id="10e0c-155">如何与客户密码箱相关的特权访问管理？</span><span class="sxs-lookup"><span data-stu-id="10e0c-155">How is privileged access management related to Customer Lockbox?</span></span>

<span data-ttu-id="10e0c-156">[客户密码箱](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) 允许在 Microsoft 访问数据时为组织提供级别的访问控制。</span><span class="sxs-lookup"><span data-stu-id="10e0c-156">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations when Microsoft accesses data.</span></span> <span data-ttu-id="10e0c-157">"特权访问管理" 允许对所有 Microsoft 365 特权任务的组织内的粒度访问控制。</span><span class="sxs-lookup"><span data-stu-id="10e0c-157">Privileged access management allows granular access control within an organization for all Microsoft 365 privileged tasks.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="10e0c-158">准备好开始了吗？</span><span class="sxs-lookup"><span data-stu-id="10e0c-158">Ready to get started?</span></span>

<span data-ttu-id="10e0c-159">开始 [为您的组织配置特权访问管理](privileged-access-management-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="10e0c-159">Start [configuring your organization for privileged access management](privileged-access-management-configuration.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="10e0c-160">了解更多</span><span class="sxs-lookup"><span data-stu-id="10e0c-160">Learn more</span></span>

[<span data-ttu-id="10e0c-161">交互式指南：使用特权访问管理监视和控制管理员任务</span><span class="sxs-lookup"><span data-stu-id="10e0c-161">Interactive guide: Monitor and control administrator tasks with privileged access management</span></span>](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
