---
title: 阶段 2：身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的身份基础结构的步骤。
ms.openlocfilehash: 6acd462a0fcd4169a42a0b1d0e1738ffcba597f5
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073892"
---
# <a name="phase-2-identity"></a><span data-ttu-id="6fbe1-103">阶段 2：身份</span><span class="sxs-lookup"><span data-stu-id="6fbe1-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="6fbe1-104">在 Microsoft 365 企业版中，精心计划和执行的身份基础结构将有助于实现更强的安全性，并仅允许通过身份验证的用户和设备访问生产力工作负载和数据。</span><span class="sxs-lookup"><span data-stu-id="6fbe1-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="6fbe1-105">如果已部署身份基础结构，请参阅[身份退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必需条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="6fbe1-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="6fbe1-106">计划和部署 Microsoft 365 企业版身份基础结构</span><span class="sxs-lookup"><span data-stu-id="6fbe1-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="6fbe1-107">开始之前，请观看此视频，以获取 Microsoft 365 身份模型和身份验证的概述。</span><span class="sxs-lookup"><span data-stu-id="6fbe1-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="6fbe1-p101">使用以下步骤在云中计划和部署新身份基础结构。此外，还可用这些步骤调整现有本地或混合身份基础结构，以与 Microsoft 365 企业版一起使用。</span><span class="sxs-lookup"><span data-stu-id="6fbe1-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="6fbe1-110">计划用户和组</span><span class="sxs-lookup"><span data-stu-id="6fbe1-110">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="6fbe1-111">保护你的特权标识</span><span class="sxs-lookup"><span data-stu-id="6fbe1-111">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="6fbe1-112">配置混合标识</span><span class="sxs-lookup"><span data-stu-id="6fbe1-112">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="6fbe1-113">配置安全的用户身份验证</span><span class="sxs-lookup"><span data-stu-id="6fbe1-113">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="6fbe1-114">简化用户访问权限</span><span class="sxs-lookup"><span data-stu-id="6fbe1-114">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="6fbe1-115">使用组实现更轻松地管理</span><span class="sxs-lookup"><span data-stu-id="6fbe1-115">Use groups for easier management</span></span>](identity-self-service-group-management.md) |

<span data-ttu-id="6fbe1-116">在完成这些步骤后，请转到这一阶段的[退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="6fbe1-116">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="6fbe1-117">标识和设备访问建议</span><span class="sxs-lookup"><span data-stu-id="6fbe1-117">Identity and device access recommendations</span></span>

<span data-ttu-id="6fbe1-p102">Microsoft 提供了一组有关[标识和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。对于标识，请使用下列文章中的建议和设置以及此阶段中的步骤：</span><span class="sxs-lookup"><span data-stu-id="6fbe1-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="6fbe1-120">先决条件</span><span class="sxs-lookup"><span data-stu-id="6fbe1-120">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="6fbe1-121">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="6fbe1-121">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="6fbe1-122">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="6fbe1-122">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6fbe1-123">了解 Microsoft 的 IT 专家如何[管理标识和安全访问](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5)。</span><span class="sxs-lookup"><span data-stu-id="6fbe1-123">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="6fbe1-124">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="6fbe1-124">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6fbe1-125">了解 Contoso Corporation（虚构但具代表性的跨国企业）如何为 Microsoft 365 云服务[部署混合身份基础结构](contoso-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="6fbe1-125">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="6fbe1-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6fbe1-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="6fbe1-127">计划用户和组</span><span class="sxs-lookup"><span data-stu-id="6fbe1-127">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
