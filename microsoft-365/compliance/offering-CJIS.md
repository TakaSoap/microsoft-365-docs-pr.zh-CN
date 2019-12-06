---
title: 刑事审判信息服务（CJIS）安全策略
description: Microsoft 政府云服务遵守美国刑事审判信息服务安全策略。
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
ms.openlocfilehash: 8d28327e4627351c27140e954c2fa26571d1689d
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "39860042"
---
# <a name="criminal-justice-information-services-cjis-security-policy"></a><span data-ttu-id="01246-104">刑事审判信息服务（CJIS）安全策略</span><span class="sxs-lookup"><span data-stu-id="01246-104">Criminal Justice Information Services (CJIS) Security Policy</span></span>

## <a name="cjis-overview"></a><span data-ttu-id="01246-105">CJIS 概述</span><span class="sxs-lookup"><span data-stu-id="01246-105">CJIS overview</span></span>

<span data-ttu-id="01246-106">美国联邦调查局（FBI）的犯罪法案信息服务（CJIS）分公司提供州、地方和联邦法律实施和刑事审判机构访问刑事审判信息（CJI），例如指纹记录和刑事历史记录。</span><span class="sxs-lookup"><span data-stu-id="01246-106">The Criminal Justice Information Services (CJIS) Division of the US Federal Bureau of Investigation (FBI) gives state, local, and federal law enforcement and criminal justice agencies access to criminal justice information (CJI) — for example, fingerprint records and criminal histories.</span></span> <span data-ttu-id="01246-107">美国的执法机构和其他政府机构必须确保其对 CJI 的传输、存储或处理的使用云服务符合[CJIS 安全策略](https://aka.ms/cjis-security-policy)，后者建立最低安全性要求和控制措施来保护 CJI。</span><span class="sxs-lookup"><span data-stu-id="01246-107">Law enforcement and other government agencies in the United States must ensure that their use of cloud services for the transmission, storage, or processing of CJI complies with the [CJIS Security Policy](https://aka.ms/cjis-security-policy), which establishes minimum security requirements and controls to safeguard CJI.</span></span>

<span data-ttu-id="01246-108">CJIS 安全策略集成了总统和 FBI 指令、联邦法律和刑事审判社区的咨询策略董事会决策，以及美国国家标准和技术协会（NIST）的指导。</span><span class="sxs-lookup"><span data-stu-id="01246-108">The CJIS Security Policy integrates presidential and FBI directives, federal laws, and the criminal justice community’s Advisory Policy Board decisions, along with guidance from the National Institute of Standards and Technology (NIST).</span></span> <span data-ttu-id="01246-109">定期更新策略以反映日益增长的安全要求。</span><span class="sxs-lookup"><span data-stu-id="01246-109">The Policy is periodically updated to reflect evolving security requirements.</span></span>

<span data-ttu-id="01246-110">CJIS 安全策略定义了专用承包商（如云服务提供商）必须评估的13个方面，以确定其云服务的使用是否符合 CJIS 要求。</span><span class="sxs-lookup"><span data-stu-id="01246-110">The CJIS Security Policy defines 13 areas that private contractors such as cloud service providers must evaluate to determine if their use of cloud services can be consistent with CJIS requirements.</span></span> <span data-ttu-id="01246-111">这些领域与 NIST 800-53 密切对应，这也是联邦风险和授权管理计划（[FedRAMP](offering-FedRAMP.md)）的基础，它是 Microsoft 为其政府云产品认证的计划。</span><span class="sxs-lookup"><span data-stu-id="01246-111">These areas correspond closely to NIST 800-53, which is also the basis for the Federal Risk and Authorization Management Program ([FedRAMP](offering-FedRAMP.md)), a program under which Microsoft has been certified for its Government Cloud offerings.</span></span>

<span data-ttu-id="01246-112">此外，处理 CJI 的所有私有承包商必须签署 CJIS 安全附录，这是由美国律师通用批准的统一协议，可帮助确保安全策略所需的安全性和机密性。</span><span class="sxs-lookup"><span data-stu-id="01246-112">In addition, all private contractors who process CJI must sign the CJIS Security Addendum, a uniform agreement approved by the US Attorney General that helps ensure the security and confidentiality of CJI required by the Security Policy.</span></span> <span data-ttu-id="01246-113">它还承诺承包商遵守联邦和州法律、法规和标准，使安全计划保持一致，并将 CJI 的使用限制为政府机构向其提供的目的。</span><span class="sxs-lookup"><span data-stu-id="01246-113">It also commits the contractor to maintaining a security program consistent with federal and state laws, regulations, and standards, and limits the use of CJI to the purposes for which a government agency provided it.</span></span>

## <a name="microsoft-and-cjis-security-policy"></a><span data-ttu-id="01246-114">Microsoft 和 CJIS 安全策略</span><span class="sxs-lookup"><span data-stu-id="01246-114">Microsoft and CJIS Security Policy</span></span>

<span data-ttu-id="01246-115">Microsoft 使用 CJIS 信息协议签署 CJIS 安全附录。</span><span class="sxs-lookup"><span data-stu-id="01246-115">Microsoft signs the CJIS Security Addendum in states with CJIS Information Agreements.</span></span> <span data-ttu-id="01246-116">这些指导状态定律强制颁发机构负责遵从 CJIS 安全策略 Microsoft 的云安全控制如何帮助保护数据的完整生命周期，并确保适当的操作人员后台筛选以访问CJI.</span><span class="sxs-lookup"><span data-stu-id="01246-116">These tell state law enforcement authorities responsible for compliance with CJIS Security Policy how Microsoft's cloud security controls help protect the full lifecycle of data and ensure appropriate background screening of operating personnel with access to CJI.</span></span> <span data-ttu-id="01246-117">Microsoft 将继续与州政府合作，以输入 CJIS 信息协议。</span><span class="sxs-lookup"><span data-stu-id="01246-117">Microsoft continues to work with state governments to enter into CJIS Information Agreements.</span></span>

<span data-ttu-id="01246-118">Microsoft 已评估 Microsoft Azure 政府、Microsoft Office 365 美国政府和 Microsoft Dynamics 365 美国政府的操作策略和过程，并将证明其在适用服务协议方面的能力能够满足 FBI对使用范围内服务的要求。</span><span class="sxs-lookup"><span data-stu-id="01246-118">Microsoft has assessed the operational policies and procedures of Microsoft Azure Government, Microsoft Office 365 U.S. Government, and Microsoft Dynamics 365 U.S. Government, and will attest to their ability in the applicable services agreements to meet FBI requirements for the use of in-scope services.</span></span>

<span data-ttu-id="01246-119">了解 CJIS 安全策略在 Microsoft 云上的优势：了解[Genetec 如何清除犯罪调查](https://customers.microsoft.com/story/genetec)</span><span class="sxs-lookup"><span data-stu-id="01246-119">Learn about the benefits of CJIS Security policy on the Microsoft Cloud: [Read how Genetec cleared criminal investigations](https://customers.microsoft.com/story/genetec)</span></span>

<span data-ttu-id="01246-120">了解如何使用 Azure 安全性和合规性蓝图加快 CJIS 安全策略：[下载 Microsoft 政府云服务的 CJIS 实施指南](https://gallery.technet.microsoft.com/CJIS-Implementation-62af7c27)</span><span class="sxs-lookup"><span data-stu-id="01246-120">Learn how to accelerate your CJIS Security policy with our Azure Security and Compliance Blueprint: [Download the CJIS implementation guidelines for Microsoft Government Cloud Services](https://gallery.technet.microsoft.com/CJIS-Implementation-62af7c27)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="01246-121">Microsoft 范围内的云服务</span><span class="sxs-lookup"><span data-stu-id="01246-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="01246-122">Azure 政府</span><span class="sxs-lookup"><span data-stu-id="01246-122">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="01246-123">美国政府 Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="01246-123">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- [<span data-ttu-id="01246-124">Office 365 美国政府版</span><span class="sxs-lookup"><span data-stu-id="01246-124">Office 365 U.S. Government</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="01246-125">Power BI 云服务，作为独立服务提供，或者随 Office 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="01246-125">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="01246-126">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="01246-126">Audits, reports, and certificates</span></span>

<span data-ttu-id="01246-127">FBI 不提供 Microsoft 符合 CJIS 要求的认证。</span><span class="sxs-lookup"><span data-stu-id="01246-127">The FBI does not offer certification of Microsoft compliance with CJIS requirements.</span></span> <span data-ttu-id="01246-128">相反，Microsoft 证明包括在 Microsoft 和州的 CJIS 机构之间的协议以及 Microsoft 与其客户之间。</span><span class="sxs-lookup"><span data-stu-id="01246-128">Instead, a Microsoft attestation is included in agreements between Microsoft and a state’s CJIS authority, and between Microsoft and its customers.</span></span>

[<span data-ttu-id="01246-129">Microsoft CJIS 云要求</span><span class="sxs-lookup"><span data-stu-id="01246-129">Microsoft CJIS Cloud Requirements</span></span>](https://aka.ms/MicrosoftCJISCloudRequirements)

## <a name="cjis-status-in-the-united-states-current-as-of-9232019"></a><span data-ttu-id="01246-130">美国的 CJIS 状态（当前状态为9/23/2019）</span><span class="sxs-lookup"><span data-stu-id="01246-130">CJIS status in the United States (current as of 9/23/2019)</span></span>

<span data-ttu-id="01246-131">37州和哥伦比亚带有管理协议的地区，以绿色的地图突出显示：</span><span class="sxs-lookup"><span data-stu-id="01246-131">37 states and the District of Columbia with management agreements, highlighted on the map in green include:</span></span>

<span data-ttu-id="01246-132">Alabama、阿拉斯加、Arkansas、亚利桑那、加利福尼亚、科罗拉多、佛罗里达、格鲁吉亚、夏威夷、伊利诺斯州、印地安那、艾奥瓦、堪萨斯州、Kentucky、Maine、马萨诸塞州、密歇根、Minnesota、Missouri、Montana、New Jersey、纽约、内华达、北卡罗莱纳州、俄克拉荷马、俄勒冈州宾夕法尼亚州、Rhode 岛、南部卡罗莱纳州、田纳西州、德克萨斯、犹他、Vermont、弗吉尼亚州、华盛顿特区、西弗吉尼亚州、Wisconsin。</span><span class="sxs-lookup"><span data-stu-id="01246-132">Alabama, Alaska, Arkansas, Arizona, California, Colorado, Florida, Georgia, Hawaii, Illinois, Indiana, Iowa, Kansas, Kentucky, Maine, Massachusetts, Michigan, Minnesota, Missouri, Montana, New Jersey, New York, Nevada, North Carolina, Oklahoma, Oregon, Pennsylvania, Rhode Island, South Carolina, Tennessee, Texas, Utah, Vermont, Virginia, Washington, Washington D.C., West Virginia, Wisconsin.</span></span>

<span data-ttu-id="01246-133">Microsoft 承诺满足适用的 CJIS 管理法规控制措施，允许刑事审判组织实施基于云的解决方案，并符合 CJIS 安全策略 V 5.8。</span><span class="sxs-lookup"><span data-stu-id="01246-133">Microsoft's commitment to meeting the applicable CJIS regulatory controls allows Criminal Justice organizations to implement cloud-based solutions and be compliant with CJIS Security Policy V5.8.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="01246-134">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="01246-134">Frequently asked questions</span></span>

<span data-ttu-id="01246-135">**在哪里可以请求符合性信息？**</span><span class="sxs-lookup"><span data-stu-id="01246-135">**Where can I request compliance information?**</span></span>

<span data-ttu-id="01246-136">请联系你的 Microsoft 帐户代表以获取有关你感兴趣的司法辖区的信息。</span><span class="sxs-lookup"><span data-stu-id="01246-136">Contact your Microsoft account representative for information on the jurisdiction you are interested in.</span></span> <span data-ttu-id="01246-137">有关<cjis@microsoft.com>当前可在哪些状态提供服务的信息，请联系。</span><span class="sxs-lookup"><span data-stu-id="01246-137">Contact <cjis@microsoft.com> for information on which services are currently available in which states.</span></span>

<span data-ttu-id="01246-138">**Microsoft 如何证明其云服务能够符合我的状态要求？**</span><span class="sxs-lookup"><span data-stu-id="01246-138">**How does Microsoft demonstrate that its cloud services enable compliance with my state’s requirements?**</span></span>

<span data-ttu-id="01246-139">Microsoft 使用州 CJIS Systems 机关（CSA）签署信息协议;你可以从你的状态的 CSA 请求副本。</span><span class="sxs-lookup"><span data-stu-id="01246-139">Microsoft signs an Information Agreement with a state CJIS Systems Agency (CSA); you may request a copy from your state’s CSA.</span></span> <span data-ttu-id="01246-140">此外，Microsoft 还为客户提供了详细的安全、隐私和合规性信息。</span><span class="sxs-lookup"><span data-stu-id="01246-140">In addition, Microsoft provides customers with in-depth security, privacy, and compliance information.</span></span> <span data-ttu-id="01246-141">客户还可以查看独立审计员准备的安全性和合规性报告，以便他们能够验证 Microsoft 是否已实现适合相关审核作用域的安全控制（如 ISO 27001）。</span><span class="sxs-lookup"><span data-stu-id="01246-141">Customers may also review security and compliance reports prepared by independent auditors so they can validate that Microsoft has implemented security controls (such as ISO 27001) appropriate to the relevant audit scope.</span></span>

<span data-ttu-id="01246-142">**我应从哪里开始使用我的机构的合规性工作？**</span><span class="sxs-lookup"><span data-stu-id="01246-142">**Where do I start with my agency’s compliance effort?**</span></span>

<span data-ttu-id="01246-143">[CJIS 安全策略](https://aka.ms/cjis-security-policy)涵盖了您的机构必须采取的预防措施以保护 CJI。</span><span class="sxs-lookup"><span data-stu-id="01246-143">[CJIS Security Policy](https://aka.ms/cjis-security-policy) covers the precautions that your agency must take to protect CJI.</span></span> <span data-ttu-id="01246-144">此外，你的 Microsoft 帐户代表可以与熟悉你的司法辖区要求的人员联系。</span><span class="sxs-lookup"><span data-stu-id="01246-144">In addition, your Microsoft account representative can put you in touch with those familiar with the requirements of your jurisdiction</span></span>

## <a name="resources"></a><span data-ttu-id="01246-145">资源</span><span class="sxs-lookup"><span data-stu-id="01246-145">Resources</span></span>

- [<span data-ttu-id="01246-146">刑事审判信息服务</span><span class="sxs-lookup"><span data-stu-id="01246-146">Criminal Justice Information Services</span></span>](https://aka.ms/cjis)
- [<span data-ttu-id="01246-147">CJIS 安全策略</span><span class="sxs-lookup"><span data-stu-id="01246-147">CJIS Security Policy</span></span>](https://aka.ms/cjis-security-policy)
- [<span data-ttu-id="01246-148">CJIS 安全策略版本 5.3 backgrounder</span><span class="sxs-lookup"><span data-stu-id="01246-148">CJIS security policy version 5.3 backgrounder</span></span>](https://aka.ms/cjis-backgrounder)
- [<span data-ttu-id="01246-149">适用于 Azure 政府的 CJIS 实施指南</span><span class="sxs-lookup"><span data-stu-id="01246-149">CJIS implementation guidelines for Azure Government</span></span>](https://aka.ms/cjisimplementationguidelines)
- [<span data-ttu-id="01246-150">Microsoft 公共控制中心合规性框架</span><span class="sxs-lookup"><span data-stu-id="01246-150">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="01246-151">Microsoft 政府云</span><span class="sxs-lookup"><span data-stu-id="01246-151">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/?linkid=2087246)
- [<span data-ttu-id="01246-152">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="01246-152">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="01246-153">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="01246-153">Download the offering backgrounder</span></span>

<span data-ttu-id="01246-154">需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="01246-154">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="01246-155">请下载 [PDF](https://download.microsoft.com/download/4/D/0/4D008840-B8C4-480B-ACD1-D55CB34AD6BC/CJIS_Compliance_Backgrounder.pdf)。</span><span class="sxs-lookup"><span data-stu-id="01246-155">Download the [PDF](https://download.microsoft.com/download/4/D/0/4D008840-B8C4-480B-ACD1-D55CB34AD6BC/CJIS_Compliance_Backgrounder.pdf).</span></span>
