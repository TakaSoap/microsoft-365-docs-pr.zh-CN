---
title: 在租户允许/阻止列表中管理你的允许和阻止的 URL
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在安全与合规中心的"租户允许/阻止&"列表中& URL 条目。
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845938"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-103">管理租户允许/阻止列表中的 URL</span><span class="sxs-lookup"><span data-stu-id="3842d-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="3842d-104">本主题中介绍的功能在预览版中、可能会发生变更，并不适用于所有组织。</span><span class="sxs-lookup"><span data-stu-id="3842d-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="3842d-105">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，你可能希望与 EOP 筛选 Verdict 的禁用。</span><span class="sxs-lookup"><span data-stu-id="3842d-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="3842d-106">例如，一条正常邮件可能标记为错误的邮件 (误报) ，或者对于错误的负面建议，可能允许 (错误) 的邮件。</span><span class="sxs-lookup"><span data-stu-id="3842d-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="3842d-107">通过安全与合规中心内的租户 &允许/阻止列表，可以手动替代 Microsoft 365 筛选结果。</span><span class="sxs-lookup"><span data-stu-id="3842d-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="3842d-108">在邮件流中和单击用户时会使用租户允许/阻止列表。</span><span class="sxs-lookup"><span data-stu-id="3842d-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="3842d-109">可以指定要在租户允许/阻止列表中允许或阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="3842d-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="3842d-110">本主题介绍如何在安全 & 合规中心内的租户允许/阻止列表中，或在具有 Exchange Online 邮箱的 Microsoft 365 组织的 PowerShell (Exchange Online PowerShell 中配置条目;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="3842d-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3842d-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="3842d-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3842d-112">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="3842d-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3842d-113">若要直接转到"租户 **允许/阻止列表"** 页面，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="3842d-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="3842d-114">本主题后面将会在"租户允许 [/阻止列表"部分的 URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="3842d-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="3842d-115">租户允许/阻止列表最多可允许 500 个 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="3842d-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="3842d-116">条目应在 15 分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3842d-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="3842d-117">阻止条目优先于允许条目。</span><span class="sxs-lookup"><span data-stu-id="3842d-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="3842d-118">默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="3842d-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="3842d-119">你可以指定日期或将其设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="3842d-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="3842d-120">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3842d-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3842d-121">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3842d-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3842d-122">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="3842d-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="3842d-123">若要在租户允许/阻止列表中添加和删除值，您需要是以下角色组的成员之一：</span><span class="sxs-lookup"><span data-stu-id="3842d-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3842d-124">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="3842d-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3842d-125">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="3842d-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="3842d-126">必须是以下角色之一的成员，才能对租户允许/阻止列表进行只读访问：</span><span class="sxs-lookup"><span data-stu-id="3842d-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3842d-127">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="3842d-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3842d-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="3842d-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-129">使用安全与&中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="3842d-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3842d-130">有关 URL 条目的语法的详细信息，请参阅本主题 [后面的"租户允许/阻止列表](#url-syntax-for-the-tenant-allowblock-list) "一节的 URL 语法。</span><span class="sxs-lookup"><span data-stu-id="3842d-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="3842d-131">在安全与合规&中心，转到"**威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3842d-132">在" **租户允许/阻止列表** "页上，验证 **是否已选择"URL"** 选项卡，然后单击"添加 **"**</span><span class="sxs-lookup"><span data-stu-id="3842d-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="3842d-133">在 **显示的"添加新** URL"浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3842d-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3842d-134">**添加带通配符的**URL：每行输入一个 URL，最多 20 个 URL。</span><span class="sxs-lookup"><span data-stu-id="3842d-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="3842d-135">**阻止/允许**：选择是 **要** 允许 **还是** 阻止指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="3842d-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="3842d-136">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="3842d-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="3842d-137">验证此设置是否禁用了 (![ ](../../media/scc-toggle-off.png) 状态) 并使用 **"过期"** 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="3842d-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="3842d-138">或</span><span class="sxs-lookup"><span data-stu-id="3842d-138">or</span></span>

     - <span data-ttu-id="3842d-139">将切换开关移动到右侧可将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="3842d-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="3842d-141">.</span><span class="sxs-lookup"><span data-stu-id="3842d-141">.</span></span>

   - <span data-ttu-id="3842d-142">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="3842d-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="3842d-143">完成后，请单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-144">使用安全与&中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="3842d-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="3842d-145">在安全与合规&，转到"**威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3842d-146">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3842d-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="3842d-147">单击以下列标题以按升序或降序进行排序：</span><span class="sxs-lookup"><span data-stu-id="3842d-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="3842d-148">**值**</span><span class="sxs-lookup"><span data-stu-id="3842d-148">**Value**</span></span>
- <span data-ttu-id="3842d-149">**操作**：**阻止或\*\*\*\*允许**。</span><span class="sxs-lookup"><span data-stu-id="3842d-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="3842d-150">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="3842d-150">**Last updated date**</span></span>
- <span data-ttu-id="3842d-151">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="3842d-151">**Expiration date**</span></span>
- <span data-ttu-id="3842d-152">**注意**</span><span class="sxs-lookup"><span data-stu-id="3842d-152">**Note**</span></span>

<span data-ttu-id="3842d-153">单击 **"组**"将这些条目按 **"操作" (Block**或 **") "\*\*\*\*或"无"来分组**。 **Block**</span><span class="sxs-lookup"><span data-stu-id="3842d-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="3842d-154">单击 **"搜索**"，输入全部或部分值，然后按 Enter 查找特定值。</span><span class="sxs-lookup"><span data-stu-id="3842d-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="3842d-155">完成后，请单击"清除搜索 **清除搜索** ![ "图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="3842d-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="3842d-156">单击"**筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-156">Click **Filter**.</span></span> <span data-ttu-id="3842d-157">在随 **后** 出现的"筛选器"浮出控件中，配置以下任意设置：</span><span class="sxs-lookup"><span data-stu-id="3842d-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="3842d-158">**操作**：选择"**允许"和\*\*\*\*/或"** 从中"两者。</span><span class="sxs-lookup"><span data-stu-id="3842d-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="3842d-159">**永不过期**：选中 (![ 关闭 (](../../media/scc-toggle-off.png)) 或打开 ![ ("切换 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)) 。</span><span class="sxs-lookup"><span data-stu-id="3842d-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="3842d-160">**Last updated**： Select a start date (**From**) ， an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="3842d-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="3842d-161">**到期日期：** 选择 **从 (结束** 日期 () ，结束日期（ (开始) **或**) 或两者。</span><span class="sxs-lookup"><span data-stu-id="3842d-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="3842d-162">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="3842d-163">若要清除现有筛选器，请单击 **"筛选器"，** 然后在**出现的筛选器**浮出控件中单击"**清除筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-164">使用安全&合规中心修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="3842d-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3842d-165">您不能修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="3842d-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="3842d-166">您需要删除该项，然后重新创建它。</span><span class="sxs-lookup"><span data-stu-id="3842d-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="3842d-167">在安全与合规&中心，转到"**威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3842d-168">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3842d-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="3842d-169">选择要修改的条目，然后单击"编辑 **"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="3842d-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="3842d-170">在显示的浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3842d-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3842d-171">**阻止/允许**：选择 **"允许**"或 **"阻止"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="3842d-172">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="3842d-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="3842d-173">验证是否已在默认切换 (![ ](../../media/scc-toggle-off.png) 状态) 并使用 **"过期** "框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="3842d-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="3842d-174">或</span><span class="sxs-lookup"><span data-stu-id="3842d-174">or</span></span>

     - <span data-ttu-id="3842d-175">将切换开关移动到右侧可将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="3842d-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="3842d-177">.</span><span class="sxs-lookup"><span data-stu-id="3842d-177">.</span></span>

   - <span data-ttu-id="3842d-178">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="3842d-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="3842d-179">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3842d-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-180">使用安全与&中心删除租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="3842d-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="3842d-181">在安全与合规&中心，转到"**威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3842d-182">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3842d-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="3842d-183">选择要删除的项，然后单击"删除 **"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="3842d-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="3842d-184">在出现的警告对话框中，单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="3842d-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-185">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="3842d-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-186">使用 PowerShell 在租户允许/阻止列表中添加条目</span><span class="sxs-lookup"><span data-stu-id="3842d-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3842d-187">若要在租户允许/阻止列表中添加条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3842d-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="3842d-188">此示例为所有子域（如contoso.com、 (www.contoso.com 和xyz.abc.contoso.com) ）contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3842d-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="3842d-189">因为我们未使用 ExpirationDate 或 NoExpiration 参数，该条目会在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="3842d-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="3842d-190">有关语法和参数的详细信息，请参阅[New-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="3842d-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-191">使用 PowerShell 查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="3842d-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3842d-192">若要查看租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3842d-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="3842d-193">此示例返回所有已禁止的 URL。</span><span class="sxs-lookup"><span data-stu-id="3842d-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="3842d-194">有关语法和参数的详细信息，请参阅[Get-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="3842d-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-195">使用 PowerShell 修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="3842d-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3842d-196">您不能修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="3842d-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="3842d-197">您需要删除该项，然后重新创建它。</span><span class="sxs-lookup"><span data-stu-id="3842d-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="3842d-198">若要修改租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3842d-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="3842d-199">本示例更改指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="3842d-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="3842d-200">有关语法和参数的详细信息，请参阅[Set-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="3842d-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-201">使用 PowerShell 从租户允许/阻止列表中删除条目</span><span class="sxs-lookup"><span data-stu-id="3842d-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="3842d-202">若要从租户允许/阻止列表中删除条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3842d-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="3842d-203">本示例从租户允许/阻止列表中删除指定的 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="3842d-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="3842d-204">有关语法和参数的详细信息，请参阅[Remove-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="3842d-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="3842d-205">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="3842d-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="3842d-206">允许 IP4v 和 IPv6 地址，但 TCP/UDP 端口不允许。</span><span class="sxs-lookup"><span data-stu-id="3842d-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="3842d-207">例如，不允许 (扩展名test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="3842d-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="3842d-208">不支持 Unicode，但 Punycode 是 Punycode。</span><span class="sxs-lookup"><span data-stu-id="3842d-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="3842d-209">下列所有语句都为真时，允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="3842d-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="3842d-210">主机名中包含句点。</span><span class="sxs-lookup"><span data-stu-id="3842d-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="3842d-211">句点左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="3842d-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="3842d-212">句点右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="3842d-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="3842d-213">例如，允许 `t.co` 或 `.com` `contoso.` 不允许。</span><span class="sxs-lookup"><span data-stu-id="3842d-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="3842d-214">子路径不为隐式路径。</span><span class="sxs-lookup"><span data-stu-id="3842d-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="3842d-215">例如， `contoso.com` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="3842d-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="3842d-216">在下列 (通) 通配符通配符：</span><span class="sxs-lookup"><span data-stu-id="3842d-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="3842d-217">左侧通配符的后面必须为句点以指定子域。</span><span class="sxs-lookup"><span data-stu-id="3842d-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="3842d-218">例如， `*.contoso.com` 允许; `*contoso.com` 不允许使用。</span><span class="sxs-lookup"><span data-stu-id="3842d-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="3842d-219">正确的通配符必须遵循正斜 (/) 来指定路径。</span><span class="sxs-lookup"><span data-stu-id="3842d-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="3842d-220">例如，允许 `contoso.com/*` 或 `contoso.com*` `contoso.com/ab*` 不允许。</span><span class="sxs-lookup"><span data-stu-id="3842d-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="3842d-221">所有子路径都不由正确的通配符来表示。</span><span class="sxs-lookup"><span data-stu-id="3842d-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="3842d-222">例如， `contoso.com/*` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="3842d-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="3842d-223">`*.com*` 无效对象 (可解析的域无效，正确的通配符不遵循正斜) 。</span><span class="sxs-lookup"><span data-stu-id="3842d-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="3842d-224">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="3842d-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="3842d-225">在下列情况 () 和尾部字符类型：</span><span class="sxs-lookup"><span data-stu-id="3842d-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="3842d-226">左色板表示域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="3842d-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="3842d-227">例如， `~contoso.com` 包括 `contoso.com` `*.contoso.com` 和 。</span><span class="sxs-lookup"><span data-stu-id="3842d-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="3842d-228">包含协议的 URL (例如 `http://` ，或 `https://` `ftp://`) 将失败，因为 URL 条目将应用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="3842d-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="3842d-229">不支持或不要求使用用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="3842d-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="3842d-230">引用 ("或"引用) 字符。</span><span class="sxs-lookup"><span data-stu-id="3842d-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="3842d-231">URL 应包括所有可能的重定向。</span><span class="sxs-lookup"><span data-stu-id="3842d-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="3842d-232">URL 入口方案</span><span class="sxs-lookup"><span data-stu-id="3842d-232">URL entry scenarios</span></span>

<span data-ttu-id="3842d-233">下面的部分分说明有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="3842d-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="3842d-234">方案：无通配符</span><span class="sxs-lookup"><span data-stu-id="3842d-234">Scenario: No wildcards</span></span>

<span data-ttu-id="3842d-235">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="3842d-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="3842d-236">**允许匹配**：contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="3842d-237">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="3842d-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-238">abc-contoso.com</span></span>
  - <span data-ttu-id="3842d-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3842d-239">contoso.com/a</span></span>
  - <span data-ttu-id="3842d-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="3842d-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="3842d-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="3842d-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-243">www.contoso.com</span></span>
  - <span data-ttu-id="3842d-244">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="3842d-245">**块匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-245">**Block match**:</span></span>

  - <span data-ttu-id="3842d-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-246">contoso.com</span></span>
  - <span data-ttu-id="3842d-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3842d-247">contoso.com/a</span></span>
  - <span data-ttu-id="3842d-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="3842d-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="3842d-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="3842d-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-251">www.contoso.com</span></span>
  - <span data-ttu-id="3842d-252">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="3842d-253">**阻止不匹配：abc-contoso.com**</span><span class="sxs-lookup"><span data-stu-id="3842d-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="3842d-254">方案：子域 (留通配) </span><span class="sxs-lookup"><span data-stu-id="3842d-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="3842d-255">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="3842d-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="3842d-256">**允许比赛** 和 **块匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3842d-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-257">www.contoso.com</span></span>
  - <span data-ttu-id="3842d-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="3842d-259">**允许不匹配且\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3842d-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-260">123contoso.com</span></span>
  - <span data-ttu-id="3842d-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-261">contoso.com</span></span>
  - <span data-ttu-id="3842d-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="3842d-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="3842d-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="3842d-264">方案：路径顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="3842d-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="3842d-265">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="3842d-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="3842d-266">**允许比赛** 和 **块匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3842d-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="3842d-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="3842d-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="3842d-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="3842d-269">contoso.com/a/？q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="3842d-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="3842d-270">**允许不匹配且\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3842d-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-271">contoso.com</span></span>
  - <span data-ttu-id="3842d-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3842d-272">contoso.com/a</span></span>
  - <span data-ttu-id="3842d-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-273">www.contoso.com</span></span>
  - <span data-ttu-id="3842d-274">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="3842d-275">场景：左色</span><span class="sxs-lookup"><span data-stu-id="3842d-275">Scenario: Left tilde</span></span>

<span data-ttu-id="3842d-276">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="3842d-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="3842d-277">**允许比赛** 和 **块匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3842d-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-278">contoso.com</span></span>
  - <span data-ttu-id="3842d-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-279">www.contoso.com</span></span>
  - <span data-ttu-id="3842d-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="3842d-281">**允许不匹配且\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3842d-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-282">123contoso.com</span></span>
  - <span data-ttu-id="3842d-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="3842d-283">contoso.com/abc</span></span>
  - <span data-ttu-id="3842d-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="3842d-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="3842d-285">方案：右侧的通配符后缀</span><span class="sxs-lookup"><span data-stu-id="3842d-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="3842d-286">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="3842d-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="3842d-287">**允许比赛** 和 **块匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3842d-288">contoso.com/？q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3842d-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="3842d-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3842d-289">contoso.com/a</span></span>
  - <span data-ttu-id="3842d-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="3842d-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="3842d-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="3842d-291">contoso.com/ab</span></span>
  - <span data-ttu-id="3842d-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="3842d-292">contoso.com/b</span></span>
  - <span data-ttu-id="3842d-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="3842d-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="3842d-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="3842d-294">contoso.com/ba</span></span>

- <span data-ttu-id="3842d-295">**允许不匹配且\*\*\*\*阻止不匹配**：contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="3842d-296">方案：左侧通配符子域和右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="3842d-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="3842d-297">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="3842d-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="3842d-298">**允许比赛** 和 **块匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3842d-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="3842d-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="3842d-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="3842d-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="3842d-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3842d-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="3842d-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="3842d-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="3842d-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="3842d-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="3842d-304">**允许不匹配且\*\*\*\*阻止未匹配**：contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="3842d-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="3842d-305">场景：左和右量</span><span class="sxs-lookup"><span data-stu-id="3842d-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="3842d-306">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="3842d-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="3842d-307">**允许比赛** 和 **块匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3842d-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-308">contoso.com</span></span>
  - <span data-ttu-id="3842d-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3842d-309">contoso.com/a</span></span>
  - <span data-ttu-id="3842d-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-310">www.contoso.com</span></span>
  - <span data-ttu-id="3842d-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="3842d-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="3842d-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="3842d-313">**允许不匹配且\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3842d-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-314">123contoso.com</span></span>
  - <span data-ttu-id="3842d-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="3842d-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="3842d-316">方案：IP 地址</span><span class="sxs-lookup"><span data-stu-id="3842d-316">Scenario: IP address</span></span>

<span data-ttu-id="3842d-317">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="3842d-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="3842d-318">**允许比赛** 和 **块匹配**：1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="3842d-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="3842d-319">**允许不匹配且\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3842d-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="3842d-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="3842d-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="3842d-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="3842d-322">具有正确通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="3842d-322">IP address with right wildcard</span></span>

<span data-ttu-id="3842d-323">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="3842d-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="3842d-324">**允许比赛** 和 **块匹配**：</span><span class="sxs-lookup"><span data-stu-id="3842d-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3842d-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="3842d-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="3842d-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="3842d-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="3842d-327">无效条目示例</span><span class="sxs-lookup"><span data-stu-id="3842d-327">Examples of invalid entries</span></span>

<span data-ttu-id="3842d-328">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="3842d-328">The following entries are invalid:</span></span>

- <span data-ttu-id="3842d-329">**缺少域值或无效的域值**：</span><span class="sxs-lookup"><span data-stu-id="3842d-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="3842d-330">contoso</span><span class="sxs-lookup"><span data-stu-id="3842d-330">contoso</span></span>
  - <span data-ttu-id="3842d-331">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="3842d-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="3842d-332">\*.com</span><span class="sxs-lookup"><span data-stu-id="3842d-332">\*.com</span></span>
  - <span data-ttu-id="3842d-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="3842d-333">\*.pdf</span></span>

- <span data-ttu-id="3842d-334">**文本通配符或不包含空格字符**：</span><span class="sxs-lookup"><span data-stu-id="3842d-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="3842d-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-335">\*contoso.com</span></span>
  - <span data-ttu-id="3842d-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="3842d-336">contoso.com\*</span></span>
  - <span data-ttu-id="3842d-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="3842d-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="3842d-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="3842d-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="3842d-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="3842d-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="3842d-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="3842d-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="3842d-341">**具有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="3842d-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="3842d-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="3842d-342">contoso.com:443</span></span>
  - <span data-ttu-id="3842d-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="3842d-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="3842d-344">**非描述性通配符**：</span><span class="sxs-lookup"><span data-stu-id="3842d-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="3842d-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="3842d-345">\*.\*</span></span>

- <span data-ttu-id="3842d-346">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="3842d-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="3842d-347">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="3842d-347">conto\*so.com</span></span>
  - <span data-ttu-id="3842d-348">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="3842d-348">conto~so.com</span></span>

- <span data-ttu-id="3842d-349">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="3842d-349">**Double wildcards**</span></span>

  - <span data-ttu-id="3842d-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="3842d-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="3842d-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="3842d-351">contoso.com/\*/\*</span></span>
