---
title: 联邦风险和授权管理项目 (FedRAMP)
description: Microsoft 被授予美国联邦风险和授权管理计划 P-ATOs 和 ATOs。
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
ms.openlocfilehash: c91c71f199ef36c1c9a0da023c7b26d6cb64282e
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415776"
---
# <a name="federal-risk-and-authorization-management-program-fedramp"></a><span data-ttu-id="858e5-104">联邦风险和授权管理项目 (FedRAMP)</span><span class="sxs-lookup"><span data-stu-id="858e5-104">Federal Risk and Authorization Management Program (FedRAMP)</span></span>

## <a name="fedramp-overview"></a><span data-ttu-id="858e5-105">FedRAMP 概述</span><span class="sxs-lookup"><span data-stu-id="858e5-105">FedRAMP overview</span></span>

<span data-ttu-id="858e5-106">美国联邦风险和授权管理计划 (FedRAMP) 已建立，以提供一种标准化的方法来评估、监控和授权联邦信息安全管理 (法案（FISMA) ）下的云计算产品和服务，并加速联邦机构采用安全云解决方案。</span><span class="sxs-lookup"><span data-stu-id="858e5-106">The US Federal Risk and Authorization Management Program (FedRAMP) was established to provide a standardized approach for assessing, monitoring, and authorizing cloud computing products and services under the Federal Information Security Management Act (FISMA), and to accelerate the adoption of secure cloud solutions by federal agencies.</span></span>

<span data-ttu-id="858e5-107">管理办公室和预算现在要求所有执行联邦机构使用 FedRAMP 来验证云服务的安全性。</span><span class="sxs-lookup"><span data-stu-id="858e5-107">The Office of Management and Budget now requires all executive federal agencies to use FedRAMP to validate the security of cloud services.</span></span> <span data-ttu-id="858e5-108"> (其他机构也采用了它，因此它在公共部门的其他领域也很有用。 ) 美国国家标准 and 技术协会 (NIST) SP 800-53 设置强制性标准、建立信息系统的安全类别（机密性、完整性和可用性），以评估组织的信息系统和信息系统对组织的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="858e5-108">(Other agencies have also adopted it, so it is useful in other areas of the public sector as well.) The National Institute of Standards and Technology (NIST) SP 800-53 sets the mandatory standards, establish security categories of information systems—confidentiality, integrity, and availability—to assess the potential impact on an organization should its information and information systems be compromised.</span></span> <span data-ttu-id="858e5-109">FedRAMP 是证明云服务提供商 (CSP) 符合这些标准的程序。</span><span class="sxs-lookup"><span data-stu-id="858e5-109">FedRAMP is the program that certifies that a cloud service provider (CSP) meets those standards.</span></span>

<span data-ttu-id="858e5-110">将服务销售给联邦机构的 Csp desiring 可以采用三个途径来证明 FedRAMP 合规性：</span><span class="sxs-lookup"><span data-stu-id="858e5-110">CSPs desiring to sell services to a federal agency can take three paths to demonstrate FedRAMP compliance:</span></span>

- <span data-ttu-id="858e5-111">从联合授权委员会 (JAB) 中获取 (操作) 的临时颁发机构。</span><span class="sxs-lookup"><span data-stu-id="858e5-111">Earn a Provisional Authority to Operate (P-ATO) from the Joint Authorization Board (JAB).</span></span> <span data-ttu-id="858e5-112">JAB 是 FedRAMP 的主要调控和决策主体。</span><span class="sxs-lookup"><span data-stu-id="858e5-112">The JAB is the primary governance and decision-making body for FedRAMP.</span></span> <span data-ttu-id="858e5-113">来自国防部门的代表、Homeland 安全部门以及在董事会上的常规服务管理服务。</span><span class="sxs-lookup"><span data-stu-id="858e5-113">Representatives from the Department of Defense, the Department of Homeland Security, and the General Services Administration serve on the board.</span></span> <span data-ttu-id="858e5-114">该委员会向已证明 FedRAMP 合规性的 Csp 授予 P-ATO。</span><span class="sxs-lookup"><span data-stu-id="858e5-114">The board grants a P-ATO to CSPs that have demonstrated FedRAMP compliance.</span></span>
- <span data-ttu-id="858e5-115">接收从联邦机构 (ATO) 操作的权限。</span><span class="sxs-lookup"><span data-stu-id="858e5-115">Receive an Authority to Operate (ATO) from a federal agency.</span></span>
- <span data-ttu-id="858e5-116">或者，单独工作以开发符合程序要求的 CSP 提供的程序包。</span><span class="sxs-lookup"><span data-stu-id="858e5-116">Or, work independently to develop a CSP Supplied Package that meets program requirements.</span></span>

<span data-ttu-id="858e5-117">这些路径中的每一条都需要由 FedRAMP 计划管理办公室 (PMO) 和由该程序获得资格鉴定的独立第三方组织进行评估。</span><span class="sxs-lookup"><span data-stu-id="858e5-117">Each of these paths requires a stringent technical review by the FedRAMP Program Management Office (PMO) and an assessment by an independent third-party organization that is accredited by the program.</span></span>

<span data-ttu-id="858e5-118">基于 NIST 指南（低、中和高）的三个影响级别授予 FedRAMP 授权。</span><span class="sxs-lookup"><span data-stu-id="858e5-118">FedRAMP authorizations are granted at three impact levels based on NIST guidelines—low, medium, and high.</span></span> <span data-ttu-id="858e5-119">这些级别对组织中可能存在的机密性、完整性或可用性的影响（低 (有限影响) 、中型 (严重影响) 以及高 (严重或灾难性影响) ）进行了排序。</span><span class="sxs-lookup"><span data-stu-id="858e5-119">These levels rank the impact that the loss of confidentiality, integrity, or availability could have on an organization—low (limited effect), medium (serious adverse effect), and high (severe or catastrophic effect).</span></span>

## <a name="microsoft-and-fedramp"></a><span data-ttu-id="858e5-120">Microsoft 与 FedRAMP</span><span class="sxs-lookup"><span data-stu-id="858e5-120">Microsoft and FedRAMP</span></span>

<span data-ttu-id="858e5-121">Microsoft 的政府云服务（包括 Azure 政府、Dynamics 365 政府和 Office 365 美国政府）满足美国联邦风险和授权管理计划 (FedRAMP) 的要求，使美国联邦机构能够从 Microsoft 云的成本节约和严格的安全性中获益。</span><span class="sxs-lookup"><span data-stu-id="858e5-121">Microsoft’s government cloud services, including Azure Government, Dynamics 365 Government, and Office 365 U.S. Government meet the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling U.S. federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

<span data-ttu-id="858e5-122">Microsoft 政府云服务为公共部门客户提供了一系列符合 FedRAMP 的服务，并提供了强健的指导和实现工具，包括 [FedRAMP 高蓝图](https://aka.ms/fedrampblueprint)，可帮助客户为必须实现 FedRAMP 高控制的任何 Azure 部署体系结构部署一组核心策略。</span><span class="sxs-lookup"><span data-stu-id="858e5-122">Microsoft government cloud services offer public sector customers a rich array of services compliant with FedRAMP, and robust guidance and implementation tools, including the [FedRAMP High blueprint](https://aka.ms/fedrampblueprint), which helps customers deploy a core set of policies for any Azure-deployed architecture that must implement FedRAMP High controls.</span></span>

## <a name="microsoft-azure-p-atos"></a><span data-ttu-id="858e5-123">Microsoft Azure P-ATOs</span><span class="sxs-lookup"><span data-stu-id="858e5-123">Microsoft Azure P-ATOs</span></span>

<span data-ttu-id="858e5-124">Azure 和 Azure 政府已在联合授权委员会的 "高影响级别" 中获得了 ATO，这是 FedRAMP 资格鉴定的最高的一条，它可以授权使用 Azure 和 Azure 政府处理高度敏感的数据。</span><span class="sxs-lookup"><span data-stu-id="858e5-124">Azure and Azure Government have earned a P-ATO at the High Impact Level from the Joint Authorization Board, the highest bar for FedRAMP accreditation, which authorizes the use of Azure and Azure Government to process highly sensitive data.</span></span>

<span data-ttu-id="858e5-125">Azure 和 Azure 政府的 FedRAMP 审核包含的信息安全管理系统涵盖了对范围内服务的基础结构、开发、操作、管理和支持。</span><span class="sxs-lookup"><span data-stu-id="858e5-125">The FedRAMP audit of Azure and Azure Government included the information security management system that encompasses infrastructure, development, operations, management, and support of in-scope services.</span></span> <span data-ttu-id="858e5-126">一旦授予了 ATO，CSP 仍然需要授权 (来自它使用的任何政府机构) 的 ATO。</span><span class="sxs-lookup"><span data-stu-id="858e5-126">Once a P-ATO is granted, a CSP still requires an authorization (an ATO) from any government agency it works with.</span></span> <span data-ttu-id="858e5-127">对于 Azure，政府机构可以在其自己的安全授权过程中使用 Azure ATO，并将其作为颁发机构 ATO （也满足 FedRAMP 要求）的基础。</span><span class="sxs-lookup"><span data-stu-id="858e5-127">For Azure, a government agency can use the Azure P-ATO in its own security authorization process and rely on it as the basis for issuing an agency ATO that also meets FedRAMP requirements.</span></span>

<span data-ttu-id="858e5-128">Azure 继续支持比任何其他云提供商更高的 FedRAMP 高影响级别上的服务。</span><span class="sxs-lookup"><span data-stu-id="858e5-128">Azure continues to support more services at FedRAMP High Impact levels than any other cloud provider.</span></span> <span data-ttu-id="858e5-129">而在 Azure 公共云中，FedRAMP 高将满足多个美国政府客户的需求，则具有更严格的要求的代理将继续依赖 Azure 政府，后者提供了额外的安全措施，如更高级的人员筛选。</span><span class="sxs-lookup"><span data-stu-id="858e5-129">And while FedRAMP High in the Azure public cloud will meet the needs of many US government customers, agencies with more stringent requirements will continue to rely on Azure Government, which provides additional safeguards such as the heightened screening of personnel.</span></span> <span data-ttu-id="858e5-130">Microsoft 列出了 Azure 政府 [目前提供的所有 azure 公共服务](https://docs.microsoft.com/azure/azure-government/compliance/azure-services-in-fedramp-auditscope#azure-public-services-by-audit-scope) 和 FedRAMP 高边界，以及为今年规划的服务。</span><span class="sxs-lookup"><span data-stu-id="858e5-130">Microsoft lists all [Azure public services currently available](https://docs.microsoft.com/azure/azure-government/compliance/azure-services-in-fedramp-auditscope#azure-public-services-by-audit-scope) in Azure Government to the FedRAMP High boundary, as well as services planned for the current year.</span></span>

## <a name="microsoft-dynamics-365-us-government-ato"></a><span data-ttu-id="858e5-131">Microsoft Dynamics 365 美国政府版 ATO</span><span class="sxs-lookup"><span data-stu-id="858e5-131">Microsoft Dynamics 365 U.S. Government ATO</span></span>

<span data-ttu-id="858e5-132">Dynamics 365 美国政府已向美国的 FedRAMP 机构 ATO 授予美国) 的美国的 HUD 和市内 (开发的高影响级别。</span><span class="sxs-lookup"><span data-stu-id="858e5-132">Dynamics 365 U.S. Government was granted a FedRAMP Agency ATO at the High Impact Level by the US Department of Housing and Urban Development (HUD).</span></span> <span data-ttu-id="858e5-133">虽然认证范围仅限于政府社区云，但 Dynamics 365 美国政府商业版和企业版计划在同一组严格的 FedRAMP 控件的后面运行。</span><span class="sxs-lookup"><span data-stu-id="858e5-133">Although the scope of the certification is limited to the Government Community Cloud, Dynamics 365 U.S. Government business and enterprise plans operate following the same set of stringent FedRAMP controls.</span></span>

## <a name="microsoft-office-365-and-office-365-us-government-atos"></a><span data-ttu-id="858e5-134">Microsoft Office 365 和 Office 365 美国政府版 ATOs</span><span class="sxs-lookup"><span data-stu-id="858e5-134">Microsoft Office 365 and Office 365 U.S. Government ATOs</span></span>

- <span data-ttu-id="858e5-135">Office 365 和 Office 365 美国政府在美国卫生部门 (DHHS) 中有一个 ATO。</span><span class="sxs-lookup"><span data-stu-id="858e5-135">Office 365 and Office 365 U.S. Government have an ATO from the US Department of Health and Human Services (DHHS).</span></span>
- <span data-ttu-id="858e5-136">Office 365 美国政府防御版中有一个 ATO 来自美国国防部的公司 (DISA) 。</span><span class="sxs-lookup"><span data-stu-id="858e5-136">Office 365 U.S. Government Defense has a P-ATO from the US Defense Information Systems Agency (DISA).</span></span> <span data-ttu-id="858e5-137">任何想要部署 Office 365 美国政府防御的客户都可能使用 DISA P-ATO 来生成一个代理商的 ATO，以记录其对其接受程度。</span><span class="sxs-lookup"><span data-stu-id="858e5-137">Any customer wishing to deploy Office 365 U.S. Government Defense may use the DISA P‑ATO to generate an agency ATO to document their acceptance of it.</span></span>
- <span data-ttu-id="858e5-138">Office 365 (企业和企业计划) 和 Office 365 美国政府在检查器常规的 DHHS 办公室中有一个 FedRAMP 机构 ATO，在中等影响级别。</span><span class="sxs-lookup"><span data-stu-id="858e5-138">Office 365 (enterprise and business plans) and Office 365 U.S. Government have a FedRAMP Agency ATO at the Moderate Impact Level from the DHHS Office of the Inspector General.</span></span> <span data-ttu-id="858e5-139">Office 365 美国政府是第一个用于获取此授权的基于云的电子邮件和协作服务。</span><span class="sxs-lookup"><span data-stu-id="858e5-139">Office 365 U.S. Government was the first cloud-based email and collaboration service to obtain this authorization.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="858e5-140">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="858e5-140">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="858e5-141">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="858e5-141">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2095323)
- [<span data-ttu-id="858e5-142">美国政府 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="858e5-142">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="858e5-143">Intune</span><span class="sxs-lookup"><span data-stu-id="858e5-143">Intune</span></span>
- [<span data-ttu-id="858e5-144">Office 365 和 Office 365 美国 Governmen</span><span class="sxs-lookup"><span data-stu-id="858e5-144">Office 365 and Office 365 U.S. Governmen</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- <span data-ttu-id="858e5-145">Office 365 美国政府防御版</span><span class="sxs-lookup"><span data-stu-id="858e5-145">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="858e5-146">Power BI 云服务，无论是独立服务还是随 Office 365 品牌计划或套件提供的服务</span><span class="sxs-lookup"><span data-stu-id="858e5-146">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="858e5-147">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="858e5-147">Microsoft Defender ATP</span></span>

> [!NOTE]
> <span data-ttu-id="858e5-148">在 Azure 政府中使用 Azure Active Directory 要求使用在 azure 公有云之外部署到 Azure 政府之外的组件。</span><span class="sxs-lookup"><span data-stu-id="858e5-148">The use of Azure Active Directory within Azure Government requires the use of components that are deployed outside of Azure Government on the Azure public cloud.</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="858e5-149">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="858e5-149">Audits, reports, and certificates</span></span>

<span data-ttu-id="858e5-150">Microsoft 每年都必须重新证明其云服务，以维持其 P-ATO 和 ATO 认证。</span><span class="sxs-lookup"><span data-stu-id="858e5-150">Microsoft is required to recertify its cloud services each year to maintain its P-ATOs and ATOs.</span></span> <span data-ttu-id="858e5-151">为此，Microsoft 必须不断监视和评估其安全控制，并证明其服务的安全性仍符合合规性。</span><span class="sxs-lookup"><span data-stu-id="858e5-151">To do so, Microsoft must monitor and assess its security controls continuously, and demonstrate that the security of its services remains in compliance.</span></span>

- [<span data-ttu-id="858e5-152">Microsoft 云服务 FedRAMP 授权</span></span><span class="sxs-lookup"><span data-stu-id="858e5-152">Microsoft cloud services FedRAMP authorizations</span></span></span>](https://marketplace.fedramp.gov/#/product/azure-government?sort=productName&productNameSearch=azure)
- [<span data-ttu-id="858e5-153">Microsoft FedRAMP 审计报告</span></span><span class="sxs-lookup"><span data-stu-id="858e5-153">Microsoft FedRAMP Audit Reports</span></span></span>](https://aka.ms/MicrosoftFedRAMPAuditDocuments)  

<span data-ttu-id="858e5-154">若要接收其他 FedRAMP 报告，请将电子邮件发送到 [Azure 联邦文档](mailto:AzFedDoc@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="858e5-154">To receive other FedRAMP reports, send email to [Azure Federal Documentation](mailto:AzFedDoc@microsoft.com).</span></span>

## <a name="quickly-deploy-your-fedramp-solutions-on-azure-government"></a><span data-ttu-id="858e5-155">在 Azure 政府上快速部署 FedRAMP 解决方案</span><span class="sxs-lookup"><span data-stu-id="858e5-155">Quickly deploy your FedRAMP solutions on Azure Government</span></span>

<span data-ttu-id="858e5-156">让 Microsoft 引导您完成 ATO 过程，并使用 FedRAMP 高蓝图快速部署 FedRAMP 解决方案，这有助于客户为必须实现 FedRAMP 高控制措施的任何 Azure 部署的体系结构实施一组核心策略。</span><span class="sxs-lookup"><span data-stu-id="858e5-156">Let Microsoft guide you through the ATO process and quickly deploy your FedRAMP solutions using the FedRAMP High blueprint, which helps customers implement a core set of policies for any Azure-deployed architecture that must implement FedRAMP High controls.</span></span>

[<span data-ttu-id="858e5-157">开始使用 Azure FedRAMP High 蓝图</span><span class="sxs-lookup"><span data-stu-id="858e5-157">Start using the Azure FedRAMP High Blueprint</span></span>](https://aka.ms/fedrampblueprint)

## <a name="frequently-asked-questions"></a><span data-ttu-id="858e5-158">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="858e5-158">Frequently asked questions</span></span>

<span data-ttu-id="858e5-159">**Microsoft 云服务是否符合联邦信息安全管理法案 (FISMA) ？**</span><span class="sxs-lookup"><span data-stu-id="858e5-159">**Do Microsoft cloud services comply with the Federal Information Security Management Act (FISMA)?**</span></span>

<span data-ttu-id="858e5-160">FISMA 是一种联邦法律，要求我们的联邦机构及其合作伙伴仅从符合 FISMA 要求的组织购买信息系统和服务。</span><span class="sxs-lookup"><span data-stu-id="858e5-160">FISMA is the federal law that requires US federal agencies and their partners to procure information systems and services only from organizations that adhere to FISMA requirements.</span></span> <span data-ttu-id="858e5-161">大多数机构及其供应商指示它们是 FISMA 合规性的，它们都是指它们如何满足由 NIST 在特殊出版物800-53 修订版4中所标识的控制措施。</span><span class="sxs-lookup"><span data-stu-id="858e5-161">Most agencies and their vendors that indicate that they are FISMA-compliant are referring to how they meet the controls identified by the NIST in Special Publication 800-53 rev 4.</span></span> <span data-ttu-id="858e5-162">FISMA 过程 (，但不是基础标准本身) 替换为2011中的 FedRAMP。</span><span class="sxs-lookup"><span data-stu-id="858e5-162">The FISMA process (but not the underlying standards themselves) was replaced by FedRAMP in 2011.</span></span>

<span data-ttu-id="858e5-163">**FedRAMP 适用于哪些人？**</span><span class="sxs-lookup"><span data-stu-id="858e5-163">**To whom does FedRAMP apply?**</span></span>

<span data-ttu-id="858e5-164">对于采用低风险和中等风险影响级别的联邦机构云部署和服务模型，"FedRAMP" 是必需的。</span><span class="sxs-lookup"><span data-stu-id="858e5-164">'FedRAMP is mandatory for federal agency cloud deployments and service models at the low and moderate risk impact levels.'</span></span> <span data-ttu-id="858e5-165">任何想要接洽 CSP 的联邦机构可能都需要满足 FedRAMP 规范。</span><span class="sxs-lookup"><span data-stu-id="858e5-165">Any federal agency that wants to engage a CSP may be required to meet FedRAMP specifications.</span></span> <span data-ttu-id="858e5-166">此外，在联邦政府使用的产品或服务中使用云技术的公司可能需要获取 ATO。</span><span class="sxs-lookup"><span data-stu-id="858e5-166">In addition, companies that employ cloud technologies in products or services used by the federal government may be required to obtain an ATO.</span></span>

<span data-ttu-id="858e5-167">**我的机构在哪里启动其自己的合规性工作？**</span><span class="sxs-lookup"><span data-stu-id="858e5-167">**Where does my agency start its own compliance effort?**</span></span>

<span data-ttu-id="858e5-168">若要概述必须采取的步骤才能成功导航 FedRAMP 并满足其要求，请转到 [获得授权：代理授权](https://www.fedramp.gov/agency-authorization/)。</span><span class="sxs-lookup"><span data-stu-id="858e5-168">For an overview of the steps federal agencies must take to successfully navigate FedRAMP and meet its requirements, go to [Get Authorized: Agency Authorization](https://www.fedramp.gov/agency-authorization/).</span></span>

<span data-ttu-id="858e5-169">**我可以在代理的授权过程中使用 Microsoft 合规性吗？**</span><span class="sxs-lookup"><span data-stu-id="858e5-169">**Can I use Microsoft compliance in my agency’s authorization process?**</span></span>

<span data-ttu-id="858e5-170">是。</span><span class="sxs-lookup"><span data-stu-id="858e5-170">Yes.</span></span> <span data-ttu-id="858e5-171">您可以使用 Microsoft 云服务的认证，作为任何需要联邦政府机构 ATO 的计划或计划的基础。</span><span class="sxs-lookup"><span data-stu-id="858e5-171">You may use the certifications of Microsoft cloud services as the foundation for any program or initiative that requires an ATO from a federal government agency.</span></span> <span data-ttu-id="858e5-172">但是，您需要在这些服务之外为自己的组件实现自己的授权。</span><span class="sxs-lookup"><span data-stu-id="858e5-172">However, you need to achieve your own authorizations for components outside these services.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="858e5-173">使用 Microsoft 合规性分数评估风险</span><span class="sxs-lookup"><span data-stu-id="858e5-173">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="858e5-174">[Microsoft 合规性分数](compliance-score.md)是 [Microsoft 365 合规中心](microsoft-365-compliance-center.md)中的一项预览功能，旨在帮助你了解组织的合规情况并采取措施帮助降低风险。</span><span class="sxs-lookup"><span data-stu-id="858e5-174">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization’s compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="858e5-175">[设置合规性分数](compliance-score-setup.md)后，从 "**模板**" 下拉菜单中选择预配置的[FedRAMP 模板](https://go.microsoft.com/fwlink/?linkid=2118102)，以帮助组织满足此法规的要求。</span><span class="sxs-lookup"><span data-stu-id="858e5-175">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [FedRAMP template](https://go.microsoft.com/fwlink/?linkid=2118102) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="858e5-176">资源</span><span class="sxs-lookup"><span data-stu-id="858e5-176">Resources</span></span>

- [<span data-ttu-id="858e5-177">联邦风险和授权管理计划</span><span class="sxs-lookup"><span data-stu-id="858e5-177">Federal Risk and Authorization Management Program</span></span>](https://www.fedramp.gov/)
- [<span data-ttu-id="858e5-178">FedRAMP 安全评估框架</span><span class="sxs-lookup"><span data-stu-id="858e5-178">FedRAMP Security Assessment Framework</span></span>](https://www.fedramp.gov/assets/resources/documents/FedRAMP_Security_Assessment_Framework.pdf)
- [<span data-ttu-id="858e5-179">在 Microsoft 云中管理合规性</span><span class="sxs-lookup"><span data-stu-id="858e5-179">Managing compliance in the cloud at Microsoft</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="858e5-180">Microsoft 政府云</span><span class="sxs-lookup"><span data-stu-id="858e5-180">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="858e5-181">Azure 合规性服务</span><span class="sxs-lookup"><span data-stu-id="858e5-181">Azure Compliance Offerings</span></span>](https://aka.ms/azurecompliance)
