---
title: 在租户允许/阻止列表中管理允许和阻止
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
description: 管理员可以了解如何在安全门户的租户允许/阻止列表中配置允许和阻止。
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799709"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-103">管理租户允许/阻止列表中的允许和阻止</span><span class="sxs-lookup"><span data-stu-id="2fad6-103">Managing allows and blocks in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="2fad6-104">本文中所述的功能为预览版，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="2fad6-104">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="2fad6-105">在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，您可能与 EOP 筛选裁定不一致。</span><span class="sxs-lookup"><span data-stu-id="2fad6-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="2fad6-106">例如，一条好邮件可能标记为误报 (误报) ，或者可能允许错误邮件通过漏报 (漏报) 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="2fad6-107">安全与合规中心中的租户&/阻止列表提供了一种手动替代 Microsoft 365 筛选裁定的方法。</span><span class="sxs-lookup"><span data-stu-id="2fad6-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="2fad6-108">租户允许/阻止列表在邮件流期间和用户单击时使用。</span><span class="sxs-lookup"><span data-stu-id="2fad6-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="2fad6-109">可以在租户允许/阻止列表中指定允许或阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="2fad6-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="2fad6-110">本主题介绍如何在安全与合规中心或 PowerShell & (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止列表条目;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2fad6-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2fad6-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2fad6-112">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="2fad6-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2fad6-113">若要直接转到租户允许 **/阻止列表** 页，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="2fad6-114">本文稍后的"租户允许/阻止列表"一节的 URL 语法中介绍了 [可用的](#url-syntax-for-the-tenant-allowblock-list) URL 值。</span><span class="sxs-lookup"><span data-stu-id="2fad6-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="2fad6-115">租户允许/阻止列表允许最多 500 个 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="2fad6-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="2fad6-116">条目应在 15 分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="2fad6-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="2fad6-117">阻止条目优先于允许条目。</span><span class="sxs-lookup"><span data-stu-id="2fad6-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="2fad6-118">默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="2fad6-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="2fad6-119">可以指定日期或将其设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="2fad6-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="2fad6-120">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2fad6-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2fad6-121">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2fad6-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2fad6-122">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="2fad6-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2fad6-123">若要在租户允许/阻止列表中添加和删除值，你需要是组织 **管理或\*\*\*\*安全** 管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="2fad6-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2fad6-124">若要对租户允许/阻止列表进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="2fad6-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="2fad6-125">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2fad6-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="2fad6-126">**注意**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-126">**Notes**:</span></span>

  - <span data-ttu-id="2fad6-127">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="2fad6-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2fad6-128">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="2fad6-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="2fad6-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="2fad6-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-130">使用安全&合规中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="2fad6-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2fad6-131">有关 URL 条目的语法的详细信息，请参阅本文稍后介绍的"租户允许 [/阻止](#url-syntax-for-the-tenant-allowblock-list) 列表"一节的 URL 语法。</span><span class="sxs-lookup"><span data-stu-id="2fad6-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="2fad6-132">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2fad6-133">在 **"租户允许/阻止列表** "页上，验证是否选择了 **"URL"** 选项卡，然后单击"添加 **"**</span><span class="sxs-lookup"><span data-stu-id="2fad6-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="2fad6-134">在 **出现的"添加新 URL"** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="2fad6-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2fad6-135">**添加包含通配符的 URL：** 每行输入一个 URL，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="2fad6-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="2fad6-136">**阻止/允许**：选择是允许还是 **阻止** 指定的 URL。 </span><span class="sxs-lookup"><span data-stu-id="2fad6-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="2fad6-137">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="2fad6-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2fad6-138">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="2fad6-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="2fad6-139">或者</span><span class="sxs-lookup"><span data-stu-id="2fad6-139">or</span></span>

     - <span data-ttu-id="2fad6-140">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="2fad6-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="2fad6-142">.</span><span class="sxs-lookup"><span data-stu-id="2fad6-142">.</span></span>

   - <span data-ttu-id="2fad6-143">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="2fad6-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="2fad6-144">完成后，单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-145">使用安全&合规中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="2fad6-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2fad6-146">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2fad6-147">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fad6-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="2fad6-148">单击以下列标题以按升序或降序排序：</span><span class="sxs-lookup"><span data-stu-id="2fad6-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="2fad6-149">**值**</span><span class="sxs-lookup"><span data-stu-id="2fad6-149">**Value**</span></span>
- <span data-ttu-id="2fad6-150">**操作**： **阻止** 或 **允许**。</span><span class="sxs-lookup"><span data-stu-id="2fad6-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="2fad6-151">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="2fad6-151">**Last updated date**</span></span>
- <span data-ttu-id="2fad6-152">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="2fad6-152">**Expiration date**</span></span>
- <span data-ttu-id="2fad6-153">**注意**</span><span class="sxs-lookup"><span data-stu-id="2fad6-153">**Note**</span></span>

<span data-ttu-id="2fad6-154">单击 **"分组**"按"操作" ("阻止"或") "或"无"对 **条目进行分组**。  </span><span class="sxs-lookup"><span data-stu-id="2fad6-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="2fad6-155">单击 **"搜索**"，输入全部或部分值，然后按 Enter 查找特定值。</span><span class="sxs-lookup"><span data-stu-id="2fad6-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="2fad6-156">完成后，单击"清除 **搜索清除** ![ 搜索"图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="2fad6-157">单击 **"筛选"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-157">Click **Filter**.</span></span> <span data-ttu-id="2fad6-158">在 **出现的"** 筛选器"飞出中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="2fad6-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="2fad6-159">**操作**：选择 **"允许"\*\*\*\*和/或"阻止**"。</span><span class="sxs-lookup"><span data-stu-id="2fad6-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="2fad6-160">**永不过期**： 选择关闭： ![ 关闭 ](../../media/scc-toggle-off.png) 或打开： ![ 切换。 ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="2fad6-160">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="2fad6-161">**Last updated**： Select a start date (**From**) ， an end date (**To**) both.</span><span class="sxs-lookup"><span data-stu-id="2fad6-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="2fad6-162">**到期日期：** 选择开始日期 (开始日期) 、结束日期 () 两者。  </span><span class="sxs-lookup"><span data-stu-id="2fad6-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="2fad6-163">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="2fad6-164">若要清除现有筛选器，请单击 **"筛选器**"，在出现的 **"** 筛选器"飞出中，单击 **"清除筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-165">使用安全&合规中心修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="2fad6-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2fad6-166">不能修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="2fad6-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="2fad6-167">相反，需要删除条目并重新创建它。</span><span class="sxs-lookup"><span data-stu-id="2fad6-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="2fad6-168">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2fad6-169">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fad6-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="2fad6-170">选择要修改的条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="2fad6-171">在出现的飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="2fad6-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2fad6-172">**阻止/允许**：选择 **"允许"** 或"**阻止"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="2fad6-173">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="2fad6-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2fad6-174">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="2fad6-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="2fad6-175">或者</span><span class="sxs-lookup"><span data-stu-id="2fad6-175">or</span></span>

     - <span data-ttu-id="2fad6-176">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="2fad6-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="2fad6-178">.</span><span class="sxs-lookup"><span data-stu-id="2fad6-178">.</span></span>

   - <span data-ttu-id="2fad6-179">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="2fad6-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="2fad6-180">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2fad6-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-181">使用安全&合规中心从租户允许/阻止列表中删除条目</span><span class="sxs-lookup"><span data-stu-id="2fad6-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2fad6-182">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2fad6-183">选择 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fad6-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="2fad6-184">选择要删除的条目，然后单击"删除 **删除"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="2fad6-185">在出现的警告对话框中，单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="2fad6-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-186">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="2fad6-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-187">使用 PowerShell 在租户允许/阻止列表中添加条目</span><span class="sxs-lookup"><span data-stu-id="2fad6-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2fad6-188">若要在租户允许/阻止列表中添加条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2fad6-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="2fad6-189">此示例为网站和contoso.com域（例如 (、contoso.com、www.contoso.com和xyz.abc.contoso.com) ）添加 URL 阻止xyz.abc.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="2fad6-190">由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="2fad6-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="2fad6-191">有关语法和参数的详细信息，请参阅[New-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="2fad6-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-192">使用 PowerShell 查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="2fad6-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2fad6-193">若要查看租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2fad6-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="2fad6-194">此示例返回所有阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="2fad6-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="2fad6-195">有关语法和参数的详细信息，请参阅[Get-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="2fad6-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-196">使用 PowerShell 修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="2fad6-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2fad6-197">不能修改 URL 值本身。</span><span class="sxs-lookup"><span data-stu-id="2fad6-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="2fad6-198">相反，需要删除条目并重新创建它。</span><span class="sxs-lookup"><span data-stu-id="2fad6-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="2fad6-199">若要修改租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2fad6-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="2fad6-200">本示例更改指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="2fad6-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="2fad6-201">有关语法和参数的详细信息，请参阅[Set-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="2fad6-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-202">使用 PowerShell 从租户允许/阻止列表中删除条目</span><span class="sxs-lookup"><span data-stu-id="2fad6-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="2fad6-203">若要从租户允许/阻止列表中删除条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2fad6-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="2fad6-204">此示例从租户允许/阻止列表中删除指定的 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="2fad6-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="2fad6-205">有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="2fad6-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="2fad6-206">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="2fad6-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="2fad6-207">允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="2fad6-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="2fad6-208">例如，不允许使用 (扩展名test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="2fad6-209">不支持 Unicode，但 Punycode 支持。</span><span class="sxs-lookup"><span data-stu-id="2fad6-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="2fad6-210">如果以下所有语句都为 true，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="2fad6-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="2fad6-211">主机名包含一个时间段。</span><span class="sxs-lookup"><span data-stu-id="2fad6-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="2fad6-212">在时间段的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="2fad6-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="2fad6-213">此期间右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="2fad6-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="2fad6-214">例如， `t.co` 允许; `.com` `contoso.` 或不允许。</span><span class="sxs-lookup"><span data-stu-id="2fad6-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="2fad6-215">不隐含子路径。</span><span class="sxs-lookup"><span data-stu-id="2fad6-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="2fad6-216">例如， `contoso.com` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="2fad6-217">以下 (允许) \*通配符：</span><span class="sxs-lookup"><span data-stu-id="2fad6-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="2fad6-218">左通配符后必须跟一个时间段，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="2fad6-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="2fad6-219">例如， `*.contoso.com` 允许; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="2fad6-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="2fad6-220">右通配符必须遵循正斜杠 (/) 指定路径。</span><span class="sxs-lookup"><span data-stu-id="2fad6-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="2fad6-221">例如， `contoso.com/*` 允许; `contoso.com*` `contoso.com/ab*` 或不允许。</span><span class="sxs-lookup"><span data-stu-id="2fad6-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="2fad6-222">右通配符不隐含所有子路径。</span><span class="sxs-lookup"><span data-stu-id="2fad6-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="2fad6-223">例如， `contoso.com/*` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="2fad6-224">`*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="2fad6-225">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="2fad6-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="2fad6-226">下列情况下 (~) 符：</span><span class="sxs-lookup"><span data-stu-id="2fad6-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="2fad6-227">左波浪符表示域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="2fad6-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="2fad6-228">例如 `~contoso.com` ，includes `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="2fad6-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="2fad6-229">包含协议（例如， (，或) ）的 URL 条目将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="2fad6-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="2fad6-230">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="2fad6-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="2fad6-231">引号 ("或") 无效字符。</span><span class="sxs-lookup"><span data-stu-id="2fad6-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="2fad6-232">URL 应包含所有重定向（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="2fad6-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="2fad6-233">URL 条目方案</span><span class="sxs-lookup"><span data-stu-id="2fad6-233">URL entry scenarios</span></span>

<span data-ttu-id="2fad6-234">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="2fad6-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="2fad6-235">方案：无通配符</span><span class="sxs-lookup"><span data-stu-id="2fad6-235">Scenario: No wildcards</span></span>

<span data-ttu-id="2fad6-236">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2fad6-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="2fad6-237">**允许匹配**：contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="2fad6-238">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="2fad6-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-239">abc-contoso.com</span></span>
  - <span data-ttu-id="2fad6-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2fad6-240">contoso.com/a</span></span>
  - <span data-ttu-id="2fad6-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="2fad6-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="2fad6-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="2fad6-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-244">www.contoso.com</span></span>
  - <span data-ttu-id="2fad6-245">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="2fad6-246">**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-246">**Block match**:</span></span>

  - <span data-ttu-id="2fad6-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-247">contoso.com</span></span>
  - <span data-ttu-id="2fad6-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2fad6-248">contoso.com/a</span></span>
  - <span data-ttu-id="2fad6-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="2fad6-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="2fad6-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="2fad6-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-252">www.contoso.com</span></span>
  - <span data-ttu-id="2fad6-253">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="2fad6-254">**阻止不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="2fad6-255">方案：将通配符 (子域) </span><span class="sxs-lookup"><span data-stu-id="2fad6-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="2fad6-256">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2fad6-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="2fad6-257">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2fad6-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-258">www.contoso.com</span></span>
  - <span data-ttu-id="2fad6-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2fad6-260">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2fad6-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-261">123contoso.com</span></span>
  - <span data-ttu-id="2fad6-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-262">contoso.com</span></span>
  - <span data-ttu-id="2fad6-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="2fad6-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2fad6-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="2fad6-265">方案：路径顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="2fad6-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="2fad6-266">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="2fad6-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="2fad6-267">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2fad6-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="2fad6-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="2fad6-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2fad6-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2fad6-270">contoso.com/a/？q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="2fad6-271">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2fad6-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-272">contoso.com</span></span>
  - <span data-ttu-id="2fad6-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2fad6-273">contoso.com/a</span></span>
  - <span data-ttu-id="2fad6-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-274">www.contoso.com</span></span>
  - <span data-ttu-id="2fad6-275">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="2fad6-276">方案：左波浪符</span><span class="sxs-lookup"><span data-stu-id="2fad6-276">Scenario: Left tilde</span></span>

<span data-ttu-id="2fad6-277">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2fad6-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="2fad6-278">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2fad6-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-279">contoso.com</span></span>
  - <span data-ttu-id="2fad6-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-280">www.contoso.com</span></span>
  - <span data-ttu-id="2fad6-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2fad6-282">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2fad6-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-283">123contoso.com</span></span>
  - <span data-ttu-id="2fad6-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2fad6-284">contoso.com/abc</span></span>
  - <span data-ttu-id="2fad6-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2fad6-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="2fad6-286">方案：右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="2fad6-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="2fad6-287">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="2fad6-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="2fad6-288">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2fad6-289">contoso.com/？q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="2fad6-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2fad6-290">contoso.com/a</span></span>
  - <span data-ttu-id="2fad6-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2fad6-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2fad6-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="2fad6-292">contoso.com/ab</span></span>
  - <span data-ttu-id="2fad6-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2fad6-293">contoso.com/b</span></span>
  - <span data-ttu-id="2fad6-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="2fad6-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="2fad6-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="2fad6-295">contoso.com/ba</span></span>

- <span data-ttu-id="2fad6-296">**允许不匹配和\*\*\*\*阻止不匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="2fad6-297">方案：左通配符子域和右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="2fad6-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="2fad6-298">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="2fad6-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="2fad6-299">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2fad6-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="2fad6-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="2fad6-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2fad6-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2fad6-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2fad6-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="2fad6-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="2fad6-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="2fad6-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="2fad6-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="2fad6-305">**允许不匹配和\*\*\*\*阻止不匹配**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2fad6-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="2fad6-306">方案：向左和向右波浪符</span><span class="sxs-lookup"><span data-stu-id="2fad6-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="2fad6-307">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="2fad6-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="2fad6-308">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2fad6-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-309">contoso.com</span></span>
  - <span data-ttu-id="2fad6-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2fad6-310">contoso.com/a</span></span>
  - <span data-ttu-id="2fad6-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-311">www.contoso.com</span></span>
  - <span data-ttu-id="2fad6-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2fad6-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="2fad6-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2fad6-314">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2fad6-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-315">123contoso.com</span></span>
  - <span data-ttu-id="2fad6-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="2fad6-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="2fad6-317">方案：IP 地址</span><span class="sxs-lookup"><span data-stu-id="2fad6-317">Scenario: IP address</span></span>

<span data-ttu-id="2fad6-318">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="2fad6-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="2fad6-319">**允许匹配** 和 **阻止匹配**：1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="2fad6-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="2fad6-320">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2fad6-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="2fad6-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="2fad6-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="2fad6-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="2fad6-323">具有右通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="2fad6-323">IP address with right wildcard</span></span>

<span data-ttu-id="2fad6-324">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="2fad6-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="2fad6-325">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2fad6-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="2fad6-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="2fad6-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="2fad6-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="2fad6-328">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="2fad6-328">Examples of invalid entries</span></span>

<span data-ttu-id="2fad6-329">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="2fad6-329">The following entries are invalid:</span></span>

- <span data-ttu-id="2fad6-330">**缺少或无效的域值**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="2fad6-331">contoso</span><span class="sxs-lookup"><span data-stu-id="2fad6-331">contoso</span></span>
  - <span data-ttu-id="2fad6-332">\*.contoso。\*</span><span class="sxs-lookup"><span data-stu-id="2fad6-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="2fad6-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-333">\*.com</span></span>
  - <span data-ttu-id="2fad6-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="2fad6-334">\*.pdf</span></span>

- <span data-ttu-id="2fad6-335">**文本上的通配符或不带空格字符：**</span><span class="sxs-lookup"><span data-stu-id="2fad6-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="2fad6-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-336">\*contoso.com</span></span>
  - <span data-ttu-id="2fad6-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="2fad6-337">contoso.com\*</span></span>
  - <span data-ttu-id="2fad6-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="2fad6-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="2fad6-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="2fad6-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="2fad6-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="2fad6-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="2fad6-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="2fad6-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="2fad6-342">**具有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="2fad6-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="2fad6-343">contoso.com:443</span></span>
  - <span data-ttu-id="2fad6-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="2fad6-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="2fad6-345">**非描述性通配符**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="2fad6-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="2fad6-346">\*.\*</span></span>

- <span data-ttu-id="2fad6-347">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="2fad6-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="2fad6-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-348">conto\*so.com</span></span>
  - <span data-ttu-id="2fad6-349">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="2fad6-349">conto~so.com</span></span>

- <span data-ttu-id="2fad6-350">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="2fad6-350">**Double wildcards**</span></span>

  - <span data-ttu-id="2fad6-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="2fad6-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="2fad6-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="2fad6-352">contoso.com/\*/\*</span></span>
