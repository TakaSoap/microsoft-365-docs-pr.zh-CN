---
title: 在租户允许/阻止列表中管理允许和阻止的 Url
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
description: 管理员可以了解如何在安全 & 合规性中心的租户允许/阻止列表中配置 URL 条目。
ms.openlocfilehash: 0fdfa23ba22b240032e7a6888948de180aa0f6ae
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614960"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-103">管理租户允许/阻止列表中的 URL</span><span class="sxs-lookup"><span data-stu-id="a1fad-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="a1fad-104">本主题中所述的功能处于预览阶段，可能会发生更改，并且在所有组织中均不可用。</span><span class="sxs-lookup"><span data-stu-id="a1fad-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="a1fad-105">在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，您可能不同意 EOP 筛选判定。</span><span class="sxs-lookup"><span data-stu-id="a1fad-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="a1fad-106">例如，良好的邮件可能会被标记为 "错误" (误报) ，或者可能允许通过 (false 否定) 的错误消息。</span><span class="sxs-lookup"><span data-stu-id="a1fad-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="a1fad-107">Security & 合规性中心中的租户允许/阻止列表为你提供了一种手动替代 Microsoft 365 筛选 verdicts 的方法。</span><span class="sxs-lookup"><span data-stu-id="a1fad-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="a1fad-108">在邮件流期间和用户单击时使用租户允许/阻止列表。</span><span class="sxs-lookup"><span data-stu-id="a1fad-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="a1fad-109">可以在 "租户允许/阻止" 列表中指定允许或阻止的 Url。</span><span class="sxs-lookup"><span data-stu-id="a1fad-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="a1fad-110">本主题介绍如何使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中的 Microsoft 365 组织配置租户允许/阻止列表中的条目;没有 Exchange Online 邮箱) 组织的独立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a1fad-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a1fad-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="a1fad-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a1fad-112">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="a1fad-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a1fad-113">若要直接转到 **租户允许/阻止列表** 页，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="a1fad-114">在本主题后面的 [租户允许/阻止列表部分的 url 语法](#url-syntax-for-the-tenant-allowblock-list) 中介绍了可用的 url 值。</span><span class="sxs-lookup"><span data-stu-id="a1fad-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="a1fad-115">租户允许/阻止列表允许 Url 最多为500个条目。</span><span class="sxs-lookup"><span data-stu-id="a1fad-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="a1fad-116">条目应在15分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a1fad-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="a1fad-117">阻止项优先于允许项。</span><span class="sxs-lookup"><span data-stu-id="a1fad-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="a1fad-118">默认情况下，租户允许/阻止列表中的条目将在30天后过期。</span><span class="sxs-lookup"><span data-stu-id="a1fad-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="a1fad-119">您可以指定一个日期或将它们设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="a1fad-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="a1fad-120">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a1fad-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a1fad-121">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a1fad-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a1fad-122">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="a1fad-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a1fad-123">若要添加和删除租户允许/阻止列表中的值，您需要是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="a1fad-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a1fad-124">若要对租户允许/阻止列表进行只读访问，您需要是 **全局读取器** 或 **安全读者** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="a1fad-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a1fad-125">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fad-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="a1fad-126">**注意**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-126">**Notes**:</span></span>

  - <span data-ttu-id="a1fad-127">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="a1fad-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a1fad-128">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="a1fad-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="a1fad-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="a1fad-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-130">使用安全 & 合规性中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="a1fad-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a1fad-131">有关 URL 项的语法的详细信息，请参阅本主题后面的 [租户允许/阻止列表部分的 URL 语法](#url-syntax-for-the-tenant-allowblock-list) 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="a1fad-132">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="a1fad-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a1fad-133">在 "**租户允许/阻止列表**" 页上，确认已选择 " **url** " 选项卡，然后单击 "**添加**"</span><span class="sxs-lookup"><span data-stu-id="a1fad-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="a1fad-134">在出现的 " **添加新 url** " 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a1fad-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a1fad-135">**添加带通配符的 url**：每行输入一个 URL，最多为20个。</span><span class="sxs-lookup"><span data-stu-id="a1fad-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a1fad-136">**阻止/允许**：选择是否要 **允许** 或 **阻止** 指定的 url。</span><span class="sxs-lookup"><span data-stu-id="a1fad-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="a1fad-137">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="a1fad-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a1fad-138">验证设置是否已关闭 (![ 切换 ](../../media/scc-toggle-off.png)) 并使用 " **过期时间** " 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="a1fad-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a1fad-139">或</span><span class="sxs-lookup"><span data-stu-id="a1fad-139">or</span></span>

     - <span data-ttu-id="a1fad-140">将切换向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="a1fad-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="a1fad-142">.</span><span class="sxs-lookup"><span data-stu-id="a1fad-142">.</span></span>

   - <span data-ttu-id="a1fad-143">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="a1fad-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a1fad-144">完成后，请单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="a1fad-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-145">使用安全 & 合规性中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a1fad-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a1fad-146">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="a1fad-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a1fad-147">选择 " **url** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a1fad-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="a1fad-148">单击以下列标题，以按升序或降序进行排序：</span><span class="sxs-lookup"><span data-stu-id="a1fad-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="a1fad-149">**值**</span><span class="sxs-lookup"><span data-stu-id="a1fad-149">**Value**</span></span>
- <span data-ttu-id="a1fad-150">**操作**： **阻止** 或 **允许**。</span><span class="sxs-lookup"><span data-stu-id="a1fad-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="a1fad-151">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="a1fad-151">**Last updated date**</span></span>
- <span data-ttu-id="a1fad-152">**过期日期**</span><span class="sxs-lookup"><span data-stu-id="a1fad-152">**Expiration date**</span></span>
- <span data-ttu-id="a1fad-153">**注意**</span><span class="sxs-lookup"><span data-stu-id="a1fad-153">**Note**</span></span>

<span data-ttu-id="a1fad-154">单击 " **组** " 将按 **操作** 对条目进行分组 (**阻止** 或 **允许**) 或 " **无**"。</span><span class="sxs-lookup"><span data-stu-id="a1fad-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="a1fad-155">单击 " **搜索**"，输入全部或部分值，然后按 enter 以查找特定值。</span><span class="sxs-lookup"><span data-stu-id="a1fad-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="a1fad-156">完成后，请单击 " **清除搜索**" "清除 ![ 搜索" 图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="a1fad-157">单击 " **筛选**"。</span><span class="sxs-lookup"><span data-stu-id="a1fad-157">Click **Filter**.</span></span> <span data-ttu-id="a1fad-158">在出现的 **筛选器** 浮出控件中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="a1fad-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="a1fad-159">**操作**：选择 " **允许**"、" **阻止** " 或两者。</span><span class="sxs-lookup"><span data-stu-id="a1fad-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="a1fad-160">**永不过期**：选中 "关闭 (![ 切换 ](../../media/scc-toggle-off.png) ") 或 "在 ![) 上 (切换" ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="a1fad-161">**上次更新** 时间： **从**) 中选择开始日期 (，结束日期 (**为**) 或同时更新两者。</span><span class="sxs-lookup"><span data-stu-id="a1fad-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="a1fad-162">**过期日期**： **从**) 中选择开始日期 (，结束日期 (为) 或同时 **为** 两者。</span><span class="sxs-lookup"><span data-stu-id="a1fad-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="a1fad-163">完成后，请单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="a1fad-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="a1fad-164">若要清除现有筛选器，请单击 " **筛选**"，并在出现的 **筛选器** 浮出控件中，单击 " **清除筛选**"</span><span class="sxs-lookup"><span data-stu-id="a1fad-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-165">使用安全 & 合规性中心修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a1fad-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a1fad-166">您不能修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="a1fad-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="a1fad-167">相反，您需要删除并重新创建该条目。</span><span class="sxs-lookup"><span data-stu-id="a1fad-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="a1fad-168">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="a1fad-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a1fad-169">选择 " **url** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a1fad-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="a1fad-170">选择要修改的条目，然后单击 " **编辑** ![ 编辑图标" ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="a1fad-171">在出现的浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a1fad-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a1fad-172">**阻止/允许**：选择 " **允许** " 或 " **阻止**"。</span><span class="sxs-lookup"><span data-stu-id="a1fad-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="a1fad-173">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="a1fad-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a1fad-174">验证设置是否已关闭 (![ 切换 ](../../media/scc-toggle-off.png)) 并使用 " **过期时间** " 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="a1fad-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="a1fad-175">或</span><span class="sxs-lookup"><span data-stu-id="a1fad-175">or</span></span>

     - <span data-ttu-id="a1fad-176">将切换向右移动以将该项配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="a1fad-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="a1fad-178">.</span><span class="sxs-lookup"><span data-stu-id="a1fad-178">.</span></span>

   - <span data-ttu-id="a1fad-179">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="a1fad-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="a1fad-180">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="a1fad-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-181">使用安全 & 合规性中心删除租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a1fad-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a1fad-182">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="a1fad-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a1fad-183">选择 " **url** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a1fad-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="a1fad-184">选择要删除的条目，然后单击 " **删除** ![ 删除图标" ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="a1fad-185">在出现的警告对话框中，单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="a1fad-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-186">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="a1fad-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-187">使用 PowerShell 在租户允许/阻止列表中添加条目</span><span class="sxs-lookup"><span data-stu-id="a1fad-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a1fad-188">若要添加租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a1fad-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a1fad-189">本示例为 contoso.com 和所有子域 (添加 URL 阻止项，例如，contoso.com、www.contoso.com 和 xyz.abc.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="a1fad-190">由于我们未使用 ExpirationDate 或 NoExpiration 参数，因此该条目将在30天后过期。</span><span class="sxs-lookup"><span data-stu-id="a1fad-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="a1fad-191">有关语法和参数的详细信息，请参阅 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a1fad-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-192">使用 PowerShell 查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a1fad-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a1fad-193">若要查看租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a1fad-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="a1fad-194">本示例返回所有被阻止的 Url。</span><span class="sxs-lookup"><span data-stu-id="a1fad-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="a1fad-195">有关语法和参数的详细信息，请参阅 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a1fad-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-196">使用 PowerShell 修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a1fad-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a1fad-197">您不能修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="a1fad-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="a1fad-198">相反，您需要删除并重新创建该条目。</span><span class="sxs-lookup"><span data-stu-id="a1fad-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="a1fad-199">若要修改租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a1fad-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a1fad-200">本示例将更改指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="a1fad-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="a1fad-201">有关语法和参数的详细信息，请参阅 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a1fad-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-202">使用 PowerShell 删除租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a1fad-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a1fad-203">若要从租户允许/阻止列表中删除条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a1fad-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a1fad-204">本示例将从租户允许/阻止列表中删除指定的 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="a1fad-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="a1fad-205">有关语法和参数的详细信息，请参阅 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a1fad-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="a1fad-206">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="a1fad-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="a1fad-207">允许使用 IP4v 和 IPv6 地址，但 TCP/UDP 端口不允许。</span><span class="sxs-lookup"><span data-stu-id="a1fad-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="a1fad-208">不允许使用文件名扩展 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="a1fad-209">Unicode 不受支持，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="a1fad-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="a1fad-210">如果下列所有语句都为真，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="a1fad-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="a1fad-211">主机名包含一个句点。</span><span class="sxs-lookup"><span data-stu-id="a1fad-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="a1fad-212">句点的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="a1fad-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="a1fad-213">句点的右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="a1fad-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="a1fad-214">例如， `t.co` 允许; `.com` 或 `contoso.` 不允许。</span><span class="sxs-lookup"><span data-stu-id="a1fad-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="a1fad-215">不暗含子路径。</span><span class="sxs-lookup"><span data-stu-id="a1fad-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="a1fad-216">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="a1fad-217">在以下方案中允许使用通配符 ( \* ) ：</span><span class="sxs-lookup"><span data-stu-id="a1fad-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="a1fad-218">左侧通配符后面必须跟一个句点以指定一个子域。</span><span class="sxs-lookup"><span data-stu-id="a1fad-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="a1fad-219">例如， `*.contoso.com` 允许; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="a1fad-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="a1fad-220">右通配符必须遵循正斜杠 (/) 指定路径。</span><span class="sxs-lookup"><span data-stu-id="a1fad-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="a1fad-221">例如， `contoso.com/*` 允许; `contoso.com*` 或 `contoso.com/ab*` 不允许。</span><span class="sxs-lookup"><span data-stu-id="a1fad-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="a1fad-222">所有子路径都不是由右侧通配符暗示的。</span><span class="sxs-lookup"><span data-stu-id="a1fad-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="a1fad-223">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="a1fad-224">`*.com*` 无效 (不是可解析的域，右通配符不跟正斜线) 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="a1fad-225">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="a1fad-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="a1fad-226">在以下方案中，可以使用颚化符 (~) 字符：</span><span class="sxs-lookup"><span data-stu-id="a1fad-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="a1fad-227">左波形符表示域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="a1fad-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="a1fad-228">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="a1fad-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="a1fad-229">包含协议的 URL 项 (例如、、 `http://` `https://` 或 `ftp://`) 将失败，因为 url 条目适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="a1fad-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="a1fad-230">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="a1fad-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="a1fad-231">引号 ( "或" ) 是无效字符。</span><span class="sxs-lookup"><span data-stu-id="a1fad-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="a1fad-232">URL 应尽可能包含所有重定向。</span><span class="sxs-lookup"><span data-stu-id="a1fad-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="a1fad-233">URL 入口应用场景</span><span class="sxs-lookup"><span data-stu-id="a1fad-233">URL entry scenarios</span></span>

<span data-ttu-id="a1fad-234">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="a1fad-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="a1fad-235">方案：不带通配符</span><span class="sxs-lookup"><span data-stu-id="a1fad-235">Scenario: No wildcards</span></span>

<span data-ttu-id="a1fad-236">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a1fad-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="a1fad-237">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="a1fad-238">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="a1fad-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-239">abc-contoso.com</span></span>
  - <span data-ttu-id="a1fad-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a1fad-240">contoso.com/a</span></span>
  - <span data-ttu-id="a1fad-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="a1fad-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="a1fad-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a1fad-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-244">www.contoso.com</span></span>
  - <span data-ttu-id="a1fad-245">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="a1fad-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a1fad-246">**块匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-246">**Block match**:</span></span>

  - <span data-ttu-id="a1fad-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-247">contoso.com</span></span>
  - <span data-ttu-id="a1fad-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a1fad-248">contoso.com/a</span></span>
  - <span data-ttu-id="a1fad-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="a1fad-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="a1fad-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a1fad-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-252">www.contoso.com</span></span>
  - <span data-ttu-id="a1fad-253">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="a1fad-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a1fad-254">**阻止不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="a1fad-255">方案： Left 通配符 (子域) </span><span class="sxs-lookup"><span data-stu-id="a1fad-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="a1fad-256">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a1fad-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="a1fad-257">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a1fad-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-258">www.contoso.com</span></span>
  - <span data-ttu-id="a1fad-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a1fad-260">**允许不匹配** 和 **阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a1fad-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-261">123contoso.com</span></span>
  - <span data-ttu-id="a1fad-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-262">contoso.com</span></span>
  - <span data-ttu-id="a1fad-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="a1fad-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a1fad-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="a1fad-265">方案： path 顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="a1fad-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="a1fad-266">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="a1fad-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="a1fad-267">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a1fad-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="a1fad-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="a1fad-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a1fad-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a1fad-270">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="a1fad-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="a1fad-271">**允许不匹配** 和 **阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a1fad-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-272">contoso.com</span></span>
  - <span data-ttu-id="a1fad-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a1fad-273">contoso.com/a</span></span>
  - <span data-ttu-id="a1fad-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-274">www.contoso.com</span></span>
  - <span data-ttu-id="a1fad-275">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="a1fad-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="a1fad-276">方案：左波形符</span><span class="sxs-lookup"><span data-stu-id="a1fad-276">Scenario: Left tilde</span></span>

<span data-ttu-id="a1fad-277">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a1fad-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="a1fad-278">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a1fad-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-279">contoso.com</span></span>
  - <span data-ttu-id="a1fad-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-280">www.contoso.com</span></span>
  - <span data-ttu-id="a1fad-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a1fad-282">**允许不匹配** 和 **阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a1fad-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-283">123contoso.com</span></span>
  - <span data-ttu-id="a1fad-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a1fad-284">contoso.com/abc</span></span>
  - <span data-ttu-id="a1fad-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a1fad-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="a1fad-286">方案：右侧通配符后缀</span><span class="sxs-lookup"><span data-stu-id="a1fad-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="a1fad-287">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a1fad-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="a1fad-288">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a1fad-289">contoso/？ q = whatever@fabrikam</span><span class="sxs-lookup"><span data-stu-id="a1fad-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="a1fad-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a1fad-290">contoso.com/a</span></span>
  - <span data-ttu-id="a1fad-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a1fad-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a1fad-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a1fad-292">contoso.com/ab</span></span>
  - <span data-ttu-id="a1fad-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a1fad-293">contoso.com/b</span></span>
  - <span data-ttu-id="a1fad-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a1fad-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a1fad-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a1fad-295">contoso.com/ba</span></span>

- <span data-ttu-id="a1fad-296">**Allow 不匹配** 和 **阻止不匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="a1fad-297">方案：左通配符子域和右侧通配符后缀</span><span class="sxs-lookup"><span data-stu-id="a1fad-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="a1fad-298">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a1fad-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="a1fad-299">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a1fad-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a1fad-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="a1fad-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a1fad-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a1fad-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a1fad-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="a1fad-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a1fad-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a1fad-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a1fad-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="a1fad-305">**Allow 不匹配** 和 **阻止不匹配**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a1fad-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="a1fad-306">方案：左和右波形符</span><span class="sxs-lookup"><span data-stu-id="a1fad-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="a1fad-307">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="a1fad-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="a1fad-308">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a1fad-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-309">contoso.com</span></span>
  - <span data-ttu-id="a1fad-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a1fad-310">contoso.com/a</span></span>
  - <span data-ttu-id="a1fad-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-311">www.contoso.com</span></span>
  - <span data-ttu-id="a1fad-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a1fad-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="a1fad-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a1fad-314">**允许不匹配** 和 **阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a1fad-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-315">123contoso.com</span></span>
  - <span data-ttu-id="a1fad-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="a1fad-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="a1fad-317">方案： IP 地址</span><span class="sxs-lookup"><span data-stu-id="a1fad-317">Scenario: IP address</span></span>

<span data-ttu-id="a1fad-318">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="a1fad-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="a1fad-319">**允许匹配** 和 **阻止匹配**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="a1fad-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="a1fad-320">**允许不匹配** 和 **阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a1fad-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a1fad-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="a1fad-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a1fad-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="a1fad-323">使用右侧通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="a1fad-323">IP address with right wildcard</span></span>

<span data-ttu-id="a1fad-324">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="a1fad-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="a1fad-325">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a1fad-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="a1fad-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="a1fad-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="a1fad-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="a1fad-328">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="a1fad-328">Examples of invalid entries</span></span>

<span data-ttu-id="a1fad-329">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="a1fad-329">The following entries are invalid:</span></span>

- <span data-ttu-id="a1fad-330">**缺少或无效的域值**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="a1fad-331">尚未</span><span class="sxs-lookup"><span data-stu-id="a1fad-331">contoso</span></span>
  - <span data-ttu-id="a1fad-332">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="a1fad-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="a1fad-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-333">\*.com</span></span>
  - <span data-ttu-id="a1fad-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="a1fad-334">\*.pdf</span></span>

- <span data-ttu-id="a1fad-335">**文本上的通配符或不含间距的字符**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="a1fad-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-336">\*contoso.com</span></span>
  - <span data-ttu-id="a1fad-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="a1fad-337">contoso.com\*</span></span>
  - <span data-ttu-id="a1fad-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a1fad-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="a1fad-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="a1fad-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="a1fad-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="a1fad-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="a1fad-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="a1fad-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="a1fad-342">**带有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="a1fad-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="a1fad-343">contoso.com:443</span></span>
  - <span data-ttu-id="a1fad-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="a1fad-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="a1fad-345">**不描述的通配符**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="a1fad-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="a1fad-346">\*.\*</span></span>

- <span data-ttu-id="a1fad-347">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="a1fad-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="a1fad-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="a1fad-348">conto\*so.com</span></span>
  - <span data-ttu-id="a1fad-349">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="a1fad-349">conto~so.com</span></span>

- <span data-ttu-id="a1fad-350">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="a1fad-350">**Double wildcards**</span></span>

  - <span data-ttu-id="a1fad-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="a1fad-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="a1fad-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="a1fad-352">contoso.com/\*/\*</span></span>
