---
title: 部署 Microsoft 365 企业版的 Microsoft Teams
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 逐步了解相关信息，然后在整个组织中内推广 Microsoft Teams。
ms.openlocfilehash: d34673a412539dfc73296f0139fa2eb555c17099
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636695"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="6b386-103">部署 Microsoft 365 企业版的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b386-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6b386-104">*此工作负载包含在适用于 Microsoft 365 企业版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="6b386-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6b386-p101">Microsoft Teams 集聊天、会议、文档共享和按线索组织对话等多项功能于一体，可以轻松地跨组创建和共享内容。Teams 不仅是你针对 Microsoft 365 企业版进行团队合作和协作的方式，还是构建 Microsoft 365 的团队合作价值的关键要素。</span><span class="sxs-lookup"><span data-stu-id="6b386-p101">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups. Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365.</span></span> 

<span data-ttu-id="6b386-107">如果你是 Teams 的全新用户，请参阅[欢迎使用 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview)。</span><span class="sxs-lookup"><span data-stu-id="6b386-107">If you're brand new to Teams, see [Welcome to Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> 


## <a name="roll-out-teams-to-your-organization"></a><span data-ttu-id="6b386-108">在组织内推广 Teams</span><span class="sxs-lookup"><span data-stu-id="6b386-108">Roll out Teams to your organization</span></span>

<span data-ttu-id="6b386-109">开始之前：</span><span class="sxs-lookup"><span data-stu-id="6b386-109">Before you begin:</span></span>

- <span data-ttu-id="6b386-110">请确保你配置了右侧的[基础结构](deploy-foundation-infrastructure.md)阶段，以便团队具有所需的用户帐户和安全功能。</span><span class="sxs-lookup"><span data-stu-id="6b386-110">Make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the user accounts and security capabilities you need.</span></span> <span data-ttu-id="6b386-111">对于登录并使用带有保留和敏感度标签的安全电子邮件及文件，“标识”和“信息保护”阶段最为重要。</span><span class="sxs-lookup"><span data-stu-id="6b386-111">The Identity and Information Protection phases are the most important for signing on and using securing email and files with retention and sensitivity labels.</span></span>
- <span data-ttu-id="6b386-112">通过[本文](https://docs.microsoft.com/microsoftteams/security-compliance-overview)详细了解 Teams 中的安全性和合规性。</span><span class="sxs-lookup"><span data-stu-id="6b386-112">Learn about security and compliance in Teams with [this article](https://docs.microsoft.com/microsoftteams/security-compliance-overview).</span></span>
- <span data-ttu-id="6b386-113">通过[本文](https://docs.microsoft.com/microsoftteams/office-365-licensing)详细了解适用于 Teams 的许可。</span><span class="sxs-lookup"><span data-stu-id="6b386-113">Learn about licensing for Teams with [this article](https://docs.microsoft.com/microsoftteams/office-365-licensing).</span></span>

<span data-ttu-id="6b386-114">若要在组织内推广 Teams，请阅读[如何推广 Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams)。</span><span class="sxs-lookup"><span data-stu-id="6b386-114">To roll out Teams in your organization, read [How to roll out Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span></span>

<span data-ttu-id="6b386-115">对于第一组 Teams 功能，请参阅 [Microsoft Teams 中的聊天、团队、频道和应用](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="6b386-115">For your first set of Teams capabilities, see [Chat, teams, channels, and apps in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span></span>

<span data-ttu-id="6b386-116">有关更为高级的 Teams 功能，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6b386-116">For more advanced Teams capabilities, see:</span></span>

- [<span data-ttu-id="6b386-117">会话和会议</span><span class="sxs-lookup"><span data-stu-id="6b386-117">Meetings and Conferencing</span></span>](https://docs.microsoft.com/microsoftteams/deploy-meetings-microsoft-teams-landing-page)
- <span data-ttu-id="6b386-118">[云语音](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)（需要 Microsoft 365 E5）</span><span class="sxs-lookup"><span data-stu-id="6b386-118">[Cloud voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (requires Microsoft 365 E5)</span></span>

<span data-ttu-id="6b386-119">若要监视组织对 Teams 的使用情况，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6b386-119">To monitor your organization's usage of Teams, see:</span></span>

- [<span data-ttu-id="6b386-120">Teams 中的跨团队和每团队分析</span><span class="sxs-lookup"><span data-stu-id="6b386-120">Cross-team and per-team analytics in Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/cross-team-per-team-analytics)
- [<span data-ttu-id="6b386-121">分析和报告</span><span class="sxs-lookup"><span data-stu-id="6b386-121">Analytics and reporting</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)


## <a name="upgrade-to-teams"></a><span data-ttu-id="6b386-122">升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="6b386-122">Upgrade to Teams</span></span>

<span data-ttu-id="6b386-123">如果尚未进行升级，你很快就可以从 Skype for Business 升级到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6b386-123">If it hasn’t happened already, you will soon upgrade from Skype for Business to Microsoft Teams.</span></span> <span data-ttu-id="6b386-124">无论你是刚开始使用 Teams，已经将 Teams 与 Skype for Business 一起使用，还是准备进行升级，我们都希望确保你拥有成功开启 Teams 之旅所需的一切。</span><span class="sxs-lookup"><span data-stu-id="6b386-124">Whether you’re just getting started with Teams, already using Teams alongside Skype for Business, or ready to upgrade, we want to ensure you have everything you need to navigate a successful journey to Teams.</span></span>

<span data-ttu-id="6b386-125">无论是从 Skype for Business Online 升级到 Teams，还是从 Skype for Business 本地环境升级到 Teams，升级框架都将根据你的业务方案指导你完成整个过程。</span><span class="sxs-lookup"><span data-stu-id="6b386-125">Whether you are upgrading from Skype for Business Online to Teams or from a Skype for Business on-premises environment to Teams, the upgrade framework will guide you through the process based on your business scenario.</span></span>
 
<span data-ttu-id="6b386-126">有关详细信息，请参阅[开始 Microsoft Teams 升级](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="6b386-126">See the [Getting started with your Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) for more information.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="6b386-127">Microsoft 如何对 Microsoft 365 企业版执行操作</span><span class="sxs-lookup"><span data-stu-id="6b386-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6b386-128">若要深入了解 Microsoft，了解如何进行部署以及如何使用 Teams 进行协作，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6b386-128">To peek inside Microsoft and learn how we deployed and are using Teams for collaboration, see:</span></span>

- [<span data-ttu-id="6b386-129">Microsoft Teams 采用策略让员工为新的工作文化做好准备</span><span class="sxs-lookup"><span data-stu-id="6b386-129">Microsoft Teams adoption strategy prepares employees for a new culture of work</span></span>](https://www.microsoft.com/itshowcase/microsoft-teams-adoption-strategy-prepares-employees-for-a-new-culture-of-work)
- [<span data-ttu-id="6b386-130">通过 Microsoft Teams 会议室在全球范围内实现可扩展的新式会议体验</span><span class="sxs-lookup"><span data-stu-id="6b386-130">With Microsoft Teams Rooms, comes a globally scalable modern meeting experience</span></span>](https://www.microsoft.com/itshowcase/with-microsoft-teams-rooms-comes-a-globally-scalable-modern-meeting-experience)

## <a name="next-steps"></a><span data-ttu-id="6b386-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6b386-131">Next steps</span></span>

- [<span data-ttu-id="6b386-132">为你的组织管理 Microsoft Teams 功能</span><span class="sxs-lookup"><span data-stu-id="6b386-132">Manage Microsoft Teams features for your organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="6b386-133">Microsoft Teams 管理培训</span><span class="sxs-lookup"><span data-stu-id="6b386-133">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)

