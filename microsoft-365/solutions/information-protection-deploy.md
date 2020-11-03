---
title: 为 Microsoft 365 中的数据隐私法规部署信息保护
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: 配置安全和服务基础结构，以保护您的信息并遵守数据隐私法规。
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842292"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="7da54-103">为 Microsoft 365 中的数据隐私法规部署信息保护</span><span class="sxs-lookup"><span data-stu-id="7da54-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="7da54-104">您的组织可能受区域数据隐私法规的约束，这些法规要求您保护、管理和提供对存储在 IT 基础结构中的个人信息（包括内部部署和云中的个人信息）的权限和控制。</span><span class="sxs-lookup"><span data-stu-id="7da54-104">Your organization may be subject to regional data privacy regulations that require you to protect, manage, and provide rights and control over personal information stored in your IT infrastructure, including both on-premises and in the cloud.</span></span> <span data-ttu-id="7da54-105">数据隐私法规的最佳示例是欧盟的一般数据保护法规 (GDPR) 。</span><span class="sxs-lookup"><span data-stu-id="7da54-105">The best example of a data privacy regulation is the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="7da54-106">如果不遵守数据隐私法规，可能会导致巨额罚款。</span><span class="sxs-lookup"><span data-stu-id="7da54-106">Failure to comply with data privacy regulations can result in substantial fines.</span></span>

<span data-ttu-id="7da54-107">Microsoft 365 中的数据类型示例包括 Microsoft 团队中的聊天会话、Exchange 中的电子邮件以及 SharePoint 和 OneDrive 中的文件。</span><span class="sxs-lookup"><span data-stu-id="7da54-107">Examples of the types of data in Microsoft 365 include chat sessions in Microsoft Teams, emails in Exchange, and files in SharePoint and OneDrive.</span></span> <span data-ttu-id="7da54-108">此解决方案提供了有关如何评估风险和标识信息、保护、管理和响应 Microsoft 365 服务中存储的适用于数据隐私法规的个人数据的数据隐私事件的指南。</span><span class="sxs-lookup"><span data-stu-id="7da54-108">This solution provides guidance on how to assess risks and identify information, protect, govern, and respond to data privacy incidents for personal data stored in Microsoft 365 services that is subject to data privacy regulations.</span></span>

![什么是针对数据隐私法规的信息保护](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

<span data-ttu-id="7da54-110">此外，还提供了针对你的数据隐私需求使用 Microsoft 365 标识、设备和威胁防护控制的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7da54-110">Additional information is also provided on the use of Microsoft 365 identity, device, and threat protection controls for your data privacy needs.</span></span> 

<span data-ttu-id="7da54-111">若要符合保护信息以实现与数据隐私法规遵从性的标准，请使用以下 Microsoft 365 功能和功能。</span><span class="sxs-lookup"><span data-stu-id="7da54-111">To meet the criteria for protecting information for compliance with data privacy regulations, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="7da54-112">功能或特性</span><span class="sxs-lookup"><span data-stu-id="7da54-112">Capability or feature</span></span> | <span data-ttu-id="7da54-113">说明</span><span class="sxs-lookup"><span data-stu-id="7da54-113">Description</span></span> | <span data-ttu-id="7da54-114">许可</span><span class="sxs-lookup"><span data-stu-id="7da54-114">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="7da54-115">合规性管理器</span><span class="sxs-lookup"><span data-stu-id="7da54-115">Compliance Manager</span></span> | <span data-ttu-id="7da54-116">管理法规遵从性活动，获取当前合规性配置的整体分数，并在 Microsoft 365 合规性中心中查找基于工作流的风险评估工具改进的建议。</span><span class="sxs-lookup"><span data-stu-id="7da54-116">Manage regulatory compliance activities, get an overall score of your current compliance configuration, and find recommendations for improvement in this workflow-based risk assessment tool in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="7da54-117">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="7da54-117">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="7da54-118">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7da54-118">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="7da54-119">保护你的 Microsoft 365 应用和数据（例如电子邮件、Office 文档和协作工具）免受攻击。</span><span class="sxs-lookup"><span data-stu-id="7da54-119">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> | <span data-ttu-id="7da54-120">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="7da54-120">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="7da54-121">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="7da54-121">Sensitivity labels</span></span> | <span data-ttu-id="7da54-122">通过在电子邮件、文件或站点上放置具有不同保护级别的标签，可以在不影响用户工作效率和协作能力的情况下对组织的数据进行分类和保护。</span><span class="sxs-lookup"><span data-stu-id="7da54-122">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate by placing labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="7da54-123">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="7da54-123">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="7da54-124">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="7da54-124">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="7da54-125">在内部和外部检测、警告和阻止有风险的、无意或不适当的共享，例如包含个人信息的数据共享。</span><span class="sxs-lookup"><span data-stu-id="7da54-125">Detect, warn, and block risky, inadvertent, or inappropriate sharing, such as sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="7da54-126">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="7da54-126">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="7da54-127">数据保留标签和策略</span><span class="sxs-lookup"><span data-stu-id="7da54-127">Data retention labels and policies</span></span> | <span data-ttu-id="7da54-128">实施信息治理控制，例如将数据保留多长时间以及对客户个人数据存储的要求，以符合组织的政策或数据法规。</span><span class="sxs-lookup"><span data-stu-id="7da54-128">Implement information governance controls, such as how long to keep data and requirements on the storage of personal data on customers, to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="7da54-129">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="7da54-129">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="7da54-130">电子邮件加密</span><span class="sxs-lookup"><span data-stu-id="7da54-130">Email encryption</span></span> | <span data-ttu-id="7da54-131">在组织内部和外部的人员之间发送和接收加密的电子邮件，其中包含受监管的数据，例如客户的个人数据。</span><span class="sxs-lookup"><span data-stu-id="7da54-131">Send and receive encrypted email messages between people inside and outside your organization that contains regulated data, such as personal data on customers.</span></span> | <span data-ttu-id="7da54-132">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="7da54-132">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a><span data-ttu-id="7da54-133">本解决方案中指南的组织结构</span><span class="sxs-lookup"><span data-stu-id="7da54-133">Organization of the guidance in this solution</span></span>

<span data-ttu-id="7da54-134">为了帮助您了解可用于识别、管理、控制和监视个人数据受一种或多种与隐私相关的法规约束的 Microsoft 365 工具，本指南分为几节。</span><span class="sxs-lookup"><span data-stu-id="7da54-134">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![对数据隐私法规实施信息保护的步骤](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

<span data-ttu-id="7da54-136">这两个部分分别对应于本解决方案中的一篇文章。</span><span class="sxs-lookup"><span data-stu-id="7da54-136">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="7da54-137">如果您已熟悉您的数据隐私义务并正针对现有计划执行，您可能希望将重点放在阻止、保护、保留和调查指南中。</span><span class="sxs-lookup"><span data-stu-id="7da54-137">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="7da54-138">遵循本指南并不一定会使您符合任何数据隐私法规，尤其要考虑功能上下文之外所需的步骤数。</span><span class="sxs-lookup"><span data-stu-id="7da54-138">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="7da54-139">您有责任确保您的合规性并咨询您的法律和合规性团队，或者从第三方（具体符合合规性）中寻求指导和建议。</span><span class="sxs-lookup"><span data-stu-id="7da54-139">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="7da54-140">Plan：评估数据隐私风险并确定敏感项目</span><span class="sxs-lookup"><span data-stu-id="7da54-140">Plan: Assess data privacy risks and identify sensitive items</span></span>

<span data-ttu-id="7da54-141">评估您的组织所依赖的数据隐私法规和风险是开始实施改进（包括通过 Microsoft 365 配置实现的）之前需要执行的重要第一步。</span><span class="sxs-lookup"><span data-stu-id="7da54-141">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="7da54-142">这可能包括您的组织需要遵守的管理法规控制和在 Microsoft 365 环境中出现的特定敏感信息类型的总体准备情况评估或标识。</span><span class="sxs-lookup"><span data-stu-id="7da54-142">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="7da54-143">有关详细信息，请参阅 [评估数据隐私风险和标识敏感项目](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="7da54-143">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a><span data-ttu-id="7da54-144">跟踪：运行风险评估并检查合规性分数</span><span class="sxs-lookup"><span data-stu-id="7da54-144">Track: Run risk assessments and check your compliance score</span></span>

<span data-ttu-id="7da54-145">合规性管理器（可在 Microsoft 365 合规性中心中提供）为您提供了一个内置的功能，用于跟踪和管理整体改进操作以及与适用于您的多个数据隐私法规相关的问题。</span><span class="sxs-lookup"><span data-stu-id="7da54-145">Compliance Manager, available in the Microsoft 365 compliance center, provides you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations that apply to you.</span></span>

<span data-ttu-id="7da54-146">利用特定于每个法规的内置评估模板，您可以在其中跟踪选定的每个评估模板的操作项，并查看特定的规章控件，并将它们与特定操作相关联。</span><span class="sxs-lookup"><span data-stu-id="7da54-146">Leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="7da54-147">有关详细信息，请参阅 [Use 合规性管理器管理改进操作](information-protection-deploy-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="7da54-147">For more information, see [Use Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-protect-personal-data"></a><span data-ttu-id="7da54-148">阻止：保护个人数据</span><span class="sxs-lookup"><span data-stu-id="7da54-148">Prevent: Protect personal data</span></span>

<span data-ttu-id="7da54-149">Microsoft 365 提供了大量标识、设备和威胁防护功能，可用于帮助遵守数据隐私法规遵从性。</span><span class="sxs-lookup"><span data-stu-id="7da54-149">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="7da54-150">有关详细信息，请参阅 [对数据隐私法规使用标识、设备和威胁防护](information-protection-deploy-identity-device-threat.md)。</span><span class="sxs-lookup"><span data-stu-id="7da54-150">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="7da54-151">本文简要介绍了在这些领域中通常要调用的数据隐私法规，并提供了相关 Microsoft 365 解决方案的列表，并提供了可帮助您满足任何实现要求的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="7da54-151">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="7da54-152">保护受数据隐私法规制约的信息</span><span class="sxs-lookup"><span data-stu-id="7da54-152">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="7da54-153">数据隐私规章规定了许多可在您的环境中使用的个人信息保护控件，其中包括40个在 GDPR 的示例集（加利福尼亚州消费者防护法案 (CCPA) 、HIPAA-高科技 (美国卫生保健隐私法案) 以及巴西数据保护法案 (LGPD) 中的四个数据隐私规章中保护信息控制。</span><span class="sxs-lookup"><span data-stu-id="7da54-153">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="7da54-154">有关详细信息，请参阅 [保护受组织中数据隐私法规制约的信息](information-protection-deploy-protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="7da54-154">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="7da54-155">本文介绍了可用于为组织中的数据隐私提供寻址信息保护需求的主要控件方案。</span><span class="sxs-lookup"><span data-stu-id="7da54-155">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="7da54-156">保留：管理受数据隐私法规约束的信息</span><span class="sxs-lookup"><span data-stu-id="7da54-156">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="7da54-157">数据隐私管理法规要求在您的环境中可采用的个人信息治理控制措施，包括 GDPR、CCPA、HIPAA-高科技和 LGPD 的示例集中四个数据隐私法规的四个以上的控制措施。</span><span class="sxs-lookup"><span data-stu-id="7da54-157">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="7da54-158">有关详细信息，请参阅 [管理组织中的数据隐私法规所依据的信息](information-protection-deploy-govern.md)。</span><span class="sxs-lookup"><span data-stu-id="7da54-158">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="7da54-159">尽管在故意保留、删除和存档等信息管理方面，数据保密法规可能不 &mdash; 明确，但 &mdash; 本文还介绍了主要控件方案，您可以对组织中的数据隐私使用地址信息治理需求。</span><span class="sxs-lookup"><span data-stu-id="7da54-159">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a><span data-ttu-id="7da54-160">调查：监控、调查和响应数据隐私事件</span><span class="sxs-lookup"><span data-stu-id="7da54-160">Investigate: Monitor, investigate, and respond to data privacy incidents</span></span>

<span data-ttu-id="7da54-161">有 Microsoft 365 功能可帮助您在您的组织中监视、调查数据隐私事件并在 operationalize 相关功能时对其做出响应。</span><span class="sxs-lookup"><span data-stu-id="7da54-161">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="7da54-162">对于每个以上的过程、过程和其他文档来说，向管理法规遵守合规性可能非常重要。</span><span class="sxs-lookup"><span data-stu-id="7da54-162">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="7da54-163">有关详细信息，请参阅 [监视和响应组织中的数据隐私事件](information-protection-deploy-monitor-respond.md)。</span><span class="sxs-lookup"><span data-stu-id="7da54-163">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
