---
title: 在 Office 365 中更改非活动邮箱的保留期
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: 在 Office 365 邮箱变为非活动状态后，可以更改分配给非活动邮箱的保留或 Office 365 保留策略的持续时间。 保留期定义了"可恢复的项目"文件夹中的项目的保留持续时间。
ms.openlocfilehash: e1c2515c155192739e771bd646753f24bac92a2d
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558389"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="45cdd-104">在 Office 365 中更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="45cdd-104">Change the hold duration for an inactive mailbox in Office 365</span></span>

<span data-ttu-id="45cdd-105">非活动邮箱用于在离开组织后保留前一个员工的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="45cdd-105">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="45cdd-106">当诉讼保留、就地保留、Office 365 保留策略或与电子数据展示事例相关联的保留在邮箱中时，邮箱将变为非活动状态，并且相应的 Office 365 用户帐户将被删除。</span><span class="sxs-lookup"><span data-stu-id="45cdd-106">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, an Office 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding Office 365 user account is deleted.</span></span> <span data-ttu-id="45cdd-107">非活动邮箱的内容会在邮箱处于非活动状态之前放置在邮箱保留期间的保留时间内进行保留。</span><span class="sxs-lookup"><span data-stu-id="45cdd-107">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="45cdd-108">保留期定义了"可恢复的项目"文件夹中的项目的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="45cdd-108">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="45cdd-109">如果"可恢复的项目"文件夹中的项目的保留期过期，则此项目会从非活动邮箱中永久删除（清除）。</span><span class="sxs-lookup"><span data-stu-id="45cdd-109">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="45cdd-110">将邮箱设为非活动状态后，可以更改为非活动邮箱分配的保留或 Office 365 保留策略的持续时间。</span><span class="sxs-lookup"><span data-stu-id="45cdd-110">After a mailbox is made inactive, you can change the duration of the hold or Office 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="45cdd-111">随着我们继续投资保留邮箱内容的不同方式，我们宣布在 Exchange 管理中心中停用就地保留。</span><span class="sxs-lookup"><span data-stu-id="45cdd-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="45cdd-112">这意味着，应使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="45cdd-112">That means you should use Litigation Holds and Office 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="45cdd-113">从2020年4月1日开始，你将无法在 Exchange Online 中创建新的就地保留。</span><span class="sxs-lookup"><span data-stu-id="45cdd-113">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="45cdd-114">但您仍可以更改非活动邮箱上设置的就地保留的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="45cdd-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="45cdd-115">不过，从2020年6月1日开始，你将无法更改保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-115">However, starting July 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="45cdd-116">你将只能通过删除就地保留来删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="45cdd-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="45cdd-117">在删除保留之前，就地保留中的现有非活动邮箱仍将保留。</span><span class="sxs-lookup"><span data-stu-id="45cdd-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="45cdd-118">有关停用就地保留的详细信息，请参阅[旧版电子数据展示工具的退休](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="45cdd-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="45cdd-119">开始之前</span><span class="sxs-lookup"><span data-stu-id="45cdd-119">Before you begin</span></span>

- <span data-ttu-id="45cdd-120">您必须使用 Exchange Online PowerShell 更改非活动邮箱上的诉讼保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-120">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="45cdd-121">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="45cdd-121">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="45cdd-122">但您可以使用 Exchange Online PowerShell 或 EAC 更改就地保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-122">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="45cdd-123">您可以使用安全与合规中心或 Security & 合规性中心 PowerShell 更改 Office 365 保留策略的保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-123">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for an Office 365 retention policy.</span></span>
    
- <span data-ttu-id="45cdd-124">若要连接到 Exchange Online PowerShell 或 Security & 合规性中心 PowerShell，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="45cdd-124">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="45cdd-125">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="45cdd-125">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="45cdd-126">连接到 Office 365 安全与合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="45cdd-126">Connect to Office 365 Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="45cdd-127">与电子数据展示事例关联的保留是无限保留，这意味着没有可更改的保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-127">Holds associated with eDiscovery cases are infinite holds, which means there's no hold duration that can be changed.</span></span> <span data-ttu-id="45cdd-128">项目永久保留，或者在删除保留和删除非活动邮箱之前进行。</span><span class="sxs-lookup"><span data-stu-id="45cdd-128">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="45cdd-129">有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="45cdd-129">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="45cdd-130">第 1 步：识别非活动邮箱上设置的保留</span><span class="sxs-lookup"><span data-stu-id="45cdd-130">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="45cdd-131">由于不同类型的保留或一个或多个 Office 365 保留策略可能放置在非活动邮箱上，因此第一步是标识非活动邮箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="45cdd-131">Because different types of holds or one or more Office 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="45cdd-132">在 Exchange Online PowerShell 中运行以下命令，以显示组织中所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="45cdd-132">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

<span data-ttu-id="45cdd-133">如果 **LitigationHoldEnabled** 属性的值为 **True** ，则表示非活动邮箱被置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="45cdd-133">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="45cdd-134">如果非活动邮箱上设置了就地保留、电子数据展示保留或 Office 365 保留策略，则保留或保留策略的 GUID 将显示为**InPlaceHolds**属性的值。</span><span class="sxs-lookup"><span data-stu-id="45cdd-134">If an In-Place Hold, eDiscovery hold, or Office 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="45cdd-135">例如，下面显示了五个非活动邮箱的结果。</span><span class="sxs-lookup"><span data-stu-id="45cdd-135">For example, the following shows results for five inactive mailboxes.</span></span> 
  
||
|:-----|
|
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

<span data-ttu-id="45cdd-136">下表列出了用于将每个邮箱设为非活动状态的五种不同的保留类型。</span><span class="sxs-lookup"><span data-stu-id="45cdd-136">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="45cdd-137">**非活动邮箱**</span><span class="sxs-lookup"><span data-stu-id="45cdd-137">**Inactive mailbox**</span></span>|<span data-ttu-id="45cdd-138">**保留类型**</span><span class="sxs-lookup"><span data-stu-id="45cdd-138">**Hold type**</span></span>|<span data-ttu-id="45cdd-139">**如何标识非活动邮箱上的保留**</span><span class="sxs-lookup"><span data-stu-id="45cdd-139">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45cdd-140">王小姐 Beebe</span><span class="sxs-lookup"><span data-stu-id="45cdd-140">Ann Beebe</span></span>  <br/> |<span data-ttu-id="45cdd-141">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="45cdd-141">Litigation Hold</span></span>  <br/> |<span data-ttu-id="45cdd-142">*LitigationHoldEnabled*属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="45cdd-142">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="45cdd-143">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="45cdd-143">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="45cdd-144">就地保留</span><span class="sxs-lookup"><span data-stu-id="45cdd-144">In-Place Hold</span></span>  <br/> |<span data-ttu-id="45cdd-145">*InPlaceHolds*属性包含非活动邮箱上设置的就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="45cdd-145">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="45cdd-146">您可以指示这是就地保留，因为 ID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="45cdd-146">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="45cdd-147">您可以使用 Exchange `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Online PowerShell 中的命令来获取非活动邮箱的就地保留的相关信息。</span><span class="sxs-lookup"><span data-stu-id="45cdd-147">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="45cdd-148">Mario Necaise</span><span class="sxs-lookup"><span data-stu-id="45cdd-148">Mario Necaise</span></span>  <br/> |<span data-ttu-id="45cdd-149">安全 & 合规中心中的组织范围内的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="45cdd-149">Organization-wide Office 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="45cdd-150">*InPlaceHolds*属性为空。</span><span class="sxs-lookup"><span data-stu-id="45cdd-150">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="45cdd-151">这表示一个或多个组织范围或（Exchange wide） Office 365 保留策略应用于非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="45cdd-151">This indicates that one or more organization-wide or (Exchange-wide) Office 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="45cdd-152">在这种情况下，您可以`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`在 Exchange Online PowerShell 中运行命令，以获取组织范围内的 Office 365 保留策略的 guid 列表。</span><span class="sxs-lookup"><span data-stu-id="45cdd-152">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="45cdd-153">应用于 Exchange 邮箱的组织范围的保留策略的 GUID 以`mbx`前缀开头;例如， `mbxa3056bb15562480fadb46ce523ff7b02`。</span><span class="sxs-lookup"><span data-stu-id="45cdd-153">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="45cdd-154">若要标识应用于非活动邮箱的 Office 365 保留策略，请在 Security & 合规性中心 PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="45cdd-154">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="45cdd-155">Carol Olson</span><span class="sxs-lookup"><span data-stu-id="45cdd-155">Carol Olson</span></span>  <br/> |<span data-ttu-id="45cdd-156">在应用于特定邮箱的安全性 & 合规性中心中的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="45cdd-156">Office 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="45cdd-157">*InPlaceHolds*属性包含应用于非活动邮箱的 Office 365 保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="45cdd-157">The  *InPlaceHolds*  property contains the GUID of the Office 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="45cdd-158">您可以告诉这是应用于特定邮箱的保留策略，因为 GUID 以`mbx`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="45cdd-158">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="45cdd-159">如果应用于非活动邮箱的保留策略的 GUID 是使用`skp`前缀启动的，则会显示该保留策略应用于 Skype for business 会话。</span><span class="sxs-lookup"><span data-stu-id="45cdd-159">If the GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, it would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="45cdd-160">若要标识应用于非活动邮箱的 Office 365 保留策略，请在 Security & 合规性中心 PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="45cdd-160">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="45cdd-161">运行此命令时， `mbx`请`skp`务必删除或前缀。</span><span class="sxs-lookup"><span data-stu-id="45cdd-161">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="45cdd-162">Abraham McMahon</span><span class="sxs-lookup"><span data-stu-id="45cdd-162">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="45cdd-163">安全 & 合规中心中的电子数据展示案例保留</span><span class="sxs-lookup"><span data-stu-id="45cdd-163">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="45cdd-164">*InPlaceHolds*属性包含非活动邮箱上所放置的电子数据展示事例保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="45cdd-164">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="45cdd-165">你可以告诉这是电子数据展示事例保留，因为 GUID 以`UniH`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="45cdd-165">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="45cdd-166">您可以使用 Security `Get-CaseHoldPolicy` & 合规性中心 PowerShell 中的 cmdlet，以获取有关非活动邮箱上保留的电子数据展示事例的相关信息。</span><span class="sxs-lookup"><span data-stu-id="45cdd-166">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="45cdd-167">例如，您可以运行命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`以显示非活动邮箱上的事例保留的名称。</span><span class="sxs-lookup"><span data-stu-id="45cdd-167">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="45cdd-168">运行此命令时， `UniH`请务必删除前缀。</span><span class="sxs-lookup"><span data-stu-id="45cdd-168">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="45cdd-169">若要标识非活动邮箱上的保留的电子数据展示事例与关联，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="45cdd-169">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="45cdd-170">**注意：** 建议不要对非活动邮箱使用电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="45cdd-170">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="45cdd-171">这是因为电子数据展示事例适用于与法律问题相关的特定的与时间绑定的情况。</span><span class="sxs-lookup"><span data-stu-id="45cdd-171">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="45cdd-172">有时，法律案例可能会结束，与事例关联的保留将被删除，并且电子数据展示事例将关闭（或删除）。</span><span class="sxs-lookup"><span data-stu-id="45cdd-172">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="45cdd-173">实际上，如果在非活动邮箱上设置的保留与电子数据展示事例相关联，并且已释放保留或电子数据展示事例关闭或删除，则非活动邮箱将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="45cdd-173">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="45cdd-174">有关 Office 365 保留策略的详细信息，请参阅[保留策略概述](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="45cdd-174">For more information about Office 365 retention policies, see [Overview of retention policies](retention-policies.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="45cdd-175">第 2 步：更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="45cdd-175">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="45cdd-176">在确定了非活动邮箱上设置的保留的类型（以及是否设置多个保留）后，下一步就要更改保留期了。</span><span class="sxs-lookup"><span data-stu-id="45cdd-176">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="45cdd-177">更改诉讼保留的保留期</span><span class="sxs-lookup"><span data-stu-id="45cdd-177">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="45cdd-178">下面介绍了如何使用 Exchange Online PowerShell 更改非活动邮箱上的诉讼保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-178">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span></span> <span data-ttu-id="45cdd-179">不能使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="45cdd-179">You can't use the EAC.</span></span> <span data-ttu-id="45cdd-180">运行以下命令，更改保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-180">Run the following command to change the hold duration.</span></span> <span data-ttu-id="45cdd-181">在此示例中，可将保留期更改为无限期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-181">In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="45cdd-182">结果是非活动邮箱中的项目会无限期保留，或者直到删除保留或保留持续时间更改为其他值。</span><span class="sxs-lookup"><span data-stu-id="45cdd-182">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="45cdd-p114">标识非活动邮箱的最佳方式是使用 **Distinguished Name** 或 **Exchange GUID** 值。 使用下列值之一有助于避免意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="45cdd-p114">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="45cdd-185">更改就地保留的保留期</span><span class="sxs-lookup"><span data-stu-id="45cdd-185">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="45cdd-186">您可以使用 EAC 或 Exchange Online PowerShell 更改就地保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-186">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="45cdd-187">使用 EAC 更改保留期</span><span class="sxs-lookup"><span data-stu-id="45cdd-187">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="45cdd-188">如果您知道要更改的就地保留的名称，请转到下一步。</span><span class="sxs-lookup"><span data-stu-id="45cdd-188">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="45cdd-189">如果不知道，请运行以下命令，获取非活动邮箱上设置的就地保留的名称。</span><span class="sxs-lookup"><span data-stu-id="45cdd-189">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="45cdd-190">使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="45cdd-190">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="45cdd-191">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="45cdd-191">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="45cdd-192">选择要更改的就地保留，然后选择 "**编辑** ![" "编辑" 图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="45cdd-192">Select the In-Place Hold you want to change, and then select **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="45cdd-193">在 "**就地电子数据展示&amp;保留**属性" 页上，选择 "**就地保留**"。</span><span class="sxs-lookup"><span data-stu-id="45cdd-193">On the **In-Place eDiscovery &amp; Hold** properties page, select **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="45cdd-194">。</span><span class="sxs-lookup"><span data-stu-id="45cdd-194">Do one of the following based on the current hold duration:</span></span>
    
    1. <span data-ttu-id="45cdd-195">选择 "**无限期保留**" 可无限期地保留项目。</span><span class="sxs-lookup"><span data-stu-id="45cdd-195">Select **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
    2. <span data-ttu-id="45cdd-196">选择 "**指定保留的天数" 相对于其接收日期的项目**，以在特定时间段内保留项目。</span><span class="sxs-lookup"><span data-stu-id="45cdd-196">Select **Specify number of days to hold items relative to their received date** to hold items for a specific period.</span></span> <span data-ttu-id="45cdd-197">键入所需的项目保留天数。</span><span class="sxs-lookup"><span data-stu-id="45cdd-197">Type the number of days that you want to hold items for.</span></span> 
    
    ![单击"指定自接收日期起保留邮件的天数"可以在特定的时间段内保留项目。](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="45cdd-199">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="45cdd-199">Select **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="45cdd-200">使用 Exchange Online PowerShell 更改保留期</span><span class="sxs-lookup"><span data-stu-id="45cdd-200">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="45cdd-201">如果您知道要更改的就地保留的名称，请转到下一步。</span><span class="sxs-lookup"><span data-stu-id="45cdd-201">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="45cdd-202">如果不知道，请运行以下命令，获取非活动邮箱上设置的就地保留的名称。</span><span class="sxs-lookup"><span data-stu-id="45cdd-202">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="45cdd-203">使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="45cdd-203">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="45cdd-204">运行以下命令，更改保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-204">Run the following command to change the hold duration.</span></span> <span data-ttu-id="45cdd-205">在此示例中，保留期更改为2555天（约为七年）。</span><span class="sxs-lookup"><span data-stu-id="45cdd-205">In this example, the hold duration is changed to 2,555 days (approximately seven years).</span></span> 
    
    ```powershell
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="45cdd-206">运行以下命令，更改保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-206">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="45cdd-207">详细信息</span><span class="sxs-lookup"><span data-stu-id="45cdd-207">More information</span></span>

- <span data-ttu-id="45cdd-p119">**如何计算非活动邮箱中项目的保留期？** 保留期从邮箱项目的接收或创建原始日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="45cdd-p119">**How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="45cdd-210">**当保留期过期时，会怎么样？**</span><span class="sxs-lookup"><span data-stu-id="45cdd-210">**What happens when the hold duration expires?**</span></span> <span data-ttu-id="45cdd-211">当 "可恢复的项目" 文件夹中某个邮箱项目的保留持续时间过期时，将从非活动邮箱中永久删除（清除）此项目。</span><span class="sxs-lookup"><span data-stu-id="45cdd-211">When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="45cdd-212">如果没有为非活动邮箱上的保留指定持续时间，则永远不会清除 "可恢复的项目" 文件夹中的项目（除非对非活动邮箱的保留期进行了更改）。</span><span class="sxs-lookup"><span data-stu-id="45cdd-212">If there's no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="45cdd-213">**是否仍在非活动邮箱上处理 Exchange 保留策略？**</span><span class="sxs-lookup"><span data-stu-id="45cdd-213">**Is an Exchange retention policy still processed on inactive mailboxes?**</span></span> <span data-ttu-id="45cdd-214">如果 Exchange 保留策略（Exchange Online 中的 "邮件记录管理" 或 "MRM" 功能）在邮箱变为非活动状态时应用于该邮箱，则将继续在非活动邮箱上处理删除策略（即，使用**删除**保留操作配置的保留标记）。</span><span class="sxs-lookup"><span data-stu-id="45cdd-214">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span></span> <span data-ttu-id="45cdd-215">也就是说，在保留期过期时，标记有删除策略的项目会移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="45cdd-215">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span></span> <span data-ttu-id="45cdd-216">当项目的保留期过期时，这些项目会从非活动邮箱中清除。</span><span class="sxs-lookup"><span data-stu-id="45cdd-216">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="45cdd-p122">当项目的保留期过期时，这些项目会从非活动邮箱中清除。 相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 MoveToArchive 保留操作的保留标记）会遭到忽略。也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。这些项目不会移到存档邮箱或其中的"可恢复的项目"文件夹内。由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。 相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 MoveToArchive 保留操作的保留标记）会遭到忽略。 也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="45cdd-p122">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="45cdd-221">由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。</span><span class="sxs-lookup"><span data-stu-id="45cdd-221">**To check the new hold duration, run one of the following commands.**</span></span> <span data-ttu-id="45cdd-222">第一个命令适用于诉讼保留;第二个用于就地保留。</span><span class="sxs-lookup"><span data-stu-id="45cdd-222">The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```powershell
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="45cdd-223">**托管文件夹助理 (MFA) 还会处理非活动邮箱，就像处理常规邮箱一样。**</span><span class="sxs-lookup"><span data-stu-id="45cdd-223">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.**</span></span> <span data-ttu-id="45cdd-224">在 Exchange Online 中，MFA 大约每七天处理一次邮箱。</span><span class="sxs-lookup"><span data-stu-id="45cdd-224">In Exchange Online, the MFA processes mailboxes approximately once every seven days.</span></span> <span data-ttu-id="45cdd-225">更改非活动邮箱的保留期后，您可以使用 **Start-ManagedFolderAssistant** cmdlet 立即开始处理非活动邮箱的新保留期。</span><span class="sxs-lookup"><span data-stu-id="45cdd-225">After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox.</span></span> <span data-ttu-id="45cdd-226">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="45cdd-226">Run the following command.</span></span> 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="45cdd-227">**如果将多个保留放在非活动邮箱上，则不会显示所有保留 Guid。**</span><span class="sxs-lookup"><span data-stu-id="45cdd-227">**If many holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="45cdd-228">您可以运行以下命令来显示非活动邮箱上的所有保留项（诉讼保留除外）的 Guid。</span><span class="sxs-lookup"><span data-stu-id="45cdd-228">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
