---
title: 组服务交互
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 组服务交互
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613222"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="9168c-103">组服务交互</span><span class="sxs-lookup"><span data-stu-id="9168c-103">Groups services interactions</span></span>

<span data-ttu-id="9168c-104">Microsoft 365 组为 Microsoft 365 平台中的大量服务和工作负载提供了一个通用结构，以便为最终用户提供连接体验。</span><span class="sxs-lookup"><span data-stu-id="9168c-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="9168c-105">在其核心中，有一个 Microsoft 365 组可提供：</span><span class="sxs-lookup"><span data-stu-id="9168c-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="9168c-106">一种管理成员身份 (Azure AD 的方法) </span><span class="sxs-lookup"><span data-stu-id="9168c-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="9168c-107">邮件和对话的位置 (Exchange 邮箱、Microsoft 团队、Yammer) </span><span class="sxs-lookup"><span data-stu-id="9168c-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="9168c-108">用于将文件存储 (SharePoint 的位置) </span><span class="sxs-lookup"><span data-stu-id="9168c-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="9168c-109">安排 (Exchange) 的日历</span><span class="sxs-lookup"><span data-stu-id="9168c-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="9168c-110">用于捕获笔记 (OneNote) 的笔记本</span><span class="sxs-lookup"><span data-stu-id="9168c-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="9168c-111">在创建组的同时，还设置了许多其他资源，但是在首次从服务访问时，它们不可见：</span><span class="sxs-lookup"><span data-stu-id="9168c-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="9168c-112">用于管理组任务 (Planner) 的主板</span><span class="sxs-lookup"><span data-stu-id="9168c-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="9168c-113">用于报告 (Power BI) 的工作区</span><span class="sxs-lookup"><span data-stu-id="9168c-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="9168c-114"> (Microsoft Stream) 的共享视频区域</span><span class="sxs-lookup"><span data-stu-id="9168c-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="9168c-115"> (表单的共享表单区域) </span><span class="sxs-lookup"><span data-stu-id="9168c-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="9168c-116">在 Microsoft 365 中，其他服务能够与 Microsoft 365 组进行交互，以提供对组成员的其他功能和功能。</span><span class="sxs-lookup"><span data-stu-id="9168c-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="9168c-117">此示例包括：</span><span class="sxs-lookup"><span data-stu-id="9168c-117">Examples of this include:</span></span>

- <span data-ttu-id="9168c-118">应用程序的电源应用程序</span><span class="sxs-lookup"><span data-stu-id="9168c-118">Power Apps for apps</span></span>
- <span data-ttu-id="9168c-119">工作流的自动电源</span><span class="sxs-lookup"><span data-stu-id="9168c-119">Power Automate for workflows</span></span>
- <span data-ttu-id="9168c-120">基于瀑布的项目管理的 web 和路线图上的项目</span><span class="sxs-lookup"><span data-stu-id="9168c-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="9168c-121">基于频道的对话的团队</span><span class="sxs-lookup"><span data-stu-id="9168c-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="9168c-122">Yammer 适用于感兴趣的社区</span><span class="sxs-lookup"><span data-stu-id="9168c-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="9168c-123">用户与组的交互</span><span class="sxs-lookup"><span data-stu-id="9168c-123">User interactions with groups</span></span>

<span data-ttu-id="9168c-124">可以从各种接口（包括管理员和最终用户）创建和管理 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="9168c-125">管理体验</span><span class="sxs-lookup"><span data-stu-id="9168c-125">Administrative experiences</span></span>

<span data-ttu-id="9168c-126">管理员可以从多个工作负荷管理中心、支持脚本编写的命令行界面以及与 Graph API 交互的自定义应用程序创建和管理 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="9168c-127">唯一的例外是 Yammer 组–必须在 Yammer web 界面中创建。</span><span class="sxs-lookup"><span data-stu-id="9168c-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="9168c-128">**相关设置**</span><span class="sxs-lookup"><span data-stu-id="9168c-128">**Related settings**</span></span>

<span data-ttu-id="9168c-129">在可以管理组设置的各个管理界面中，有几个重叠需要注意。</span><span class="sxs-lookup"><span data-stu-id="9168c-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="9168c-130">**Microsoft 365 管理中心**</span><span class="sxs-lookup"><span data-stu-id="9168c-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="9168c-131">在 Microsoft 365 管理中心中，默认情况下会启用对组的来宾访问权限，这是允许所有者添加来宾的功能。</span><span class="sxs-lookup"><span data-stu-id="9168c-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="9168c-132">来自此管理中心的组没有更多的组织级控件可用。</span><span class="sxs-lookup"><span data-stu-id="9168c-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="9168c-133">**Azure AD 管理中心**</span><span class="sxs-lookup"><span data-stu-id="9168c-133">**Azure AD admin center**</span></span>

<span data-ttu-id="9168c-134">Azure AD 管理中心提供了有关用户是否可以在 Azure 门户中创建组或分配所有者，以及过期和命名策略设置的控制。</span><span class="sxs-lookup"><span data-stu-id="9168c-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="9168c-135">管理中心还提供了一些超过 Microsoft 365 管理中心的来宾邀请控制措施，例如，限制非所有者是否也可以邀请来宾的功能</span><span class="sxs-lookup"><span data-stu-id="9168c-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="9168c-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="9168c-136">**SharePoint**</span></span>

<span data-ttu-id="9168c-137">SharePoint 网站是使用所有者、成员和访问者安全组创建的，其中前两个匹配的是其 Microsoft 365 组的对应项。</span><span class="sxs-lookup"><span data-stu-id="9168c-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="9168c-138">虽然 SharePoint Online 网站的成员身份通常由关联的 Microsoft 365 组管理，但它并不是双向关系。</span><span class="sxs-lookup"><span data-stu-id="9168c-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="9168c-139">对 Microsoft 365 组级别的成员身份所做的任何更改都将反映在 SharePoint 中，但是，如果 SharePoint 组中的成员身份发生了更改，则不会在 Microsoft 365 组中反映出来。</span><span class="sxs-lookup"><span data-stu-id="9168c-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="9168c-140">用户体验</span><span class="sxs-lookup"><span data-stu-id="9168c-140">User experiences</span></span>

<span data-ttu-id="9168c-141">最终用户可以从 Microsoft 365 中的多个服务创建组，并且在其他用户中只能与组共享。</span><span class="sxs-lookup"><span data-stu-id="9168c-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="9168c-142">以下服务允许最终用户创建组：</span><span class="sxs-lookup"><span data-stu-id="9168c-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="9168c-143">适用于 web SharePoint Stream 的 Outlook Planner 项目 Microsoft 团队 Yammer</span><span class="sxs-lookup"><span data-stu-id="9168c-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="9168c-144">**组创建限制**</span><span class="sxs-lookup"><span data-stu-id="9168c-144">**Restriction of group creation**</span></span>

<span data-ttu-id="9168c-145">控制团队的数量的常用方法是限制哪些用户可以创建这些团队。</span><span class="sxs-lookup"><span data-stu-id="9168c-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="9168c-146">这只能通过限制组创建来实现。</span><span class="sxs-lookup"><span data-stu-id="9168c-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="9168c-147">这样做会影响从其他服务创建组的能力，在这种情况下，最终用户可能需要这些组。</span><span class="sxs-lookup"><span data-stu-id="9168c-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="9168c-148">Microsoft 365 组不支持从某些应用或服务中限制组创建的功能，同时允许其他应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="9168c-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="9168c-149">组创建限制的体验因应用程序和服务而异：</span><span class="sxs-lookup"><span data-stu-id="9168c-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="9168c-150">应用或服务</span><span class="sxs-lookup"><span data-stu-id="9168c-150">App or service</span></span>|<span data-ttu-id="9168c-151">体验</span><span class="sxs-lookup"><span data-stu-id="9168c-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="9168c-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="9168c-152">Outlook</span></span>|<span data-ttu-id="9168c-153">从 "人员" 页面的 "新建" 菜单中删除了 "**新建组**" 选项</span><span class="sxs-lookup"><span data-stu-id="9168c-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="9168c-154">Planner</span><span class="sxs-lookup"><span data-stu-id="9168c-154">Planner</span></span>|<span data-ttu-id="9168c-155">**新计划** 说明已关闭组创建，并提供将计划添加到现有组中的功能</span><span class="sxs-lookup"><span data-stu-id="9168c-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="9168c-156">Web 和路线图的项目</span><span class="sxs-lookup"><span data-stu-id="9168c-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="9168c-157">"**创建组**" 菜单说明组创建受到限制，并建议使用现有组。</span><span class="sxs-lookup"><span data-stu-id="9168c-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="9168c-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9168c-158">SharePoint</span></span>|<span data-ttu-id="9168c-159">仍可以创建未连接到组的团队网站。</span><span class="sxs-lookup"><span data-stu-id="9168c-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="9168c-160">Stream</span><span class="sxs-lookup"><span data-stu-id="9168c-160">Stream</span></span>|<span data-ttu-id="9168c-161">"**创建" 菜单** 下不显示 "**组**" 选项。</span><span class="sxs-lookup"><span data-stu-id="9168c-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="9168c-162">Teams</span><span class="sxs-lookup"><span data-stu-id="9168c-162">Teams</span></span>|<span data-ttu-id="9168c-163">用户无法使用新组创建团队，但仍可创建利用现有组的团队。</span><span class="sxs-lookup"><span data-stu-id="9168c-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="9168c-164">"**创建团队**" 按钮将 **从组中的 "创建团队" 中** 替换。</span><span class="sxs-lookup"><span data-stu-id="9168c-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="9168c-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="9168c-165">Yammer</span></span>|<span data-ttu-id="9168c-166">"**创建组**" 选项将从 "主组/社区导航" 中删除。</span><span class="sxs-lookup"><span data-stu-id="9168c-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="9168c-167">与组的服务交互</span><span class="sxs-lookup"><span data-stu-id="9168c-167">Services interactions with groups</span></span>

<span data-ttu-id="9168c-168">请参阅 Microsoft 365 海报中的组，以获取有关不同类型的组、如何创建和管理这些组以及几个监管建议的信息。</span><span class="sxs-lookup"><span data-stu-id="9168c-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="9168c-169">[![组信息图的缩略图](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="9168c-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="9168c-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="9168c-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="9168c-171">下表提供了 Microsoft 365 组与各种服务的交互的概述：</span><span class="sxs-lookup"><span data-stu-id="9168c-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="9168c-172">产品</span><span class="sxs-lookup"><span data-stu-id="9168c-172">Product</span></span>|<span data-ttu-id="9168c-173">功能</span><span class="sxs-lookup"><span data-stu-id="9168c-173">Features</span></span>|<span data-ttu-id="9168c-174">服务是否</span><span class="sxs-lookup"><span data-stu-id="9168c-174">Does the service</span></span><br><span data-ttu-id="9168c-175">是否存在没有组的情况？</span><span class="sxs-lookup"><span data-stu-id="9168c-175">exist without a group?</span></span>|<span data-ttu-id="9168c-176">服务是否可以</span><span class="sxs-lookup"><span data-stu-id="9168c-176">Can the service</span></span><br><span data-ttu-id="9168c-177">是否创建组？</span><span class="sxs-lookup"><span data-stu-id="9168c-177">create a group?</span></span>|<span data-ttu-id="9168c-178">删除</span><span class="sxs-lookup"><span data-stu-id="9168c-178">Does deleting the</span></span><br><span data-ttu-id="9168c-179">实例是否删除组？</span><span class="sxs-lookup"><span data-stu-id="9168c-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="9168c-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="9168c-180">Azure AD</span></span>|<span data-ttu-id="9168c-181">成员资格、组控件、来宾</span><span class="sxs-lookup"><span data-stu-id="9168c-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="9168c-182">是</span><span class="sxs-lookup"><span data-stu-id="9168c-182">Yes</span></span>|<span data-ttu-id="9168c-183">是</span><span class="sxs-lookup"><span data-stu-id="9168c-183">Yes</span></span>|<span data-ttu-id="9168c-184">是</span><span class="sxs-lookup"><span data-stu-id="9168c-184">Yes</span></span>|
|<span data-ttu-id="9168c-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="9168c-185">Exchange</span></span>|<span data-ttu-id="9168c-186">日历、邮箱</span><span class="sxs-lookup"><span data-stu-id="9168c-186">Calendar, mailbox</span></span>|<span data-ttu-id="9168c-187">是</span><span class="sxs-lookup"><span data-stu-id="9168c-187">Yes</span></span>|<span data-ttu-id="9168c-188">是</span><span class="sxs-lookup"><span data-stu-id="9168c-188">Yes</span></span>|<span data-ttu-id="9168c-189">是</span><span class="sxs-lookup"><span data-stu-id="9168c-189">Yes</span></span>|
|<span data-ttu-id="9168c-190">Forms</span><span class="sxs-lookup"><span data-stu-id="9168c-190">Forms</span></span>|<span data-ttu-id="9168c-191">表单</span><span class="sxs-lookup"><span data-stu-id="9168c-191">Form</span></span>|<span data-ttu-id="9168c-192">是</span><span class="sxs-lookup"><span data-stu-id="9168c-192">Yes</span></span>|<span data-ttu-id="9168c-193">否</span><span class="sxs-lookup"><span data-stu-id="9168c-193">No</span></span>|<span data-ttu-id="9168c-194">否</span><span class="sxs-lookup"><span data-stu-id="9168c-194">No</span></span>|
|<span data-ttu-id="9168c-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="9168c-195">OneNote</span></span>|<span data-ttu-id="9168c-196">Notebook</span><span class="sxs-lookup"><span data-stu-id="9168c-196">Notebook</span></span>|<span data-ttu-id="9168c-197">是</span><span class="sxs-lookup"><span data-stu-id="9168c-197">Yes</span></span>|<span data-ttu-id="9168c-198">否</span><span class="sxs-lookup"><span data-stu-id="9168c-198">No</span></span>|<span data-ttu-id="9168c-199">否</span><span class="sxs-lookup"><span data-stu-id="9168c-199">No</span></span>|
|<span data-ttu-id="9168c-200">Planner</span><span class="sxs-lookup"><span data-stu-id="9168c-200">Planner</span></span>|<span data-ttu-id="9168c-201">任务板</span><span class="sxs-lookup"><span data-stu-id="9168c-201">Task board</span></span>|<span data-ttu-id="9168c-202">否</span><span class="sxs-lookup"><span data-stu-id="9168c-202">No</span></span>|<span data-ttu-id="9168c-203">是</span><span class="sxs-lookup"><span data-stu-id="9168c-203">Yes</span></span>|<span data-ttu-id="9168c-204">是</span><span class="sxs-lookup"><span data-stu-id="9168c-204">Yes</span></span>|
|<span data-ttu-id="9168c-205">Power Apps 应用</span><span class="sxs-lookup"><span data-stu-id="9168c-205">Power Apps app</span></span>|<span data-ttu-id="9168c-206">应用</span><span class="sxs-lookup"><span data-stu-id="9168c-206">App</span></span>|<span data-ttu-id="9168c-207">是</span><span class="sxs-lookup"><span data-stu-id="9168c-207">Yes</span></span>|<span data-ttu-id="9168c-208">否</span><span class="sxs-lookup"><span data-stu-id="9168c-208">No</span></span>|<span data-ttu-id="9168c-209">否</span><span class="sxs-lookup"><span data-stu-id="9168c-209">No</span></span>|
|<span data-ttu-id="9168c-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="9168c-210">Power Automate</span></span>|<span data-ttu-id="9168c-211">工作流</span><span class="sxs-lookup"><span data-stu-id="9168c-211">Workflow</span></span>|<span data-ttu-id="9168c-212">是</span><span class="sxs-lookup"><span data-stu-id="9168c-212">Yes</span></span>|<span data-ttu-id="9168c-213">否</span><span class="sxs-lookup"><span data-stu-id="9168c-213">No</span></span>|<span data-ttu-id="9168c-214">否</span><span class="sxs-lookup"><span data-stu-id="9168c-214">No</span></span>|
|<span data-ttu-id="9168c-215">Power BI (经典) </span><span class="sxs-lookup"><span data-stu-id="9168c-215">Power BI (classic)</span></span>|<span data-ttu-id="9168c-216">工作区</span><span class="sxs-lookup"><span data-stu-id="9168c-216">Workspace</span></span>|<span data-ttu-id="9168c-217">否</span><span class="sxs-lookup"><span data-stu-id="9168c-217">No</span></span>|<span data-ttu-id="9168c-218">是</span><span class="sxs-lookup"><span data-stu-id="9168c-218">Yes</span></span>|<span data-ttu-id="9168c-219">是</span><span class="sxs-lookup"><span data-stu-id="9168c-219">Yes</span></span>|
|<span data-ttu-id="9168c-220">Power BI (新) </span><span class="sxs-lookup"><span data-stu-id="9168c-220">Power BI (new)</span></span>|<span data-ttu-id="9168c-221">工作区</span><span class="sxs-lookup"><span data-stu-id="9168c-221">Workspace</span></span>|<span data-ttu-id="9168c-222">是</span><span class="sxs-lookup"><span data-stu-id="9168c-222">Yes</span></span>|<span data-ttu-id="9168c-223">否</span><span class="sxs-lookup"><span data-stu-id="9168c-223">No</span></span>|<span data-ttu-id="9168c-224">是</span><span class="sxs-lookup"><span data-stu-id="9168c-224">Yes</span></span>|
|<span data-ttu-id="9168c-225">Project 网页版</span><span class="sxs-lookup"><span data-stu-id="9168c-225">Project for the web</span></span>|<span data-ttu-id="9168c-226">项目计划</span><span class="sxs-lookup"><span data-stu-id="9168c-226">Project plan</span></span>|<span data-ttu-id="9168c-227">是</span><span class="sxs-lookup"><span data-stu-id="9168c-227">Yes</span></span>|<span data-ttu-id="9168c-228">是</span><span class="sxs-lookup"><span data-stu-id="9168c-228">Yes</span></span>|<span data-ttu-id="9168c-229">否</span><span class="sxs-lookup"><span data-stu-id="9168c-229">No</span></span>|
|<span data-ttu-id="9168c-230">路线图</span><span class="sxs-lookup"><span data-stu-id="9168c-230">Roadmap</span></span>|<span data-ttu-id="9168c-231">路线图</span><span class="sxs-lookup"><span data-stu-id="9168c-231">Roadmap</span></span>|<span data-ttu-id="9168c-232">是</span><span class="sxs-lookup"><span data-stu-id="9168c-232">Yes</span></span>|<span data-ttu-id="9168c-233">是</span><span class="sxs-lookup"><span data-stu-id="9168c-233">Yes</span></span>|<span data-ttu-id="9168c-234">否</span><span class="sxs-lookup"><span data-stu-id="9168c-234">No</span></span>|
|<span data-ttu-id="9168c-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9168c-235">SharePoint</span></span>|<span data-ttu-id="9168c-236">Site</span><span class="sxs-lookup"><span data-stu-id="9168c-236">Site</span></span>|<span data-ttu-id="9168c-237">是</span><span class="sxs-lookup"><span data-stu-id="9168c-237">Yes</span></span>|<span data-ttu-id="9168c-238">是</span><span class="sxs-lookup"><span data-stu-id="9168c-238">Yes</span></span>|<span data-ttu-id="9168c-239">是</span><span class="sxs-lookup"><span data-stu-id="9168c-239">Yes</span></span>|
|<span data-ttu-id="9168c-240">Stream</span><span class="sxs-lookup"><span data-stu-id="9168c-240">Stream</span></span>|<span data-ttu-id="9168c-241">频道、视频</span><span class="sxs-lookup"><span data-stu-id="9168c-241">Channel, video</span></span>|<span data-ttu-id="9168c-242">是</span><span class="sxs-lookup"><span data-stu-id="9168c-242">Yes</span></span>|<span data-ttu-id="9168c-243">是</span><span class="sxs-lookup"><span data-stu-id="9168c-243">Yes</span></span>|<span data-ttu-id="9168c-244">是</span><span class="sxs-lookup"><span data-stu-id="9168c-244">Yes</span></span>|
|<span data-ttu-id="9168c-245">Teams</span><span class="sxs-lookup"><span data-stu-id="9168c-245">Teams</span></span>|<span data-ttu-id="9168c-246">团队</span><span class="sxs-lookup"><span data-stu-id="9168c-246">Team</span></span>|<span data-ttu-id="9168c-247">否</span><span class="sxs-lookup"><span data-stu-id="9168c-247">No</span></span>|<span data-ttu-id="9168c-248">是</span><span class="sxs-lookup"><span data-stu-id="9168c-248">Yes</span></span>|<span data-ttu-id="9168c-249">是</span><span class="sxs-lookup"><span data-stu-id="9168c-249">Yes</span></span>|
|<span data-ttu-id="9168c-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="9168c-250">Yammer</span></span>|<span data-ttu-id="9168c-251">组</span><span class="sxs-lookup"><span data-stu-id="9168c-251">Group</span></span>|<span data-ttu-id="9168c-252">是</span><span class="sxs-lookup"><span data-stu-id="9168c-252">Yes</span></span>|<span data-ttu-id="9168c-253">是</span><span class="sxs-lookup"><span data-stu-id="9168c-253">Yes</span></span>|<span data-ttu-id="9168c-254">是</span><span class="sxs-lookup"><span data-stu-id="9168c-254">Yes</span></span>|

<span data-ttu-id="9168c-255">[！注意] 上表提供了与 Microsoft 365 服务的组交互的高级概述，您应该了解许多细微差别和复杂之处。</span><span class="sxs-lookup"><span data-stu-id="9168c-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="9168c-256">以下各节更深入地介绍了特定工作负荷及其与组的交互。</span><span class="sxs-lookup"><span data-stu-id="9168c-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="9168c-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="9168c-257">Azure AD</span></span>

<span data-ttu-id="9168c-258">Azure AD 在 Microsoft 365 中提供了基础标识管理功能。</span><span class="sxs-lookup"><span data-stu-id="9168c-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="9168c-259">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="9168c-260">组成员身份</span><span class="sxs-lookup"><span data-stu-id="9168c-260">Group membership</span></span>
- <span data-ttu-id="9168c-261">命名策略</span><span class="sxs-lookup"><span data-stu-id="9168c-261">Naming policy</span></span>
- <span data-ttu-id="9168c-262">过期策略</span><span class="sxs-lookup"><span data-stu-id="9168c-262">Expiration policy</span></span>
- <span data-ttu-id="9168c-263">限制</span><span class="sxs-lookup"><span data-stu-id="9168c-263">Guests</span></span>
- <span data-ttu-id="9168c-264">组创建限制</span><span class="sxs-lookup"><span data-stu-id="9168c-264">Restriction of Group creation</span></span>

<span data-ttu-id="9168c-265">**Azure AD 是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="9168c-266">是的，可以从 Azure AD 创建 Microsoft 365 组，方法是通过管理 web 门户、PowerShell 或 Graph API。</span><span class="sxs-lookup"><span data-stu-id="9168c-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="9168c-267">**Azure AD 是否不存在组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="9168c-268">是的，Azure AD 执行大量与 Microsoft 365 组没有关系的服务。</span><span class="sxs-lookup"><span data-stu-id="9168c-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="9168c-269">每个 Microsoft 365 组都表示为 Azure AD 中的一个对象。</span><span class="sxs-lookup"><span data-stu-id="9168c-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="9168c-270">**每个组是否可以有多个 Azure AD 实例？**</span><span class="sxs-lookup"><span data-stu-id="9168c-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="9168c-271">否，只有一个 Azure AD 实例。</span><span class="sxs-lookup"><span data-stu-id="9168c-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="9168c-272">**Azure AD 是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="9168c-273">是，因为 Azure AD 是提供组成员身份服务的基础平台。</span><span class="sxs-lookup"><span data-stu-id="9168c-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="9168c-274">**Azure AD 与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="9168c-275">否，Azure AD 是组存在的基础平台。</span><span class="sxs-lookup"><span data-stu-id="9168c-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="9168c-276">**删除实例是否删除了组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="9168c-277">在 Azure AD 中删除组将删除与组关联的相关服务和内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="9168c-278">Teams</span><span class="sxs-lookup"><span data-stu-id="9168c-278">Teams</span></span>

<span data-ttu-id="9168c-279">团队是一个以聊天为中心的工作区，旨在通过提供与各种 Microsoft 和第三方服务交互的单一界面来增强协作。</span><span class="sxs-lookup"><span data-stu-id="9168c-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="9168c-280">默认情况下，在创建团队时，与 Microsoft 365 组关联的邮箱和日历将隐藏在 Exchange 中的全局地址列表和 Outlook 中。</span><span class="sxs-lookup"><span data-stu-id="9168c-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="9168c-281">如果用户希望同时在同一个 Microsoft 365 组上使用 Outlook 和团队，则管理员可以手动将其重写。</span><span class="sxs-lookup"><span data-stu-id="9168c-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="9168c-282">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="9168c-283">对话</span><span class="sxs-lookup"><span data-stu-id="9168c-283">Conversations</span></span>
- <span data-ttu-id="9168c-284">频道 & 选项卡</span><span class="sxs-lookup"><span data-stu-id="9168c-284">Channels & tabs</span></span>
- <span data-ttu-id="9168c-285">会议</span><span class="sxs-lookup"><span data-stu-id="9168c-285">Meetings</span></span>

<span data-ttu-id="9168c-286">**团队是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="9168c-287">是的，创建新的团队将创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="9168c-288">此外，还可以为现有组创建当前不具有一个团队的团队。</span><span class="sxs-lookup"><span data-stu-id="9168c-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="9168c-289">**是否存在没有组的团队？**</span><span class="sxs-lookup"><span data-stu-id="9168c-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="9168c-290">否，不能存在没有组的团队。</span><span class="sxs-lookup"><span data-stu-id="9168c-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="9168c-291">**每个组是否可以有多个团队？**</span><span class="sxs-lookup"><span data-stu-id="9168c-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="9168c-292">否，团队和组之间的关系为1:1。</span><span class="sxs-lookup"><span data-stu-id="9168c-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="9168c-293">**团队是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-294">不能，团队本身只能与单个组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="9168c-295">**团队与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="9168c-296">否，团队只能与最初关联的组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="9168c-297">**删除团队是否删除了组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="9168c-298">是的，删除 Microsoft 团队中的团队将删除组、与组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="9168c-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="9168c-299">Exchange</span></span>

<span data-ttu-id="9168c-300">Exchange Online 提供了邮件、日历、联系人和相关功能。</span><span class="sxs-lookup"><span data-stu-id="9168c-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="9168c-301">在组的上下文中，仅与一个资源相关联–而不是与整个服务实例相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="9168c-302">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="9168c-303">邮箱和日历</span><span class="sxs-lookup"><span data-stu-id="9168c-303">Mailbox and calendar</span></span>
- <span data-ttu-id="9168c-304">能够通过电子邮件发送所有组成员</span><span class="sxs-lookup"><span data-stu-id="9168c-304">Ability to email all Group members</span></span>
- <span data-ttu-id="9168c-305">存储团队频道对话以用于电子数据展示目的、Planner 注释</span><span class="sxs-lookup"><span data-stu-id="9168c-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="9168c-306">**Exchange 是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="9168c-307">是的，可以从 Exchange Online 管理中心和 Outlook 创建组。</span><span class="sxs-lookup"><span data-stu-id="9168c-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="9168c-308">您还可以将 Exchange 通讯组列表转换为 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="9168c-309">**Exchange 是否不存在组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="9168c-310">是的，Exchange Online 提供了许多服务，包括共享邮箱和日历，没有任何组关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="9168c-311">**每个组是否可以有多个 Exchange 邮箱或日历实例？**</span><span class="sxs-lookup"><span data-stu-id="9168c-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="9168c-312">不可以，组只能有一个 Exchange Online 邮箱和日历。</span><span class="sxs-lookup"><span data-stu-id="9168c-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="9168c-313">**Exchange 邮箱和日历是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-314">否，邮箱和日历与组有1:1 关系。</span><span class="sxs-lookup"><span data-stu-id="9168c-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="9168c-315">可以与其他用户或组共享邮箱，但这不会建立任何形式的服务关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="9168c-316">**Exchange 邮箱或日历与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="9168c-317">否，不能将邮箱和日历更改为其他组。</span><span class="sxs-lookup"><span data-stu-id="9168c-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="9168c-318">但是，可以在 Outlook 或使用第三方工具将内容从一个邮箱移动到另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="9168c-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="9168c-319">**删除邮箱是否删除了组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="9168c-320">是的，删除 Exchange 中的邮箱将删除该组以及与组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="9168c-321">Forms</span><span class="sxs-lookup"><span data-stu-id="9168c-321">Forms</span></span>

<span data-ttu-id="9168c-322">表单提供基于 web 的调查和测验。</span><span class="sxs-lookup"><span data-stu-id="9168c-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="9168c-323">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="9168c-324">表单的所有权</span><span class="sxs-lookup"><span data-stu-id="9168c-324">Ownership of forms</span></span>

<span data-ttu-id="9168c-325">**表单是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="9168c-326">否，窗体无法创建组。</span><span class="sxs-lookup"><span data-stu-id="9168c-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="9168c-327">**表单是否存在而没有组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="9168c-328">是的，可以直接在最终用户帐户中创建调查和测验。</span><span class="sxs-lookup"><span data-stu-id="9168c-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="9168c-329">**每个组是否可以有多个窗体？**</span><span class="sxs-lookup"><span data-stu-id="9168c-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="9168c-330">是的，可以有多个窗体与组关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="9168c-331">**表单是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-332">不能，窗体只能与单个组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="9168c-333">**窗体与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="9168c-334">否，一旦将窗体与组相关联 (在中直接创建，或从单个) 转移的所有权，则无法将其移到其他组。</span><span class="sxs-lookup"><span data-stu-id="9168c-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="9168c-335">**删除该表单会删除此组吗？**</span><span class="sxs-lookup"><span data-stu-id="9168c-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="9168c-336">否，不能从窗体界面中删除组，只能从单个窗体中删除。</span><span class="sxs-lookup"><span data-stu-id="9168c-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="9168c-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="9168c-337">OneNote</span></span>

<span data-ttu-id="9168c-338">OneNote 是一个数字笔记本应用程序。</span><span class="sxs-lookup"><span data-stu-id="9168c-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="9168c-339">使用组创建的 OneNote 笔记本是关联的 SharePoint 网站中的文件，而不是与组连接的服务。</span><span class="sxs-lookup"><span data-stu-id="9168c-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="9168c-340">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="9168c-341">共享笔记本 (存储在与组关联的 SharePoint 库中) </span><span class="sxs-lookup"><span data-stu-id="9168c-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="9168c-342">**OneNote 是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="9168c-343">否，OneNote 应用程序无法创建组。</span><span class="sxs-lookup"><span data-stu-id="9168c-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="9168c-344">**OneNote 笔记本是否在没有组的情况下存在？**</span><span class="sxs-lookup"><span data-stu-id="9168c-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="9168c-345">是的，笔记本可以直接在 OneDrive 中创建，也可以在其他共享位置创建。</span><span class="sxs-lookup"><span data-stu-id="9168c-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="9168c-346">**每个组是否可以有多个 OneNote 笔记本？**</span><span class="sxs-lookup"><span data-stu-id="9168c-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="9168c-347">是的，默认情况下会创建笔记本，并且可以添加其他人，但与组关联的服务的 OneNote 链接将始终转到默认笔记本。</span><span class="sxs-lookup"><span data-stu-id="9168c-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="9168c-348">**OneNote 笔记本是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-349">否，笔记本存储在与组关联的 SharePoint 网站库中并从各种接口进行链接。</span><span class="sxs-lookup"><span data-stu-id="9168c-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="9168c-350">但可以与其他组共享，其方式与与个人共享的方式相同。</span><span class="sxs-lookup"><span data-stu-id="9168c-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="9168c-351">**笔记本与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="9168c-352">否，笔记本本身与组相关联，并且可以从其他组连接服务直接访问，但是可以在 OneNote 应用程序中将内容从一个笔记本移动到另一个笔记本。</span><span class="sxs-lookup"><span data-stu-id="9168c-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="9168c-353">**删除笔记本是否删除了此组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="9168c-354">否，但如果删除了 OneNote 笔记本，某些与组相关的服务中的链接可能会断开。</span><span class="sxs-lookup"><span data-stu-id="9168c-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="9168c-355">Planner</span><span class="sxs-lookup"><span data-stu-id="9168c-355">Planner</span></span>

<span data-ttu-id="9168c-356">Planner 是一种轻型组任务管理服务。</span><span class="sxs-lookup"><span data-stu-id="9168c-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="9168c-357">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="9168c-358">用于管理组任务的板</span><span class="sxs-lookup"><span data-stu-id="9168c-358">Board for managing group tasks</span></span>

<span data-ttu-id="9168c-359">**规划者是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="9168c-360">是的，创建计划将创建新组。</span><span class="sxs-lookup"><span data-stu-id="9168c-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="9168c-361">**是否不存在具有组的 Planner 面板？**</span><span class="sxs-lookup"><span data-stu-id="9168c-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="9168c-362">否，计划必须与组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="9168c-363">**每个组是否可以有多个计划？**</span><span class="sxs-lookup"><span data-stu-id="9168c-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="9168c-364">是的，每个组可以有多个计划。</span><span class="sxs-lookup"><span data-stu-id="9168c-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="9168c-365">**计划是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-366">否，计划只依赖于组成员身份来确定访问权限。</span><span class="sxs-lookup"><span data-stu-id="9168c-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="9168c-367">**计划与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="9168c-368">但如果复制计划，则会创建一个新组。</span><span class="sxs-lookup"><span data-stu-id="9168c-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="9168c-369">由任何其他应用程序创建的组不会为用户自动显示在 Planner 中。</span><span class="sxs-lookup"><span data-stu-id="9168c-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="9168c-370">若要访问主板，最初需要从其他基于组的界面（如 Outlook）打开它。</span><span class="sxs-lookup"><span data-stu-id="9168c-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="9168c-371">**删除该计划是否删除了此组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="9168c-372">是的，删除计划将删除组和组相关的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="9168c-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="9168c-373">Power Apps</span></span>

<span data-ttu-id="9168c-374">节能应用程序为无需代码的应用程序开发提供了画布。</span><span class="sxs-lookup"><span data-stu-id="9168c-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="9168c-375">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="9168c-376">可以与组共享应用程序以进行运行和修改</span><span class="sxs-lookup"><span data-stu-id="9168c-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="9168c-377">**电源应用是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="9168c-378">否，Power Apps 无法创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="9168c-379">**是否在没有组的情况下存在电源应用？**</span><span class="sxs-lookup"><span data-stu-id="9168c-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="9168c-380">是的，可以在 Power 应用程序中创建应用程序，并将其驻留在创建者帐户中，直到共享或发布。</span><span class="sxs-lookup"><span data-stu-id="9168c-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="9168c-381">**每个组是否可以有多个应用程序？**</span><span class="sxs-lookup"><span data-stu-id="9168c-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="9168c-382">是的，可以有多个与组共享的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9168c-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="9168c-383">**是否可以将应用程序与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-384">是的，可以与多个组共享应用程序。</span><span class="sxs-lookup"><span data-stu-id="9168c-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="9168c-385">**应用与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="9168c-386">是，因为电源应用和 Microsoft 365 组之间的关联仅共享–应用程序仍与创建者驻留在一起。</span><span class="sxs-lookup"><span data-stu-id="9168c-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9168c-387">[在与用户共享应用程序之前，必须启用组的安全性](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="9168c-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="9168c-388">**删除应用程序是否删除组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="9168c-389">否，应用不会连接到组，而不是与它们共享。</span><span class="sxs-lookup"><span data-stu-id="9168c-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="9168c-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="9168c-390">Power Automate</span></span>

<span data-ttu-id="9168c-391">电源自动运行 (以前称为 Microsoft Flow) 提供工作流和自动化服务。</span><span class="sxs-lookup"><span data-stu-id="9168c-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="9168c-392">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="9168c-393">可以将工作流与组共享，以进行运行和修改。</span><span class="sxs-lookup"><span data-stu-id="9168c-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="9168c-394">**能否对组进行电源自动创建？**</span><span class="sxs-lookup"><span data-stu-id="9168c-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="9168c-395">不，电源自动化无法在关联的上下文中创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="9168c-396">但是，可以创建执行各种操作（如创建 Azure AD 安全组或更新 Microsoft 365 组的成员身份）的流。</span><span class="sxs-lookup"><span data-stu-id="9168c-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="9168c-397">**是否存在不含组的流？**</span><span class="sxs-lookup"><span data-stu-id="9168c-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="9168c-398">是的，在 Power 自动化中可以创建流，并驻留在创建者帐户中，直到共享或发布。</span><span class="sxs-lookup"><span data-stu-id="9168c-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="9168c-399">**每个组是否可以有多个流？**</span><span class="sxs-lookup"><span data-stu-id="9168c-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="9168c-400">是的，可以有多个流与组共享。</span><span class="sxs-lookup"><span data-stu-id="9168c-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="9168c-401">**流是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-402">是的，可以与多个组共享流。</span><span class="sxs-lookup"><span data-stu-id="9168c-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="9168c-403">**流与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="9168c-404">是的，由于电源自动化与 Microsoft 365 组之间的关联仅共享–该流仍将与创建者驻留在一起。</span><span class="sxs-lookup"><span data-stu-id="9168c-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="9168c-405">**删除流是否删除组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="9168c-406">否，与电源应用一样，流不会连接到组，而不是与它们共享。</span><span class="sxs-lookup"><span data-stu-id="9168c-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="9168c-407">Power BI (经典) </span><span class="sxs-lookup"><span data-stu-id="9168c-407">Power BI (classic)</span></span>

<span data-ttu-id="9168c-408">Power BI 提供交互式数据驱动仪表板和报告。</span><span class="sxs-lookup"><span data-stu-id="9168c-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="9168c-409">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="9168c-410">数据报告</span><span class="sxs-lookup"><span data-stu-id="9168c-410">Data reporting</span></span>

<span data-ttu-id="9168c-411">**Power BI 是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="9168c-412">是的，创建经典工作区将创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="9168c-413">**是否在没有组的情况下存在 Power BI 经典工作区？**</span><span class="sxs-lookup"><span data-stu-id="9168c-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="9168c-414">不是， [POWER BI 中的经典工作区必须与组相关联](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace)。</span><span class="sxs-lookup"><span data-stu-id="9168c-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="9168c-415">**每个组是否可以有多个 Power BI 工作区？**</span><span class="sxs-lookup"><span data-stu-id="9168c-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="9168c-416">否，经典工作区和组之间的关系为1:1。</span><span class="sxs-lookup"><span data-stu-id="9168c-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="9168c-417">**是否可以将工作区与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-418">从技术上讲，如果使用组创建经典工作区，则可以在具有用户和安全组的组外共享内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="9168c-419">**工作区与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="9168c-420">否，经典工作区本身与组关联，但可以在 Power BI 接口中将内容移动到另一个工作区，也可以通过在本地导出内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="9168c-421">**删除该工作区是否删除了此组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="9168c-422">是的，删除 Power BI 中的工作区将删除组和组相关的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="9168c-423">Power BI (新) </span><span class="sxs-lookup"><span data-stu-id="9168c-423">Power BI (new)</span></span>

<span data-ttu-id="9168c-424">Power BI 提供交互式数据驱动仪表板和报告。</span><span class="sxs-lookup"><span data-stu-id="9168c-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="9168c-425">在 Power BI 中创建新的工作区不会创建 Microsoft 365 组时，通过任何其他方式创建一个组将会在 Power BI 中创建一个新的 (而不是经典) 工作区。</span><span class="sxs-lookup"><span data-stu-id="9168c-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="9168c-426">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="9168c-427">数据报告</span><span class="sxs-lookup"><span data-stu-id="9168c-427">Data reporting</span></span>

<span data-ttu-id="9168c-428">**Power BI 是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="9168c-429">否，不能从新的 Power BI 接口创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="9168c-430">**新的 Power BI 工作区在没有组的情况下存在吗？**</span><span class="sxs-lookup"><span data-stu-id="9168c-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="9168c-431">是的，在 Power BI 中创建的报告和工作区可能与 Microsoft 365 组不关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="9168c-432">**每个组是否可以有多个工作区？**</span><span class="sxs-lookup"><span data-stu-id="9168c-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="9168c-433">是的， [由 POWER BI 创建的多个工作区可以与单个组共享](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)。</span><span class="sxs-lookup"><span data-stu-id="9168c-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="9168c-434">**是否可以将工作区与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-435">否，Power BI 创建的工作区只能与单个组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="9168c-436">**工作区与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="9168c-437">"是" 和 "否"。</span><span class="sxs-lookup"><span data-stu-id="9168c-437">Yes and no.</span></span> <span data-ttu-id="9168c-438">Power BI 创建的工作区一次只能与一个组关联，但可以随时更改关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="9168c-439">组在 Power BI 中创建的工作区将永久关联到该组。</span><span class="sxs-lookup"><span data-stu-id="9168c-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="9168c-440">**删除该工作区是否删除了此组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="9168c-441">是的，删除 Power BI 中的工作区将删除组和组相关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="9168c-442">Project 网页版</span><span class="sxs-lookup"><span data-stu-id="9168c-442">Project for the web</span></span>

<span data-ttu-id="9168c-443">为 web 项目提供了创建项目计划、甘特图和路线图的功能。</span><span class="sxs-lookup"><span data-stu-id="9168c-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="9168c-444">提供给组的主要功能。</span><span class="sxs-lookup"><span data-stu-id="9168c-444">Key features provided to groups.</span></span>

- <span data-ttu-id="9168c-445">项目计划</span><span class="sxs-lookup"><span data-stu-id="9168c-445">Project plans</span></span>

<span data-ttu-id="9168c-446">**可以为 web 创建一个组的项目吗？**</span><span class="sxs-lookup"><span data-stu-id="9168c-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="9168c-447">是的，可以直接从 web 项目创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="9168c-448">**是否存在不包含组的项目？**</span><span class="sxs-lookup"><span data-stu-id="9168c-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="9168c-449">是的，项目可以存在，但不与 Microsoft 365 组关联，但任务分配需要组关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="9168c-450">**每个组是否可以有多个项目？**</span><span class="sxs-lookup"><span data-stu-id="9168c-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="9168c-451">是的，可以在一个组中连接多个项目。</span><span class="sxs-lookup"><span data-stu-id="9168c-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="9168c-452">**项目是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-453">否，一个项目只能与一个组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="9168c-454">**项目与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="9168c-455">否，一旦建立与组的关联，就无法更改。</span><span class="sxs-lookup"><span data-stu-id="9168c-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="9168c-456">**删除项目后删除了组吗？**</span><span class="sxs-lookup"><span data-stu-id="9168c-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="9168c-457">否，删除 web 项目中的项目不会删除组。</span><span class="sxs-lookup"><span data-stu-id="9168c-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="9168c-458">路线图</span><span class="sxs-lookup"><span data-stu-id="9168c-458">Roadmap</span></span>

<span data-ttu-id="9168c-459">通过路线图，可以为 web 和 Project Online 的 Project 创建项目路线图。</span><span class="sxs-lookup"><span data-stu-id="9168c-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="9168c-460">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="9168c-461">项目路线图</span><span class="sxs-lookup"><span data-stu-id="9168c-461">Project roadmaps</span></span>

<span data-ttu-id="9168c-462">**路线图是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="9168c-463">是的，可以直接从路线图创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="9168c-464">**是否存在没有组的路线图？**</span><span class="sxs-lookup"><span data-stu-id="9168c-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="9168c-465">是的，路线图可以存在，但不与 Microsoft 365 组关联，但共享路线图需要组关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="9168c-466">**每个组是否可以有多个路线图？**</span><span class="sxs-lookup"><span data-stu-id="9168c-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="9168c-467">是的，可以将多个路线图连接到单个组。</span><span class="sxs-lookup"><span data-stu-id="9168c-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="9168c-468">**是否可以将路线图与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-469">否，一个路线图只能与一个组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="9168c-470">**路线图与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="9168c-471">否，一旦建立与组的关联，就无法更改。</span><span class="sxs-lookup"><span data-stu-id="9168c-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="9168c-472">**删除该路线图是否删除了此组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="9168c-473">否，删除路线图不会删除组。</span><span class="sxs-lookup"><span data-stu-id="9168c-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="9168c-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9168c-474">SharePoint</span></span>

<span data-ttu-id="9168c-475">SharePoint 是一种基于 web 的内容管理平台，可提供多种 Microsoft 365 服务的其他内容和存储服务。</span><span class="sxs-lookup"><span data-stu-id="9168c-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="9168c-476">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="9168c-477">文档库</span><span class="sxs-lookup"><span data-stu-id="9168c-477">Document library</span></span>
- <span data-ttu-id="9168c-478">OneNote 笔记本存储库</span><span class="sxs-lookup"><span data-stu-id="9168c-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="9168c-479">团队 wiki 文件的存储</span><span class="sxs-lookup"><span data-stu-id="9168c-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="9168c-480">**SharePoint 是否可以创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="9168c-481">是的，默认情况下，在 SharePoint 中创建团队网站将创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="9168c-482">此外，还可以为现有网站创建组和（可选）团队。</span><span class="sxs-lookup"><span data-stu-id="9168c-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="9168c-483">**SharePoint 网站是否存在而不包含组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="9168c-484">是的，SharePoint 提供了大量与非组关联的服务和网站，如通信和中心网站。</span><span class="sxs-lookup"><span data-stu-id="9168c-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="9168c-485">**每个组是否可以有多个站点？**</span><span class="sxs-lookup"><span data-stu-id="9168c-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="9168c-486">不能，每个组只能有一个站点。</span><span class="sxs-lookup"><span data-stu-id="9168c-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="9168c-487">团队中的专用通道使用未连接到组的其他网站。</span><span class="sxs-lookup"><span data-stu-id="9168c-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="9168c-488">**是否可以将网站与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-489">从技术上说，在使用组创建网站时，可以与其他组共享内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="9168c-490">**网站与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="9168c-491">否，网站本身与组关联，但可以通过在本地导出内容或使用第三方工具将内容从一个网站移到另一个网站。</span><span class="sxs-lookup"><span data-stu-id="9168c-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="9168c-492">**删除网站是否删除组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="9168c-493">是，删除 SharePoint 中的网站将删除组和组相关的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="9168c-494">Stream</span><span class="sxs-lookup"><span data-stu-id="9168c-494">Stream</span></span>

<span data-ttu-id="9168c-495">Microsoft Stream 是一个视频托管和共享平台。</span><span class="sxs-lookup"><span data-stu-id="9168c-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="9168c-496">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="9168c-497">视频存储</span><span class="sxs-lookup"><span data-stu-id="9168c-497">Video storage</span></span>
- <span data-ttu-id="9168c-498">团队会议录制</span><span class="sxs-lookup"><span data-stu-id="9168c-498">Teams meeting recording</span></span>
- <span data-ttu-id="9168c-499">视频通道</span><span class="sxs-lookup"><span data-stu-id="9168c-499">Video channels</span></span>

<span data-ttu-id="9168c-500">**是否可以流创建组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="9168c-501">是的，可以直接从 Stream 创建一个新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="9168c-502">**是否存在没有组的流？**</span><span class="sxs-lookup"><span data-stu-id="9168c-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="9168c-503">是的，视频通道和视频可以存在于 Stream 中，而不会与组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="9168c-504">**每个组是否可以有多个视频和通道？**</span><span class="sxs-lookup"><span data-stu-id="9168c-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="9168c-505">是的，每个组中可以有多个视频和频道。</span><span class="sxs-lookup"><span data-stu-id="9168c-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="9168c-506">**视频或通道是否可以与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="9168c-507">是的，虽然使用组创建视频或频道，但可以与其他组共享。</span><span class="sxs-lookup"><span data-stu-id="9168c-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="9168c-508">**它与组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="9168c-509">是和否;Stream 中的视频由原始上载程序或会议录制器拥有，因此可以与任何组关联，但视频通道只能与最初在其中创建的组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="9168c-510">**删除视频或频道是否删除了组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="9168c-511">否，删除视频或频道不会删除该组。</span><span class="sxs-lookup"><span data-stu-id="9168c-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="9168c-512">但是，删除 Stream 中的组本身将会删除与组关联的服务和内容（实际视频除外）。</span><span class="sxs-lookup"><span data-stu-id="9168c-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="9168c-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="9168c-513">Yammer</span></span>

<span data-ttu-id="9168c-514">Yammer 是一个企业社交平台，旨在促进组织内部和组织之间的社区参与。</span><span class="sxs-lookup"><span data-stu-id="9168c-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="9168c-515">在 Yammer 中创建一个以前称为 "组" ) 的社区 (将创建一个邮箱，但目前不使用。</span><span class="sxs-lookup"><span data-stu-id="9168c-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="9168c-516">与 Yammer 关联的 Microsoft 365 组不能与 Microsoft 团队中的团队一起使用。</span><span class="sxs-lookup"><span data-stu-id="9168c-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="9168c-517">**提供给组的主要功能**</span><span class="sxs-lookup"><span data-stu-id="9168c-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="9168c-518">会话区域</span><span class="sxs-lookup"><span data-stu-id="9168c-518">Conversation area</span></span>

<span data-ttu-id="9168c-519">**Yammer 是否可以创建 Microsoft 365 组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="9168c-520">是，在 Yammer 中创建新组将创建一个新的 Microsoft 365 组（如果已连接平台，并且用户能够创建组）。</span><span class="sxs-lookup"><span data-stu-id="9168c-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="9168c-521">不能在 Yammer 本身之外的任何接口或服务中创建具有关联的 Microsoft 365 组的 Yammer 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="9168c-522">**Yammer 组是否存在不包含 Microsoft 365 的组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="9168c-523">是的，可以在没有 Microsoft 365 组的情况下创建 Yammer 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="9168c-524">如果 Yammer 平台未连接到 Microsoft 365 组，或者用户不能创建 Microsoft 365 组，则在没有 Microsoft 365 组关联的情况下创建 Yammer 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="9168c-525">**每个 Microsoft 365 组是否可以有多个 Yammer 组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="9168c-526">不是，Yammer 组和 Microsoft 365 组之间的关系为1:1。</span><span class="sxs-lookup"><span data-stu-id="9168c-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="9168c-527">**Yammer 组是否可以与多个 Microsoft 365 组关联？**</span><span class="sxs-lookup"><span data-stu-id="9168c-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="9168c-528">不能，Yammer 组只能与一个 Microsoft 365 组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="9168c-529">可以与其他 Yammer 组共享帖子或将其移至其他 Yammer 组。</span><span class="sxs-lookup"><span data-stu-id="9168c-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="9168c-530">**Yammer 组与 Microsoft 365 组的关联是否可以更改？**</span><span class="sxs-lookup"><span data-stu-id="9168c-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="9168c-531">否，Yammer 组只能与最初与之关联的 Microsoft 365 组相关联。</span><span class="sxs-lookup"><span data-stu-id="9168c-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="9168c-532">**删除 Yammer 组是否删除了 Microsoft 365 组？**</span><span class="sxs-lookup"><span data-stu-id="9168c-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="9168c-533">是，删除 Yammer 中的组将删除相关的 Microsoft 组和与组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="9168c-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9168c-534">相关主题</span><span class="sxs-lookup"><span data-stu-id="9168c-534">Related topics</span></span>

[<span data-ttu-id="9168c-535">协作治理规划分步</span><span class="sxs-lookup"><span data-stu-id="9168c-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="9168c-536">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="9168c-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

