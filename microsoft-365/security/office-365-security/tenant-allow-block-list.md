---
title: 在租户允许/阻止列表中管理允许和阻止的 URL
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
description: 管理员可以了解如何在安全与合规中心的租户允许/阻止& URL 条目。
ms.openlocfilehash: 4bf5e2e29a9f48c434be527a2447ca4bf98c4208
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659994"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-103">管理租户允许/阻止列表中的 URL</span><span class="sxs-lookup"><span data-stu-id="11f77-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="11f77-104">本文中所述的功能为预览版，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="11f77-104">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="11f77-105">在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，您可能与 EOP 筛选裁定不一致。</span><span class="sxs-lookup"><span data-stu-id="11f77-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="11f77-106">例如，一条好邮件可能标记为误报 (误报) ，或者可能允许错误邮件通过漏报 (漏报) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="11f77-107">安全与合规中心中的租户&/阻止列表提供了一种手动替代 Microsoft 365 筛选裁定的方法。</span><span class="sxs-lookup"><span data-stu-id="11f77-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="11f77-108">租户允许/阻止列表在邮件流期间和用户单击时使用。</span><span class="sxs-lookup"><span data-stu-id="11f77-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="11f77-109">可以在租户允许/阻止列表中指定允许或阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="11f77-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="11f77-110">本主题介绍如何在安全 & 合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止列表条目;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="11f77-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="11f77-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="11f77-112">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="11f77-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="11f77-113">若要直接转到"租户允许 **/阻止列表"** 页，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="11f77-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="11f77-114">本文稍后的"租户允许/阻止列表"一节的 URL 语法中介绍了 [可用的 URL](#url-syntax-for-the-tenant-allowblock-list) 值。</span><span class="sxs-lookup"><span data-stu-id="11f77-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="11f77-115">租户允许/阻止列表允许最多 500 个 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="11f77-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="11f77-116">条目应在 15 分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="11f77-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="11f77-117">阻止条目优先于允许条目。</span><span class="sxs-lookup"><span data-stu-id="11f77-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="11f77-118">默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="11f77-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="11f77-119">可以指定日期或将其设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="11f77-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="11f77-120">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="11f77-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="11f77-121">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="11f77-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="11f77-122">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="11f77-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="11f77-123">若要在租户允许/阻止列表中添加和删除值，你需要是组织 **管理或** 安全管理员角色 **组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="11f77-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="11f77-124">若要对租户允许/阻止列表进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="11f77-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="11f77-125">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="11f77-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="11f77-126">**注意**：</span><span class="sxs-lookup"><span data-stu-id="11f77-126">**Notes**:</span></span>

  - <span data-ttu-id="11f77-127">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="11f77-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="11f77-128">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="11f77-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="11f77-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="11f77-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-130">使用安全&中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="11f77-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="11f77-131">有关 URL 条目的语法的详细信息，请参阅本文稍后介绍的"租户允许 [/阻止](#url-syntax-for-the-tenant-allowblock-list) 列表"一节的 URL 语法。</span><span class="sxs-lookup"><span data-stu-id="11f77-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="11f77-132">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="11f77-133">在 **"租户允许/阻止列表** "页上，验证是否选择了 **"URL"** 选项卡，然后单击"添加 **"**</span><span class="sxs-lookup"><span data-stu-id="11f77-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="11f77-134">在 **出现的"添加新 URL"** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="11f77-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="11f77-135">**添加包含通配符的 URL：** 每行输入一个 URL，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="11f77-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="11f77-136">**阻止/允许**：选择 **是允许还是\*\*\*\*阻止** 指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="11f77-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="11f77-137">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="11f77-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="11f77-138">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="11f77-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="11f77-139">或</span><span class="sxs-lookup"><span data-stu-id="11f77-139">or</span></span>

     - <span data-ttu-id="11f77-140">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="11f77-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="11f77-142">.</span><span class="sxs-lookup"><span data-stu-id="11f77-142">.</span></span>

   - <span data-ttu-id="11f77-143">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="11f77-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="11f77-144">完成后，单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-145">使用安全&合规中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="11f77-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="11f77-146">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="11f77-147">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="11f77-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="11f77-148">单击以下列标题以按升序或降序排序：</span><span class="sxs-lookup"><span data-stu-id="11f77-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="11f77-149">**值**</span><span class="sxs-lookup"><span data-stu-id="11f77-149">**Value**</span></span>
- <span data-ttu-id="11f77-150">**操作**： **阻止** 或 **允许**。</span><span class="sxs-lookup"><span data-stu-id="11f77-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="11f77-151">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="11f77-151">**Last updated date**</span></span>
- <span data-ttu-id="11f77-152">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="11f77-152">**Expiration date**</span></span>
- <span data-ttu-id="11f77-153">**注意**</span><span class="sxs-lookup"><span data-stu-id="11f77-153">**Note**</span></span>

<span data-ttu-id="11f77-154">单击 **"分组**"按"操作" ("阻止"或") "或"无"对 **条目进行分组**。  </span><span class="sxs-lookup"><span data-stu-id="11f77-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="11f77-155">单击 **"搜索**"，输入全部或部分值，然后按 Enter 查找特定值。</span><span class="sxs-lookup"><span data-stu-id="11f77-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="11f77-156">完成后，单击" **清除搜索清除** ![ 搜索"图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="11f77-157">单击 **"筛选"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-157">Click **Filter**.</span></span> <span data-ttu-id="11f77-158">在 **出现的"** 筛选器"飞出中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="11f77-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="11f77-159">**操作**：选择 **"允许"\*\*\*\*和/或"阻止**"。</span><span class="sxs-lookup"><span data-stu-id="11f77-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="11f77-160">**永不过期**：选择 (![ 关闭) ](../../media/scc-toggle-off.png) 或 (![ 切换 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="11f77-161">**Last updated**： Select a start date (**From**) ， an end date (**To**) both.</span><span class="sxs-lookup"><span data-stu-id="11f77-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="11f77-162">**到期日期：** 选择开始日期 (**开始日期) 、** 结束日期 () 两者。 </span><span class="sxs-lookup"><span data-stu-id="11f77-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="11f77-163">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="11f77-164">若要清除现有筛选器，请单击 **"筛选器**"，在出现的 **"** 筛选器"飞出中，单击 **"清除筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-165">使用安全&合规中心修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="11f77-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="11f77-166">不能修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="11f77-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="11f77-167">相反，需要删除条目并重新创建它。</span><span class="sxs-lookup"><span data-stu-id="11f77-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="11f77-168">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="11f77-169">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="11f77-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="11f77-170">选择要修改的条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="11f77-171">在出现的飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="11f77-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="11f77-172">**阻止/允许**：选择 **"允许**"或"**阻止"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="11f77-173">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="11f77-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="11f77-174">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="11f77-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="11f77-175">或</span><span class="sxs-lookup"><span data-stu-id="11f77-175">or</span></span>

     - <span data-ttu-id="11f77-176">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="11f77-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="11f77-178">.</span><span class="sxs-lookup"><span data-stu-id="11f77-178">.</span></span>

   - <span data-ttu-id="11f77-179">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="11f77-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="11f77-180">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="11f77-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-181">使用安全&合规中心从租户允许/阻止列表中删除条目</span><span class="sxs-lookup"><span data-stu-id="11f77-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="11f77-182">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="11f77-183">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="11f77-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="11f77-184">选择要删除的条目，然后单击"删除 **"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="11f77-185">在出现的警告对话框中，单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="11f77-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-186">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="11f77-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-187">使用 PowerShell 在租户允许/阻止列表中添加条目</span><span class="sxs-lookup"><span data-stu-id="11f77-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="11f77-188">若要在租户允许/阻止列表中添加条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11f77-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="11f77-189">此示例为网站和contoso.com域（例如， (、contoso.com、www.contoso.com 和 xyz.abc.contoso.com) ）添加 URL 阻止xyz.abc.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="11f77-190">由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="11f77-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="11f77-191">有关语法和参数的详细信息，请参阅[New-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="11f77-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-192">使用 PowerShell 查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="11f77-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="11f77-193">若要查看租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11f77-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="11f77-194">此示例返回所有阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="11f77-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="11f77-195">有关语法和参数的详细信息，请参阅[Get-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="11f77-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-196">使用 PowerShell 修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="11f77-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="11f77-197">不能修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="11f77-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="11f77-198">相反，需要删除条目并重新创建它。</span><span class="sxs-lookup"><span data-stu-id="11f77-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="11f77-199">若要修改租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11f77-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="11f77-200">本示例更改指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="11f77-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="11f77-201">有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="11f77-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-202">使用 PowerShell 从租户允许/阻止列表中删除条目</span><span class="sxs-lookup"><span data-stu-id="11f77-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="11f77-203">若要从租户允许/阻止列表中删除条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11f77-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="11f77-204">此示例从租户允许/阻止列表中删除指定的 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="11f77-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="11f77-205">有关语法和参数的详细信息，请参阅[Remove-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="11f77-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="11f77-206">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="11f77-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="11f77-207">允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="11f77-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="11f77-208">例如，不允许使用 (扩展名test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="11f77-209">不支持 Unicode，但 Punycode 支持。</span><span class="sxs-lookup"><span data-stu-id="11f77-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="11f77-210">如果以下所有语句都为 true，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="11f77-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="11f77-211">主机名包含一个时间段。</span><span class="sxs-lookup"><span data-stu-id="11f77-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="11f77-212">在时间段的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="11f77-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="11f77-213">此期间右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="11f77-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="11f77-214">例如， `t.co` 允许; `.com` `contoso.` 或不允许。</span><span class="sxs-lookup"><span data-stu-id="11f77-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="11f77-215">不隐含子路径。</span><span class="sxs-lookup"><span data-stu-id="11f77-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="11f77-216">例如， `contoso.com` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="11f77-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="11f77-217">在下列 (允许) \*通配符：</span><span class="sxs-lookup"><span data-stu-id="11f77-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="11f77-218">左通配符后必须跟一个时间段，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="11f77-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="11f77-219">例如， `*.contoso.com` 允许; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="11f77-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="11f77-220">右通配符必须按照正斜杠 (/) 指定路径。</span><span class="sxs-lookup"><span data-stu-id="11f77-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="11f77-221">例如， `contoso.com/*` 允许; `contoso.com*` `contoso.com/ab*` 或不允许。</span><span class="sxs-lookup"><span data-stu-id="11f77-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="11f77-222">右通配符不隐含所有子路径。</span><span class="sxs-lookup"><span data-stu-id="11f77-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="11f77-223">例如， `contoso.com/*` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="11f77-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="11f77-224">`*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。</span><span class="sxs-lookup"><span data-stu-id="11f77-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="11f77-225">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="11f77-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="11f77-226">下列情况下 (~) 符：</span><span class="sxs-lookup"><span data-stu-id="11f77-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="11f77-227">左波浪符表示域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="11f77-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="11f77-228">例如 `~contoso.com` ，includes `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="11f77-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="11f77-229">包含协议（例如， (，或) ）的 URL 条目将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="11f77-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="11f77-230">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="11f77-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="11f77-231">引号 ("或") 无效字符。</span><span class="sxs-lookup"><span data-stu-id="11f77-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="11f77-232">URL 应包含所有重定向（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="11f77-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="11f77-233">URL 条目方案</span><span class="sxs-lookup"><span data-stu-id="11f77-233">URL entry scenarios</span></span>

<span data-ttu-id="11f77-234">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="11f77-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="11f77-235">方案：无通配符</span><span class="sxs-lookup"><span data-stu-id="11f77-235">Scenario: No wildcards</span></span>

<span data-ttu-id="11f77-236">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="11f77-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="11f77-237">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="11f77-238">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="11f77-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-239">abc-contoso.com</span></span>
  - <span data-ttu-id="11f77-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="11f77-240">contoso.com/a</span></span>
  - <span data-ttu-id="11f77-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="11f77-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="11f77-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="11f77-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-244">www.contoso.com</span></span>
  - <span data-ttu-id="11f77-245">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="11f77-246">**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-246">**Block match**:</span></span>

  - <span data-ttu-id="11f77-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-247">contoso.com</span></span>
  - <span data-ttu-id="11f77-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="11f77-248">contoso.com/a</span></span>
  - <span data-ttu-id="11f77-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="11f77-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="11f77-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="11f77-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-252">www.contoso.com</span></span>
  - <span data-ttu-id="11f77-253">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="11f77-254">**阻止不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="11f77-255">方案：将通配符 (子域) </span><span class="sxs-lookup"><span data-stu-id="11f77-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="11f77-256">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="11f77-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="11f77-257">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="11f77-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-258">www.contoso.com</span></span>
  - <span data-ttu-id="11f77-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="11f77-260">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="11f77-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-261">123contoso.com</span></span>
  - <span data-ttu-id="11f77-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-262">contoso.com</span></span>
  - <span data-ttu-id="11f77-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="11f77-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="11f77-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="11f77-265">方案：路径顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="11f77-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="11f77-266">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="11f77-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="11f77-267">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="11f77-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="11f77-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="11f77-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="11f77-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="11f77-270">contoso.com/a/？q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="11f77-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="11f77-271">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="11f77-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-272">contoso.com</span></span>
  - <span data-ttu-id="11f77-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="11f77-273">contoso.com/a</span></span>
  - <span data-ttu-id="11f77-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-274">www.contoso.com</span></span>
  - <span data-ttu-id="11f77-275">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="11f77-276">方案：左波浪符</span><span class="sxs-lookup"><span data-stu-id="11f77-276">Scenario: Left tilde</span></span>

<span data-ttu-id="11f77-277">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="11f77-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="11f77-278">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="11f77-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-279">contoso.com</span></span>
  - <span data-ttu-id="11f77-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-280">www.contoso.com</span></span>
  - <span data-ttu-id="11f77-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="11f77-282">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="11f77-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-283">123contoso.com</span></span>
  - <span data-ttu-id="11f77-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="11f77-284">contoso.com/abc</span></span>
  - <span data-ttu-id="11f77-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="11f77-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="11f77-286">方案：右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="11f77-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="11f77-287">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="11f77-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="11f77-288">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="11f77-289">contoso.com/？q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="11f77-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="11f77-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="11f77-290">contoso.com/a</span></span>
  - <span data-ttu-id="11f77-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="11f77-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="11f77-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="11f77-292">contoso.com/ab</span></span>
  - <span data-ttu-id="11f77-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="11f77-293">contoso.com/b</span></span>
  - <span data-ttu-id="11f77-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="11f77-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="11f77-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="11f77-295">contoso.com/ba</span></span>

- <span data-ttu-id="11f77-296">**允许不匹配和\*\*\*\*阻止不匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="11f77-297">方案：左通配符子域和右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="11f77-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="11f77-298">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="11f77-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="11f77-299">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="11f77-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="11f77-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="11f77-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="11f77-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="11f77-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="11f77-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="11f77-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="11f77-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="11f77-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="11f77-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="11f77-305">**允许不匹配和\*\*\*\*阻止不匹配**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="11f77-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="11f77-306">方案：向左和向右波浪符</span><span class="sxs-lookup"><span data-stu-id="11f77-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="11f77-307">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="11f77-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="11f77-308">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="11f77-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-309">contoso.com</span></span>
  - <span data-ttu-id="11f77-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="11f77-310">contoso.com/a</span></span>
  - <span data-ttu-id="11f77-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-311">www.contoso.com</span></span>
  - <span data-ttu-id="11f77-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="11f77-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="11f77-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="11f77-314">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="11f77-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-315">123contoso.com</span></span>
  - <span data-ttu-id="11f77-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="11f77-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="11f77-317">方案：IP 地址</span><span class="sxs-lookup"><span data-stu-id="11f77-317">Scenario: IP address</span></span>

<span data-ttu-id="11f77-318">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="11f77-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="11f77-319">**允许匹配** 和 **阻止匹配**：1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="11f77-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="11f77-320">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="11f77-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="11f77-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="11f77-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="11f77-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="11f77-323">具有右通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11f77-323">IP address with right wildcard</span></span>

<span data-ttu-id="11f77-324">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="11f77-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="11f77-325">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="11f77-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="11f77-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="11f77-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="11f77-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="11f77-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="11f77-328">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="11f77-328">Examples of invalid entries</span></span>

<span data-ttu-id="11f77-329">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="11f77-329">The following entries are invalid:</span></span>

- <span data-ttu-id="11f77-330">**缺少或无效的域值**：</span><span class="sxs-lookup"><span data-stu-id="11f77-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="11f77-331">contoso</span><span class="sxs-lookup"><span data-stu-id="11f77-331">contoso</span></span>
  - <span data-ttu-id="11f77-332">\*.contoso。\*</span><span class="sxs-lookup"><span data-stu-id="11f77-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="11f77-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="11f77-333">\*.com</span></span>
  - <span data-ttu-id="11f77-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="11f77-334">\*.pdf</span></span>

- <span data-ttu-id="11f77-335">**文本上的通配符或不带空格字符：**</span><span class="sxs-lookup"><span data-stu-id="11f77-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="11f77-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="11f77-336">\*contoso.com</span></span>
  - <span data-ttu-id="11f77-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="11f77-337">contoso.com\*</span></span>
  - <span data-ttu-id="11f77-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="11f77-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="11f77-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="11f77-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="11f77-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="11f77-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="11f77-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="11f77-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="11f77-342">**具有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="11f77-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="11f77-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="11f77-343">contoso.com:443</span></span>
  - <span data-ttu-id="11f77-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="11f77-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="11f77-345">**非描述性通配符**：</span><span class="sxs-lookup"><span data-stu-id="11f77-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="11f77-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="11f77-346">\*.\*</span></span>

- <span data-ttu-id="11f77-347">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="11f77-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="11f77-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="11f77-348">conto\*so.com</span></span>
  - <span data-ttu-id="11f77-349">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="11f77-349">conto~so.com</span></span>

- <span data-ttu-id="11f77-350">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="11f77-350">**Double wildcards**</span></span>

  - <span data-ttu-id="11f77-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="11f77-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="11f77-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="11f77-352">contoso.com/\*/\*</span></span>
