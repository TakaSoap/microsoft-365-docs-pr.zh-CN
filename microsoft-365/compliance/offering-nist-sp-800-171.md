---
title: NIST SP 800 –171
description: Microsoft 云服务遵循 NIST SP 800 –171准则来保护受控的未分类信息 (CUI) 在 nonfederal 信息系统中。
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
ms.openlocfilehash: 757541aa86049106ad06f02419fee02033c6a0e3
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417064"
---
# <a name="nist-sp-800171"></a><span data-ttu-id="d6a18-104">NIST SP 800 –171</span><span class="sxs-lookup"><span data-stu-id="d6a18-104">NIST SP 800–171</span></span>

## <a name="about-nist-sp-800171"></a><span data-ttu-id="d6a18-105">关于 NIST SP 800 –171</span><span class="sxs-lookup"><span data-stu-id="d6a18-105">About NIST SP 800–171</span></span>

<span data-ttu-id="d6a18-106">美国国家标准和技术协会 (NIST) 促进并维护度量标准和准则，以帮助保护联邦机构的信息和信息系统。</span><span class="sxs-lookup"><span data-stu-id="d6a18-106">The US National Institute of Standards and Technology (NIST) promotes and maintains measurement standards and guidelines to help protect the information and information systems of federal agencies.</span></span> <span data-ttu-id="d6a18-107">为了响应执行官订单13556的 (管理 CUI) ，it 发布了 [NIST SP 800 – 171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)，从而 *保护了 Nonfederal 信息系统和组织中的受控制的未分类信息*。</span><span class="sxs-lookup"><span data-stu-id="d6a18-107">In response to Executive Order 13556 on managing controlled unclassified information (CUI), it published [NIST SP 800–171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final), *Protecting Controlled Unclassified Information In Nonfederal Information Systems and Organizations*.</span></span> <span data-ttu-id="d6a18-108">CUI 定义为由政府 (或代表其代表的实体创建的信息（数字和物理）) ，而不是保密的信息仍是敏感的，需要保护。</span><span class="sxs-lookup"><span data-stu-id="d6a18-108">CUI is defined as information — both digital and physical — created by a government (or an entity on its behalf) that, while not classified, is still sensitive and requires protection.</span></span>

<span data-ttu-id="d6a18-109">NIST SP 800 –171最初是在2015年6月发布的，并且自那时起已更新多次，以响应演变的威胁。</span><span class="sxs-lookup"><span data-stu-id="d6a18-109">NIST SP 800–171 was originally published in June 2015 and has been updated several times since then in response to evolving cyberthreats.</span></span> <span data-ttu-id="d6a18-110">它提供了有关如何在 nonfederal 信息系统和组织中安全地访问、传输和存储 CUI 的指南。其要求分为四个主要类别：</span><span class="sxs-lookup"><span data-stu-id="d6a18-110">It provides guidelines on how CUI should be securely accessed, transmitted, and stored in nonfederal information systems and organizations; its requirements fall into four main categories:</span></span>

- <span data-ttu-id="d6a18-111">用于管理和保护的控件和流程</span><span class="sxs-lookup"><span data-stu-id="d6a18-111">Controls and processes for managing and protecting</span></span>
- <span data-ttu-id="d6a18-112">IT 系统的监控和管理</span><span class="sxs-lookup"><span data-stu-id="d6a18-112">Monitoring and management of IT systems</span></span>
- <span data-ttu-id="d6a18-113">最终用户的明确实践和过程</span><span class="sxs-lookup"><span data-stu-id="d6a18-113">Clear practices and procedures for end users</span></span>
- <span data-ttu-id="d6a18-114">技术和物理安全措施的实施</span><span class="sxs-lookup"><span data-stu-id="d6a18-114">Implementation of technological and physical security measures</span></span>

## <a name="microsoft-and-nist-sp-800171"></a><span data-ttu-id="d6a18-115">Microsoft 和 NIST SP 800 –171</span><span class="sxs-lookup"><span data-stu-id="d6a18-115">Microsoft and NIST SP 800–171</span></span>

<span data-ttu-id="d6a18-116">经资格鉴定的第三方评估组织、Kratos Secureinfo 和 Coalfire 与 Microsoft 合作，以证明其范围内的云服务符合 NIST SP 800 –171中的条件，在 *Nonfederal 信息系统和组织中保护受控制的未分类信息 () CUI 在*处理 CUI 时。</span><span class="sxs-lookup"><span data-stu-id="d6a18-116">Accredited third-party assessment organizations, Kratos Secureinfo and Coalfire, partnered with Microsoft to attest that its in-scope cloud services meet the criteria in NIST SP 800–171, *Protecting Controlled Unclassified Information (CUI) in Nonfederal Information Systems and Organizations*, when they process CUI.</span></span> <span data-ttu-id="d6a18-117">[Microsoft FedRAMP](offering-fedramp.md)要求的实现有助于确保 microsoft 范围内的云服务符合或超过 NIST SP 800 –171的要求，而这些系统和实践已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="d6a18-117">The [Microsoft implementation of FedRAMP](offering-fedramp.md) requirements help ensure Microsoft in-scope cloud services meet or exceed the requirements of NIST SP 800–171 using the systems and practices already in place.</span></span>

<span data-ttu-id="d6a18-118">NIST SP 800 –171要求是 NIST SP 800-53 的子集，FedRAMP 使用的标准。</span><span class="sxs-lookup"><span data-stu-id="d6a18-118">NIST SP 800–171 requirements are a subset of NIST SP 800-53, the standard that FedRAMP uses.</span></span> <span data-ttu-id="d6a18-119">在 NIST SP 800 –171的附录 D 中，可将其 CUI 安全要求直接映射到 NIST SP 800-53 中的相关安全控件，该服务已在 FedRAMP 程序下评估并授权了此项范围内的云服务。</span><span class="sxs-lookup"><span data-stu-id="d6a18-119">Appendix D of NIST SP 800–171 provides a direct mapping of its CUI security requirements to the relevant security controls in NIST SP 800-53, for which the in-scope cloud services have already been assessed and authorized under the FedRAMP program.</span></span>

<span data-ttu-id="d6a18-120">处理或存储美国政府 CUI 的任何实体（研究机构、咨询公司、制造承包商）必须遵守 NIST SP 800 –171的严格要求。</span><span class="sxs-lookup"><span data-stu-id="d6a18-120">Any entity that processes or stores US government CUI — research institutions, consulting companies, manufacturing contractors — must comply with the stringent requirements of NIST SP 800–171.</span></span> <span data-ttu-id="d6a18-121">此证明意味着 Microsoft 的范围内云服务可以适应希望部署 CUI 工作负荷的客户，并确保 Microsoft 处于完全遵从性。</span><span class="sxs-lookup"><span data-stu-id="d6a18-121">This attestation means Microsoft in-scope cloud services can accommodate customers looking to deploy CUI workloads with the assurance that Microsoft is in full compliance.</span></span> <span data-ttu-id="d6a18-122">例如，在其信息系统中使用范围内的 Microsoft 云服务处理、存储或传输 "覆盖的防御信息" 的所有 DoD 承包商都将满足美国国防部的 DFARS 条款要求符合 NIST SP 800 –171的安全要求。</span><span class="sxs-lookup"><span data-stu-id="d6a18-122">For example, all DoD contractors who process, store, or transmit 'covered defense information' using in-scope Microsoft cloud services in their information systems meet the US Department of Defense DFARS clauses that require compliance with the security requirements of NIST SP 800–171.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="d6a18-123">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="d6a18-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="d6a18-124">Azure 政府</span><span class="sxs-lookup"><span data-stu-id="d6a18-124">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="d6a18-125">美国政府 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d6a18-125">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="d6a18-126">Intune</span><span class="sxs-lookup"><span data-stu-id="d6a18-126">Intune</span></span>
- [<span data-ttu-id="d6a18-127">Office 365 美国政府社区云 (GCC) 、Office 365 GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="d6a18-127">Office 365 U.S. Government Community Cloud (GCC), Office 365 GCC High, and DoD</span></span>](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="d6a18-128">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="d6a18-128">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="d6a18-129">具有 NIST SP 800 –171的 Azure 政府合规性证明</span><span class="sxs-lookup"><span data-stu-id="d6a18-129">Azure Government Attestation of Compliance with NIST SP 800–171</span></span>](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a><span data-ttu-id="d6a18-130">如何实现</span><span class="sxs-lookup"><span data-stu-id="d6a18-130">How to implement</span></span>

- <span data-ttu-id="d6a18-131">[Azure 蓝图示例](https://docs.microsoft.com/azure/governance/blueprints/samples/)：获取对实施符合 NIST 的控件的工作负荷的支持。</span><span class="sxs-lookup"><span data-stu-id="d6a18-131">[Azure Blueprint samples](https://docs.microsoft.com/azure/governance/blueprints/samples/): Get support for implementing workloads that comply with NIST-based controls.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d6a18-132">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="d6a18-132">Frequently asked questions</span></span>

<span data-ttu-id="d6a18-133">**对于我的组织，我可以使用 Microsoft 合规性的 NIST SP 800 –171吗？**</span><span class="sxs-lookup"><span data-stu-id="d6a18-133">**Can I use Microsoft compliance with NIST SP 800–171 for my organization?**</span></span>

<span data-ttu-id="d6a18-134">是。</span><span class="sxs-lookup"><span data-stu-id="d6a18-134">Yes.</span></span> <span data-ttu-id="d6a18-135">Microsoft 客户可以使用来自独立第三方评估组织的报告中所述的审核的控件 (3PAO) 在 FedRAMP 标准中，作为其自己的 FedRAMP 和 NIST 风险分析和资格努力的一部分。</span><span class="sxs-lookup"><span data-stu-id="d6a18-135">Microsoft customers may use the audited controls described in the reports from independent third-party assessment organizations (3PAO) on FedRAMP standards as part of their own FedRAMP and NIST risk analysis and qualification efforts.</span></span> <span data-ttu-id="d6a18-136">这些报告证明 Microsoft 已在其范围内的云服务中实现的控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="d6a18-136">These reports attest to the effectiveness of the controls Microsoft has implemented in its in-scope cloud services.</span></span> <span data-ttu-id="d6a18-137">客户负责确保其 CUI 工作负载符合 NIST SP 800 –171准则。</span><span class="sxs-lookup"><span data-stu-id="d6a18-137">Customers are responsible for ensuring that their CUI workloads comply with NIST SP 800–171 guidelines.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="d6a18-138">使用 Microsoft 合规性分数评估风险</span><span class="sxs-lookup"><span data-stu-id="d6a18-138">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="d6a18-139">[Microsoft 合规性分数](compliance-score.md)是 [Microsoft 365 合规中心](microsoft-365-compliance-center.md)中的一项预览功能，旨在帮助你了解组织的合规情况并采取措施帮助降低风险。</span><span class="sxs-lookup"><span data-stu-id="d6a18-139">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization’s compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="d6a18-140">[设置合规性分数](compliance-score-setup.md)后，从 "**模板**" 下拉菜单中选择预配置的[NIST 800-171 模板](https://go.microsoft.com/fwlink/?linkid=2117526)，以帮助您的组织满足此法规的要求。</span><span class="sxs-lookup"><span data-stu-id="d6a18-140">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [NIST 800-171 template](https://go.microsoft.com/fwlink/?linkid=2117526) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="d6a18-141">资源</span><span class="sxs-lookup"><span data-stu-id="d6a18-141">Resources</span></span>

- [<span data-ttu-id="d6a18-142">Microsoft DoD 认证符合 NIST 800 –171要求</span><span class="sxs-lookup"><span data-stu-id="d6a18-142">Microsoft DoD Certification Meets NIST 800–171 Requirements</span></span>](offering-DoD-DISA-L2-L4-L5.md)
- [<span data-ttu-id="d6a18-143">NIST 800 –171合规性从 Cybersecurity 文档开始</span><span class="sxs-lookup"><span data-stu-id="d6a18-143">NIST 800–171 Compliance Starts with Cybersecurity Documentation</span></span>](https://www.nist800171.com/)
- [<span data-ttu-id="d6a18-144">Microsoft 云服务 FedRAMP 授权</span><span class="sxs-lookup"><span data-stu-id="d6a18-144">Microsoft Cloud Services FedRAMP Authorizations</span></span>](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [<span data-ttu-id="d6a18-145">NIST 800-171 3.3 审核和责任与 Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="d6a18-145">NIST 800-171 3.3 Audit and Accountability with Office 365 GCC High</span></span>](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [<span data-ttu-id="d6a18-146">Microsoft 和 NIST Cybersecurity 框架</span><span class="sxs-lookup"><span data-stu-id="d6a18-146">Microsoft and the NIST Cybersecurity Framework</span></span>](offering-nist-csf.md)
- [<span data-ttu-id="d6a18-147">Microsoft 政府云</span><span class="sxs-lookup"><span data-stu-id="d6a18-147">Microsoft Government Cloud</span></span>](https://www.microsoft.com/enterprise/government)
- [<span data-ttu-id="d6a18-148">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="d6a18-148">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
