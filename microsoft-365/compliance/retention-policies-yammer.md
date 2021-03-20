---
title: 了解用于 Yammer 的保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解适用于 Yammer 的保留策略。
ms.openlocfilehash: 0426fdf04090e535a99f8acd3bf376adfb016796
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917798"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="dd162-103">了解用于 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="dd162-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="dd162-104">*[Microsoft 365 安全与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="dd162-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="dd162-105">此功能为预览版，尚未提供给所有客户。</span><span class="sxs-lookup"><span data-stu-id="dd162-105">This feature is in preview and not yet available for all customers.</span></span>

<span data-ttu-id="dd162-106">本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Yammer 的信息。</span><span class="sxs-lookup"><span data-stu-id="dd162-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="dd162-107">有关其他工作负载，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dd162-107">For other workloads, see:</span></span>

- [<span data-ttu-id="dd162-108">了解用于 SharePoint 和 OneDrive 的保留</span><span class="sxs-lookup"><span data-stu-id="dd162-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="dd162-109">了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="dd162-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="dd162-110">了解用于 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="dd162-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="dd162-111">保留和删除包括哪些内容</span><span class="sxs-lookup"><span data-stu-id="dd162-111">What's included for retention and deletion</span></span>

<span data-ttu-id="dd162-112">可使用 Yammer 的保留策略来保留和删除以下 Yammer 项目：社区消息和私人消息。</span><span class="sxs-lookup"><span data-stu-id="dd162-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="dd162-113">这些消息中不包括其他人以表情符号的形式所做的回复。</span><span class="sxs-lookup"><span data-stu-id="dd162-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="dd162-114">用于 Yammer 的保留的工作原理</span><span class="sxs-lookup"><span data-stu-id="dd162-114">How retention works with Yammer</span></span>

<span data-ttu-id="dd162-115">可使用保留策略在 Yammer 中保留和删除社区消息和私人消息。</span><span class="sxs-lookup"><span data-stu-id="dd162-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="dd162-116">私人消息存储在消息中的每个用户邮箱中的隐藏文件夹内，社区消息存储在社区组邮箱中类似的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dd162-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="dd162-117">Yammer 消息不受针对用户或组邮箱配置的保留策略影响。</span><span class="sxs-lookup"><span data-stu-id="dd162-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="dd162-118">即使 Yammer 消息存储在 Exchange 中，此 Yammer 数据仍将仅包含在针对 **Yammer 社区消息** 和 **Yammer 私人消息** 位置配置的保留策略中。</span><span class="sxs-lookup"><span data-stu-id="dd162-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer private messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="dd162-119">如果用户包含在保留 Yammer 数据的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Yammer 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="dd162-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="dd162-120">如果不需要为用户保留此 Yammer 数据，请在删除用户的邮箱之前，将用户帐户从保留策略中排除。</span><span class="sxs-lookup"><span data-stu-id="dd162-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="dd162-121">为 Yammer 消息配置保留策略后，Exchange 服务中的计时器作业会定期评估存储这些 Yammer 消息的隐藏文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="dd162-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="dd162-122">计时器作业最多需要 7 天才能运行。</span><span class="sxs-lookup"><span data-stu-id="dd162-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="dd162-123">这些项目的保留期限到期后，它们将被移至 SubstrateHolds 文件夹，此文件夹是每个用户或组邮箱中的隐藏文件夹，用于在永久删除“软删除”项目之前存储这些项目。</span><span class="sxs-lookup"><span data-stu-id="dd162-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="dd162-124">为 Yammer 消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。</span><span class="sxs-lookup"><span data-stu-id="dd162-124">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="dd162-125">如果保留策略为“保留后删除”：</span><span class="sxs-lookup"><span data-stu-id="dd162-125">When the retention policy is to retain and then delete:</span></span>

![Yammer 消息的保留流示意图](../media/yammerretentionlifecycle.png)

<span data-ttu-id="dd162-127">对于图中的两条路径：</span><span class="sxs-lookup"><span data-stu-id="dd162-127">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="dd162-128">**如果用户在保留期内编辑或删除了 Yammer 消息**，则该原始消息将被立即复制（如果已编辑）或移动（如果已删除）到 SubstrateHolds 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dd162-128">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="dd162-129">消息将存储在此处，直到保留期到期，然后立即将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="dd162-129">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="dd162-130">**如果未删除 Yammer 消息**，并且对于编辑后的当前消息，则保留期到期后，消息将被移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd162-130">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="dd162-131">此操作自到期之日起最多需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="dd162-131">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="dd162-132">如果消息位于 SubstrateHolds 文件夹中时，它将立即被永久删除。</span><span class="sxs-lookup"><span data-stu-id="dd162-132">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="dd162-133">可通过电子数据展示工具搜索 SubstrateHolds 文件夹中的消息。</span><span class="sxs-lookup"><span data-stu-id="dd162-133">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="dd162-134">消息被永久删除（位于 SubstrateHolds 文件夹中）前，仍可由 eDiscovery 工具搜索。</span><span class="sxs-lookup"><span data-stu-id="dd162-134">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="dd162-135">如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。</span><span class="sxs-lookup"><span data-stu-id="dd162-135">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="dd162-136">“仅保留”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="dd162-136">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="dd162-137">**如果编辑或删除了 Yammer 消息**：立即在 SubstrateHolds 文件夹中创建原始消息的副本，并将其保留在那里，直到保留期到期。</span><span class="sxs-lookup"><span data-stu-id="dd162-137">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="dd162-138">然后，此消息会立即从 SubstrateHolds 文件夹中永久删除。</span><span class="sxs-lookup"><span data-stu-id="dd162-138">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="dd162-139">**如果 Yammer 消息在保持期内未遭修改或删除** 以及保留期内编辑后的当前消息：保留期前后无变化；消息仍保留在原始位置。</span><span class="sxs-lookup"><span data-stu-id="dd162-139">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="dd162-140">“仅删除”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="dd162-140">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="dd162-141">**如果 Yammer 消息在保持期内未遭删除**：在保持期结束时，消息将移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd162-141">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="dd162-142">此操作自到期之日起最多需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="dd162-142">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="dd162-143">然后，此消息会立即从 SubstrateHolds 文件夹中永久删除。</span><span class="sxs-lookup"><span data-stu-id="dd162-143">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="dd162-144">**如果用户在保留期内删除 Yammer 消息**，该项目将立即移至 SubstrateHolds 文件夹，并立即将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="dd162-144">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="dd162-145">消息和外部用户</span><span class="sxs-lookup"><span data-stu-id="dd162-145">Messages and external users</span></span>

<span data-ttu-id="dd162-146">默认情况下，Yammer 私人消息的保留策略应用于组织中的所有用户，但不应用于外部用户。</span><span class="sxs-lookup"><span data-stu-id="dd162-146">By default, a retention policy for Yammer private messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="dd162-147">如果使用 **选择用户** 并指定其帐户，则可以向外部用户应用保留策略。</span><span class="sxs-lookup"><span data-stu-id="dd162-147">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="dd162-148">目前，不支持 Azure B2B 来宾用户。</span><span class="sxs-lookup"><span data-stu-id="dd162-148">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="dd162-149">如果某用户离开组织</span><span class="sxs-lookup"><span data-stu-id="dd162-149">When a user leaves the organization</span></span> 

<span data-ttu-id="dd162-150">如果用户离开你的组织，并且其 Microsoft 365 帐户被删除，则其要保留的 Yammer 私人消息将存储在非活动邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dd162-150">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer private messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="dd162-151">这些消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="dd162-151">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="dd162-152">有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="dd162-152">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="dd162-153">如果用户在 Yammer 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="dd162-153">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="dd162-154">限制</span><span class="sxs-lookup"><span data-stu-id="dd162-154">Limitations</span></span>

<span data-ttu-id="dd162-155">Yammer 保留策略目前处于预览阶段，我们正在不断努力优化保留功能。</span><span class="sxs-lookup"><span data-stu-id="dd162-155">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="dd162-156">在此期间，在对 Yammer 社区消息和私人消息使用保留时，需要注意以下几个限制：</span><span class="sxs-lookup"><span data-stu-id="dd162-156">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="dd162-157">为“**Yammer 私人消息**”位置选择“**选择用户**”时，你可能会看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="dd162-157">When you select **Choose users** for the **Yammer private messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="dd162-158">保留策略并非专为这些用户设计的，因此请不要选择他们。</span><span class="sxs-lookup"><span data-stu-id="dd162-158">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="dd162-159">配置指南</span><span class="sxs-lookup"><span data-stu-id="dd162-159">Configuration guidance</span></span>

<span data-ttu-id="dd162-160">如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="dd162-160">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="dd162-161">如果已准备好配置 Teams 的保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="dd162-161">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>