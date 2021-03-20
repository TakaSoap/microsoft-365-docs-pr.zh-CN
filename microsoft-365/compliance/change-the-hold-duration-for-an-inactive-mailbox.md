---
title: 更改非活动邮箱的保留期
f1.keywords:
- NOCSH
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
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Office 365 邮箱变为非活动邮箱后，更改分配给非活动邮箱的保留期或 Office 365 保留策略。
ms.openlocfilehash: 49d133c64763cee12cb26e27d372a16ba4ad7e94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918198"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="33734-103">更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="33734-103">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="33734-104">非活动邮箱用于在前员工离开组织后保留其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="33734-104">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="33734-105">当邮箱上设置诉讼保留、In-Place 保留、Microsoft 365 保留策略或与电子数据展示案例关联的保留时，邮箱将变为非活动状态，并删除相应的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="33734-105">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, a Microsoft 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding user account is deleted.</span></span> <span data-ttu-id="33734-106">在非活动邮箱变为非活动邮箱之前，非活动邮箱的内容将在邮箱上置于保留状态期间保留。</span><span class="sxs-lookup"><span data-stu-id="33734-106">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="33734-107">保留期定义了"可恢复的项目"文件夹中的项目的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="33734-107">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="33734-108">如果"可恢复的项目"文件夹中的项目的保留期过期，则此项目会从非活动邮箱中永久删除（清除）。</span><span class="sxs-lookup"><span data-stu-id="33734-108">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="33734-109">邮箱变为非活动邮箱后，可以更改保留期或分配给非活动邮箱的 Microsoft 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="33734-109">After a mailbox is made inactive, you can change the duration of the hold or Microsoft 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="33734-110">由于我们将继续以不同方式投资来保留邮箱内容，因此我们将宣布在 Exchange 管理中心停用 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="33734-110">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="33734-111">这意味着您应该使用诉讼保留和 Microsoft 365 保留策略来创建非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="33734-111">That means you should use Litigation Holds and Microsoft 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="33734-112">从 2020 年 4 月 1 日起，将无法在 Exchange Online In-Place保留项。</span><span class="sxs-lookup"><span data-stu-id="33734-112">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="33734-113">但你仍然可以更改非活动邮箱上In-Place保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-113">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="33734-114">但是，从 2020 年 7 月 1 日开始，将不能更改保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-114">However, starting July 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="33734-115">仅能删除非活动邮箱，即删除"In-Place保留"。</span><span class="sxs-lookup"><span data-stu-id="33734-115">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="33734-116">在删除保留之前，In-Place处于保留状态的现有非活动邮箱仍将保留。</span><span class="sxs-lookup"><span data-stu-id="33734-116">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="33734-117">有关停用保留In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="33734-117">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
## <a name="connect-to-powershell"></a><span data-ttu-id="33734-118">连接到 PowerShell</span><span class="sxs-lookup"><span data-stu-id="33734-118">Connect to PowerShell</span></span>

- <span data-ttu-id="33734-119">您必须使用 Exchange Online PowerShell 更改非活动邮箱上诉讼保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-119">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="33734-120">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="33734-120">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="33734-121">但是，您可以使用 Exchange Online PowerShell 或 EAC 更改保留期In-Place保留。</span><span class="sxs-lookup"><span data-stu-id="33734-121">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="33734-122">可以使用安全与合规中心或安全与合规&中心 PowerShell 更改 Microsoft 365 保留策略的保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-122">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for a Microsoft 365 retention policy.</span></span>
    
- <span data-ttu-id="33734-123">若要连接到 Exchange Online PowerShell 或安全&合规中心 PowerShell，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="33734-123">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="33734-124">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="33734-124">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [<span data-ttu-id="33734-125">连接到安全与合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="33734-125">Connect to Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)
    
- <span data-ttu-id="33734-126">与电子数据展示事例关联的保留是无限期保留，这意味着没有可更改的保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-126">Holds associated with eDiscovery cases are infinite holds, which means there's no hold duration that can be changed.</span></span> <span data-ttu-id="33734-127">项目将永久保留，或一直保留到删除保留并删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="33734-127">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="33734-128">有关非活动邮箱详细信息，请参阅 [Microsoft 365](inactive-mailboxes-in-office-365.md)中的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="33734-128">For more information about inactive mailboxes, see [Inactive mailboxes in Microsoft 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="33734-129">第 1 步：识别非活动邮箱上设置的保留</span><span class="sxs-lookup"><span data-stu-id="33734-129">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="33734-130">由于不同类型的保留或一个或多个 Microsoft 365 保留策略可能会置于非活动邮箱上，因此第一步是标识非活动邮箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="33734-130">Because different types of holds or one or more Microsoft 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="33734-131">在 Exchange Online PowerShell 中运行以下命令，以显示组织中所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="33734-131">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

<span data-ttu-id="33734-132">如果 **LitigationHoldEnabled** 属性的值为 **True** ，则表示非活动邮箱被置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="33734-132">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="33734-133">如果将In-Place保留、电子数据展示保留或 Microsoft 365 保留策略置于非活动邮箱上，则保留或保留策略的 GUID 将显示为 **InPlaceHolds** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="33734-133">If an In-Place Hold, eDiscovery hold, or Microsoft 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="33734-134">例如，下面显示了五个非活动邮箱的结果。</span><span class="sxs-lookup"><span data-stu-id="33734-134">For example, the following shows results for five inactive mailboxes.</span></span> 
  
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

<span data-ttu-id="33734-135">下表标识了使每个邮箱变为非活动状态的五种不同的保留类型。</span><span class="sxs-lookup"><span data-stu-id="33734-135">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="33734-136">**非活动邮箱**</span><span class="sxs-lookup"><span data-stu-id="33734-136">**Inactive mailbox**</span></span>|<span data-ttu-id="33734-137">**保留类型**</span><span class="sxs-lookup"><span data-stu-id="33734-137">**Hold type**</span></span>|<span data-ttu-id="33734-138">**如何识别非活动邮箱上的保留**</span><span class="sxs-lookup"><span data-stu-id="33734-138">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33734-139">Ann Beebe</span><span class="sxs-lookup"><span data-stu-id="33734-139">Ann Beebe</span></span>  <br/> |<span data-ttu-id="33734-140">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="33734-140">Litigation Hold</span></span>  <br/> |<span data-ttu-id="33734-141">*LitigationHoldEnabled* 属性设置为 `True` 。</span><span class="sxs-lookup"><span data-stu-id="33734-141">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="33734-142">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="33734-142">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="33734-143">就地保留</span><span class="sxs-lookup"><span data-stu-id="33734-143">In-Place Hold</span></span>  <br/> |<span data-ttu-id="33734-144">*InPlaceHolds* 属性包含非活动邮箱In-Place保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="33734-144">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="33734-145">你可以判断这是一个In-Place保留，因为 ID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="33734-145">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="33734-146">您可以使用 Exchange Online PowerShell 中的命令获取有关非活动邮箱In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` 保留的信息。</span><span class="sxs-lookup"><span data-stu-id="33734-146">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="33734-147">为百分卡</span><span class="sxs-lookup"><span data-stu-id="33734-147">Mario Necaise</span></span>  <br/> |<span data-ttu-id="33734-148">安全与合规中心中的组织范围内的 Microsoft 365 &策略</span><span class="sxs-lookup"><span data-stu-id="33734-148">Organization-wide Microsoft 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="33734-149">*InPlaceHolds* 属性为空。</span><span class="sxs-lookup"><span data-stu-id="33734-149">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="33734-150">这表示 Microsoft 365 保留策略 (一个或多个组织范围的保留策略) Exchange 范围的保留策略。</span><span class="sxs-lookup"><span data-stu-id="33734-150">This indicates that one or more organization-wide or (Exchange-wide) Microsoft 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="33734-151">在这种情况下，可以在 Exchange Online PowerShell 中运行命令，获取组织范围内 Microsoft 365 保留策略的  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID 列表。</span><span class="sxs-lookup"><span data-stu-id="33734-151">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Microsoft 365 retention policies.</span></span> <span data-ttu-id="33734-152">应用于 Exchange 邮箱的组织范围的保留策略的 GUID 以 前缀开头;  `mbx` 例如，  `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="33734-152">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="33734-153">若要标识应用于非活动邮箱的 Microsoft 365 保留策略，请运行安全与合规& PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="33734-153">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="33734-154">表示 Olson</span><span class="sxs-lookup"><span data-stu-id="33734-154">Carol Olson</span></span>  <br/> |<span data-ttu-id="33734-155">应用于特定邮箱的安全与合规中心& Microsoft 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="33734-155">Microsoft 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="33734-156">*InPlaceHolds* 属性包含应用于非活动邮箱的 Microsoft 365 保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="33734-156">The  *InPlaceHolds*  property contains the GUID of the Microsoft 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="33734-157">你可以判断这是应用于特定邮箱的保留策略，因为 GUID 以前缀  `mbx` 开头。</span><span class="sxs-lookup"><span data-stu-id="33734-157">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="33734-158">如果应用于非活动邮箱的保留策略的 GUID 以前缀开头，则表明保留策略已应用于  `skp` Skype for Business 对话。</span><span class="sxs-lookup"><span data-stu-id="33734-158">If the GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, it would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="33734-159">若要标识应用于非活动邮箱的 Microsoft 365 保留策略，请运行安全与合规& PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="33734-159">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="33734-160">运行此命令时，  `mbx` 请务必删除 或  `skp` 前缀。</span><span class="sxs-lookup"><span data-stu-id="33734-160">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="33734-161">为 McMahon</span><span class="sxs-lookup"><span data-stu-id="33734-161">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="33734-162">安全与合规中心中的电子数据&保留</span><span class="sxs-lookup"><span data-stu-id="33734-162">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="33734-163">*InPlaceHolds* 属性包含非活动邮箱上设置电子数据展示案例保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="33734-163">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="33734-164">你可以判断这是电子数据展示案例保留，因为 GUID 以前缀  `UniH` 开头。</span><span class="sxs-lookup"><span data-stu-id="33734-164">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="33734-165">您可以使用安全与合规中心 PowerShell & cmdlet 获取有关非活动邮箱上的保留关联的电子数据展示  `Get-CaseHoldPolicy` 案例的信息。</span><span class="sxs-lookup"><span data-stu-id="33734-165">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="33734-166">例如，可以运行命令来显示非活动邮箱上案例保留  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 的名称。</span><span class="sxs-lookup"><span data-stu-id="33734-166">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="33734-167">运行此命令时  `UniH` ，请务必删除前缀。</span><span class="sxs-lookup"><span data-stu-id="33734-167">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="33734-168">若要标识与非活动邮箱上的保留相关联的电子数据展示案例，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="33734-168">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="33734-169">**注意：** 建议不要对非活动邮箱使用电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="33734-169">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="33734-170">这是因为电子数据展示事例适用于与安全问题相关的特定、有时间限制的事例。</span><span class="sxs-lookup"><span data-stu-id="33734-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="33734-171">有时，法律案件可能会结束，并且与该案件关联的保留将被删除，电子数据展示案例将在最终 (或删除) 。</span><span class="sxs-lookup"><span data-stu-id="33734-171">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="33734-172">事实上，如果非活动邮箱上的保留与电子数据展示案例关联，并且该保留已释放或者电子数据展示案例已关闭或删除，则非活动邮箱将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="33734-172">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="33734-173">有关 Microsoft 365 保留策略详细信息，请参阅 [了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="33734-173">For more information about Microsoft 365 retention policies, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="33734-174">第 2 步：更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="33734-174">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="33734-175">在确定了非活动邮箱上设置的保留的类型（以及是否设置多个保留）后，下一步就要更改保留期了。</span><span class="sxs-lookup"><span data-stu-id="33734-175">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="33734-176">更改诉讼保留的保留期</span><span class="sxs-lookup"><span data-stu-id="33734-176">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="33734-177">下面将了解如何使用 Exchange Online PowerShell 更改非活动邮箱上设置的诉讼保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-177">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span></span> <span data-ttu-id="33734-178">不能使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="33734-178">You can't use the EAC.</span></span> <span data-ttu-id="33734-179">运行以下命令，更改保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-179">Run the following command to change the hold duration.</span></span> <span data-ttu-id="33734-180">在此示例中，可将保留期更改为无限期。</span><span class="sxs-lookup"><span data-stu-id="33734-180">In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="33734-181">结果是非活动邮箱中的项目会无限期保留，或者一直保留到删除保留或将保留期更改为其他值。</span><span class="sxs-lookup"><span data-stu-id="33734-181">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="33734-p113">标识非活动邮箱的最佳方式是使用 **Distinguished Name** 或 **Exchange GUID** 值。 使用下列值之一有助于避免意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="33734-p113">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="33734-184">更改就地保留的保留期</span><span class="sxs-lookup"><span data-stu-id="33734-184">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="33734-185">In-Place保留已停用且无法再修改。</span><span class="sxs-lookup"><span data-stu-id="33734-185">In-Place Holds have been retired and can no longer be modified.</span></span> <span data-ttu-id="33734-186">如果非活动邮箱应用了In-Place保留，则不能更改保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-186">If an inactive mailbox has an In-Place Hold applied to it, you can't change the hold duration.</span></span> <span data-ttu-id="33734-187">只能删除In-Place保留，这可能会导致删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="33734-187">You can only remove the In-Place Hold, which will result in the deletion of the inactive mailbox.</span></span> <span data-ttu-id="33734-188">有关详细信息，请参阅删除 [非活动邮箱](delete-an-inactive-mailbox.md#remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="33734-188">For more information, see [Delete an inactive mailbox](delete-an-inactive-mailbox.md#remove-in-place-holds).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="33734-189">详细信息</span><span class="sxs-lookup"><span data-stu-id="33734-189">More information</span></span>

- <span data-ttu-id="33734-p115">**如何计算非活动邮箱中项目的保留期？** 保留期从邮箱项目的接收或创建原始日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="33734-p115">**How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="33734-192">**当保留期过期时，会怎么样？**</span><span class="sxs-lookup"><span data-stu-id="33734-192">**What happens when the hold duration expires?**</span></span> <span data-ttu-id="33734-193">当"可恢复的项目"文件夹中的邮箱项目的保留期过期时，会从非活动邮箱中 (项目) 永久删除。</span><span class="sxs-lookup"><span data-stu-id="33734-193">When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="33734-194">如果没有为非活动邮箱上的保留指定持续时间，则永远不会清除"可恢复的项目"文件夹中的项目 (除非非活动邮箱的保留期) 。</span><span class="sxs-lookup"><span data-stu-id="33734-194">If there's no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="33734-195">**是否仍在非活动邮箱上处理 Exchange 保留策略？**</span><span class="sxs-lookup"><span data-stu-id="33734-195">**Is an Exchange retention policy still processed on inactive mailboxes?**</span></span> <span data-ttu-id="33734-196">如果 Exchange 保留策略 (Exchange Online) 中的邮件记录管理或 MRM 功能在变为非活动时应用于邮箱，则删除策略 (即配置了删除保留操作) 的保留标记将继续在非活动邮箱上进行处理。</span><span class="sxs-lookup"><span data-stu-id="33734-196">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span></span> <span data-ttu-id="33734-197">也就是说，在保留期过期时，标记有删除策略的项目会移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="33734-197">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span></span> <span data-ttu-id="33734-198">当项目的保留期过期时，这些项目会从非活动邮箱中清除。</span><span class="sxs-lookup"><span data-stu-id="33734-198">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="33734-p118">当项目的保留期过期时，这些项目会从非活动邮箱中清除。 相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 MoveToArchive 保留操作的保留标记）会遭到忽略。也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。这些项目不会移到存档邮箱或其中的"可恢复的项目"文件夹内。由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。 相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 MoveToArchive 保留操作的保留标记）会遭到忽略。 也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="33734-p118">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 

- <span data-ttu-id="33734-203">**若要检查诉讼保留的新保留期，请运行以下命令**</span><span class="sxs-lookup"><span data-stu-id="33734-203">**To check the new hold duration for a Litigation Hold, run the following commands**</span></span> 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- <span data-ttu-id="33734-204">**托管文件夹助理 (MFA) 还会处理非活动邮箱，就像处理常规邮箱一样。**</span><span class="sxs-lookup"><span data-stu-id="33734-204">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.**</span></span> <span data-ttu-id="33734-205">在 Exchange Online 中，MFA 大约每七天处理一次邮箱。</span><span class="sxs-lookup"><span data-stu-id="33734-205">In Exchange Online, the MFA processes mailboxes approximately once every seven days.</span></span> <span data-ttu-id="33734-206">更改非活动邮箱的保留期后，您可以使用 **Start-ManagedFolderAssistant** cmdlet 立即开始处理非活动邮箱的新保留期。</span><span class="sxs-lookup"><span data-stu-id="33734-206">After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox.</span></span> <span data-ttu-id="33734-207">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="33734-207">Run the following command.</span></span> 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="33734-208">**如果非活动邮箱上设置了许多保留，则并非所有保留项 GUID 都会显示出来。**</span><span class="sxs-lookup"><span data-stu-id="33734-208">**If many holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="33734-209">可以运行以下命令来显示非活动邮箱上 (保留) 保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="33734-209">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```