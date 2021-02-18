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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在安全门户的租户允许/阻止列表中配置允许和阻止。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290161"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-103">管理租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="0caeb-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0caeb-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="0caeb-104">**Applies to**</span></span>
- [<span data-ttu-id="0caeb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0caeb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0caeb-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="0caeb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0caeb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0caeb-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="0caeb-108">本文中介绍的功能在预览版中，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="0caeb-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="0caeb-109">此时， **你无法** 配置租户允许/阻止列表中的允许项目。</span><span class="sxs-lookup"><span data-stu-id="0caeb-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="0caeb-110">在具有 Exchange Online 邮箱的 Microsoft 365 组织或具有独立 Exchange Online Protection (EOP) 组织（没有 Exchange Online 邮箱）中，您可能会对 EOP 筛选裁定不一致。</span><span class="sxs-lookup"><span data-stu-id="0caeb-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="0caeb-111">例如，一条好邮件可能标记为错误 (误报) ，或者错误消息可能 (误报) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="0caeb-112">安全与合规中心中的租户允许/阻止&提供了一种手动覆盖 Microsoft 365 筛选裁定的方法。</span><span class="sxs-lookup"><span data-stu-id="0caeb-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="0caeb-113">租户允许/阻止列表在邮件流期间和用户单击时使用。</span><span class="sxs-lookup"><span data-stu-id="0caeb-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="0caeb-114">可以指定要始终阻止的 URL 或文件。</span><span class="sxs-lookup"><span data-stu-id="0caeb-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="0caeb-115">本文介绍如何在安全与合规中心或 PowerShell & (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止列表中的条目;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0caeb-116">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="0caeb-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0caeb-117">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="0caeb-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0caeb-118">若要直接转到" **租户允许/阻止列表"** 页，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="0caeb-119">使用文件的 SHA256 哈希值指定文件。</span><span class="sxs-lookup"><span data-stu-id="0caeb-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="0caeb-120">若要在 Windows 中查找文件的 SHA256 哈希值，在命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0caeb-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="0caeb-121">示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="0caeb-122">不支持感知哈希 (哈希) 哈希值。</span><span class="sxs-lookup"><span data-stu-id="0caeb-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="0caeb-123">本文稍后的"租户允许/阻止列表"一节的 [URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍了可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="0caeb-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="0caeb-124">租户允许/阻止列表最多允许 500 个 URL 条目和 500 个文件哈希条目。</span><span class="sxs-lookup"><span data-stu-id="0caeb-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="0caeb-125">条目应在 15 分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="0caeb-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="0caeb-126">默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="0caeb-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="0caeb-127">可以指定日期或将其设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="0caeb-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="0caeb-128">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0caeb-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0caeb-129">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0caeb-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0caeb-130">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="0caeb-130">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0caeb-131">若要在租户允许/阻止列表中添加和删除值，你需要是组织 **管理或\*\*\*\*安全管理员角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="0caeb-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0caeb-132">若要对租户允许/阻止列表进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="0caeb-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="0caeb-133">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0caeb-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="0caeb-134">**注意**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-134">**Notes**:</span></span>

  - <span data-ttu-id="0caeb-135">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="0caeb-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0caeb-136">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0caeb-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="0caeb-137">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="0caeb-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-138">使用安全&合规中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="0caeb-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0caeb-139">有关 URL 条目语法的详细信息，请参阅本文稍后介绍的 ["租户允许/阻止](#url-syntax-for-the-tenant-allowblock-list) 列表"一节的 URL 语法。</span><span class="sxs-lookup"><span data-stu-id="0caeb-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="0caeb-140">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0caeb-141">在 **"租户允许/阻止列表** "页上，验证是否选择了 **"URL"** 选项卡，然后单击"阻止 **"**</span><span class="sxs-lookup"><span data-stu-id="0caeb-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="0caeb-142">在 **出现的"阻止 URL"** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0caeb-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0caeb-143">**添加要阻止的 URL：** 每行输入一个 URL，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="0caeb-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0caeb-144">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0caeb-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0caeb-145">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="0caeb-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0caeb-146">或</span><span class="sxs-lookup"><span data-stu-id="0caeb-146">or</span></span>

     - <span data-ttu-id="0caeb-147">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="0caeb-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="0caeb-149">.</span><span class="sxs-lookup"><span data-stu-id="0caeb-149">.</span></span>

   - <span data-ttu-id="0caeb-150">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="0caeb-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0caeb-151">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="0caeb-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-152">使用安全&合规中心在租户允许/阻止列表中创建文件条目</span><span class="sxs-lookup"><span data-stu-id="0caeb-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0caeb-153">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0caeb-154">在 **"租户允许/阻止列表"页上**，**选择"** 文件"选项卡，然后单击"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="0caeb-155">在 **"添加文件以阻止** 出现的飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0caeb-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0caeb-156">**添加文件哈希**：每行输入一个 SHA256 哈希值，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="0caeb-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0caeb-157">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0caeb-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0caeb-158">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="0caeb-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0caeb-159">或</span><span class="sxs-lookup"><span data-stu-id="0caeb-159">or</span></span>

     - <span data-ttu-id="0caeb-160">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="0caeb-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="0caeb-162">.</span><span class="sxs-lookup"><span data-stu-id="0caeb-162">.</span></span>

   - <span data-ttu-id="0caeb-163">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="0caeb-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0caeb-164">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="0caeb-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-165">使用安全&合规中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="0caeb-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0caeb-166">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0caeb-167">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0caeb-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="0caeb-168">单击以下列标题以按升序或降序排序：</span><span class="sxs-lookup"><span data-stu-id="0caeb-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="0caeb-169">**值**：URL 或文件哈希。</span><span class="sxs-lookup"><span data-stu-id="0caeb-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="0caeb-170">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="0caeb-170">**Last updated date**</span></span>
- <span data-ttu-id="0caeb-171">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="0caeb-171">**Expiration date**</span></span>
- <span data-ttu-id="0caeb-172">**注意**</span><span class="sxs-lookup"><span data-stu-id="0caeb-172">**Note**</span></span>

<span data-ttu-id="0caeb-173">单击 **"搜索**"，输入值的一部分或全部，然后按 Enter 查找特定值。</span><span class="sxs-lookup"><span data-stu-id="0caeb-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="0caeb-174">完成后，单击"清除 **搜索清除** ![ 搜索"图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="0caeb-175">单击 **"筛选"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-175">Click **Filter**.</span></span> <span data-ttu-id="0caeb-176">在 **出现的"** 筛选器"飞出中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="0caeb-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="0caeb-177">**永不过期**： 选择关闭： ![ 关闭 ](../../media/scc-toggle-off.png) 或打开： ![ 打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="0caeb-178">**Last updated**： Select a start date (**From**) ， an end date (**To**) both.</span><span class="sxs-lookup"><span data-stu-id="0caeb-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="0caeb-179">**到期日期：** 选择开始日期 (开始日期) ，结束日期 (") "或同时选择这两者。  </span><span class="sxs-lookup"><span data-stu-id="0caeb-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="0caeb-180">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="0caeb-181">若要清除现有筛选器，请单击 **"筛选器**"，在出现的 **"** 筛选器"飞出中，单击 **"清除筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-182">使用安全&合规中心修改租户允许/阻止列表中的阻止条目</span><span class="sxs-lookup"><span data-stu-id="0caeb-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0caeb-183">不能修改条目中的现有阻止 URL 或文件值。</span><span class="sxs-lookup"><span data-stu-id="0caeb-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="0caeb-184">若要修改这些值，需要删除并重新创建条目。</span><span class="sxs-lookup"><span data-stu-id="0caeb-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="0caeb-185">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0caeb-186">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0caeb-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="0caeb-187">选择要修改的阻止条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="0caeb-188">在出现的飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0caeb-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0caeb-189">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0caeb-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0caeb-190">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="0caeb-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="0caeb-191">或</span><span class="sxs-lookup"><span data-stu-id="0caeb-191">or</span></span>

     - <span data-ttu-id="0caeb-192">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="0caeb-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="0caeb-194">.</span><span class="sxs-lookup"><span data-stu-id="0caeb-194">.</span></span>

   - <span data-ttu-id="0caeb-195">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="0caeb-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="0caeb-196">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="0caeb-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-197">使用安全&合规中心从租户允许/阻止列表中删除阻止条目</span><span class="sxs-lookup"><span data-stu-id="0caeb-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0caeb-198">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0caeb-199">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0caeb-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="0caeb-200">选择要删除的阻止条目，然后单击"删除 **"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="0caeb-201">在出现的警告对话框中，单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="0caeb-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-202">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="0caeb-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-203">使用 PowerShell 将阻止条目添加到租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="0caeb-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="0caeb-204">若要在租户允许/阻止列表中添加阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0caeb-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="0caeb-205">本示例为网站和contoso.com域添加一个阻止 URL 条目 (例如，contoso.com、www.contoso.com和xyz.abc.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="0caeb-206">因为我们不使用 ExpirationDate 或 NoExpiration 参数，所以条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="0caeb-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="0caeb-207">本示例为永不过期的指定文件添加阻止文件条目。</span><span class="sxs-lookup"><span data-stu-id="0caeb-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="0caeb-208">有关语法和参数的详细信息，请参阅[New-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0caeb-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-209">使用 PowerShell 查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="0caeb-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0caeb-210">若要查看租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0caeb-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="0caeb-211">此示例返回所有阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="0caeb-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="0caeb-212">此示例返回指定文件哈希值的信息。</span><span class="sxs-lookup"><span data-stu-id="0caeb-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="0caeb-213">有关语法和参数的详细信息，请参阅[Get-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0caeb-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-214">使用 PowerShell 修改租户允许/阻止列表中的阻止条目</span><span class="sxs-lookup"><span data-stu-id="0caeb-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0caeb-215">不能修改阻止条目中的现有 URL 或文件值。</span><span class="sxs-lookup"><span data-stu-id="0caeb-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="0caeb-216">若要修改这些值，需要删除并重新创建条目。</span><span class="sxs-lookup"><span data-stu-id="0caeb-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="0caeb-217">若要修改租户允许/阻止列表中的阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0caeb-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="0caeb-218">本示例更改指定阻止条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="0caeb-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="0caeb-219">有关语法和参数的详细信息，请参阅[Set-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0caeb-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-220">使用 PowerShell 从租户允许/阻止列表中删除阻止条目</span><span class="sxs-lookup"><span data-stu-id="0caeb-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="0caeb-221">若要从租户允许/阻止列表中删除阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0caeb-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="0caeb-222">此示例从租户允许/阻止列表中删除指定的阻止 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="0caeb-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="0caeb-223">有关语法和参数的详细信息，请参阅[Remove-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="0caeb-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="0caeb-224">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="0caeb-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="0caeb-225">允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="0caeb-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="0caeb-226">不允许使用文件名扩展名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="0caeb-227">不支持 Unicode，但 Punycode 支持。</span><span class="sxs-lookup"><span data-stu-id="0caeb-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="0caeb-228">如果以下所有语句都为 true，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="0caeb-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="0caeb-229">主机名包含一个时间段。</span><span class="sxs-lookup"><span data-stu-id="0caeb-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="0caeb-230">在时间段的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="0caeb-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="0caeb-231">此期间右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="0caeb-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="0caeb-232">例如， `t.co` 允许; `.com` `contoso.` 或不允许。</span><span class="sxs-lookup"><span data-stu-id="0caeb-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="0caeb-233">不隐含子路径。</span><span class="sxs-lookup"><span data-stu-id="0caeb-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="0caeb-234">例如， `contoso.com` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="0caeb-235">以下 (允许) \*通配符：</span><span class="sxs-lookup"><span data-stu-id="0caeb-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="0caeb-236">左通配符后跟一个时间段以指定子域。</span><span class="sxs-lookup"><span data-stu-id="0caeb-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="0caeb-237">例如， `*.contoso.com` 允许; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="0caeb-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="0caeb-238">右通配符必须遵循正斜杠 (/) 指定路径。</span><span class="sxs-lookup"><span data-stu-id="0caeb-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="0caeb-239">例如， `contoso.com/*` 允许; `contoso.com*` `contoso.com/ab*` 或不允许。</span><span class="sxs-lookup"><span data-stu-id="0caeb-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="0caeb-240">右通配符不隐含所有子路径。</span><span class="sxs-lookup"><span data-stu-id="0caeb-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="0caeb-241">例如， `contoso.com/*` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="0caeb-242">`*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="0caeb-243">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0caeb-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="0caeb-244">tilde (~) 字符在下列情况下可用：</span><span class="sxs-lookup"><span data-stu-id="0caeb-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="0caeb-245">左波浪符表示域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="0caeb-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="0caeb-246">例如， `~contoso.com` 包括 `contoso.com` `*.contoso.com` 和 。</span><span class="sxs-lookup"><span data-stu-id="0caeb-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="0caeb-247">包含协议（例如， (，或) ）的 URL 条目将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="0caeb-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="0caeb-248">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="0caeb-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="0caeb-249">引号 ("或") 无效字符。</span><span class="sxs-lookup"><span data-stu-id="0caeb-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="0caeb-250">URL 应包含所有重定向（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="0caeb-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="0caeb-251">URL 条目方案</span><span class="sxs-lookup"><span data-stu-id="0caeb-251">URL entry scenarios</span></span>

<span data-ttu-id="0caeb-252">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="0caeb-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="0caeb-253">方案：无通配符</span><span class="sxs-lookup"><span data-stu-id="0caeb-253">Scenario: No wildcards</span></span>

<span data-ttu-id="0caeb-254">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0caeb-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="0caeb-255">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="0caeb-256">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="0caeb-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-257">abc-contoso.com</span></span>
  - <span data-ttu-id="0caeb-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0caeb-258">contoso.com/a</span></span>
  - <span data-ttu-id="0caeb-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="0caeb-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="0caeb-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0caeb-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-262">www.contoso.com</span></span>
  - <span data-ttu-id="0caeb-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0caeb-264">**块匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-264">**Block match**:</span></span>

  - <span data-ttu-id="0caeb-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-265">contoso.com</span></span>
  - <span data-ttu-id="0caeb-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0caeb-266">contoso.com/a</span></span>
  - <span data-ttu-id="0caeb-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="0caeb-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="0caeb-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0caeb-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-270">www.contoso.com</span></span>
  - <span data-ttu-id="0caeb-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0caeb-272">**块不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="0caeb-273">方案：将通配符 (子域) </span><span class="sxs-lookup"><span data-stu-id="0caeb-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="0caeb-274">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0caeb-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="0caeb-275">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0caeb-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-276">www.contoso.com</span></span>
  - <span data-ttu-id="0caeb-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0caeb-278">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0caeb-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-279">123contoso.com</span></span>
  - <span data-ttu-id="0caeb-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-280">contoso.com</span></span>
  - <span data-ttu-id="0caeb-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="0caeb-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0caeb-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="0caeb-283">方案：路径顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="0caeb-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="0caeb-284">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="0caeb-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="0caeb-285">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0caeb-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="0caeb-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="0caeb-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0caeb-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0caeb-288">contoso.com/a/？q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="0caeb-289">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0caeb-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-290">contoso.com</span></span>
  - <span data-ttu-id="0caeb-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0caeb-291">contoso.com/a</span></span>
  - <span data-ttu-id="0caeb-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-292">www.contoso.com</span></span>
  - <span data-ttu-id="0caeb-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="0caeb-294">方案：左波浪符</span><span class="sxs-lookup"><span data-stu-id="0caeb-294">Scenario: Left tilde</span></span>

<span data-ttu-id="0caeb-295">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0caeb-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="0caeb-296">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0caeb-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-297">contoso.com</span></span>
  - <span data-ttu-id="0caeb-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-298">www.contoso.com</span></span>
  - <span data-ttu-id="0caeb-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0caeb-300">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0caeb-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-301">123contoso.com</span></span>
  - <span data-ttu-id="0caeb-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0caeb-302">contoso.com/abc</span></span>
  - <span data-ttu-id="0caeb-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0caeb-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="0caeb-304">方案：右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="0caeb-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="0caeb-305">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0caeb-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="0caeb-306">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0caeb-307">contoso.com/？q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="0caeb-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0caeb-308">contoso.com/a</span></span>
  - <span data-ttu-id="0caeb-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0caeb-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0caeb-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0caeb-310">contoso.com/ab</span></span>
  - <span data-ttu-id="0caeb-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0caeb-311">contoso.com/b</span></span>
  - <span data-ttu-id="0caeb-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0caeb-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0caeb-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0caeb-313">contoso.com/ba</span></span>

- <span data-ttu-id="0caeb-314">**允许不匹配和\*\*\*\*阻止不匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="0caeb-315">方案：左通配符子域和右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="0caeb-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="0caeb-316">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0caeb-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="0caeb-317">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0caeb-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0caeb-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="0caeb-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0caeb-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0caeb-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0caeb-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="0caeb-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0caeb-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0caeb-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0caeb-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="0caeb-323">**允许不匹配和\*\*\*\*阻止不匹配**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0caeb-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="0caeb-324">方案：左右波浪符</span><span class="sxs-lookup"><span data-stu-id="0caeb-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="0caeb-325">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="0caeb-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="0caeb-326">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0caeb-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-327">contoso.com</span></span>
  - <span data-ttu-id="0caeb-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0caeb-328">contoso.com/a</span></span>
  - <span data-ttu-id="0caeb-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-329">www.contoso.com</span></span>
  - <span data-ttu-id="0caeb-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0caeb-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="0caeb-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0caeb-332">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0caeb-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-333">123contoso.com</span></span>
  - <span data-ttu-id="0caeb-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="0caeb-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="0caeb-335">方案：IP 地址</span><span class="sxs-lookup"><span data-stu-id="0caeb-335">Scenario: IP address</span></span>

<span data-ttu-id="0caeb-336">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="0caeb-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="0caeb-337">**允许匹配** 和 **阻止匹配**：1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0caeb-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="0caeb-338">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0caeb-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0caeb-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="0caeb-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0caeb-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="0caeb-341">具有右通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0caeb-341">IP address with right wildcard</span></span>

<span data-ttu-id="0caeb-342">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="0caeb-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="0caeb-343">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0caeb-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="0caeb-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="0caeb-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="0caeb-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="0caeb-346">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="0caeb-346">Examples of invalid entries</span></span>

<span data-ttu-id="0caeb-347">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="0caeb-347">The following entries are invalid:</span></span>

- <span data-ttu-id="0caeb-348">**域值缺失或无效**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="0caeb-349">contoso</span><span class="sxs-lookup"><span data-stu-id="0caeb-349">contoso</span></span>
  - <span data-ttu-id="0caeb-350">\*.contoso。\*</span><span class="sxs-lookup"><span data-stu-id="0caeb-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="0caeb-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-351">\*.com</span></span>
  - <span data-ttu-id="0caeb-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="0caeb-352">\*.pdf</span></span>

- <span data-ttu-id="0caeb-353">**文本上的通配符或不带空格字符的通配符**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="0caeb-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-354">\*contoso.com</span></span>
  - <span data-ttu-id="0caeb-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="0caeb-355">contoso.com\*</span></span>
  - <span data-ttu-id="0caeb-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0caeb-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="0caeb-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="0caeb-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="0caeb-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="0caeb-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="0caeb-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="0caeb-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="0caeb-360">**具有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="0caeb-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="0caeb-361">contoso.com:443</span></span>
  - <span data-ttu-id="0caeb-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="0caeb-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="0caeb-363">**非描述性通配符**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="0caeb-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="0caeb-364">\*.\*</span></span>

- <span data-ttu-id="0caeb-365">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="0caeb-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="0caeb-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-366">conto\*so.com</span></span>
  - <span data-ttu-id="0caeb-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="0caeb-367">conto~so.com</span></span>

- <span data-ttu-id="0caeb-368">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="0caeb-368">**Double wildcards**</span></span>

  - <span data-ttu-id="0caeb-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="0caeb-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="0caeb-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="0caeb-370">contoso.com/\*/\*</span></span>
