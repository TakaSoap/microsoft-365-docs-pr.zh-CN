---
title: 阶段 2：身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的身份基础结构的步骤。
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865804"
---
# <a name="phase-2-identity"></a><span data-ttu-id="b767b-103">阶段 2：身份</span><span class="sxs-lookup"><span data-stu-id="b767b-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="b767b-104">在 Microsoft 365 企业版中，精心计划和执行的身份基础结构将有助于实现更强的安全性，并仅允许通过身份验证的用户和设备访问生产力工作负载和数据。</span><span class="sxs-lookup"><span data-stu-id="b767b-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="b767b-105">如果已部署身份基础结构，请参阅[身份退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必需条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="b767b-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="b767b-106">计划和部署 Microsoft 365 企业版身份基础结构</span><span class="sxs-lookup"><span data-stu-id="b767b-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="b767b-p101">使用以下步骤在云中计划和部署新身份基础结构。此外，还可用这些步骤调整现有本地或混合身份基础结构，以与 Microsoft 365 企业版一起使用。</span><span class="sxs-lookup"><span data-stu-id="b767b-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="b767b-109">计划用户和组</span><span class="sxs-lookup"><span data-stu-id="b767b-109">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="b767b-110">保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="b767b-110">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="b767b-111">设置按需全局管理员</span><span class="sxs-lookup"><span data-stu-id="b767b-111">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="b767b-112">简化密码重置</span><span class="sxs-lookup"><span data-stu-id="b767b-112">Simplify password resets</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="b767b-113">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="b767b-113">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="b767b-114">防止凭据泄露</span><span class="sxs-lookup"><span data-stu-id="b767b-114">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="b767b-115">同步目录</span><span class="sxs-lookup"><span data-stu-id="b767b-115">Synchronize directories</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="b767b-116">监控同步运行状况</span><span class="sxs-lookup"><span data-stu-id="b767b-116">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="b767b-117">简化密码更新</span><span class="sxs-lookup"><span data-stu-id="b767b-117">Simplify password updates</span></span>](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="b767b-118">简化用户登录</span><span class="sxs-lookup"><span data-stu-id="b767b-118">Simplify user sign-in</span></span>](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="b767b-119">自定义 Office 365 登录页</span><span class="sxs-lookup"><span data-stu-id="b767b-119">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="b767b-120">设置自动许可</span><span class="sxs-lookup"><span data-stu-id="b767b-120">Set up automatic licensing</span></span>](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="b767b-121">监控租户和登录活动</span><span class="sxs-lookup"><span data-stu-id="b767b-121">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="b767b-122">允许用户创建和管理自己的组</span><span class="sxs-lookup"><span data-stu-id="b767b-122">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="b767b-123">设置动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="b767b-123">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |

<span data-ttu-id="b767b-124">在完成这些步骤后，请转到这一阶段的[退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="b767b-124">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="b767b-125">标识和设备访问建议</span><span class="sxs-lookup"><span data-stu-id="b767b-125">Identity and device access prerequisites</span></span>

<span data-ttu-id="b767b-p102">Microsoft 提供了一组有关[标识和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。对于标识，请使用下列文章中的建议和设置以及此阶段中的步骤：</span><span class="sxs-lookup"><span data-stu-id="b767b-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="b767b-128">先决条件</span><span class="sxs-lookup"><span data-stu-id="b767b-128">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="b767b-129">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="b767b-129">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="b767b-130">Microsoft 如何使用 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="b767b-130">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b767b-131">了解 Microsoft 的 IT 专家如何使用以下这些资源来计划和部署 Microsoft 365 企业版的标识功能：</span><span class="sxs-lookup"><span data-stu-id="b767b-131">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="b767b-132">管理 Microsoft 用户标识和安全访问</span><span class="sxs-lookup"><span data-stu-id="b767b-132">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="b767b-133">使用 Azure AD Privileged Identity Management 进行提升的访问</span><span class="sxs-lookup"><span data-stu-id="b767b-133">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="b767b-134">Contoso 如何使用 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="b767b-134">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b767b-135">了解 Contoso Corporation（虚构但具代表性的跨国企业）如何为 Microsoft 365 云服务[部署混合身份基础结构](contoso-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="b767b-135">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="b767b-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b767b-136">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="b767b-137">计划用户和组</span><span class="sxs-lookup"><span data-stu-id="b767b-137">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
