---
title: 欧洲银行管理局 (EBA)
description: Microsoft 指导有助于欧盟金融机构遵循 EBA 关于采用云的建议。
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
ms.openlocfilehash: 9b3655c5b9a4fec2055993ace185ed899f8e0dbc
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602509"
---
# <a name="european-banking-authority-eba"></a><span data-ttu-id="2df59-104">欧洲银行管理局 (EBA)</span><span class="sxs-lookup"><span data-stu-id="2df59-104">European Banking Authority (EBA)</span></span>

## <a name="about-the-eba"></a><span data-ttu-id="2df59-105">关于 EBA</span><span class="sxs-lookup"><span data-stu-id="2df59-105">About the EBA</span></span>

<span data-ttu-id="2df59-106">[欧洲银行管理局](https://eba.europa.eu/) (EBA) 是“一家独立机构，致力于确保在整个欧洲银行业实现高效、一致的审慎监管和监督”。</span><span class="sxs-lookup"><span data-stu-id="2df59-106">The [European Banking Authority](https://eba.europa.eu/) (EBA) is “an independent authority that works to ensure effective and consistent prudential regulation and supervision across the EU banking sector.”</span></span> <span data-ttu-id="2df59-107">2017 年 12 月，EBA 发布了[最终报告：有关外包给云服务提供商的建议](https://eba.europa.eu/documents/10180/2170121/Final+draft+Recommendations+on+Cloud+Outsourcing+%28EBA-Rec-2017-03%29.pdf/5fa5cdde-3219-4e95-946d-0c0d05494362)，就欧盟境内金融机构外包云计算提出了一个综合方法。</span><span class="sxs-lookup"><span data-stu-id="2df59-107">In December 2017, the EBA issued its [Final Report: Recommendations on outsourcing to cloud services providers](https://eba.europa.eu/documents/10180/2170121/Final+draft+Recommendations+on+Cloud+Outsourcing+%28EBA-Rec-2017-03%29.pdf/5fa5cdde-3219-4e95-946d-0c0d05494362), which outlined a comprehensive approach to the outsourcing of cloud computing by financial institutions in the EU.</span></span> <span data-ttu-id="2df59-108">这些建议明确了何时允许外包到云，从技术中立角度应用基于原则的方法评估风险，并致力于在欧洲及之外的地方实现统一。</span><span class="sxs-lookup"><span data-stu-id="2df59-108">The recommendations clarify when outsourcing to the cloud is permitted, apply a principles-based approach towards measuring risk from a technology-neutral perspective, and strive towards greater harmonization within Europe and beyond.</span></span>

<span data-ttu-id="2df59-109">EBA 建议于 2018 年7 月生效，并以欧洲银行监察委员会 2006 年发布的一般外包准则为基础，使之更加明确。</span><span class="sxs-lookup"><span data-stu-id="2df59-109">The EBA recommendations took effect in July 2018, and they build on and add clarity to the general outsourcing guidelines published in 2006 by the Committee of European Banking Supervisors.</span></span> <span data-ttu-id="2df59-110">实际上，这些建议是在 Microsoft 提供了实质性反馈意见的磋商期之后发布的。</span><span class="sxs-lookup"><span data-stu-id="2df59-110">In fact, the issuance of these recommendations comes after a consultation period during which Microsoft provided substantive feedback.</span></span> <span data-ttu-id="2df59-111">许多最终建议都考虑了 Microsoft 向 EBA 提供的意见。</span><span class="sxs-lookup"><span data-stu-id="2df59-111">Many of the final recommendations account for comments Microsoft provided to the EBA.</span></span>

## <a name="microsoft-and-the-eba"></a><span data-ttu-id="2df59-112">Microsoft 和 EBA</span><span class="sxs-lookup"><span data-stu-id="2df59-112">Microsoft and the EBA</span></span>

<span data-ttu-id="2df59-113">为帮助欧盟金融机构遵循欧洲银行管理局 (EBA) 有关采用云的建议，Microsoft 发布了[欧洲银行管理局指南首次解决了云计算](https://aka.ms/FinServ-Guide-EuBankAuth)。</span><span class="sxs-lookup"><span data-stu-id="2df59-113">To help financial institutions in the EU follow the European Banking Authority (EBA) recommendations for cloud adoption, Microsoft published [European Banking Authority Guidance Addresses Cloud Computing for the First Time](https://aka.ms/FinServ-Guide-EuBankAuth).</span></span> <span data-ttu-id="2df59-114">本文档介绍了关键要求，并说明了如何使用 Microsoft Azure 和 Microsoft 365 来满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="2df59-114">This document addresses key requirements and explains how Microsoft Azure and Microsoft 365 can be used to satisfy them.</span></span> <span data-ttu-id="2df59-115">本指南可帮助金融机构采用 Azure 和 Microsoft，并确保他们能够满足 EBA 框架下的义务。</span><span class="sxs-lookup"><span data-stu-id="2df59-115">The guidance can help financial institutions adopt Azure and Microsoft with the confidence that they can meet their obligations under the EBA framework.</span></span>

<span data-ttu-id="2df59-116">Microsoft 指南逐条解释了每个 EBA 建议：</span><span class="sxs-lookup"><span data-stu-id="2df59-116">The Microsoft guidance addresses, point by point, each of the EBA recommendations:</span></span>

- <span data-ttu-id="2df59-117">审核权限。</span><span class="sxs-lookup"><span data-stu-id="2df59-117">Audit rights.</span></span> <span data-ttu-id="2df59-118">Microsoft 在其行业领先的“金融服务修正案”中为客户提供合同审核权，为监管机构提供检查权。</span><span class="sxs-lookup"><span data-stu-id="2df59-118">Microsoft provides contractual audit rights for customers and rights of examination for regulators in its industry-leading Financial Services Amendment.</span></span>
- <span data-ttu-id="2df59-119">有关外包的通知。</span><span class="sxs-lookup"><span data-stu-id="2df59-119">Notification regarding outsourcing.</span></span> <span data-ttu-id="2df59-120">Microsoft 可帮助客户将要外包的重要活动通知给监管机构。</span><span class="sxs-lookup"><span data-stu-id="2df59-120">Microsoft can assist customers with notifying regulators of material activities to be outsourced.</span></span>
- <span data-ttu-id="2df59-121">数据驻留。</span><span class="sxs-lookup"><span data-stu-id="2df59-121">Data residency.</span></span> <span data-ttu-id="2df59-122">Microsoft 拥有 36 个区域（其中欧洲 6 个），在全球云服务提供商中数据中心数量最多。</span><span class="sxs-lookup"><span data-stu-id="2df59-122">With 36 regions, including six in Europe, Microsoft offers the largest number of datacenters worldwide of any cloud service provider.</span></span> <span data-ttu-id="2df59-123">组织无需在欧洲托管数据即可在一个区域部署工作负载。</span><span class="sxs-lookup"><span data-stu-id="2df59-123">Organizations can deploy workloads in one region without being required to host data in Europe.</span></span>
- <span data-ttu-id="2df59-124">有关分包商的通知。</span><span class="sxs-lookup"><span data-stu-id="2df59-124">Notification regarding subcontractors.</span></span> <span data-ttu-id="2df59-125">Microsoft 在行业中率先采用合同承诺，提前 180 天向客户通知新分包商，如果客户不认可指定的新分包商，其有权终止。</span><span class="sxs-lookup"><span data-stu-id="2df59-125">Microsoft leads the industry with a contractual commitment to provide customers with 180-day notice of new subcontractors, and a right to terminate if the customer does not approve of the appointment of a new subcontractor.</span></span>
- <span data-ttu-id="2df59-126">业务连续性。</span><span class="sxs-lookup"><span data-stu-id="2df59-126">Business continuity.</span></span> <span data-ttu-id="2df59-127">Microsoft 在“金融服务修正案”中提供了业务连续性和解决方案规定，包括希望通过 Microsoft 咨询服务提供过渡帮助的意愿。</span><span class="sxs-lookup"><span data-stu-id="2df59-127">Microsoft provides business continuity and resolution provisions in our Financial Services Amendment, including the willingness to provide transition assistance through Microsoft Consulting Services.</span></span>
- <span data-ttu-id="2df59-128">风险评估和安全监控。</span><span class="sxs-lookup"><span data-stu-id="2df59-128">Risk assessment and security monitoring.</span></span> <span data-ttu-id="2df59-129">Microsoft 允许客户自行进行风险评估，并提供工具和仪表板，以便他们可以监督和监控我们的云服务。</span><span class="sxs-lookup"><span data-stu-id="2df59-129">Microsoft enables customers to conduct their own risk assessments and provides tools and dashboards so they can supervise and monitor our cloud services.</span></span>

<span data-ttu-id="2df59-130">针对欧盟的金融机构，Microsoft 还发布了根据 EBA 指南建立的清单：[面向采用 Microsoft 云的金融机构的风险评估和合规性指南](https://aka.ms/RiskGovernanceGuide)。</span><span class="sxs-lookup"><span data-stu-id="2df59-130">For financial institutions in the EU, Microsoft has also published [Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud](https://aka.ms/RiskGovernanceGuide), a checklist modeled after EBA guidance.</span></span> <span data-ttu-id="2df59-131">它解释了如何建立经优化以符合法规要求的管理模型，并高效评估使用 Microsoft 云服务的风险，然后提交供监管审批。</span><span class="sxs-lookup"><span data-stu-id="2df59-131">It explains how to establish a governance model optimized to meet regulatory requirements, and efficiently evaluate the risks of using Microsoft cloud services, followed by submission for regulatory approval.</span></span> <span data-ttu-id="2df59-132">我们的指南包括一个需要在法规申报中回答的问题列表，借鉴并响应了 EBA 关于外包给云服务提供商的指南。</span><span class="sxs-lookup"><span data-stu-id="2df59-132">Our guide includes a list of questions to be answered in a regulatory submission that are drawn from, and responsive to, EBA guidance on outsourcing to cloud service providers.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="2df59-133">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="2df59-133">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="2df59-134">Azure</span><span class="sxs-lookup"><span data-stu-id="2df59-134">Azure</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="2df59-135">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2df59-135">Microsoft 365</span></span>](https://aka.ms/o365-compliance-framework)

## <a name="how-to-implement"></a><span data-ttu-id="2df59-136">如何实现</span><span class="sxs-lookup"><span data-stu-id="2df59-136">How to implement</span></span>

- <span data-ttu-id="2df59-137">[对 EBA 指南的响应](https://aka.ms/FinServ-Guide-EuBankAuth)：Microsoft 指南有助于欧盟金融机构遵循 EBA 在采用云方面的建议。</span><span class="sxs-lookup"><span data-stu-id="2df59-137">[Response to EBA guidance](https://aka.ms/FinServ-Guide-EuBankAuth): Microsoft guidance helps EU financial institutions follow EBA recommendations for cloud adoption.</span></span>
- <span data-ttu-id="2df59-138">[金融用例](https://docs.microsoft.com/azure/industry/financial/)：借助用例概述、教程和其他资源，构建适合金融服务的 Azure 解决方案。</span><span class="sxs-lookup"><span data-stu-id="2df59-138">[Financial use cases](https://docs.microsoft.com/azure/industry/financial/): Use-case overviews, tutorials, and other resources to build Azure solutions for financial services.</span></span>
- <span data-ttu-id="2df59-139">[金融合规性计划](https://aka.ms/FSCP-Print)：金融机构可在使用 Microsoft 云服务的风险评估方面获取帮助。</span><span class="sxs-lookup"><span data-stu-id="2df59-139">[Financial Compliance Program](https://aka.ms/FSCP-Print): Financial institutions can get help assessing the risks of using Microsoft cloud services.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="2df59-140">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="2df59-140">Frequently asked questions</span></span>

<span data-ttu-id="2df59-141">**提交到监管机构的内容应包含哪些信息？**</span><span class="sxs-lookup"><span data-stu-id="2df59-141">**What information should be included in a submission to regulators?**</span></span>

<span data-ttu-id="2df59-142">Microsoft 发布的[面向采用 Microsoft 云的金融机构的风险评估和合规性指南](https://aka.ms/RiskGovernanceGuide)，提供了有关 EBA 指南建议在法规申报中回答的问题清单，并提供了有关如何回答这些问题的建议。</span><span class="sxs-lookup"><span data-stu-id="2df59-142">The Microsoft publication, [Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud](https://aka.ms/RiskGovernanceGuide), offers a checklist of questions that the EBA guidance recommends answering in a regulatory submission, and provides suggestions on how to answer those questions.</span></span>

## <a name="resources"></a><span data-ttu-id="2df59-143">资源</span><span class="sxs-lookup"><span data-stu-id="2df59-143">Resources</span></span>

- [<span data-ttu-id="2df59-144">Microsoft 服务信任门户</span><span class="sxs-lookup"><span data-stu-id="2df59-144">Microsoft Service Trust Portal</span></span>](https://aka.ms/STP)
- [<span data-ttu-id="2df59-145">Microsoft 金融服务合规性计划</span><span class="sxs-lookup"><span data-stu-id="2df59-145">Microsoft Financial Services Compliance Program</span></span>](https://aka.ms/FSCP-Print)
- [<span data-ttu-id="2df59-146">Microsoft 商业云服务和金融服务</span><span class="sxs-lookup"><span data-stu-id="2df59-146">Microsoft business cloud services and financial services</span></span>](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [<span data-ttu-id="2df59-147">Azure 中的金融服务合规性</span><span class="sxs-lookup"><span data-stu-id="2df59-147">Financial services compliance in Azure</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [<span data-ttu-id="2df59-148">Azure 金融服务云风险评估工具</span><span class="sxs-lookup"><span data-stu-id="2df59-148">Azure Financial Services Cloud Risk Assessment Tool</span></span>](https://aka.ms/FFIEC-CSDT)
- [<span data-ttu-id="2df59-149">Microsoft 金融服务博客</span><span class="sxs-lookup"><span data-stu-id="2df59-149">Microsoft Financial Services Blog</span></span>](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [<span data-ttu-id="2df59-150">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="2df59-150">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="2df59-151">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="2df59-151">Download the offering backgrounder</span></span>

<span data-ttu-id="2df59-152">需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="2df59-152">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="2df59-153">请下载 [PDF](https://download.microsoft.com/download/A/9/3/A93DEE11-4758-4E03-8035-D8C5843B70C2/EBA-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="2df59-153">Download the [PDF](https://download.microsoft.com/download/A/9/3/A93DEE11-4758-4E03-8035-D8C5843B70C2/EBA-Compliance.pdf).</span></span>

