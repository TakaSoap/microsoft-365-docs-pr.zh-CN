---
title: 第 6 阶段：信息保护
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 这些步骤用于部署 Microsoft 365 企业版信息保护基础结构。
ms.openlocfilehash: 418506927885948cd917061d99bb69163b1e44a5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067125"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="8efc4-103">阶段 6：信息保护</span><span class="sxs-lookup"><span data-stu-id="8efc4-103">Phase 6: Information protection</span></span>

![阶段 6：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="8efc4-p101">信息保护是一组策略和技术，定义了如何传输、存储和处理敏感信息。在第 6 阶段逐步介绍了 Microsoft 365 企业版的信息保护设置和功能，有助于用户保护基于云的工作负载和方案的数据安全。</span><span class="sxs-lookup"><span data-stu-id="8efc4-p101">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information. In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="8efc4-107">如果已部署信息保护，请查看这一阶段的[退出条件](infoprotect-exit-criteria.md)，以确保其满足 Microsoft 365 企业版的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="8efc4-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="8efc4-108">计划和部署 Microsoft 365 企业版信息保护基础结构</span><span class="sxs-lookup"><span data-stu-id="8efc4-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="8efc4-p102">与法律和合规团队协作以确定组织是否需要符合 HIPPA、CJIS 或 GDPR 等合规标准，这一点很重要。此外，还应与安全组协作，以确定组织和需要额外安全性的部门或组的信息保护目标。</span><span class="sxs-lookup"><span data-stu-id="8efc4-p102">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR. You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="8efc4-111">接下来，使用以下步骤来构建 Microsoft 365 企业版的信息保护。</span><span class="sxs-lookup"><span data-stu-id="8efc4-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![第 1 步](../media/stepnumbers/Step1.png)|[<span data-ttu-id="8efc4-113">定义安全和信息保护级别</span><span class="sxs-lookup"><span data-stu-id="8efc4-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![第 2 步](../media/stepnumbers/Step2.png)|[<span data-ttu-id="8efc4-115">配置环境分类</span><span class="sxs-lookup"><span data-stu-id="8efc4-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![第 3 步](../media/stepnumbers/Step3.png)|[<span data-ttu-id="8efc4-117">为 Microsoft 365 配置提升的安全性</span><span class="sxs-lookup"><span data-stu-id="8efc4-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![第 4 步](../media/stepnumbers/Step4.png)|[<span data-ttu-id="8efc4-119">配置 Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="8efc4-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![第 5 步](../media/stepnumbers/Step5.png)|[<span data-ttu-id="8efc4-121">配置 Office 365 数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="8efc4-121">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![第 6 步](../media/stepnumbers/Step6.png)|[<span data-ttu-id="8efc4-123">配置电子邮件加密</span><span class="sxs-lookup"><span data-stu-id="8efc4-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![第 7 步](../media/stepnumbers/Step7.png)|[<span data-ttu-id="8efc4-125">配置 Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="8efc4-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="8efc4-126">在完成这些步骤后，请转到这一阶段的[退出条件](infoprotect-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必备条件和可选条件。</span><span class="sxs-lookup"><span data-stu-id="8efc4-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="8efc4-127">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="8efc4-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8efc4-128">了解 Microsoft 的 IT 专家如何使用 [Azure 信息保护和保护数据](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9)。</span><span class="sxs-lookup"><span data-stu-id="8efc4-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="8efc4-129">Contoso 是如何使用 Microsoft 365 企业版的</span><span class="sxs-lookup"><span data-stu-id="8efc4-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8efc4-130">了解 Contoso Corporation（虚构但具代表性的跨国企业）如何使用 Microsoft 365 云服务[实现信息保护](contoso-info-protect.md)。</span><span class="sxs-lookup"><span data-stu-id="8efc4-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="8efc4-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8efc4-132">Next step</span></span>

|||
|:-------|:-----|
|![第 1 步](../media/stepnumbers/Step1.png)|[<span data-ttu-id="8efc4-134">定义安全和信息保护级别</span><span class="sxs-lookup"><span data-stu-id="8efc4-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

