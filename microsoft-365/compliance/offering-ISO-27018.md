---
title: 保护云中个人数据的 ISO/IEC 27018 行为守则
description: Microsoft 是第一家遵循此云隐私行为守则的云提供商。
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
ms.openlocfilehash: 176c80309e3a99707191c2dfba37e5147c875b17
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417696"
---
# <a name="isoiec-27018-code-of-practice-for-protecting-personal-data-in-the-cloud"></a><span data-ttu-id="1ccf8-104">保护云中个人数据的 ISO/IEC 27018 行为守则</span><span class="sxs-lookup"><span data-stu-id="1ccf8-104">ISO/IEC 27018 Code of Practice for Protecting Personal Data in the Cloud</span></span>

## <a name="isoiec-27018-overview"></a><span data-ttu-id="1ccf8-105">ISO/IEC 27018 概述</span><span class="sxs-lookup"><span data-stu-id="1ccf8-105">ISO/IEC 27018 overview</span></span>

<span data-ttu-id="1ccf8-106">国际标准化组织 (ISO) 是一个独立的非政府组织，是全球最大的自愿性国际标准开发者联盟。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-106">The International Organization for Standardization (ISO) is an independent nongovernmental organization and the world's largest developer of voluntary international standards.</span></span> <span data-ttu-id="1ccf8-107">ISO/IEC 27000 系列标准可帮助每种类型和规模的组织确保信息资产安全无虞。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-107">The ISO/IEC 27000 family of standards helps organizations of every type and size keep information assets secure.</span></span>

<span data-ttu-id="1ccf8-108">ISO 于 2014 年采用了第一个国际云隐私行为守则 ISO/IEC 27018:2014（ISO/IEC 27001 的附录）。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-108">In 2014, the ISO adopted ISO/IEC 27018:2014, an addendum to ISO/IEC 27001, the first international code of practice for cloud privacy.</span></span> <span data-ttu-id="1ccf8-109">该标准基于欧盟数据保护法律，为充当个人身份信息 (PII) 处理者的云服务提供商 (CSP) 提供有关评估风险和实施先进控制措施的专门指导，以便保护 PII。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-109">Based on EU data-protection laws, it gives specific guidance to cloud service providers (CSPs) acting as processors of personally identifiable information (PII) on assessing risks and implementing state-of-the-art controls for protecting PII.</span></span>

<span data-ttu-id="1ccf8-110">Microsoft 和 ISO/IEC 27018</span><span class="sxs-lookup"><span data-stu-id="1ccf8-110">Microsoft and ISO/IEC 27018</span></span>

<span data-ttu-id="1ccf8-111">至少一年一次，Microsoft Azure 和 Azure 德国会由一个经认可的第三方认证机构对其是否符合 ISO/IEC 27001 和 ISO/IEC 27018 进行审核，以提供独立验证，证明适用的安全控制措施已经就位且有效运行。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-111">At least once a year, Microsoft Azure and Azure Germany are audited for compliance with ISO/IEC 27001 and ISO/IEC 27018 by an accredited third-party certification body, providing independent validation that applicable security controls are in place and operating effectively.</span></span> <span data-ttu-id="1ccf8-112">作为此合规性验证过程的一部分，审核员会在其适用性声明中确认 Microsoft 范围内云服务和商业技术支持服务已包含 ISO/IEC 27018 控制措施，可保护 Azure 中的 PII。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-112">As part of this compliance verification process, the auditors validate in their statement of applicability that Microsoft in-scope cloud services and commercial technical support services have incorporated ISO/IEC 27018 controls for the protection of PII in Azure.</span></span> <span data-ttu-id="1ccf8-113">为保持合规性，Microsoft 云服务必须接受第三方年度审核。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-113">To remain compliant, Microsoft cloud services must be subject to annual third-party reviews.</span></span>

<span data-ttu-id="1ccf8-114">通过遵循 ISO/IEC 27001 标准以及 ISO/IEC 27018 包含的行为守则，Microsoft 作为第一家纳入此行为守则的主要云提供商，能够证明其隐私政策和过程安全可靠，且符合其高标准。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-114">By following the standards of ISO/IEC 27001 and the code of practice embodied in ISO/IEC 27018, Microsoft (the first major cloud provider to incorporate this code of practice) demonstrates that its privacy policies and procedures are robust and in line with its high standards.</span></span>

- <span data-ttu-id="1ccf8-115">**Microsoft 云服务客户知道其数据的存储位置。**</span><span class="sxs-lookup"><span data-stu-id="1ccf8-115">**Customers of Microsoft cloud services know where their data is stored.**</span></span> <span data-ttu-id="1ccf8-116">因为 ISO/IEC 27018 要求经认证的 CSP 告知客户将其数据存储在哪个国家/地区，所以，Microsoft 云服务客户可以看到他们需要遵守的任何适用的信息安全性规则。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-116">Because ISO/IEC 27018 requires certified CSPs to inform customers of the countries in which their data may be stored, Microsoft cloud service customers have the visibility they need to comply with any applicable information security rules.</span></span>
- <span data-ttu-id="1ccf8-117">**未经明确同意，客户数据不会被用于市场营销或广告宣传。**</span><span class="sxs-lookup"><span data-stu-id="1ccf8-117">**Customer data won't be used for marketing or advertising without explicit consent.**</span></span> <span data-ttu-id="1ccf8-118">某些 CSP 会出于其自身商业目的使用客户数据，包括进行有针对性的广告宣传。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-118">Some CSPs use customer data for their own commercial ends, including for targeted advertising.</span></span> <span data-ttu-id="1ccf8-119">由于 Microsoft 已对其范围内企业云服务采用了 ISO/IEC 27018，因此，未经客户明确同意，其数据绝不会用于此类目的，并且“同意”并不表示可以无条件使用云服务，客户在这方面大可放心。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-119">Because Microsoft has adopted ISO/IEC 27018 for its in-scope enterprise cloud services, customers can rest assured that their data will never be used for such purposes without explicit consent, and that consent cannot be a condition for use of the cloud service.</span></span>
- <span data-ttu-id="1ccf8-120">**Microsoft 客户了解其 PII 的使用情况。**</span><span class="sxs-lookup"><span data-stu-id="1ccf8-120">**Microsoft customers know what's happening with their PII.**</span></span> <span data-ttu-id="1ccf8-121">ISO/IEC 27018 要求制定相应策略，以允许在合理期限内返回、传输和安全处置个人信息。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-121">ISO/IEC 27018 requires a policy that allows for the return, transfer, and secure disposal of personal information within a reasonable period of time.</span></span> <span data-ttu-id="1ccf8-122">如果 Microsoft 与需要访问客户数据的其他公司合作，Microsoft 将主动公开这些附属处理者的身份。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-122">If Microsoft works with other companies that need access to your customer data, Microsoft proactively discloses the identities of those sub-processors.</span></span>
- <span data-ttu-id="1ccf8-123">**在客户数据披露方面，Microsoft 仅遵守具有法律约束力的请求。**</span><span class="sxs-lookup"><span data-stu-id="1ccf8-123">**Microsoft complies only with legally binding requests for disclosure of customer data.**</span></span> <span data-ttu-id="1ccf8-124">如果 Microsoft 必须遵守如刑事侦察这样的请求，Microsoft 将始终通知客户，除非法律禁止这样做。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-124">If Microsoft must comply with such a request (as in the case of a criminal investigation), it will always notify the customer unless it is prohibited by law from doing so.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="1ccf8-125">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="1ccf8-125">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="1ccf8-126">Azure、Azure 政府和 Azure 德国</span><span class="sxs-lookup"><span data-stu-id="1ccf8-126">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="1ccf8-127">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="1ccf8-127">Azure DevOps Services</span></span>
- <span data-ttu-id="1ccf8-128">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1ccf8-128">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1ccf8-129">Dynamics 365、Dynamics 365 和 Dynamics 365 德国</span><span class="sxs-lookup"><span data-stu-id="1ccf8-129">Dynamics 365, Dynamics 365, and Dynamics 365 Germany</span></span>
- <span data-ttu-id="1ccf8-130">Microsoft 专业服务：针对 Azure、Dynamics 365、Intune 及 Microsoft 365 商业版中型企业客户的高级和本地支持。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-130">Microsoft Professional Services: Premier and On Premises for Azure, Dynamics 365, Intune, and for medium business and enterprise customers of Microsoft 365 for business</span></span>
- <span data-ttu-id="1ccf8-131">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="1ccf8-131">Microsoft Graph</span></span>
- <span data-ttu-id="1ccf8-132">Microsoft 医疗保健机器人</span><span class="sxs-lookup"><span data-stu-id="1ccf8-132">Microsoft Healthcare Bot</span></span>
- <span data-ttu-id="1ccf8-133">Intune</span><span class="sxs-lookup"><span data-stu-id="1ccf8-133">Intune</span></span>
- <span data-ttu-id="1ccf8-134">Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="1ccf8-134">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="1ccf8-135">Power Automate (以前称为 Microsoft Flow)： 云服务作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="1ccf8-135">Power Automate (formerly Microsoft Flow): cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="1ccf8-136">Office 365、Office 365 U.S. Government 和 Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="1ccf8-136">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2077751)
- <span data-ttu-id="1ccf8-137">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="1ccf8-137">Office 365 Germany</span></span>
- <span data-ttu-id="1ccf8-138">OMS Service Map</span><span class="sxs-lookup"><span data-stu-id="1ccf8-138">OMS Service Map</span></span>
- <span data-ttu-id="1ccf8-139">PowerApps 云服务：作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="1ccf8-139">PowerApps cloud service: either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="1ccf8-140">Power BI 云服务：作为独立服务提供，或者随 Office 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="1ccf8-140">Power BI cloud service: either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="1ccf8-141">Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="1ccf8-141">Power BI Embedded</span></span>
- <span data-ttu-id="1ccf8-142">Power Virtual Agents</span><span class="sxs-lookup"><span data-stu-id="1ccf8-142">Power Virtual Agents</span></span>
- <span data-ttu-id="1ccf8-143">Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="1ccf8-143">Microsoft Threat Experts</span></span>
- <span data-ttu-id="1ccf8-144">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="1ccf8-144">Microsoft Stream</span></span>
- <span data-ttu-id="1ccf8-145">Windows Defender ATP — 终结点检测和响应、自动调查和修正、安全分数</span><span class="sxs-lookup"><span data-stu-id="1ccf8-145">Windows Defender ATP — Endpoint Detection & Response, Automatic Investigation & Remediation, Secure Score</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="1ccf8-146">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="1ccf8-146">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="1ccf8-147">审核周期</span><span class="sxs-lookup"><span data-stu-id="1ccf8-147">Audit cycle</span></span>

<span data-ttu-id="1ccf8-148">作为 ISO/IEC 27001 认证过程的一部分，每年会对 Microsoft 云服务和商业技术支持服务进行一次 ISO/IEC 27018 行为守则审核。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-148">Microsoft cloud and commercial technical support services are audited once a year for the ISO/IEC 27018 code of practice as part of the certification process for ISO/IEC 27001.</span></span>

### <a name="audits-and-reports"></a><span data-ttu-id="1ccf8-149">审核和报告</span><span class="sxs-lookup"><span data-stu-id="1ccf8-149">Audits and reports</span></span>

- [<span data-ttu-id="1ccf8-150">Azure、Dynamics 365 和联机服务：ISO27018 证书</span><span class="sxs-lookup"><span data-stu-id="1ccf8-150">Azure, Dynamics 365, and Online Services: ISO27018 Certificate</span></span>](https://aka.ms/azureiso27018cert)
- [<span data-ttu-id="1ccf8-151">AAzure、Dynamics 365 和联机服务： ISO27018 评估报告</span><span class="sxs-lookup"><span data-stu-id="1ccf8-151">AAzure, Dynamics 365, and Online Services: ISO27018 Assessment Report</span></span>](https://aka.ms/azureiso27001report)
- [<span data-ttu-id="1ccf8-152">Azure 德国：ISO 27018 保护云中个人数据的行为守则证书</span><span class="sxs-lookup"><span data-stu-id="1ccf8-152">Azure Germany: ISO27018 Code of Practice for Protecting Personal Data in the Cloud Certificate</span></span>](https://servicetrust.microsoft.com/Documents/ComplianceReports?downloadDocument=1&documentId=6a0dab80-8382-4af6-980c-ed2ed9a341c6)

### <a name="office-365"></a><span data-ttu-id="1ccf8-153">Office 365</span><span class="sxs-lookup"><span data-stu-id="1ccf8-153">Office 365</span></span>

- [<span data-ttu-id="1ccf8-154">Office 365: ISO 27001、27018 和 27017 审核评估报告</span><span class="sxs-lookup"><span data-stu-id="1ccf8-154">Office 365: ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)
- [<span data-ttu-id="1ccf8-155">Yammer ISO 27018 审核评估报告</span><span class="sxs-lookup"><span data-stu-id="1ccf8-155">Yammer ISO 27018 Audit Assessment Report</span></span>](https://aka.ms/YammerISO27018Auditreport)

### <a name="azure-devops-services"></a><span data-ttu-id="1ccf8-156">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="1ccf8-156">Azure DevOps Services</span></span>

- [<span data-ttu-id="1ccf8-157">Azure DevOps Services：ISO27018 证书 PII 665918</span><span class="sxs-lookup"><span data-stu-id="1ccf8-157">Azure DevOps Services: ISO27018 Certificate PII 665918</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2062252)

## <a name="frequently-asked-questions"></a><span data-ttu-id="1ccf8-158">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="1ccf8-158">Frequently asked questions</span></span>

<span data-ttu-id="1ccf8-159">**ISO/IEC 27018 适用于哪些对象？**</span><span class="sxs-lookup"><span data-stu-id="1ccf8-159">**To whom does ISO/IEC 27018 apply?**</span></span>

<span data-ttu-id="1ccf8-160">该行为守则适用于根据合同处理其他组织的 PII 的 CSP。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-160">This code of practice applies to CSPs that process PII under contract for other organizations.</span></span> <span data-ttu-id="1ccf8-161">在 Microsoft，它还适用于这些 CSP 的支持。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-161">At Microsoft, it also applies to the support of those CSPs.</span></span>

<span data-ttu-id="1ccf8-162">**“个人信息控制者”和“个人信息处理者”之间有何区别？**</span><span class="sxs-lookup"><span data-stu-id="1ccf8-162">**What is the difference between 'personal information controllers' and 'personal information processors'?**</span></span>

<span data-ttu-id="1ccf8-163">在 ISO/IEC 27018 背景下：</span><span class="sxs-lookup"><span data-stu-id="1ccf8-163">In the context of ISO/IEC 27018:</span></span>

- <span data-ttu-id="1ccf8-164">“控制者”控制个人信息的收集、保留、处理或使用；其中包括代表其他公司控制信息的人员。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-164">'Controllers' control the collection, holding, processing, or use of personal information; they include those who control it on another company's behalf.</span></span>
- <span data-ttu-id="1ccf8-165">“处理者”代表控制者处理信息；他们不决定如何使用信息或处理的目的。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-165">'Processors' process information on behalf of controllers; they do not make decisions as to how to use the information or the purposes of the processing.</span></span> <span data-ttu-id="1ccf8-166">在提供企业云服务时，Microsoft（作为你的供应商）是信息处理者。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-166">In providing its enterprise cloud services, Microsoft (as a vendor to you) is an information processor.</span></span>

<span data-ttu-id="1ccf8-167">**可在何处查看针对 ISO/IEC 27018 的 Microsoft 合规性信息？**</span><span class="sxs-lookup"><span data-stu-id="1ccf8-167">**Where can I view Microsoft compliance information for ISO/IEC 27018?**</span></span>

- <span data-ttu-id="1ccf8-168">你可以查看针对 [Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016)、[Microsoft 专业服务](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270)和 [Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016) 的 BSI 中的 ISO/IEC 27018 证书。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-168">You can review the ISO/IEC 27018 certificates from BSI for [Azure](https://go.microsoft.com/fwlink/p/?linkid=2078016), [Microsoft Professional Services](https://www.bsigroup.com/Our-services/Management-system-certification/Certificate-and-Client-Directory-Search/Certificate-Client-Directory-Search-Results/?searchkey=company%3dMicrosoft%2bCorporation&licencenumber=PII%20642270), and [Power BI](https://go.microsoft.com/fwlink/p/?linkid=2078016).</span></span>
- <span data-ttu-id="1ccf8-169">此外，你还可以查看针对 [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert)、[Office 365](https://aka.ms/Office365-Cert) 和 [Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159) 的 BSI 中的 ISO/IEC 27001 证书（ISO/IEC 27018 认证基于这些证书）。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-169">You can also review ISO/IEC 27001 certificates from BSI upon which ISO/IEC 27018 certification is based for [Dynamics 365](https://aka.ms/Dynamics-CRM-Online-Cert), [Office 365](https://aka.ms/Office365-Cert), and [Azure DevOps Services](https://go.microsoft.com/fwlink/p/?linkid=2062159).</span></span>
- <span data-ttu-id="1ccf8-170">若要查看 BSI 报告，了解独立审核员是否已验证 Microsoft 符合 ISO/IEC 27018，请访问[服务信任门户](https://aka.ms/stphelp)。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-170">To review the BSI reports, the independent auditor that validated Microsoft compliance with ISO/IEC 27018, visit the [Service Trust Portal](https://aka.ms/stphelp).</span></span>

<span data-ttu-id="1ccf8-171">**能否在我组织的认证过程中使用 Microsoft 的合规性认证？**</span><span class="sxs-lookup"><span data-stu-id="1ccf8-171">**Can I use Microsoft's compliance in my organization's certification process?**</span></span>

<span data-ttu-id="1ccf8-172">可以。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-172">Yes.</span></span> <span data-ttu-id="1ccf8-173">如果符合 ISO/IEC 27018 对你的业务及在任何 Microsoft 范围内企业云服务上部署的实施非常重要，则可在合规性评估中使用 Microsoft 的 ISO/IEC 27018 合规性证明和 Microsoft 的 ISO/IEC 27001 合规性证书。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-173">If compliance with ISO/IEC 27018 is important for your business and implementations deployed on any of Microsoft in-scope enterprise cloud services, you can use Microsoft's attestation of compliance with ISO/IEC 27018 with Microsoft's certification for ISO/IEC 27001 in your compliance assessment.</span></span>

<span data-ttu-id="1ccf8-174">但是，你需要负责聘请评估方来评估合规性政策的实施情况，以及所在组织中的控制措施和流程。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-174">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="1ccf8-175">使用 Microsoft 合规性分数评估风险</span><span class="sxs-lookup"><span data-stu-id="1ccf8-175">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="1ccf8-176">[Microsoft 合规性分数](compliance-score.md)是 [Microsoft 365 合规中心](microsoft-365-compliance-center.md)中的一项预览功能，旨在帮助你了解组织的合规情况并采取措施帮助降低风险。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-176">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="1ccf8-177">在[设置合规性分数](compliance-score-setup.md)之后，从“**模板**”下拉菜单中选择预配置的“[ISO 27018 模板](https://go.microsoft.com/fwlink/?linkid=2117523)”帮助组织满足此法规的要求。</span><span class="sxs-lookup"><span data-stu-id="1ccf8-177">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [ISO 27018 template](https://go.microsoft.com/fwlink/?linkid=2117523) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="1ccf8-178">资源</span><span class="sxs-lookup"><span data-stu-id="1ccf8-178">Resources</span></span>

- [<span data-ttu-id="1ccf8-179">ISO/IEC 27018:2014 行为守则</span><span class="sxs-lookup"><span data-stu-id="1ccf8-179">ISO/IEC 27018:2014 code of practice</span></span>](https://aka.ms/ISO.IEC_27018.2014)
- [<span data-ttu-id="1ccf8-180">Microsoft 公共控制中心合规性框架</span><span class="sxs-lookup"><span data-stu-id="1ccf8-180">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="1ccf8-181">Microsoft 企业云和技术服务的数据访问策略</span><span class="sxs-lookup"><span data-stu-id="1ccf8-181">Data access policies for Microsoft enterprise cloud and technical services</span></span>](https://www.microsoft.com/trustcenter/Privacy/Who-can-access-your-data-and-on-what-terms)
- [<span data-ttu-id="1ccf8-182">Microsoft 在线服务条款</span><span class="sxs-lookup"><span data-stu-id="1ccf8-182">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="1ccf8-183">Microsoft 政府云</span><span class="sxs-lookup"><span data-stu-id="1ccf8-183">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="1ccf8-184">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="1ccf8-184">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
