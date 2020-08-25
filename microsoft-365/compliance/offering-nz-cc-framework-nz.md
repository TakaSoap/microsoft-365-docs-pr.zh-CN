---
title: 新西威政府云计算安全和隐私注意事项
description: Microsoft NZ 解决了在新西方云计算框架中发布的问题。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
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
ms.openlocfilehash: 99e7d28bea37ec282bd6358b5af81a3078dfdd38
ms.sourcegitcommit: b7f4f1e04b27519b818d4255022b28f99fbe54af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46852498"
---
# <a name="new-zealand-government-cloud-computing-security-and-privacy-considerations"></a><span data-ttu-id="c2a98-104">新西威政府云计算安全和隐私注意事项</span><span class="sxs-lookup"><span data-stu-id="c2a98-104">New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

## <a name="new-zealand-government-cloud-computing-security-and-privacy-overview"></a><span data-ttu-id="c2a98-105">新西威政府云计算安全和隐私概述</span><span class="sxs-lookup"><span data-stu-id="c2a98-105">New Zealand Government Cloud Computing Security and Privacy overview</span></span>

<span data-ttu-id="c2a98-106">新西方政府于 2015 年 10 月，新西亚政府将由修订的全政府 ICT 策略进行了修订，以补充了其"云优先"策略，以便使用整个公共企业的信息技术。</span><span class="sxs-lookup"><span data-stu-id="c2a98-106">In October 2015, the New Zealand Government endorsed a revised all-government ICT strategy that reaffirmed its “cloud first” policy on using information technology across the public sector.</span></span> <span data-ttu-id="c2a98-107">修改后的策略保留着美国政府政府政府机构和 GCIO 管理人员的权限开发和实现的"云计算风险 (保证) 。</span><span class="sxs-lookup"><span data-stu-id="c2a98-107">The revised strategy retains the “Cloud Computing Risk and Assurance Framework” that was developed and implemented under the authority of the NZ Government Chief Information Officer (GCIO).</span></span>

<span data-ttu-id="c2a98-108">政府希望所有新的西班状态服务机构都能在此框架中使用，以评估和采用云服务。</span><span class="sxs-lookup"><span data-stu-id="c2a98-108">The government expects all New Zealand State Service agencies to work within this framework when assessing and adopting cloud services.</span></span> <span data-ttu-id="c2a98-109">"云计算要求"概述了在采用云服务时机构必须执行的操作，并概述政府云策略的历史记录。</span><span class="sxs-lookup"><span data-stu-id="c2a98-109">“Requirements for Cloud Computing” outlines what agencies must do when adopting cloud services along with an overview of the history of the government’s cloud policy.</span></span>

<span data-ttu-id="c2a98-110">为了帮助 NZ 政府机构对潜在云解决方案进行一致且可靠的截断分类，GCIO 发布了"云计算：信息安全和隐私注意事项" (上的"云计算 ISPC") 。</span><span class="sxs-lookup"><span data-stu-id="c2a98-110">To assist NZ government agencies in conducting consistent and robust due diligence on potential cloud solutions, the GCIO has published “Cloud Computing: Information Security and Privacy Considerations” (the “Cloud Computing ISPC”).</span></span> <span data-ttu-id="c2a98-111">本文档包含侧重于数据重点高的 100 个以上的问题、隐私、安全性、治理、机密性、数据完整性、可用性和事件响应和管理。</span><span class="sxs-lookup"><span data-stu-id="c2a98-111">This document contains more than 100 questions focused on data sovereignty, privacy, security, governance, confidentiality, data integrity, availability, and incident response and management.</span></span> <span data-ttu-id="c2a98-112">请注意，"云计算 IPSC"并不针对云服务提供商必须证明正式合规性定义 NZ 政府标准。</span><span class="sxs-lookup"><span data-stu-id="c2a98-112">Note that “Cloud Computing IPSC” does not define a NZ government standard against which cloud service providers must demonstrate formal compliance.</span></span> <span data-ttu-id="c2a98-113">不过，文档中设置了许多问题是，指向了解云服务提供商如何遵从大量相关标准的重要性。</span><span class="sxs-lookup"><span data-stu-id="c2a98-113">Many of the questions set out in the document do, however, point toward the importance of understanding how cloud service providers comply with a wide array of relevant standards.</span></span>

<span data-ttu-id="c2a98-114">Microsoft 和新西政府云计算安全和隐私注意事项</span><span class="sxs-lookup"><span data-stu-id="c2a98-114">Microsoft and New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

<span data-ttu-id="c2a98-115">为了帮助代理对 Microsoft 企业云服务进行分析和评估，Microsoft 新西向服务制定了一系列文档，说明其企业云服务如何通过将问题链接到针对其通过 Microsoft 云服务认证的标准来解决"云计算 ISPC"中设置的问题。</span><span class="sxs-lookup"><span data-stu-id="c2a98-115">To help agencies undertake their analysis and evaluation of Microsoft enterprise cloud services, Microsoft New Zealand has produced a series of documents showing how its enterprise cloud services address the questions set out in the “Cloud Computing ISPC” by linking them to the standards against which Microsoft cloud services are certified.</span></span> <span data-ttu-id="c2a98-116">这些认证是 Microsoft 如何向公共和私有企业客户保证其云服务设计、构建和运营以有效缓解隐私和安全风险并解决数据主查问题的中心。</span><span class="sxs-lookup"><span data-stu-id="c2a98-116">These certifications are central to how Microsoft assures both public and private sector customers that its cloud services are designed, built, and operated to effectively mitigate privacy and security risks and address data sovereignty concerns.</span></span>

<span data-ttu-id="c2a98-117">了解如何在我们的 Azure 安全性和合规性蓝图上加快 NZ CC 框架部署：下载 [Azure 对 NZ CC 框架的响应](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span><span class="sxs-lookup"><span data-stu-id="c2a98-117">Learn how to accelerate your NZ CC Framework deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the NZ CC Framework](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="c2a98-118">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="c2a98-118">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="c2a98-119">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="c2a98-119">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="c2a98-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c2a98-120">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="c2a98-121">Intune</span><span class="sxs-lookup"><span data-stu-id="c2a98-121">Intune</span></span>
- <span data-ttu-id="c2a98-122">Power BI 云服务，作为独立服务提供，后者随 Office 365 品牌计划或套件一并提供</span><span class="sxs-lookup"><span data-stu-id="c2a98-122">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- [<span data-ttu-id="c2a98-123">Office 365</span><span class="sxs-lookup"><span data-stu-id="c2a98-123">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="c2a98-124">Exchange Online、SharePoint Online 和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="c2a98-124">Exchange Online, SharePoint Online, and Microsoft Teams.</span></span> <span data-ttu-id="c2a98-125">Microsoft NZ 与 GCIO 团队协作，可开发用于集成 Exchange Online 和 SEEMail 的参考体系结构。</span><span class="sxs-lookup"><span data-stu-id="c2a98-125">Microsoft NZ has worked with the GCIO team to develop a reference architecture for integrating Exchange Online and SEEMail.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c2a98-126">常见问题</span><span class="sxs-lookup"><span data-stu-id="c2a98-126">Frequently asked questions</span></span>

<span data-ttu-id="c2a98-127">**框架适用于哪些人员？**</span><span class="sxs-lookup"><span data-stu-id="c2a98-127">**To whom does the framework apply?**</span></span>

<span data-ttu-id="c2a98-128">受 GCIO 要求的组织（公用和非公共服务部门、20 个分支健康板和七项 Crown 实体）在决定使用云服务时，必须遵守框架。</span><span class="sxs-lookup"><span data-stu-id="c2a98-128">Organizations that fall under the GCIO mandate — the public and non-public service departments, the 20 district health boards, and seven Crown entities — must adhere to the framework when they are deciding on the use of a cloud service.</span></span>

<span data-ttu-id="c2a98-129">**我的机构能否在 ICT 系统的认证过程中使用 Microsoft 对此框架的响应？**</span><span class="sxs-lookup"><span data-stu-id="c2a98-129">**Can my agency use Microsoft’s responses to this framework in the certification process of our ICT systems?**</span></span>

<span data-ttu-id="c2a98-130">如果机构要求在新西信息安全手动下对其 ICT 系统进行认证和 [资产](https://go.microsoft.com/fwlink/p/?linkid=2099496)，则在分析时可以使用这些响应。</span><span class="sxs-lookup"><span data-stu-id="c2a98-130">If your agency is required to undertake certification and accreditation of its ICT system under the [New Zealand Information Security Manual](https://go.microsoft.com/fwlink/p/?linkid=2099496), then you can use these responses as part of your analysis.</span></span>

## <a name="resources"></a><span data-ttu-id="c2a98-131">资源</span><span class="sxs-lookup"><span data-stu-id="c2a98-131">Resources</span></span>

- [<span data-ttu-id="c2a98-132">offshore hosted Office productivity services 的安全要求：Office 365 合规性指南</span><span class="sxs-lookup"><span data-stu-id="c2a98-132">Security requirements for offshore hosted Office productivity services: conformance guide for Office 365</span></span>](https://aka.ms/o365-gcio-conformance-guidance)
- [<span data-ttu-id="c2a98-133">Microsoft Azure 在新西年安全和隐私要求上下文中的合规性</span><span class="sxs-lookup"><span data-stu-id="c2a98-133">Microsoft Azure compliance in the context of New Zealand security and privacy requirements</span></span>](https://aka.ms/azurecompliancenewzealand)
- [<span data-ttu-id="c2a98-134">NZ 政府版 ICT 战略 2015</span><span class="sxs-lookup"><span data-stu-id="c2a98-134">NZ Government ICT Strategy 2015</span></span>](https://www.ict.govt.nz/strategy-and-action-plan/strategy/)
- [<span data-ttu-id="c2a98-135">云计算的 NZ 政府要求</span><span class="sxs-lookup"><span data-stu-id="c2a98-135">NZ Government requirements for cloud computing</span></span>](https://aka.ms/NZ-Cloud-Requirements)
- [<span data-ttu-id="c2a98-136">云计算：ISPC 活动的信息安全和 (隐私注意事) </span><span class="sxs-lookup"><span data-stu-id="c2a98-136">Cloud Computing: Information Security and Privacy Considerations (ISPC)</span></span>](https://www.digital.govt.nz/standards-and-guidance/technology-and-architecture/cloud-services/)
- [<span data-ttu-id="c2a98-137">Microsoft 在线服务条款</span><span class="sxs-lookup"><span data-stu-id="c2a98-137">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- <span data-ttu-id="c2a98-138">[Office 365：有关云服务采用情况的其他](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) Microsoft NZ (Microsoft NZ 指南，请查看邮件集成和参考体系结构) </span><span class="sxs-lookup"><span data-stu-id="c2a98-138">[Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) (additional Microsoft NZ guidance on cloud service adoption)</span></span>
- [<span data-ttu-id="c2a98-139">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="c2a98-139">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-responses-to-cloud-computing-ipsc"></a><span data-ttu-id="c2a98-140">Microsoft 对"云计算 IPSC"的响应</span><span class="sxs-lookup"><span data-stu-id="c2a98-140">Microsoft responses to 'Cloud Computing IPSC'</span></span>

- [<span data-ttu-id="c2a98-141">Azure</span><span class="sxs-lookup"><span data-stu-id="c2a98-141">Azure</span></span>](https://aka.ms/Azure-NZ-response)
- [<span data-ttu-id="c2a98-142">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c2a98-142">Dynamics 365</span></span>](https://aka.ms/d365-nz-response)
- [<span data-ttu-id="c2a98-143">Intune</span><span class="sxs-lookup"><span data-stu-id="c2a98-143">Intune</span></span>](https://aka.ms/Intune-NZ-response)
- [<span data-ttu-id="c2a98-144">Office 365</span><span class="sxs-lookup"><span data-stu-id="c2a98-144">Office 365</span></span>](https://aka.ms/O365-NZ-Response)
- [<span data-ttu-id="c2a98-145">Power BI</span><span class="sxs-lookup"><span data-stu-id="c2a98-145">Power BI</span></span>](https://download.microsoft.com/download/5/1/7/51726B9B-2E76-49C4-9D4F-A36BF025CB93/Response-to-GCIO-105-questions-Power-BI.pdf)
