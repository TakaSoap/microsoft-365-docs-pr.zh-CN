---
title: 为 Microsoft 365 中的数据隐私法规部署信息保护
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 配置安全和服务基础结构，以保护您的信息并遵守数据隐私法规。
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695100"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="590ed-103">为 Microsoft 365 中的数据隐私法规部署信息保护</span><span class="sxs-lookup"><span data-stu-id="590ed-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="590ed-104">此解决方案提供了有关如何在 Microsoft 365 服务中规划和保护存储在 Microsoft 服务中的个人数据的指南，并可能会遵守数据隐私法规（如欧盟的常规数据保护法规（GDPR））。</span><span class="sxs-lookup"><span data-stu-id="590ed-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="590ed-105">此解决方案重点介绍了适用的 Microsoft 信息保护和合规性功能、Microsoft 合规性分数和评估工具，可帮助您了解数据。</span><span class="sxs-lookup"><span data-stu-id="590ed-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="590ed-106">此外，还提供了有关您的数据隐私需求的 Microsoft 标识、设备和威胁防护控制以及数据事件发现和响应工具的其他信息。</span><span class="sxs-lookup"><span data-stu-id="590ed-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="590ed-107">本指南资料的组织结构</span><span class="sxs-lookup"><span data-stu-id="590ed-107">Organization of this guidance material</span></span>

<span data-ttu-id="590ed-108">为了帮助您了解可用于识别、管理、控制和监视个人数据受一种或多种与隐私相关的法规约束的 Microsoft 365 工具，本指南分为几节。</span><span class="sxs-lookup"><span data-stu-id="590ed-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![为数据隐私法规部署信息保护](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="590ed-110">这两个部分分别对应于本解决方案中的一篇文章。</span><span class="sxs-lookup"><span data-stu-id="590ed-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="590ed-111">如果您已熟悉您的数据隐私义务并正针对现有计划执行，您可能希望将重点放在阻止、保护、保留和调查指南中。</span><span class="sxs-lookup"><span data-stu-id="590ed-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="590ed-112">遵循本指南并不一定会使您符合任何数据隐私法规，尤其要考虑功能上下文之外所需的步骤数。</span><span class="sxs-lookup"><span data-stu-id="590ed-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="590ed-113">您有责任确保您的合规性并咨询您的法律和合规性团队，或者从第三方（具体符合合规性）中寻求指导和建议。</span><span class="sxs-lookup"><span data-stu-id="590ed-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="590ed-114">Plan：评估数据隐私风险并确定敏感项目</span><span class="sxs-lookup"><span data-stu-id="590ed-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="590ed-115">评估您的组织所依赖的数据隐私法规和风险是开始实施改进（包括通过 Microsoft 365 配置实现的）之前需要执行的重要第一步。</span><span class="sxs-lookup"><span data-stu-id="590ed-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="590ed-116">这可能包括您的组织需要遵守的管理法规控制和在 Microsoft 365 环境中出现的特定敏感信息类型的总体准备情况评估或标识。</span><span class="sxs-lookup"><span data-stu-id="590ed-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="590ed-117">有关详细信息，请参阅[评估数据隐私风险和标识敏感项目](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="590ed-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="590ed-118">跟踪：使用合规性分数和合规性管理器</span><span class="sxs-lookup"><span data-stu-id="590ed-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="590ed-119">合规性分数和合规性管理器提供了 Microsoft 365 合规性管理中心和服务信任门户中提供的一组集成工具。</span><span class="sxs-lookup"><span data-stu-id="590ed-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="590ed-120">此外，这些工具还提供了内置的功能，可以跟踪和管理整体以及与您所受到的多个数据隐私保护法规相关的整体改进措施。</span><span class="sxs-lookup"><span data-stu-id="590ed-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="590ed-121">这些工具还允许您利用特定于每个法规的内置评估模板，您可以在其中跟踪选定的每个评估模板的操作项，并查看特定的规章控件，并将它们与特定操作相关联。</span><span class="sxs-lookup"><span data-stu-id="590ed-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="590ed-122">有关详细信息，请参阅[使用合规性分数和合规性管理器管理改进操作](information-protection-deploy-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="590ed-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="590ed-123">阻止：对数据隐私法规使用标识、设备和威胁防护</span><span class="sxs-lookup"><span data-stu-id="590ed-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="590ed-124">Microsoft 365 提供了大量标识、设备和威胁防护功能，可用于帮助遵守数据隐私法规遵从性。</span><span class="sxs-lookup"><span data-stu-id="590ed-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="590ed-125">有关详细信息，请参阅[对数据隐私法规使用标识、设备和威胁防护](information-protection-deploy-identity-device-threat.md)。</span><span class="sxs-lookup"><span data-stu-id="590ed-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="590ed-126">本文简要介绍了在这些领域中通常要调用的数据隐私法规，并提供了相关 Microsoft 365 解决方案的列表，并提供了可帮助您满足任何实现要求的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="590ed-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="590ed-127">保护受数据隐私法规制约的信息</span><span class="sxs-lookup"><span data-stu-id="590ed-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="590ed-128">数据隐私规章规定了许多可在您的环境中使用的个人信息保护控件，其中包括40个在 GDPR、加利福尼亚州消费者保护法（CCPA）、HIPAA-高科技（美国卫生保健隐私保护法案）和巴西数据保护法案（LGPD）中的四个数据隐私规章中保护信息控制。</span><span class="sxs-lookup"><span data-stu-id="590ed-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="590ed-129">有关详细信息，请参阅[保护受组织中数据隐私法规制约的信息](information-protection-deploy-protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="590ed-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="590ed-130">本文介绍了可用于为组织中的数据隐私提供寻址信息保护需求的主要控件方案。</span><span class="sxs-lookup"><span data-stu-id="590ed-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="590ed-131">保留：管理受数据隐私法规约束的信息</span><span class="sxs-lookup"><span data-stu-id="590ed-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="590ed-132">数据隐私管理法规要求在您的环境中可采用的个人信息治理控制措施，包括 GDPR、CCPA、HIPAA-高科技和 LGPD 的示例集中四个数据隐私法规的四个以上的控制措施。</span><span class="sxs-lookup"><span data-stu-id="590ed-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="590ed-133">有关详细信息，请参阅[管理组织中的数据隐私法规所依据的信息](information-protection-deploy-govern.md)。</span><span class="sxs-lookup"><span data-stu-id="590ed-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="590ed-134">尽管在故意保留、删除和存档等信息管理方面，数据保密法规可能不 &mdash; 明确，但 &mdash; 本文还介绍了主要控件方案，您可以对组织中的数据隐私使用地址信息治理需求。</span><span class="sxs-lookup"><span data-stu-id="590ed-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="590ed-135">调查：监视和响应数据隐私法规的主题</span><span class="sxs-lookup"><span data-stu-id="590ed-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="590ed-136">有 Microsoft 365 功能可帮助您在您的组织中监视、调查数据隐私事件并在 operationalize 相关功能时对其做出响应。</span><span class="sxs-lookup"><span data-stu-id="590ed-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="590ed-137">对于每个以上的过程、过程和其他文档来说，向管理法规遵守合规性可能非常重要。</span><span class="sxs-lookup"><span data-stu-id="590ed-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="590ed-138">有关详细信息，请参阅[监视和响应组织中的数据隐私事件](information-protection-deploy-monitor-respond.md)。</span><span class="sxs-lookup"><span data-stu-id="590ed-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
