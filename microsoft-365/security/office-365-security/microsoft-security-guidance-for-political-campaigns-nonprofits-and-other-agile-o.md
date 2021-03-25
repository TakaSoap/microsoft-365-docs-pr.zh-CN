---
title: Microsoft 安全指南 - 政治宣传活动与非盈利组织
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 摘要：针对发展迅速且配置文件威胁不断增加的组织的计划和实现指南。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac278103caf5d4d70b303b50b73db1b4b3571e6b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203228"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="ff2d7-103">Microsoft 针对政治宣传活动、非营利组织和其他敏捷型组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="ff2d7-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff2d7-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="ff2d7-104">**Applies to**</span></span>
- [<span data-ttu-id="ff2d7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ff2d7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ff2d7-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="ff2d7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="ff2d7-107">**摘要：** 针对发展迅速且配置文件威胁不断增加的组织的计划和实现指南。</span><span class="sxs-lookup"><span data-stu-id="ff2d7-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="ff2d7-p101">如果你所在组织是敏捷型组织，而由你领导一个小的 IT 团队，且威胁配置文件高于平均值，那么本指南对你特别适用。 此解决方案演示如何从头开始快速构建包含安全控件的基本云服务环境。 本指南提供有关保护来自移动设备的数据、标识、电子邮件和访问的说明性安全建议。</span><span class="sxs-lookup"><span data-stu-id="ff2d7-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="ff2d7-111">安全解决方案指南</span><span class="sxs-lookup"><span data-stu-id="ff2d7-111">Security solution guidance</span></span>

<span data-ttu-id="ff2d7-p102">本指南介绍了如何实现安全的云环境。 该解决方案指南可供任何组织使用。 并且对带有 BYOD 访问权限和来宾帐户的敏捷型组织提供了更多帮助。 可使用本指南作为设计自己环境的起点。 我们欢迎你在 [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com) 上提供反馈。</span><span class="sxs-lookup"><span data-stu-id="ff2d7-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="ff2d7-117">Item</span><span class="sxs-lookup"><span data-stu-id="ff2d7-117">Item</span></span>|<span data-ttu-id="ff2d7-118">说明</span><span class="sxs-lookup"><span data-stu-id="ff2d7-118">Description</span></span>|
|---|---|
|<span data-ttu-id="ff2d7-119">**Microsoft 针对政治宣传活动的安全指南**</span><span class="sxs-lookup"><span data-stu-id="ff2d7-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="ff2d7-120">[![迷你海报集的缩略图。](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="ff2d7-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="ff2d7-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="ff2d7-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="ff2d7-p103">本指南以政治宣传活动的组织为例，可将本指南用作任何环境的起点。</span><span class="sxs-lookup"><span data-stu-id="ff2d7-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="ff2d7-124">**Microsoft 针对非营利组织的安全指南**</span><span class="sxs-lookup"><span data-stu-id="ff2d7-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="ff2d7-125">[![可下载文件的缩略图](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="ff2d7-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="ff2d7-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="ff2d7-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="ff2d7-p104">本指南经过略微修订，适用于非盈利组织。例如，引入了 Office 365 非盈利组织版计划。该技术指南与政治宣传活动解决方案指南相同。</span><span class="sxs-lookup"><span data-stu-id="ff2d7-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="ff2d7-130">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="ff2d7-130">Test Lab Guides</span></span>

<span data-ttu-id="ff2d7-131">要创建此解决方案的开发/测试环境，请使用以下测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="ff2d7-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="ff2d7-132">为政治宣传活动开发/测试环境配置组和用户</span><span class="sxs-lookup"><span data-stu-id="ff2d7-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="ff2d7-133">为 Office 365 和 EMS 创建试用订阅，然后为具有代表性的政治宣传活动创建组和用户。</span><span class="sxs-lookup"><span data-stu-id="ff2d7-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="ff2d7-134">在政治宣传活动开发/测试环境中创建团队网站</span><span class="sxs-lookup"><span data-stu-id="ff2d7-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="ff2d7-135">创建四个具有内部、专用、敏感和高度机密级别的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="ff2d7-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="ff2d7-136">有关演示或概念证明的其他安全功能，请参阅 [Office 365 测试实验室指南](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)。</span><span class="sxs-lookup"><span data-stu-id="ff2d7-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff2d7-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff2d7-137">See Also</span></span>

[<span data-ttu-id="ff2d7-138">Microsoft 云 IT 体系结构资源</span><span class="sxs-lookup"><span data-stu-id="ff2d7-138">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)
