---
title: 交易所最低可接受风险标准 (MARS-E) 2.0 框架
description: Microsoft 遵守美国交易所最低可接受风险标准 (MARS-E)。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 2d2c9862fe5af3eedd9ff90ff5bb6d33e1e06f10
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417516"
---
# <a name="minimum-acceptable-risk-standards-for-exchanges-mars-e-20-framework"></a><span data-ttu-id="89d0d-104">交易所最低可接受风险标准 (MARS-E) 2.0 框架</span><span class="sxs-lookup"><span data-stu-id="89d0d-104">Minimum Acceptable Risk Standards for Exchanges (MARS-E) 2.0 Framework</span></span>

## <a name="mars-e-20-framework-overview"></a><span data-ttu-id="89d0d-105">MARS-E 2.0 框架概述</span><span class="sxs-lookup"><span data-stu-id="89d0d-105">MARS-E 2.0 Framework overview</span></span>

<span data-ttu-id="89d0d-106">在 2012 年，美国医疗保险和医疗补助服务中心 (CMS) 根据 CMS 信息安全和隐私计划发布了交易所最低可接受风险标准 (MARS-E)。</span><span class="sxs-lookup"><span data-stu-id="89d0d-106">In 2012, the Center for Medicare and Medicaid Services (CMS) published the Minimum Acceptable Risk Standards for Exchanges (MARS-E) in accordance with CMS information security and privacy programs.</span></span> <span data-ttu-id="89d0d-107">这套文档（包括指南、要求和模板）旨在遵循《患者保护和大众医疗法》(ACA) 的强制要求以及适用于 ACA 的“卫生和公共服务部”的法规。</span><span class="sxs-lookup"><span data-stu-id="89d0d-107">The suite of documents, including guidance, requirements, and templates, was designed to address mandates of the Patient Protection and Affordable Care Act (ACA) and regulations of the Department of Health and Human Services that apply to the ACA.</span></span> <span data-ttu-id="89d0d-108">国家标准与技术研究院 (NIST) 特刊 800-53 作为父框架，为 ACA 授权的健康交易所和市场之间的所有系统、接口和连接制定安全性和合规性要求。</span><span class="sxs-lookup"><span data-stu-id="89d0d-108">The National Institute of Standards and Technology (NIST) Special Publication 800-53 serves as the parent framework that establishes the security and compliance requirements for all systems, interfaces, and connections between ACA-mandated health exchanges and marketplaces.</span></span>

<span data-ttu-id="89d0d-109">在 MARS-E 发布后，NIST 发布了一个更新（特刊 800-53r4），以应对日益严峻的在线安全（包括应用程序安全）的挑战、内部威胁和高级持久性威胁、供应链风险，以及移动和云计算系统的可靠性、保证性和弹性。</span><span class="sxs-lookup"><span data-stu-id="89d0d-109">Following the release of MARS-E, NIST released an update, Special Publication 800-53r4, to address growing challenges to online security, including application security; insider and advanced persistent threats; supply chain risks; and the trustworthiness, assurance, and resilience of systems of mobile and cloud computing.</span></span> <span data-ttu-id="89d0d-110">随后，CMS 修改了 MARS-E 框架，以与 NIST 800.53r4 中更新的控制措施和参数保持一致，并于 2015 年发布了 MARS-E 2.0。</span><span class="sxs-lookup"><span data-stu-id="89d0d-110">CMS then revised the MARS-E framework to align with the updated controls and parameters in NIST 800.53r4, publishing MARS-E 2.0 in 2015.</span></span>

<span data-ttu-id="89d0d-111">这些更新涉及健康交易所中受保护数据的机密性、完整性和可用性，这些数据包括个人身份信息、受保护健康信息和联邦税收信息。</span><span class="sxs-lookup"><span data-stu-id="89d0d-111">These updates address the confidentiality, integrity, and availability in health exchanges of protected data, which includes personally identifiable information, protected health information, and federal tax information.</span></span> <span data-ttu-id="89d0d-112">MARS-E 2.0 框架旨在保护此类受保护数据的安全，并适用于所有 ACA 管理实体，包括交易所或市场（联邦、州、州医疗补助或儿童健康保险计划 (CHIP) 机构），以及支持承包商。</span><span class="sxs-lookup"><span data-stu-id="89d0d-112">The MARS-E 2.0 framework aims to secure this protected data and applies to all ACA administering entities, including exchanges or marketplaces — federal, state, state Medicaid, or Children’s Health Insurance Program (CHIP) agencies — and supporting contractors.</span></span>

## <a name="microsoft-and-mars-e-20-framework"></a><span data-ttu-id="89d0d-113">Microsoft 和 MARS-E 2.0 框架</span><span class="sxs-lookup"><span data-stu-id="89d0d-113">Microsoft and MARS-E 2.0 framework</span></span>

<span data-ttu-id="89d0d-114">目前，没有针对 MARS-E 的正式授权和认证过程。</span><span class="sxs-lookup"><span data-stu-id="89d0d-114">Currently, there is no formal authorization and accreditation process for MARS-E.</span></span> <span data-ttu-id="89d0d-115">但是，Microsoft Azure 平台服务已在中等影响级别进行了 FedRAMP 独立审核，在高影响级别进行了 Azure 政府审核，并且已根据 FedRAMP 标准进行了授权。</span><span class="sxs-lookup"><span data-stu-id="89d0d-115">However, Microsoft Azure platform services have undergone independent FedRAMP audits at the Moderate Impact Level and Azure Government at the High Impact Level, and are authorized according to FedRAMP standards.</span></span> <span data-ttu-id="89d0d-116">虽然这些标准并非专门针对 MARS-E，但 MARS-E 控制要求和目标相辅相成，可用于保护 Azure 上数据的机密性、完整性和可用性。</span><span class="sxs-lookup"><span data-stu-id="89d0d-116">Although these standards do not specifically focus on MARS-E, the MARS-E control requirements and objectives are closely aligned and serve to protect the confidentiality, integrity, and availability of data on Azure.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="89d0d-117">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="89d0d-117">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="89d0d-118">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="89d0d-118">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="89d0d-119">Intune</span><span class="sxs-lookup"><span data-stu-id="89d0d-119">Intune</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="89d0d-120">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="89d0d-120">Audits, reports, and certificates</span></span>

<span data-ttu-id="89d0d-121">每年会针对 FedRAMP 授权流程对 Microsoft 商业云服务进行监视和评估。</span><span class="sxs-lookup"><span data-stu-id="89d0d-121">Microsoft business cloud services are monitored and assessed each year for the FedRAMP authorization process.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="89d0d-122">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="89d0d-122">Frequently asked questions</span></span>

<span data-ttu-id="89d0d-123">**此标准适用于哪些对象？**</span><span class="sxs-lookup"><span data-stu-id="89d0d-123">**To whom does the standard apply?**</span></span>

<span data-ttu-id="89d0d-124">MARS-E 适用于所有《大众医疗法》管理实体，包括交易所或市场（管理基本健康计划的联邦、州、医疗补助或 CHIP 机构），以及支持承包商和分包商。</span><span class="sxs-lookup"><span data-stu-id="89d0d-124">MARS-E applies to all Affordable Care Act administering entities, including exchanges or marketplaces — federal, state, Medicaid, and CHIP agencies administering the Basic Health Program — as well as all their contractors and subcontractors.</span></span>

<span data-ttu-id="89d0d-125">**Microsoft 如何通过此标准证明 Azure 和 Azure 政府合规性？**</span><span class="sxs-lookup"><span data-stu-id="89d0d-125">**How does Microsoft demonstrate Azure and Azure Government compliance with this standard?**</span></span>

<span data-ttu-id="89d0d-126">使用第三方针对 FedRAMP 授权准备的正式审核报告，Microsoft 能够说明这些报告中所述的相关控制措施如何展示 Azure 在满足 MARS-E 安全和隐私控制要求方面的能力。</span><span class="sxs-lookup"><span data-stu-id="89d0d-126">Using the formal audit reports prepared by third parties for FedRAMP authorizations, Microsoft is able to show how relevant controls noted that within these reports demonstrate Azure capabilities in meeting MARS-E security and privacy control requirements.</span></span> <span data-ttu-id="89d0d-127">Microsoft 实施的已审核控制措施旨在保护 Azure 平台上所存储数据的机密性、完整性和可用性，并且符合 MARS-E 中定义的已确定为 Microsoft 责任的适用法规要求。</span><span class="sxs-lookup"><span data-stu-id="89d0d-127">Audited controls implemented by Microsoft serve to protect the confidentiality, integrity, and availability of data stored on the Azure platform, and correspond to the applicable regulatory requirements defined in MARS-E that have been identified as the responsibility of Microsoft.</span></span>

<span data-ttu-id="89d0d-128">**Microsoft 对确保符合这一标准负有哪些责任？**</span><span class="sxs-lookup"><span data-stu-id="89d0d-128">**What are Microsoft's responsibilities for maintaining compliance with this standard?**</span></span>

<span data-ttu-id="89d0d-129">Microsoft 确保 Azure 平台符合管理[在线服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)和适用的服务级别协议 (SLA) 中定义的条款。</span><span class="sxs-lookup"><span data-stu-id="89d0d-129">Microsoft ensures that the Azure platform meets the terms defined within the governing [Online Services Terms](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31) and applicable service level agreements (SLAs).</span></span> <span data-ttu-id="89d0d-130">这些条款规定了我们在实施和维护足以确保 Azure 平台安全并监视系统的控制措施方面的责任。</span><span class="sxs-lookup"><span data-stu-id="89d0d-130">These define our responsibility for implementing and maintaining controls adequate to secure the Azure platform and monitor the system.</span></span>

<span data-ttu-id="89d0d-131">**能否在我所在组织的 MARS-E 认证工作中采用 Microsoft 的合规性认证？**</span><span class="sxs-lookup"><span data-stu-id="89d0d-131">**Can I use Microsoft's compliance in the MARS-E qualification efforts for my organization?**</span></span>

<span data-ttu-id="89d0d-132">能。</span><span class="sxs-lookup"><span data-stu-id="89d0d-132">Yes.</span></span> <span data-ttu-id="89d0d-133">符合 FedRAMP 标准的第三方审核报告可证实 Microsoft 已实施的、用于确保 Azure 平台安全性和隐私的控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="89d0d-133">Third-party audit reports to the FedRAMP standards attest to the effectiveness of the controls Microsoft has implemented to maintain the security and privacy of the Azure platform.</span></span> <span data-ttu-id="89d0d-134">Azure 和 Azure 政府客户可以在自己的 FedRAMP 和 MARS-E 风险分析和鉴定工作中采用这些相关报告中所述的已审核控制措施。</span><span class="sxs-lookup"><span data-stu-id="89d0d-134">Azure and Azure Government customers may use the audited controls described in these related reports as part of their own FedRAMP and MARS-E risk analysis and qualification efforts.</span></span>

## <a name="resources"></a><span data-ttu-id="89d0d-135">资源</span><span class="sxs-lookup"><span data-stu-id="89d0d-135">Resources</span></span>

- <span data-ttu-id="89d0d-136">MARS-E 规章指南, MARS-E 文档套件, 版本 2.0</span><span class="sxs-lookup"><span data-stu-id="89d0d-136">MARS-E regulatory guidance, MARS-E Document Suite, Version 2.0</span></span>
    - [<span data-ttu-id="89d0d-137">第 II 卷：交易所最低可接受风险标准</span><span class="sxs-lookup"><span data-stu-id="89d0d-137">Volume II: Minimum acceptable risk standards for exchanges</span></span>](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/2-MARS-E-v2-0-Minimum-Acceptable-Risk-Standards-for-Exchanges-11102015.pdf)
    - [<span data-ttu-id="89d0d-138">第 III 卷：交易所最低可接受风险安全性和隐私控制措施目录</span><span class="sxs-lookup"><span data-stu-id="89d0d-138">Volume III: Catalog of minimum acceptable risk security and privacy controls for exchanges</span></span>](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/3-MARS-E-v2-0-Catalog-of-Security-and-Privacy-Controls-11102015.pdf)
- [<span data-ttu-id="89d0d-139">Microsoft 在线服务合规性框架白皮书</span><span class="sxs-lookup"><span data-stu-id="89d0d-139">Microsoft compliance framework for online services white paper</span></span>](https://aka.ms/compliance-framework)
- [<span data-ttu-id="89d0d-140">Microsoft 在线服务条款</span><span class="sxs-lookup"><span data-stu-id="89d0d-140">Microsoft Online Services Terms</span></span>](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [<span data-ttu-id="89d0d-141">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="89d0d-141">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
