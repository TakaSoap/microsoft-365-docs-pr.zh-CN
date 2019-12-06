---
title: 云计算合规性控制目录 (C5)
description: 了解 Azure、Azure Government 和 Azure Germany 如何演示云计算合规性控制目录 (C5) 的合规性证明。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: e668793da42010656d58f3a474c86e1d24814e84
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "39860102"
---
# <a name="cloud-computing-compliance-controls-catalog-c5"></a><span data-ttu-id="27435-104">云计算合规性控制目录 (C5)</span><span class="sxs-lookup"><span data-stu-id="27435-104">Cloud Computing Compliance Controls Catalog (C5)</span></span>

## <a name="c5-overview"></a><span data-ttu-id="27435-105">C5 概述</span><span class="sxs-lookup"><span data-stu-id="27435-105">C5 overview</span></span>

<span data-ttu-id="27435-106">2016 年，德国联邦信息安全局（Bundesamt für Sicherheit in der Informationstechnik 或 BSI）创建了云计算合规性控制目录 (C5)。</span><span class="sxs-lookup"><span data-stu-id="27435-106">In 2016, the German Federal Office for Information Security (Bundesamt für Sicherheit in der Informationstechnik, or BSI) created the Cloud Computing Compliance Controls Catalog (C5).</span></span> <span data-ttu-id="27435-107">C5 是经审核的标准，可为云安全建立必要的最低基准，并由德国政府机构以及与政府合作的组织采用公共云解决方案。</span><span class="sxs-lookup"><span data-stu-id="27435-107">C5 is an audited standard that establishes a mandatory minimum baseline for cloud security and the adoption of public cloud solutions by German government agencies and organizations that work with government.</span></span> <span data-ttu-id="27435-108">越来越多的私营部门也逐渐采用 C5。</span><span class="sxs-lookup"><span data-stu-id="27435-108">C5 is also being increasingly adopted by the private sector.</span></span>

<span data-ttu-id="27435-109">C5 目录的要求旨在提供一致的安全框架，以便于验证云服务提供商，并使客户确信自己的数据受到安全管理。</span><span class="sxs-lookup"><span data-stu-id="27435-109">The purpose of the C5 catalog of requirements is to provide a consistent security framework for certifying cloud service providers and to give customers assurance that their data will be managed securely.</span></span>

<span data-ttu-id="27435-110">C5 基于国际认可的 IT 安全标准，如 ISO/IEC 27001:2013、云安全联盟云控制矩阵 3.0.1 和 BSI IT-Grundschutz 目录。</span><span class="sxs-lookup"><span data-stu-id="27435-110">C5 is based on internationally recognized IT security standards like ISO/IEC 27001:2013, the Cloud Security Alliance Cloud Controls Matrix 3.0.1, and BSI’s own IT-Grundschutz Catalogues.</span></span> <span data-ttu-id="27435-111">目录包含跨 17 个领域（例如信息安全和物理安全组织）的 114 项要求，其中包含对所有云服务提供商的基本安全要求，以及对处理高度机密数据和需要高可用性的情况的额外要求。</span><span class="sxs-lookup"><span data-stu-id="27435-111">The catalog consists of 114 requirements across 17 domains — for example, the organization of information security and physical security — with security requirements basic to all cloud service providers, and additional requirements for processing highly confidential data and situations requiring high availability.</span></span>

<span data-ttu-id="27435-112">BSI 还着重强调了透明化。</span><span class="sxs-lookup"><span data-stu-id="27435-112">The BSI also puts emphasis on transparency.</span></span> <span data-ttu-id="27435-113">作为审核的一部分，云提供商必须包含详细的系统说明并披露环境参数，例如管辖权和数据处理位置、服务提供、向其他云服务颁发的其他认证以及关于云提供商对公共机关的披露义务的信息。</span><span class="sxs-lookup"><span data-stu-id="27435-113">As part of an audit, the cloud provider must include a detailed system description and disclose environmental parameters like jurisdiction and data processing location, provision of services, and other certifications issued to the cloud services, and information about the cloud provider’s disclosure obligations to public authorities.</span></span> <span data-ttu-id="27435-114">这有助于潜在云客户决定云服务是否满足基本要求，例如与数据保护和公司策略等法规要求的合规性或解决行业间谍威胁的能力。</span><span class="sxs-lookup"><span data-stu-id="27435-114">This helps potential cloud customers decide whether the cloud services meet their essential requirements such as compliance with legal requirements like data protection, company policies, or the ability to address the threat of industrial espionage.</span></span>

## <a name="microsoft-and-c5"></a><span data-ttu-id="27435-115">Microsoft 和 C5</span><span class="sxs-lookup"><span data-stu-id="27435-115">Microsoft and C5</span></span>

<span data-ttu-id="27435-116">Microsoft 云服务会根据 SOC 2（AT 条例 101）标准每年至少进行一次审核。</span><span class="sxs-lookup"><span data-stu-id="27435-116">Microsoft cloud services are audited at least annually against SOC 2 (AT Section 101) standards.</span></span> <span data-ttu-id="27435-117">根据 BSI，可将 C5 审核与 SOC 2 审核结合使用，对重叠控制重用部分系统描述和审核结果。</span><span class="sxs-lookup"><span data-stu-id="27435-117">According to BSI, a C5 audit can be combined with a SOC 2 audit to reuse parts of the system description and audit results for overlapping controls.</span></span> <span data-ttu-id="27435-118">Microsoft Azure、Azure Government 和 Azure Germany 根据独立审核员进行的审核评估制定综合报告（C5、SOC 2 类型 2、CSA STAR 证明），这可证明与 C5 的合规性。</span><span class="sxs-lookup"><span data-stu-id="27435-118">Microsoft Azure, Azure Government, and Azure Germany maintain a combined report (C5, SOC 2 Type 2, CSA STAR Attestation) based on the audit assessment performed by an independent auditor, which demonstrates proof of compliance with C5.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="27435-119">Microsoft 范围内的云服务</span><span class="sxs-lookup"><span data-stu-id="27435-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="27435-120">Azure、Azure Government 和 Azure Germany</span><span class="sxs-lookup"><span data-stu-id="27435-120">Azure, Azure Government, and Azure Germany</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="27435-121">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="27435-121">Office 365 Germany</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="27435-122">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="27435-122">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="27435-123">Azure, Azure Government, and Azure Germany SOC 2 Type II Report.pdf</span><span class="sxs-lookup"><span data-stu-id="27435-123">Azure, Azure Government, and Azure Germany SOC 2 Type II Report.pdf</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2093520)

## <a name="frequently-asked-questions"></a><span data-ttu-id="27435-124">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="27435-124">Frequently asked questions</span></span>

<span data-ttu-id="27435-125">**我能否使用 Microsoft C5 合规性帮助我的组织获得自己的 C5 证明？**</span><span class="sxs-lookup"><span data-stu-id="27435-125">**Can I use Microsoft compliance with C5 to help my organization get its own C5 attestation?**</span></span>

<span data-ttu-id="27435-126">能。</span><span class="sxs-lookup"><span data-stu-id="27435-126">Yes.</span></span> <span data-ttu-id="27435-127">你可以将 Microsoft 云服务证明作为需要 C5 的任何项目或计划的基础。</span><span class="sxs-lookup"><span data-stu-id="27435-127">You may use the attestation of Microsoft cloud services as the foundation for any program or initiative that requires C5.</span></span> <span data-ttu-id="27435-128">但是，你需要为这些服务之外或在这些服务的基础上构建的组件获得自己的 C5 证明。</span><span class="sxs-lookup"><span data-stu-id="27435-128">However, you need to achieve your own C5 attestation for components outside or built on top of these services.</span></span>

<span data-ttu-id="27435-129">**C5 与 IT-Grundschutz 目录之间有何区别？**</span><span class="sxs-lookup"><span data-stu-id="27435-129">**What’s the difference between C5 and the IT-Grundschutz Catalogues?**</span></span>

<span data-ttu-id="27435-130">IT-Grundschutz 提供了特定方法，帮助组织确定和实施 IT 系统的安全措施，它是构建 C5 标准所需的要素之一。</span><span class="sxs-lookup"><span data-stu-id="27435-130">IT-Grundschutz supplies the specific methodology to help organizations identify and implement security measures for IT systems and is one of the elements upon which the C5 standards are built.</span></span> <span data-ttu-id="27435-131">C5 为云服务提供商提供一系列审核标准，但会将实施的详细信息保留给云服务提供商。</span><span class="sxs-lookup"><span data-stu-id="27435-131">C5 provides a set of audit standards for cloud service providers but leaves the details of implementation up to the cloud service provider.</span></span>

<span data-ttu-id="27435-132">**什么是 Microsoft Cloud Germany？**</span><span class="sxs-lookup"><span data-stu-id="27435-132">**What is Microsoft Cloud Germany?**</span></span>

<span data-ttu-id="27435-133">Microsoft Cloud Germany 实际位于德国，并遵守德国隐私法的要求，严格限制将个人数据传输到其他国家/地区，包括防止其他司法管辖区的机构访问可能违反国内法律的数据。</span><span class="sxs-lookup"><span data-stu-id="27435-133">Microsoft Cloud Germany is physically based in Germany, adhering to the requirement of German privacy law, which limits the transfer of personal data to other countries and offers protection against access by authorities from other jurisdictions who could violate domestic laws.</span></span> <span data-ttu-id="27435-134">Azure Germany 从数据位于德国的德国数据中心交付 Azure 服务，它通过德国法律管辖的独特数据委托模型实施严格的数据访问和控制措施。</span><span class="sxs-lookup"><span data-stu-id="27435-134">Azure Germany delivers Azure services from German datacenters with data residency in Germany, and it delivers strict data access and control measures provided through a unique data trustee model governed under German law.</span></span>

## <a name="resources"></a><span data-ttu-id="27435-135">资源</span><span class="sxs-lookup"><span data-stu-id="27435-135">Resources</span></span>

- <span data-ttu-id="27435-136">云计算合规性控制目录 (C5)（[英语](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Controls_Catalogue/Compliance_Controls_Catalogue_node.html)）（[德语](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Anforderungskatalog/Anforderungskatalog_node.html)）</span><span class="sxs-lookup"><span data-stu-id="27435-136">Cloud Computing Compliance Controls Catalogue (C5) ([English](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Controls_Catalogue/Compliance_Controls_Catalogue_node.html)) ([German](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Anforderungskatalog/Anforderungskatalog_node.html))</span></span>
- [<span data-ttu-id="27435-137">在国际标准中引用云计算合规性控制目录 (C5)</span><span class="sxs-lookup"><span data-stu-id="27435-137">Referencing Cloud Computing Compliance Controls Catalogue (C5) to International Standards</span></span>](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/CloudComputing/ComplianceControlsCatalogue/Referencing_Cloud_Computing_Compliance_Controls_Catalogue.pdf;jsessionid=E5F009E49EB2689FAC3705578821BCB6.2_cid286?__blob=publicationFile&v=2)
- [<span data-ttu-id="27435-138">给云计算提供商的安全建议</span><span class="sxs-lookup"><span data-stu-id="27435-138">Security Recommendations for Cloud Computing Providers</span></span>](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/CloudComputing/SecurityRecommendationsCloudComputingProviders.pdf?__blob=publicationFile&v=2)
- [<span data-ttu-id="27435-139">合规性报告：C5- und SOC-Testate Azure Deutschland</span><span class="sxs-lookup"><span data-stu-id="27435-139">Compliance Reports: C5- und SOC-Testate Azure Deutschland</span></span>](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=df100ae1-baf9-4785-8a6d-864c0bc5c308&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)
- <span data-ttu-id="27435-140">[IT-Grundschutz 合规性工作簿](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7) - Microsoft Azure Germany</span><span class="sxs-lookup"><span data-stu-id="27435-140">[IT-Grundschutz Compliance Workbook](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7) for Microsoft Azure Germany</span></span>
- [<span data-ttu-id="27435-141">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="27435-141">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="27435-142">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="27435-142">Download the offering backgrounder</span></span>

<span data-ttu-id="27435-143">需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="27435-143">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="27435-144">请下载 [PDF](https://download.microsoft.com/download/E/F/6/EF619A4D-C17C-4279-8DC4-79C0620676AB/C5Germany-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="27435-144">Download the [PDF](https://download.microsoft.com/download/E/F/6/EF619A4D-C17C-4279-8DC4-79C0620676AB/C5Germany-Compliance.pdf).</span></span>
