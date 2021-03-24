---
title: Microsoft 365 的识别指南
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
- m365initiative-coredeploy
ms.custom: ''
description: Microsoft 365 标识路线图。
ms.openlocfilehash: 456841bfc15d143409535140f2b5a63ee72e99d2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051302"
---
# <a name="identity-roadmap-for-microsoft-365"></a><span data-ttu-id="3be8d-103">Microsoft 365 的识别指南</span><span class="sxs-lookup"><span data-stu-id="3be8d-103">Identity roadmap for Microsoft 365</span></span>

<span data-ttu-id="3be8d-104">在 Microsoft 365 企业版中，精心规划和执行的身份基础结构为增强安全性提供途径，包括将工作效率工作负载及其数据的访问权限限制为仅经过身份验证的用户和设备。</span><span class="sxs-lookup"><span data-stu-id="3be8d-104">In Microsoft 365 for enterprise, a well-planned and executed identity infrastructure paves the way for stronger security, including restricting access to your productivity workloads and their data to only authenticated users and devices.</span></span>

<span data-ttu-id="3be8d-105">有关 Microsoft 365 企业版标识模型和身份验证的概述，请观看此视频。</span><span class="sxs-lookup"><span data-stu-id="3be8d-105">For an overview of identity models and authentication for Microsoft 365 for enterprise, watch this video.</span></span>

<span data-ttu-id="3be8d-106"><p> </p></span><span class="sxs-lookup"><span data-stu-id="3be8d-106"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="3be8d-107">有关每个 Microsoft 365 企业版计划的标识功能、Azure Active Directory 的角色、本地和基于云的组件以及最常见的身份验证配置的信息，请参阅标识 [基础结构海报](../downloads/m365e-identity-infra.pdf)。</span><span class="sxs-lookup"><span data-stu-id="3be8d-107">For information about the identity features of each Microsoft 365 for enterprise plan, the role of Azure Active Directory, both the on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](../downloads/m365e-identity-infra.pdf).</span></span>

<span data-ttu-id="3be8d-108">[![身份基础结构海报](../downloads/m365e-identity-infra.png)](../downloads/m365e-identity-infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="3be8d-108">[![The Identity Infrastructure poster](../downloads/m365e-identity-infra.png)](../downloads/m365e-identity-infra.pdf)</span></span>

<span data-ttu-id="3be8d-109">查看此两页海报，以快速提升 Microsoft 365 企业版的身份概念和配置。</span><span class="sxs-lookup"><span data-stu-id="3be8d-109">Review this two-page poster to quickly ramp up on identity concepts and configurations for Microsoft 365 for enterprise.</span></span>

<span data-ttu-id="3be8d-110">您还可以下载 [此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/m365e-identity-infra.pdf) ，并可以 11 x 17 格式以信函、法律或文 (格式) 打印。</span><span class="sxs-lookup"><span data-stu-id="3be8d-110">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/m365e-identity-infra.pdf) and can print it in letter, legal, or tabloid (11 x 17) format.</span></span>

## <a name="plan"></a><span data-ttu-id="3be8d-111">计划</span><span class="sxs-lookup"><span data-stu-id="3be8d-111">Plan</span></span>

<span data-ttu-id="3be8d-112">要规划标识实现，请执行：</span><span class="sxs-lookup"><span data-stu-id="3be8d-112">To plan for your identity implementation:</span></span>

- [<span data-ttu-id="3be8d-113">了解不同的标识模型</span><span class="sxs-lookup"><span data-stu-id="3be8d-113">Understand the different identity models</span></span>](about-microsoft-365-identity.md)
- [<span data-ttu-id="3be8d-114">规划混合标识和目录同步</span><span class="sxs-lookup"><span data-stu-id="3be8d-114">Plan for hybrid identity and directory synchronization</span></span>](plan-for-directory-synchronization.md)

## <a name="deploy"></a><span data-ttu-id="3be8d-115">部署</span><span class="sxs-lookup"><span data-stu-id="3be8d-115">Deploy</span></span>

<span data-ttu-id="3be8d-116">部署标识实现：</span><span class="sxs-lookup"><span data-stu-id="3be8d-116">To deploy your identity implementation:</span></span>

- [<span data-ttu-id="3be8d-117">保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="3be8d-117">Protect your global administrator accounts</span></span>](protect-your-global-administrator-accounts.md)
- [<span data-ttu-id="3be8d-118">配置和使用仅云标识</span><span class="sxs-lookup"><span data-stu-id="3be8d-118">Configure and use cloud-only identities</span></span>](cloud-only-identities.md)
- [<span data-ttu-id="3be8d-119">配置和使用混合标识</span><span class="sxs-lookup"><span data-stu-id="3be8d-119">Configure and use hybrid identities</span></span>](prepare-for-directory-synchronization.md)
- [<span data-ttu-id="3be8d-120">设置目录同步</span><span class="sxs-lookup"><span data-stu-id="3be8d-120">Set up directory synchronization</span></span>](set-up-directory-synchronization.md)
- <span data-ttu-id="3be8d-121">如果需要，部署 [混合标识方案](hybrid-solutions.md)</span><span class="sxs-lookup"><span data-stu-id="3be8d-121">If needed, deploy [hybrid identity scenarios](hybrid-solutions.md)</span></span>

### <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="3be8d-122">标识和设备访问建议</span><span class="sxs-lookup"><span data-stu-id="3be8d-122">Identity and device access recommendations</span></span>

<span data-ttu-id="3be8d-123">为了帮助确保员工的安全和高效工作，Microsoft 提供了一组有关标识 [和设备访问的建议](../security/defender-365-security/microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="3be8d-123">To help ensure a secure and productive workforce, Microsoft provides a set of recommendations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md).</span></span> <span data-ttu-id="3be8d-124">对于标识，请使用以下文章中的建议和设置：</span><span class="sxs-lookup"><span data-stu-id="3be8d-124">For identity, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="3be8d-125">先决条件</span><span class="sxs-lookup"><span data-stu-id="3be8d-125">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="3be8d-126">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="3be8d-126">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="manage"></a><span data-ttu-id="3be8d-127">管理</span><span class="sxs-lookup"><span data-stu-id="3be8d-127">Manage</span></span>

<span data-ttu-id="3be8d-128">若要管理 Microsoft 365 标识部署，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3be8d-128">To manage your Microsoft 365 identity deployment, see:</span></span>

- [<span data-ttu-id="3be8d-129">用户帐户</span><span class="sxs-lookup"><span data-stu-id="3be8d-129">User accounts</span></span>](manage-microsoft-365-accounts.md)
- [<span data-ttu-id="3be8d-130">许可证</span><span class="sxs-lookup"><span data-stu-id="3be8d-130">Licenses</span></span>](assign-licenses-to-user-accounts.md)
- [<span data-ttu-id="3be8d-131">密码</span><span class="sxs-lookup"><span data-stu-id="3be8d-131">Passwords</span></span>](manage-microsoft-365-passwords.md)
- [<span data-ttu-id="3be8d-132">组</span><span class="sxs-lookup"><span data-stu-id="3be8d-132">Groups</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="3be8d-133">管理</span><span class="sxs-lookup"><span data-stu-id="3be8d-133">Governance</span></span>](manage-microsoft-365-identity-governance.md)
- [<span data-ttu-id="3be8d-134">目录同步</span><span class="sxs-lookup"><span data-stu-id="3be8d-134">Directory synchronization</span></span>](view-directory-synchronization-status.md)

## <a name="how-microsoft-does-identity-for-microsoft-365"></a><span data-ttu-id="3be8d-135">Microsoft 如何为 Microsoft 365 标识</span><span class="sxs-lookup"><span data-stu-id="3be8d-135">How Microsoft does identity for Microsoft 365</span></span>

<span data-ttu-id="3be8d-136">了解 Microsoft 的 IT 专家如何[管理标识和安全访问](https://www.microsoft.com/en-us/itshowcase/managing-user-identities-and-secure-access-at-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="3be8d-136">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/en-us/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span></span>

>[!Note]
><span data-ttu-id="3be8d-137">此 IT 展示资源仅提供英文版。</span><span class="sxs-lookup"><span data-stu-id="3be8d-137">This IT Showcase resource is available only in English.</span></span>
>

## <a name="how-contoso-did-identity-for-microsoft-365"></a><span data-ttu-id="3be8d-138">Contoso 如何识别 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3be8d-138">How Contoso did identity for Microsoft 365</span></span>

<span data-ttu-id="3be8d-139">有关虚构但具有代表性的跨国组织如何为 Microsoft 365 云服务部署混合标识基础结构的示例，请参阅 [Contoso Corporation](contoso-identity.md)的标识。</span><span class="sxs-lookup"><span data-stu-id="3be8d-139">For an example of how a fictional but representative multinational organization has deployed a hybrid identity infrastructure for Microsoft 365 cloud services, see [Identity for the Contoso Corporation](contoso-identity.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="3be8d-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3be8d-140">Next step</span></span>

<span data-ttu-id="3be8d-141">使用标识模型开始 [身份规划](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="3be8d-141">Start your identity planning with [Identity models](about-microsoft-365-identity.md).</span></span>
