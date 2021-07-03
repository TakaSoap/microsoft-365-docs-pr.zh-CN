---
title: 为数据隐私法规部署信息保护与Microsoft 365
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
description: 针对数据隐私Microsoft 365如 GDPR 和加州消费者隐私法案 (CCPA) （包括 Microsoft Teams、SharePoint 和电子邮件）配置信息保护。
ms.openlocfilehash: c0ffe7cf850ec6e7ae8c974f983ce43668bf6f30
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287707"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="4bf97-103">为数据隐私法规部署信息保护与Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4bf97-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="4bf97-104">你的组织可能受区域数据隐私法规的约束，这些法规要求你保护、管理和控制存储在 IT 基础结构（包括本地和云）中的个人信息。</span><span class="sxs-lookup"><span data-stu-id="4bf97-104">Your organization may be subject to regional data privacy regulations that require you to protect, manage, and provide rights and control over personal information stored in your IT infrastructure, including both on-premises and in the cloud.</span></span> <span data-ttu-id="4bf97-105">数据隐私条例的最佳示例是欧盟一般数据保护条例 (GDPR) 。</span><span class="sxs-lookup"><span data-stu-id="4bf97-105">The best example of a data privacy regulation is the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="4bf97-106">如果不遵守数据隐私法规，可能会导致大量罚款。</span><span class="sxs-lookup"><span data-stu-id="4bf97-106">Failure to comply with data privacy regulations can result in substantial fines.</span></span>

<span data-ttu-id="4bf97-107">Microsoft 365中数据类型的示例包括 Microsoft Teams 中的聊天会话、Exchange 中的电子邮件以及 SharePoint 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4bf97-107">Examples of the types of data in Microsoft 365 include chat sessions in Microsoft Teams, emails in Exchange, and files in SharePoint and OneDrive.</span></span> <span data-ttu-id="4bf97-108">此解决方案提供有关如何评估风险并采取适当的措施来保护数据中个人数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4bf97-108">This solution provides guidance on how to assess risks and take appropriate action to protect personal data in Microsoft 365.</span></span> <span data-ttu-id="4bf97-109">这包括标识个人信息，以便你可以保护、治理和响应数据隐私事件。</span><span class="sxs-lookup"><span data-stu-id="4bf97-109">This includes identifying  personal information so you can protect, govern, and respond to data privacy incidents.</span></span>

![什么是数据隐私法规的信息保护](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

<span data-ttu-id="4bf97-111">此外，还提供了有关数据隐私Microsoft 365、设备和威胁防护控件的使用的其他信息。</span><span class="sxs-lookup"><span data-stu-id="4bf97-111">Additional information is also provided on the use of Microsoft 365 identity, device, and threat protection controls for your data privacy needs.</span></span>

<span data-ttu-id="4bf97-112">观看此视频以简要了解部署流程。</span><span class="sxs-lookup"><span data-stu-id="4bf97-112">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

<span data-ttu-id="4bf97-113">这些Microsoft 365功能可帮助您满足保护信息的条件。</span><span class="sxs-lookup"><span data-stu-id="4bf97-113">These Microsoft 365 capabilities and features help you meet the criteria for protecting information.</span></span>

| <span data-ttu-id="4bf97-114">功能或特性</span><span class="sxs-lookup"><span data-stu-id="4bf97-114">Capability or feature</span></span> | <span data-ttu-id="4bf97-115">说明</span><span class="sxs-lookup"><span data-stu-id="4bf97-115">Description</span></span> | <span data-ttu-id="4bf97-116">许可</span><span class="sxs-lookup"><span data-stu-id="4bf97-116">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="4bf97-117">合规性管理器</span><span class="sxs-lookup"><span data-stu-id="4bf97-117">Compliance Manager</span></span> | <span data-ttu-id="4bf97-118">管理法规合规性活动，获取当前合规性配置的整体分数，并查找改进建议。</span><span class="sxs-lookup"><span data-stu-id="4bf97-118">Manage regulatory compliance activities, get an overall score of your current compliance configuration, and find recommendations for improvement.</span></span> <span data-ttu-id="4bf97-119">这是工作流中基于工作流的风险评估Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="4bf97-119">This is a workflow-based risk assessment tool in the Microsoft 365 compliance center.</span></span> | <span data-ttu-id="4bf97-120">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="4bf97-120">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="4bf97-121">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4bf97-121">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="4bf97-122">保护你的 Microsoft 365 应用和数据（例如电子邮件、Office 文档和协作工具）免受攻击。</span><span class="sxs-lookup"><span data-stu-id="4bf97-122">Protect your Microsoft 365 apps and data—such as email messages, Office documents, and collaboration tools—from attack.</span></span> | <span data-ttu-id="4bf97-123">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="4bf97-123">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="4bf97-124">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="4bf97-124">Sensitivity labels</span></span> | <span data-ttu-id="4bf97-125">对组织的数据进行分类和保护，而不会妨碍用户的工作效率及其协作能力。</span><span class="sxs-lookup"><span data-stu-id="4bf97-125">Classify and protect your organization's data without hindering the productivity of users and their ability to collaborate.</span></span> <span data-ttu-id="4bf97-126">将具有各种保护级别的标签放在电子邮件、文件或网站上。</span><span class="sxs-lookup"><span data-stu-id="4bf97-126">Place labels with various levels of protection on email, files, or sites.</span></span> | <span data-ttu-id="4bf97-127">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="4bf97-127">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="4bf97-128">数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="4bf97-128">Data Loss Protection (DLP)</span></span> | <span data-ttu-id="4bf97-129">检测、警告和阻止在内部和外部共享包含个人信息的数据存在风险、无意或不当共享。</span><span class="sxs-lookup"><span data-stu-id="4bf97-129">Detect, warn, and block risky, inadvertent, or inappropriate sharing of data containing personal information, both internally and externally.</span></span> | <span data-ttu-id="4bf97-130">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="4bf97-130">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="4bf97-131">数据保留标签和策略</span><span class="sxs-lookup"><span data-stu-id="4bf97-131">Data retention labels and policies</span></span> | <span data-ttu-id="4bf97-132">实施信息治理控制。</span><span class="sxs-lookup"><span data-stu-id="4bf97-132">Implement information governance controls.</span></span> <span data-ttu-id="4bf97-133">这些可能包括确定保留数据 (例如与符合组织策略或数据) 的客户相关的个人数据。</span><span class="sxs-lookup"><span data-stu-id="4bf97-133">These can include determining how long to keep data (such as personal data related to customers) to comply with your organization's policies or data regulations.</span></span> | <span data-ttu-id="4bf97-134">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="4bf97-134">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="4bf97-135">电子邮件加密</span><span class="sxs-lookup"><span data-stu-id="4bf97-135">Email encryption</span></span> | <span data-ttu-id="4bf97-136">通过发送和接收组织内外人员之间的加密电子邮件来保护个人数据。</span><span class="sxs-lookup"><span data-stu-id="4bf97-136">Protect personal data by sending and receiving encrypted email messages between people inside and outside your organization.</span></span> | <span data-ttu-id="4bf97-137">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="4bf97-137">Microsoft 365 E3 and E5</span></span> |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a><span data-ttu-id="4bf97-138">此解决方案中指南的组织</span><span class="sxs-lookup"><span data-stu-id="4bf97-138">Organization of the guidance in this solution</span></span>

<span data-ttu-id="4bf97-139">为了帮助你了解Microsoft 365隐私相关法规的可用工具，本指南分为多个部分。</span><span class="sxs-lookup"><span data-stu-id="4bf97-139">To help you understand the Microsoft 365 tools available to help you meet one or more privacy-related regulations, this guidance is organized into sections.</span></span>

![实施数据隐私法规信息保护的步骤](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

<span data-ttu-id="4bf97-141">这些部分分别对应于此解决方案中的一篇单独的文章。</span><span class="sxs-lookup"><span data-stu-id="4bf97-141">Each of these sections corresponds to a separate article in this solution.</span></span>

> [!NOTE]
> <span data-ttu-id="4bf97-142">如果你已熟悉数据隐私义务，并且正在针对现有计划执行，你可能希望专注于防止、保护、保留和调查指南。</span><span class="sxs-lookup"><span data-stu-id="4bf97-142">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bf97-143">遵循本指南并不一定符合任何数据隐私法规，尤其是考虑在功能上下文之外需要执行的步骤数。</span><span class="sxs-lookup"><span data-stu-id="4bf97-143">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="4bf97-144">你有责任确保合规性，并咨询法律和合规性团队，或者向专门负责合规性的第三方寻求指导和建议。</span><span class="sxs-lookup"><span data-stu-id="4bf97-144">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="4bf97-145">计划：评估数据隐私风险并识别敏感项目</span><span class="sxs-lookup"><span data-stu-id="4bf97-145">Plan: Assess data privacy risks and identify sensitive items</span></span>

<span data-ttu-id="4bf97-146">评估组织所受数据隐私法规和风险是开始实施改进（包括配置 Microsoft 365 中的功能）之前要采取的关键第一Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4bf97-146">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including configuring capabilities in Microsoft 365.</span></span> <span data-ttu-id="4bf97-147">此工作可能包括总体准备情况评估或特定敏感信息类型的标识，这些类型受组织需要遵守的法规控制。</span><span class="sxs-lookup"><span data-stu-id="4bf97-147">This work can include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with.</span></span>

<span data-ttu-id="4bf97-148">有关详细信息，请参阅评估 [数据隐私风险并识别敏感项目](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf97-148">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a><span data-ttu-id="4bf97-149">跟踪：运行风险评估并检查合规性分数</span><span class="sxs-lookup"><span data-stu-id="4bf97-149">Track: Run risk assessments and check your compliance score</span></span>

<span data-ttu-id="4bf97-150">合规性管理器（Microsoft 365 合规中心中提供）内置功能，可跟踪和管理整体改进操作，以及适用于你的多个数据隐私法规的相关改进操作。</span><span class="sxs-lookup"><span data-stu-id="4bf97-150">Compliance Manager, available in the Microsoft 365 compliance center, provides you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations that apply to you.</span></span>

<span data-ttu-id="4bf97-151">可以使用特定于每个法规的内置评估模板，可在其中跟踪选定每个评估模板的行动项，并查看特定法规控制措施，以及将其与特定行动关联。</span><span class="sxs-lookup"><span data-stu-id="4bf97-151">You can use built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="4bf97-152">有关详细信息，请参阅使用 [合规性管理器管理改进操作](information-protection-deploy-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf97-152">For more information, see [Use Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-protect-personal-data"></a><span data-ttu-id="4bf97-153">防止：保护个人数据</span><span class="sxs-lookup"><span data-stu-id="4bf97-153">Prevent: Protect personal data</span></span>

<span data-ttu-id="4bf97-154">Microsoft 365提供可用于帮助遵守数据隐私法规的标识、设备和威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="4bf97-154">Microsoft 365 provides identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span>

<span data-ttu-id="4bf97-155">有关详细信息，请参阅对数据隐私法规使用标识 [、设备和威胁防护](information-protection-deploy-identity-device-threat.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf97-155">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="4bf97-156">本文简要介绍了在这些方面通常要求的数据隐私法规，并提供了相关 Microsoft 365 解决方案列表，并提供了可帮助您满足任何实施要求的更多信息的链接。</span><span class="sxs-lookup"><span data-stu-id="4bf97-156">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span>

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="4bf97-157">保护受数据隐私条例保护的信息</span><span class="sxs-lookup"><span data-stu-id="4bf97-157">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="4bf97-158">数据隐私法规规定可在你的环境中使用大量个人信息保护控制措施，包括 GDPR 示例集、加州消费者保护法案 (CCPA) 、HIPAA-HITECH (美国医疗保健隐私法案) 和巴西数据保护法案 (LGPD) 中用于保护信息的 40 多个控制措施。</span><span class="sxs-lookup"><span data-stu-id="4bf97-158">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than 40 controls for protecting information across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="4bf97-159">有关详细信息，请参阅 [保护受组织中数据隐私法规的约束的信息](information-protection-deploy-protect-information.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf97-159">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="4bf97-160">本文规定了可用于满足组织中数据隐私的信息保护需求的主要控制方案。</span><span class="sxs-lookup"><span data-stu-id="4bf97-160">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="4bf97-161">保留：管理受数据隐私法规约束的信息</span><span class="sxs-lookup"><span data-stu-id="4bf97-161">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="4bf97-162">数据隐私法规要求在环境中可以使用的个人信息治理控制措施，包括 GDPR、CCPA、HIPAA-HITECH 和 LGPD 示例集内四种数据隐私法规中的超过 24 项控制措施。</span><span class="sxs-lookup"><span data-stu-id="4bf97-162">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than 24 controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="4bf97-163">有关详细信息，请参阅 [在组织中受数据隐私法规约束的治理信息](information-protection-deploy-govern.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf97-163">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="4bf97-164">虽然数据隐私法规对于信息治理（如有目的的保留、删除和存档）而言是模糊的，但本文规定了主要控制方案，您可以使用这些方案满足组织对数据隐私的信息管理 &mdash; &mdash; 需求。</span><span class="sxs-lookup"><span data-stu-id="4bf97-164">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a><span data-ttu-id="4bf97-165">调查：监视、调查和响应数据隐私事件</span><span class="sxs-lookup"><span data-stu-id="4bf97-165">Investigate: Monitor, investigate, and respond to data privacy incidents</span></span>

<span data-ttu-id="4bf97-166">在Microsoft 365相关功能时，可以使用一些功能来帮助你监视、调查和响应组织的数据隐私事件。</span><span class="sxs-lookup"><span data-stu-id="4bf97-166">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span>

<span data-ttu-id="4bf97-167">拥有使用这些功能的流程、过程和其他文档对于证明监管机构的合规性非常重要。</span><span class="sxs-lookup"><span data-stu-id="4bf97-167">Having processes, procedures, and other documentation for using these features can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="4bf97-168">有关详细信息，请参阅 [监视和响应组织中数据隐私事件](information-protection-deploy-monitor-respond.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf97-168">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>

## <a name="training-for-administrators"></a><span data-ttu-id="4bf97-169">管理员培训</span><span class="sxs-lookup"><span data-stu-id="4bf97-169">Training for administrators</span></span>

<span data-ttu-id="4bf97-170">Microsoft Learn 中的这些培训模块可帮助你了解对信息保护非常重要的功能。</span><span class="sxs-lookup"><span data-stu-id="4bf97-170">These training modules from Microsoft Learn can help you learn about how capabilities that are important for information protection.</span></span>


#### <a name="information-protection"></a><span data-ttu-id="4bf97-171">信息保护</span><span class="sxs-lookup"><span data-stu-id="4bf97-171">Information protection</span></span>

|<span data-ttu-id="4bf97-172">培训：</span><span class="sxs-lookup"><span data-stu-id="4bf97-172">Training:</span></span>|<span data-ttu-id="4bf97-173">使用 Microsoft 365 保护企业信息</span><span class="sxs-lookup"><span data-stu-id="4bf97-173">Protect enterprise information with Microsoft 365</span></span>|
|:---|:---|
|![Teams信息保护培训图标](../media/protect-enterprise-information-microsoft-365.svg)|<span data-ttu-id="4bf97-175">保护和保证组织的信息安全以往任何时候都更具挑战性。</span><span class="sxs-lookup"><span data-stu-id="4bf97-175">Protecting and securing your organization's information is more challenging than ever.</span></span> <span data-ttu-id="4bf97-176">使用 Microsoft 365 保护企业信息学习路径介绍如何防止敏感信息被意外过度分享或滥用，如何发现和分类数据，如何使用敏感度标签保护数据，以及如何同时监视和分析敏感信息以防信息丢失。</span><span class="sxs-lookup"><span data-stu-id="4bf97-176">The Protect enterprise information with Microsoft 365 learning path discusses how to protect your sensitive information from accidental oversharing or misuse, how to discover and classify data, how to protect it with sensitivity labels, and how to both monitor and analyze your sensitive information to protect against its loss.</span></span> <span data-ttu-id="4bf97-177">此学习路径可帮助你准备Microsoft 365：安全管理员关联Microsoft 365认证：Enterprise专家认证。</span><span class="sxs-lookup"><span data-stu-id="4bf97-177">This learning path can help you prepare for the Microsoft 365 Certified: Security Administrator Associate and Microsoft 365 Certified: Enterprise Administration Expert certifications..</span></span><br><br><span data-ttu-id="4bf97-178">1 小时 - Learning 路径 - 5 个模块</span><span class="sxs-lookup"><span data-stu-id="4bf97-178">1 hr - Learning Path - 5 Modules</span></span>|

> [!div class="nextstepaction"]
> [<span data-ttu-id="4bf97-179">开始></span><span class="sxs-lookup"><span data-stu-id="4bf97-179">Start ></span></span>](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a><span data-ttu-id="4bf97-180">身份和访问控制</span><span class="sxs-lookup"><span data-stu-id="4bf97-180">Identity and access</span></span>

|<span data-ttu-id="4bf97-181">培训：</span><span class="sxs-lookup"><span data-stu-id="4bf97-181">Training:</span></span>|<span data-ttu-id="4bf97-182">使用 Azure Active Directory 提供标识和访问保护</span><span class="sxs-lookup"><span data-stu-id="4bf97-182">Protect identity and access with Azure Active Directory</span></span>|
|:---|:---|
|![标识和访问培训图标](../media/protect-identity-and-access-with-microsoft-365.svg)|<span data-ttu-id="4bf97-184">标识和访问学习路径涵盖了最新的身份和访问技术、用于加强身份验证的工具以及组织内有关身份保护的指南。</span><span class="sxs-lookup"><span data-stu-id="4bf97-184">The Identity and Access learning path covers the latest identity and access technologies, tools for strengthening authentication, and guidance on identity protection within your organization.</span></span> <span data-ttu-id="4bf97-185">Microsoft 访问和身份技术使你能够保护组织的身份（无论是本地身份还是在云中），并使用户能够从任何位置安全地工作。</span><span class="sxs-lookup"><span data-stu-id="4bf97-185">Microsoft access and identity technologies enable you to secure your organization’s identity, whether it is on-premises or in the cloud, and empower your users to work securely from any location.</span></span> <span data-ttu-id="4bf97-186">此学习途径可帮助你准备 Microsoft 365 认证：安全管理员关联与Microsoft 365 认证：企业管理专家认证。</span><span class="sxs-lookup"><span data-stu-id="4bf97-186">This learning path can help you prepare for the Microsoft 365 Certified: Security Administrator Associate and Microsoft 365 Certified: Enterprise Administration Expert certifications.</span></span><br><br><span data-ttu-id="4bf97-187">2 小时 52 分钟 - Learning 路径 - 6 个模块</span><span class="sxs-lookup"><span data-stu-id="4bf97-187">2 hr 52 min - Learning Path - 6 Modules</span></span>|

> [!div class="nextstepaction"]
> [<span data-ttu-id="4bf97-188">开始></span><span class="sxs-lookup"><span data-stu-id="4bf97-188">Start ></span></span>](/learn/modules/m365-identity-overview/introduction/)