---
title: 云中的多地理位置Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: 了解Teams多地理位置Microsoft 365工作原理。
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362639"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="9eb49-103">多地理位置功能Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9eb49-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="9eb49-104">多地理位置功能Teams允许Teams聊天数据以静止状态存储在指定地理位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="9eb49-105">聊天数据由聊天消息（包括私人消息、频道消息和聊天中使用的图像）组成。</span><span class="sxs-lookup"><span data-stu-id="9eb49-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="9eb49-106">Teams用户和组 (PDL) 首选数据位置，以确定存储数据的位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="9eb49-107">如果未设置 PDL 或 PDL 无效，则数据存储在租户的中心位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="9eb49-108">用户聊天</span><span class="sxs-lookup"><span data-stu-id="9eb49-108">User chat</span></span>

<span data-ttu-id="9eb49-109">用户聊天包括一对一、一对多和私人会议消息。</span><span class="sxs-lookup"><span data-stu-id="9eb49-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="9eb49-110">当创建一个新用户时，Teams读取用户的 PDL，并存储其所有聊天数据。</span><span class="sxs-lookup"><span data-stu-id="9eb49-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="9eb49-111">对于现有用户，如果管理员添加或修改用户的 PDL，该用户的聊天数据将添加到迁移队列中以移动到指定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="9eb49-112">一对一或一对多聊天的存储位置基于创建聊天的人的 PDL。</span><span class="sxs-lookup"><span data-stu-id="9eb49-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="9eb49-113">如果该用户的 PDL 发生更改，聊天将迁移到新的地理位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="9eb49-114">会议聊天的存储位置基于会议组织者的 PDL。</span><span class="sxs-lookup"><span data-stu-id="9eb49-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="9eb49-115">若要查找用户当前存储数据Teams，请连接到[Teams PowerShell 并](/powershell/module/teams/connect-microsoftteams)运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9eb49-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="9eb49-116">频道消息</span><span class="sxs-lookup"><span data-stu-id="9eb49-116">Channel messages</span></span>

<span data-ttu-id="9eb49-117">每个Microsoft 365组都有一 (PDL) 首选数据位置，该位置表示要存储数据的地理位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="9eb49-118">Teams使用与每个团队关联的组的 PDL 来确定在何处存储该团队的频道消息数据。</span><span class="sxs-lookup"><span data-stu-id="9eb49-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="9eb49-119">这包括频道会议内发生的聊天。</span><span class="sxs-lookup"><span data-stu-id="9eb49-119">This includes chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="9eb49-120">当用户创建新团队时，该用户的 PDL 将确定分配给该组Microsoft 365 PDL。</span><span class="sxs-lookup"><span data-stu-id="9eb49-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="9eb49-121">组 PDL 确定团队数据的存储位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="9eb49-122">如果该用户的 PDL 稍后发生更改，则组的 PDL 不会更改。</span><span class="sxs-lookup"><span data-stu-id="9eb49-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="9eb49-123">对于现有团队，如果管理员添加或修改支持团队的 Microsoft 365 组的 PDL，该团队的频道消息数据将添加到迁移队列中，以移动到指定地理位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="9eb49-124">更改组组的 PDL Microsoft 365将Teams数据排入队列，以迁移到所选位置。</span><span class="sxs-lookup"><span data-stu-id="9eb49-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="9eb49-125">但是，这不会迁移SharePoint组关联的网站或文件。</span><span class="sxs-lookup"><span data-stu-id="9eb49-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="9eb49-126">必须按照将网站移动到其他地理位置中SharePoint[移动网站](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)。</span><span class="sxs-lookup"><span data-stu-id="9eb49-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="9eb49-127">请务必执行这两个步骤，以避免Teams组的数据SharePoint访问数据。</span><span class="sxs-lookup"><span data-stu-id="9eb49-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="9eb49-128">若要查找团队数据的当前位置，请连接到 Teams [PowerShell](/powershell/module/teams/connect-microsoftteams)并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9eb49-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="9eb49-129">用户体验</span><span class="sxs-lookup"><span data-stu-id="9eb49-129">User Experience</span></span>

<span data-ttu-id="9eb49-130">Teams多地理位置对最终用户是无缝的。</span><span class="sxs-lookup"><span data-stu-id="9eb49-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="9eb49-131">更改用户或组的 PDL 后，相应的数据将排入迁移队列，并且迁移将自动进行，不会影响用户或 Teams 客户端，即使它们在迁移发生时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="9eb49-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="9eb49-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9eb49-132">See also</span></span>

[<span data-ttu-id="9eb49-133">Microsoft 365 多地理位置租户配置</span><span class="sxs-lookup"><span data-stu-id="9eb49-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="9eb49-134">管理多地理位置环境</span><span class="sxs-lookup"><span data-stu-id="9eb49-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="9eb49-135">在多地理位置环境中管理 Exchange Online 邮箱</span><span class="sxs-lookup"><span data-stu-id="9eb49-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
