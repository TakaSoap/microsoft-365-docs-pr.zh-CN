---
title: 规划组和组织的组织和生命周期Microsoft 365和Microsoft Teams
ms.reviewer: arvaradh
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
recommendations: false
description: 与协作工具的生命周期管理选项Microsoft 365
ms.openlocfilehash: 7d88618b75ef731bf38df029970efdc05f3eea5a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538815"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="0d669-103">规划组和组织的组织和生命周期Microsoft 365和Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d669-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="0d669-104">Microsoft 365组具有一组丰富的工具来实施组织所需的管理功能。</span><span class="sxs-lookup"><span data-stu-id="0d669-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="0d669-105">下一节介绍这些功能、推荐最佳实践，并提供指导，以提出正确的问题以确定管理要求以及如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="0d669-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="0d669-106">控制哪些人可以创建Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="0d669-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="0d669-107">最终用户可以从多个终点创建组，包括Outlook、SharePoint、Teams和其他环境。</span><span class="sxs-lookup"><span data-stu-id="0d669-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![图像 desc](../media/04.png)

<span data-ttu-id="0d669-109">我们强烈建议自助服务，为组所有者提供能力并帮助用户更轻松地完成工作。</span><span class="sxs-lookup"><span data-stu-id="0d669-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="0d669-110">限制组和团队创建可能会降低用户的工作效率，因为许多Microsoft 365服务需要创建组，服务才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="0d669-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="0d669-111">考虑以下组创建管理选项：</span><span class="sxs-lookup"><span data-stu-id="0d669-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="0d669-112">若要限制组移动，请使用 [组过期策略](microsoft-365-groups-expiration-policy.md) 自动删除不使用的组。</span><span class="sxs-lookup"><span data-stu-id="0d669-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="0d669-113">将组创建限制为包含动态成员身份[](/azure/active-directory/users-groups-roles/groups-create-rule)（例如，所有全职员工）的安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="0d669-113">Limit group creation to members of a [security groups with dynamic membership](/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="0d669-114">将组创建限制为安全组，并要求用户完成组织的组使用策略中的培训，以便成为安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="0d669-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="0d669-115">如果要限制可以创建组的人，请参阅管理哪些人[可以创建Microsoft 365组，](manage-creation-of-groups.md)了解如何配置此组。</span><span class="sxs-lookup"><span data-stu-id="0d669-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="0d669-116">组删除、还原和存档</span><span class="sxs-lookup"><span data-stu-id="0d669-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="0d669-117">删除Microsoft 365组时，默认情况下该组将保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="0d669-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="0d669-118">这 30 天时间被称为"软删除"，因为仍然可以对组进行还原。</span><span class="sxs-lookup"><span data-stu-id="0d669-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="0d669-119">30 天后，组和相关内容将永久删除且无法还原。</span><span class="sxs-lookup"><span data-stu-id="0d669-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="0d669-120">如果已制定保留策略来保留聊天、文件或邮件，则删除组后将保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="0d669-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="0d669-121">有关详细信息 [，请参阅了解](../compliance/retention.md) 保留策略。</span><span class="sxs-lookup"><span data-stu-id="0d669-121">See [Learn about retention policies](../compliance/retention.md) for details.</span></span>

<span data-ttu-id="0d669-122">如果要删除组，但保留一个或多个已连接组的服务中的内容，请参阅存档组、团队和[Yammer获取信息](end-life-cycle-groups-teams-sites-yammer.md)。</span><span class="sxs-lookup"><span data-stu-id="0d669-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="0d669-123">组命名策略</span><span class="sxs-lookup"><span data-stu-id="0d669-123">Group naming policy</span></span>

<span data-ttu-id="0d669-124">组命名策略可以通过两种方式帮助您管理组：</span><span class="sxs-lookup"><span data-stu-id="0d669-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="0d669-125">前缀/后缀命名策略可用于在组名称及其关联电子邮件地址的开头或结尾强制执行固定字符串或 Azure AD 属性。</span><span class="sxs-lookup"><span data-stu-id="0d669-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="0d669-126">通过执行此操作，可以确保在组名称中加入部门名称或区域等。</span><span class="sxs-lookup"><span data-stu-id="0d669-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="0d669-127">阻止的词语策略可以确保某些词语（如主管的姓名）不会用于组名。</span><span class="sxs-lookup"><span data-stu-id="0d669-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="0d669-128">从任何组连接的服务创建组时，将应用命名策略。</span><span class="sxs-lookup"><span data-stu-id="0d669-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="0d669-129">如果你决定对组使用命名策略，请参阅Microsoft 365[组命名策略。](groups-naming-policy.md)</span><span class="sxs-lookup"><span data-stu-id="0d669-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="0d669-130">组过期策略</span><span class="sxs-lookup"><span data-stu-id="0d669-130">Group expiration policy</span></span>

<span data-ttu-id="0d669-131">你可以指定过期期限，达到该期限到期且未续订的任何组都将被删除。</span><span class="sxs-lookup"><span data-stu-id="0d669-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="0d669-132">过期期限从组创建时或上次续订日期开始。</span><span class="sxs-lookup"><span data-stu-id="0d669-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="0d669-133">将组设置为过期后：</span><span class="sxs-lookup"><span data-stu-id="0d669-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="0d669-134">该组的所有者将收到通知，以在即将过期时续订组。</span><span class="sxs-lookup"><span data-stu-id="0d669-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="0d669-135">自动续订活动组。</span><span class="sxs-lookup"><span data-stu-id="0d669-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="0d669-136">任何未续订的组都将被删除。</span><span class="sxs-lookup"><span data-stu-id="0d669-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="0d669-137">任何已删除的组都可以在 30 天内由组所有者或管理员还原。</span><span class="sxs-lookup"><span data-stu-id="0d669-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="0d669-138">过期策略是一种通过确保删除不再使用的组来限制组过期的一个好方法。</span><span class="sxs-lookup"><span data-stu-id="0d669-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="0d669-139">如果要创建组过期策略，请参阅Microsoft 365[过期策略。](microsoft-365-groups-expiration-policy.md)</span><span class="sxs-lookup"><span data-stu-id="0d669-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d669-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="0d669-140">Related topics</span></span>

[<span data-ttu-id="0d669-141">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="0d669-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="0d669-142">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="0d669-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="0d669-143">删除以前的员工和安全数据</span><span class="sxs-lookup"><span data-stu-id="0d669-143">Remove a former employee and secure data</span></span>](/microsoft-365/admin/add-users/remove-former-employee)
