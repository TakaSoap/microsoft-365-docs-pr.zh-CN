---
title: 支付卡行业 (PCI) 数据安全标准 (DSS)
description: Azure、SharePoint Online 和 OneDrive for Business 符合支付卡行业数据安全标准 Level 1 3.2 版。
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
ms.openlocfilehash: cb4d1a4c4632763506fd2d3b05431acb9233f744
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071960"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a><span data-ttu-id="fbdc6-104">支付卡行业 (PCI) 数据安全标准 (DSS)</span><span class="sxs-lookup"><span data-stu-id="fbdc6-104">Payment Card Industry (PCI) Data Security Standard (DSS)</span></span>

## <a name="pci-dss-overview"></a><span data-ttu-id="fbdc6-105">PCI DSS 概述</span><span class="sxs-lookup"><span data-stu-id="fbdc6-105">PCI DSS overview</span></span>

<span data-ttu-id="fbdc6-p101">支付卡行业（PCI）数据安全标准（DSS）是一个全球性的信息安全标准，旨在通过加强对信用卡数据的控制来防止欺诈。任何规模的组织如果接受五大信用卡品牌（Visa、MasterCard、American Express、Discover和日本信用局（JCB））的支付卡，都必须遵守PCI DSS标准。任何存储、处理或传输支付和持卡人数据的组织都必须遵守PCI DSS标准。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p101">The Payment Card Industry (PCI) Data Security Standards (DSS) is a global information security standard designed to prevent fraud through increased control of credit card data. Organizations of all sizes must follow PCI DSS standards if they accept payment cards from the five major credit card brands — Visa, MasterCard, American Express, Discover, and the Japan Credit Bureau (JCB). Compliance with PCI DSS is required for any organization that stores, processes, or transmits payment and cardholder data.</span></span>

## <a name="microsoft-and-pci-dss"></a><span data-ttu-id="fbdc6-109">Microsoft 和 PCI DSS</span><span class="sxs-lookup"><span data-stu-id="fbdc6-109">Microsoft and PCI DSS</span></span>

<span data-ttu-id="fbdc6-p102">Microsoft 使用经批准的合格安全评估师（QSA）完成了年度 PCI DSS 评估。审计人员审查了 Microsoft Azure、Microsoft OneDrive for Business 和 Microsoft SharePoint Online 环境，其中包括验证基础设施、开发、运营、管理、支持和范围内服务。PCI DSS 根据交易量指定了四个级别的合规性。认证 Azure、OneDrive for Business 和 SharePoint Online 为符合 PCI DSS 3.2 版的第一级服务提供商（交易量最高的级别 - 每年超过 600 万）。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p102">Microsoft completed an annual PCI DSS assessment using an approved Qualified Security Assessor (QSA). The auditors reviewed Microsoft Azure, Microsoft OneDrive for Business, and Microsoft SharePoint Online  environments, which include validating the infrastructure, development, operations, management, support, and in-scope services. The PCI DSS designates four levels of compliance based on transaction volume. Azure, OneDrive for Business, and SharePoint Online are certified as compliant under PCI DSS version 3.2 at Service Provider Level 1 (the highest volume of transactions — more than 6 million a year).</span></span>

<span data-ttu-id="fbdc6-p103">评估的结果是向客户提供合规证明（AoC），并由质检局出具合规报告（RoC）。合规的有效期限从通过审计并收到评估员的合规证明开始，到合规证明签署之日起一年。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p103">The assessment results in an Attestation of Compliance (AoC), which is available to customers and Report on Compliance (RoC) issued by the QSA. The effective period for compliance begins upon passing the audit and receiving the AoC from the assessor and ends one year from the date the AoC is signed.</span></span> 

<span data-ttu-id="fbdc6-116">希望开发持卡人环境或卡处理服务的客户可以在许多底层部分中使用这些验证，从而减少获取自己的 PCI DSS 认证的相关工作和成本。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-116">Customers who want to develop a cardholder environment or card processing service can use these validations in many of the underlying portions, thereby reducing the associated effort and costs of getting their own PCI DSS certification.</span></span>

<span data-ttu-id="fbdc6-p104">重要的是要明白，Azure、OneDrive for Business 和 SharePoint Online 的 PCI DSS 合规性状态不会自动转化为客户在这些平台上构建或托管的服务的 PCI DSS 认证。客户有责任确保他们达到 PCI DSS 要求的合规性。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p104">It is important to understand that PCI DSS compliance status for Azure, OneDrive for Business, and SharePoint Online not automatically translate to PCI DSS certification for the services that customers build or host on these platforms. Customers are responsible for ensuring that they achieve compliance with PCI DSS requirements.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="fbdc6-119">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="fbdc6-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="fbdc6-120">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="fbdc6-120">Azure and Azure Government</span></span>](https://azure.microsoft.com/global-infrastructure/government/)
- <span data-ttu-id="fbdc6-121">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="fbdc6-121">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="fbdc6-122">Flow 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="fbdc6-122">Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="fbdc6-123">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="fbdc6-123">Microsoft Graph</span></span>
- <span data-ttu-id="fbdc6-124">Intune</span><span class="sxs-lookup"><span data-stu-id="fbdc6-124">Intune</span></span>
- [<span data-ttu-id="fbdc6-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fbdc6-125">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- <span data-ttu-id="fbdc6-126">PowerApps 云服务，作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="fbdc6-126">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="fbdc6-127">Power BI 云服务，无论是独立服务还是随 Office 365 品牌计划或套件提供的服务</span><span class="sxs-lookup"><span data-stu-id="fbdc6-127">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="fbdc6-128">OneDrive for Business 和 SharePoint Online（仅限美国）</span><span class="sxs-lookup"><span data-stu-id="fbdc6-128">OneDrive for Business and SharePoint Online (United States only)</span></span>

## <a name="audit-reports-and-certificates"></a><span data-ttu-id="fbdc6-129">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="fbdc6-129">Audit, reports, and certificates</span></span>

- [<span data-ttu-id="fbdc6-130">Azure PCI DSS 合规性证明 (AoC)</span><span class="sxs-lookup"><span data-stu-id="fbdc6-130">Azure PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/azure-pci)
- [<span data-ttu-id="fbdc6-131">OneDrive for Business 和 SharePoint Online PCI DSS 合规性证明 (AoC)</span><span class="sxs-lookup"><span data-stu-id="fbdc6-131">OneDrive for Business and SharePoint Online PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a><span data-ttu-id="fbdc6-132">获取 Azure 上运行的 PCI DSS 解决方案</span><span class="sxs-lookup"><span data-stu-id="fbdc6-132">Get your PCI DSS solution running on Azure</span></span>

<span data-ttu-id="fbdc6-p105">借助 Azure 安全性与合规性 PCI DSS 蓝图，在云中更快地构建和部署 PCI DSS 解决方案。获取参考架构、部署指导、控制实施映射、自动脚本等。[开始使用 Azure PCI DSS 蓝图](https://aka.ms/pciblueprint)。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p105">Build and deploy your PCI DSS solution in the cloud even faster with the Azure Security and Compliance PCI DSS Blueprint. Get reference architectures, deployment guidance, control implementation mappings, automated scripts and more. [Start using the Azure PCI DSS Blueprint](https://aka.ms/pciblueprint).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="fbdc6-136">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="fbdc6-136">Frequently asked questions</span></span>

<span data-ttu-id="fbdc6-137">**为什么合规性证明 (AoC) 封面上写着“2018 年 6 月”？**</span><span class="sxs-lookup"><span data-stu-id="fbdc6-137">**Why does the Attestation of Compliance (AoC) cover page say 'June 2018'?**</span></span>

<span data-ttu-id="fbdc6-p106">封面上 2018 年 6 月的日期是 AoC 模板发布的时间。关于评估日期，请参考第2节。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p106">The June 2018 date on the cover page is when the AoC template was published. Refer to Section 2 for the date of the assessment.</span></span>

<span data-ttu-id="fbdc6-140">**为什么会有多个 Azure 合规性证明 (AoC)？**</span><span class="sxs-lookup"><span data-stu-id="fbdc6-140">**Why are there multiple Azure Attestations of Compliance (AoCs)?**</span></span>

<span data-ttu-id="fbdc6-p107">Azure AoC 包有对应 Azure 公有云、德国云和政府云的 AoC。客户应使用与其 Azure 环境相对应的 AoC。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p107">The Azure AoC package has AoCs corresponding to Azure Public, Germany, and Government cloud. Customers should use the AoC that corresponds with their Azure environment.</span></span>  

<span data-ttu-id="fbdc6-143">**PA DSS 与 PCI DSS 之间有何关系？**</span><span class="sxs-lookup"><span data-stu-id="fbdc6-143">**What is the relationship between the PA DSS and PCI DSS?**</span></span>

<span data-ttu-id="fbdc6-p108">支付应用数据安全标准（PA DSS）是一套符合 PCI DSS 的要求，并取代了 Visa 的支付应用最佳实践，整合了其他主要发卡机构的合规要求。PA DSS 帮助软件供应商开发第三方应用程序，这些应用程序存储、处理或传输持卡人支付数据，作为卡授权或结算流程的一部分。零售商必须使用经过 PA DSS 认证的应用程序来有效地实现其 PCI DSS 的合规性。PA DSS 不适用于 Azure。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p108">The Payment Application Data Security Standard (PA DSS) is a set of requirements that comply with the PCI DSS, and replaces Visa's Payment Application Best Practices, and consolidates the compliance requirements of the other primary card issuers. The PA DSS helps software vendors develop third-party applications that store, process, or transmit cardholder payment data as part of a card authorization or settlement process. Retailers must use PA DSS certified applications to efficiently achieve their PCI DSS compliance. The PA DSS does not apply to Azure.</span></span>

<span data-ttu-id="fbdc6-148">**什么是收单机构，Azure 是否使用收单机构？**</span><span class="sxs-lookup"><span data-stu-id="fbdc6-148">**What is an acquirer and does Azure use one?**</span></span>

<span data-ttu-id="fbdc6-p109">Acquirer 是处理支付卡交易的银行或其他实体。Azure 不提供支付卡处理服务，因此不使用 Acquirer。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p109">An acquirer is a bank or other entity that processes payment card transactions. Azure does not offer payment card processing as a service and thus does not use an acquirer.</span></span>

<span data-ttu-id="fbdc6-151">**PCI DSS 适用于哪些组织和商家？**</span><span class="sxs-lookup"><span data-stu-id="fbdc6-151">**To what organizations and merchants does the PCI DSS apply?**</span></span>

<span data-ttu-id="fbdc6-p110">PCI DSS 适用于任何接受、传输或存储持卡人数据的公司，无论其规模大小、交易数量多少。也就是说，如果有客户使用信用卡或借记卡向公司付款，则适用 PCI DSS 要求。根据 12 个月内的总交易量，公司将在四个级别中的一个进行验证。第 1 级适用于每年处理超过 600 万笔交易的公司；第 2 级适用于 100 万至 600 万笔交易；第 3 级适用于 2 万至 100 万笔交易；第 4 级适用于少于 2 万笔的交易。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p110">PCI DSS applies to any company, no matter the size, or number of transactions, that accepts, transmits, or stores cardholder data. That is, if any customer ever pays a company using a credit or debit card, then the PCI DSS requirements apply. Companies are validated at one of four levels based on the total transaction volume over a 12-month period. Level 1 is for companies that process over 6 million transactions a year; Level 2 for 1 million to 6 million transactions; Level 3 is for 20,000 to 1 million transactions; and Level 4 is for fewer than 20,000 transactions.</span></span>

<span data-ttu-id="fbdc6-156">**我的组织从何处着手开展针对部署在 Azure 上的解决方案的 PCI DSS 合规工作？**</span><span class="sxs-lookup"><span data-stu-id="fbdc6-156">**Where do I begin my organization's PCI DSS compliance efforts for a solution deployed on Azure?**</span></span>

<span data-ttu-id="fbdc6-p111">PCI 安全标准委员会提供的信息是了解具体合规要求的好地方。该委员会为商家和参与支付卡处理的其他人员发布了[PCI DSS快速参考指南](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)。该指南解释了 PCI DSS 是如何帮助保护支付卡交易环境以及该如何应用它。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p111">The information that the PCI Security Standards Council makes available is a good place to learn about specific compliance requirements. The council publishes the [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) for merchants and others involved in payment card processing. The guide explains how the PCI DSS can help protect a payment card transaction environment and how to apply it.</span></span>

<span data-ttu-id="fbdc6-p112">合规性涉及多个因素，包括评估未托管在 Azure 上的系统和流程。个别要求根据使用的 Azure 服务及其在解决方案中的应用方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p112">Compliance involves several factors, including assessing the systems and processes not hosted on Azure. Individual requirements vary based on which Azure services are used and how they are employed within the solution.</span></span>

<span data-ttu-id="fbdc6-162">**OneDrive for Business 和 SharePoint Online 是否有在美国境外实现 PCI DSS 合规性的计划？**</span><span class="sxs-lookup"><span data-stu-id="fbdc6-162">**Are there plans for OneDrive for Business and SharePoint Online to be PCI DSS-compliant outside of the United States?**</span></span>

<span data-ttu-id="fbdc6-p113">目前，OneDrive for Business 和 SharePoint 在线仅在美国（US）符合 PCI-DSS 标准。Microsoft 将评估美国以外地区的要求和时间表，并在其他地区加入路线图时提供更新。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p113">Currently OneDrive for Business and SharePoint Online is PCI-DSS compliant only in the United States (US). Microsoft will evaluate the requirements and timelines for regions outside of US and provide updates when and if other regions are added to the roadmap.</span></span>

<span data-ttu-id="fbdc6-165">**OneDrive for Business 和 SharePoint Online 的范围内是什么？**</span><span class="sxs-lookup"><span data-stu-id="fbdc6-165">**What is in-scope for OneDrive for Business and SharePoint Online?**</span></span>

<span data-ttu-id="fbdc6-166">目前，只有上载到 OneDrive for Business 和 SharePoint Online 的文件和文档符合 PCI DSS。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-166">Currently, only files and documents uploaded to OneDrive for Business and SharePoint Online will be complaint with PCI DSS.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="fbdc6-167">使用 Microsoft 合规性管理器评估风险</span><span class="sxs-lookup"><span data-stu-id="fbdc6-167">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="fbdc6-p114">[Microsoft 合规性管理器](compliance-manager.md)是 [Microsoft 365 合规中心](microsoft-365-compliance-center.md)的一项功能，可帮助你了解组织的合规态势，并采取行动以帮助降低风险。合规性管理器提供了一个高级模板，用于构建该法规的评估。在合规性管理器的 **评估模板** 页面中找到该模板。了解如何 [在合规管理器中构建评估](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="fbdc6-p114">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks. Compliance Manager offers a premium template for building an assessment for this regulation. Find the template in the **assessment templates** page in Compliance Manager. Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="fbdc6-172">资源</span><span class="sxs-lookup"><span data-stu-id="fbdc6-172">Resources</span></span>

- [<span data-ttu-id="fbdc6-173">支付卡行业数据安全标准委员会</span><span class="sxs-lookup"><span data-stu-id="fbdc6-173">PCI Security Standards Council</span></span>](https://www.pcisecuritystandards.org/)
- [<span data-ttu-id="fbdc6-174">PCI 数据安全标准</span><span class="sxs-lookup"><span data-stu-id="fbdc6-174">PCI Data Security Standard</span></span>](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [<span data-ttu-id="fbdc6-175">Azure PCI DSS 3.2.1 蓝图</span><span class="sxs-lookup"><span data-stu-id="fbdc6-175">Azure PCI DSS 3.2.1 Blueprint</span></span>](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [<span data-ttu-id="fbdc6-176">PCI DSS 快速参考指南</span><span class="sxs-lookup"><span data-stu-id="fbdc6-176">PCI DSS Quick Reference Guide</span></span>](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [<span data-ttu-id="fbdc6-177">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="fbdc6-177">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
