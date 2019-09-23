---
title: 阶段 2：身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的身份基础结构的步骤。
ms.openlocfilehash: 2d9ffcc5122b5a5dfc94fb007167655e879d6799
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071691"
---
# <a name="phase-2-identity"></a><span data-ttu-id="afdb7-103">阶段 2：身份</span><span class="sxs-lookup"><span data-stu-id="afdb7-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="afdb7-104">在 Microsoft 365 企业版中，精心计划和执行的身份基础结构将有助于实现更强的安全性，并仅允许通过身份验证的用户和设备访问生产力工作负载和数据。</span><span class="sxs-lookup"><span data-stu-id="afdb7-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="afdb7-105">观看此视频，以获取 Microsoft 365 企业版身份模型和身份验证的概述。</span><span class="sxs-lookup"><span data-stu-id="afdb7-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="afdb7-106"><p> </p></span><span class="sxs-lookup"><span data-stu-id="afdb7-106"></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="afdb7-107">如果已部署身份基础结构，请参阅[身份退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必需条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="afdb7-107">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="afdb7-108">有关每个 Microsoft 365 企业版计划的身份功能、Azure Active Directory (Azure AD) 的角色、本地和基于云的组件，以及最常见的身份验证配置，请参阅[身份基础结构海报](media/identity-infrastructure/M365E-ID-Infra.pdf)。</span><span class="sxs-lookup"><span data-stu-id="afdb7-108">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="afdb7-109">[![身份基础结构海报](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="afdb7-109">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="afdb7-110">此海报包含两页内容，可借助它快速实施 Microsoft 365 企业版的身份概念和配置。</span><span class="sxs-lookup"><span data-stu-id="afdb7-110">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="afdb7-111">还可以[下载此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)并按 letter、legal 或 tabloid (11 x 17) 格式打印。</span><span class="sxs-lookup"><span data-stu-id="afdb7-111">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="afdb7-112">计划和部署 Microsoft 365 企业版身份基础结构</span><span class="sxs-lookup"><span data-stu-id="afdb7-112">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="afdb7-p101">使用以下步骤在云中计划和部署新身份基础结构。此外，还可用这些步骤调整现有本地或混合身份基础结构，以与 Microsoft 365 企业版一起使用。</span><span class="sxs-lookup"><span data-stu-id="afdb7-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="afdb7-115">创建和保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="afdb7-115">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="afdb7-116">保护密码安全</span><span class="sxs-lookup"><span data-stu-id="afdb7-116">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="afdb7-117">保护和管理用户登录</span><span class="sxs-lookup"><span data-stu-id="afdb7-117">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="afdb7-118">添加用户帐户</span><span class="sxs-lookup"><span data-stu-id="afdb7-118">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="afdb7-119">使用组进行管理</span><span class="sxs-lookup"><span data-stu-id="afdb7-119">Use groups for easier management</span></span>](identity-use-group-management.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="afdb7-120">配置标识治理</span><span class="sxs-lookup"><span data-stu-id="afdb7-120">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="afdb7-121">在完成这些步骤后，请转到这一阶段的[退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版标识的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="afdb7-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="afdb7-122">标识和设备访问建议</span><span class="sxs-lookup"><span data-stu-id="afdb7-122">Identity and device access recommendations</span></span>

<span data-ttu-id="afdb7-p102">Microsoft 提供了一组有关[标识和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。对于标识，请使用下列文章中的建议和设置以及此阶段中的步骤：</span><span class="sxs-lookup"><span data-stu-id="afdb7-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="afdb7-125">先决条件</span><span class="sxs-lookup"><span data-stu-id="afdb7-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="afdb7-126">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="afdb7-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="afdb7-127">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="afdb7-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="afdb7-128">了解 Microsoft 的 IT 专家如何[管理标识和安全访问](https://www.microsoft.com/zh-CN/itshowcase/deploying-and-managing-microsoft-365#primaryR5)。</span><span class="sxs-lookup"><span data-stu-id="afdb7-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/zh-CN/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="afdb7-129">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="afdb7-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="afdb7-130">了解 Contoso Corporation（虚构但具代表性的跨国企业）如何为 Microsoft 365 云服务[部署混合身份基础结构](contoso-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="afdb7-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="afdb7-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="afdb7-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="afdb7-132">创建和保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="afdb7-132">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
