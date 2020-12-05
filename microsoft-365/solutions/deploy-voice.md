---
title: 在 Microsoft 365 中部署语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 了解如何为你的组织选择和部署正确的团队语音解决方案。
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580886"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="71d88-103">规划和部署团队语音解决方案</span><span class="sxs-lookup"><span data-stu-id="71d88-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="71d88-104">使用团队语音解决方案，组织中的人员可以在组织内部和外部进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="71d88-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="71d88-105">完整的语音解决方案由团队、Microsoft 电话系统和用于连接到公用电话交换网的电话网络 (PSTN) 的选项组成。</span><span class="sxs-lookup"><span data-stu-id="71d88-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![团队语音解决方案概述](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="71d88-107">电话系统为您的组织提供完整的专用分支 Exchange (PBX) 功能。</span><span class="sxs-lookup"><span data-stu-id="71d88-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="71d88-108">您的组织中的用户之间的呼叫（无论其地理位置如何）在电话系统内部进行内部处理，从而消除了这些内部呼叫的长途开销。</span><span class="sxs-lookup"><span data-stu-id="71d88-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="71d88-109">通过将电话系统连接到公用电话交换网 (PSTN) ，团队用户也可以在组织外部进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="71d88-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="71d88-110">本解决方案指南可帮助您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="71d88-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="71d88-111">选择适合您的组织的语音解决方案</span><span class="sxs-lookup"><span data-stu-id="71d88-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="71d88-112">部署所选的语音解决方案</span><span class="sxs-lookup"><span data-stu-id="71d88-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="71d88-113">按照以下步骤选择、规划和配置语音解决方案：</span><span class="sxs-lookup"><span data-stu-id="71d88-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![选择语音解决方案](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="71d88-115">选择语音解决方案</span><span class="sxs-lookup"><span data-stu-id="71d88-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="71d88-116">设置电话系统</span><span class="sxs-lookup"><span data-stu-id="71d88-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="71d88-117">通过选择以下一种或多种方式来设置 PSTN 连接：</span><span class="sxs-lookup"><span data-stu-id="71d88-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="71d88-118">[通话套餐](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -microsoft 的云即用 MICROSOFT 作为 PSTN 运营商的云解决方案</span><span class="sxs-lookup"><span data-stu-id="71d88-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="71d88-119">[直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -使用直接路由将你自己的 PSTN 运营商连接到团队</span><span class="sxs-lookup"><span data-stu-id="71d88-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="71d88-120">此外，您可能希望了解在 [Contoso 个案研究](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)中如何将大型的多国公司迁移到团队语音解决方案中。</span><span class="sxs-lookup"><span data-stu-id="71d88-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="71d88-121">有关所需许可证的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="71d88-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="71d88-122">团队附加许可证</span><span class="sxs-lookup"><span data-stu-id="71d88-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="71d88-123">直接路由许可要求</span><span class="sxs-lookup"><span data-stu-id="71d88-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
