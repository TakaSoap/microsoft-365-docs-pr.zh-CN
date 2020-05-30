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
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以了解如何在安全 & 合规性中心中配置租户允许/阻止列表中的 URL 和文件条目。
ms.openlocfilehash: b3a25458bbde2b3a78cfecc60ccb75fe298013f7
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419253"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="92855-103">管理租户允许/阻止列表中的 Url 和文件</span><span class="sxs-lookup"><span data-stu-id="92855-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="92855-104">本主题中所述的功能处于预览阶段，可能会发生更改，并且在所有组织中均不可用。</span><span class="sxs-lookup"><span data-stu-id="92855-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="92855-105">在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online 保护（EOP）组织中具有邮箱的 Microsoft 365 组织中，您可能不同意 EOP 筛选判定。</span><span class="sxs-lookup"><span data-stu-id="92855-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="92855-106">例如，良好的邮件可能会被标记为 "坏" （误报），或者可能允许通过（误报）的错误消息。</span><span class="sxs-lookup"><span data-stu-id="92855-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="92855-107">Security & 合规性中心中的租户允许/阻止列表为你提供了一种手动替代 Microsoft 365 筛选 verdicts 的方法。</span><span class="sxs-lookup"><span data-stu-id="92855-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="92855-108">在邮件流期间和用户单击时使用租户允许/阻止列表。</span><span class="sxs-lookup"><span data-stu-id="92855-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="92855-109">可以在 "租户允许/阻止" 列表中指定要允许或阻止的 Url 和文件。</span><span class="sxs-lookup"><span data-stu-id="92855-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="92855-110">本主题介绍如何在 Security & 合规性中心或 PowerShell （Exchange Online PowerShell for Microsoft 365 组织中使用 Exchange Online 中的邮箱的 Exchange Online PowerShell; 独立 EOP PowerShell for 组织（无 Exchange Online 邮箱）中配置租户允许/阻止列表中的条目。</span><span class="sxs-lookup"><span data-stu-id="92855-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="92855-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="92855-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="92855-112">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="92855-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="92855-113">若要直接转到**租户允许/阻止列表**页，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="92855-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="92855-114">您可以使用文件的 SHA256 哈希值指定文件。</span><span class="sxs-lookup"><span data-stu-id="92855-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="92855-115">若要在 Windows 中查找文件的 SHA256 哈希值，请在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="92855-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="92855-116">示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="92855-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="92855-117">不允许使用感知哈希值（pHash）值。</span><span class="sxs-lookup"><span data-stu-id="92855-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="92855-118">在本主题后面的[租户允许/阻止列表部分的 url 语法](#url-syntax-for-the-tenant-allowblock-list)中介绍了可用的 url 值。</span><span class="sxs-lookup"><span data-stu-id="92855-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="92855-119">租户允许/阻止列表允许 Url 最多为500个条目，为文件哈希提供500个条目。</span><span class="sxs-lookup"><span data-stu-id="92855-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="92855-120">条目应在15分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="92855-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="92855-121">阻止项优先于允许项。</span><span class="sxs-lookup"><span data-stu-id="92855-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="92855-122">默认情况下，租户允许/阻止列表中的条目将在30天后过期。</span><span class="sxs-lookup"><span data-stu-id="92855-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="92855-123">您可以指定一个日期或将它们设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="92855-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="92855-124">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="92855-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="92855-125">若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="92855-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="92855-126">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="92855-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="92855-127">若要添加和删除租户允许/阻止列表中的值，您需要是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="92855-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="92855-128">若要对租户允许/阻止列表进行只读访问，您需要是**安全读者**角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="92855-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="92855-129">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="92855-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="92855-130">使用安全 & 合规性中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="92855-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="92855-131">有关 URL 项的语法的详细信息，请参阅本主题后面的[租户允许/阻止列表部分的 URL 语法](#url-syntax-for-the-tenant-allowblock-list)。</span><span class="sxs-lookup"><span data-stu-id="92855-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="92855-132">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="92855-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="92855-133">在 "**租户允许/阻止列表**" 页上，确认已选择 " **url** " 选项卡，然后单击 "**添加**"</span><span class="sxs-lookup"><span data-stu-id="92855-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="92855-134">在出现的 "**添加新 url** " 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="92855-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="92855-135">**添加带通配符的 url**：每行输入一个 URL，最多为20个。</span><span class="sxs-lookup"><span data-stu-id="92855-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="92855-136">**阻止/允许**：选择是否要**允许**或**阻止**指定的 url。</span><span class="sxs-lookup"><span data-stu-id="92855-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="92855-137">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="92855-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="92855-138">验证设置是否已关闭（ ![ 关闭 "关闭" ](../../media/scc-toggle-off.png) ），并使用 "**到期**日期" 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="92855-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="92855-139">或</span><span class="sxs-lookup"><span data-stu-id="92855-139">or</span></span>

     - <span data-ttu-id="92855-140">将切换向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="92855-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="92855-142">.</span><span class="sxs-lookup"><span data-stu-id="92855-142">.</span></span>

   - <span data-ttu-id="92855-143">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="92855-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="92855-144">完成后，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="92855-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="92855-145">使用安全 & 合规性中心在租户允许/阻止列表中创建文件条目</span><span class="sxs-lookup"><span data-stu-id="92855-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="92855-146">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="92855-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="92855-147">在 "**租户允许/阻止列表**" 页上，选择 "**文件**" 选项卡，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="92855-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="92855-148">在出现的 "**添加新文件**" 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="92855-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="92855-149">**添加文件哈希**：每行输入一个 SHA256 哈希值，最多为20个。</span><span class="sxs-lookup"><span data-stu-id="92855-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="92855-150">**阻止/允许**：选择是否要**允许**或**阻止**指定的文件。</span><span class="sxs-lookup"><span data-stu-id="92855-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="92855-151">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="92855-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="92855-152">验证设置是否已关闭（ ![ 关闭 "关闭" ](../../media/scc-toggle-off.png) ），并使用 "**到期**日期" 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="92855-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="92855-153">或</span><span class="sxs-lookup"><span data-stu-id="92855-153">or</span></span>

     - <span data-ttu-id="92855-154">将切换向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="92855-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="92855-156">.</span><span class="sxs-lookup"><span data-stu-id="92855-156">.</span></span>

   - <span data-ttu-id="92855-157">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="92855-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="92855-158">完成后，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="92855-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="92855-159">使用安全 & 合规性中心查看租户允许/阻止列表中的 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="92855-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="92855-160">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="92855-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="92855-161">选择 " **url** " 选项卡或 "**文件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="92855-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="92855-162">单击以下列标题，以按升序或降序进行排序：</span><span class="sxs-lookup"><span data-stu-id="92855-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="92855-163">**值**： URL 或文件哈希。</span><span class="sxs-lookup"><span data-stu-id="92855-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="92855-164">**操作**：**阻止**或**允许**。</span><span class="sxs-lookup"><span data-stu-id="92855-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="92855-165">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="92855-165">**Last updated date**</span></span>
- <span data-ttu-id="92855-166">**过期日期**</span><span class="sxs-lookup"><span data-stu-id="92855-166">**Expiration date**</span></span>
- <span data-ttu-id="92855-167">**注意**</span><span class="sxs-lookup"><span data-stu-id="92855-167">**Note**</span></span>

<span data-ttu-id="92855-168">单击 "**组**" 按**操作**（**阻止**或**允许**）或 "**无**" 对条目进行分组。</span><span class="sxs-lookup"><span data-stu-id="92855-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="92855-169">单击 "**搜索**"，输入全部或部分 URL 或文件值，然后按 enter 以查找特定值。</span><span class="sxs-lookup"><span data-stu-id="92855-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="92855-170">完成后，请单击 "**清除搜索**" "清除 ![ 搜索" 图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="92855-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="92855-171">单击 "**筛选**"。</span><span class="sxs-lookup"><span data-stu-id="92855-171">Click **Filter**.</span></span> <span data-ttu-id="92855-172">在出现的**筛选器**浮出控件中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="92855-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="92855-173">**操作**：选择 "**允许**"、"**阻止**" 或两者。</span><span class="sxs-lookup"><span data-stu-id="92855-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="92855-174">**永不过期**：选择 "关闭 ![ " （ ](../../media/scc-toggle-off.png) "关闭"）或 "打开" （打开开启 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ）。</span><span class="sxs-lookup"><span data-stu-id="92855-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="92855-175">**上次更新**时间：选择开始日期（**起始**日期）、结束日期（结束日期）或同时**进行**这两者。</span><span class="sxs-lookup"><span data-stu-id="92855-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="92855-176">**过期日期**：选择开始日期（**起始**日期）、结束日期（结束**日期）或**同时选择这两者。</span><span class="sxs-lookup"><span data-stu-id="92855-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="92855-177">完成后，请单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="92855-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="92855-178">若要清除现有筛选器，请单击 "**筛选**"，并在出现的**筛选器**浮出控件中，单击 "**清除筛选**"</span><span class="sxs-lookup"><span data-stu-id="92855-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="92855-179">使用安全 & 合规性中心修改租户允许/阻止列表中的 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="92855-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="92855-180">您不能修改 URL 或文件值本身。</span><span class="sxs-lookup"><span data-stu-id="92855-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="92855-181">相反，您需要删除并重新创建该条目。</span><span class="sxs-lookup"><span data-stu-id="92855-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="92855-182">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="92855-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="92855-183">选择 " **url** " 选项卡或 "**文件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="92855-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="92855-184">选择要修改的条目，然后单击 "**编辑** ![ 编辑图标" ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="92855-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="92855-185">在出现的浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="92855-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="92855-186">**阻止/允许**：选择 "**允许**" 或 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="92855-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="92855-187">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="92855-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="92855-188">验证设置是否已关闭（ ![ 关闭 "关闭" ](../../media/scc-toggle-off.png) ），并使用 "**到期**日期" 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="92855-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="92855-189">或</span><span class="sxs-lookup"><span data-stu-id="92855-189">or</span></span>

     - <span data-ttu-id="92855-190">将切换向右移动以将该项配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="92855-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="92855-192">.</span><span class="sxs-lookup"><span data-stu-id="92855-192">.</span></span>

   - <span data-ttu-id="92855-193">**可选注释**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="92855-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="92855-194">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="92855-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="92855-195">使用安全 & 合规性中心从租户允许/阻止列表中删除 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="92855-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="92855-196">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **租户允许/阻止" 列表**。</span><span class="sxs-lookup"><span data-stu-id="92855-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="92855-197">选择 " **url** " 选项卡或 "**文件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="92855-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="92855-198">选择要删除的条目，然后单击 "**删除** ![ 删除图标" ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="92855-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="92855-199">在出现的警告对话框中，单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="92855-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="92855-200">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="92855-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="92855-201">使用 PowerShell 在租户允许/阻止列表中添加 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="92855-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="92855-202">若要在租户允许/阻止列表中添加 URL 和文件条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="92855-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="92855-203">此示例为 contoso.com 和所有子域添加 URL 块条目（例如，contoso.com、www.contoso.com 和 xyz.abc.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="92855-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="92855-204">由于我们未使用 ExpirationDate 或 NoExpiration 参数，因此该条目将在30天后过期。</span><span class="sxs-lookup"><span data-stu-id="92855-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="92855-205">本示例为永不过期的指定文件添加一个文件允许项。</span><span class="sxs-lookup"><span data-stu-id="92855-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="92855-206">有关语法和参数的详细信息，请参阅[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="92855-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="92855-207">使用 PowerShell 查看租户允许/阻止列表中的 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="92855-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="92855-208">若要查看租户允许/阻止列表中的 URL 和文件条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="92855-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="92855-209">本示例返回所有被阻止的 Url。</span><span class="sxs-lookup"><span data-stu-id="92855-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="92855-210">此示例返回指定文件哈希值的信息。</span><span class="sxs-lookup"><span data-stu-id="92855-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="92855-211">有关语法和参数的详细信息，请参阅[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="92855-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="92855-212">使用 PowerShell 修改租户允许/阻止列表中的 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="92855-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="92855-213">您不能修改 URL 或文件值本身。</span><span class="sxs-lookup"><span data-stu-id="92855-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="92855-214">相反，您需要删除并重新创建该条目。</span><span class="sxs-lookup"><span data-stu-id="92855-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="92855-215">若要修改租户允许/阻止列表中的 URL 和文件条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="92855-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="92855-216">本示例将更改指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="92855-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="92855-217">有关语法和参数的详细信息，请参阅[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="92855-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="92855-218">使用 PowerShell 从租户允许/阻止列表中删除 URL 和文件条目</span><span class="sxs-lookup"><span data-stu-id="92855-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="92855-219">若要从租户允许/阻止列表中删除 URL 和文件条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="92855-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="92855-220">本示例将从租户允许/阻止列表中删除指定的 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="92855-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="92855-221">有关语法和参数的详细信息，请参阅[TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="92855-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="92855-222">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="92855-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="92855-223">允许使用 IP4v 和 IPv6 地址，但 TCP/UDP 端口不允许。</span><span class="sxs-lookup"><span data-stu-id="92855-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="92855-224">不允许使用文件扩展名（例如，"test"）。</span><span class="sxs-lookup"><span data-stu-id="92855-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="92855-225">Unicode 不受支持，但 Punycode 是。</span><span class="sxs-lookup"><span data-stu-id="92855-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="92855-226">如果下列所有语句都为真，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="92855-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="92855-227">主机名包含一个句点。</span><span class="sxs-lookup"><span data-stu-id="92855-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="92855-228">句点的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="92855-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="92855-229">句点的右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="92855-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="92855-230">例如， `t.co` 允许; `.com` 或 `contoso.` 不允许。</span><span class="sxs-lookup"><span data-stu-id="92855-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="92855-231">不暗含子路径。</span><span class="sxs-lookup"><span data-stu-id="92855-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="92855-232">例如，不 `contoso.com` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="92855-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="92855-233">在以下方案中允许使用通配符（\*）：</span><span class="sxs-lookup"><span data-stu-id="92855-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="92855-234">左侧通配符后面必须跟一个句点以指定一个子域。</span><span class="sxs-lookup"><span data-stu-id="92855-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="92855-235">例如， `*.contoso.com` 允许; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="92855-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="92855-236">右通配符必须紧跟在正斜杠（/）的情况下，才能指定路径。</span><span class="sxs-lookup"><span data-stu-id="92855-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="92855-237">例如， `contoso.com/*` 允许; `contoso.com*` 或 `contoso.com/ab*` 不允许。</span><span class="sxs-lookup"><span data-stu-id="92855-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="92855-238">所有子路径都不是由右侧通配符暗示的。</span><span class="sxs-lookup"><span data-stu-id="92855-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="92855-239">例如，不 `contoso.com/*` 包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="92855-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="92855-240">`*.com*`无效（不是可解析的域，并且右侧的通配符不跟正斜杠）。</span><span class="sxs-lookup"><span data-stu-id="92855-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="92855-241">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="92855-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="92855-242">在以下情况下，可以使用波形符（~）：</span><span class="sxs-lookup"><span data-stu-id="92855-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="92855-243">左波形符表示域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="92855-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="92855-244">例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="92855-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="92855-245">包含协议的 URL 项（例如、、 `http://` `https://` 、或 `ftp://` ）将失败，因为 url 条目适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="92855-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="92855-246">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="92855-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="92855-247">引号（' 或 '）是无效字符。</span><span class="sxs-lookup"><span data-stu-id="92855-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="92855-248">URL 应尽可能包含所有重定向。</span><span class="sxs-lookup"><span data-stu-id="92855-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="92855-249">URL 入口应用场景</span><span class="sxs-lookup"><span data-stu-id="92855-249">URL entry scenarios</span></span>

<span data-ttu-id="92855-250">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="92855-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="92855-251">方案：不带通配符</span><span class="sxs-lookup"><span data-stu-id="92855-251">Scenario: No wildcards</span></span>

<span data-ttu-id="92855-252">**条目**：`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="92855-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="92855-253">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="92855-254">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="92855-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-255">abc-contoso.com</span></span>
  - <span data-ttu-id="92855-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="92855-256">contoso.com/a</span></span>
  - <span data-ttu-id="92855-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="92855-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="92855-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="92855-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-260">www.contoso.com</span></span>
  - <span data-ttu-id="92855-261">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="92855-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="92855-262">**块匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-262">**Block match**:</span></span>

  - <span data-ttu-id="92855-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-263">contoso.com</span></span>
  - <span data-ttu-id="92855-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="92855-264">contoso.com/a</span></span>
  - <span data-ttu-id="92855-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="92855-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="92855-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="92855-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-268">www.contoso.com</span></span>
  - <span data-ttu-id="92855-269">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="92855-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="92855-270">**阻止不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="92855-271">方案： Left 通配符（子域）</span><span class="sxs-lookup"><span data-stu-id="92855-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="92855-272">**条目**：`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="92855-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="92855-273">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="92855-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-274">www.contoso.com</span></span>
  - <span data-ttu-id="92855-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="92855-276">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="92855-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-277">123contoso.com</span></span>
  - <span data-ttu-id="92855-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-278">contoso.com</span></span>
  - <span data-ttu-id="92855-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="92855-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="92855-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="92855-281">方案： path 顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="92855-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="92855-282">**条目**：`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="92855-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="92855-283">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="92855-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="92855-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="92855-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="92855-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="92855-286">contoso/a/？ q = joe@t .com</span><span class="sxs-lookup"><span data-stu-id="92855-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="92855-287">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="92855-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-288">contoso.com</span></span>
  - <span data-ttu-id="92855-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="92855-289">contoso.com/a</span></span>
  - <span data-ttu-id="92855-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-290">www.contoso.com</span></span>
  - <span data-ttu-id="92855-291">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="92855-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="92855-292">方案：左波形符</span><span class="sxs-lookup"><span data-stu-id="92855-292">Scenario: Left tilde</span></span>

<span data-ttu-id="92855-293">**条目**：`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="92855-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="92855-294">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="92855-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-295">contoso.com</span></span>
  - <span data-ttu-id="92855-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-296">www.contoso.com</span></span>
  - <span data-ttu-id="92855-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="92855-298">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="92855-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-299">123contoso.com</span></span>
  - <span data-ttu-id="92855-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="92855-300">contoso.com/abc</span></span>
  - <span data-ttu-id="92855-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="92855-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="92855-302">方案：右侧通配符后缀</span><span class="sxs-lookup"><span data-stu-id="92855-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="92855-303">**条目**：`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="92855-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="92855-304">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="92855-305">contoso/？ q = whatever@fabrikam</span><span class="sxs-lookup"><span data-stu-id="92855-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="92855-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="92855-306">contoso.com/a</span></span>
  - <span data-ttu-id="92855-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="92855-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="92855-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="92855-308">contoso.com/ab</span></span>
  - <span data-ttu-id="92855-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="92855-309">contoso.com/b</span></span>
  - <span data-ttu-id="92855-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="92855-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="92855-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="92855-311">contoso.com/ba</span></span>

- <span data-ttu-id="92855-312">**Allow 不匹配**和**阻止不匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="92855-313">方案：左通配符子域和右侧通配符后缀</span><span class="sxs-lookup"><span data-stu-id="92855-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="92855-314">**条目**：`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="92855-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="92855-315">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="92855-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="92855-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="92855-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="92855-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="92855-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="92855-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="92855-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="92855-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="92855-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="92855-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="92855-321">**Allow 不匹配**和**阻止不匹配**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="92855-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="92855-322">方案：左和右波形符</span><span class="sxs-lookup"><span data-stu-id="92855-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="92855-323">**条目**：`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="92855-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="92855-324">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="92855-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-325">contoso.com</span></span>
  - <span data-ttu-id="92855-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="92855-326">contoso.com/a</span></span>
  - <span data-ttu-id="92855-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-327">www.contoso.com</span></span>
  - <span data-ttu-id="92855-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="92855-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="92855-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="92855-330">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="92855-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-331">123contoso.com</span></span>
  - <span data-ttu-id="92855-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="92855-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="92855-333">方案： IP 地址</span><span class="sxs-lookup"><span data-stu-id="92855-333">Scenario: IP address</span></span>

<span data-ttu-id="92855-334">**条目**：`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="92855-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="92855-335">**允许匹配**和**阻止匹配**：1.2.3。4</span><span class="sxs-lookup"><span data-stu-id="92855-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="92855-336">**允许不匹配**和**阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="92855-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="92855-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="92855-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="92855-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="92855-339">使用右侧通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="92855-339">IP address with right wildcard</span></span>

<span data-ttu-id="92855-340">**条目**：`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="92855-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="92855-341">**允许匹配**和**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="92855-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="92855-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="92855-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="92855-343">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="92855-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="92855-344">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="92855-344">Examples of invalid entries</span></span>

<span data-ttu-id="92855-345">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="92855-345">The following entries are invalid:</span></span>

- <span data-ttu-id="92855-346">**缺少或无效的域值**：</span><span class="sxs-lookup"><span data-stu-id="92855-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="92855-347">尚未</span><span class="sxs-lookup"><span data-stu-id="92855-347">contoso</span></span>
  - <span data-ttu-id="92855-348">\*尚未.\*</span><span class="sxs-lookup"><span data-stu-id="92855-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="92855-349">\*.com</span><span class="sxs-lookup"><span data-stu-id="92855-349">\*.com</span></span>
  - <span data-ttu-id="92855-350">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="92855-350">\*.pdf</span></span>

- <span data-ttu-id="92855-351">**文本上的通配符或不含间距的字符**：</span><span class="sxs-lookup"><span data-stu-id="92855-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="92855-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="92855-352">\*contoso.com</span></span>
  - <span data-ttu-id="92855-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="92855-353">contoso.com\*</span></span>
  - <span data-ttu-id="92855-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="92855-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="92855-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="92855-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="92855-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="92855-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="92855-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="92855-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="92855-358">**带有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="92855-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="92855-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="92855-359">contoso.com:443</span></span>
  - <span data-ttu-id="92855-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="92855-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="92855-361">**不描述的通配符**：</span><span class="sxs-lookup"><span data-stu-id="92855-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="92855-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="92855-362">\*.\*</span></span>

- <span data-ttu-id="92855-363">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="92855-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="92855-364">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="92855-364">conto\*so.com</span></span>
  - <span data-ttu-id="92855-365">conto ~ .com</span><span class="sxs-lookup"><span data-stu-id="92855-365">conto~so.com</span></span>

- <span data-ttu-id="92855-366">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="92855-366">**Double wildcards**</span></span>

  - <span data-ttu-id="92855-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="92855-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="92855-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="92855-368">contoso.com/\*/\*</span></span>
