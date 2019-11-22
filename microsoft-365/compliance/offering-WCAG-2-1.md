---
title: Web 内容辅助功能准则 2.1
description: Microsoft 发布了 WCAG 2.1 AA 报告，其中反映了整个产品/服务或者产品中可单独安装的部分。
keywords: Microsoft 365, 合规性, 产品
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 9239ac26cfdb0e81c979faacf253191577a22b9a
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "39195125"
---
# <a name="compliance-offering-web-content-accessibility-guidelines-21"></a><span data-ttu-id="dcf84-104">合规性产品：Web 内容辅助功能准则 2.1</span><span class="sxs-lookup"><span data-stu-id="dcf84-104">Compliance offering: Web Content Accessibility Guidelines 2.1</span></span>

## <a name="about-wcag-21"></a><span data-ttu-id="dcf84-105">关于 WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="dcf84-105">WCAG 2.1</span></span>

<span data-ttu-id="dcf84-106">WCAG 2.1 提供了一个 Web 内功开发框架，除了帮助使用图形化能力有限的设备的用户，还让残障人士更易访问这些内容。</span><span class="sxs-lookup"><span data-stu-id="dcf84-106">WCAG 2.1 provides a framework for developing web content that improves accessibility for people with disabilities, in addition to users of devices with limited graphical abilities.</span></span> <span data-ttu-id="dcf84-107">WCAG 2.0 是万维网联盟 (W3C)（一家致力于制定 Web 标准的国际组织）于 2008 年发布的，在 2018 年 6 月更新为 WCAG 2.1 版。</span><span class="sxs-lookup"><span data-stu-id="dcf84-107">WCAG 2.0 was published in 2008 by the World Wide Web Consortium (W3C), an international organization dedicated to creating web standards, and updated to WCAG 2.1 in June 2018.</span></span> <span data-ttu-id="dcf84-108">2012 年，国际标准化组织 (ISO) 也以 ISO/IEC 40500:2012 的形式发布了 WCAG 2.0。</span><span class="sxs-lookup"><span data-stu-id="dcf84-108">In 2012, WCAG 2.0 was also published by the International Organization for Standardization (ISO) as ISO/IEC 40500:2012.</span></span>  
  
<span data-ttu-id="dcf84-109">符合 WCAG 2.1 的内容也符合 WCAG 2.0。</span><span class="sxs-lookup"><span data-stu-id="dcf84-109">Content that conforms to WCAG 2.1 also conforms to WCAG 2.0.</span></span> <span data-ttu-id="dcf84-110">对于需遵从 WCAG 2.0 的策略，WCAG 2.1 可提供替代合规方法。</span><span class="sxs-lookup"><span data-stu-id="dcf84-110">For policies requiring conformance to WCAG 2.0, WCAG 2.1 can provide an alternate means of conformance.</span></span>  
  
<span data-ttu-id="dcf84-111">每个准则的遵从要求都按 A、AA 和 AAA 这三个级别进行衡量。</span><span class="sxs-lookup"><span data-stu-id="dcf84-111">Conformance requirements for each guideline are measured in three levels: A, AA, and AAA.</span></span> <span data-ttu-id="dcf84-112">Microsoft 是世界各地国家/地区和政府的主要软件及云服务提供商，因此它承诺遵守各项相关[国际标准和合规控制措施](https://go.microsoft.com/fwlink/p/?linkid=2052226)。</span><span class="sxs-lookup"><span data-stu-id="dcf84-112">Because Microsoft is a major software and cloud-services provider to states and governments around the world, it is committed to complying with all relevant [international standards and compliance controls](https://go.microsoft.com/fwlink/p/?linkid=2052226).</span></span> <span data-ttu-id="dcf84-113">通过坚持这些广泛的无障碍标准，Microsoft 保护政府内外各方客户都可使用 Microsoft 服务和产品。</span><span class="sxs-lookup"><span data-stu-id="dcf84-113">By adhering to these wide-ranging accessibility standards, Microsoft ensures that all customers — both inside and outside of government — can use Microsoft services and products.</span></span>  

## <a name="microsoft-and-wcag-21"></a><span data-ttu-id="dcf84-114">Microsoft 与 WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="dcf84-114">Microsoft and WCAG 2.1</span></span>

<span data-ttu-id="dcf84-115">Microsoft 遵守 WCAG 2.1 (ISO/IEC 40500) 标准表明了它承诺让所有客户都更易访问技术和数据。</span><span class="sxs-lookup"><span data-stu-id="dcf84-115">Microsoft’s adherence to the WCAG 2.1 (ISO/IEC 40500) standard points to its commitment to making technology and data accessible for all customers.</span></span> <span data-ttu-id="dcf84-116">WCAG 2.1 (ISO/IEC 40500) 是一项国际无障碍要求，对欧洲的 EN 301 549 和美国的第 508 条规定进行了补充。</span><span class="sxs-lookup"><span data-stu-id="dcf84-116">WCAG 2.1 (ISO/IEC 40500) is the international accessibility requirement that complements EN 301 549 (Europe) and Section 508 (U.S.).</span></span>  
  
<span data-ttu-id="dcf84-117">Microsoft 发布了 WCAG 2.1 报告，其中反映的是完整的产品或服务。</span><span class="sxs-lookup"><span data-stu-id="dcf84-117">Microsoft publishes WCAG 2.1 reports that reflect the complete product or service.</span></span> <span data-ttu-id="dcf84-118">它通常不对单个功能或组件创建报告。</span><span class="sxs-lookup"><span data-stu-id="dcf84-118">It generally does not create reports for individual features or components.</span></span> <span data-ttu-id="dcf84-119">有时，Microsoft 可能会对现有产品发布新的组件，或者发布现有组件的新版本 - 用户可选择单独安装它们，此时 Microsoft 可能也会对该组件发布 WCAG 2.1 报告。</span><span class="sxs-lookup"><span data-stu-id="dcf84-119">Sometimes, Microsoft might release a new component for an existing product, or a new version of an existing component, which users can choose to install separately, and Microsoft might also publish a WCAG 2.1 report for that component.</span></span>  
  
[<span data-ttu-id="dcf84-120">下载 WCAG 2.1 (ISO/IEC 40500) 辅助功能标准</span><span class="sxs-lookup"><span data-stu-id="dcf84-120">Download the WCAG 2.1 (ISO/IEC 40500) accessibility standards</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2052226)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="dcf84-121">Microsoft 范围内的云服务</span><span class="sxs-lookup"><span data-stu-id="dcf84-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="dcf84-122">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="dcf84-122">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="dcf84-123">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="dcf84-123">Azure DevOps Services</span></span>
- <span data-ttu-id="dcf84-124">Dynamics 365 和 Dynamics 365 美国政府</span><span class="sxs-lookup"><span data-stu-id="dcf84-124">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="dcf84-125">Intune</span><span class="sxs-lookup"><span data-stu-id="dcf84-125">Intune</span></span>
- <span data-ttu-id="dcf84-126">Office 365 和 Office 365 US 政府计划</span><span class="sxs-lookup"><span data-stu-id="dcf84-126">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span>
- <span data-ttu-id="dcf84-127">Office 365 美国政府防御版</span><span class="sxs-lookup"><span data-stu-id="dcf84-127">Office 365 US Government Defense</span></span>
- <span data-ttu-id="dcf84-128">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="dcf84-128">Windows Server 2016</span></span>

## <a name="microsoft-accessibility-conformance-reports"></a><span data-ttu-id="dcf84-129">Microsoft 辅助功能遵从报告</span><span class="sxs-lookup"><span data-stu-id="dcf84-129">Microsoft accessibility conformance reports</span></span>

<span data-ttu-id="dcf84-130">查找我们各项产品和服务的 WCAG 报告。</span><span class="sxs-lookup"><span data-stu-id="dcf84-130">Find WCAG reports for all our products and services.</span></span>

[<span data-ttu-id="dcf84-131">**了解详细信息**</span><span class="sxs-lookup"><span data-stu-id="dcf84-131">**Learn more**</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050974)

## <a name="resources"></a><span data-ttu-id="dcf84-132">资源</span><span class="sxs-lookup"><span data-stu-id="dcf84-132">Resources</span></span>

<span data-ttu-id="dcf84-133">[Microsoft 辅助功能网站 - 学习如何使用辅助功能，了解 Microsoft 通过创新来帮助人实现更多目标的方式。</span><span class="sxs-lookup"><span data-stu-id="dcf84-133">[Microsoft accessibility site — Get information on using accessibility features and explore the ways Microsoft innovates to help everyone achieve more.</span></span>

<span data-ttu-id="dcf84-134">[Office 365 辅助功能中心](https://go.microsoft.com/fwlink/p/?linkid=2051801)</span><span class="sxs-lookup"><span data-stu-id="dcf84-134">[](https://go.microsoft.com/fwlink/p/?linkid=2051801)Office 365 Trust Center</span></span>
    - <span data-ttu-id="dcf84-135">Office 365 面向残障人士的资源。</span><span class="sxs-lookup"><span data-stu-id="dcf84-135">Office 365 resources for people with disabilities.</span></span>

[<span data-ttu-id="dcf84-136">企业级辅助功能咨询台</span><span class="sxs-lookup"><span data-stu-id="dcf84-136">Disability Answer Desk</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050890)
    - <span data-ttu-id="dcf84-137">针对就我们的产品和服务或合规性抱有可访问性方面的问题的企业客户提供专属支持。</span><span class="sxs-lookup"><span data-stu-id="dcf84-137">Dedicated support for enterprise customers with accessibility questions about our products and services or compliance.</span></span>

[<span data-ttu-id="dcf84-138">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="dcf84-138">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="dcf84-139">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="dcf84-139">Download the offering backgrounder</span></span>

<span data-ttu-id="dcf84-140">是否需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="dcf84-140">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="dcf84-141">请下载 [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf)。</span><span class="sxs-lookup"><span data-stu-id="dcf84-141">Download the [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span></span>
