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
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921020"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="3b575-103">组服务交互</span><span class="sxs-lookup"><span data-stu-id="3b575-103">Groups services interactions</span></span>

<span data-ttu-id="3b575-104">Microsoft 365 组为 Microsoft 365 平台中的许多服务和工作负载提供了一个常见结构，为最终用户提供连接体验。</span><span class="sxs-lookup"><span data-stu-id="3b575-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="3b575-105">Microsoft 365 组的核心是提供：</span><span class="sxs-lookup"><span data-stu-id="3b575-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="3b575-106">管理 Azure AD (成员身份) </span><span class="sxs-lookup"><span data-stu-id="3b575-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="3b575-107">Exchange 邮箱、Microsoft Teams、Yammer (邮件和对话) </span><span class="sxs-lookup"><span data-stu-id="3b575-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="3b575-108">用于将文件存储在 SharePoint () </span><span class="sxs-lookup"><span data-stu-id="3b575-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="3b575-109">计划 Exchange (日历) </span><span class="sxs-lookup"><span data-stu-id="3b575-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="3b575-110">用于捕获 OneNote (笔记的) </span><span class="sxs-lookup"><span data-stu-id="3b575-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="3b575-111">在组创建时，还会设置大量其他资源，但在首次从服务访问它们之前，它们不可见：</span><span class="sxs-lookup"><span data-stu-id="3b575-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="3b575-112">用于管理 Planner (组) </span><span class="sxs-lookup"><span data-stu-id="3b575-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="3b575-113">用于报告 Power BI (工作区) </span><span class="sxs-lookup"><span data-stu-id="3b575-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="3b575-114">Microsoft Stream (共享视频) </span><span class="sxs-lookup"><span data-stu-id="3b575-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="3b575-115">共享表单和表单 (区域) </span><span class="sxs-lookup"><span data-stu-id="3b575-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="3b575-116">在 Microsoft 365 中，其他服务能够与 Microsoft 365 组交互，以向组的成员提供其他特性和功能。</span><span class="sxs-lookup"><span data-stu-id="3b575-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="3b575-117">例如：</span><span class="sxs-lookup"><span data-stu-id="3b575-117">Examples of this include:</span></span>

- <span data-ttu-id="3b575-118">Power Apps for apps</span><span class="sxs-lookup"><span data-stu-id="3b575-118">Power Apps for apps</span></span>
- <span data-ttu-id="3b575-119">工作流的 Power Automate</span><span class="sxs-lookup"><span data-stu-id="3b575-119">Power Automate for workflows</span></span>
- <span data-ttu-id="3b575-120">Project 网页和基于瀑布的项目管理路线图</span><span class="sxs-lookup"><span data-stu-id="3b575-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="3b575-121">用于基于频道的对话的 Teams</span><span class="sxs-lookup"><span data-stu-id="3b575-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="3b575-122">Yammer for communities for interest</span><span class="sxs-lookup"><span data-stu-id="3b575-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="3b575-123">用户与组的交互</span><span class="sxs-lookup"><span data-stu-id="3b575-123">User interactions with groups</span></span>

<span data-ttu-id="3b575-124">管理员和最终用户可以通过各种界面创建和管理 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="3b575-125">管理体验</span><span class="sxs-lookup"><span data-stu-id="3b575-125">Administrative experiences</span></span>

<span data-ttu-id="3b575-126">管理员可以从多个工作负载管理中心、支持脚本的命令行界面以及与 Graph API 交互的自定义生成应用创建和管理 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="3b575-127">唯一的例外是 Yammer 组，必须从 Yammer Web 界面内创建组。</span><span class="sxs-lookup"><span data-stu-id="3b575-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="3b575-128">**相关设置**</span><span class="sxs-lookup"><span data-stu-id="3b575-128">**Related settings**</span></span>

<span data-ttu-id="3b575-129">在可以管理组设置的各种管理界面中，存在一些应注意的重叠。</span><span class="sxs-lookup"><span data-stu-id="3b575-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="3b575-130">**Microsoft 365 管理中心**</span><span class="sxs-lookup"><span data-stu-id="3b575-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="3b575-131">在 Microsoft 365 管理中心中，默认情况下启用对组的来宾访问，以及允许所有者添加来宾的能力。</span><span class="sxs-lookup"><span data-stu-id="3b575-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="3b575-132">此管理中心不再对组提供组织级别控制。</span><span class="sxs-lookup"><span data-stu-id="3b575-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="3b575-133">**Azure AD 管理中心**</span><span class="sxs-lookup"><span data-stu-id="3b575-133">**Azure AD admin center**</span></span>

<span data-ttu-id="3b575-134">Azure AD 管理中心控制用户是否可以在 Azure 门户创建组或分配所有者，以及过期和命名策略设置。</span><span class="sxs-lookup"><span data-stu-id="3b575-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="3b575-135">管理中心还提供了一些除 Microsoft 365 管理中心之外的来宾邀请控制措施，例如限制非所有者是否可以邀请来宾的能力</span><span class="sxs-lookup"><span data-stu-id="3b575-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="3b575-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="3b575-136">**SharePoint**</span></span>

<span data-ttu-id="3b575-137">SharePoint 网站使用所有者、成员和访问者安全组创建，前两个安全组与 Microsoft 365 组对应方匹配。</span><span class="sxs-lookup"><span data-stu-id="3b575-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="3b575-138">虽然 SharePoint Online 网站的成员身份通常由关联的 Microsoft 365 组管理，但它不是双向关系。</span><span class="sxs-lookup"><span data-stu-id="3b575-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="3b575-139">对 Microsoft 365 组级别的成员身份的任何更改都反映在 SharePoint 中，但如果 SharePoint 组的成员身份发生更改，则这不会反映在 Microsoft 365 组中。</span><span class="sxs-lookup"><span data-stu-id="3b575-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="3b575-140">用户体验</span><span class="sxs-lookup"><span data-stu-id="3b575-140">User experiences</span></span>

<span data-ttu-id="3b575-141">最终用户可以从 Microsoft 365 中的一些服务创建组，在另外一些服务中，他们只能与组共享。</span><span class="sxs-lookup"><span data-stu-id="3b575-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="3b575-142">以下服务允许最终用户创建组：</span><span class="sxs-lookup"><span data-stu-id="3b575-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="3b575-143">Outlook Planner Project 网页 SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="3b575-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="3b575-144">**组创建限制**</span><span class="sxs-lookup"><span data-stu-id="3b575-144">**Restriction of group creation**</span></span>

<span data-ttu-id="3b575-145">控制团队的激增的一种常见方法是限制哪些用户可以创建团队。</span><span class="sxs-lookup"><span data-stu-id="3b575-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="3b575-146">这仅可通过限制组的创建完成。</span><span class="sxs-lookup"><span data-stu-id="3b575-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="3b575-147">这样做会影响从最终用户可能需要的其他服务创建组的能力。</span><span class="sxs-lookup"><span data-stu-id="3b575-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="3b575-148">Microsoft 365 组不支持限制从某些应用或服务创建组，同时允许其他应用或服务创建组。</span><span class="sxs-lookup"><span data-stu-id="3b575-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="3b575-149">组创建限制的体验因应用和服务而异：</span><span class="sxs-lookup"><span data-stu-id="3b575-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="3b575-150">应用或服务</span><span class="sxs-lookup"><span data-stu-id="3b575-150">App or service</span></span>|<span data-ttu-id="3b575-151">体验</span><span class="sxs-lookup"><span data-stu-id="3b575-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="3b575-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="3b575-152">Outlook</span></span>|<span data-ttu-id="3b575-153">**"新建组** "选项已从"人员"页面的"新建"菜单中删除</span><span class="sxs-lookup"><span data-stu-id="3b575-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="3b575-154">规划器</span><span class="sxs-lookup"><span data-stu-id="3b575-154">Planner</span></span>|<span data-ttu-id="3b575-155">**新** 计划说明组创建已关闭，并提供将计划添加到现有组</span><span class="sxs-lookup"><span data-stu-id="3b575-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="3b575-156">Project 网页和路线图</span><span class="sxs-lookup"><span data-stu-id="3b575-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="3b575-157">**"创建组** "菜单说明组创建受到限制，并建议使用现有组。</span><span class="sxs-lookup"><span data-stu-id="3b575-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="3b575-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b575-158">SharePoint</span></span>|<span data-ttu-id="3b575-159">仍然能够创建未连接到组的工作组网站。</span><span class="sxs-lookup"><span data-stu-id="3b575-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="3b575-160">Stream</span><span class="sxs-lookup"><span data-stu-id="3b575-160">Stream</span></span>|<span data-ttu-id="3b575-161">**"** 组"选项不会显示在"创建" **菜单下**。</span><span class="sxs-lookup"><span data-stu-id="3b575-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="3b575-162">Teams</span><span class="sxs-lookup"><span data-stu-id="3b575-162">Teams</span></span>|<span data-ttu-id="3b575-163">用户不能使用新组创建团队，但仍可以创建利用现有组的团队。</span><span class="sxs-lookup"><span data-stu-id="3b575-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="3b575-164">**"创建团队"** 按钮将替换为"**从组创建团队"。**</span><span class="sxs-lookup"><span data-stu-id="3b575-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="3b575-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="3b575-165">Yammer</span></span>|<span data-ttu-id="3b575-166">**"创建组"** 选项已从主"组/社区"导航中删除。</span><span class="sxs-lookup"><span data-stu-id="3b575-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="3b575-167">服务与组的交互</span><span class="sxs-lookup"><span data-stu-id="3b575-167">Services interactions with groups</span></span>

<span data-ttu-id="3b575-168">请参阅 Microsoft 365 中的组海报，了解不同类型的组、如何创建和管理这些组，以及一些管理建议。</span><span class="sxs-lookup"><span data-stu-id="3b575-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="3b575-169">[![组信息图的缩略图](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="3b575-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="3b575-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="3b575-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="3b575-171">下表概述了 Microsoft 365 组与各种服务的交互：</span><span class="sxs-lookup"><span data-stu-id="3b575-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="3b575-172">产品</span><span class="sxs-lookup"><span data-stu-id="3b575-172">Product</span></span>|<span data-ttu-id="3b575-173">功能</span><span class="sxs-lookup"><span data-stu-id="3b575-173">Features</span></span>|<span data-ttu-id="3b575-174">服务是否</span><span class="sxs-lookup"><span data-stu-id="3b575-174">Does the service</span></span><br><span data-ttu-id="3b575-175">是否存在没有组？</span><span class="sxs-lookup"><span data-stu-id="3b575-175">exist without a group?</span></span>|<span data-ttu-id="3b575-176">服务能否</span><span class="sxs-lookup"><span data-stu-id="3b575-176">Can the service</span></span><br><span data-ttu-id="3b575-177">创建组</span><span class="sxs-lookup"><span data-stu-id="3b575-177">create a group?</span></span>|<span data-ttu-id="3b575-178">是否删除</span><span class="sxs-lookup"><span data-stu-id="3b575-178">Does deleting the</span></span><br><span data-ttu-id="3b575-179">实例删除组</span><span class="sxs-lookup"><span data-stu-id="3b575-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="3b575-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b575-180">Azure AD</span></span>|<span data-ttu-id="3b575-181">成员身份、组控件、来宾</span><span class="sxs-lookup"><span data-stu-id="3b575-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="3b575-182">是</span><span class="sxs-lookup"><span data-stu-id="3b575-182">Yes</span></span>|<span data-ttu-id="3b575-183">是</span><span class="sxs-lookup"><span data-stu-id="3b575-183">Yes</span></span>|<span data-ttu-id="3b575-184">是</span><span class="sxs-lookup"><span data-stu-id="3b575-184">Yes</span></span>|
|<span data-ttu-id="3b575-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="3b575-185">Exchange</span></span>|<span data-ttu-id="3b575-186">日历、邮箱</span><span class="sxs-lookup"><span data-stu-id="3b575-186">Calendar, mailbox</span></span>|<span data-ttu-id="3b575-187">是</span><span class="sxs-lookup"><span data-stu-id="3b575-187">Yes</span></span>|<span data-ttu-id="3b575-188">是</span><span class="sxs-lookup"><span data-stu-id="3b575-188">Yes</span></span>|<span data-ttu-id="3b575-189">是</span><span class="sxs-lookup"><span data-stu-id="3b575-189">Yes</span></span>|
|<span data-ttu-id="3b575-190">Forms</span><span class="sxs-lookup"><span data-stu-id="3b575-190">Forms</span></span>|<span data-ttu-id="3b575-191">表单</span><span class="sxs-lookup"><span data-stu-id="3b575-191">Form</span></span>|<span data-ttu-id="3b575-192">是</span><span class="sxs-lookup"><span data-stu-id="3b575-192">Yes</span></span>|<span data-ttu-id="3b575-193">否</span><span class="sxs-lookup"><span data-stu-id="3b575-193">No</span></span>|<span data-ttu-id="3b575-194">否</span><span class="sxs-lookup"><span data-stu-id="3b575-194">No</span></span>|
|<span data-ttu-id="3b575-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="3b575-195">OneNote</span></span>|<span data-ttu-id="3b575-196">Notebook</span><span class="sxs-lookup"><span data-stu-id="3b575-196">Notebook</span></span>|<span data-ttu-id="3b575-197">是</span><span class="sxs-lookup"><span data-stu-id="3b575-197">Yes</span></span>|<span data-ttu-id="3b575-198">否</span><span class="sxs-lookup"><span data-stu-id="3b575-198">No</span></span>|<span data-ttu-id="3b575-199">否</span><span class="sxs-lookup"><span data-stu-id="3b575-199">No</span></span>|
|<span data-ttu-id="3b575-200">规划器</span><span class="sxs-lookup"><span data-stu-id="3b575-200">Planner</span></span>|<span data-ttu-id="3b575-201">任务板</span><span class="sxs-lookup"><span data-stu-id="3b575-201">Task board</span></span>|<span data-ttu-id="3b575-202">否</span><span class="sxs-lookup"><span data-stu-id="3b575-202">No</span></span>|<span data-ttu-id="3b575-203">是</span><span class="sxs-lookup"><span data-stu-id="3b575-203">Yes</span></span>|<span data-ttu-id="3b575-204">是</span><span class="sxs-lookup"><span data-stu-id="3b575-204">Yes</span></span>|
|<span data-ttu-id="3b575-205">Power Apps 应用</span><span class="sxs-lookup"><span data-stu-id="3b575-205">Power Apps app</span></span>|<span data-ttu-id="3b575-206">应用</span><span class="sxs-lookup"><span data-stu-id="3b575-206">App</span></span>|<span data-ttu-id="3b575-207">是</span><span class="sxs-lookup"><span data-stu-id="3b575-207">Yes</span></span>|<span data-ttu-id="3b575-208">否</span><span class="sxs-lookup"><span data-stu-id="3b575-208">No</span></span>|<span data-ttu-id="3b575-209">否</span><span class="sxs-lookup"><span data-stu-id="3b575-209">No</span></span>|
|<span data-ttu-id="3b575-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="3b575-210">Power Automate</span></span>|<span data-ttu-id="3b575-211">工作流</span><span class="sxs-lookup"><span data-stu-id="3b575-211">Workflow</span></span>|<span data-ttu-id="3b575-212">是</span><span class="sxs-lookup"><span data-stu-id="3b575-212">Yes</span></span>|<span data-ttu-id="3b575-213">否</span><span class="sxs-lookup"><span data-stu-id="3b575-213">No</span></span>|<span data-ttu-id="3b575-214">否</span><span class="sxs-lookup"><span data-stu-id="3b575-214">No</span></span>|
|<span data-ttu-id="3b575-215">Power BI (经典) </span><span class="sxs-lookup"><span data-stu-id="3b575-215">Power BI (classic)</span></span>|<span data-ttu-id="3b575-216">工作区</span><span class="sxs-lookup"><span data-stu-id="3b575-216">Workspace</span></span>|<span data-ttu-id="3b575-217">否</span><span class="sxs-lookup"><span data-stu-id="3b575-217">No</span></span>|<span data-ttu-id="3b575-218">是</span><span class="sxs-lookup"><span data-stu-id="3b575-218">Yes</span></span>|<span data-ttu-id="3b575-219">是</span><span class="sxs-lookup"><span data-stu-id="3b575-219">Yes</span></span>|
|<span data-ttu-id="3b575-220">Power BI (新增) </span><span class="sxs-lookup"><span data-stu-id="3b575-220">Power BI (new)</span></span>|<span data-ttu-id="3b575-221">工作区</span><span class="sxs-lookup"><span data-stu-id="3b575-221">Workspace</span></span>|<span data-ttu-id="3b575-222">是</span><span class="sxs-lookup"><span data-stu-id="3b575-222">Yes</span></span>|<span data-ttu-id="3b575-223">否</span><span class="sxs-lookup"><span data-stu-id="3b575-223">No</span></span>|<span data-ttu-id="3b575-224">是</span><span class="sxs-lookup"><span data-stu-id="3b575-224">Yes</span></span>|
|<span data-ttu-id="3b575-225">Project 网页版</span><span class="sxs-lookup"><span data-stu-id="3b575-225">Project for the web</span></span>|<span data-ttu-id="3b575-226">项目计划</span><span class="sxs-lookup"><span data-stu-id="3b575-226">Project plan</span></span>|<span data-ttu-id="3b575-227">是</span><span class="sxs-lookup"><span data-stu-id="3b575-227">Yes</span></span>|<span data-ttu-id="3b575-228">是</span><span class="sxs-lookup"><span data-stu-id="3b575-228">Yes</span></span>|<span data-ttu-id="3b575-229">否</span><span class="sxs-lookup"><span data-stu-id="3b575-229">No</span></span>|
|<span data-ttu-id="3b575-230">路线图</span><span class="sxs-lookup"><span data-stu-id="3b575-230">Roadmap</span></span>|<span data-ttu-id="3b575-231">路线图</span><span class="sxs-lookup"><span data-stu-id="3b575-231">Roadmap</span></span>|<span data-ttu-id="3b575-232">是</span><span class="sxs-lookup"><span data-stu-id="3b575-232">Yes</span></span>|<span data-ttu-id="3b575-233">是</span><span class="sxs-lookup"><span data-stu-id="3b575-233">Yes</span></span>|<span data-ttu-id="3b575-234">否</span><span class="sxs-lookup"><span data-stu-id="3b575-234">No</span></span>|
|<span data-ttu-id="3b575-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b575-235">SharePoint</span></span>|<span data-ttu-id="3b575-236">Site</span><span class="sxs-lookup"><span data-stu-id="3b575-236">Site</span></span>|<span data-ttu-id="3b575-237">是</span><span class="sxs-lookup"><span data-stu-id="3b575-237">Yes</span></span>|<span data-ttu-id="3b575-238">是</span><span class="sxs-lookup"><span data-stu-id="3b575-238">Yes</span></span>|<span data-ttu-id="3b575-239">是</span><span class="sxs-lookup"><span data-stu-id="3b575-239">Yes</span></span>|
|<span data-ttu-id="3b575-240">Stream</span><span class="sxs-lookup"><span data-stu-id="3b575-240">Stream</span></span>|<span data-ttu-id="3b575-241">频道、视频</span><span class="sxs-lookup"><span data-stu-id="3b575-241">Channel, video</span></span>|<span data-ttu-id="3b575-242">是</span><span class="sxs-lookup"><span data-stu-id="3b575-242">Yes</span></span>|<span data-ttu-id="3b575-243">是</span><span class="sxs-lookup"><span data-stu-id="3b575-243">Yes</span></span>|<span data-ttu-id="3b575-244">是</span><span class="sxs-lookup"><span data-stu-id="3b575-244">Yes</span></span>|
|<span data-ttu-id="3b575-245">Teams</span><span class="sxs-lookup"><span data-stu-id="3b575-245">Teams</span></span>|<span data-ttu-id="3b575-246">团队</span><span class="sxs-lookup"><span data-stu-id="3b575-246">Team</span></span>|<span data-ttu-id="3b575-247">否</span><span class="sxs-lookup"><span data-stu-id="3b575-247">No</span></span>|<span data-ttu-id="3b575-248">是</span><span class="sxs-lookup"><span data-stu-id="3b575-248">Yes</span></span>|<span data-ttu-id="3b575-249">是</span><span class="sxs-lookup"><span data-stu-id="3b575-249">Yes</span></span>|
|<span data-ttu-id="3b575-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="3b575-250">Yammer</span></span>|<span data-ttu-id="3b575-251">组</span><span class="sxs-lookup"><span data-stu-id="3b575-251">Group</span></span>|<span data-ttu-id="3b575-252">是</span><span class="sxs-lookup"><span data-stu-id="3b575-252">Yes</span></span>|<span data-ttu-id="3b575-253">是</span><span class="sxs-lookup"><span data-stu-id="3b575-253">Yes</span></span>|<span data-ttu-id="3b575-254">是</span><span class="sxs-lookup"><span data-stu-id="3b575-254">Yes</span></span>|

<span data-ttu-id="3b575-255">虽然上表提供了与 Microsoft 365 服务的组交互的简要概述，但您应该了解许多细微差别和细节。</span><span class="sxs-lookup"><span data-stu-id="3b575-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="3b575-256">以下各节将深入探讨特定的工作负荷及其与组的交互。</span><span class="sxs-lookup"><span data-stu-id="3b575-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="3b575-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b575-257">Azure AD</span></span>

<span data-ttu-id="3b575-258">Azure AD 在 Microsoft 365 中提供基础标识管理功能。</span><span class="sxs-lookup"><span data-stu-id="3b575-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="3b575-259">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3b575-260">组成员身份</span><span class="sxs-lookup"><span data-stu-id="3b575-260">Group membership</span></span>
- <span data-ttu-id="3b575-261">命名策略</span><span class="sxs-lookup"><span data-stu-id="3b575-261">Naming policy</span></span>
- <span data-ttu-id="3b575-262">过期策略</span><span class="sxs-lookup"><span data-stu-id="3b575-262">Expiration policy</span></span>
- <span data-ttu-id="3b575-263">来宾</span><span class="sxs-lookup"><span data-stu-id="3b575-263">Guests</span></span>
- <span data-ttu-id="3b575-264">组创建限制</span><span class="sxs-lookup"><span data-stu-id="3b575-264">Restriction of Group creation</span></span>

<span data-ttu-id="3b575-265">**Azure AD 能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="3b575-266">可以，可通过管理 Web 门户、PowerShell 或 Graph API 从 Azure AD 创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="3b575-267">**Azure AD 是否存在没有组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="3b575-268">是的，Azure AD 执行大量与 Microsoft 365 组无关系的服务。</span><span class="sxs-lookup"><span data-stu-id="3b575-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="3b575-269">每个 Microsoft 365 组都表示为 Azure AD 中的对象。</span><span class="sxs-lookup"><span data-stu-id="3b575-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="3b575-270">**每个组能否有多个 Azure AD 实例？**</span><span class="sxs-lookup"><span data-stu-id="3b575-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="3b575-271">否，只有一个 Azure AD 实例。</span><span class="sxs-lookup"><span data-stu-id="3b575-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="3b575-272">**Azure AD 能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="3b575-273">是的，因为 Azure AD 是提供组成员身份服务的基础平台。</span><span class="sxs-lookup"><span data-stu-id="3b575-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="3b575-274">**Azure AD 与组关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="3b575-275">否，Azure AD 是存在组的基础平台。</span><span class="sxs-lookup"><span data-stu-id="3b575-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="3b575-276">**删除实例是否删除组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="3b575-277">在 Azure AD 中删除组将删除相关的组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="3b575-278">Teams</span><span class="sxs-lookup"><span data-stu-id="3b575-278">Teams</span></span>

<span data-ttu-id="3b575-279">Teams 是一个以聊天为中心的工作区，旨在通过提供与各种 Microsoft 和第三方服务交互的单数界面来增强协作。</span><span class="sxs-lookup"><span data-stu-id="3b575-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="3b575-280">默认情况下，创建团队时，与 Microsoft 365 组关联的邮箱和日历在 Exchange 和 Outlook 中的全局地址列表中都处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="3b575-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="3b575-281">如果用户希望在同一 Microsoft 365 组上同时使用 Outlook 和 Teams，则管理员可以手动覆盖此选项。</span><span class="sxs-lookup"><span data-stu-id="3b575-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="3b575-282">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3b575-283">对话</span><span class="sxs-lookup"><span data-stu-id="3b575-283">Conversations</span></span>
- <span data-ttu-id="3b575-284">频道&选项卡</span><span class="sxs-lookup"><span data-stu-id="3b575-284">Channels & tabs</span></span>
- <span data-ttu-id="3b575-285">会议</span><span class="sxs-lookup"><span data-stu-id="3b575-285">Meetings</span></span>

<span data-ttu-id="3b575-286">**Teams 能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="3b575-287">是的，创建新团队将创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="3b575-288">也可以为当前没有团队的现有组创建团队。</span><span class="sxs-lookup"><span data-stu-id="3b575-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="3b575-289">**团队是否存在没有组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="3b575-290">否，没有组，团队不可能存在。</span><span class="sxs-lookup"><span data-stu-id="3b575-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="3b575-291">**每个组可以有多个团队吗？**</span><span class="sxs-lookup"><span data-stu-id="3b575-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="3b575-292">否，团队和组之间的关系是 1：1。</span><span class="sxs-lookup"><span data-stu-id="3b575-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="3b575-293">**团队能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-294">否，团队本身只能与一个组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="3b575-295">**团队与组关联能否发生变化？**</span><span class="sxs-lookup"><span data-stu-id="3b575-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="3b575-296">否，团队只能与最初关联的组相关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="3b575-297">**删除团队是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="3b575-298">可以，删除 Microsoft Teams 中的团队将删除组、组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="3b575-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="3b575-299">Exchange</span></span>

<span data-ttu-id="3b575-300">Exchange Online 提供消息传递、日历、联系人和相关功能。</span><span class="sxs-lookup"><span data-stu-id="3b575-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="3b575-301">在组上下文中，仅关联单个资源，而不是整个服务实例。</span><span class="sxs-lookup"><span data-stu-id="3b575-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="3b575-302">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3b575-303">邮箱和日历</span><span class="sxs-lookup"><span data-stu-id="3b575-303">Mailbox and calendar</span></span>
- <span data-ttu-id="3b575-304">能够向所有组的成员发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="3b575-304">Ability to email all Group members</span></span>
- <span data-ttu-id="3b575-305">存储 Teams 频道对话以用于电子数据展示，Planner 评论</span><span class="sxs-lookup"><span data-stu-id="3b575-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="3b575-306">**Exchange 可以创建组吗？**</span><span class="sxs-lookup"><span data-stu-id="3b575-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="3b575-307">可以，可以同时从 Exchange Online 管理中心以及 Outlook 创建组。</span><span class="sxs-lookup"><span data-stu-id="3b575-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="3b575-308">您还可以将 Exchange 通讯组列表转换为 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="3b575-309">**Exchange 是否存在没有组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="3b575-310">是的，Exchange Online 提供了许多服务，包括共享邮箱和日历，没有任何组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="3b575-311">**每个组能否有多个 Exchange 邮箱或日历实例？**</span><span class="sxs-lookup"><span data-stu-id="3b575-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="3b575-312">否，组只能有一个 Exchange Online 邮箱和日历。</span><span class="sxs-lookup"><span data-stu-id="3b575-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="3b575-313">**Exchange 邮箱和日历能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-314">否，邮箱和日历与组具有 1：1 关系。</span><span class="sxs-lookup"><span data-stu-id="3b575-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="3b575-315">可以与其他用户或组共享邮箱，但这不会建立任何形式的服务关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="3b575-316">**Exchange 邮箱或日历与组之间的关联是否可更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="3b575-317">否，不能将邮箱和日历更改为其他组。</span><span class="sxs-lookup"><span data-stu-id="3b575-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="3b575-318">但是，内容可以在 Outlook 中或通过使用第三方工具从一个邮箱移动到另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="3b575-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="3b575-319">**删除邮箱是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="3b575-320">可以，删除 Exchange 中的邮箱将删除组以及组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="3b575-321">Forms</span><span class="sxs-lookup"><span data-stu-id="3b575-321">Forms</span></span>

<span data-ttu-id="3b575-322">表单提供基于 Web 的调查和测验。</span><span class="sxs-lookup"><span data-stu-id="3b575-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="3b575-323">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="3b575-324">表单的所有权</span><span class="sxs-lookup"><span data-stu-id="3b575-324">Ownership of forms</span></span>

<span data-ttu-id="3b575-325">**窗体可以创建组吗？**</span><span class="sxs-lookup"><span data-stu-id="3b575-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="3b575-326">否，Forms 无法创建组。</span><span class="sxs-lookup"><span data-stu-id="3b575-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="3b575-327">**是否存在没有组的表单？**</span><span class="sxs-lookup"><span data-stu-id="3b575-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="3b575-328">可以，可以直接在最终用户帐户中创建调查和测验。</span><span class="sxs-lookup"><span data-stu-id="3b575-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="3b575-329">**每个组可以有多个表单吗？**</span><span class="sxs-lookup"><span data-stu-id="3b575-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="3b575-330">可以，可以有多个表单与一个组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="3b575-331">**表单能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-332">否，表单只能与单个组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="3b575-333">**表单与组的关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="3b575-334">否，一旦表单与直接在内部 (组关联，或者从单个组传输的所有权) 无法移动到另一个组。</span><span class="sxs-lookup"><span data-stu-id="3b575-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="3b575-335">**删除表单是否将删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="3b575-336">否，不能从 Forms 界面中删除组，只能从单个窗体中删除组。</span><span class="sxs-lookup"><span data-stu-id="3b575-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="3b575-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="3b575-337">OneNote</span></span>

<span data-ttu-id="3b575-338">OneNote 是数字笔记本应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b575-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="3b575-339">使用组创建的 OneNote 笔记本是关联的 SharePoint 网站中的文件，而不是组连接的服务。</span><span class="sxs-lookup"><span data-stu-id="3b575-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="3b575-340">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="3b575-341">共享笔记本 (组关联的 SharePoint 库库中) </span><span class="sxs-lookup"><span data-stu-id="3b575-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="3b575-342">**OneNote 能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="3b575-343">否，OneNote 应用程序无法创建组。</span><span class="sxs-lookup"><span data-stu-id="3b575-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="3b575-344">**是否存在没有组的 OneNote 笔记本？**</span><span class="sxs-lookup"><span data-stu-id="3b575-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="3b575-345">可以，笔记本可以直接在 OneDrive 或其他共享位置创建。</span><span class="sxs-lookup"><span data-stu-id="3b575-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="3b575-346">**每个组能否有多个 OneNote 笔记本？**</span><span class="sxs-lookup"><span data-stu-id="3b575-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="3b575-347">是，默认情况下会创建一个笔记本，可以添加其他笔记本，但是从组关联的服务到 OneNote 的任何链接将始终转到默认笔记本。</span><span class="sxs-lookup"><span data-stu-id="3b575-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="3b575-348">**OneNote 笔记本能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-349">否，笔记本存储在与组关联的 SharePoint 网站库中，并且从各种界面链接。</span><span class="sxs-lookup"><span data-stu-id="3b575-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="3b575-350">但是，它可以与其他组共享，方式与个人共享的方式相同。</span><span class="sxs-lookup"><span data-stu-id="3b575-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="3b575-351">**笔记本与组关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="3b575-352">否，笔记本本身与组关联，并且可以从其他已连接组的服务直接访问，但是内容可以从 OneNote 应用程序内的一个笔记本移动到另一个笔记本。</span><span class="sxs-lookup"><span data-stu-id="3b575-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="3b575-353">**删除笔记本是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="3b575-354">否，但是，如果删除了 OneNote 笔记本，则某些组关联的服务中可能会断开链接。</span><span class="sxs-lookup"><span data-stu-id="3b575-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="3b575-355">规划器</span><span class="sxs-lookup"><span data-stu-id="3b575-355">Planner</span></span>

<span data-ttu-id="3b575-356">Planner 是轻型组任务管理服务。</span><span class="sxs-lookup"><span data-stu-id="3b575-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="3b575-357">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="3b575-358">用于管理组任务的板</span><span class="sxs-lookup"><span data-stu-id="3b575-358">Board for managing group tasks</span></span>

<span data-ttu-id="3b575-359">**Planner 可以创建组吗？**</span><span class="sxs-lookup"><span data-stu-id="3b575-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="3b575-360">是的，创建计划将创建新组。</span><span class="sxs-lookup"><span data-stu-id="3b575-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="3b575-361">**Planner 板是否存在没有组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="3b575-362">否，计划必须与组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="3b575-363">**每个组能否有多个计划？**</span><span class="sxs-lookup"><span data-stu-id="3b575-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="3b575-364">可以，每个组可以有多个计划。</span><span class="sxs-lookup"><span data-stu-id="3b575-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="3b575-365">**计划能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-366">否，计划仅依赖组成员身份来确定访问权限。</span><span class="sxs-lookup"><span data-stu-id="3b575-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="3b575-367">**计划与组关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="3b575-368">否，但是复制计划会创建新组。</span><span class="sxs-lookup"><span data-stu-id="3b575-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="3b575-369">由任何其他应用程序创建的组不会自动显示在用户的 Planner 中。</span><span class="sxs-lookup"><span data-stu-id="3b575-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="3b575-370">若要最初访问该板，他们将需要从另一个基于组的界面（如 Outlook）打开它。</span><span class="sxs-lookup"><span data-stu-id="3b575-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="3b575-371">**删除计划是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="3b575-372">可以，删除计划将删除组和组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="3b575-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="3b575-373">Power Apps</span></span>

<span data-ttu-id="3b575-374">Power Apps 提供了一个画布，用于应用开发，而无需使用代码。</span><span class="sxs-lookup"><span data-stu-id="3b575-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="3b575-375">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3b575-376">可以与要运行和修改的组共享应用</span><span class="sxs-lookup"><span data-stu-id="3b575-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="3b575-377">**Power Apps 能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="3b575-378">否，Power Apps 无法创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="3b575-379">**是否存在没有组的 Power Apps？**</span><span class="sxs-lookup"><span data-stu-id="3b575-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="3b575-380">可以，应用可以在 Power Apps 中创建，并驻留在创建者帐户内，直到共享或发布。</span><span class="sxs-lookup"><span data-stu-id="3b575-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="3b575-381">**每个组能否有多个应用？**</span><span class="sxs-lookup"><span data-stu-id="3b575-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="3b575-382">可以，可以有多个应用与一个组共享。</span><span class="sxs-lookup"><span data-stu-id="3b575-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="3b575-383">**应用能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-384">是，可以与多个组共享应用。</span><span class="sxs-lookup"><span data-stu-id="3b575-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="3b575-385">**应用与组关联能否发生变化？**</span><span class="sxs-lookup"><span data-stu-id="3b575-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="3b575-386">可以，因为 Power Apps 和 Microsoft 365 组之间的关联只是共享 ，所以应用仍与创建者驻留在一起。</span><span class="sxs-lookup"><span data-stu-id="3b575-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b575-387">[必须先启用安全组，然后才能与组共享应用](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="3b575-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="3b575-388">**删除应用是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="3b575-389">否，除了与应用共享外，这些应用不会连接到组。</span><span class="sxs-lookup"><span data-stu-id="3b575-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="3b575-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="3b575-390">Power Automate</span></span>

<span data-ttu-id="3b575-391">Power Automate (以前称为 Microsoft Flow) 提供工作流和自动化服务。</span><span class="sxs-lookup"><span data-stu-id="3b575-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="3b575-392">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="3b575-393">工作流可以与要运行和修改的组共享。</span><span class="sxs-lookup"><span data-stu-id="3b575-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="3b575-394">**Power Automate 能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="3b575-395">否，Power Automate 无法在与一个组关联的上下文中创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="3b575-396">但是，可以创建执行各种操作（如创建 Azure AD 安全组或更新 Microsoft 365 组的成员身份）的流。</span><span class="sxs-lookup"><span data-stu-id="3b575-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="3b575-397">**是否存在没有组的流？**</span><span class="sxs-lookup"><span data-stu-id="3b575-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="3b575-398">是，可以在 Power Automate 中创建流，并驻留在创建者帐户内，直到共享或发布。</span><span class="sxs-lookup"><span data-stu-id="3b575-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="3b575-399">**每个组能否有多个流？**</span><span class="sxs-lookup"><span data-stu-id="3b575-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="3b575-400">可以，可以与一个组共享多个流。</span><span class="sxs-lookup"><span data-stu-id="3b575-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="3b575-401">**流能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-402">是，可以与多个组共享流。</span><span class="sxs-lookup"><span data-stu-id="3b575-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="3b575-403">**流与组关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="3b575-404">可以，因为 Power Automate 和 Microsoft 365 组之间的关联只是共享，所以流仍由创建者驻留。</span><span class="sxs-lookup"><span data-stu-id="3b575-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="3b575-405">**删除流是否删除组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="3b575-406">否，与 Power Apps 一样，流未连接到组，而不是与它们共享。</span><span class="sxs-lookup"><span data-stu-id="3b575-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="3b575-407">Power BI (经典) </span><span class="sxs-lookup"><span data-stu-id="3b575-407">Power BI (classic)</span></span>

<span data-ttu-id="3b575-408">Power BI 提供交互式数据驱动的仪表板和报告。</span><span class="sxs-lookup"><span data-stu-id="3b575-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="3b575-409">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="3b575-410">数据报告</span><span class="sxs-lookup"><span data-stu-id="3b575-410">Data reporting</span></span>

<span data-ttu-id="3b575-411">**Power BI 能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="3b575-412">是的，创建经典工作区将创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="3b575-413">**是否存在没有组的 Power BI 经典工作区？**</span><span class="sxs-lookup"><span data-stu-id="3b575-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="3b575-414">否 [，Power BI 中的经典工作区必须与组关联](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)。</span><span class="sxs-lookup"><span data-stu-id="3b575-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="3b575-415">**每个组能否有多个 Power BI 工作区？**</span><span class="sxs-lookup"><span data-stu-id="3b575-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="3b575-416">否，经典工作区和组之间的关系是 1：1。</span><span class="sxs-lookup"><span data-stu-id="3b575-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="3b575-417">**工作区能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-418">从技术上说，不是，虽然经典工作区是使用组创建的，但内容可以在组外部与用户和安全组共享。</span><span class="sxs-lookup"><span data-stu-id="3b575-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="3b575-419">**工作区与组关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="3b575-420">否，经典工作区本身与组相关联，但内容可以在 Power BI 界面中从一个工作区移动到另一个工作区，或者通过在本地导出内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="3b575-421">**删除工作区是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="3b575-422">可以，删除 Power BI 中的工作区将删除组和组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="3b575-423">Power BI (新增) </span><span class="sxs-lookup"><span data-stu-id="3b575-423">Power BI (new)</span></span>

<span data-ttu-id="3b575-424">Power BI 提供交互式数据驱动的仪表板和报告。</span><span class="sxs-lookup"><span data-stu-id="3b575-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="3b575-425">虽然在 Power BI 中创建新工作区不会创建 Microsoft 365 组，但通过任何其他方式创建组 (在 Power BI 中新建) 工作区。</span><span class="sxs-lookup"><span data-stu-id="3b575-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="3b575-426">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="3b575-427">数据报告</span><span class="sxs-lookup"><span data-stu-id="3b575-427">Data reporting</span></span>

<span data-ttu-id="3b575-428">**Power BI 能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="3b575-429">否，无法从新的 Power BI 界面创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="3b575-430">**是否存在没有组的新 Power BI 工作区？**</span><span class="sxs-lookup"><span data-stu-id="3b575-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="3b575-431">可以，有可能在 Power BI 中创建不与 Microsoft 365 组关联的报表和工作区。</span><span class="sxs-lookup"><span data-stu-id="3b575-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="3b575-432">**每个组能否有多个工作区？**</span><span class="sxs-lookup"><span data-stu-id="3b575-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="3b575-433">可以 [，Power BI 创建的多个工作区可以与单个组共享](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)。</span><span class="sxs-lookup"><span data-stu-id="3b575-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="3b575-434">**工作区能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-435">否，Power BI 创建的工作区只能与单个组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="3b575-436">**工作区与组关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="3b575-437">是，否。</span><span class="sxs-lookup"><span data-stu-id="3b575-437">Yes and no.</span></span> <span data-ttu-id="3b575-438">Power BI 创建的工作区一次只能与一个组关联，但随时都可以更改关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="3b575-439">在 Power BI 中由组创建的工作区将永久关联到该组。</span><span class="sxs-lookup"><span data-stu-id="3b575-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="3b575-440">**删除工作区是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="3b575-441">可以，删除 Power BI 中的工作区将删除组和组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="3b575-442">Project 网页版</span><span class="sxs-lookup"><span data-stu-id="3b575-442">Project for the web</span></span>

<span data-ttu-id="3b575-443">Project 网页页面提供创建项目计划、甘特图和路线图的能力。</span><span class="sxs-lookup"><span data-stu-id="3b575-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="3b575-444">为组提供的关键功能。</span><span class="sxs-lookup"><span data-stu-id="3b575-444">Key features provided to groups.</span></span>

- <span data-ttu-id="3b575-445">项目计划</span><span class="sxs-lookup"><span data-stu-id="3b575-445">Project plans</span></span>

<span data-ttu-id="3b575-446">**Project 网页应用能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="3b575-447">可以，可以直接从 Project 网页版创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="3b575-448">**项目是否存在没有组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="3b575-449">可以，项目可以在不与 Microsoft 365 组关联的情况下存在，但任务分配需要组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="3b575-450">**每个组能否有多个项目？**</span><span class="sxs-lookup"><span data-stu-id="3b575-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="3b575-451">可以，可以连接单个组中的多个项目。</span><span class="sxs-lookup"><span data-stu-id="3b575-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="3b575-452">**项目能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-453">否，项目只能与单个组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="3b575-454">**项目与组的关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="3b575-455">否，一旦建立与组的关联，它就无法更改。</span><span class="sxs-lookup"><span data-stu-id="3b575-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="3b575-456">**删除项目是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="3b575-457">否，在 Project 网页项目中删除项目不会删除该组。</span><span class="sxs-lookup"><span data-stu-id="3b575-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="3b575-458">路线图</span><span class="sxs-lookup"><span data-stu-id="3b575-458">Roadmap</span></span>

<span data-ttu-id="3b575-459">路线图提供了使用 Project 网页版和 Project Online 创建项目路线图的能力。</span><span class="sxs-lookup"><span data-stu-id="3b575-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="3b575-460">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3b575-461">项目路线图</span><span class="sxs-lookup"><span data-stu-id="3b575-461">Project roadmaps</span></span>

<span data-ttu-id="3b575-462">**路线图能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="3b575-463">可以，可以直接根据路线图创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="3b575-464">**路线图是否存在没有组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="3b575-465">可以，路线图可以在不与 Microsoft 365 组关联的情况下存在，但共享路线图需要组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="3b575-466">**每个组能否有多个路线图？**</span><span class="sxs-lookup"><span data-stu-id="3b575-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="3b575-467">可以，可将多个路线图连接到单个组。</span><span class="sxs-lookup"><span data-stu-id="3b575-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="3b575-468">**路线图能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-469">否，路线图只能与单个组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="3b575-470">**路线图与组关联能否发生变化？**</span><span class="sxs-lookup"><span data-stu-id="3b575-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="3b575-471">否，一旦建立与组的关联，它就无法更改。</span><span class="sxs-lookup"><span data-stu-id="3b575-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="3b575-472">**删除路线图是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="3b575-473">否，删除路线图不会删除该组。</span><span class="sxs-lookup"><span data-stu-id="3b575-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="3b575-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b575-474">SharePoint</span></span>

<span data-ttu-id="3b575-475">SharePoint 是基于 Web 的内容管理平台，可为许多 Microsoft 365 服务提供存储服务等。</span><span class="sxs-lookup"><span data-stu-id="3b575-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="3b575-476">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3b575-477">文档库</span><span class="sxs-lookup"><span data-stu-id="3b575-477">Document library</span></span>
- <span data-ttu-id="3b575-478">OneNote 笔记本存储库</span><span class="sxs-lookup"><span data-stu-id="3b575-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="3b575-479">存储 Teams Wiki 文件</span><span class="sxs-lookup"><span data-stu-id="3b575-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="3b575-480">**SharePoint 能否创建组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="3b575-481">可以，默认情况下，在 SharePoint 中创建团队网站将创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="3b575-482">还可以为现有网站创建组和（可选）团队。</span><span class="sxs-lookup"><span data-stu-id="3b575-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="3b575-483">**SharePoint 网站是否存在没有组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="3b575-484">是的，SharePoint 提供许多非组关联的服务和网站，如通信和中心网站。</span><span class="sxs-lookup"><span data-stu-id="3b575-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="3b575-485">**每个组能否有多个网站？**</span><span class="sxs-lookup"><span data-stu-id="3b575-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="3b575-486">否，每个组只能有一个网站。</span><span class="sxs-lookup"><span data-stu-id="3b575-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="3b575-487">Teams 中的私人频道使用未连接到组的其他网站。</span><span class="sxs-lookup"><span data-stu-id="3b575-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="3b575-488">**网站能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-489">从技术上说没有，但在使用组创建网站时，内容可以与其他组共享。</span><span class="sxs-lookup"><span data-stu-id="3b575-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="3b575-490">**网站与组关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="3b575-491">否，网站本身与组相关联，但内容可以通过在本地导出内容或通过使用第三方工具从 SharePoint 界面中的一个网站移动到另一个网站。</span><span class="sxs-lookup"><span data-stu-id="3b575-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="3b575-492">**删除网站是否删除组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="3b575-493">可以，删除 SharePoint 中的网站将删除组和组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="3b575-494">Stream</span><span class="sxs-lookup"><span data-stu-id="3b575-494">Stream</span></span>

<span data-ttu-id="3b575-495">Microsoft Stream 是一个视频托管和共享平台。</span><span class="sxs-lookup"><span data-stu-id="3b575-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="3b575-496">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3b575-497">视频存储</span><span class="sxs-lookup"><span data-stu-id="3b575-497">Video storage</span></span>
- <span data-ttu-id="3b575-498">Teams 会议录制</span><span class="sxs-lookup"><span data-stu-id="3b575-498">Teams meeting recording</span></span>
- <span data-ttu-id="3b575-499">视频频道</span><span class="sxs-lookup"><span data-stu-id="3b575-499">Video channels</span></span>

<span data-ttu-id="3b575-500">**Stream 可以创建组吗？**</span><span class="sxs-lookup"><span data-stu-id="3b575-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="3b575-501">可以，可以直接从 Stream 创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="3b575-502">**Stream 是否存在没有组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="3b575-503">可以，视频频道和视频可以存在于 Stream 中，而无需与组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="3b575-504">**每个组能否有多个视频和频道？**</span><span class="sxs-lookup"><span data-stu-id="3b575-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="3b575-505">可以，每个组中可以有多个视频和频道。</span><span class="sxs-lookup"><span data-stu-id="3b575-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="3b575-506">**视频或频道能否与多个组关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="3b575-507">可以，当视频或频道与组一起创建时，可以与其他组共享。</span><span class="sxs-lookup"><span data-stu-id="3b575-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="3b575-508">**其与组关联能否更改？**</span><span class="sxs-lookup"><span data-stu-id="3b575-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="3b575-509">是和否;Stream 中的视频归原始上传者或会议录制器所有，因此可以与任何组关联，但是视频频道只能与最初创建的组相关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="3b575-510">**删除视频或频道是否删除该组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="3b575-511">否，删除视频或频道不会删除组。</span><span class="sxs-lookup"><span data-stu-id="3b575-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="3b575-512">但是，在 Stream 中删除组本身将删除与组关联的服务和内容，实际视频除外。</span><span class="sxs-lookup"><span data-stu-id="3b575-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="3b575-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="3b575-513">Yammer</span></span>

<span data-ttu-id="3b575-514">Yammer 是一个企业社交平台，旨在促进组织内部和组织之间的社区参与。</span><span class="sxs-lookup"><span data-stu-id="3b575-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="3b575-515">在 Yammer (之前称为"组") 创建一个邮箱，但当前尚未使用。</span><span class="sxs-lookup"><span data-stu-id="3b575-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="3b575-516">与 Yammer 关联的 Microsoft 365 组不能与 Microsoft Teams 中的团队一同使用。</span><span class="sxs-lookup"><span data-stu-id="3b575-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="3b575-517">**向组提供的关键功能**</span><span class="sxs-lookup"><span data-stu-id="3b575-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3b575-518">对话区域</span><span class="sxs-lookup"><span data-stu-id="3b575-518">Conversation area</span></span>

<span data-ttu-id="3b575-519">**Yammer 能否创建 Microsoft 365 组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="3b575-520">可以，如果平台已连接且用户能够创建组，则 Yammer 中创建新组将创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="3b575-521">无法在除 Yammer 本身外的任何接口或服务中创建与 Microsoft 365 组关联的 Yammer 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="3b575-522">**是否存在没有 Microsoft 365 组的 Yammer 组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="3b575-523">可以，可以创建没有 Microsoft 365 组的 Yammer 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="3b575-524">如果 Yammer 平台未连接到 Microsoft 365 组，或者用户无法创建 Microsoft 365 组，则创建 Yammer 组时将没有 Microsoft 365 组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="3b575-525">**每个 Microsoft 365 组能否有多个 Yammer 组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="3b575-526">否，Yammer 组和 Microsoft 365 组之间的关系是 1：1。</span><span class="sxs-lookup"><span data-stu-id="3b575-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="3b575-527">**Yammer 组能否与多个 Microsoft 365 组相关联？**</span><span class="sxs-lookup"><span data-stu-id="3b575-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="3b575-528">否，Yammer 组只能与单个 Microsoft 365 组关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="3b575-529">可以与其他 Yammer 组共享帖子或将帖子移动到其他 Yammer 组。</span><span class="sxs-lookup"><span data-stu-id="3b575-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="3b575-530">**Yammer 组与 Microsoft 365 组关联能否发生变化？**</span><span class="sxs-lookup"><span data-stu-id="3b575-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="3b575-531">否，Yammer 组只能与最初关联的 Microsoft 365 组相关联。</span><span class="sxs-lookup"><span data-stu-id="3b575-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="3b575-532">**删除 Yammer 组是否删除 Microsoft 365 组？**</span><span class="sxs-lookup"><span data-stu-id="3b575-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="3b575-533">可以，删除 Yammer 中的组将删除相关的 Microsoft 组和组关联的服务和内容。</span><span class="sxs-lookup"><span data-stu-id="3b575-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b575-534">相关主题</span><span class="sxs-lookup"><span data-stu-id="3b575-534">Related topics</span></span>

[<span data-ttu-id="3b575-535">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="3b575-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="3b575-536">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="3b575-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)