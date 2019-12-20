---
title: 健康信息信任联盟（HITRUST）常见安全框架（CSF）
description: Azure 和 Office 365 认证为健康信息信任联盟（HITRUST）常见安全框架（CSF）。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 9b0448a3ed5cf36a909ebb14e0aadf2b8ac96610
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40804795"
---
# <a name="health-information-trust-alliance-hitrust-common-security-framework-csf"></a><span data-ttu-id="f6859-104">健康信息信任联盟（HITRUST）常见安全框架（CSF）</span><span class="sxs-lookup"><span data-stu-id="f6859-104">Health Information Trust Alliance (HITRUST) Common Security Framework (CSF)</span></span>

## <a name="hitrust--csf-overview"></a><span data-ttu-id="f6859-105">HITRUST — CSF 概述</span><span class="sxs-lookup"><span data-stu-id="f6859-105">HITRUST — CSF overview</span></span>

<span data-ttu-id="f6859-106">健康信息信任联盟（HITRUST）是由医疗保健行业的代表管辖的组织。</span><span class="sxs-lookup"><span data-stu-id="f6859-106">The Health Information Trust Alliance (HITRUST) is an organization governed by representatives from the healthcare industry.</span></span> <span data-ttu-id="f6859-107">HITRUST 创建和维护通用安全框架（CSF），这是一种 certifiable 框架，可帮助医疗保健组织及其提供商以一致且简化的方式展示其安全性和合规性。</span><span class="sxs-lookup"><span data-stu-id="f6859-107">HITRUST created and maintains the Common Security Framework (CSF), a certifiable framework to help healthcare organizations and their providers demonstrate their security and compliance in a consistent and streamlined manner.</span></span>

<span data-ttu-id="f6859-108">CSF 建立在 HIPAA 和高科技法案之上，这是美国医疗保健法律，已为使用、公开和保护单独可识别的健康信息提供了要求，并强制实施不合规。</span><span class="sxs-lookup"><span data-stu-id="f6859-108">The CSF builds on HIPAA and the HITECH Act, which are US healthcare laws that have established requirements for the use, disclosure, and safeguarding of individually identifiable health information, and that enforce noncompliance.</span></span> <span data-ttu-id="f6859-109">HITRUST 提供了一个基准，即标准化合规性框架、评估和认证过程，以供云服务提供商和所涵盖的运行状况实体对合规性进行衡量。</span><span class="sxs-lookup"><span data-stu-id="f6859-109">HITRUST provides a benchmark — a standardized compliance framework, assessment, and certification process — against which cloud service providers and covered health entities can measure compliance.</span></span> <span data-ttu-id="f6859-110">CSF 还将此类现有框架中特定于医疗保健的安全、隐私和其他法规要求作为支付卡行业数据安全标准（[PCI-DSS](https://www.microsoft.com/trustcenter/compliance/pci)）、 [ISO/IEC 27001](https://www.microsoft.com/trustcenter/compliance/iso-iec-27001)信息安全管理标准以及可接受的最低风险标准（[MARS-E](https://www.microsoft.com/trustcenter/compliance/mars-e)）结合在一起。</span><span class="sxs-lookup"><span data-stu-id="f6859-110">The CSF also incorporates healthcare-specific security, privacy, and other regulatory requirements from such existing frameworks as the Payment Card Industry Data Security Standard ([PCI-DSS](https://www.microsoft.com/trustcenter/compliance/pci)), [ISO/IEC 27001](https://www.microsoft.com/trustcenter/compliance/iso-iec-27001) information security management standards, and Minimum Acceptable Risk Standards for Exchanges ([MARS-E](https://www.microsoft.com/trustcenter/compliance/mars-e)).</span></span>

<span data-ttu-id="f6859-111">CSF 分为19个不同的域，包括 endpoint protection、移动设备安全性和访问控制。</span><span class="sxs-lookup"><span data-stu-id="f6859-111">The CSF is divided into 19 different domains, including endpoint protection, mobile device security, and access control.</span></span> <span data-ttu-id="f6859-112">HITRUST 针对这些控制措施证明 IT 产品。</span><span class="sxs-lookup"><span data-stu-id="f6859-112">HITRUST certifies IT offerings against these controls.</span></span> <span data-ttu-id="f6859-113">HITRUST 还根据组织、系统和法规因素，改编对组织风险的证书要求。</span><span class="sxs-lookup"><span data-stu-id="f6859-113">HITRUST also adapts requirements for certification to the risks of an organization based on organizational, system, and regulatory factors.</span></span>

<span data-ttu-id="f6859-114">健康信息信任联盟（HITRUST）常见安全框架（CSF）</span><span class="sxs-lookup"><span data-stu-id="f6859-114">Health Information Trust Alliance (HITRUST) Common Security Framework (CSF)</span></span>

<span data-ttu-id="f6859-115">HITRUST 提供了三个确定性或评估级别：自我评估、CSF 验证和 CSF 认证。</span><span class="sxs-lookup"><span data-stu-id="f6859-115">HITRUST offers three degrees of assurance, or levels of assessment: self-assessment, CSF validated, and CSF-certified.</span></span> <span data-ttu-id="f6859-116">每个级别的生成都在下面的项中增加了严格。</span><span class="sxs-lookup"><span data-stu-id="f6859-116">Each level builds with increasing rigor on the one below it.</span></span> <span data-ttu-id="f6859-117">具有最高级别的 CSF 认证的组织满足 CSF 的所有认证要求。</span><span class="sxs-lookup"><span data-stu-id="f6859-117">An organization with the highest level, CSF-certified, meets all the certification requirements of the CSF.</span></span> <span data-ttu-id="f6859-118">Microsoft Azure 和 Office 365 是用于接收 HITRUST CSF 认证的第一个超大型云服务。</span><span class="sxs-lookup"><span data-stu-id="f6859-118">Microsoft Azure and Office 365 are the first hyperscale cloud services to receive certification for the HITRUST CSF.</span></span> <span data-ttu-id="f6859-119">Coalfire，HITRUST 评估员公司，根据 Azure 和 Office 365 如何实现安全、隐私和管理法规要求来保护敏感信息，从而执行评估。</span><span class="sxs-lookup"><span data-stu-id="f6859-119">Coalfire, a HITRUST assessor firm, performed the assessments based on how Azure and Office 365 implement security, privacy, and regulatory requirements to protect sensitive information.</span></span> <span data-ttu-id="f6859-120">Microsoft 支持 HITRUST 共享责任计划。</span><span class="sxs-lookup"><span data-stu-id="f6859-120">Microsoft supports the HITRUST Shared Responsibility Program.</span></span>

<span data-ttu-id="f6859-121">了解如何使用我们的 Azure 安全性和合规性蓝图加快您的 HITRUST 部署。</span><span class="sxs-lookup"><span data-stu-id="f6859-121">Learn how to accelerate your HITRUST deployment with our Azure Security and Compliance Blueprint.</span></span>

[<span data-ttu-id="f6859-122">下载 Microsoft Azure HITRUST 客户责任矩阵（CRM）蓝图9.0 版 d</span><span class="sxs-lookup"><span data-stu-id="f6859-122">Download the Microsoft Azure HITRUST Customer Responsibility Matrix (CRM) blueprint v9.0d</span></span>](https://servicetrust.microsoft.com/ViewPage/Blueprint?command=Download&downloadType=Document&downloadId=3ccde498-4761-4be0-be8b-cd8d379a3a4f&docTab=fc060920-cdb8-11e7-bacf-0bf52b09d912_Healthcare_Blueprint)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="f6859-123">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="f6859-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="f6859-124">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="f6859-124">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="f6859-125">Intune</span><span class="sxs-lookup"><span data-stu-id="f6859-125">Intune</span></span>
- [<span data-ttu-id="f6859-126">Office 365 和 Office 365 US 政府计划</span><span class="sxs-lookup"><span data-stu-id="f6859-126">Office 365 and Office 365 U.S. Government</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="f6859-127">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="f6859-127">Audits, reports, and certificates</span></span>

<span data-ttu-id="f6859-128">Azure 和 Office 365 的 HITRUST CSF 认证的有效期为两年。</span><span class="sxs-lookup"><span data-stu-id="f6859-128">The HITRUST CSF certification of Azure and Office 365 is valid for two years.</span></span>

- [<span data-ttu-id="f6859-129">Azure HITRUST 证书颁发信</span><span class="sxs-lookup"><span data-stu-id="f6859-129">Azure HITRUST Letter of Certification</span></span>](https://aka.ms/AzureHiTrustLetterofCertification)
- [<span data-ttu-id="f6859-130">Office 365 HITRUST 证书颁发信</span><span class="sxs-lookup"><span data-stu-id="f6859-130">Office 365 HITRUST Letter of Certification</span></span>](https://aka.ms/O365HITRUSTcertification)

## <a name="accelerate-your-deployment-of-hipaahitrust-solutions-on-azure"></a><span data-ttu-id="f6859-131">在 Azure 上加快对 HIPAA/HITRUST 解决方案的部署</span><span class="sxs-lookup"><span data-stu-id="f6859-131">Accelerate your deployment of HIPAA/HITRUST solutions on Azure</span></span>

<span data-ttu-id="f6859-132">首先利用云针对运行状况数据解决方案与 Azure 安全性和合规性蓝图（HIPAA/HITRUST 运行状况数据和 AI）的优势。</span><span class="sxs-lookup"><span data-stu-id="f6859-132">Get a head start on taking advantage of the benefits of the cloud for health data solutions with the Azure Security and Compliance Blueprint — HIPAA/HITRUST Health Data and AI.</span></span> <span data-ttu-id="f6859-133">此蓝图提供的工具和指南可帮助您立即开始构建 HIPAA/HITRUST 解决方案。</span><span class="sxs-lookup"><span data-stu-id="f6859-133">This blueprint provides tools and guidance to get you started building HIPAA/HITRUST solutions today.</span></span>

[<span data-ttu-id="f6859-134">开始使用 Azure HIPAA/HITRUST 蓝图</span><span class="sxs-lookup"><span data-stu-id="f6859-134">Start using the Azure HIPAA/HITRUST Blueprint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2100613)

## <a name="accelerate-your-hipaahitrust-compliance-when-using-office-365"></a><span data-ttu-id="f6859-135">使用 Office 365 时，提高您的 HIPAA/HITRUST 合规性</span><span class="sxs-lookup"><span data-stu-id="f6859-135">Accelerate your HIPAA/HITRUST compliance when using Office 365</span></span>

<span data-ttu-id="f6859-136">使用 Office 365，通过合规性管理器以安全且合规的方式管理运行状况信息，这使您能够对诸如 HIPAA 和安全控制框架（如 NIST CSF 和 NIST 800-53）执行风险评估（如卫生法规）。</span><span class="sxs-lookup"><span data-stu-id="f6859-136">Use Office 365 to manage health information in a secure and compliant way with Compliance Manager, which enables you to perform risk assessments against health regulations like HIPAA and security control frameworks like NIST CSF and NIST 800-53.</span></span> <span data-ttu-id="f6859-137">您可以按照分步指南操作，了解如何实施和维护可帮助您满足医疗保健合规性义务的数据保护控制。</span><span class="sxs-lookup"><span data-stu-id="f6859-137">You can follow step-by-step guidance to know how to implement and maintain data protection controls that help you meet healthcare compliance obligations.</span></span>

[<span data-ttu-id="f6859-138">开始使用合规性管理器</span><span class="sxs-lookup"><span data-stu-id="f6859-138">Start using Compliance Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=862650)

## <a name="collaborate-with-microsoft-in-the-hitrust-shared-responsibility-program"></a><span data-ttu-id="f6859-139">在 HITRUST 共享责任计划中与 Microsoft 协作</span><span class="sxs-lookup"><span data-stu-id="f6859-139">Collaborate with Microsoft in the HITRUST Shared Responsibility Program</span></span>

<span data-ttu-id="f6859-140">通过在 HITRUST MyCSF 工具中使用 Azure 的完全继承或共享责任控件预填充你的评估，加快为 Microsoft Azure 上的解决方案实现 HITRUST 合规性，并在你的计算机上与 Microsoft 协作因素.</span><span class="sxs-lookup"><span data-stu-id="f6859-140">Accelerate achieving HITRUST compliance for your solution hosted on Microsoft Azure by pre-populating your assessment with fully inherited or shared responsibility controls for Azure in the HITRUST MyCSF tool, and collaborating with Microsoft on your assessment.</span></span>

[<span data-ttu-id="f6859-141">了解更多</span><span class="sxs-lookup"><span data-stu-id="f6859-141">Learn more</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2100268)

## <a name="frequently-asked-questions"></a><span data-ttu-id="f6859-142">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f6859-142">Frequently asked questions</span></span>

<span data-ttu-id="f6859-143">**我可以使用 Azure HITRUST 合规性来构建组织的认证过程吗？**</span><span class="sxs-lookup"><span data-stu-id="f6859-143">**Can I use the Azure HITRUST compliance to build on my organization's certification process?**</span></span>

<span data-ttu-id="f6859-144">是。</span><span class="sxs-lookup"><span data-stu-id="f6859-144">Yes.</span></span> <span data-ttu-id="f6859-145">如果企业需要对部署在 Microsoft 服务上的实施进行 HITRUST 认证，则可以在进行合规性评估时在 Azure HITRUST 合规性上构建。</span><span class="sxs-lookup"><span data-stu-id="f6859-145">If your business requires a HITRUST certification for implementations deployed on Microsoft services, you can build on Azure HITRUST compliance when you conduct your compliance assessment.</span></span> <span data-ttu-id="f6859-146">不过，您需要负责评估您自己的组织中的 HITRUST 要求和控件。</span><span class="sxs-lookup"><span data-stu-id="f6859-146">However, you are responsible for evaluating the HITRUST requirements and controls within your own organization.</span></span>

<span data-ttu-id="f6859-147">**如何获取 HITRUST 证书的副本？**</span><span class="sxs-lookup"><span data-stu-id="f6859-147">**How can I get a copy of the HITRUST certification?**</span></span>

<span data-ttu-id="f6859-148">您可以下载[Azure](https://aka.ms/AzureHiTrustLetterofCertification)和[Office 365](https://aka.ms/O365HITRUSTcertification)证书的一份副本。</span><span class="sxs-lookup"><span data-stu-id="f6859-148">You can download a copy of letter of certification for [Azure](https://aka.ms/AzureHiTrustLetterofCertification) and [Office 365](https://aka.ms/O365HITRUSTcertification).</span></span>

<span data-ttu-id="f6859-149">**Office 365 的范围内服务有哪些？**</span><span class="sxs-lookup"><span data-stu-id="f6859-149">**What are the in-scope services for Office 365?**</span></span>

<span data-ttu-id="f6859-150">HITRUST CSF 认证的范围内的服务包括 Exchange Online 存档、Exchange Online Protection、Exchange Online、Skype for Business、管理中心、SharePoint Online、Project Online、OneDrive for Business、Office Online、MyAnalytics、MicrosoftOffice 365 多租户云和 Office 365 GCC 中的团队、Office 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="f6859-150">The in-scope services of HITRUST CSF certification are Exchange Online Archiving, Exchange Online Protection, Exchange Online, Skype for Business, Admin Center, SharePoint Online, Project Online, OneDrive for Business, Office Online, MyAnalytics, Microsoft Teams, Office ProPlus in Office 365 Multi-tenant cloud and Office 365 GCC.</span></span>

> [!NOTE]
> <span data-ttu-id="f6859-151">Office 365 专业增强版支持对各种云服务（如漫游设置、许可和 OneDrive 消费者云存储）的访问，并可能在将来能够访问其他云服务。</span><span class="sxs-lookup"><span data-stu-id="f6859-151">Office 365 ProPlus enables access to various cloud services, such as Roaming Settings, Licensing, and OneDrive consumer cloud storage, and may enable access to additional cloud services in the future.</span></span> <span data-ttu-id="f6859-152">漫游设置和许可支持 HITRUST 的标准。</span><span class="sxs-lookup"><span data-stu-id="f6859-152">Roaming Settings and Licensing support the standards for HITRUST.</span></span> <span data-ttu-id="f6859-153">OneDrive 消费者云存储不支持，并且其他可通过 Office 365 专业增强版访问的云服务以及 Microsoft 将来可能会提供的云服务也可能不支持这些标准。 \*</span><span class="sxs-lookup"><span data-stu-id="f6859-153">OneDrive consumer cloud storage does not, and other cloud services that are accessible through Office 365 ProPlus and that Microsoft may offer in the future also may not, support these standards.\*</span></span>

<span data-ttu-id="f6859-154">**为什么某些 Office 365 服务不在此认证的范围内？**</span><span class="sxs-lookup"><span data-stu-id="f6859-154">**Why are some Office 365 services not in the scope of this certification?**</span></span>

<span data-ttu-id="f6859-155">与其他云服务提供商相比，Microsoft 提供了最全面的产品。</span><span class="sxs-lookup"><span data-stu-id="f6859-155">Microsoft provides the most comprehensive offerings compared to other cloud service providers.</span></span> <span data-ttu-id="f6859-156">为了在各地区和行业中保持我们的广泛合规性产品，我们根据市场需求、客户反馈和产品生命周期，在我们的保证工作范围中加入服务。</span><span class="sxs-lookup"><span data-stu-id="f6859-156">To keep up with our broad compliance offerings across regions and industries, we include services in the scope of our assurance efforts based on the market demand, customer feedback, and product lifecycle.</span></span> <span data-ttu-id="f6859-157">如果某项服务未包含在特定合规性产品的当前范围内，则您的组织有责任根据您的合规性义务评估风险，并确定您处理该服务中的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="f6859-157">If a service is not included in the current scope of a specific compliance offering, your organization has the responsibility to assess the risks based on your compliance obligations and determine the way you process the data in that service.</span></span> <span data-ttu-id="f6859-158">我们不断地收集来自客户的反馈，并与管理机构和审计员合作，以满足您的安全和合规性需求。</span><span class="sxs-lookup"><span data-stu-id="f6859-158">We continuously collect feedback from customers and work with regulators and auditors to expand our compliance coverage to meet your security and compliance needs.</span></span>

<span data-ttu-id="f6859-159">**Microsoft 认证表示如果我的组织使用 Azure 或 Office 365，则符合 HITRUST CSF？**</span><span class="sxs-lookup"><span data-stu-id="f6859-159">**Does Microsoft certification mean that if my organization uses Azure or Office 365, it is compliant with HITRUST CSF?**</span></span>

<span data-ttu-id="f6859-160">当您将数据存储在 SaaS （如 Office 365）中时，Microsoft 与您的组织之间共同负责实现合规性。</span><span class="sxs-lookup"><span data-stu-id="f6859-160">When you store your data in a SaaS like Office 365, it’s a shared responsibility between Microsoft and your organization to achieve compliance.</span></span> <span data-ttu-id="f6859-161">Microsoft 管理大多数基础结构控件，包括物理安全性、网络控件、应用程序级别控制等，并且您的组织具有管理访问控制和保护敏感数据的责任。</span><span class="sxs-lookup"><span data-stu-id="f6859-161">Microsoft manages majority of the infrastructure controls including physical security, network controls, application level controls, etc., and your organization has the responsibility to manage access controls and protect your sensitive data.</span></span> <span data-ttu-id="f6859-162">Office 365 HITRUST 认证说明了 Microsoft 的控制框架的合规性。</span><span class="sxs-lookup"><span data-stu-id="f6859-162">The Office 365 HITRUST certification demonstrates the compliance of Microsoft’s control framework.</span></span> <span data-ttu-id="f6859-163">基于这一点，贵组织需要实施并维护自己的数据保护控件，以满足 HITRUST CSF 要求。</span><span class="sxs-lookup"><span data-stu-id="f6859-163">Building on that, your organization needs to implement and maintain your own data protection controls to meet HITRUST CSF requirements.</span></span>

<span data-ttu-id="f6859-164">**在使用 Office 365 时，Microsoft 是否为我的组织提供了实施相应控件的指导？**</span><span class="sxs-lookup"><span data-stu-id="f6859-164">**Does Microsoft provide guidance for my organization to implement appropriate controls when using Office 365?**</span></span>

<span data-ttu-id="f6859-165">是的，您可以在合规性管理器中查找推荐的客户操作、跨 Microsoft 云解决方案，帮助组织在使用云服务时满足复杂合规性义务。</span><span class="sxs-lookup"><span data-stu-id="f6859-165">Yes, you can find recommended customer actions in Compliance Manager, cross-Microsoft Cloud solutions that help your organization meet complex compliance obligations when using cloud services.</span></span> <span data-ttu-id="f6859-166">具体来说，对于 HITRUST CSF，我们建议您在合规性管理器中使用 NIST 800-53 和 NIST CSF 评估执行风险评估。</span><span class="sxs-lookup"><span data-stu-id="f6859-166">Specifically, for HITRUST CSF, we recommend that you perform risk assessments using the NIST 800-53 and NIST CSF assessments in Compliance Manager.</span></span> <span data-ttu-id="f6859-167">在评估中，我们为你提供了分步指南以及你可以用来实现数据保护控件的 Microsoft 解决方案。</span><span class="sxs-lookup"><span data-stu-id="f6859-167">In the assessments, we provide you with step-by-step guidance and the Microsoft solutions you can use to implement your data protection controls.</span></span> <span data-ttu-id="f6859-168">您可以在此[白皮书](https://resources.office.com/ww-landing-m365e-gdpr-compliance-manager-whitepaper.html?lcid=en-us)中了解有关合规性管理器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6859-168">You can learn more about Compliance Manager in this [whitepaper](https://resources.office.com/ww-landing-m365e-gdpr-compliance-manager-whitepaper.html?lcid=en-us).</span></span>

<span data-ttu-id="f6859-169">**如何与 Microsoft 联系？**</span><span class="sxs-lookup"><span data-stu-id="f6859-169">**How do I engage with Microsoft?**</span></span>

<span data-ttu-id="f6859-170">登录到 HITRUST MyCSF®工具，并使用 Azure 的完全继承或共享责任控制在 Microsoft Azure 上为托管的解决方案预填充评估。</span><span class="sxs-lookup"><span data-stu-id="f6859-170">Log in to the HITRUST MyCSF® tool and pre-populate your assessment for your solution hosted on Microsoft Azure with either fully inherited or shared responsibility controls for Azure.</span></span> <span data-ttu-id="f6859-171">然后，Microsoft HITRUST 管理员将使用其在 "MyCSF"®工具上的帐户完成评估的部分。</span><span class="sxs-lookup"><span data-stu-id="f6859-171">A Microsoft HITRUST Administrator will then complete their part of the assessment using their account on the MyCSF® tool.</span></span>

## <a name="resources"></a><span data-ttu-id="f6859-172">资源</span><span class="sxs-lookup"><span data-stu-id="f6859-172">Resources</span></span>

- [<span data-ttu-id="f6859-173">HITRUST 联盟</span><span class="sxs-lookup"><span data-stu-id="f6859-173">HITRUST Alliance</span></span>](https://hitrustalliance.net/)
- [<span data-ttu-id="f6859-174">HITRUST CSF 8。1</span><span class="sxs-lookup"><span data-stu-id="f6859-174">HITRUST CSF 8.1</span></span>](https://hitrustalliance.net/csf-license-agreement/)
- [<span data-ttu-id="f6859-175">了解和利用 CSF</span><span class="sxs-lookup"><span data-stu-id="f6859-175">Understanding and Leveraging the CSF</span></span>](https://hitrustalliance.net/understanding-leveraging-csf/)
- [<span data-ttu-id="f6859-176">了解有关 HITRUST 共享责任计划的详细信息</span><span class="sxs-lookup"><span data-stu-id="f6859-176">Find out more about the HITRUST Shared Responsibility Program</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2100268)
- [<span data-ttu-id="f6859-177">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="f6859-177">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="f6859-178">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="f6859-178">Download the offering backgrounder</span></span>

<span data-ttu-id="f6859-179">需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="f6859-179">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="f6859-180">请下载 [PDF](https://download.microsoft.com/download/7/2/6/7265470A-862D-4665-91E8-E17BF0C8A1E2/HITRUST-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="f6859-180">Download the [PDF](https://download.microsoft.com/download/7/2/6/7265470A-862D-4665-91E8-E17BF0C8A1E2/HITRUST-Compliance.pdf).</span></span>
