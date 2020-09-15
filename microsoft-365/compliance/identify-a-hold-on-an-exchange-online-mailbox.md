---
title: 如何识别为 Exchange Online 邮箱设置的保留类型
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: 了解如何确定可在 Microsoft 365 中的 Exchange Online 邮箱上放置的不同保留类型。
ms.openlocfilehash: a76b02f6345421871c759e1b31bf19207b474e2a
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816821"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="ddd50-103">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="ddd50-103">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="ddd50-104">本文介绍如何识别在 Microsoft 365 的 Exchange Online 邮箱中放置的保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-104">This article explains how to identify holds placed on Exchange Online mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="ddd50-105">Microsoft 365 提供了多种方法，使您的组织可以阻止邮箱内容被永久删除。</span><span class="sxs-lookup"><span data-stu-id="ddd50-105">Microsoft 365 offers several ways that your organization can prevent mailbox content from being permanently deleted.</span></span> <span data-ttu-id="ddd50-106">这使您的组织可以保留内容以满足合规性管理法规或在法律和其他类型的调查过程中。</span><span class="sxs-lookup"><span data-stu-id="ddd50-106">This allows your organization to retain content to meet compliance regulations or during legal and other types of investigations.</span></span> <span data-ttu-id="ddd50-107">下面列出了 Office 365 中的保留功能 (也称为 *保留*) ：</span><span class="sxs-lookup"><span data-stu-id="ddd50-107">Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="ddd50-108">**[诉讼保留](create-a-litigation-hold.md)：** 应用于 Exchange Online 中的用户邮箱的保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-108">**[Litigation Hold](create-a-litigation-hold.md):** Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="ddd50-109">**[电子数据展示保留](create-ediscovery-holds.md)：** 与安全与合规中心中的核心电子数据展示事例相关联的保留项。</span><span class="sxs-lookup"><span data-stu-id="ddd50-109">**[eDiscovery hold](create-ediscovery-holds.md):** Holds that are associated with a Core eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="ddd50-110">电子数据展示保留可应用于用户邮箱以及 Microsoft 365 组和 Microsoft 团队对应的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ddd50-110">eDiscovery holds can be applied to user mailboxes and to the corresponding mailbox for Microsoft 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="ddd50-111">**[就地保留](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)：** 使用 exchange Online 中 Exchange 管理中心的就地电子数据展示 & 保留工具对用户邮箱应用的保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-111">**[In-Place Hold](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="ddd50-112">\*\* [Microsoft 365 保留策略](retention.md)：\*\* 可以配置为保留 (或保留，然后在 Exchange Online 中的用户邮箱中以及 Microsoft 365 组和 Microsoft 团队对应的邮箱中删除) 内容。</span><span class="sxs-lookup"><span data-stu-id="ddd50-112">**[Microsoft 365 retention policies](retention.md):** Can be configured to retain (or retain and then delete) content in user mailboxes in Exchange Online and in the corresponding mailbox for Microsoft 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="ddd50-113">您还可以创建保留策略以保留 Skype for Business 对话，这些会话存储在用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ddd50-113">You can also create a retention policy to retain Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="ddd50-114">有两种类型的 Microsoft 365 保留策略可分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="ddd50-114">There are two types of Microsoft 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="ddd50-115">**特定位置保留策略：** 这些是分配给特定用户的内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="ddd50-115">**Specific location retention policies:** These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="ddd50-116">您可以使用 Exchange Online PowerShell 中的 **邮箱获取** cmdlet 获取有关分配给特定邮箱的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="ddd50-116">You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="ddd50-117">有关此类型的保留策略的详细信息，请参阅保留策略文档中 [带有特定包含或排除的策略](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) 一节。</span><span class="sxs-lookup"><span data-stu-id="ddd50-117">For more information about this type of retention policy, see the section [A policy with specific inclusions or exclusions](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) from the retention policy documentation.</span></span>

    - <span data-ttu-id="ddd50-118">**组织范围内的保留策略：** 这些是分配给组织中的所有内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="ddd50-118">**Organization-wide retention policies:** These are policies that are assigned to all content locations in your organization.</span></span> <span data-ttu-id="ddd50-119">您可以使用 Exchange Online PowerShell 中的 **set-organizationconfig** cmdlet 来获取有关组织范围的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="ddd50-119">You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span> <span data-ttu-id="ddd50-120">有关此类型的保留策略的详细信息，请参阅保留策略文档中 [适用于整个位置的策略](create-retention-policies.md#a-policy-that-applies-to-entire-locations) 部分。</span><span class="sxs-lookup"><span data-stu-id="ddd50-120">For more information about this type of retention policy, see the section [A policy that applies to entire locations](create-retention-policies.md#a-policy-that-applies-to-entire-locations) from the retention policy documentation.</span></span>

- <span data-ttu-id="ddd50-121">**[Microsoft 365 保留标签](retention.md)：** 如果用户将 microsoft 365 保留标签 (配置为保留内容或保留，然后删除其邮箱中的 *任何* 文件夹或项目的内容) ，则邮箱上将放置在邮箱中，就像邮箱被置于诉讼保留或分配到 Microsoft 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="ddd50-121">**[Microsoft 365 retention labels](retention.md):** If a user applies a Microsoft 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox as if the mailbox was placed on Litigation Hold or assigned to a Microsoft 365 retention policy.</span></span> <span data-ttu-id="ddd50-122">有关详细信息，请参阅 [保留邮箱处于保留状态，因为已将保留标签应用于本文中的文件夹或项目](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) 部分。</span><span class="sxs-lookup"><span data-stu-id="ddd50-122">For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="ddd50-123">若要管理处于保留状态的邮箱，您可能需要确定邮箱中放置的保留类型，以便可以执行诸如更改保留持续时间、临时或永久删除保留或从 Microsoft 365 保留策略中排除邮箱等任务。</span><span class="sxs-lookup"><span data-stu-id="ddd50-123">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Microsoft 365 retention policy.</span></span> <span data-ttu-id="ddd50-124">在这些情况下，第一步是确定邮箱上放置的保留类型。</span><span class="sxs-lookup"><span data-stu-id="ddd50-124">In these cases, the first step is to identify the type of hold placed on the mailbox.</span></span> <span data-ttu-id="ddd50-125">由于多个保留 (和不同类型的保留) 可以放置在单个邮箱上，因此，如果您想要删除或更改保留，则必须标识邮箱中的所有保留项。</span><span class="sxs-lookup"><span data-stu-id="ddd50-125">And because multiple holds (and different types of holds) can be placed on a single mailbox, you have to identify all holds placed on a mailbox if you want to remove or change a hold.</span></span>

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="ddd50-126">步骤1：获取邮箱上放置的保留的 GUID</span><span class="sxs-lookup"><span data-stu-id="ddd50-126">Step 1: Obtain the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="ddd50-127">您可以在 Exchange Online PowerShell 中运行以下两个 cmdlet，以获取邮箱中放置的保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ddd50-127">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox.</span></span> <span data-ttu-id="ddd50-128">获取 GUID 后，可以使用它来标识步骤2中的特定保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-128">After you obtain a GUID, you use it to identify the specific hold in Step 2.</span></span> <span data-ttu-id="ddd50-129">GUID 未标识诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-129">A Litigation Hold isn't identified by a GUID.</span></span> <span data-ttu-id="ddd50-130">为邮箱启用或禁用诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-130">Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="ddd50-131">**获取邮箱：** 此 cmdlet 可用于确定是否对邮箱启用了诉讼保留，以及如何获取专门分配给邮箱的电子数据展示保留、就地保留和 Microsoft 365 保留策略的 Guid。</span><span class="sxs-lookup"><span data-stu-id="ddd50-131">**Get-Mailbox:** Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Microsoft 365 retention policies that are specifically assigned to a mailbox.</span></span> <span data-ttu-id="ddd50-132">此 cmdlet 的输出还将指示是否已从组织范围的保留策略中显式排除了邮箱。</span><span class="sxs-lookup"><span data-stu-id="ddd50-132">The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="ddd50-133">**Set-organizationconfig：** 此 cmdlet 可用于获取组织范围的保留策略的 Guid。</span><span class="sxs-lookup"><span data-stu-id="ddd50-133">**Get-OrganizationConfig:** Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="ddd50-134">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ddd50-134">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="ddd50-135">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="ddd50-135">Get-Mailbox</span></span>

<span data-ttu-id="ddd50-136">运行以下命令以获取有关应用于邮箱的保留和 Microsoft 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="ddd50-136">Run the following command to get information about the holds and Microsoft 365 retention policies applied to a mailbox.</span></span>

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="ddd50-137">如果 InPlaceHolds 属性中的值过多，并且不是全部显示，则可以运行 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 命令将每个 GUID 显示在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="ddd50-137">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="ddd50-138">下表介绍在运行 InPlaceHolds **cmdlet 时**，如何根据*InPlaceHolds*属性中的值标识不同类型的保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-138">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="ddd50-139">保留类型</span><span class="sxs-lookup"><span data-stu-id="ddd50-139">Hold type</span></span>  |<span data-ttu-id="ddd50-140">示例值</span><span class="sxs-lookup"><span data-stu-id="ddd50-140">Example value</span></span>  |<span data-ttu-id="ddd50-141">如何识别保留</span><span class="sxs-lookup"><span data-stu-id="ddd50-141">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ddd50-142">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="ddd50-142">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="ddd50-143">当 *LitigationHoldEnabled* 属性设置为时，将对邮箱启用诉讼保留 `True` 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-143">Litigation Hold is enabled for a mailbox when the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="ddd50-144">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="ddd50-144">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="ddd50-145">*InPlaceHolds 属性*包含与安全与合规中心中的电子数据展示事例关联的任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ddd50-145">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="ddd50-146">你可以告诉这是电子数据展示保留，因为 GUID 以 `UniH` 代表统一保留) 的 (前缀开头。</span><span class="sxs-lookup"><span data-stu-id="ddd50-146">You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="ddd50-147">就地保留</span><span class="sxs-lookup"><span data-stu-id="ddd50-147">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="ddd50-148">或</span><span class="sxs-lookup"><span data-stu-id="ddd50-148">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="ddd50-149">*InPlaceHolds*属性包含邮箱中放置的就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ddd50-149">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="ddd50-150">您可以指示这是就地保留，因为 GUID 既不以前缀开头，也不以 `cld` 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="ddd50-150">You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="ddd50-151">Microsoft 365 专用于邮箱的保留策略</span><span class="sxs-lookup"><span data-stu-id="ddd50-151">Microsoft 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="ddd50-152">或</span><span class="sxs-lookup"><span data-stu-id="ddd50-152">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="ddd50-153">InPlaceHolds 属性包含应用于邮箱的任何特定位置保留策略的 Guid。</span><span class="sxs-lookup"><span data-stu-id="ddd50-153">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox.</span></span> <span data-ttu-id="ddd50-154">您可以确定保留策略，因为 GUID 以 `mbx` 或 `skp` 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="ddd50-154">You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix.</span></span> <span data-ttu-id="ddd50-155">`skp`前缀指示将保留策略应用于用户邮箱中的 Skype For business 会话。</span><span class="sxs-lookup"><span data-stu-id="ddd50-155">The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="ddd50-156">从组织范围的 Microsoft 365 保留策略中排除</span><span class="sxs-lookup"><span data-stu-id="ddd50-156">Excluded from an organization-wide Microsoft 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="ddd50-157">如果从组织范围的 Microsoft 365 保留策略中排除了邮箱，则从 InPlaceHolds 属性中排除的保留策略的 GUID 将显示在 "" 属性中，并由前缀进行标识 `-mbx` 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-157">If a mailbox is excluded from an organization-wide Microsoft 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="ddd50-158">Set-organizationconfig</span><span class="sxs-lookup"><span data-stu-id="ddd50-158">Get-OrganizationConfig</span></span>
<span data-ttu-id="ddd50-159">如果运行**邮箱**cmdlet 时， *InPlaceHolds*属性为空，则仍有一个或多个组织范围的 Microsoft 365 保留策略应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="ddd50-159">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Microsoft 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="ddd50-160">在 Exchange Online PowerShell 中运行以下命令，获取组织范围内的 Microsoft 365 保留策略的 Guid 列表。</span><span class="sxs-lookup"><span data-stu-id="ddd50-160">Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Microsoft 365 retention policies.</span></span>

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="ddd50-161">如果 InPlaceHolds 属性中的值过多，并且不是全部显示，则可以运行 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 命令将每个 GUID 显示在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="ddd50-161">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="ddd50-162">下表介绍了不同类型的组织范围的保留，以及在运行**set-organizationconfig** cmdlet 时如何根据*InPlaceHolds*属性中包含的 guid 标识每种类型。</span><span class="sxs-lookup"><span data-stu-id="ddd50-162">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="ddd50-163">保留类型</span><span class="sxs-lookup"><span data-stu-id="ddd50-163">Hold type</span></span>  |<span data-ttu-id="ddd50-164">示例值</span><span class="sxs-lookup"><span data-stu-id="ddd50-164">Example value</span></span>  |<span data-ttu-id="ddd50-165">说明</span><span class="sxs-lookup"><span data-stu-id="ddd50-165">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ddd50-166">适用于 Exchange 邮箱、Exchange 公用文件夹和团队聊天的 Microsoft 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="ddd50-166">Microsoft 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="ddd50-167">在 Microsoft 团队中应用于 Exchange 邮箱、Exchange 公用文件夹和1xN 聊天的组织范围内的保留策略由以前缀开头的 Guid 进行标识 `mbx` 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-167">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix.</span></span> <span data-ttu-id="ddd50-168">注意1xN 聊天存储在各个聊天参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ddd50-168">Note 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="ddd50-169">适用于 Microsoft 365 组和团队频道消息的 microsoft 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="ddd50-169">Microsoft 365 retention policy applied to Microsoft 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="ddd50-170">在 Microsoft 团队中应用于 Microsoft 365 组和频道消息的组织范围内的保留策略由以前缀开头的 Guid 标识 `grp` 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-170">Organization-wide retention policies applied to Microsoft 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix.</span></span> <span data-ttu-id="ddd50-171">注释通道邮件存储在与 Microsoft 团队相关联的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ddd50-171">Note channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="ddd50-172">有关应用于 Microsoft 团队的保留策略的详细信息，请参阅 [了解 Microsoft 团队的保留策略](retention-policies-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ddd50-172">For more information about retention policies applied to Microsoft Teams, see [Learn about retention policies for Microsoft Teams](retention-policies-teams.md).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="ddd50-173">了解保留策略的 InPlaceHolds 值的格式</span><span class="sxs-lookup"><span data-stu-id="ddd50-173">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="ddd50-174">除了将 InPlaceHolds 属性中的项目标识为 Microsoft 365 保留策略 (mbx、skp 或 grp) 之外，此值还包含一个后缀，用于标识为策略配置的保留操作的类型。</span><span class="sxs-lookup"><span data-stu-id="ddd50-174">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as a Microsoft 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy.</span></span> <span data-ttu-id="ddd50-175">例如，在以下示例中，操作后缀以粗体突出显示：</span><span class="sxs-lookup"><span data-stu-id="ddd50-175">For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="ddd50-176">`skp127d7cf1076947929bf136b7a2a8c36f`**：1**</span><span class="sxs-lookup"><span data-stu-id="ddd50-176">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="ddd50-177">`mbx7cfb30345d454ac0a989ab3041051209`**：2**</span><span class="sxs-lookup"><span data-stu-id="ddd50-177">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="ddd50-178">`grp1a0a132ee8944501a4bb6a452ec31171`**：3**</span><span class="sxs-lookup"><span data-stu-id="ddd50-178">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="ddd50-179">下表定义了三种可能的保留操作：</span><span class="sxs-lookup"><span data-stu-id="ddd50-179">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="ddd50-180">值</span><span class="sxs-lookup"><span data-stu-id="ddd50-180">Value</span></span>  |<span data-ttu-id="ddd50-181">说明</span><span class="sxs-lookup"><span data-stu-id="ddd50-181">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ddd50-182">**1**</span><span class="sxs-lookup"><span data-stu-id="ddd50-182">**1**</span></span>     | <span data-ttu-id="ddd50-183">指示保留策略已配置为删除项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-183">Indicates that the retention policy is configured to delete items.</span></span> <span data-ttu-id="ddd50-184">策略不会保留项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-184">The policy doesn't retain items.</span></span>        |
|<span data-ttu-id="ddd50-185">**2**</span><span class="sxs-lookup"><span data-stu-id="ddd50-185">**2**</span></span>    |    <span data-ttu-id="ddd50-186">指示保留策略配置为保留项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-186">Indicates that the retention policy is configured to hold items.</span></span> <span data-ttu-id="ddd50-187">在保留期过期后，策略不会删除项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-187">The policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="ddd50-188">**第三章**</span><span class="sxs-lookup"><span data-stu-id="ddd50-188">**3**</span></span>     |   <span data-ttu-id="ddd50-189">指示保留策略配置为保留项目，然后在保留期过期后将其删除。</span><span class="sxs-lookup"><span data-stu-id="ddd50-189">Indicates that the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="ddd50-190">有关保留操作的详细信息，请参阅在 [特定时间段内保留内容](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) 一节。</span><span class="sxs-lookup"><span data-stu-id="ddd50-190">For more information about retention actions, see the [Retaining content for a specific period of time](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) section.</span></span>
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a><span data-ttu-id="ddd50-191">步骤2：使用 GUID 标识保留</span><span class="sxs-lookup"><span data-stu-id="ddd50-191">Step 2: Use the GUID to identify the hold</span></span>

<span data-ttu-id="ddd50-192">获取应用于邮箱的保留的 GUID 后，下一步是使用该 GUID 标识保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-192">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold.</span></span> <span data-ttu-id="ddd50-193">以下各节介绍如何使用保留 GUID 标识保留项的名称 (和其他信息) 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-193">The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="ddd50-194">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="ddd50-194">eDiscovery holds</span></span>

<span data-ttu-id="ddd50-195">在 Security & 合规性中心 PowerShell 中运行以下命令，以确定应用于邮箱的电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-195">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox.</span></span> <span data-ttu-id="ddd50-196">使用 GUID (不包括您在步骤1中确定的电子数据展示保留的 UniH 前缀) 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-196">Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="ddd50-197">第一个命令创建包含有关保留的信息的变量。</span><span class="sxs-lookup"><span data-stu-id="ddd50-197">The first command creates a variable that contains information about the hold.</span></span> <span data-ttu-id="ddd50-198">在其他命令中使用此变量。</span><span class="sxs-lookup"><span data-stu-id="ddd50-198">This variable is used in the other commands.</span></span> <span data-ttu-id="ddd50-199">第二个命令显示与保留相关联的电子数据展示事例的名称。</span><span class="sxs-lookup"><span data-stu-id="ddd50-199">The second command displays the name of the eDiscovery case the hold is associated with.</span></span> <span data-ttu-id="ddd50-200">第三个命令显示保留的名称和应用保留的邮箱列表。</span><span class="sxs-lookup"><span data-stu-id="ddd50-200">The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="ddd50-201">若要连接到安全 & 合规性中心 PowerShell，请参阅  [connect To Security & 合规性中心 powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ddd50-201">To connect to Security & Compliance Center PowerShell, see  [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="ddd50-202">就地保留</span><span class="sxs-lookup"><span data-stu-id="ddd50-202">In-Place Holds</span></span>

<span data-ttu-id="ddd50-203">在 Exchange Online PowerShell 中运行以下命令，以确定应用于邮箱的就地保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-203">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox.</span></span> <span data-ttu-id="ddd50-204">对您在步骤1中标识的就地保留使用 GUID。</span><span class="sxs-lookup"><span data-stu-id="ddd50-204">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> <span data-ttu-id="ddd50-205">该命令将显示保留的名称和应用保留的邮箱列表。</span><span class="sxs-lookup"><span data-stu-id="ddd50-205">The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

<span data-ttu-id="ddd50-206">如果就地保留的 GUID 以 `cld` 前缀开头，请确保在运行前一个命令时包含前缀。</span><span class="sxs-lookup"><span data-stu-id="ddd50-206">If the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddd50-207">随着我们继续投资保留邮箱内容的不同方式，我们宣布在 Exchange 管理中心 (EAC) 中停用就地保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-207">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="ddd50-208">从2020年6月1日开始，你将无法在 Exchange Online 中创建新的就地保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-208">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="ddd50-209">但您仍可以在 EAC 中管理就地保留或通过在 Exchange Online PowerShell 中使用 **new-mailboxsearch** cmdlet 来管理。</span><span class="sxs-lookup"><span data-stu-id="ddd50-209">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="ddd50-210">但是，从2020年10月1日开始，你将无法管理就地保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-210">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="ddd50-211">您只能将其从 EAC 中删除或使用 **new-mailboxsearch** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ddd50-211">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="ddd50-212">有关停用就地保留的详细信息，请参阅 [旧版电子数据展示工具的退休](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="ddd50-212">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>

### <a name="microsoft-365-retention-policies"></a><span data-ttu-id="ddd50-213">Microsoft 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="ddd50-213">Microsoft 365 retention policies</span></span>

<span data-ttu-id="ddd50-214">在 Security & 合规中心 PowerShell 中运行以下命令，以将 Microsoft 365 保留策略 (应用于该邮箱的组织范围或特定位置) 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-214">Run the following command in Security & Compliance Center PowerShell to identity the Microsoft 365 retention policy (organization-wide or specific location) that's applied to the mailbox.</span></span> <span data-ttu-id="ddd50-215">使用 GUID (不包括 mbx、skp 或 grp 前缀或您在步骤1中标识的操作后缀) 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-215">Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="ddd50-216">由于已将保留标签应用于文件夹或项目，因此标识邮箱处于保留状态</span><span class="sxs-lookup"><span data-stu-id="ddd50-216">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="ddd50-217">只要用户应用配置为保留内容或保留内容的保留标签，然后将内容删除到其邮箱中的任何文件夹或项目， *ComplianceTagHoldApplied* 邮箱属性将设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="ddd50-217">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="ddd50-218">发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留状态或分配给 Microsoft 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="ddd50-218">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a Microsoft 365 retention policy.</span></span> <span data-ttu-id="ddd50-219">当 *ComplianceTagHoldApplied* 属性设置为 **True**时，可能会出现以下情况：</span><span class="sxs-lookup"><span data-stu-id="ddd50-219">When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="ddd50-220">如果删除了邮箱或用户的用户帐户，则邮箱将成为 [非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ddd50-220">If the mailbox or the user's user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="ddd50-221">您不能禁用邮箱 (主邮箱或存档邮箱（如果已启用) ）。</span><span class="sxs-lookup"><span data-stu-id="ddd50-221">You aren't able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="ddd50-222">邮箱中的项目可能会超过预期的保留时间。</span><span class="sxs-lookup"><span data-stu-id="ddd50-222">Items in the mailbox may be retained longer than expected.</span></span> <span data-ttu-id="ddd50-223">这是因为邮箱处于保留状态，因此在清除)  (不会永久删除任何项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-223">This is because the mailbox is on hold and therefore no items are permanently deleted (purged).</span></span>

<span data-ttu-id="ddd50-224">若要查看 *ComplianceTagHoldApplied* 属性的值，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ddd50-224">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="ddd50-225">有关保留标签的详细信息，请参阅 [保留标签](retention.md#retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="ddd50-225">For more information about retention labels, see [retention labels](retention.md#retention-labels).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="ddd50-226">在延迟保留时管理邮箱</span><span class="sxs-lookup"><span data-stu-id="ddd50-226">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="ddd50-227">从邮箱中删除了任何类型的保留后，将应用 *延迟保留* 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-227">After any type of hold is removed from a mailbox, a *delay hold* is applied.</span></span> <span data-ttu-id="ddd50-228">这意味着，保留的实际删除延迟了30天，以防止数据被永久删除 (从邮箱中清除的) 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-228">This means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox.</span></span> <span data-ttu-id="ddd50-229">这使管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-229">This gives admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.</span></span> <span data-ttu-id="ddd50-230">在下一次托管文件夹助理处理邮箱并检测已删除保留时，会在邮箱上放置延迟保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-230">A delay hold is placed on a mailbox the next time the Managed Folder Assistant processes the mailbox and detects that a hold was removed.</span></span> <span data-ttu-id="ddd50-231">具体来说，当托管文件夹助理将下列邮箱属性之一设置为 **True**时，将对邮箱应用延迟保留：</span><span class="sxs-lookup"><span data-stu-id="ddd50-231">Specifically, a delay hold is applied to a mailbox when the Managed Folder Assistant sets one of the following mailbox properties to **True**:</span></span>

- <span data-ttu-id="ddd50-232">**DelayHoldApplied：** 此属性适用于与电子邮件相关的内容 (由使用 Outlook 和 web 上的 Outlook 的用户生成的) 存储在用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ddd50-232">**DelayHoldApplied:** This property applies to email-related content (generated by people using Outlook and Outlook on the web) that's stored in a user's mailbox.</span></span>

- <span data-ttu-id="ddd50-233">**DelayReleaseHoldApplied：** 此属性适用于基于云的内容 (由非 Outlook 应用程序生成，例如 Microsoft 团队、Microsoft Forms 和 Microsoft Yammer) ，存储在用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ddd50-233">**DelayReleaseHoldApplied:** This property applies to cloud-based content (generated by non-Outlook apps such as Microsoft Teams, Microsoft Forms, and Microsoft Yammer) that's stored in a user's mailbox.</span></span> <span data-ttu-id="ddd50-234">Microsoft 应用生成的云数据通常存储在用户邮箱的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ddd50-234">Cloud data generated by a Microsoft app is typically stored in a hidden folder in a user's mailbox.</span></span>
 
 <span data-ttu-id="ddd50-235">将 "延迟保留" 放在邮箱上 (当上述任一属性设置为 **True**) 时，邮箱仍被视为无限制保留持续时间的保留状态，就像邮箱处于诉讼保留状态一样。</span><span class="sxs-lookup"><span data-stu-id="ddd50-235">When a delay hold is placed on the mailbox (when either of the previous properties is set to **True**), the mailbox is still considered to be on hold for an unlimited hold duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="ddd50-236">30天后，延迟保留过期，Microsoft 365 将自动尝试删除延迟保留 (通过将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **False**) 以便删除保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-236">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the DelayHoldApplied or DelayReleaseHoldApplied property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="ddd50-237">在这两个属性都设置为 **False**后，在下一次由托管文件夹助理处理邮箱时，将清除标记为要删除的相应项。</span><span class="sxs-lookup"><span data-stu-id="ddd50-237">After either of these properties are set to **False**, the corresponding items that are marked for removal are purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="ddd50-238">若要查看邮箱的 DelayHoldApplied 和 DelayReleaseHoldApplied 属性的值，请在 Exchange Online PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ddd50-238">To view the values for the DelayHoldApplied and DelayReleaseHoldApplied properties for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

<span data-ttu-id="ddd50-239">若要在过期之前删除延迟保留，可以在 Exchange Online PowerShell 中运行一个 (或这两个命令) 以下命令，具体取决于要更改的属性：</span><span class="sxs-lookup"><span data-stu-id="ddd50-239">To remove the delay hold before it expires, you can run one (or both) the following commands in Exchange Online PowerShell, depending on which property you want to change:</span></span> 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="ddd50-240">或</span><span class="sxs-lookup"><span data-stu-id="ddd50-240">Or</span></span>
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="ddd50-241">您必须在 Exchange Online 中向您分配 "合法保留" 角色，才能使用 *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 参数。</span><span class="sxs-lookup"><span data-stu-id="ddd50-241">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameters.</span></span> 

<span data-ttu-id="ddd50-242">若要删除非活动邮箱的延迟保留，请在 Exchange Online PowerShell 中运行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="ddd50-242">To remove the delay hold on an inactive mailbox, run one of the following commands in Exchange Online PowerShell:</span></span>

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

<span data-ttu-id="ddd50-243">或</span><span class="sxs-lookup"><span data-stu-id="ddd50-243">Or</span></span>

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> <span data-ttu-id="ddd50-244">在上一命令中指定非活动邮箱的最佳方法是使用其可分辨名称或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="ddd50-244">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="ddd50-245">使用下列值之一有助于避免意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ddd50-245">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

<span data-ttu-id="ddd50-246">有关使用这些参数管理延迟保留的详细信息，请参阅 [设置邮箱](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="ddd50-246">For more information about using these parameters for managing delay holds, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="ddd50-247">在延迟保留时管理邮箱时，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="ddd50-247">Keep the following things in mind when managing a mailbox on delay hold:</span></span>

- <span data-ttu-id="ddd50-248">如果将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **True** ，并删除邮箱 (或相应的用户帐户) 删除，则邮箱将成为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="ddd50-248">If either the DelayHoldApplied or DelayReleaseHoldApplied property is set to **True** and a mailbox (or the corresponding user account) is deleted, the mailbox becomes an inactive mailbox.</span></span> <span data-ttu-id="ddd50-249">这是因为，如果将某个属性设置为 **True**，并在保留时删除邮箱导致非活动邮箱中的邮箱，则认为邮箱处于保留状态。</span><span class="sxs-lookup"><span data-stu-id="ddd50-249">That's because a mailbox is considered to be on hold if either property is set to **True**, and deleting a mailbox on hold results in an inactive mailbox.</span></span> <span data-ttu-id="ddd50-250">若要删除邮箱而不使其成为非活动邮箱，必须将这两个属性都设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="ddd50-250">To delete a mailbox and not make it an inactive mailbox, you have to set both properties to **False**.</span></span>

- <span data-ttu-id="ddd50-251">如前所述，如果 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **True**，则会将邮箱视为无限制保留持续时间的保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-251">As previous stated, a mailbox is considered to be on hold for an unlimited hold duration if either the DelayHoldApplied or DelayReleaseHoldApplied property is set to **True**.</span></span> <span data-ttu-id="ddd50-252">但是，这并不意味着保留邮箱中的 *所有* 内容。</span><span class="sxs-lookup"><span data-stu-id="ddd50-252">However, that doesn't mean that *all* content in the mailbox is preserved.</span></span> <span data-ttu-id="ddd50-253">这取决于设置为每个属性的值。</span><span class="sxs-lookup"><span data-stu-id="ddd50-253">It depends on the value that's set to each property.</span></span> <span data-ttu-id="ddd50-254">例如，假设这两个属性都设置为 **True** ，因为从邮箱中删除了保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-254">For example, let's say both properties are set to **True** because holds are removed from the mailbox.</span></span> <span data-ttu-id="ddd50-255">然后，使用 *RemoveDelayReleaseHoldApplied* 参数) 仅删除应用于非 Outlook 云数据 (的延迟保留。</span><span class="sxs-lookup"><span data-stu-id="ddd50-255">Then you remove only the delay hold that's applied to non-Outlook cloud data (by using the *RemoveDelayReleaseHoldApplied* parameter).</span></span> <span data-ttu-id="ddd50-256">托管文件夹助理下次处理邮箱时，将清除标记为要删除的非 Outlook 项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-256">The next time the Managed Folder Assistant processes the mailbox, the non-Outlook items marked for removal are purged.</span></span> <span data-ttu-id="ddd50-257">由于 DelayHoldApplied 属性仍设置为 **True**，因此不会清除任何标记为要删除的 Outlook 项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-257">Any Outlook items marked for removal won't be purged because the DelayHoldApplied property is still set to **True**.</span></span> <span data-ttu-id="ddd50-258">反之也是如此：如果将 DelayHoldApplied 设置为 **False** ，DelayReleaseHoldApplied 设置为 **true**，则仅清除标记为删除的 Outlook 项目。</span><span class="sxs-lookup"><span data-stu-id="ddd50-258">The opposite would also be true: if DelayHoldApplied is set to **False** and DelayReleaseHoldApplied is set to **True**, then only Outlook items marked for removal would be purged.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ddd50-259">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ddd50-259">Next steps</span></span>

<span data-ttu-id="ddd50-260">在确定了应用于邮箱的保留后，可以执行一些任务，如更改保留的持续时间、临时或永久删除保留或从 Microsoft 365 保留策略中排除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="ddd50-260">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or excluding an inactive mailbox from a Microsoft 365 retention policy.</span></span> <span data-ttu-id="ddd50-261">有关执行与保留相关的任务的详细信息，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="ddd50-261">For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="ddd50-262">在 Security & 合规性中心 PowerShell 中运行[AddExchangeLocationException \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)命令，以将邮箱从组织范围的 Microsoft 365 保留策略中排除。</span><span class="sxs-lookup"><span data-stu-id="ddd50-262">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Microsoft 365 retention policy.</span></span> <span data-ttu-id="ddd50-263">此命令仅可用于 *ExchangeLocation* 属性值等于的保留策略 `All` 。</span><span class="sxs-lookup"><span data-stu-id="ddd50-263">This command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="ddd50-264">在 Exchange Online PowerShell 中运行 "[设置邮箱-ExcludeFromOrgHolds \<hold GUID without prefix or suffix> ](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) " 命令，以从组织范围内的 Microsoft 365 保留策略中排除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="ddd50-264">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Microsoft 365 retention policy.</span></span>

- [<span data-ttu-id="ddd50-265">更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="ddd50-265">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="ddd50-266">删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="ddd50-266">Delete an inactive mailbox</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="ddd50-267">删除保留状态云邮箱的“可恢复的项目”文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="ddd50-267">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
