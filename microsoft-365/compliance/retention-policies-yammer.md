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
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362290"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="0df26-103">了解用于 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="0df26-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="0df26-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="0df26-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="0df26-105">此功能暂处于预览阶段，可能会发生变更。</span><span class="sxs-lookup"><span data-stu-id="0df26-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="0df26-106">本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Yammer 的信息。</span><span class="sxs-lookup"><span data-stu-id="0df26-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="0df26-107">有关其他工作负载，请参阅：</span><span class="sxs-lookup"><span data-stu-id="0df26-107">For other workloads, see:</span></span>

- [<span data-ttu-id="0df26-108">了解用于 SharePoint 和 OneDrive 的保留</span><span class="sxs-lookup"><span data-stu-id="0df26-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="0df26-109">了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="0df26-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="0df26-110">了解用于 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="0df26-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="0df26-111">保留和删除包括哪些内容</span><span class="sxs-lookup"><span data-stu-id="0df26-111">What's included for retention and deletion</span></span>

<span data-ttu-id="0df26-112">可通过使用 Yammer 的保留策略来保留和删除以下 Yammer 项：社区消息和用户消息。</span><span class="sxs-lookup"><span data-stu-id="0df26-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and user messages.</span></span>

<span data-ttu-id="0df26-113">这些消息中不包括其他人以表情符号的形式所做的回复。</span><span class="sxs-lookup"><span data-stu-id="0df26-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="0df26-114">用于 Yammer 的保留的工作原理</span><span class="sxs-lookup"><span data-stu-id="0df26-114">How retention works with Yammer</span></span>

<span data-ttu-id="0df26-115">使用本节以了解如何通过后端存储和流程满足合规性要求，以及应如何通过电子数据展示工具，而不是通过当前在 Yammer 应用中可见的邮件来进行验证。</span><span class="sxs-lookup"><span data-stu-id="0df26-115">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Yammer app.</span></span>

<span data-ttu-id="0df26-116">可以使用保留策略在 Yammer 中保留社区邮件和用户邮件中的数据，并删除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="0df26-116">You can use a retention policy to retain data from community messages and user messages in Yammer, and delete these messages.</span></span> <span data-ttu-id="0df26-117">Exchange 邮箱在后台用于存储从这些邮件中复制的数据。</span><span class="sxs-lookup"><span data-stu-id="0df26-117">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="0df26-118">来自 Yammer 用户邮件的数据存储包含于用户邮件中每个用户邮箱内的隐藏文件夹中，组邮箱中的类似隐藏文件夹则用于社区邮件。</span><span class="sxs-lookup"><span data-stu-id="0df26-118">Data from Yammer user messages is stored in a hidden folder in the mailbox of each user included in the user message, and a similar hidden folder in a group mailbox is used for community messages.</span></span>

<span data-ttu-id="0df26-119">当 @提及用户或通知用户有人答复时，社区邮件的副本也可以存储在用户邮箱的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0df26-119">Copies of community messages can also be stored in the hidden folder of user mailboxes when they @ mention users or notify the user of a reply.</span></span> <span data-ttu-id="0df26-120">尽管这些邮件源自社区邮件，但 Yammer 用户邮件的保留策略通常包括社区邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="0df26-120">Although these messages originate as a community message, a retention policy for Yammer user messages will often include copies of community messages.</span></span>

<span data-ttu-id="0df26-121">这些隐藏的文件夹不是为了供用户或管理员直接访问，而是存储合规性管理员可以使用电子数据展示工具搜索的数据。</span><span class="sxs-lookup"><span data-stu-id="0df26-121">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0df26-122">由于社区邮件的副本也可以存储在用户邮箱中，因此对 Yammer 用户邮件执行删除操作的保留策略可能导致 Yammer 应用中的用户不再看到原始社区邮件。</span><span class="sxs-lookup"><span data-stu-id="0df26-122">Because copies of community messages can also be stored in user mailboxes, a retention policy with a delete action for Yammer user messages can result in the original community message no longer visible to users in the Yammer app.</span></span>
> 
> <span data-ttu-id="0df26-123">但是，原始邮件的副本在社区组邮箱的隐藏文件夹中仍然可用，并可出于合规目的通过电子数据展示搜索进行访问。</span><span class="sxs-lookup"><span data-stu-id="0df26-123">However, a copy of the original message is still available in the hidden folder of the community group mailbox, and accessible with eDiscovery searches for compliance purposes.</span></span>

<span data-ttu-id="0df26-124">Yammer 邮件不受针对 Exchange 邮箱配置的保留策略影响。</span><span class="sxs-lookup"><span data-stu-id="0df26-124">Yammer messages are not affected by retention policies that are configured for Exchange mailboxes.</span></span> <span data-ttu-id="0df26-125">即使 Yammer 消息存储在 Exchange 中，此 Yammer 数据仍将仅包含在针对 **Yammer 社区消息** 和 **Yammer 用户消息** 位置配置的保留策略中。</span><span class="sxs-lookup"><span data-stu-id="0df26-125">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="0df26-126">如果用户包含在保留 Yammer 数据的活动保留策略中，并且删除了包含在此策略中的用户邮箱，为了保留 Yammer 数据，邮箱会转换为[非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0df26-126">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="0df26-127">如果不需要为用户保留此 Yammer 数据，请在删除用户的邮箱之前，将用户帐户从保留策略中排除。</span><span class="sxs-lookup"><span data-stu-id="0df26-127">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="0df26-128">为 Yammer 消息配置保留策略后，Exchange 服务中的计时器作业会定期评估存储这些 Yammer 消息的隐藏文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="0df26-128">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="0df26-129">计时器作业最多需要 7 天才能运行。</span><span class="sxs-lookup"><span data-stu-id="0df26-129">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="0df26-130">这些项目的保留期限到期后，它们将被移至 SubstrateHolds 文件夹，此文件夹是每个用户或组邮箱中的隐藏文件夹，用于在永久删除“软删除”项目之前存储这些项目。</span><span class="sxs-lookup"><span data-stu-id="0df26-130">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="0df26-131">由于[第一个保留策略](retention.md#the-principles-of-retention-or-what-takes-precedence)，如果由于另一个保留策略而必须保留同一项目，或者由于法律或调查原因而处于电子数据展示保留状态，则永久删除始终处于暂停状态。</span><span class="sxs-lookup"><span data-stu-id="0df26-131">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="0df26-132">为 Yammer 消息配置保留策略后，内容路径取决于保留策略是“保留后删除”、“仅保留”还是“仅删除”。</span><span class="sxs-lookup"><span data-stu-id="0df26-132">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="0df26-133">如果保留策略为“保留后删除”：</span><span class="sxs-lookup"><span data-stu-id="0df26-133">When the retention policy is to retain and then delete:</span></span>

![Yammer 消息的保留流示意图](../media/yammerretentionlifecycle.png)

<span data-ttu-id="0df26-135">对于图中的两条路径：</span><span class="sxs-lookup"><span data-stu-id="0df26-135">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="0df26-136">**如果用户在保留期内编辑或删除了 Yammer 消息**，则该原始消息将被立即复制（如果已编辑）或移动（如果已删除）到 SubstrateHolds 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0df26-136">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="0df26-137">消息将存储在此处，直到保留期到期，然后立即将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="0df26-137">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="0df26-138">**如果未删除 Yammer 消息**，并且对于编辑后的当前消息，则保留期到期后，消息将被移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0df26-138">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="0df26-139">此操作自到期之日起最多需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="0df26-139">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="0df26-140">如果消息位于 SubstrateHolds 文件夹中时，它将立即被永久删除。</span><span class="sxs-lookup"><span data-stu-id="0df26-140">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="0df26-141">可通过电子数据展示工具搜索 SubstrateHolds 文件夹中的消息。</span><span class="sxs-lookup"><span data-stu-id="0df26-141">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="0df26-142">消息被永久删除（位于 SubstrateHolds 文件夹中）前，仍可由 eDiscovery 工具搜索。</span><span class="sxs-lookup"><span data-stu-id="0df26-142">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="0df26-143">如果保留策略为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化。</span><span class="sxs-lookup"><span data-stu-id="0df26-143">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="0df26-144">“仅保留”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="0df26-144">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="0df26-145">**如果编辑或删除了 Yammer 消息**：立即在 SubstrateHolds 文件夹中创建原始消息的副本，并将其保留在那里，直到保留期到期。</span><span class="sxs-lookup"><span data-stu-id="0df26-145">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="0df26-146">然后，此消息会立即从 SubstrateHolds 文件夹中永久删除。</span><span class="sxs-lookup"><span data-stu-id="0df26-146">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="0df26-147">**如果 Yammer 消息在保持期内未遭修改或删除** 以及保留期内编辑后的当前消息：保留期前后无变化；消息仍保留在原始位置。</span><span class="sxs-lookup"><span data-stu-id="0df26-147">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="0df26-148">“仅删除”保留策略的内容路径</span><span class="sxs-lookup"><span data-stu-id="0df26-148">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="0df26-149">**如果 Yammer 消息在保持期内未遭删除**：在保持期结束时，消息将移至 SubstrateHolds 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0df26-149">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="0df26-150">此操作自到期之日起最多需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="0df26-150">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="0df26-151">然后，此消息会立即从 SubstrateHolds 文件夹中永久删除。</span><span class="sxs-lookup"><span data-stu-id="0df26-151">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="0df26-152">**如果用户在保留期内删除 Yammer 消息**，该项目将立即移至 SubstrateHolds 文件夹，并立即将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="0df26-152">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="0df26-153">消息和外部用户</span><span class="sxs-lookup"><span data-stu-id="0df26-153">Messages and external users</span></span>

<span data-ttu-id="0df26-154">默认情况下，Yammer 用户消息的保留策略应用于组织中的所有用户，但不应用于外部用户。</span><span class="sxs-lookup"><span data-stu-id="0df26-154">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="0df26-155">如果对包含的用户使用“**编辑**”选项并指定其帐户，则可以向外部用户应用保留策略。</span><span class="sxs-lookup"><span data-stu-id="0df26-155">You can apply a retention policy to external users if you use the **Edit** option for users included, and specify their account.</span></span>

<span data-ttu-id="0df26-156">目前，不支持 Azure B2B 来宾用户。</span><span class="sxs-lookup"><span data-stu-id="0df26-156">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="0df26-157">如果某用户离开组织</span><span class="sxs-lookup"><span data-stu-id="0df26-157">When a user leaves the organization</span></span> 

<span data-ttu-id="0df26-158">如果用户离开你的组织，并且其 Microsoft 365 帐户被删除，则其要保留的 Yammer 用户消息将存储在非活动邮箱中。</span><span class="sxs-lookup"><span data-stu-id="0df26-158">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="0df26-159">这些消息仍受用户在其邮箱变为非活动状态之前所应用的任何保留策略的约束，并且内容支持电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="0df26-159">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="0df26-160">有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0df26-160">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="0df26-161">如果用户在 Yammer 中存储了任何文件，请参阅 SharePoint 和 OneDrive 的[等效部分](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。</span><span class="sxs-lookup"><span data-stu-id="0df26-161">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="0df26-162">限制</span><span class="sxs-lookup"><span data-stu-id="0df26-162">Limitations</span></span>

<span data-ttu-id="0df26-163">Yammer 保留策略目前处于预览阶段，我们正在不断努力优化保留功能。</span><span class="sxs-lookup"><span data-stu-id="0df26-163">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="0df26-164">在此期间，在对 Yammer 社区邮件和用户邮件使用保留时，需要注意以下几个限制：</span><span class="sxs-lookup"><span data-stu-id="0df26-164">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and user messages:</span></span>

- <span data-ttu-id="0df26-165">为 **Yammer 用户邮件** 位置选择“**编辑**”时，可能看到来宾和非邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="0df26-165">When you select **Edit** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="0df26-166">保留策略并非专为这些用户设计的，因此请不要选择他们。</span><span class="sxs-lookup"><span data-stu-id="0df26-166">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="0df26-167">配置指南</span><span class="sxs-lookup"><span data-stu-id="0df26-167">Configuration guidance</span></span>

<span data-ttu-id="0df26-168">如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="0df26-168">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="0df26-169">如果已准备好配置 Teams 的保留策略，请参阅[创建和配置保留策略](create-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0df26-169">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>