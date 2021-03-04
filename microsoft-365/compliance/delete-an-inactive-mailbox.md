---
title: 删除非活动邮箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: 当不再需要保留 Microsoft 365 非活动邮箱的内容时，可以永久删除非活动邮箱。
ms.openlocfilehash: 0e5a56fce7f41b0c3b30e56aefbaae0593470756
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423209"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="df04a-103">删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="df04a-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="df04a-104">非活动邮箱用于在之前的员工离开公司之后保留其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="df04a-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="df04a-105">如果您不再需要保留非活动邮箱的内容，可以通过删除保留永久性地删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="df04a-106">此外，还可以对非活动邮箱设置多个保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="df04a-107">例如，非活动邮箱上可以设置诉讼保留以及一个或多个就地保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="df04a-108">此外，在 Office 365 (Microsoft 365 安全与合规中心创建的保留策略) 可能会应用于非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="df04a-109">您必须从非活动邮箱中删除所有保留和保留策略，以将其删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="df04a-110">删除保留和保留策略后，非活动邮箱将被标记为删除，处理后将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="df04a-111">由于我们将继续以不同方式投资来保留邮箱内容，我们宣布在 Exchange 管理中心In-Place保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="df04a-112">这意味着你应该使用诉讼保留和保留策略来创建非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="df04a-113">从 2020 年 7 月 1 日开始，你将无法在 Exchange Online In-Place保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="df04a-114">但你仍然可以更改非活动邮箱上In-Place保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="df04a-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="df04a-115">但是，从 2020 年 10 月 1 日起，将不能更改保留期。</span><span class="sxs-lookup"><span data-stu-id="df04a-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="df04a-116">你仅能删除非活动邮箱，只需删除In-Place保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="df04a-117">在删除保留之前，In-Place处于保留状态的现有非活动邮箱仍将保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="df04a-118">有关停用保留In-Place，请参阅停用 [旧版电子数据展示工具](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="df04a-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="df04a-119">请参阅[详细信息](#more-information)部分了解从非活动邮箱删除保留后会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="df04a-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="df04a-120">删除非活动邮箱之前</span><span class="sxs-lookup"><span data-stu-id="df04a-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="df04a-121">您必须使用 Exchange Online PowerShell 从非活动邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="df04a-122">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="df04a-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="df04a-123">有关分步说明，请参阅[连接 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="df04a-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="df04a-124">在删除保留设置和非活动邮箱之前，您可以将非活动邮箱的内容复制到另一个邮箱中。</span><span class="sxs-lookup"><span data-stu-id="df04a-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="df04a-125">有关详细信息，请参阅 [在 Office 365 中还原非活动邮箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="df04a-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="df04a-126">如果从非活动邮箱中删除保留策略或保留策略，并且邮箱的软删除邮箱保留期已过期，则邮箱将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="df04a-127">在此邮箱删除后，您将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="df04a-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="df04a-128">在删除保留设置之前，请确保您不再需要此邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="df04a-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="df04a-129">如果您想重新激活非活动邮箱，则可以恢复它。</span><span class="sxs-lookup"><span data-stu-id="df04a-129">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="df04a-130">有关详细信息，请参阅["恢复 Office 365 中的非活动邮箱"。](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="df04a-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="df04a-131">有关非活动邮箱的信息，请参阅 [Office 365](inactive-mailboxes-in-office-365.md)中的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="df04a-132">第 1 步：识别非活动邮箱上设置的保留</span><span class="sxs-lookup"><span data-stu-id="df04a-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="df04a-133">如前所述，可能会将诉讼保留、In-Place保留或保留策略置于非活动邮箱上。</span><span class="sxs-lookup"><span data-stu-id="df04a-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="df04a-134">第一步是识别非活动邮箱上设置的保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="df04a-135">运行以下命令，显示组织中所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="df04a-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="df04a-136">如果 **LitigationHoldEnabled** 属性的值为 **True** ，则表示非活动邮箱被置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="df04a-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="df04a-137">如果非活动邮箱被置于就地保留状态，则保留的 GUID 会显示为 **InPlaceHolds** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="df04a-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="df04a-138">例如，以下两个非活动邮箱的结果显示 Ann Beebe 上已设置诉讼保留，并且 pilar Pinilla 上In-Place保留和保留策略。</span><span class="sxs-lookup"><span data-stu-id="df04a-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="df04a-139">如果对非In-Place邮箱设置大量保留或保留策略，则In-Place所有保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="df04a-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="df04a-140">可以运行以下命令来显示 InPlaceHolds 属性中的所有 GUID：  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="df04a-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="df04a-141">有关标识保留项详细信息，请参阅如何 [标识邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="df04a-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="df04a-142">步骤 2：从非活动邮箱删除保留</span><span class="sxs-lookup"><span data-stu-id="df04a-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="df04a-p109">在确定了非活动邮箱上设置的保留类型（以及是否存在多个保留）后，接下来是删除邮箱上的保留。如前所述，您必须删除所有保留后方可永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-p109">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="df04a-145">删除诉讼保留</span><span class="sxs-lookup"><span data-stu-id="df04a-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="df04a-p110">如前所述，您必须使用 Windows PowerShell 从非活动邮箱删除诉讼保留。不能使用 EAC。运行以下命令以删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-p110">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="df04a-p111">若要识别非活动邮箱，最好的方法是通过其可分辨名称或 Exchange GUID 值。使用下列值之一有助于防止意外地指定了错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-p111">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="df04a-151">从保留策略中删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="df04a-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="df04a-152">从 Microsoft 365 保留策略中删除非活动邮箱的过程取决于分配给非活动邮箱的保留策略是组织范围的还是显式的。</span><span class="sxs-lookup"><span data-stu-id="df04a-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="df04a-153">分配给非活动邮箱的保留策略类型。</span><span class="sxs-lookup"><span data-stu-id="df04a-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="df04a-154">分配给组织内所有邮箱的组织范围的保留策略。</span><span class="sxs-lookup"><span data-stu-id="df04a-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="df04a-155">使用 Exchange Online PowerShell **中的 Get-OrganizationConfig** cmdlet 获取有关组织范围的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="df04a-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="df04a-156">分配给特定邮箱的特定位置保留策略。</span><span class="sxs-lookup"><span data-stu-id="df04a-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="df04a-157">这些是分配给特定用户的内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="df04a-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="df04a-158">使用 Exchange Online PowerShell 中的 **Get-Mailbox -IncludeInactiveMailbox** cmdlet 获取有关分配给特定非活动邮箱的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="df04a-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="df04a-159">从组织范围的保留策略中删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="df04a-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="df04a-160">在 Exchange Online PowerShell 中运行以下命令，从组织范围的保留策略中排除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="df04a-161">有关标识应用于非活动邮箱的组织范围的保留策略并获取保留策略的 GUID 详细信息，请参阅"如何标识邮箱上置于的保留类型"中的"Get-OrganizationConfig"[部分。](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="df04a-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="df04a-162">或者，可以运行以下命令从所有组织范围内的策略中删除非活动邮箱：</span><span class="sxs-lookup"><span data-stu-id="df04a-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="df04a-163">从特定位置保留策略中删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="df04a-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="df04a-164">在安全与合规& [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 中运行以下命令，从显式保留策略中删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-164">Run the following command in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="df04a-165">有关标识应用于非活动邮箱的特定位置保留策略并获取保留策略的 GUID 详细信息，请参阅"如何标识邮箱上放置的保留类型"中的"Get-Mailbox" [部分](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="df04a-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="df04a-166">删除就地保留</span><span class="sxs-lookup"><span data-stu-id="df04a-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="df04a-167">有两种方法可以从非活动邮箱删除就地保留：</span><span class="sxs-lookup"><span data-stu-id="df04a-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="df04a-168">**删除In-Place保留对象** 如果要永久删除的非活动邮箱是邮件保留In-Place源邮箱，则只需删除In-Place保留对象。</span><span class="sxs-lookup"><span data-stu-id="df04a-168">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="df04a-p115">您必须先禁用该保留，然后才能删除就地保留对象。如果尝试删除启用了该保留的就地保留对象，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="df04a-p115">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="df04a-171">**删除非活动邮箱作为非活动邮箱的源In-Place保留** 如果要将其他源邮箱保留为In-Place保留，可以从源邮箱列表中删除非活动邮箱，并保留In-Place保留对象。</span><span class="sxs-lookup"><span data-stu-id="df04a-171">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="df04a-172">删除In-Place保留</span><span class="sxs-lookup"><span data-stu-id="df04a-172">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="df04a-p116">创建一个变量，其中包含您想要删除的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="df04a-p116">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="df04a-175">禁用就地保留上的该保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-175">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="df04a-176">删除该就地保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-176">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="df04a-177">从邮箱保留中删除非In-Place邮箱</span><span class="sxs-lookup"><span data-stu-id="df04a-177">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="df04a-178">如果就地保留中包含大量的源邮箱，则非活动邮箱有可能不会列在 EAC 的“源”页面上。</span><span class="sxs-lookup"><span data-stu-id="df04a-178">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="df04a-179">在编辑就地保留时，“源”页面上最多显示 3000 个邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-179">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="df04a-180">如果未在"源"页上列出非活动邮箱，可以使用 Exchange Online PowerShell 将其从"保留In-Place中删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-180">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="df04a-p118">创建一个变量，其中包含非活动邮箱上设置的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="df04a-p118">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="df04a-183">验证非活动邮箱是否作为就地保留的源邮箱列出。</span><span class="sxs-lookup"><span data-stu-id="df04a-183">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="df04a-184">保留的 *Sources* 属性In-Place *其 LegacyExchangeDN* 属性标识源邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-184">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="df04a-185">由于此属性唯一标识非活动邮箱，因此使用"保留In-Place源属性有助于防止删除错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-185">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="df04a-186">如果两个邮箱具有相同的别名或 SMTP 地址，这还有助于避免出现问题。</span><span class="sxs-lookup"><span data-stu-id="df04a-186">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="df04a-187">从变量中的源邮箱列表删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-187">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="df04a-188">请务必使用上一步中的命令返回的非活动邮箱的 **LegacyExchangeDN。**</span><span class="sxs-lookup"><span data-stu-id="df04a-188">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="df04a-189">例如，以下命令将删除 Pilar Pinilla 的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-189">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="df04a-190">验证非活动邮箱已从变量中的源邮箱列表中删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-190">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="df04a-191">使用源邮箱的更新列表（其中不包括非活动邮箱）修改就地保留。</span><span class="sxs-lookup"><span data-stu-id="df04a-191">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="df04a-192">验证非活动邮箱已从就地保留的源邮箱列表中删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-192">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="df04a-193">更多信息</span><span class="sxs-lookup"><span data-stu-id="df04a-193">More information</span></span>

- <span data-ttu-id="df04a-194">**非活动邮箱是一种软删除邮箱。**</span><span class="sxs-lookup"><span data-stu-id="df04a-194">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="df04a-195">在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-195">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="df04a-196">Exchange Online 中的软删除邮箱保留期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="df04a-196">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="df04a-197">这意味着该邮箱可以在软删除后 30 天内进行恢复。</span><span class="sxs-lookup"><span data-stu-id="df04a-197">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="df04a-198">30 天后，软删除邮箱将标记为永久删除并且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="df04a-198">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="df04a-199">**如果删除非活动邮箱的保留设置，后面会怎么样？**</span><span class="sxs-lookup"><span data-stu-id="df04a-199">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="df04a-200">系统会将此邮箱与其他软删除邮箱视为一类，并在 30 天软删除邮箱保留期过期后将其标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-200">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="df04a-201">此保留期的起始日以该邮箱初次变为非活动状态的日期为准。</span><span class="sxs-lookup"><span data-stu-id="df04a-201">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="df04a-202">此日期称为软删除日期，即删除相应用户帐户的日期，或者使用 **Remove-Mailbox** cmdlet 删除 Exchange Online 邮箱的日期。</span><span class="sxs-lookup"><span data-stu-id="df04a-202">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="df04a-203">软删除日期不是您删除保留的日期。</span><span class="sxs-lookup"><span data-stu-id="df04a-203">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="df04a-204">**在您删除非活动邮箱的保留设置后，系统会立即永久删除此邮箱吗？**</span><span class="sxs-lookup"><span data-stu-id="df04a-204">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="df04a-205">如果非活动邮箱的软删除日期是在 30 天之前，则系统不会在您删除保留设置后立即永久删除此邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-205">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="df04a-206">该邮箱将标记为永久删除，并在下次处理时删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-206">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span>

- <span data-ttu-id="df04a-207">**软删除邮箱保留期对非活动邮箱有何影响？**</span><span class="sxs-lookup"><span data-stu-id="df04a-207">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="df04a-208">如果非活动邮箱的软删除日期距离之后的保留设置删除日期有 30 多天，则系统会将此邮箱标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-208">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="df04a-209">不过，如果距离非活动邮箱的软删除日期还不到 30 天并且您删除保留设置，则您可以在软删除邮箱保留期过期之前恢复此邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-209">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="df04a-210">有关详细信息，请参阅 [删除或还原 Exchange Online 中的用户邮箱](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="df04a-210">For details, see [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span></span> <span data-ttu-id="df04a-211">在软删除邮箱保留期过期后，您可以按照相关步骤操作，恢复非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="df04a-211">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="df04a-212">有关详细信息，请参阅["恢复 Office 365 中的非活动邮箱"。](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="df04a-212">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="df04a-213">**在删除保留设置后，如何显示非活动邮箱的相关信息？**</span><span class="sxs-lookup"><span data-stu-id="df04a-213">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="df04a-214">删除保留且非活动邮箱恢复为软删除邮箱后，不会通过  *将 InactiveMailboxOnly*  参数与 **Get-Mailbox** cmdlet 一同使用返回。</span><span class="sxs-lookup"><span data-stu-id="df04a-214">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="df04a-215">但是，您可以使用 **Get-Mailbox -SoftDeletedMailbox** 命令显示有关邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="df04a-215">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="df04a-216">例如：</span><span class="sxs-lookup"><span data-stu-id="df04a-216">For example:</span></span>

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  <span data-ttu-id="df04a-217">在上例中 *，WhenSoftDeleted* 属性标识软删除日期，本示例中为 2014 年 10 月 30 日。</span><span class="sxs-lookup"><span data-stu-id="df04a-217">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="df04a-218">如果此软删除邮箱以前是已删除其保留的非活动邮箱，它将在 *WhenSoftDeleted* 属性的值 30 天后永久删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-218">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="df04a-219">在本例中，该邮箱将在 2014 年 11 月 30 日之后永久删除。</span><span class="sxs-lookup"><span data-stu-id="df04a-219">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>
