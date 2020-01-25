---
title: ISO/IEC 27017:2015 信息安全控制措施行为守则
description: Microsoft 云服务已实施此信息安全控制措施行为守则。
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
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 758e7d0f3e82afa6cfd4b90501bd84080d8f6303
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260010"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="b68c4-104">ISO/IEC 27017:2015 信息安全控制措施行为守则</span><span class="sxs-lookup"><span data-stu-id="b68c4-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="b68c4-105">ISO-IEC 27017 概述</span><span class="sxs-lookup"><span data-stu-id="b68c4-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="b68c4-106">ISO/IEC 27017:2015 行为守则专为组织设计，用作在根据 ISO/IEC 27002:2013 实施云计算信息安全管理系统时选择云服务信息安全控制措施的参考。</span><span class="sxs-lookup"><span data-stu-id="b68c4-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="b68c4-107">此外，云服务提供商还可将其用作实施公认的保护控制措施的指南文档。</span><span class="sxs-lookup"><span data-stu-id="b68c4-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="b68c4-108">此国际标准基于 ISO/IEC 27002 提供了特定于云的附加实施指南，并针对 ISO/IEC 27002:2013 第 5-18 条中特定于云的信息安全威胁和风险提供了附加控制措施、实施指南和其他信息。</span><span class="sxs-lookup"><span data-stu-id="b68c4-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="b68c4-109">具体来说，此标准提供了 ISO/IEC 27002 中有关 37 个控制措施的指南，以及在 ISO/IEC 27002 中未重复的 7 个新控制措施。</span><span class="sxs-lookup"><span data-stu-id="b68c4-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="b68c4-110">这些新控制措施可解决以下重要方面：</span><span class="sxs-lookup"><span data-stu-id="b68c4-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="b68c4-111">云计算环境中的共享角色和职责</span><span class="sxs-lookup"><span data-stu-id="b68c4-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="b68c4-112">合同终止时删除和退回云服务客户资产</span><span class="sxs-lookup"><span data-stu-id="b68c4-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="b68c4-113">保护客户的虚拟环境并将其与其他客户的虚拟环境分离</span><span class="sxs-lookup"><span data-stu-id="b68c4-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="b68c4-114">强化要求以满足业务需求的虚拟机</span><span class="sxs-lookup"><span data-stu-id="b68c4-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="b68c4-115">云计算环境的管理操作程序</span><span class="sxs-lookup"><span data-stu-id="b68c4-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="b68c4-116">使客户能够监视云计算环境中的相关活动</span><span class="sxs-lookup"><span data-stu-id="b68c4-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="b68c4-117">协调虚拟和物理网络的安全管理</span><span class="sxs-lookup"><span data-stu-id="b68c4-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="b68c4-118">Microsoft 和 ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="b68c4-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="b68c4-119">ISO/IEC 27017 在为云服务提供商和云服务客户提供指南方面是独一无二的。</span><span class="sxs-lookup"><span data-stu-id="b68c4-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="b68c4-120">此外，它还为云服务客户提供有关预期从云服务提供商获得内容的实用信息。</span><span class="sxs-lookup"><span data-stu-id="b68c4-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="b68c4-121">通过确保客户了解云中的共同职责，他们可以直接从 ISO/IEC 27017 中受益。</span><span class="sxs-lookup"><span data-stu-id="b68c4-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

<span data-ttu-id="b68c4-122">了解有关 Microsoft 云的 ISO/IEC 27017 优势：[下载 ISO/IEC 27017: 信息安全控制措施行为守则](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="b68c4-122">Learn about the benefits of ISO/IEC 27017 on the Microsoft Cloud: [Download the ISO/IEC 27017: Code of Practice for Information Security Controls](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="b68c4-123">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="b68c4-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="b68c4-124">Azure、Azure 政府和 Azure 德国</span><span class="sxs-lookup"><span data-stu-id="b68c4-124">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="b68c4-125">云应用安全</span><span class="sxs-lookup"><span data-stu-id="b68c4-125">Cloud App Security</span></span>
- [<span data-ttu-id="b68c4-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b68c4-126">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="b68c4-127">Genomics</span><span class="sxs-lookup"><span data-stu-id="b68c4-127">Genomics</span></span>
- <span data-ttu-id="b68c4-128">Graph</span><span class="sxs-lookup"><span data-stu-id="b68c4-128">Graph</span></span>
- <span data-ttu-id="b68c4-129">Intune</span><span class="sxs-lookup"><span data-stu-id="b68c4-129">Intune</span></span>
- <span data-ttu-id="b68c4-130">Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="b68c4-130">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="b68c4-131">Microsoft Flow 云服务，作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="b68c4-131">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="b68c4-132">Office 365、Office 365 美国政府版、Office 365 美国政府版防御和 Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="b68c4-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="b68c4-133">PowerApps 云服务，作为独立服务提供，或者随 Office 365 或 Dynamics 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="b68c4-133">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="b68c4-134">Power BI 云服务，作为独立服务提供，或者随 Office 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="b68c4-134">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="b68c4-135">请参阅 Office 365 中涵盖的服务的[详细列表](https://go.microsoft.com/fwlink/p/?linkid=2077751)</span><span class="sxs-lookup"><span data-stu-id="b68c4-135">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="b68c4-136">审核、报告和证书</span><span class="sxs-lookup"><span data-stu-id="b68c4-136">Audits, reports, and certificates</span></span>

<span data-ttu-id="b68c4-137">作为 ISO/IEC 27001:2013 认证过程的一部分，每年都会对 Microsoft 云服务进行 ISO/IEC 27017:2015 行为守则审核。</span><span class="sxs-lookup"><span data-stu-id="b68c4-137">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="b68c4-138">Azure ISO 27017 证书</span><span class="sxs-lookup"><span data-stu-id="b68c4-138">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="b68c4-139">Azure ISO 27017 评估报告</span><span class="sxs-lookup"><span data-stu-id="b68c4-139">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="b68c4-140">Azure ISO 27017 适用性声明</span><span class="sxs-lookup"><span data-stu-id="b68c4-140">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/AzureISO27017StatementofApplicability)
- [<span data-ttu-id="b68c4-141">Office 365 ISO 27001、27018 和 27017 审核评估报告</span><span class="sxs-lookup"><span data-stu-id="b68c4-141">Office 365 ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="b68c4-142">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="b68c4-142">Frequently asked questions</span></span>

<span data-ttu-id="b68c4-143">此标准适用于哪些人员？</span><span class="sxs-lookup"><span data-stu-id="b68c4-143">To whom does the standard apply?</span></span>

<span data-ttu-id="b68c4-144">此行为守则为云服务提供商和云服务客户提供控制措施和实施指南。</span><span class="sxs-lookup"><span data-stu-id="b68c4-144">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="b68c4-145">其格式结构类似于 ISO/IEC 27002:2013。</span><span class="sxs-lookup"><span data-stu-id="b68c4-145">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="b68c4-146">**在哪里可以查看 Microsoft 的 ISO/IEC 27017:2015 合规性信息？**</span><span class="sxs-lookup"><span data-stu-id="b68c4-146">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="b68c4-147">你可以下载适用于 Azure、Intune 和 Power BI 的 [ISO/IEC 27017:2015 证书](https://aka.ms/azureiso27017)。</span><span class="sxs-lookup"><span data-stu-id="b68c4-147">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="b68c4-148">**能否在我所在组织的认证过程中使用 Microsoft 服务的 ISO/IEC 27017 合规性认证？**</span><span class="sxs-lookup"><span data-stu-id="b68c4-148">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="b68c4-149">能。</span><span class="sxs-lookup"><span data-stu-id="b68c4-149">Yes.</span></span> <span data-ttu-id="b68c4-150">如果你的企业正在寻求对任何 Microsoft 范围内企业云服务中部署的实施流程进行认证，则可以在你的合规性评估中利用 Microsoft 的相关认证。</span><span class="sxs-lookup"><span data-stu-id="b68c4-150">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="b68c4-151">但是，你需要负责聘请评估方来评估合规性政策的实施情况，以及所在组织中的控制措施和流程。</span><span class="sxs-lookup"><span data-stu-id="b68c4-151">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="b68c4-152">**如何获得适用审核报告的副本？**</span><span class="sxs-lookup"><span data-stu-id="b68c4-152">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="b68c4-153">[服务信任门户](https://aka.ms/stphelp)提供独立第三方审核报告和其他相关文档。</span><span class="sxs-lookup"><span data-stu-id="b68c4-153">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="b68c4-154">你可以使用门户下载和查看本文档以就自己的法规要求获得帮助。</span><span class="sxs-lookup"><span data-stu-id="b68c4-154">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="b68c4-155">资源</span><span class="sxs-lookup"><span data-stu-id="b68c4-155">Resources</span></span>

- [<span data-ttu-id="b68c4-156">ISO/IEC 27017:2015 行为守则</span><span class="sxs-lookup"><span data-stu-id="b68c4-156">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="b68c4-157">Microsoft 在线服务条款</span><span class="sxs-lookup"><span data-stu-id="b68c4-157">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="b68c4-158">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="b68c4-158">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="b68c4-159">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="b68c4-159">Download the offering backgrounder</span></span>

<span data-ttu-id="b68c4-160">需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="b68c4-160">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="b68c4-161">请下载 [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b68c4-161">Download the [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span></span>
