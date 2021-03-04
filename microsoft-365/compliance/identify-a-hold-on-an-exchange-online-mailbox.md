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
description: 了解如何标识可在 Microsoft 365 中的 Exchange Online 邮箱上放置的不同类型的保留。
ms.openlocfilehash: a5bea8cd279bb980ba2f8a57950c8a66857ba502
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423623"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="5e9be-103">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="5e9be-103">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="5e9be-104">本文介绍如何标识在 Microsoft 365 中对 Exchange Online 邮箱的保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-104">This article explains how to identify holds placed on Exchange Online mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="5e9be-105">Microsoft 365 提供了组织可以阻止邮箱内容被永久删除的几种方法。</span><span class="sxs-lookup"><span data-stu-id="5e9be-105">Microsoft 365 offers several ways that your organization can prevent mailbox content from being permanently deleted.</span></span> <span data-ttu-id="5e9be-106">这样，组织可以保留内容以满足合规性法规，或在法律和其他类型的调查期间保留内容。</span><span class="sxs-lookup"><span data-stu-id="5e9be-106">This allows your organization to retain content to meet compliance regulations or during legal and other types of investigations.</span></span> <span data-ttu-id="5e9be-107">下面列出了 Office 365 中 (*保留*) 保留功能：</span><span class="sxs-lookup"><span data-stu-id="5e9be-107">Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="5e9be-108">**[诉讼保留](create-a-litigation-hold.md)：** 应用于 Exchange Online 中的用户邮箱的保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-108">**[Litigation Hold](create-a-litigation-hold.md):** Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="5e9be-109">**[电子数据展示保留](create-ediscovery-holds.md)：** 与安全与合规中心的核心电子数据展示案例相关联的保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-109">**[eDiscovery hold](create-ediscovery-holds.md):** Holds that are associated with a Core eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="5e9be-110">电子数据展示保留可应用于用户邮箱和 Microsoft 365 组和 Microsoft Teams 的相应邮箱。</span><span class="sxs-lookup"><span data-stu-id="5e9be-110">eDiscovery holds can be applied to user mailboxes and to the corresponding mailbox for Microsoft 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="5e9be-111">**[就地保留](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)：** 通过使用 Exchange Online Exchange 管理中心中的In-Place电子数据展示&保留工具应用于用户邮箱的保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-111">**[In-Place Hold](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="5e9be-112">In-Place保留已停用，并且你无法再创建In-Place保留或将其应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="5e9be-112">In-Place Holds have been retired and you can no longer create In-Place Holds or apply them to mailboxes.</span></span> <span data-ttu-id="5e9be-113">但是，In-Place保留可能仍应用于您组织的邮箱，这就是为什么它们包含在本文中的原因。</span><span class="sxs-lookup"><span data-stu-id="5e9be-113">However, In-Place Holds might still be applied to mailboxes in your organization, which is why they are included in this article.</span></span> <span data-ttu-id="5e9be-114">有关详细信息，请参阅停用 [旧版电子数据展示工具](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="5e9be-114">For more information, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center).</span></span>

- <span data-ttu-id="5e9be-115">**[Microsoft 365 保留策略](retention.md)：** 可以配置为保留或 (，然后删除 Exchange Online 用户邮箱和 Microsoft 365 组和 Microsoft Teams 的相应邮箱中的) 内容。</span><span class="sxs-lookup"><span data-stu-id="5e9be-115">**[Microsoft 365 retention policies](retention.md):** Can be configured to retain (or retain and then delete) content in user mailboxes in Exchange Online and in the corresponding mailbox for Microsoft 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="5e9be-116">还可以创建保留策略来保留存储在用户邮箱中的 Skype for Business 对话。</span><span class="sxs-lookup"><span data-stu-id="5e9be-116">You can also create a retention policy to retain Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="5e9be-117">有两种类型的 Microsoft 365 保留策略可以分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="5e9be-117">There are two types of Microsoft 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="5e9be-118">**特定位置保留策略：** 这些是分配给特定用户的内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="5e9be-118">**Specific location retention policies:** These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="5e9be-119">您可以使用 Exchange Online PowerShell 中的 **Get-Mailbox** cmdlet 获取有关分配给特定邮箱的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="5e9be-119">You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="5e9be-120">有关此类型的保留策略详细信息，请参阅包含保留策略文档中特定 [包含或](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) 排除项的策略一节。</span><span class="sxs-lookup"><span data-stu-id="5e9be-120">For more information about this type of retention policy, see the section [A policy with specific inclusions or exclusions](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) from the retention policy documentation.</span></span>

    - <span data-ttu-id="5e9be-121">**组织范围的保留策略：** 这些是分配给组织中所有内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="5e9be-121">**Organization-wide retention policies:** These are policies that are assigned to all content locations in your organization.</span></span> <span data-ttu-id="5e9be-122">您可以使用 Exchange Online PowerShell **中的 Get-OrganizationConfig** cmdlet 获取有关组织范围的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="5e9be-122">You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span> <span data-ttu-id="5e9be-123">有关此类型的保留策略详细信息，请参阅适用于保留策略文档中的整个[](create-retention-policies.md#a-policy-that-applies-to-entire-locations)位置的策略一节。</span><span class="sxs-lookup"><span data-stu-id="5e9be-123">For more information about this type of retention policy, see the section [A policy that applies to entire locations](create-retention-policies.md#a-policy-that-applies-to-entire-locations) from the retention policy documentation.</span></span>

- <span data-ttu-id="5e9be-124">**[Microsoft 365](retention.md)** 保留标签：如果用户应用 Microsoft 365 保留标签 (其中一个配置为保留内容或保留内容，然后将内容) 删除到其邮箱中任何文件夹或项目，则邮箱将置于保留状态，就像将邮箱置于诉讼保留或分配给 Microsoft 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="5e9be-124">**[Microsoft 365 retention labels](retention.md):** If a user applies a Microsoft 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox as if the mailbox was placed on Litigation Hold or assigned to a Microsoft 365 retention policy.</span></span> <span data-ttu-id="5e9be-125">有关详细信息，请参阅本文中的"标识保留 [邮箱](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) "部分，因为保留标签已应用于文件夹或项目部分。</span><span class="sxs-lookup"><span data-stu-id="5e9be-125">For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="5e9be-126">若要管理处于保留状态中的邮箱，可能需要确定邮箱上放置的保留类型，以便执行诸如更改保留期、临时或永久删除保留或者从 Microsoft 365 保留策略中排除邮箱等任务。</span><span class="sxs-lookup"><span data-stu-id="5e9be-126">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Microsoft 365 retention policy.</span></span> <span data-ttu-id="5e9be-127">在这些情况下，第一步是标识邮箱上的保留类型。</span><span class="sxs-lookup"><span data-stu-id="5e9be-127">In these cases, the first step is to identify the type of hold placed on the mailbox.</span></span> <span data-ttu-id="5e9be-128">由于多个保留 (，并且可以将不同类型的保留) 一个邮箱上，因此如果要删除或更改保留，必须标识邮箱上的所有保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-128">And because multiple holds (and different types of holds) can be placed on a single mailbox, you have to identify all holds placed on a mailbox if you want to remove or change a hold.</span></span>

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="5e9be-129">步骤 1：获取置于邮箱上的保留项的 GUID</span><span class="sxs-lookup"><span data-stu-id="5e9be-129">Step 1: Obtain the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="5e9be-130">您可以在 Exchange Online PowerShell 中运行以下两个 cmdlet，获取邮箱上保留项的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-130">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox.</span></span> <span data-ttu-id="5e9be-131">获取 GUID 后，可以使用它标识步骤 2 中的特定保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-131">After you obtain a GUID, you use it to identify the specific hold in Step 2.</span></span> <span data-ttu-id="5e9be-132">诉讼保留不是由 GUID 标识的。</span><span class="sxs-lookup"><span data-stu-id="5e9be-132">A Litigation Hold isn't identified by a GUID.</span></span> <span data-ttu-id="5e9be-133">为邮箱启用或禁用诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-133">Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="5e9be-134">**Get-Mailbox：** 使用此 cmdlet 可确定是否为邮箱启用诉讼保留，并获取专门分配给邮箱的电子数据展示保留、In-Place 保留和 Microsoft 365 保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-134">**Get-Mailbox:** Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Microsoft 365 retention policies that are specifically assigned to a mailbox.</span></span> <span data-ttu-id="5e9be-135">此 cmdlet 的输出还将指示邮箱是否已被明确从组织范围的保留策略中排除。</span><span class="sxs-lookup"><span data-stu-id="5e9be-135">The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="5e9be-136">**Get-OrganizationConfig：** 使用此 cmdlet 可获取组织范围的保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-136">**Get-OrganizationConfig:** Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="5e9be-137">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5e9be-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="5e9be-138">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="5e9be-138">Get-Mailbox</span></span>

<span data-ttu-id="5e9be-139">运行以下命令，获取有关应用于邮箱的保留和 Microsoft 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="5e9be-139">Run the following command to get information about the holds and Microsoft 365 retention policies applied to a mailbox.</span></span>

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="5e9be-140">如果 InPlaceHolds 属性中的值太多，但并非所有值都显示，您可以运行命令以在单独的行上显示每个 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-140">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="5e9be-141">下表介绍了在运行 **Get-Mailbox** cmdlet 时，如何根据 *InPlaceHolds* 属性的值标识不同类型的保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-141">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>

|<span data-ttu-id="5e9be-142">保留类型</span><span class="sxs-lookup"><span data-stu-id="5e9be-142">Hold type</span></span>  |<span data-ttu-id="5e9be-143">示例值</span><span class="sxs-lookup"><span data-stu-id="5e9be-143">Example value</span></span>  |<span data-ttu-id="5e9be-144">如何识别保留</span><span class="sxs-lookup"><span data-stu-id="5e9be-144">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5e9be-145">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="5e9be-145">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="5e9be-146">当 *LitigationHoldEnabled* 属性设置为时，会为邮箱启用诉讼保留 `True` 。</span><span class="sxs-lookup"><span data-stu-id="5e9be-146">Litigation Hold is enabled for a mailbox when the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="5e9be-147">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="5e9be-147">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="5e9be-148">*InPlaceHolds 属性* 包含在安全与合规中心内与电子数据展示案例关联的任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-148">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="5e9be-149">你可以判断这是电子数据展示保留，因为 GUID 以前缀 (表示统一保留 `UniH`) 。</span><span class="sxs-lookup"><span data-stu-id="5e9be-149">You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="5e9be-150">就地保留</span><span class="sxs-lookup"><span data-stu-id="5e9be-150">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="5e9be-151">或</span><span class="sxs-lookup"><span data-stu-id="5e9be-151">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="5e9be-152">*InPlaceHolds* 属性包含In-Place保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-152">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="5e9be-153">你可以判断这是一个In-Place保留，因为 GUID 不是以前缀开头，就是以前缀 `cld` 开头。</span><span class="sxs-lookup"><span data-stu-id="5e9be-153">You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="5e9be-154">专门应用于邮箱的 Microsoft 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5e9be-154">Microsoft 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="5e9be-155">或</span><span class="sxs-lookup"><span data-stu-id="5e9be-155">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="5e9be-156">InPlaceHolds 属性包含应用于邮箱的任何特定位置保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-156">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox.</span></span> <span data-ttu-id="5e9be-157">您可以标识保留策略，因为 GUID 以前缀 `mbx` 或前缀 `skp` 开头。</span><span class="sxs-lookup"><span data-stu-id="5e9be-157">You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix.</span></span> <span data-ttu-id="5e9be-158">前缀 `skp` 指示保留策略应用于用户邮箱中的 Skype for Business 对话。</span><span class="sxs-lookup"><span data-stu-id="5e9be-158">The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="5e9be-159">从组织范围内的 Microsoft 365 保留策略中排除</span><span class="sxs-lookup"><span data-stu-id="5e9be-159">Excluded from an organization-wide Microsoft 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="5e9be-160">如果邮箱从组织范围的 Microsoft 365 保留策略中排除，则从中排除邮箱的保留策略的 GUID 将显示在 InPlaceHolds 属性中，并且由前缀标识。 `-mbx`</span><span class="sxs-lookup"><span data-stu-id="5e9be-160">If a mailbox is excluded from an organization-wide Microsoft 365 retention policy, the GUID for the retention policy that the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="5e9be-161">Get-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="5e9be-161">Get-OrganizationConfig</span></span>
<span data-ttu-id="5e9be-162">如果在运行 **Get-Mailbox** cmdlet 时 *InPlaceHolds* 属性为空，则仍可能有一个或多个应用于邮箱的组织范围的 Microsoft 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="5e9be-162">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Microsoft 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="5e9be-163">在 Exchange Online PowerShell 中运行以下命令，获取组织范围内的 Microsoft 365 保留策略的 GUID 列表。</span><span class="sxs-lookup"><span data-stu-id="5e9be-163">Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Microsoft 365 retention policies.</span></span>

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="5e9be-164">如果 InPlaceHolds 属性中的值太多，但并非所有值都显示，您可以运行命令以在单独的行上显示每个 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-164">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="5e9be-165">下表介绍了不同类型的组织范围内的保留，以及如何在运行 **Get-OrganizationConfig** cmdlet 时根据 *InPlaceHolds* 属性中包含的 GUID 标识每种类型。</span><span class="sxs-lookup"><span data-stu-id="5e9be-165">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>

|<span data-ttu-id="5e9be-166">保留类型</span><span class="sxs-lookup"><span data-stu-id="5e9be-166">Hold type</span></span>  |<span data-ttu-id="5e9be-167">示例值</span><span class="sxs-lookup"><span data-stu-id="5e9be-167">Example value</span></span>  |<span data-ttu-id="5e9be-168">说明</span><span class="sxs-lookup"><span data-stu-id="5e9be-168">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5e9be-169">应用于 Exchange 邮箱、Exchange 公用文件夹和 Teams 聊天的 Microsoft 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5e9be-169">Microsoft 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="5e9be-170">应用于 Exchange 邮箱、Exchange 公用文件夹和 Microsoft Teams 中的 1xN 聊天的组织范围的保留策略由以前缀开头的 GUID `mbx` 标识。</span><span class="sxs-lookup"><span data-stu-id="5e9be-170">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix.</span></span> <span data-ttu-id="5e9be-171">注意 1xN 聊天存储在单个聊天参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5e9be-171">Note 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="5e9be-172">应用于 Microsoft 365 组和 Teams 频道消息的 Microsoft 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5e9be-172">Microsoft 365 retention policy applied to Microsoft 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="5e9be-173">适用于 Microsoft 365 组和 Microsoft Teams 中的频道消息的组织范围的保留策略由以前缀开头的 GUID `grp` 标识。</span><span class="sxs-lookup"><span data-stu-id="5e9be-173">Organization-wide retention policies applied to Microsoft 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix.</span></span> <span data-ttu-id="5e9be-174">请注意，频道邮件存储在与 Microsoft 团队关联的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5e9be-174">Note channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="5e9be-175">有关应用于 Microsoft Teams 的保留策略详细信息，请参阅了解 [Microsoft Teams 的保留策略](retention-policies-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9be-175">For more information about retention policies applied to Microsoft Teams, see [Learn about retention policies for Microsoft Teams](retention-policies-teams.md).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="5e9be-176">了解保留策略的 InPlaceHolds 值的格式</span><span class="sxs-lookup"><span data-stu-id="5e9be-176">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="5e9be-177">除了将 InPlaceHolds 属性中的项目标识为 Microsoft 365 保留策略的前缀 (mbx、skp 或 grp) 之外，值还包含一个后缀，用于标识为策略配置的保留操作的类型。</span><span class="sxs-lookup"><span data-stu-id="5e9be-177">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as a Microsoft 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy.</span></span> <span data-ttu-id="5e9be-178">例如，在下面的示例中，操作后缀以粗体突出显示：</span><span class="sxs-lookup"><span data-stu-id="5e9be-178">For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="5e9be-179">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span><span class="sxs-lookup"><span data-stu-id="5e9be-179">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="5e9be-180">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span><span class="sxs-lookup"><span data-stu-id="5e9be-180">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="5e9be-181">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span><span class="sxs-lookup"><span data-stu-id="5e9be-181">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="5e9be-182">下表定义了三种可能的保留操作：</span><span class="sxs-lookup"><span data-stu-id="5e9be-182">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="5e9be-183">值</span><span class="sxs-lookup"><span data-stu-id="5e9be-183">Value</span></span>  |<span data-ttu-id="5e9be-184">说明</span><span class="sxs-lookup"><span data-stu-id="5e9be-184">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5e9be-185">**1**</span><span class="sxs-lookup"><span data-stu-id="5e9be-185">**1**</span></span>     | <span data-ttu-id="5e9be-186">指示保留策略配置为删除项目。</span><span class="sxs-lookup"><span data-stu-id="5e9be-186">Indicates that the retention policy is configured to delete items.</span></span> <span data-ttu-id="5e9be-187">该策略不保留项目。</span><span class="sxs-lookup"><span data-stu-id="5e9be-187">The policy doesn't retain items.</span></span>        |
|<span data-ttu-id="5e9be-188">**2**</span><span class="sxs-lookup"><span data-stu-id="5e9be-188">**2**</span></span>    |    <span data-ttu-id="5e9be-189">指示保留策略配置为保留项目。</span><span class="sxs-lookup"><span data-stu-id="5e9be-189">Indicates that the retention policy is configured to hold items.</span></span> <span data-ttu-id="5e9be-190">策略不会在保留期到期后删除项目。</span><span class="sxs-lookup"><span data-stu-id="5e9be-190">The policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="5e9be-191">**3**</span><span class="sxs-lookup"><span data-stu-id="5e9be-191">**3**</span></span>     |   <span data-ttu-id="5e9be-192">指示保留策略配置为保留项目，然后在保留期到期后将其删除。</span><span class="sxs-lookup"><span data-stu-id="5e9be-192">Indicates that the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="5e9be-193">有关保留操作详细信息，请参阅"保留特定时间段 [的内容"部分](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) 。</span><span class="sxs-lookup"><span data-stu-id="5e9be-193">For more information about retention actions, see the [Retaining content for a specific period of time](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) section.</span></span>
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a><span data-ttu-id="5e9be-194">步骤 2：使用 GUID 标识保留</span><span class="sxs-lookup"><span data-stu-id="5e9be-194">Step 2: Use the GUID to identify the hold</span></span>

<span data-ttu-id="5e9be-195">获取应用于邮箱的保留的 GUID 后，下一步是使用该 GUID 标识保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-195">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold.</span></span> <span data-ttu-id="5e9be-196">以下各节显示如何使用保留 GUID 标识保留 (和其他) 名称。</span><span class="sxs-lookup"><span data-stu-id="5e9be-196">The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="5e9be-197">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="5e9be-197">eDiscovery holds</span></span>

<span data-ttu-id="5e9be-198">在安全与合规& PowerShell 中运行以下命令，以标识应用于邮箱的电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-198">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox.</span></span> <span data-ttu-id="5e9be-199">使用 GUID (不包括在步骤 1 中) 电子数据展示保留的 UniH 前缀值。</span><span class="sxs-lookup"><span data-stu-id="5e9be-199">Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1.</span></span> 

<span data-ttu-id="5e9be-200">若要连接到安全与&中心 PowerShell，请参阅"连接到安全与合规&[中心 PowerShell。](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="5e9be-200">To connect to Security & Compliance Center PowerShell, see  [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="5e9be-201">第一个命令创建一个包含有关保留信息的变量。</span><span class="sxs-lookup"><span data-stu-id="5e9be-201">The first command creates a variable that contains information about the hold.</span></span> <span data-ttu-id="5e9be-202">此变量用于其他命令。</span><span class="sxs-lookup"><span data-stu-id="5e9be-202">This variable is used in the other commands.</span></span> <span data-ttu-id="5e9be-203">第二个命令显示与保留相关联的电子数据展示案例的名称。</span><span class="sxs-lookup"><span data-stu-id="5e9be-203">The second command displays the name of the eDiscovery case the hold is associated with.</span></span> <span data-ttu-id="5e9be-204">第三个命令显示保留的名称和应用于保留的邮箱列表。</span><span class="sxs-lookup"><span data-stu-id="5e9be-204">The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a><span data-ttu-id="5e9be-205">就地保留</span><span class="sxs-lookup"><span data-stu-id="5e9be-205">In-Place Holds</span></span>

<span data-ttu-id="5e9be-206">在 Exchange Online PowerShell 中运行以下命令In-Place应用于邮箱的保留状态。</span><span class="sxs-lookup"><span data-stu-id="5e9be-206">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox.</span></span> <span data-ttu-id="5e9be-207">使用在步骤 1 In-Place标识的保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e9be-207">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> <span data-ttu-id="5e9be-208">该命令显示保留的名称和应用于保留的邮箱列表。</span><span class="sxs-lookup"><span data-stu-id="5e9be-208">The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

<span data-ttu-id="5e9be-209">如果保留的 GUID In-Place前缀开始，请确保在运行上一个命令时包含 `cld` 前缀。</span><span class="sxs-lookup"><span data-stu-id="5e9be-209">If the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e9be-210">由于我们将继续以不同方式投资来保留邮箱内容，我们宣布在 Exchange 管理中心 (EAC) 中停用 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-210">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="5e9be-211">从 2020 年 7 月 1 日开始，你将无法在 Exchange Online In-Place保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-211">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="5e9be-212">但你仍然可以在 EAC 中In-Place Exchange Online PowerShell 中的 **Set-MailboxSearch** cmdlet 管理保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-212">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="5e9be-213">但是，从 2020 年 10 月 1 日起，你将无法管理In-Place保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-213">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="5e9be-214">你将仅在 EAC 中或通过使用 **Remove-MailboxSearch** cmdlet 删除它们。</span><span class="sxs-lookup"><span data-stu-id="5e9be-214">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="5e9be-215">有关停用保留In-Place，请参阅停用 [旧版电子数据展示工具](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9be-215">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>

### <a name="microsoft-365-retention-policies"></a><span data-ttu-id="5e9be-216">Microsoft 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5e9be-216">Microsoft 365 retention policies</span></span>

<span data-ttu-id="5e9be-217">在安全与合规& PowerShell 中运行以下命令，以标识应用于邮箱的 Microsoft 365 (或) 位置策略。</span><span class="sxs-lookup"><span data-stu-id="5e9be-217">Run the following command in Security & Compliance Center PowerShell to identity the Microsoft 365 retention policy (organization-wide or specific location) that's applied to the mailbox.</span></span> <span data-ttu-id="5e9be-218">使用 GUID (不包括在步骤 1 中标识的 mbx、skp 或 grp 前缀或) 后缀。</span><span class="sxs-lookup"><span data-stu-id="5e9be-218">Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="5e9be-219">标识保留邮箱，因为保留标签已应用于文件夹或项目</span><span class="sxs-lookup"><span data-stu-id="5e9be-219">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="5e9be-220">每当用户应用配置为保留内容或保留内容，然后删除其邮箱中任何文件夹或项目的保留标签时 *，ComplianceTagHoldApplied* 邮箱属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="5e9be-220">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="5e9be-221">发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留或分配给 Microsoft 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="5e9be-221">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a Microsoft 365 retention policy.</span></span> <span data-ttu-id="5e9be-222">当 *ComplianceTagHoldApplied* 属性设置为 **True** 时，可能会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="5e9be-222">When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="5e9be-223">如果删除邮箱或用户的用户帐户，则邮箱将成为非 [活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9be-223">If the mailbox or the user's user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="5e9be-224">如果主邮箱或存档 (邮箱已启用，则不能禁用) 。</span><span class="sxs-lookup"><span data-stu-id="5e9be-224">You aren't able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="5e9be-225">邮箱中的项目保留时间可能会超过预期。</span><span class="sxs-lookup"><span data-stu-id="5e9be-225">Items in the mailbox may be retained longer than expected.</span></span> <span data-ttu-id="5e9be-226">这是因为邮箱已置于保留状态，因此在邮件被清除后 (永久) 。</span><span class="sxs-lookup"><span data-stu-id="5e9be-226">This is because the mailbox is on hold and therefore no items are permanently deleted (purged).</span></span>

<span data-ttu-id="5e9be-227">若要查看 *ComplianceTagHoldApplied* 属性的值，请运行 Exchange Online PowerShell 中的以下命令：</span><span class="sxs-lookup"><span data-stu-id="5e9be-227">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="5e9be-228">有关保留标签详细信息，请参阅 [保留标签](retention.md#retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="5e9be-228">For more information about retention labels, see [retention labels](retention.md#retention-labels).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="5e9be-229">管理延迟保留中的邮箱</span><span class="sxs-lookup"><span data-stu-id="5e9be-229">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="5e9be-230">从邮箱中删除任何类型的保留后，将 *应用延迟* 保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-230">After any type of hold is removed from a mailbox, a *delay hold* is applied.</span></span> <span data-ttu-id="5e9be-231">这意味着将保留的实际删除延迟 30 天，以防止从邮箱中 (数据) 删除。</span><span class="sxs-lookup"><span data-stu-id="5e9be-231">This means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox.</span></span> <span data-ttu-id="5e9be-232">这使管理员有机会搜索或恢复将在删除保留后清除的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="5e9be-232">This gives admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.</span></span> <span data-ttu-id="5e9be-233">下次托管文件夹助理处理邮箱并检测到已删除保留时，邮箱上将设置延迟保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-233">A delay hold is placed on a mailbox the next time the Managed Folder Assistant processes the mailbox and detects that a hold was removed.</span></span> <span data-ttu-id="5e9be-234">具体来说，当托管文件夹助理将下列邮箱属性之一设置为 True 时，会向邮箱应用延迟 **保留**：</span><span class="sxs-lookup"><span data-stu-id="5e9be-234">Specifically, a delay hold is applied to a mailbox when the Managed Folder Assistant sets one of the following mailbox properties to **True**:</span></span>

- <span data-ttu-id="5e9be-235">**DelayHoldApplied：** 此属性适用于用户 (Outlook 和 Outlook 网页) 用户邮箱中生成的电子邮件相关内容。</span><span class="sxs-lookup"><span data-stu-id="5e9be-235">**DelayHoldApplied:** This property applies to email-related content (generated by people using Outlook and Outlook on the web) that's stored in a user's mailbox.</span></span>

- <span data-ttu-id="5e9be-236">**DelayReleaseHoldApplied：** 此属性适用于由非 Outlook (（如 Microsoft Teams、Microsoft Forms 和 Microsoft Yammer) ）生成的基于云的内容，这些内容存储在用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5e9be-236">**DelayReleaseHoldApplied:** This property applies to cloud-based content (generated by non-Outlook apps such as Microsoft Teams, Microsoft Forms, and Microsoft Yammer) that's stored in a user's mailbox.</span></span> <span data-ttu-id="5e9be-237">由 Microsoft 应用生成的云数据通常存储在用户邮箱的隐藏文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5e9be-237">Cloud data generated by a Microsoft app is typically stored in a hidden folder in a user's mailbox.</span></span>

<span data-ttu-id="5e9be-238">当将邮箱 (当之前任一属性设置为 **True**) 时，仍认为邮箱处于保留状态，保留期不受限制，就像邮箱处于诉讼保留状态一样。</span><span class="sxs-lookup"><span data-stu-id="5e9be-238">When a delay hold is placed on the mailbox (when either of the previous properties is set to **True**), the mailbox is still considered to be on hold for an unlimited hold duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="5e9be-239">30 天后，延迟保留过期，Microsoft 365 将自动尝试通过将 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **False**) 来删除延迟保留 (，以便删除该保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-239">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the DelayHoldApplied or DelayReleaseHoldApplied property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="5e9be-240">在将其中任一属性设置为 **False** 后，下一次托管文件夹助理处理邮箱时，将清除标记为删除的相应项目。</span><span class="sxs-lookup"><span data-stu-id="5e9be-240">After either of these properties are set to **False**, the corresponding items that are marked for removal are purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="5e9be-241">若要查看邮箱的 DelayHoldApplied 和 DelayReleaseHoldApplied 属性的值，请运行 Exchange Online PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="5e9be-241">To view the values for the DelayHoldApplied and DelayReleaseHoldApplied properties for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

<span data-ttu-id="5e9be-242">若要在延迟保留过期之前删除延迟保留， (或同时运行) Exchange Online PowerShell 中的以下命令，具体取决于要更改的属性：</span><span class="sxs-lookup"><span data-stu-id="5e9be-242">To remove the delay hold before it expires, you can run one (or both) the following commands in Exchange Online PowerShell, depending on which property you want to change:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="5e9be-243">或</span><span class="sxs-lookup"><span data-stu-id="5e9be-243">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="5e9be-244">必须在 Exchange Online 中分配法定保留角色，以使用 *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 参数。</span><span class="sxs-lookup"><span data-stu-id="5e9be-244">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameters.</span></span> 

<span data-ttu-id="5e9be-245">若要删除非活动邮箱的延迟保留，请运行 Exchange Online PowerShell 中的以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="5e9be-245">To remove the delay hold on an inactive mailbox, run one of the following commands in Exchange Online PowerShell:</span></span>

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

<span data-ttu-id="5e9be-246">或</span><span class="sxs-lookup"><span data-stu-id="5e9be-246">Or</span></span>

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> <span data-ttu-id="5e9be-247">在上一个命令中指定非活动邮箱的最佳方法就是使用其可分辨名称或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="5e9be-247">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="5e9be-248">使用下列值之一有助于避免意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5e9be-248">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

<span data-ttu-id="5e9be-249">有关使用这些参数管理延迟保留的信息，请参阅 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="5e9be-249">For more information about using these parameters for managing delay holds, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="5e9be-250">管理置于延迟保留状态邮箱时，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="5e9be-250">Keep the following things in mind when managing a mailbox on delay hold:</span></span>

- <span data-ttu-id="5e9be-251">如果 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **True，** 并删除邮箱 (或相应的用户帐户) ，则邮箱将成为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5e9be-251">If either the DelayHoldApplied or DelayReleaseHoldApplied property is set to **True** and a mailbox (or the corresponding user account) is deleted, the mailbox becomes an inactive mailbox.</span></span> <span data-ttu-id="5e9be-252">这是因为如果任一属性设置为 **True，** 则认为邮箱处于保留状态，删除保留邮箱会导致邮箱处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="5e9be-252">That's because a mailbox is considered to be on hold if either property is set to **True**, and deleting a mailbox on hold results in an inactive mailbox.</span></span> <span data-ttu-id="5e9be-253">若要删除邮箱，而不要将其设置为非活动邮箱，您必须将两个属性都设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="5e9be-253">To delete a mailbox and not make it an inactive mailbox, you have to set both properties to **False**.</span></span>

- <span data-ttu-id="5e9be-254">如前文所指出，如果 DelayHoldApplied 或 DelayReleaseHoldApplied 属性设置为 **True，** 则认为邮箱将保持无限期保留。</span><span class="sxs-lookup"><span data-stu-id="5e9be-254">As previous stated, a mailbox is considered to be on hold for an unlimited hold duration if either the DelayHoldApplied or DelayReleaseHoldApplied property is set to **True**.</span></span> <span data-ttu-id="5e9be-255">但是， *这并不意味着保留邮箱* 中所有内容。</span><span class="sxs-lookup"><span data-stu-id="5e9be-255">However, that doesn't mean that *all* content in the mailbox is preserved.</span></span> <span data-ttu-id="5e9be-256">它取决于设置为每个属性的值。</span><span class="sxs-lookup"><span data-stu-id="5e9be-256">It depends on the value that's set to each property.</span></span> <span data-ttu-id="5e9be-257">例如，假设这两个属性都设置为 **True，** 因为保留从邮箱中删除。</span><span class="sxs-lookup"><span data-stu-id="5e9be-257">For example, let's say both properties are set to **True** because holds are removed from the mailbox.</span></span> <span data-ttu-id="5e9be-258">然后，使用 *RemoveDelayReleaseHoldApplied* 参数 (删除应用于非 Outlook 云数据应用的延迟) 。</span><span class="sxs-lookup"><span data-stu-id="5e9be-258">Then you remove only the delay hold that's applied to non-Outlook cloud data (by using the *RemoveDelayReleaseHoldApplied* parameter).</span></span> <span data-ttu-id="5e9be-259">下次托管文件夹助理处理邮箱时，将清除标记为删除的非 Outlook 项目。</span><span class="sxs-lookup"><span data-stu-id="5e9be-259">The next time the Managed Folder Assistant processes the mailbox, the non-Outlook items marked for removal are purged.</span></span> <span data-ttu-id="5e9be-260">任何标记为删除的 Outlook 项目将不会清除，因为 DelayHoldApplied 属性仍设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="5e9be-260">Any Outlook items marked for removal won't be purged because the DelayHoldApplied property is still set to **True**.</span></span> <span data-ttu-id="5e9be-261">另一方面也是如此：如果 DelayHoldApplied 设置为 False，DelayReleaseHoldApplied 设置为 **True，** 则只会清除标记为删除的 Outlook 项目。 </span><span class="sxs-lookup"><span data-stu-id="5e9be-261">The opposite would also be true: if DelayHoldApplied is set to **False** and DelayReleaseHoldApplied is set to **True**, then only Outlook items marked for removal would be purged.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e9be-262">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5e9be-262">Next steps</span></span>

<span data-ttu-id="5e9be-263">确定应用于邮箱的保留后，可以执行以下任务：更改保留期、临时或永久删除保留，或者从 Microsoft 365 保留策略中排除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5e9be-263">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or excluding an inactive mailbox from a Microsoft 365 retention policy.</span></span> <span data-ttu-id="5e9be-264">有关执行与保留项相关的任务详细信息，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="5e9be-264">For more information about performing tasks related to holds, see one of the following topics:</span></span>

- <span data-ttu-id="5e9be-265">在安全与合规中心 PowerShell 中运行[Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationExcept & ion \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)命令，从组织范围内的 Microsoft 365 保留策略中排除邮箱。</span><span class="sxs-lookup"><span data-stu-id="5e9be-265">Run the [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Microsoft 365 retention policy.</span></span> <span data-ttu-id="5e9be-266">此命令只能用于 *ExchangeLocation* 属性的值等于的保留策略 `All` 。</span><span class="sxs-lookup"><span data-stu-id="5e9be-266">This command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- [<span data-ttu-id="5e9be-267">更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="5e9be-267">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="5e9be-268">删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5e9be-268">Delete an inactive mailbox</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="5e9be-269">删除保留状态云邮箱的“可恢复的项目”文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="5e9be-269">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
