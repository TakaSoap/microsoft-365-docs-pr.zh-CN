---
title: 符合 GDPR 的 Azure DevOps 数据主体请求
keywords: Visual Studio Team Services、VSTS、Azure DevOps 文档、隐私、GDPR
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: jitojo
ms.author: jominana
manager: douge
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 91ab1c1e23b2f4f9aab5c4327c29ac6cea52d080
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431773"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="638c9-103">符合 GDPR 的 Azure DevOps Services 数据主体请求</span><span class="sxs-lookup"><span data-stu-id="638c9-103">Azure DevOps Services Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="638c9-p101">根据欧盟[一般数据保护条例 (GDPR)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm)，用户（在条例中称为“*数据主体*”）有权管理由“*数据控制者*”收集的个人数据。数据控制者（或简称为“*控制者*”）是雇主或其他类型结构或组织。根据 GDPR，个人数据的定义非常广泛，包括与身份已识别或可识别的自然人相关的任何数据。根据 GDPR，数据主体有权对自己的个人数据执行以下操作：获取个人数据副本、请求更正个人数据、限制个人数据处理、删除个人数据或接收电子格式的个人数据（以便于转移给其他控制者）。数据主体为了对自己的个人数据执行操作而向控制者发出的正式请求，称为“*数据主体请求*”或“DSR”。</span><span class="sxs-lookup"><span data-stu-id="638c9-p101">The European Union [General Data Protection Regulation (GDPR)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people, known in the regulation as *data subjects*, to manage the personal data that's collected by a *data controller*. A data controller, or just *controller*, is an employer or other type of agency or organization. Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data. These rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request*, or DSR.</span></span>

<span data-ttu-id="638c9-110">有关 GDPR 的一般信息，请参阅[服务信任门户的 GDPR 部分](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)。</span><span class="sxs-lookup"><span data-stu-id="638c9-110">For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

<span data-ttu-id="638c9-111">本指南介绍如何使用 Microsoft 工具在经过身份验证的 Azure DevOps Services（以前称为 Visual Studio Team Services）的（已登录）会话过程中导出或删除所收集的个人数据。</span><span class="sxs-lookup"><span data-stu-id="638c9-111">This guide discusses how to use Microsoft tools to export or delete personal data collected during an authenticated (signed-in) session of Azure DevOps Services (formerly known as Visual Studio Team Services).</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="638c9-112">其他隐私信息</span><span class="sxs-lookup"><span data-stu-id="638c9-112">Additional privacy information</span></span>

<span data-ttu-id="638c9-113">[Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)、[在线服务条款 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx) 和 [Microsoft 对 GDPR 的承诺](/legal/gdpr)文章介绍我们的数据处理做法。</span><span class="sxs-lookup"><span data-stu-id="638c9-113">The [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement), [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx), and [Microsoft's GDPR Commitments](/legal/gdpr) articles describe our data processing practices.</span></span>

## <a name="personal-data-we-collect"></a><span data-ttu-id="638c9-114">我们收集的个人数据</span><span class="sxs-lookup"><span data-stu-id="638c9-114">Personal data we collect</span></span>

<span data-ttu-id="638c9-p102">Microsoft 收集来自用户的数据，以运行和改进 Azure DevOps Services。Azure DevOps Services 收集两类数据 — 客户数据和系统生成的日志。客户数据包括 Azure DevOps Services 运行服务所需的用户身份事务和交互式数据。系统生成的日志包括针对每个产品区域和功能所聚合的服务使用数据。</span><span class="sxs-lookup"><span data-stu-id="638c9-p102">Microsoft collects data from users to operate and improve Azure DevOps Services. Azure DevOps Services collects two categories of datacustomer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that Azure DevOps Services needs to operate the service. System-generated logs include service usage data that is aggregated for each product area and feature.</span></span>

## <a name="delete-azure-devops-data"></a><span data-ttu-id="638c9-119">删除 Azure DevOps 数据</span><span class="sxs-lookup"><span data-stu-id="638c9-119">Delete Azure DevOps data</span></span>

<span data-ttu-id="638c9-p103">删除关联的 Azure DevOps Services 客户数据并匿名化系统生成日志中发现的个人身份数据的第一步是关闭你的 Azure Active Directory (AAD) 身份帐户或 Microsoft 帐户 (MSA)。Azure DevOps Services 依赖于严格完整性、可追溯性和审核规则的记录系统。这些现有责任影响我们针对 GDPR 的删除和保留责任。关闭身份帐户不会修改、删除或更改 Azure DevOps 组织中与个人身份关联的项目和记录。我们确保当整个 Azure DevOps 组织被删除时，在该组织中发现的所有关联的个人身份数据和系统生成日志都将从我们的系统中删除（在必要的 Azure DevOps 组织 30 天软删除期后）。</span><span class="sxs-lookup"><span data-stu-id="638c9-p103">The first step to delete associated Azure DevOps Services customer data and to anonymize personally identifiable data found in system-generated logs is to close your Azure Active Directory (AAD) identity account or Microsoft Account (MSA). Azure DevOps Services is relied upon as a system of record with strict integrity, traceability, and audit rules. These existing obligations affect our delete and retention obligations for GDPR. Closing the identity account does not alter, remove, or change artifacts and records associated with the individual identity in the Azure DevOps organization. We have ensured that when an entire Azure DevOps organization is deleted, all associated personally identifiable data and system-generated logs found in that organization are removed from our system (after the requisite Azure DevOps organization 30-day soft-delete period).</span></span>

## <a name="export-azure-devops-data"></a><span data-ttu-id="638c9-125">导出 Azure DevOps 数据</span><span class="sxs-lookup"><span data-stu-id="638c9-125">Export Azure DevOps data</span></span>

<span data-ttu-id="638c9-126">控制者可以使用两种方法中的任意一种来导出从其数据主体收集的客户数据和系统生成的日志，具体取决于用于登录到 Azure DevOps 服务的身份提供程序（MSA 或 AAD）。</span><span class="sxs-lookup"><span data-stu-id="638c9-126">Controllers can export customer data and system-generated logs collected from their data subjects by one of two methods, depending upon the identity provider (MSA or AAD) used to sign in to the Azure DevOps service.</span></span>

- <span data-ttu-id="638c9-127">使用受 Azure 租户支持的帐户（例如，AAD 帐户或与 Azure 订阅关联的 MSA 帐户）进行身份验证的用户可以按照[针对 GDPR 的 Azure 数据主体请求](../compliance/gdpr-dsr-azure.md)中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="638c9-127">Users that authenticate using an account that is backed by an Azure tenant, for example, AAD account or MSA account associated with an Azure subscription, can follow the instructions in [Azure Data Subject Requests for the GDPR](../compliance/gdpr-dsr-azure.md).</span></span>

- <span data-ttu-id="638c9-p104">使用 MSA 身份进行身份验证的用户可以使用此[隐私请求网站](https://www.microsoft.com/concern/privacyrequest-msa)跨多个 Microsoft 服务查看绑定到其 MSA 身份的活动数据。在此应用场景中，用户是他们自己的个人数据的控制者。</span><span class="sxs-lookup"><span data-stu-id="638c9-p104">Users that authenticate using an MSA identity can use this [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) to view activity data tied to their MSA identity across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

## <a name="export-or-delete-issues"></a><span data-ttu-id="638c9-130">导出或删除问题</span><span class="sxs-lookup"><span data-stu-id="638c9-130">Export or delete issues</span></span>

<span data-ttu-id="638c9-131">对于 AAD 身份，如果在从 Azure 门户导出或删除数据时遇到问题，请转到 Azure 门户“帮助 + 支持”\*\*\*\* 边栏选项卡，并在“订阅管理”\*\*\*\* > “其他安全与合规请求”\*\*\*\* > “隐私边栏选项卡和 GDPR 请求”\*\*\*\* 下提交新票证。</span><span class="sxs-lookup"><span data-stu-id="638c9-131">For AAD identities, if you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management** > **Other Security and Compliance Request** > **Privacy Blade and GDPR Requests**.</span></span>

<span data-ttu-id="638c9-132">对于 MSA 身份，如果在从隐私请求网站导出数据时遇到问题，请登录到[隐私请求网站](https://www.microsoft.com/concern/privacyrequest-msa)，并通过请求 Web 窗体提交请求，以获取来自 Microsoft 隐私团队的帮助。</span><span class="sxs-lookup"><span data-stu-id="638c9-132">For MSA identities, if you run into issues while exporting data from the Privacy Request site, log on to the [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) and submit a request for help from the Microsoft Privacy team via the request webform.</span></span>

## <a name="learn-more"></a><span data-ttu-id="638c9-133">了解更多</span><span class="sxs-lookup"><span data-stu-id="638c9-133">Learn more</span></span>

<span data-ttu-id="638c9-p105">Microsoft 致力于确保你的 Azure DevOps Services 数据的安全性和隐私性，并确保其不会发生异常。请访问 [Azure DevOps Services 数据保护概述](/vsts/articles/team-services-security-whitepaper?view=vsts)白皮书，以详细了解我们是如何保护你的 Azure DevOps Services 数据的。</span><span class="sxs-lookup"><span data-stu-id="638c9-p105">Microsoft is committed to ensuring that your Azure DevOps Services data remains secure and private, without exception. Visit the [Azure DevOps Services data protection overview](/vsts/articles/team-services-security-whitepaper?view=vsts) whitepaper to learn more about how we protect your Azure DevOps Services data.</span></span>

## <a name="see-also"></a><span data-ttu-id="638c9-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="638c9-136">See also</span></span>

- [<span data-ttu-id="638c9-137">Microsoft 对我们公开发布的企业软件产品的客户的 GDPR 义务</span><span class="sxs-lookup"><span data-stu-id="638c9-137">Microsoft's GDPR commitments to customers of our generally available enterprise software products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="638c9-138">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="638c9-138">Microsoft Trust center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [<span data-ttu-id="638c9-139">服务信任门户</span><span class="sxs-lookup"><span data-stu-id="638c9-139">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="638c9-140">Microsoft 隐私仪表板</span><span class="sxs-lookup"><span data-stu-id="638c9-140">Microsoft privacy dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="638c9-141">Microsoft 隐私响应中心</span><span class="sxs-lookup"><span data-stu-id="638c9-141">Microsoft privacy response center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="638c9-142">针对 GDPR 的 Azure 数据主体请求</span><span class="sxs-lookup"><span data-stu-id="638c9-142">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)