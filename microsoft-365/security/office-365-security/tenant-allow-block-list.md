---
title: 在租户允许/阻止列表中管理允许和阻止的 Url 和文件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在安全 & 合规性中心中配置租户允许/阻止列表中的 URL 和文件条目。
ms.openlocfilehash: db34abf28b5ead8106eb0b1447052d63072b2da3
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391562"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-103">管理租户允许/阻止列表中的 URL 和文件</span><span class="sxs-lookup"><span data-stu-id="8280e-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="8280e-104">本主题中所述的功能处于预览阶段，可能会发生更改，并且在所有组织中均不可用。</span><span class="sxs-lookup"><span data-stu-id="8280e-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="8280e-105">在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online 保护（EOP）组织中具有邮箱的 Microsoft 365 组织中，您可能不同意 EOP 筛选判定。</span><span class="sxs-lookup"><span data-stu-id="8280e-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="8280e-106">例如，良好的邮件可能会被标记为 "坏" （误报），或者可能允许通过（误报）的错误消息。</span><span class="sxs-lookup"><span data-stu-id="8280e-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="8280e-107">Security & 合规性中心中的租户允许/阻止列表为你提供了一种手动替代 Microsoft 365 筛选 verdicts 的方法。</span><span class="sxs-lookup"><span data-stu-id="8280e-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="8280e-108">在邮件流期间和用户单击时使用租户允许/阻止列表。</span><span class="sxs-lookup"><span data-stu-id="8280e-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="8280e-109">可以在 "租户允许/阻止" 列表中指定要允许或阻止的 Url 和文件。</span><span class="sxs-lookup"><span data-stu-id="8280e-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="8280e-110">本主题介绍如何在 Security & 合规性中心或 PowerShell （Exchange Online PowerShell for Microsoft 365 组织中使用 Exchange Online 中的邮箱的 Exchange Online PowerShell; 独立 EOP PowerShell for 组织（无 Exchange Online 邮箱）中配置租户允许/阻止列表中的条目。</span><span class="sxs-lookup"><span data-stu-id="8280e-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8280e-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8280e-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8280e-112">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="8280e-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8280e-113">若要直接转到**租户允许/阻止列表**页，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="8280e-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="8280e-114">您可以使用文件的 SHA256 哈希值指定文件。</span><span class="sxs-lookup"><span data-stu-id="8280e-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="8280e-115">若要在 Windows 中查找文件的 SHA256 哈希值，请在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8280e-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="8280e-116">示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="8280e-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="8280e-117">不允许使用感知哈希值（pHash）值。</span><span class="sxs-lookup"><span data-stu-id="8280e-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="8280e-118">在本主题后面的[租户允许/阻止列表部分的 url 语法](#url-syntax-for-the-tenant-allowblock-list)中介绍了可用的 url 值。</span><span class="sxs-lookup"><span data-stu-id="8280e-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="8280e-119">租户允许/阻止列表允许 Url 最多为500个条目，为文件哈希提供500个条目。</span><span class="sxs-lookup"><span data-stu-id="8280e-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="8280e-120">条目应在15分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="8280e-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="8280e-121">阻止项优先于允许项。</span><span class="sxs-lookup"><span data-stu-id="8280e-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="8280e-122">默认情况下，租户允许/阻止列表中的条目将在30天后过期。</span><span class="sxs-lookup"><span data-stu-id="8280e-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="8280e-123">您可以指定一个日期或将它们设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="8280e-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="8280e-124">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8280e-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8280e-125">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8280e-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8280e-126">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="8280e-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="8280e-127">若要添加和删除租户允许/阻止列表中的值，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="8280e-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8280e-128">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="8280e-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8280e-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="8280e-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="8280e-130">若要对租户允许/阻止列表进行只读访问，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="8280e-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8280e-131">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="8280e-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8280e-132">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="8280e-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-133">使用安全 & 合规性中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="8280e-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8280e-134">有关 URL 项的语法的详细信息，请参阅本主题后面的[租户允许/阻止列表部分的 URL 语法](#url-syntax-for-the-tenant-allowblock-list)。</span><span class="sxs-lookup"><span data-stu-id="8280e-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="8280e-135">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="8280e-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8280e-136">在 "**租户允许/阻止列表**" 页上，确认已选择 " **url** " 选项卡，然后单击 "**添加**"</span><span class="sxs-lookup"><span data-stu-id="8280e-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="8280e-137">在出现的 "**添加新 url** " 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="8280e-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8280e-138">**添加带通配符的 url**：每行输入一个 URL，最多为20个。</span><span class="sxs-lookup"><span data-stu-id="8280e-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="8280e-139">**阻止/允许**：选择是否要**允许**或**阻止**指定的 url。</span><span class="sxs-lookup"><span data-stu-id="8280e-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="8280e-140">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8280e-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8280e-141">验证设置是否已关闭（ ![ 关闭 "关闭" ](../../media/scc-toggle-off.png) ），并使用 "**到期**日期" 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8280e-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="8280e-142">或</span><span class="sxs-lookup"><span data-stu-id="8280e-142">or</span></span>

     - <span data-ttu-id="8280e-143">将切换向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="8280e-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="8280e-145">.</span><span class="sxs-lookup"><span data-stu-id="8280e-145">.</span></span>

   - <span data-ttu-id="8280e-146">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="8280e-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8280e-147">完成后，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="8280e-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-148">使用安全 & 合规性中心在租户允许/阻止列表中创建文件条目</span><span class="sxs-lookup"><span data-stu-id="8280e-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8280e-149">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="8280e-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8280e-150">在 "**租户允许/阻止列表**" 页上，选择 "**文件**" 选项卡，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="8280e-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="8280e-151">在出现的 "**添加新文件**" 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="8280e-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8280e-152">**添加文件哈希**：每行输入一个 SHA256 哈希值，最多为20个。</span><span class="sxs-lookup"><span data-stu-id="8280e-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="8280e-153">**阻止/允许**：选择是否要**允许**或**阻止**指定的文件。</span><span class="sxs-lookup"><span data-stu-id="8280e-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="8280e-154">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8280e-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8280e-155">验证设置是否已关闭（ ![ 关闭 "关闭" ](../../media/scc-toggle-off.png) ），并使用 "**到期**日期" 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8280e-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="8280e-156">或</span><span class="sxs-lookup"><span data-stu-id="8280e-156">or</span></span>

     - <span data-ttu-id="8280e-157">将切换向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="8280e-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="8280e-159">.</span><span class="sxs-lookup"><span data-stu-id="8280e-159">.</span></span>

   - <span data-ttu-id="8280e-160">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="8280e-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8280e-161">完成后，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="8280e-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-162">使用安全 & 合规性中心查看租户允许/阻止列表中的 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="8280e-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8280e-163">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="8280e-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8280e-164">选择 " **url** " 选项卡或 "**文件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8280e-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="8280e-165">单击以下列标题，以按升序或降序进行排序：</span><span class="sxs-lookup"><span data-stu-id="8280e-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="8280e-166">**值**： URL 或文件哈希。</span><span class="sxs-lookup"><span data-stu-id="8280e-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="8280e-167">**操作**：**阻止**或**允许**。</span><span class="sxs-lookup"><span data-stu-id="8280e-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="8280e-168">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="8280e-168">**Last updated date**</span></span>
- <span data-ttu-id="8280e-169">**过期日期**</span><span class="sxs-lookup"><span data-stu-id="8280e-169">**Expiration date**</span></span>
- <span data-ttu-id="8280e-170">**注意**</span><span class="sxs-lookup"><span data-stu-id="8280e-170">**Note**</span></span>

<span data-ttu-id="8280e-171">单击 "**组**" 按**操作**（**阻止**或**允许**）或 "**无**" 对条目进行分组。</span><span class="sxs-lookup"><span data-stu-id="8280e-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="8280e-172">单击 "**搜索**"，输入全部或部分 URL 或文件值，然后按 enter 以查找特定值。</span><span class="sxs-lookup"><span data-stu-id="8280e-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="8280e-173">完成后，请单击 "**清除搜索**" "清除 ![ 搜索" 图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8280e-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="8280e-174">单击 "**筛选**"。</span><span class="sxs-lookup"><span data-stu-id="8280e-174">Click **Filter**.</span></span> <span data-ttu-id="8280e-175">在出现的**筛选器**浮出控件中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="8280e-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="8280e-176">**操作**：选择 "**允许**"、"**阻止**" 或两者。</span><span class="sxs-lookup"><span data-stu-id="8280e-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="8280e-177">**永不过期**：选择 "关闭 ![ " （ ](../../media/scc-toggle-off.png) "关闭"）或 "打开" （打开开启 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ）。</span><span class="sxs-lookup"><span data-stu-id="8280e-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="8280e-178">**上次更新**时间：选择开始日期（**起始**日期）、结束日期（结束日期）或同时**进行**这两者。</span><span class="sxs-lookup"><span data-stu-id="8280e-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="8280e-179">**过期日期**：选择开始日期（**起始**日期）、结束日期（结束**日期）或**同时选择这两者。</span><span class="sxs-lookup"><span data-stu-id="8280e-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="8280e-180">完成后，请单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="8280e-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="8280e-181">若要清除现有筛选器，请单击 "**筛选**"，并在出现的**筛选器**浮出控件中，单击 "**清除筛选**"</span><span class="sxs-lookup"><span data-stu-id="8280e-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-182">使用安全 & 合规性中心修改租户允许/阻止列表中的 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="8280e-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8280e-183">您不能修改 URL 或文件值本身。</span><span class="sxs-lookup"><span data-stu-id="8280e-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="8280e-184">相反，您需要删除并重新创建该条目。</span><span class="sxs-lookup"><span data-stu-id="8280e-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="8280e-185">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="8280e-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8280e-186">选择 " **url** " 选项卡或 "**文件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8280e-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="8280e-187">选择要修改的条目，然后单击 "**编辑** ![ 编辑图标" ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="8280e-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="8280e-188">在出现的浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="8280e-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8280e-189">**阻止/允许**：选择 "**允许**" 或 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="8280e-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="8280e-190">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8280e-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8280e-191">验证设置是否已关闭（ ![ 关闭 "关闭" ](../../media/scc-toggle-off.png) ），并使用 "**到期**日期" 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8280e-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="8280e-192">或</span><span class="sxs-lookup"><span data-stu-id="8280e-192">or</span></span>

     - <span data-ttu-id="8280e-193">将切换向右移动以将该项配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="8280e-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="8280e-195">.</span><span class="sxs-lookup"><span data-stu-id="8280e-195">.</span></span>

   - <span data-ttu-id="8280e-196">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="8280e-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="8280e-197">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8280e-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-198">使用安全 & 合规性中心从租户允许/阻止列表中删除 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="8280e-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8280e-199">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="8280e-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8280e-200">选择 " **url** " 选项卡或 "**文件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8280e-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="8280e-201">选择要删除的条目，然后单击 "**删除** ![ 删除图标" ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="8280e-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="8280e-202">在出现的警告对话框中，单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="8280e-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-203">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="8280e-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-204">使用 PowerShell 在租户允许/阻止列表中添加 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="8280e-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8280e-205">若要在租户允许/阻止列表中添加 URL 和文件条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8280e-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="8280e-206">此示例为 contoso.com 和所有子域添加 URL 块条目（例如，contoso.com、www.contoso.com 和 xyz.abc.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="8280e-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="8280e-207">由于我们未使用 ExpirationDate 或 NoExpiration 参数，因此该条目将在30天后过期。</span><span class="sxs-lookup"><span data-stu-id="8280e-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="8280e-208">本示例为永不过期的指定文件添加一个文件允许项。</span><span class="sxs-lookup"><span data-stu-id="8280e-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="8280e-209">有关语法和参数的详细信息，请参阅[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="8280e-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-210">使用 PowerShell 查看租户允许/阻止列表中的 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="8280e-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8280e-211">若要查看租户允许/阻止列表中的 URL 和文件条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8280e-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="8280e-212">本示例返回所有被阻止的 Url。</span><span class="sxs-lookup"><span data-stu-id="8280e-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="8280e-213">此示例返回指定文件哈希值的信息。</span><span class="sxs-lookup"><span data-stu-id="8280e-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="8280e-214">有关语法和参数的详细信息，请参阅[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="8280e-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-215">使用 PowerShell 修改租户允许/阻止列表中的 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="8280e-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8280e-216">您不能修改 URL 或文件值本身。</span><span class="sxs-lookup"><span data-stu-id="8280e-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="8280e-217">相反，您需要删除并重新创建该条目。</span><span class="sxs-lookup"><span data-stu-id="8280e-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="8280e-218">若要修改租户允许/阻止列表中的 URL 和文件条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8280e-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="8280e-219">本示例将更改指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="8280e-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="8280e-220">有关语法和参数的详细信息，请参阅[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="8280e-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-221">使用 PowerShell 从租户允许/阻止列表中删除 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="8280e-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="8280e-222">若要从租户允许/阻止列表中删除 URL 和文件条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8280e-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="8280e-223">本示例将从租户允许/阻止列表中删除指定的 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="8280e-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="8280e-224">有关语法和参数的详细信息，请参阅[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="8280e-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="8280e-225">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="8280e-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="8280e-226">允许使用 IP4v 和 IPv6 地址，但 TCP/UDP 端口不允许。</span><span class="sxs-lookup"><span data-stu-id="8280e-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="8280e-227">不允许使用文件扩展名（例如，test.pdf）。</span><span class="sxs-lookup"><span data-stu-id="8280e-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="8280e-228">Unicode 不受支持，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="8280e-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="8280e-229">如果下列所有语句都为真，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="8280e-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="8280e-230">主机名包含一个句点。</span><span class="sxs-lookup"><span data-stu-id="8280e-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="8280e-231">句点的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="8280e-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="8280e-232">句点的右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="8280e-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="8280e-233">例如， `t.co` 允许; `.com` 或 `contoso.` 不允许。</span><span class="sxs-lookup"><span data-stu-id="8280e-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="8280e-234">不暗含子路径。</span><span class="sxs-lookup"><span data-stu-id="8280e-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="8280e-235">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="8280e-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="8280e-236">在以下方案中允许使用通配符（\*）：</span><span class="sxs-lookup"><span data-stu-id="8280e-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="8280e-237">左侧通配符后面必须跟一个句点以指定一个子域。</span><span class="sxs-lookup"><span data-stu-id="8280e-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="8280e-238">例如， `*.contoso.com` 允许; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="8280e-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="8280e-239">右通配符必须紧跟在正斜杠（/）的情况下，才能指定路径。</span><span class="sxs-lookup"><span data-stu-id="8280e-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="8280e-240">例如， `contoso.com/*` 允许; `contoso.com*` 或 `contoso.com/ab*` 不允许。</span><span class="sxs-lookup"><span data-stu-id="8280e-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="8280e-241">所有子路径都不是由右侧通配符暗示的。</span><span class="sxs-lookup"><span data-stu-id="8280e-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="8280e-242">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="8280e-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="8280e-243">`*.com*`无效（不是可解析的域，并且右侧的通配符不跟正斜杠）。</span><span class="sxs-lookup"><span data-stu-id="8280e-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="8280e-244">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8280e-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="8280e-245">在以下情况下，可以使用波形符（~）：</span><span class="sxs-lookup"><span data-stu-id="8280e-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="8280e-246">左波形符表示域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="8280e-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="8280e-247">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="8280e-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="8280e-248">包含协议的 URL 项（例如、、 `http://` `https://` 、或 `ftp://` ）将失败，因为 url 条目适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="8280e-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="8280e-249">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="8280e-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="8280e-250">引号（' 或 '）是无效字符。</span><span class="sxs-lookup"><span data-stu-id="8280e-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="8280e-251">URL 应尽可能包含所有重定向。</span><span class="sxs-lookup"><span data-stu-id="8280e-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="8280e-252">URL 入口应用场景</span><span class="sxs-lookup"><span data-stu-id="8280e-252">URL entry scenarios</span></span>

<span data-ttu-id="8280e-253">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="8280e-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="8280e-254">方案：不带通配符</span><span class="sxs-lookup"><span data-stu-id="8280e-254">Scenario: No wildcards</span></span>

<span data-ttu-id="8280e-255">**条目**：`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8280e-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="8280e-256">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="8280e-257">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="8280e-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-258">abc-contoso.com</span></span>
  - <span data-ttu-id="8280e-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8280e-259">contoso.com/a</span></span>
  - <span data-ttu-id="8280e-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="8280e-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="8280e-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8280e-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-263">www.contoso.com</span></span>
  - <span data-ttu-id="8280e-264">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="8280e-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="8280e-265">**块匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-265">**Block match**:</span></span>

  - <span data-ttu-id="8280e-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-266">contoso.com</span></span>
  - <span data-ttu-id="8280e-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8280e-267">contoso.com/a</span></span>
  - <span data-ttu-id="8280e-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="8280e-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="8280e-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8280e-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-271">www.contoso.com</span></span>
  - <span data-ttu-id="8280e-272">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="8280e-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="8280e-273">**阻止不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="8280e-274">方案： Left 通配符（子域）</span><span class="sxs-lookup"><span data-stu-id="8280e-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="8280e-275">**条目**：`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8280e-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="8280e-276">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8280e-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-277">www.contoso.com</span></span>
  - <span data-ttu-id="8280e-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8280e-279">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8280e-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-280">123contoso.com</span></span>
  - <span data-ttu-id="8280e-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-281">contoso.com</span></span>
  - <span data-ttu-id="8280e-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="8280e-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8280e-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="8280e-284">方案： path 顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="8280e-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="8280e-285">**条目**：`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="8280e-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="8280e-286">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8280e-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="8280e-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="8280e-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8280e-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8280e-289">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="8280e-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="8280e-290">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8280e-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-291">contoso.com</span></span>
  - <span data-ttu-id="8280e-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8280e-292">contoso.com/a</span></span>
  - <span data-ttu-id="8280e-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-293">www.contoso.com</span></span>
  - <span data-ttu-id="8280e-294">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="8280e-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="8280e-295">方案：左波形符</span><span class="sxs-lookup"><span data-stu-id="8280e-295">Scenario: Left tilde</span></span>

<span data-ttu-id="8280e-296">**条目**：`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8280e-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="8280e-297">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8280e-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-298">contoso.com</span></span>
  - <span data-ttu-id="8280e-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-299">www.contoso.com</span></span>
  - <span data-ttu-id="8280e-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8280e-301">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8280e-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-302">123contoso.com</span></span>
  - <span data-ttu-id="8280e-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8280e-303">contoso.com/abc</span></span>
  - <span data-ttu-id="8280e-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8280e-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="8280e-305">方案：右侧通配符后缀</span><span class="sxs-lookup"><span data-stu-id="8280e-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="8280e-306">**条目**：`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8280e-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="8280e-307">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8280e-308">contoso/？ q = whatever@fabrikam</span><span class="sxs-lookup"><span data-stu-id="8280e-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="8280e-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8280e-309">contoso.com/a</span></span>
  - <span data-ttu-id="8280e-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8280e-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8280e-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8280e-311">contoso.com/ab</span></span>
  - <span data-ttu-id="8280e-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8280e-312">contoso.com/b</span></span>
  - <span data-ttu-id="8280e-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8280e-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8280e-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8280e-314">contoso.com/ba</span></span>

- <span data-ttu-id="8280e-315">**Allow 不匹配**和**阻止不匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="8280e-316">方案：左通配符子域和右侧通配符后缀</span><span class="sxs-lookup"><span data-stu-id="8280e-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="8280e-317">**条目**：`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8280e-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="8280e-318">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8280e-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8280e-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="8280e-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8280e-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8280e-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8280e-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="8280e-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8280e-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8280e-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8280e-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="8280e-324">**Allow 不匹配**和**阻止不匹配**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8280e-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="8280e-325">方案：左和右波形符</span><span class="sxs-lookup"><span data-stu-id="8280e-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="8280e-326">**条目**：`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="8280e-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="8280e-327">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8280e-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-328">contoso.com</span></span>
  - <span data-ttu-id="8280e-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8280e-329">contoso.com/a</span></span>
  - <span data-ttu-id="8280e-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-330">www.contoso.com</span></span>
  - <span data-ttu-id="8280e-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8280e-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="8280e-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8280e-333">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8280e-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-334">123contoso.com</span></span>
  - <span data-ttu-id="8280e-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="8280e-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="8280e-336">方案： IP 地址</span><span class="sxs-lookup"><span data-stu-id="8280e-336">Scenario: IP address</span></span>

<span data-ttu-id="8280e-337">**条目**：`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="8280e-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="8280e-338">**允许匹配**和**阻止匹配**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="8280e-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="8280e-339">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8280e-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8280e-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="8280e-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8280e-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="8280e-342">使用右侧通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8280e-342">IP address with right wildcard</span></span>

<span data-ttu-id="8280e-343">**条目**：`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="8280e-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="8280e-344">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="8280e-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8280e-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="8280e-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="8280e-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="8280e-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="8280e-347">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="8280e-347">Examples of invalid entries</span></span>

<span data-ttu-id="8280e-348">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="8280e-348">The following entries are invalid:</span></span>

- <span data-ttu-id="8280e-349">**缺少或无效的域值**：</span><span class="sxs-lookup"><span data-stu-id="8280e-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="8280e-350">尚未</span><span class="sxs-lookup"><span data-stu-id="8280e-350">contoso</span></span>
  - <span data-ttu-id="8280e-351">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="8280e-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="8280e-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="8280e-352">\*.com</span></span>
  - <span data-ttu-id="8280e-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="8280e-353">\*.pdf</span></span>

- <span data-ttu-id="8280e-354">**文本上的通配符或不含间距的字符**：</span><span class="sxs-lookup"><span data-stu-id="8280e-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="8280e-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="8280e-355">\*contoso.com</span></span>
  - <span data-ttu-id="8280e-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="8280e-356">contoso.com\*</span></span>
  - <span data-ttu-id="8280e-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="8280e-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="8280e-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="8280e-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="8280e-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="8280e-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="8280e-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="8280e-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="8280e-361">**带有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="8280e-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="8280e-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="8280e-362">contoso.com:443</span></span>
  - <span data-ttu-id="8280e-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="8280e-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="8280e-364">**不描述的通配符**：</span><span class="sxs-lookup"><span data-stu-id="8280e-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="8280e-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="8280e-365">\*.\*</span></span>

- <span data-ttu-id="8280e-366">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="8280e-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="8280e-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="8280e-367">conto\*so.com</span></span>
  - <span data-ttu-id="8280e-368">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="8280e-368">conto~so.com</span></span>

- <span data-ttu-id="8280e-369">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="8280e-369">**Double wildcards**</span></span>

  - <span data-ttu-id="8280e-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="8280e-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="8280e-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="8280e-371">contoso.com/\*/\*</span></span>
