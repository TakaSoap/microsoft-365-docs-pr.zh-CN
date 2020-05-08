---
title: 合规性产品/服务 - 云安全联盟 (CSA) STAR 自我评估
description: Microsoft STAR 自我评估详细阐述了云服务如何满足云安全联盟的要求。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 03f80deca7ba9a65dd47ac814d15eb5a8f764f10
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066445"
---
# <a name="cloud-security-alliance-csa-star-self-assessment"></a><span data-ttu-id="10273-104">云安全联盟 (CSA) STAR 自我评估</span><span class="sxs-lookup"><span data-stu-id="10273-104">Cloud Security Alliance (CSA) STAR self-assessment</span></span>

## <a name="csa-star-self-assessment-overview"></a><span data-ttu-id="10273-105">CSA STAR 自我评估概述</span><span class="sxs-lookup"><span data-stu-id="10273-105">CSA STAR self-assessment overview</span></span>

<span data-ttu-id="10273-106">云安全联盟 (CSA) 是一家非营利性组织，它由行业从业人员、公司和其他重要利益干系人组成联盟进行领导。</span><span class="sxs-lookup"><span data-stu-id="10273-106">The Cloud Security Alliance (CSA) is a nonprofit organization led by a broad coalition of industry practitioners, corporations, and other important stakeholders.</span></span> <span data-ttu-id="10273-107">该联盟致力于确定可帮助确保云计算环境更加安全的最佳做法，同时帮助潜在的云客户在将其 IT 运营过渡到云端时做出知情决策。</span><span class="sxs-lookup"><span data-stu-id="10273-107">It is dedicated to defining best practices to help ensure a more secure cloud computing environment, and to helping potential cloud customers make informed decisions when transitioning their IT operations to the cloud.</span></span>  
  
<span data-ttu-id="10273-108">2010 年，CSA 发布了一套用于评估云 IT 运营的工具：CSA Governance、Risk Management 和 Compliance (GRC) Stack。</span><span class="sxs-lookup"><span data-stu-id="10273-108">In 2010, the CSA published a suite of tools to assess cloud IT operations: the CSA Governance, Risk Management, and Compliance (GRC) Stack.</span></span> <span data-ttu-id="10273-109">其目的在于帮助云客户对云服务提供商 (CSP) 遵循行业最佳做法和标准以及遵守法规的情况进行评估。</span><span class="sxs-lookup"><span data-stu-id="10273-109">It was designed to help cloud customers assess how cloud service providers (CSPs) follow industry best practices and standards and comply with regulations.</span></span>  
  
<span data-ttu-id="10273-110">2013 年，CSA 和英国国家标准协会启动了安全、信任及保证注册表 (STAR)，这是一个可公开访问的免费注册表，CSP 可在其中发布他们与 CSA 相关的评估。</span><span class="sxs-lookup"><span data-stu-id="10273-110">In 2013, the CSA and the British Standards Institution launched the Security, Trust & Assurance Registry (STAR), a free, publicly accessible registry in which CSPs can publish their CSA-related assessments.</span></span>  
  
<span data-ttu-id="10273-111">CSA STAR 基于 CSA GRC Stack 的两大关键组成部分：</span><span class="sxs-lookup"><span data-stu-id="10273-111">CSA STAR is based on two key components of the CSA GRC Stack:</span></span>

- <span data-ttu-id="10273-112">云控制矩阵 (CCM)：一个涵盖 16 个域的基本安全原则的控制措施框架，它可帮助云客户对 CSP 的整体安全风险进行评估。</span><span class="sxs-lookup"><span data-stu-id="10273-112">Cloud Controls Matrix (CCM): a controls framework covering fundamental security principles across 16 domains to help cloud customers assess the overall security risk of a CSP.</span></span>
- <span data-ttu-id="10273-113">共识评估倡议调查表 (CAIQ)：一份根据 CCM 制定的调查表，其中有客户或云审计师可能想要要求 CSP 根据 CSA 最佳做法对其合规性进行评估的 140 多个问题。</span><span class="sxs-lookup"><span data-stu-id="10273-113">The Consensus Assessments Initiative Questionnaire (CAIQ): a set of more than 140 questions based on the CCM that a customer or cloud auditor may want to ask of CSPs to assess their compliance with CSA best practices.</span></span>

<span data-ttu-id="10273-114">STAR 提供三种级别的保障；CSA-STAR 自我评估是第 1 级别的入门级服务，它免费提供并向所有 CSP 公开。</span><span class="sxs-lookup"><span data-stu-id="10273-114">STAR provides three levels of assurance; CSA-STAR Self-Assessment is the introductory offering at Level 1, which is free and open to all CSPs.</span></span> <span data-ttu-id="10273-115">在保障堆栈中更深一步，第 2 级别的 STAR 计划涉及到第三方基于评估的认证，第 3 级别涉及到基于持续监视授予的认证。</span><span class="sxs-lookup"><span data-stu-id="10273-115">Going further up the assurance stack, Level 2 of the STAR program involves third-party assessment-based certifications, and Level 3 involves certifications based on continuous monitoring.</span></span>

## <a name="microsoft-and-csa-star-self-assessment"></a><span data-ttu-id="10273-116">Microsoft 与 CSA STAR 自我评估</span><span class="sxs-lookup"><span data-stu-id="10273-116">Microsoft and CSA STAR self-assessment</span></span>

<span data-ttu-id="10273-117">作为 STAR 自我评估的一部分，CSP 可提交两种不同类型的文档来指出其遵守 CSA 最佳做法，它们分别是填好的 CAIQ 以及一份记录是否符合 CCM 的报告。</span><span class="sxs-lookup"><span data-stu-id="10273-117">As part of the STAR Self-Assessment, CSPs can submit two different types of documents to indicate their compliance with CSA best practices: a completed CAIQ, or a report documenting compliance with CCM.</span></span> <span data-ttu-id="10273-118">在 CSA STAR 自我评估方面，Microsoft 对 Microsoft Azure 发布了 CAIQ 调查表和基于 CCM 的报告，对 Microsoft Dynamics 365 和 Microsoft Office 365 发布了基于 CCM 的报告。</span><span class="sxs-lookup"><span data-stu-id="10273-118">For the CSA STAR Self-Assessment, Microsoft publishes both a CAIQ and a CCM-based report for Microsoft Azure, and CCM-based reports for Microsoft Dynamics 365 and Microsoft Office 365.</span></span>  

<span data-ttu-id="10273-119">了解如何在我们的 Azure 安全性和合规性蓝图的帮助下加快 CSA STAR 自我评估部署：[下载关于 CSA 共识评估的 Azure 答复](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)</span><span class="sxs-lookup"><span data-stu-id="10273-119">Learn how to accelerate your CSA STAR Self-Assessment deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the CSA Consensus Assessments](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="10273-120">Microsoft 范围内的云服务</span><span class="sxs-lookup"><span data-stu-id="10273-120">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="10273-121">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="10273-121">Azure and Azure Government</span></span>](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [<span data-ttu-id="10273-122">Dynamics 365 CSA STAR 自我评估</span><span class="sxs-lookup"><span data-stu-id="10273-122">Dynamics 365 CSA STAR Self-Assessment</span></span>](https://cloudsecurityalliance.org/star/registry/microsoft/)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="10273-123">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="10273-123">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="10273-124">针对信息请求的 Azure 标准答复</span><span class="sxs-lookup"><span data-stu-id="10273-124">Azure standard response for request for information</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7ca8423-1bc5-4be0-bff8-b6056f87c134&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)
- [<span data-ttu-id="10273-125">Azure 云安全联盟 CAIQ</span><span class="sxs-lookup"><span data-stu-id="10273-125">Azure Cloud Security Alliance CAIQ</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a966a424-ecfd-4de2-9739-b08aee2d3ca0&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)
- [<span data-ttu-id="10273-126">针对 CSA CAIQ v3.0.1 的 Azure 答复</span><span class="sxs-lookup"><span data-stu-id="10273-126">Azure responses to the CSA CAIQ v3.0.1</span></span>](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)

## <a name="frequently-asked-questions"></a><span data-ttu-id="10273-127">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="10273-127">Frequently asked questions</span></span>

<span data-ttu-id="10273-128">**CSA CCM 向哪些行业标准看齐？**</span><span class="sxs-lookup"><span data-stu-id="10273-128">**Which industry standards does the CSA CCM align with?**</span></span>

<span data-ttu-id="10273-129">CCM 与行业接受的安全标准、法规和控制措施框架相对应，例如 ISO 27001、PCI DSS、HIPAA、AICPA SOC 2、NERC CIP、FedRAMP 和 NIST 等等。</span><span class="sxs-lookup"><span data-stu-id="10273-129">The CCM corresponds to industry-accepted security standards, regulations, and control frameworks such as ISO 27001, PCI DSS, HIPAA, AICPA SOC 2, NERC CIP, FedRAMP, NIST, and many more.</span></span> <span data-ttu-id="10273-130">有关最新列表，请访问 [CSA 网站](https://cloudsecurityalliance.org/)。</span><span class="sxs-lookup"><span data-stu-id="10273-130">For the most current list, visit the [CSA website](https://cloudsecurityalliance.org/).</span></span>

<span data-ttu-id="10273-131">**CSA STAR 自我评估为什么很重要？**</span><span class="sxs-lookup"><span data-stu-id="10273-131">**Why is the CSA STAR Self-Assessment important?**</span></span>

<span data-ttu-id="10273-132">它让 CSP 能够在记录与 CSA 发布的最佳做法的合规情况方面保证公开透明操作。</span><span class="sxs-lookup"><span data-stu-id="10273-132">It enables CSPs to document compliance with CSA published best practices in a transparent manner.</span></span> <span data-ttu-id="10273-133">自我评估公开提供，从而可帮助云客户了解 CSP 的安全实践并采用同一基线对各个 CSP 进行对比。</span><span class="sxs-lookup"><span data-stu-id="10273-133">Self-assessment reports are publicly available, thereby helping cloud customers gain visibility into the security practices of CSPs, and compare various CSPs using the same baseline.</span></span>

<span data-ttu-id="10273-134">**哪些 CSA STAR 保障级别配备有 Microsoft 商业云服务？**</span><span class="sxs-lookup"><span data-stu-id="10273-134">**Which CSA STAR levels of assurance have Microsoft business cloud services attained?**</span></span>

- <span data-ttu-id="10273-135">**第 1 级别** - **CSA STAR 自我评估**：Azure、Dynamics 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="10273-135">**Level 1**: **CSA STAR Self-Assessment**: Azure, Dynamics 365, and Office 365.</span></span> <span data-ttu-id="10273-136">自我评估是云服务提供商免费提供的一项服务，可用于记录其安全控制措施，从而帮助客户对服务的安全性进行评估。</span><span class="sxs-lookup"><span data-stu-id="10273-136">The Self-Assessment is a complimentary offering from cloud service providers to document their security controls to help customers assess the security of the service.</span></span>
- <span data-ttu-id="10273-137">**第 2 级别** - **CSA STAR 认证**：Azure、Cloud App Security、Intune 和 Power BI。</span><span class="sxs-lookup"><span data-stu-id="10273-137">**Level 2**: **CSA STAR Certification**: Azure, Cloud App Security, Intune, and Power BI.</span></span> <span data-ttu-id="10273-138">如果获得 ISO/IEC 27001 认证并符合 CCM 中指定的条件，则授予 STAR 认证。</span><span class="sxs-lookup"><span data-stu-id="10273-138">STAR Certification is based on achieving ISO/IEC 27001 certification and meeting criteria specified in the CCM.</span></span> <span data-ttu-id="10273-139">第三方需对云服务提供商的安全控制措施和实践操作进行严格评估，然后才会授予该认证。</span><span class="sxs-lookup"><span data-stu-id="10273-139">It is awarded after a rigorous third-party assessment of the security controls and practices of a cloud service provider.</span></span>
- <span data-ttu-id="10273-140">**第 2 个级别** - **CSA STAR 证明**：Azure 和 Intune。</span><span class="sxs-lookup"><span data-stu-id="10273-140">**Level 2**: **CSA STAR Attestation**: Azure and Intune.</span></span> <span data-ttu-id="10273-141">CSA 和美国注册会计师协会 (AICPA) 根据 AICPA（信任服务原则，AT 101）和 CSA CCM 共同提出了指导方针，供注册会计师 (CPA) 在参与 SOC 2 认证过程中采用。</span><span class="sxs-lookup"><span data-stu-id="10273-141">CSA and the AICPA have collaborated to provide guidelines for CPAs to use in conducting SOC 2 engagements, using criteria from the AICPA (Trust Service Principles, AT 101) and the CSA CCM.</span></span> <span data-ttu-id="10273-142">STAR 证明根据这些指导方针提供，并在对云提供商进行严格独立评估后授予。</span><span class="sxs-lookup"><span data-stu-id="10273-142">STAR Attestation is based on these guidelines and is awarded after rigorous independent assessments of cloud providers.</span></span>

## <a name="resources"></a><span data-ttu-id="10273-143">资源</span><span class="sxs-lookup"><span data-stu-id="10273-143">Resources</span></span>

- [<span data-ttu-id="10273-144">云安全联盟</span><span class="sxs-lookup"><span data-stu-id="10273-144">Cloud Security Alliance</span></span>](https://cloudsecurityalliance.org/)
- [<span data-ttu-id="10273-145">云控制矩阵 (CCM)</span><span class="sxs-lookup"><span data-stu-id="10273-145">Cloud Controls Matrix (CCM)</span></span>](https://cloudsecurityalliance.org/group/cloud-controls-matrix/)
- [<span data-ttu-id="10273-146">共识评估倡议调查表 (CAIQ)</span><span class="sxs-lookup"><span data-stu-id="10273-146">Consensus Assessments Initiative Questionnaire (CAIQ)</span></span>](https://cloudsecurityalliance.org/group/consensus-assessments/)
- [<span data-ttu-id="10273-147">CSA 安全、信任及保证注册表 (STAR)</span><span class="sxs-lookup"><span data-stu-id="10273-147">CSA Security, Trust & Assurance Registry (STAR)</span></span>](https://cloudsecurityalliance.org/star/)
- [<span data-ttu-id="10273-148">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="10273-148">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-csa-star-self-assessments"></a><span data-ttu-id="10273-149">Microsoft CSA STAR 自我评估</span><span class="sxs-lookup"><span data-stu-id="10273-149">Microsoft CSA STAR self-assessments</span></span>

- [<span data-ttu-id="10273-150">Azure</span><span class="sxs-lookup"><span data-stu-id="10273-150">Azure</span></span>](https://aka.ms/Azure_STAR)
- [<span data-ttu-id="10273-151">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="10273-151">Dynamics 365</span></span>](https://aka.ms/DynamicsCRM_Online_STAR)
