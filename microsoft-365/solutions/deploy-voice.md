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
description: 了解如何为组织选择和部署正确的 Teams 语音解决方案。
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918378"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="05f52-103">计划和部署 Teams 语音解决方案</span><span class="sxs-lookup"><span data-stu-id="05f52-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="05f52-104">Teams 语音解决方案使贵组织内部和外部人员能够拨打电话。</span><span class="sxs-lookup"><span data-stu-id="05f52-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="05f52-105">完整的语音解决方案包括 Teams、Microsoft Phone System 以及用于连接到公用电话交换网和 PSTN (选项) 。</span><span class="sxs-lookup"><span data-stu-id="05f52-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Teams 语音解决方案概述](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="05f52-107">电话系统为组织 (完整的专用交换机) PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="05f52-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="05f52-108">组织中用户之间的呼叫（无论其地理位置如何）在电话系统内部处理，因此可消除这些内部呼叫的长途成本。</span><span class="sxs-lookup"><span data-stu-id="05f52-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="05f52-109">通过将电话系统连接到公用电话交换网 (PSTN) ，Teams 用户还可以在组织外部拨打电话。</span><span class="sxs-lookup"><span data-stu-id="05f52-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="05f52-110">此解决方案指南可帮助你：</span><span class="sxs-lookup"><span data-stu-id="05f52-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="05f52-111">选择适合贵组织的语音解决方案</span><span class="sxs-lookup"><span data-stu-id="05f52-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="05f52-112">部署所选的语音解决方案</span><span class="sxs-lookup"><span data-stu-id="05f52-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="05f52-113">按照以下步骤选择、计划和配置语音解决方案：</span><span class="sxs-lookup"><span data-stu-id="05f52-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![选择你的语音解决方案](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="05f52-115">选择你的语音解决方案</span><span class="sxs-lookup"><span data-stu-id="05f52-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="05f52-116">设置电话系统</span><span class="sxs-lookup"><span data-stu-id="05f52-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="05f52-117">通过选择下列选项之一或组合设置 PSTN 连接：</span><span class="sxs-lookup"><span data-stu-id="05f52-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="05f52-118">[通话套餐](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft 的全云解决方案，Microsoft 作为 PSTN 运营商</span><span class="sxs-lookup"><span data-stu-id="05f52-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="05f52-119">[直接路由](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - 使用直接路由将你自己的 PSTN 运营商连接到 Teams</span><span class="sxs-lookup"><span data-stu-id="05f52-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="05f52-120">此外，您可能希望了解 [Contoso](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)案例研究中大型的跨国公司如何迁移到 Teams 语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="05f52-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="05f52-121">有关所需许可证的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="05f52-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="05f52-122">Teams 附加许可证</span><span class="sxs-lookup"><span data-stu-id="05f52-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="05f52-123">直接路由许可要求</span><span class="sxs-lookup"><span data-stu-id="05f52-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)