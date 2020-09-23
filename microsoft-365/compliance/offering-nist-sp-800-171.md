---
title: NIST SP 800-171
description: Microsoft 云服务遵循 NIST SP 800-171 准则来保护受控的未分类信息 (CUI) 在 nonfederal 信息系统中。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
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
ms.openlocfilehash: 9874a68978e5755e8e86ff476ec96170878a10da
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208084"
---
# <a name="nist-sp-800-171"></a><span data-ttu-id="d2485-104">NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="d2485-104">NIST SP 800-171</span></span>

## <a name="about-nist-sp-800-171"></a><span data-ttu-id="d2485-105">关于 NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="d2485-105">About NIST SP 800-171</span></span>

<span data-ttu-id="d2485-106">美国国家标准和技术协会 (NIST) 促进并维护度量标准和准则，以帮助保护联邦机构的信息和信息系统。</span><span class="sxs-lookup"><span data-stu-id="d2485-106">The US National Institute of Standards and Technology (NIST) promotes and maintains measurement standards and guidelines to help protect the information and information systems of federal agencies.</span></span> <span data-ttu-id="d2485-107">为了响应执行官订单13556管理受控制的未分类信息 (CUI) ，it 发布了 [NIST SP 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)， *保护了 Nonfederal 信息系统和组织中的受控制的未分类信息*。</span><span class="sxs-lookup"><span data-stu-id="d2485-107">In response to Executive Order 13556 on managing controlled unclassified information (CUI), it published [NIST SP 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final), *Protecting Controlled Unclassified Information In Nonfederal Information Systems and Organizations*.</span></span> <span data-ttu-id="d2485-108">CUI 定义为由政府 (或代表其代表的实体创建的信息（数字和物理）) ，而不是保密的信息仍是敏感的，需要保护。</span><span class="sxs-lookup"><span data-stu-id="d2485-108">CUI is defined as information — both digital and physical — created by a government (or an entity on its behalf) that, while not classified, is still sensitive and requires protection.</span></span>

<span data-ttu-id="d2485-109">NIST SP 800-171 最初在6月2015发布，并在接下来更新几次，以响应演变的威胁。</span><span class="sxs-lookup"><span data-stu-id="d2485-109">NIST SP 800-171 was originally published in June 2015 and has been updated several times since then in response to evolving cyberthreats.</span></span> <span data-ttu-id="d2485-110">它提供了有关如何在 nonfederal 信息系统和组织中安全地访问、传输和存储 CUI 的指南。其要求分为四个主要类别：</span><span class="sxs-lookup"><span data-stu-id="d2485-110">It provides guidelines on how CUI should be securely accessed, transmitted, and stored in nonfederal information systems and organizations; its requirements fall into four main categories:</span></span>

- <span data-ttu-id="d2485-111">用于管理和保护的控件和流程</span><span class="sxs-lookup"><span data-stu-id="d2485-111">Controls and processes for managing and protecting</span></span>
- <span data-ttu-id="d2485-112">IT 系统的监控和管理</span><span class="sxs-lookup"><span data-stu-id="d2485-112">Monitoring and management of IT systems</span></span>
- <span data-ttu-id="d2485-113">最终用户的明确实践和过程</span><span class="sxs-lookup"><span data-stu-id="d2485-113">Clear practices and procedures for end users</span></span>
- <span data-ttu-id="d2485-114">技术和物理安全措施的实施</span><span class="sxs-lookup"><span data-stu-id="d2485-114">Implementation of technological and physical security measures</span></span>

## <a name="microsoft-and-nist-sp-800-171"></a><span data-ttu-id="d2485-115">Microsoft 和 NIST SP 800-171</span><span class="sxs-lookup"><span data-stu-id="d2485-115">Microsoft and NIST SP 800-171</span></span>

<span data-ttu-id="d2485-116">经资格鉴定的第三方评估组织、Kratos Secureinfo 和 Coalfire 与 Microsoft 合作，以证明其范围内的云服务符合 NIST SP 800-171 中的条件， *保护受控制的未分类信息 (CUI 在 Nonfederal 信息系统和组织中) 在*处理 CUI 时。</span><span class="sxs-lookup"><span data-stu-id="d2485-116">Accredited third-party assessment organizations, Kratos Secureinfo and Coalfire, partnered with Microsoft to attest that its in-scope cloud services meet the criteria in NIST SP 800-171, *Protecting Controlled Unclassified Information (CUI) in Nonfederal Information Systems and Organizations*, when they process CUI.</span></span> <span data-ttu-id="d2485-117">[Microsoft 实施 FedRAMP](offering-fedramp.md)要求有助于确保 microsoft 范围内的云服务使用已实施的系统和做法满足或超过 NIST SP 800-171 的要求。</span><span class="sxs-lookup"><span data-stu-id="d2485-117">The [Microsoft implementation of FedRAMP](offering-fedramp.md) requirements help ensure Microsoft in-scope cloud services meet or exceed the requirements of NIST SP 800-171 using the systems and practices already in place.</span></span>

<span data-ttu-id="d2485-118">NIST SP 800-171 要求是 NIST SP 800-53 （FedRAMP 使用的标准）的子集。</span><span class="sxs-lookup"><span data-stu-id="d2485-118">NIST SP 800-171 requirements are a subset of NIST SP 800-53, the standard that FedRAMP uses.</span></span> <span data-ttu-id="d2485-119">在 NIST SP 800-171 的附录 D 中，可将其 CUI 安全要求直接映射到 NIST SP 800-53 中的相关安全控件，该服务已在 FedRAMP 程序下评估并授权了此项范围内的云服务。</span><span class="sxs-lookup"><span data-stu-id="d2485-119">Appendix D of NIST SP 800-171 provides a direct mapping of its CUI security requirements to the relevant security controls in NIST SP 800-53, for which the in-scope cloud services have already been assessed and authorized under the FedRAMP program.</span></span>

<span data-ttu-id="d2485-120">处理或存储美国政府 CUI 的任何实体（研究机构、咨询公司、制造承包商）必须符合 NIST SP 800-171 的严格要求。</span><span class="sxs-lookup"><span data-stu-id="d2485-120">Any entity that processes or stores US government CUI — research institutions, consulting companies, manufacturing contractors — must comply with the stringent requirements of NIST SP 800-171.</span></span> <span data-ttu-id="d2485-121">此证明意味着 Microsoft 的范围内云服务可以适应希望部署 CUI 工作负荷的客户，并确保 Microsoft 处于完全遵从性。</span><span class="sxs-lookup"><span data-stu-id="d2485-121">This attestation means Microsoft in-scope cloud services can accommodate customers looking to deploy CUI workloads with the assurance that Microsoft is in full compliance.</span></span> <span data-ttu-id="d2485-122">例如，在其信息系统中使用范围内的 Microsoft 云服务处理、存储或传输 "覆盖的防御信息" 的所有 DoD 承包商都将满足美国国防部的 DFARS 条款要求符合 NIST SP 800-171 的安全要求。</span><span class="sxs-lookup"><span data-stu-id="d2485-122">For example, all DoD contractors who process, store, or transmit 'covered defense information' using in-scope Microsoft cloud services in their information systems meet the US Department of Defense DFARS clauses that require compliance with the security requirements of NIST SP 800-171.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="d2485-123">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="d2485-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="d2485-124">Azure 政府</span><span class="sxs-lookup"><span data-stu-id="d2485-124">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="d2485-125">美国政府 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d2485-125">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="d2485-126">Intune</span><span class="sxs-lookup"><span data-stu-id="d2485-126">Intune</span></span>
- [<span data-ttu-id="d2485-127">Office 365 美国政府社区云 (GCC) 、Office 365 GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="d2485-127">Office 365 U.S. Government Community Cloud (GCC), Office 365 GCC High, and DoD</span></span>](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="d2485-128">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="d2485-128">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="d2485-129">与 NIST SP 800-171 兼容性的 Azure 政府合规性证明</span><span class="sxs-lookup"><span data-stu-id="d2485-129">Azure Government Attestation of Compliance with NIST SP 800-171</span></span>](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a><span data-ttu-id="d2485-130">如何实现</span><span class="sxs-lookup"><span data-stu-id="d2485-130">How to implement</span></span>

- <span data-ttu-id="d2485-131">[Azure 蓝图示例](https://docs.microsoft.com/azure/governance/blueprints/samples/)：获取对实施符合 NIST 的控件的工作负荷的支持。</span><span class="sxs-lookup"><span data-stu-id="d2485-131">[Azure Blueprint samples](https://docs.microsoft.com/azure/governance/blueprints/samples/): Get support for implementing workloads that comply with NIST-based controls.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d2485-132">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="d2485-132">Frequently asked questions</span></span>

<span data-ttu-id="d2485-133">**是否可以对我的组织使用 NIST SP 800-171 的 Microsoft 合规性？**</span><span class="sxs-lookup"><span data-stu-id="d2485-133">**Can I use Microsoft compliance with NIST SP 800-171 for my organization?**</span></span>

<span data-ttu-id="d2485-134">是。</span><span class="sxs-lookup"><span data-stu-id="d2485-134">Yes.</span></span> <span data-ttu-id="d2485-135">Microsoft 客户可以使用来自独立第三方评估组织的报告中所述的审核的控件 (3PAO) 在 FedRAMP 标准中，作为其自己的 FedRAMP 和 NIST 风险分析和资格努力的一部分。</span><span class="sxs-lookup"><span data-stu-id="d2485-135">Microsoft customers may use the audited controls described in the reports from independent third-party assessment organizations (3PAO) on FedRAMP standards as part of their own FedRAMP and NIST risk analysis and qualification efforts.</span></span> <span data-ttu-id="d2485-136">这些报告证明 Microsoft 已在其范围内的云服务中实现的控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="d2485-136">These reports attest to the effectiveness of the controls Microsoft has implemented in its in-scope cloud services.</span></span> <span data-ttu-id="d2485-137">客户负责确保其 CUI 工作负载符合 NIST SP 800-171 指南。</span><span class="sxs-lookup"><span data-stu-id="d2485-137">Customers are responsible for ensuring that their CUI workloads comply with NIST SP 800-171 guidelines.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="d2485-138">使用 Microsoft 合规性管理器评估风险</span><span class="sxs-lookup"><span data-stu-id="d2485-138">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="d2485-139">[Microsoft 合规性管理器](compliance-manager.md) 是 [microsoft 365 合规性中心](microsoft-365-compliance-center.md) 中的一项功能，可帮助您了解组织的合规性状况并采取措施帮助降低风险。</span><span class="sxs-lookup"><span data-stu-id="d2485-139">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="d2485-140">合规性管理器提供了一个用于为此法规建立评估的高级模板。</span><span class="sxs-lookup"><span data-stu-id="d2485-140">Compliance Manager offers a premium template for building an assessment for this regulation.</span></span> <span data-ttu-id="d2485-141">在合规性管理器的 " **评估模板** " 页中查找模板。</span><span class="sxs-lookup"><span data-stu-id="d2485-141">Find the template in the **assessment templates** page in Compliance Manager.</span></span> <span data-ttu-id="d2485-142">了解如何 [在合规性管理器中构建评估](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="d2485-142">Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="d2485-143">资源</span><span class="sxs-lookup"><span data-stu-id="d2485-143">Resources</span></span>

- [<span data-ttu-id="d2485-144">Microsoft DoD 认证符合 NIST 800-171 要求</span><span class="sxs-lookup"><span data-stu-id="d2485-144">Microsoft DoD Certification Meets NIST 800-171 Requirements</span></span>](offering-DoD-DISA-L2-L4-L5.md)
- [<span data-ttu-id="d2485-145">NIST 800-171 合规性从 Cybersecurity 文档中开始</span><span class="sxs-lookup"><span data-stu-id="d2485-145">NIST 800-171 Compliance Starts with Cybersecurity Documentation</span></span>](https://www.nist800171.com/)
- [<span data-ttu-id="d2485-146">Microsoft 云服务 FedRAMP 授权</span><span class="sxs-lookup"><span data-stu-id="d2485-146">Microsoft Cloud Services FedRAMP Authorizations</span></span>](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [<span data-ttu-id="d2485-147">NIST 800-171 3.3 审核和责任与 Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="d2485-147">NIST 800-171 3.3 Audit and Accountability with Office 365 GCC High</span></span>](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [<span data-ttu-id="d2485-148">Microsoft 和 NIST Cybersecurity 框架</span><span class="sxs-lookup"><span data-stu-id="d2485-148">Microsoft and the NIST Cybersecurity Framework</span></span>](offering-nist-csf.md)
- [<span data-ttu-id="d2485-149">Microsoft 政府云</span><span class="sxs-lookup"><span data-stu-id="d2485-149">Microsoft Government Cloud</span></span>](https://www.microsoft.com/enterprise/government)
- [<span data-ttu-id="d2485-150">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="d2485-150">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
