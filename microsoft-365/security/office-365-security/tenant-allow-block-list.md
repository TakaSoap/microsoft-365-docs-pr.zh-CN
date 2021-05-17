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
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587583"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-103">管理租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="6586d-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6586d-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="6586d-104">**Applies to**</span></span>
- [<span data-ttu-id="6586d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6586d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6586d-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="6586d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6586d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6586d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="6586d-108">目前，你 **无法** 配置租户允许/阻止列表中的允许项。</span><span class="sxs-lookup"><span data-stu-id="6586d-108">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="6586d-109">在Microsoft 365没有邮箱的 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，您可能会与 EOP 筛选裁定不一致。</span><span class="sxs-lookup"><span data-stu-id="6586d-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="6586d-110">例如，一条好邮件可能标记为 (误报) ，或者可能允许错误消息通过 (漏报) 。</span><span class="sxs-lookup"><span data-stu-id="6586d-110">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="6586d-111">安全与合规中心中的租户&/阻止列表提供了一种手动覆盖Microsoft 365裁定的方法。</span><span class="sxs-lookup"><span data-stu-id="6586d-111">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="6586d-112">租户允许/阻止列表在邮件流期间和用户单击时使用。</span><span class="sxs-lookup"><span data-stu-id="6586d-112">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="6586d-113">您可以指定要始终阻止的 URL 或文件。</span><span class="sxs-lookup"><span data-stu-id="6586d-113">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="6586d-114">本文介绍如何在安全& 合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="6586d-114">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6586d-115">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="6586d-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6586d-116">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="6586d-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6586d-117">若要直接转到租户 **允许/阻止列表** 页面，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="6586d-117">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="6586d-118">使用文件的 SHA256 哈希值指定文件。</span><span class="sxs-lookup"><span data-stu-id="6586d-118">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="6586d-119">若要在命令提示符中查找文件的 SHA256 哈希Windows，在命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6586d-119">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="6586d-120">示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="6586d-120">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="6586d-121">不支持感知哈希 (pHash) 值。</span><span class="sxs-lookup"><span data-stu-id="6586d-121">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="6586d-122">本文稍后的租户允许/阻止列表一节的 [URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍了可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="6586d-122">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="6586d-123">租户允许/阻止列表允许最多 500 个 URL 条目和 500 个文件哈希条目。</span><span class="sxs-lookup"><span data-stu-id="6586d-123">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="6586d-124">每个条目的最大字符数为：</span><span class="sxs-lookup"><span data-stu-id="6586d-124">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="6586d-125">文件哈希 = 64</span><span class="sxs-lookup"><span data-stu-id="6586d-125">File hashes = 64</span></span>
  - <span data-ttu-id="6586d-126">URL = 250</span><span class="sxs-lookup"><span data-stu-id="6586d-126">URL = 250</span></span>

- <span data-ttu-id="6586d-127">条目应在 30 分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="6586d-127">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="6586d-128">默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="6586d-128">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="6586d-129">可以指定日期或将其设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="6586d-129">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="6586d-130">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6586d-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6586d-131">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6586d-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6586d-132">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="6586d-132">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6586d-133">若要在租户允许/阻止列表中添加和删除值，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="6586d-133">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="6586d-134">若要对租户允许/阻止列表进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。</span><span class="sxs-lookup"><span data-stu-id="6586d-134">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6586d-135">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="6586d-135">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="6586d-136">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="6586d-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6586d-137">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="6586d-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="6586d-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="6586d-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-139">使用安全&中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="6586d-139">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="6586d-140">有关 URL 条目的语法的详细信息，请参阅本文稍后介绍的租户 [允许/阻止列表的 URL](#url-syntax-for-the-tenant-allowblock-list) 语法部分。</span><span class="sxs-lookup"><span data-stu-id="6586d-140">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="6586d-141">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="6586d-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="6586d-142">在" **租户允许/阻止列表** "页上，验证 **"URL"** 选项卡是否被选中，然后单击"阻止 **"**</span><span class="sxs-lookup"><span data-stu-id="6586d-142">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="6586d-143">在 **出现的"阻止 URL"** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6586d-143">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6586d-144">**添加要阻止的 URL：** 每行输入一个 URL，最多输入 20 个。</span><span class="sxs-lookup"><span data-stu-id="6586d-144">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="6586d-145">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="6586d-145">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="6586d-146">验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="6586d-146">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="6586d-147">或</span><span class="sxs-lookup"><span data-stu-id="6586d-147">or</span></span>

     - <span data-ttu-id="6586d-148">将开关移到右侧，将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="6586d-148">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="6586d-150">.</span><span class="sxs-lookup"><span data-stu-id="6586d-150">.</span></span>

   - <span data-ttu-id="6586d-151">**可选说明**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="6586d-151">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="6586d-152">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6586d-152">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-153">使用安全&中心在租户允许/阻止列表中创建文件条目</span><span class="sxs-lookup"><span data-stu-id="6586d-153">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="6586d-154">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="6586d-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="6586d-155">在"**租户允许/阻止列表"页上**，选择"**文件"** 选项卡，然后单击"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="6586d-155">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="6586d-156">在 **"添加文件以阻止** 出现的飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6586d-156">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6586d-157">**添加文件哈希**：每行输入一个 SHA256 哈希值，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="6586d-157">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="6586d-158">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="6586d-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="6586d-159">验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="6586d-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="6586d-160">或</span><span class="sxs-lookup"><span data-stu-id="6586d-160">or</span></span>

     - <span data-ttu-id="6586d-161">将开关移到右侧，将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="6586d-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="6586d-163">.</span><span class="sxs-lookup"><span data-stu-id="6586d-163">.</span></span>

   - <span data-ttu-id="6586d-164">**可选说明**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="6586d-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="6586d-165">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6586d-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-166">使用安全&中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="6586d-166">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="6586d-167">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="6586d-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="6586d-168">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6586d-168">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="6586d-169">单击以下列标题以按升序或降序排序：</span><span class="sxs-lookup"><span data-stu-id="6586d-169">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="6586d-170">**值**：URL 或文件哈希。</span><span class="sxs-lookup"><span data-stu-id="6586d-170">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="6586d-171">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="6586d-171">**Last updated date**</span></span>
- <span data-ttu-id="6586d-172">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="6586d-172">**Expiration date**</span></span>
- <span data-ttu-id="6586d-173">**注意**</span><span class="sxs-lookup"><span data-stu-id="6586d-173">**Note**</span></span>

<span data-ttu-id="6586d-174">单击 **"搜索**"，输入值的全部或一部分，然后按 Enter 查找特定值。</span><span class="sxs-lookup"><span data-stu-id="6586d-174">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="6586d-175">完成后，单击"清除搜索 **""** ![ 清除搜索图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) "。</span><span class="sxs-lookup"><span data-stu-id="6586d-175">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="6586d-176">单击"**筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="6586d-176">Click **Filter**.</span></span> <span data-ttu-id="6586d-177">在出现的 **"** 筛选器"飞出中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="6586d-177">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="6586d-178">**永不过期**：选择关闭： ![ 关闭 ](../../media/scc-toggle-off.png) 或打开： ![ 打开切换 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="6586d-178">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="6586d-179">**Last updated**： Select a start date (**From**) ， an end date (**To**) both.</span><span class="sxs-lookup"><span data-stu-id="6586d-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="6586d-180">**到期日期：** 选择开始日期 (**From**) ，结束日期 (**到**) 两者。</span><span class="sxs-lookup"><span data-stu-id="6586d-180">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="6586d-181">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="6586d-181">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="6586d-182">若要清除现有筛选器，请单击 **"筛选器"，** 在出现的"筛选器"飞出中，单击"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="6586d-182">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-183">使用安全&中心修改租户允许/阻止列表中的阻止条目</span><span class="sxs-lookup"><span data-stu-id="6586d-183">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="6586d-184">不能修改条目中的现有阻止 URL 或文件值。</span><span class="sxs-lookup"><span data-stu-id="6586d-184">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="6586d-185">若要修改这些值，需要删除并重新创建条目。</span><span class="sxs-lookup"><span data-stu-id="6586d-185">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="6586d-186">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="6586d-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="6586d-187">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6586d-187">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="6586d-188">选择要修改的阻止条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="6586d-188">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="6586d-189">在出现的"飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6586d-189">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6586d-190">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="6586d-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="6586d-191">验证是否关闭该设置 (关闭) 并使用"过期 ![ ](../../media/scc-toggle-off.png) **时间"** 框指定条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="6586d-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="6586d-192">或</span><span class="sxs-lookup"><span data-stu-id="6586d-192">or</span></span>

     - <span data-ttu-id="6586d-193">将开关移到右侧，将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="6586d-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="6586d-195">.</span><span class="sxs-lookup"><span data-stu-id="6586d-195">.</span></span>

   - <span data-ttu-id="6586d-196">**可选说明**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="6586d-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="6586d-197">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6586d-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-198">使用安全&中心从租户允许/阻止列表中删除阻止条目</span><span class="sxs-lookup"><span data-stu-id="6586d-198">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="6586d-199">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="6586d-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="6586d-200">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6586d-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="6586d-201">选择要删除的阻止条目，然后单击"删除 **删除"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="6586d-201">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="6586d-202">在出现的警告对话框中，单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="6586d-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-203">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="6586d-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-204">使用 PowerShell 将阻止条目添加到租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="6586d-204">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="6586d-205">若要在租户允许/阻止列表中添加阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6586d-205">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="6586d-206">此示例为 contoso.com 及其所有子域（例如， (、contoso.com、www.contoso.com 和 xyz.abc.contoso.com) ）添加一个阻止 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="6586d-206">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="6586d-207">由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="6586d-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="6586d-208">本示例为永不过期的指定文件添加阻止文件条目。</span><span class="sxs-lookup"><span data-stu-id="6586d-208">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="6586d-209">有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="6586d-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-210">使用 PowerShell 查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="6586d-210">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="6586d-211">若要查看租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6586d-211">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="6586d-212">此示例返回所有阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="6586d-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="6586d-213">此示例返回指定文件哈希值的信息。</span><span class="sxs-lookup"><span data-stu-id="6586d-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="6586d-214">有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="6586d-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-215">使用 PowerShell 修改租户允许/阻止列表中的阻止条目</span><span class="sxs-lookup"><span data-stu-id="6586d-215">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="6586d-216">不能修改阻止条目中的现有 URL 或文件值。</span><span class="sxs-lookup"><span data-stu-id="6586d-216">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="6586d-217">若要修改这些值，需要删除并重新创建条目。</span><span class="sxs-lookup"><span data-stu-id="6586d-217">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="6586d-218">若要修改租户允许/阻止列表中的阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6586d-218">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="6586d-219">本示例更改指定阻止条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="6586d-219">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="6586d-220">有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="6586d-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-221">使用 PowerShell 从租户允许/阻止列表中删除阻止条目</span><span class="sxs-lookup"><span data-stu-id="6586d-221">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="6586d-222">若要从租户允许/阻止列表中删除阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6586d-222">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="6586d-223">此示例从租户允许/阻止列表中删除指定的阻止 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="6586d-223">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="6586d-224">有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="6586d-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="6586d-225">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="6586d-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="6586d-226">允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="6586d-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="6586d-227">例如，不允许使用文件名 (，例如test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="6586d-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="6586d-228">不支持 Unicode，但 Punycode 支持。</span><span class="sxs-lookup"><span data-stu-id="6586d-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="6586d-229">如果下列所有语句都为 true，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="6586d-229">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="6586d-230">主机名包含一个时间段。</span><span class="sxs-lookup"><span data-stu-id="6586d-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="6586d-231">在周期的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="6586d-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="6586d-232">此期间右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="6586d-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="6586d-233">例如， `t.co` 是允许的 `.com` ; `contoso.` 或者是不允许的。</span><span class="sxs-lookup"><span data-stu-id="6586d-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="6586d-234">不隐含子路径。</span><span class="sxs-lookup"><span data-stu-id="6586d-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="6586d-235">例如， `contoso.com` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="6586d-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="6586d-236">在 () 允许使用通配符或\*通配符：</span><span class="sxs-lookup"><span data-stu-id="6586d-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="6586d-237">左通配符后面必须后跟一个时间段，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="6586d-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="6586d-238">例如， `*.contoso.com` 允许 ; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="6586d-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="6586d-239">右通配符必须按照正斜杠 (/) 指定路径。</span><span class="sxs-lookup"><span data-stu-id="6586d-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="6586d-240">例如， `contoso.com/*` 是允许的 `contoso.com*` ; `contoso.com/ab*` 或者是不允许的。</span><span class="sxs-lookup"><span data-stu-id="6586d-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="6586d-241">右通配符不隐含所有子路径。</span><span class="sxs-lookup"><span data-stu-id="6586d-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="6586d-242">例如， `contoso.com/*` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="6586d-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="6586d-243">`*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。</span><span class="sxs-lookup"><span data-stu-id="6586d-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="6586d-244">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="6586d-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="6586d-245">在下列 (提供了) ~ 字符：</span><span class="sxs-lookup"><span data-stu-id="6586d-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="6586d-246">左波浪符表示域及其所有子域。</span><span class="sxs-lookup"><span data-stu-id="6586d-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="6586d-247">例如， `~contoso.com` 包括 `contoso.com` `*.contoso.com` 和 。</span><span class="sxs-lookup"><span data-stu-id="6586d-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="6586d-248">包含协议（如 、 (）的 URL) 将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="6586d-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="6586d-249">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="6586d-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="6586d-250">引号 ("或") 无效字符。</span><span class="sxs-lookup"><span data-stu-id="6586d-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="6586d-251">如果可能，URL 应包含所有重定向。</span><span class="sxs-lookup"><span data-stu-id="6586d-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="6586d-252">URL 条目方案</span><span class="sxs-lookup"><span data-stu-id="6586d-252">URL entry scenarios</span></span>

<span data-ttu-id="6586d-253">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="6586d-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="6586d-254">方案：无通配符</span><span class="sxs-lookup"><span data-stu-id="6586d-254">Scenario: No wildcards</span></span>

<span data-ttu-id="6586d-255">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="6586d-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="6586d-256">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="6586d-257">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="6586d-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-258">abc-contoso.com</span></span>
  - <span data-ttu-id="6586d-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="6586d-259">contoso.com/a</span></span>
  - <span data-ttu-id="6586d-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="6586d-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="6586d-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="6586d-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-263">www.contoso.com</span></span>
  - <span data-ttu-id="6586d-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-264">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="6586d-265">**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-265">**Block match**:</span></span>

  - <span data-ttu-id="6586d-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-266">contoso.com</span></span>
  - <span data-ttu-id="6586d-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="6586d-267">contoso.com/a</span></span>
  - <span data-ttu-id="6586d-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="6586d-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="6586d-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="6586d-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-271">www.contoso.com</span></span>
  - <span data-ttu-id="6586d-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="6586d-273">**阻止不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="6586d-274">方案：将通配符 (子域) </span><span class="sxs-lookup"><span data-stu-id="6586d-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="6586d-275">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="6586d-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="6586d-276">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="6586d-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-277">www.contoso.com</span></span>
  - <span data-ttu-id="6586d-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="6586d-279">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="6586d-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-280">123contoso.com</span></span>
  - <span data-ttu-id="6586d-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-281">contoso.com</span></span>
  - <span data-ttu-id="6586d-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="6586d-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="6586d-283">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="6586d-284">方案：路径顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="6586d-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="6586d-285">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="6586d-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="6586d-286">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="6586d-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="6586d-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="6586d-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="6586d-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="6586d-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="6586d-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="6586d-290">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="6586d-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-291">contoso.com</span></span>
  - <span data-ttu-id="6586d-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="6586d-292">contoso.com/a</span></span>
  - <span data-ttu-id="6586d-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-293">www.contoso.com</span></span>
  - <span data-ttu-id="6586d-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-294">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="6586d-295">应用场景：左波浪符</span><span class="sxs-lookup"><span data-stu-id="6586d-295">Scenario: Left tilde</span></span>

<span data-ttu-id="6586d-296">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="6586d-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="6586d-297">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="6586d-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-298">contoso.com</span></span>
  - <span data-ttu-id="6586d-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-299">www.contoso.com</span></span>
  - <span data-ttu-id="6586d-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="6586d-301">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="6586d-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-302">123contoso.com</span></span>
  - <span data-ttu-id="6586d-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="6586d-303">contoso.com/abc</span></span>
  - <span data-ttu-id="6586d-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="6586d-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="6586d-305">应用场景：右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="6586d-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="6586d-306">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="6586d-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="6586d-307">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="6586d-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6586d-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="6586d-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="6586d-309">contoso.com/a</span></span>
  - <span data-ttu-id="6586d-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="6586d-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="6586d-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="6586d-311">contoso.com/ab</span></span>
  - <span data-ttu-id="6586d-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="6586d-312">contoso.com/b</span></span>
  - <span data-ttu-id="6586d-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="6586d-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="6586d-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="6586d-314">contoso.com/ba</span></span>

- <span data-ttu-id="6586d-315">**允许不匹配和\*\*\*\*阻止不匹配**：contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="6586d-316">应用场景：左通配符子域和右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="6586d-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="6586d-317">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="6586d-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="6586d-318">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="6586d-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="6586d-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="6586d-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="6586d-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="6586d-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="6586d-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="6586d-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="6586d-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="6586d-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="6586d-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="6586d-324">**允许不匹配和\*\*\*\*阻止不匹配**：contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="6586d-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="6586d-325">应用场景：左右波浪符</span><span class="sxs-lookup"><span data-stu-id="6586d-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="6586d-326">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="6586d-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="6586d-327">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="6586d-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-328">contoso.com</span></span>
  - <span data-ttu-id="6586d-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="6586d-329">contoso.com/a</span></span>
  - <span data-ttu-id="6586d-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-330">www.contoso.com</span></span>
  - <span data-ttu-id="6586d-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="6586d-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="6586d-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="6586d-333">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="6586d-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-334">123contoso.com</span></span>
  - <span data-ttu-id="6586d-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="6586d-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="6586d-336">方案：IP 地址</span><span class="sxs-lookup"><span data-stu-id="6586d-336">Scenario: IP address</span></span>

<span data-ttu-id="6586d-337">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="6586d-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="6586d-338">**允许匹配** 和 **阻止匹配**：1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="6586d-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="6586d-339">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="6586d-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="6586d-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="6586d-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="6586d-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="6586d-342">具有右通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="6586d-342">IP address with right wildcard</span></span>

<span data-ttu-id="6586d-343">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="6586d-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="6586d-344">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="6586d-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="6586d-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="6586d-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="6586d-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="6586d-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="6586d-347">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="6586d-347">Examples of invalid entries</span></span>

<span data-ttu-id="6586d-348">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="6586d-348">The following entries are invalid:</span></span>

- <span data-ttu-id="6586d-349">**域值缺失或无效**：</span><span class="sxs-lookup"><span data-stu-id="6586d-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="6586d-350">contoso</span><span class="sxs-lookup"><span data-stu-id="6586d-350">contoso</span></span>
  - <span data-ttu-id="6586d-351">\*.contoso。\*</span><span class="sxs-lookup"><span data-stu-id="6586d-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="6586d-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="6586d-352">\*.com</span></span>
  - <span data-ttu-id="6586d-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="6586d-353">\*.pdf</span></span>

- <span data-ttu-id="6586d-354">**文本上的通配符或不带空格字符的通配符**：</span><span class="sxs-lookup"><span data-stu-id="6586d-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="6586d-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="6586d-355">\*contoso.com</span></span>
  - <span data-ttu-id="6586d-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="6586d-356">contoso.com\*</span></span>
  - <span data-ttu-id="6586d-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="6586d-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="6586d-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="6586d-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="6586d-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="6586d-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="6586d-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="6586d-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="6586d-361">**具有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="6586d-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="6586d-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="6586d-362">contoso.com:443</span></span>
  - <span data-ttu-id="6586d-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="6586d-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="6586d-364">**非描述性通配符**：</span><span class="sxs-lookup"><span data-stu-id="6586d-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="6586d-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="6586d-365">\*.\*</span></span>

- <span data-ttu-id="6586d-366">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="6586d-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="6586d-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="6586d-367">conto\*so.com</span></span>
  - <span data-ttu-id="6586d-368">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="6586d-368">conto~so.com</span></span>

- <span data-ttu-id="6586d-369">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="6586d-369">**Double wildcards**</span></span>

  - <span data-ttu-id="6586d-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="6586d-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="6586d-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="6586d-371">contoso.com/\*/\*</span></span>
