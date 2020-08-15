---
title: 为 Microsoft 365 组和 Microsoft 团队规划组织和生命周期管理
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 有关 Microsoft 365 中的协作工具的生命周期管理选项的精益
ms.openlocfilehash: 2a2f14bf439ec69e4609d22783fb14d1d5cb8e70
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662497"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="d65e8-103">为 Microsoft 365 组和 Microsoft 团队规划组织和生命周期管理</span><span class="sxs-lookup"><span data-stu-id="d65e8-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="d65e8-104">Microsoft 365 组提供了一组丰富的工具来实施您的组织所需的治理功能。</span><span class="sxs-lookup"><span data-stu-id="d65e8-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="d65e8-105">下一节介绍了功能、建议最佳做法，并提供了指导以确定对调控的要求以及如何满足这些要求的指导。</span><span class="sxs-lookup"><span data-stu-id="d65e8-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="d65e8-106">控制可以创建 Microsoft 365 组的用户</span><span class="sxs-lookup"><span data-stu-id="d65e8-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="d65e8-107">最终用户可以从多个终结点（包括 Outlook、SharePoint、团队和其他环境）创建组。</span><span class="sxs-lookup"><span data-stu-id="d65e8-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![图像 desc](../media/04.png)

<span data-ttu-id="d65e8-109">强烈建议使用自助服务所有者，并帮助用户更轻松地完成其工作。</span><span class="sxs-lookup"><span data-stu-id="d65e8-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="d65e8-110">限制组和团队创建会降低用户工作效率，因为许多 Microsoft 365 服务都需要创建组才能使服务正常工作。</span><span class="sxs-lookup"><span data-stu-id="d65e8-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="d65e8-111">考虑用于创建组的以下管理选项：</span><span class="sxs-lookup"><span data-stu-id="d65e8-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="d65e8-112">若要限制组的数量增加，请使用 [组过期策略](microsoft-365-groups-expiration-policy.md) 自动删除未使用的组。</span><span class="sxs-lookup"><span data-stu-id="d65e8-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="d65e8-113">将组创建限制为包含 [动态成员身份的安全组](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) 的成员，例如，所有全职员工。</span><span class="sxs-lookup"><span data-stu-id="d65e8-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="d65e8-114">将组创建限制为安全组，并要求用户在组织的组使用策略中完成培训，以便成为安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="d65e8-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="d65e8-115">如果要限制可以创建组的用户，请参阅 [管理可创建 Microsoft 365 组的用户](manage-creation-of-groups.md) ，以了解有关如何配置此操作的信息。</span><span class="sxs-lookup"><span data-stu-id="d65e8-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="d65e8-116">组删除、还原和存档</span><span class="sxs-lookup"><span data-stu-id="d65e8-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="d65e8-117">删除 Microsoft 365 组时，默认情况下它将保留30天。</span><span class="sxs-lookup"><span data-stu-id="d65e8-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="d65e8-118">这 30 天时间被称为"软删除"，因为仍然可以对组进行还原。</span><span class="sxs-lookup"><span data-stu-id="d65e8-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="d65e8-119">30 天后，组和相关内容将永久删除且无法还原。</span><span class="sxs-lookup"><span data-stu-id="d65e8-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="d65e8-120">如果保留了保留策略以保留聊天、文件或邮件，则在删除组后将保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="d65e8-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="d65e8-121">有关详细信息，请参阅 [了解保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 。</span><span class="sxs-lookup"><span data-stu-id="d65e8-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="d65e8-122">如果要删除一个组，但保留一个或多个组连接服务的内容，请参阅 [存档组、团队和 Yammer](end-life-cycle-groups-teams-sites-yammer.md) 获取信息。</span><span class="sxs-lookup"><span data-stu-id="d65e8-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="d65e8-123">组命名策略</span><span class="sxs-lookup"><span data-stu-id="d65e8-123">Group naming policy</span></span>

<span data-ttu-id="d65e8-124">组命名策略可帮助您以两种方式管理组：</span><span class="sxs-lookup"><span data-stu-id="d65e8-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="d65e8-125">可以使用前缀/后缀命名策略在组名称的开头或结尾强制实施固定字符串或 Azure AD 属性及其关联的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d65e8-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="d65e8-126">通过执行此操作，可以确保包含，例如，部门名称或组名称中的区域。</span><span class="sxs-lookup"><span data-stu-id="d65e8-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="d65e8-127">阻止的词策略可确保在组名称中不使用某些词（例如，行政人员姓名）。</span><span class="sxs-lookup"><span data-stu-id="d65e8-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="d65e8-128">当从任何组连接服务创建组时，将应用命名策略。</span><span class="sxs-lookup"><span data-stu-id="d65e8-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="d65e8-129">如果决定使用组的命名策略，请参阅 [Microsoft 365 组命名策略](groups-naming-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="d65e8-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="d65e8-130">组过期策略</span><span class="sxs-lookup"><span data-stu-id="d65e8-130">Group expiration policy</span></span>

<span data-ttu-id="d65e8-131">您可以指定过期期限和任何到达该时间段结束的组，并且不会被更新。</span><span class="sxs-lookup"><span data-stu-id="d65e8-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="d65e8-132">过期时间是在创建组时开始，或在上次续订日期时开始。</span><span class="sxs-lookup"><span data-stu-id="d65e8-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="d65e8-133">将组设置为过期后：</span><span class="sxs-lookup"><span data-stu-id="d65e8-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="d65e8-134">在临近过期时，会通知组的所有者续订组。</span><span class="sxs-lookup"><span data-stu-id="d65e8-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="d65e8-135">自动续订活动组。</span><span class="sxs-lookup"><span data-stu-id="d65e8-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="d65e8-136">任何未续订的组都将被删除。</span><span class="sxs-lookup"><span data-stu-id="d65e8-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="d65e8-137">可以通过组所有者或管理员在30天内恢复删除的任何组。</span><span class="sxs-lookup"><span data-stu-id="d65e8-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="d65e8-138">过期策略是通过确保删除不再使用的组来限制组数量剧增的一种有效方式。</span><span class="sxs-lookup"><span data-stu-id="d65e8-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="d65e8-139">如果要创建组过期策略，请参阅 [Microsoft 365 组过期策略](microsoft-365-groups-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="d65e8-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>
