---
title: Service Organization Controls (SOC)
description: Microsoft 云服务符合 Service Organization Controls 操作安全标准。
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
ms.openlocfilehash: 2428109743b408061ead8ad87d5e59ac30417c06
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898080"
---
# <a name="service-organization-controls-soc"></a><span data-ttu-id="632cb-104">Service Organization Controls (SOC)</span><span class="sxs-lookup"><span data-stu-id="632cb-104">Service Organization Controls (SOC)</span></span>

## <a name="soc-1-2-and-3-reports-overview"></a><span data-ttu-id="632cb-105">SOC 1、2 和 3 报告概述</span><span class="sxs-lookup"><span data-stu-id="632cb-105">SOC 1, 2, and 3 Reports overview</span></span>

<span data-ttu-id="632cb-106">企业越来越多地将基本功能（例如数据存储和应用程序的访问权）外包给云服务提供商 (CSP) 和其他服务组织。</span><span class="sxs-lookup"><span data-stu-id="632cb-106">Increasingly, businesses outsource basic functions such as data storage and access to applications to cloud service providers (CSPs) and other service organizations.</span></span> <span data-ttu-id="632cb-107">为此，美国注册会计师协会 (AICPA) 开发出了 Service Organization Controls (SOC) 框架，这是一种用于保护云中存储和处理的信息机密性和隐私性的控制措施标准。</span><span class="sxs-lookup"><span data-stu-id="632cb-107">In response, the American Institute of Certified Public Accountants (AICPA) has developed the Service Organization Controls (SOC) framework, a standard for controls that safeguard the confidentiality and privacy of information stored and processed in the cloud.</span></span> <span data-ttu-id="632cb-108">该标准符合 International Standard on Assurance Engagements (ISAE)，后者是一种针对国际服务组织的报告标准。</span><span class="sxs-lookup"><span data-stu-id="632cb-108">This aligns with the International Standard on Assurance Engagements (ISAE), the reporting standard for international service organizations.</span></span>

<span data-ttu-id="632cb-109">基于 SOC 框架的服务审核分为两类：SOC 1 和 SOC 2，适用于范围内 Microsoft 云服务。</span><span class="sxs-lookup"><span data-stu-id="632cb-109">Service audits based on the SOC framework fall into two categories — SOC 1 and SOC 2 — that apply to in-scope Microsoft cloud services.</span></span>

<span data-ttu-id="632cb-110">SOC 1 审核针对审计财务报表的 CPA 事务所，可评估 CSP 内部控制措施的有效性，这些内部控制措施会影响使用提供商云服务的客户的财务报告。</span><span class="sxs-lookup"><span data-stu-id="632cb-110">A SOC 1 audit, intended for CPA firms that audit financial statements, evaluates the effectiveness of a CSP's internal controls that affect the financial reports of a customer using the provider's cloud services.</span></span> <span data-ttu-id="632cb-111">《鉴证业务准则公告》(SSAE 18) 和《鉴证业务国际准则</span><span class="sxs-lookup"><span data-stu-id="632cb-111">The Statement on Standards for Attestation Engagements (SSAE 18) and the International Standards for Assurance Engagements No.</span></span> <span data-ttu-id="632cb-112">第 3402 号》(ISAE 3402) 是进行审核的标准，也是 SOC 1 报告的基础。</span><span class="sxs-lookup"><span data-stu-id="632cb-112">3402 (ISAE 3402) are the standards under which the audit is performed, and is the basis of the SOC 1 report.</span></span>

<span data-ttu-id="632cb-113">SOC 2 审核基于 AICPA Trust Service Principles and Criteria 来衡量 CSP 系统的有效性。</span><span class="sxs-lookup"><span data-stu-id="632cb-113">A SOC 2 audit gauges the effectiveness of a CSP's system based on the AICPA Trust Service Principles and Criteria.</span></span> <span data-ttu-id="632cb-114">Attest Engagement under Attestation Standards (AT) 条例 101 是 SOC 2 和 SOC 3 报告的基础。</span><span class="sxs-lookup"><span data-stu-id="632cb-114">An Attest Engagement under Attestation Standards (AT) Section 101 is the basis of SOC 2 and SOC 3 reports.</span></span>

<span data-ttu-id="632cb-115">在 SOC 1 或 SOC 2 审核结尾部分，服务审核员会在 SOC 1 Type 2 或 SOC 2 Type 2 报告中提供评价意见，用于描述 CSP 系统并评估 CSP 对其控制措施描述的公平性。</span><span class="sxs-lookup"><span data-stu-id="632cb-115">At the conclusion of a SOC 1 or SOC 2 audit, the service auditor renders an opinion in a SOC 1 Type 2 or SOC 2 Type 2 report, which describes the CSP's system and assesses the fairness of the CSP's description of its controls.</span></span> <span data-ttu-id="632cb-116">该结论还会评估 CSP 控制措施是否设计得当、在指定日期是否正常运行，以及在指定时间段内是否有效运行。</span><span class="sxs-lookup"><span data-stu-id="632cb-116">It also evaluates whether the CSP's controls are designed appropriately, were in operation on a specified date, and were operating effectively over a specified time period.</span></span>

<span data-ttu-id="632cb-117">审核员还可以创建 SOC 3 报告（SOC 2 Type 2 审核报告的简化版），该报告适用于想要保证 CSP 控制措施但又不需要完整的 SOC 2 报告的用户。</span><span class="sxs-lookup"><span data-stu-id="632cb-117">Auditors can also create a SOC 3 report — an abbreviated version of the SOC 2 Type 2 audit report — for users who want assurance about the CSP's controls but don't need a full SOC 2 report.</span></span> <span data-ttu-id="632cb-118">只有在 CSP 的 SOC 2 审核意见为不合格时，才能授予 SOC 3 报告。</span><span class="sxs-lookup"><span data-stu-id="632cb-118">A SOC 3 report can be conferred only if the CSP has an unqualified audit opinion for SOC 2.</span></span>

## <a name="microsoft-and-soc-1-2-and-3-reports"></a><span data-ttu-id="632cb-119">Microsoft 和 SOC 1、2 和 3 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-119">Microsoft and SOC 1, 2, and 3 Reports</span></span>

<span data-ttu-id="632cb-120">独立的第三方审核员会根据 SOC 报告框架对 Microsoft 涵盖的云服务进行审核，至少每年一次。</span><span class="sxs-lookup"><span data-stu-id="632cb-120">Microsoft covered cloud services are audited at least annually against the SOC reporting framework by independent third-party auditors.</span></span> <span data-ttu-id="632cb-121">Microsoft 云服务的审核涵盖有关数据安全性、可用性、处理完整性和机密性的控制措施（如果每个服务的范围内信任原则适用）。</span><span class="sxs-lookup"><span data-stu-id="632cb-121">The audit for Microsoft cloud services covers controls for data security, availability, processing integrity, and confidentiality as applicable to in-scope trust principles for each service.</span></span>

<span data-ttu-id="632cb-122">Microsoft 已获得 SOC 1 Type 2、SOC 2 Type 2 和 SOC 3 报告。</span><span class="sxs-lookup"><span data-stu-id="632cb-122">Microsoft has achieved SOC 1 Type 2, SOC 2 Type 2, and SOC 3 reports.</span></span> <span data-ttu-id="632cb-123">通常，SOC 1 和 SOC 2 报告仅供与 Microsoft 签署了保密协议的客户使用；SOC 3 报告是公开提供的。</span><span class="sxs-lookup"><span data-stu-id="632cb-123">In general, the availability of SOC 1 and SOC 2 reports is restricted to customers who have signed nondisclosure agreements with Microsoft; the SOC 3 report is publicly available.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="632cb-124">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="632cb-124">Microsoft in-scope cloud services</span></span>

### <a name="covered-services-for-soc-1-and-soc-2"></a><span data-ttu-id="632cb-125">SOC 1 和 SOC 2 覆盖的服务</span><span class="sxs-lookup"><span data-stu-id="632cb-125">Covered services for SOC 1 and SOC 2</span></span>

- [<span data-ttu-id="632cb-126">Azure、Azure 政府和 Azure 德国</span><span class="sxs-lookup"><span data-stu-id="632cb-126">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="632cb-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="632cb-127">Microsoft Cloud App Security</span></span>
- [<span data-ttu-id="632cb-128">Dynamics 365 和 Dynamics 365 美国政府</span><span class="sxs-lookup"><span data-stu-id="632cb-128">Dynamics 365 and Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="632cb-129">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="632cb-129">Microsoft Graph</span></span>
- <span data-ttu-id="632cb-130">Intune</span><span class="sxs-lookup"><span data-stu-id="632cb-130">Intune</span></span>
- <span data-ttu-id="632cb-131">Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="632cb-131">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="632cb-132">Power Automate (以前称为 Microsoft Flow) 云服务，作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="632cb-132">Power Automate (formerly Microsoft Flow) cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="632cb-133">Office 365、Office 365 U.S. Government 和 Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="632cb-133">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="632cb-134">PowerApps 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="632cb-134">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="632cb-135">Power BI 云服务，作为独立服务提供，或者随 Office 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="632cb-135">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="632cb-136">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="632cb-136">Microsoft Stream</span></span>
- <span data-ttu-id="632cb-137">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="632cb-137">Azure DevOps Services</span></span>

### <a name="covered-services-for-soc-3"></a><span data-ttu-id="632cb-138">SOC 3 涵盖的服务</span><span class="sxs-lookup"><span data-stu-id="632cb-138">Covered services for SOC 3</span></span>

- [<span data-ttu-id="632cb-139">Azure、Azure 政府和 Azure 德国</span><span class="sxs-lookup"><span data-stu-id="632cb-139">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="632cb-140">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="632cb-140">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="632cb-141">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="632cb-141">Microsoft Graph</span></span>
- <span data-ttu-id="632cb-142">Intune</span><span class="sxs-lookup"><span data-stu-id="632cb-142">Intune</span></span>
- <span data-ttu-id="632cb-143">Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="632cb-143">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="632cb-144">Power Automate (以前称为 Microsoft Flow) 云服务，作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="632cb-144">Power Automate (formerly Microsoft Flow) cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="632cb-145">PowerApps 云服务，作为独立服务提供，后者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="632cb-145">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="632cb-146">Office 365、Office 365 U.S. Government 和 Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="632cb-146">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="632cb-147">Power BI</span><span class="sxs-lookup"><span data-stu-id="632cb-147">Power BI</span></span>
- <span data-ttu-id="632cb-148">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="632cb-148">Microsoft Stream</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="632cb-149">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="632cb-149">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="632cb-150">审核周期</span><span class="sxs-lookup"><span data-stu-id="632cb-150">Audit cycle</span></span>

<span data-ttu-id="632cb-151">Microsoft 云服务会根据 SOC 1（SSAE18、ISAE 3402）、SOC 2（AT 条例 101）和 SOC 3 标准每年至少进行一次审核。</span><span class="sxs-lookup"><span data-stu-id="632cb-151">Microsoft cloud services are audited at least annually against SOC 1 (SSAE18, ISAE 3402), SOC 2 (AT Section 101), and SOC 3 standards.</span></span>

#### <a name="azure-dynamics-365-microsoft-cloud-app-security-flow-microsoft-graph-intune-power-bi-powerapps-microsoft-stream-and-microsoft-datacenters"></a><span data-ttu-id="632cb-152">Azure、Dynamics 365、Microsoft Cloud App Security、Flow、Microsoft Graph、Intune、Power BI、PowerApps、Microsoft Stream 和 Microsoft 数据中心</span><span class="sxs-lookup"><span data-stu-id="632cb-152">Azure, Dynamics 365, Microsoft Cloud App Security, Flow, Microsoft Graph, Intune, Power BI, PowerApps, Microsoft Stream, and Microsoft Datacenters</span></span>

- [<span data-ttu-id="632cb-153">Azure + Dynamics 365 和 Azure + Dynamics 365 政府 SOC 1 类型 2 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-153">Azure + Dynamics 365 and Azure + Dynamics 365 Government SOC 1 Type 2 Report</span></span>](https://aka.ms/azuresoc1auditreport)
- [<span data-ttu-id="632cb-154">Azure + Dynamics 365 和 Azure + Dynamics 365 政府 SOC 2 类型 2 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-154">Azure + Dynamics 365 and Azure + Dynamics 365 Government SOC 2 Type 2 Report</span></span>](https://aka.ms/azuresoc2auditreport)
- [<span data-ttu-id="632cb-155">Azure + Dynamics 365 和 Azure + Dynamics 365 政府 SOC 3 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-155">Azure + Dynamics 365 and Azure + Dynamics 365 Government SOC 3 Report</span></span>](https://aka.ms/azuresoc3auditreport)

#### <a name="office-365"></a><span data-ttu-id="632cb-156">Office 365</span><span class="sxs-lookup"><span data-stu-id="632cb-156">Office 365</span></span>

- [<span data-ttu-id="632cb-157">Office 365 Core - SSAE 18 SOC 1 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-157">Office 365 Core - SSAE 18 SOC 1 Report</span></span>](https://aka.ms/o365SOC-1)
- [<span data-ttu-id="632cb-158">Office 365 Core - SSAE 18 SOC 2 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-158">Office 365 Core - SSAE 18 SOC 2 Report</span></span>](https://aka.ms/o365SOC-2)
- [<span data-ttu-id="632cb-159">Office 365 Core - SSAE 18 SOC 3 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-159">Office 365 Core - SSAE 18 SOC 3 Report</span></span>](https://aka.ms/o365SOC-3)
- [<span data-ttu-id="632cb-160">Office 365 Microservices T1 – SSAE 18 SOC2 Type I 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-160">Office 365 Microservices T1 – SSAE 18 SOC2 Type I Report</span></span>](https://aka.ms/o365-MS-SOC-2-type1)
- [<span data-ttu-id="632cb-161">客户密码箱 SOC 1 SSAE 16 审核报告</span><span class="sxs-lookup"><span data-stu-id="632cb-161">Customer Lockbox SOC 1 SSAE 16 Audit Report</span></span>](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [<span data-ttu-id="632cb-162">Yammer SOC 2 AT 101 Type I 审核报告</span><span class="sxs-lookup"><span data-stu-id="632cb-162">Yammer SOC 2 AT 101 Type I Audit Report</span></span>](https://aka.ms/YammerSOC2Type1AuditReport)
- [<span data-ttu-id="632cb-163">Yammer SOC 2 Type II 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-163">Yammer SOC 2 Type II Report</span></span>](https://aka.ms/yammerSOC-2)
- [<span data-ttu-id="632cb-164">请参阅 Bridge Letter 和其他审核报告</span><span class="sxs-lookup"><span data-stu-id="632cb-164">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="632cb-165">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="632cb-165">Frequently asked questions</span></span>

<span data-ttu-id="632cb-166">**如何获得 SOC 报告的副本？**</span><span class="sxs-lookup"><span data-stu-id="632cb-166">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="632cb-167">使用这些报告，您的审核员可以将 Microsoft 商务云服务结果与你自己的法律和法规要求相比较。</span><span class="sxs-lookup"><span data-stu-id="632cb-167">With the reports, your auditors can compare Microsoft business cloud services results with your own legal and regulatory requirements.</span></span>

- <span data-ttu-id="632cb-168">可通过[服务信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)查看所有 SOC 报告。</span><span class="sxs-lookup"><span data-stu-id="632cb-168">You can see all SOC reports through the [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx).</span></span>
- <span data-ttu-id="632cb-169">无法访问[服务信任平台](https://www.microsoft.com/trustcenter/STP/default.aspx)的 Azure DevOps 服务客户可以向 [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) 发送电子邮件来获取其 SOC 1 和 SOC 2 报告。</span><span class="sxs-lookup"><span data-stu-id="632cb-169">Azure DevOps Service customers that can't access [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) can email [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) for its SOC 1 and SOC 2 reports.</span></span> <span data-ttu-id="632cb-170">此电子邮件仅用于请求 Azure DevOps SOC 报告。</span><span class="sxs-lookup"><span data-stu-id="632cb-170">This email is to request Azure DevOps SOC reports only.</span></span>

<span data-ttu-id="632cb-171">**Azure SOC 报告多久发布一次？**</span><span class="sxs-lookup"><span data-stu-id="632cb-171">**How often are Azure SOC reports issued?**</span></span>

<span data-ttu-id="632cb-172">Azure、Microsoft Cloud App Security、Flow、Microsoft Graph、Intune、Power BI、PowerApps、Microsoft Stream 和 Microsoft 数据中心的 SOC 报告基于滚动的 12 个月运行时间窗（审计期），且每半年（周期结束日期是 3 月 31 日和 9 月 30 日）发布一次新报告。</span><span class="sxs-lookup"><span data-stu-id="632cb-172">SOC reports for Azure, Microsoft Cloud App Security, Flow, Microsoft Graph, Intune, Power BI, PowerApps, Microsoft Stream, and Microsoft Datacenters are based on a rolling 12-month run window (audit period) with new reports issued semi-annually (period ends are March 31 and September 30).</span></span> <span data-ttu-id="632cb-173">Bridge Letter 每季度发布一次，涵盖前面 3 个月。</span><span class="sxs-lookup"><span data-stu-id="632cb-173">Bridge letters are issued each quarter to cover the prior three month period.</span></span> <span data-ttu-id="632cb-174">例如，1 月信件涵盖 10/1-12/31，4 月信件涵盖 1/1-3/31，7 月信件涵盖 4/1-6/30，而 10 月信件涵盖 7/1-9/30。</span><span class="sxs-lookup"><span data-stu-id="632cb-174">For example, the January letter covers 10/1-12/31, the April letter covers 1/1-3/31, the July letter covers 4/1-6/30, and the October letter covers 7/1-9/30.</span></span> <span data-ttu-id="632cb-175">客户可从服务信任门户[下载](https://aka.ms/stp)最新报告。</span><span class="sxs-lookup"><span data-stu-id="632cb-175">Customers can [download](https://aka.ms/stp) the latest reports from the Service Trust Portal.</span></span>

<span data-ttu-id="632cb-176">**是否需要对 Microsoft 数据中心执行我自己的审核流程？**</span><span class="sxs-lookup"><span data-stu-id="632cb-176">**Do I need to conduct my own audit of Microsoft datacenters?**</span></span>

<span data-ttu-id="632cb-177">否。</span><span class="sxs-lookup"><span data-stu-id="632cb-177">No.</span></span> <span data-ttu-id="632cb-178">Microsoft 会与客户共享独立的审核报告与认证，以便客户能够检验 Microsoft 是否符合自己的安全承诺。</span><span class="sxs-lookup"><span data-stu-id="632cb-178">Microsoft shares the independent audit reports and certifications with customers so that they can verify Microsoft compliance with its security commitments.</span></span>

<span data-ttu-id="632cb-179">**能否在我组织的认证过程中使用 Microsoft 的合规性认证？**</span><span class="sxs-lookup"><span data-stu-id="632cb-179">**Can I use Microsoft's compliance in my organization's certification process?**</span></span>

<span data-ttu-id="632cb-180">正确。</span><span class="sxs-lookup"><span data-stu-id="632cb-180">Yes.</span></span> <span data-ttu-id="632cb-181">当您将应用程序和数据迁移到所覆盖的 Microsoft 云服务时，您可以把 Microsoft 所持有的审核与认证作为构建基础。</span><span class="sxs-lookup"><span data-stu-id="632cb-181">When you migrate your applications and data to covered Microsoft cloud services, you can build on the audits and certifications that Microsoft holds.</span></span> <span data-ttu-id="632cb-182">独立报告可证实 Microsoft 已实施用于维护您数据的安全性和隐私的控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="632cb-182">The independent reports attest to the effectiveness of controls that Microsoft has implemented to help maintain the security and privacy of your data.</span></span>

<span data-ttu-id="632cb-183">**从何处着手开展我自己组织的合规工作？**</span><span class="sxs-lookup"><span data-stu-id="632cb-183">**Where do I start with my organization's own compliance effort?**</span></span>

<span data-ttu-id="632cb-184">[面向服务组织的 SOC 工具套件](https://aka.ms/soc-toolkit)对了解 SOC 报告过程和推动组织利用这些报告是非常有用的资源。</span><span class="sxs-lookup"><span data-stu-id="632cb-184">The [SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) is a helpful resource for understanding SOC reporting processes and promoting your organization's use of them.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="632cb-185">使用 Microsoft 合规性分数评估风险</span><span class="sxs-lookup"><span data-stu-id="632cb-185">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="632cb-186">[Microsoft 合规性分数](compliance-score.md)是 [Microsoft 365 合规中心](microsoft-365-compliance-center.md)中的一项预览功能，旨在帮助你了解组织的合规情况并采取措施帮助降低风险。</span><span class="sxs-lookup"><span data-stu-id="632cb-186">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="632cb-187">在[设置合规性分数](compliance-score-setup.md)之后，从“**模板**”下拉菜单中选择预配置的“[SOC 1 模板](https://go.microsoft.com/fwlink/?linkid=2117918)”和“[SOC 2 模板](https://go.microsoft.com/fwlink/?linkid=2117919)”帮助组织满足此法规的要求。</span><span class="sxs-lookup"><span data-stu-id="632cb-187">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [SOC 1 template](https://go.microsoft.com/fwlink/?linkid=2117918) and the [SOC 2 template](https://go.microsoft.com/fwlink/?linkid=2117919) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="632cb-188">资源</span><span class="sxs-lookup"><span data-stu-id="632cb-188">Resources</span></span>

- [<span data-ttu-id="632cb-189">使用 Microsoft 云服务更好地保护你的数据</span><span class="sxs-lookup"><span data-stu-id="632cb-189">Better protect your data by using Microsoft cloud services</span></span>](https://www.microsoft.com/trustcenter/guidance/protect-data)
- [<span data-ttu-id="632cb-190">Service Organization Control (SOC) 报告</span><span class="sxs-lookup"><span data-stu-id="632cb-190">Service Organization Control (SOC) Reports</span></span>](https://aka.ms/mssocreports)
- [<span data-ttu-id="632cb-191">SSAE 16 概述</span><span class="sxs-lookup"><span data-stu-id="632cb-191">SSAE 16 Overview</span></span>](http://ssae16.com/SSAE16_overview.html)
- [<span data-ttu-id="632cb-192">ISAE 3402 概述</span><span class="sxs-lookup"><span data-stu-id="632cb-192">ISAE 3402 Overview</span></span>](http://isae3402.com/ISAE3402_overview.html)
- [<span data-ttu-id="632cb-193">Microsoft 联机服务条款</span><span class="sxs-lookup"><span data-stu-id="632cb-193">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="632cb-194">Microsoft 政府云</span><span class="sxs-lookup"><span data-stu-id="632cb-194">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="632cb-195">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="632cb-195">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
