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
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515204"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-103">管理租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="a12d9-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a12d9-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="a12d9-104">**Applies to**</span></span>
- [<span data-ttu-id="a12d9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a12d9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a12d9-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="a12d9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a12d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a12d9-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="a12d9-108">本文中介绍的功能在预览版中，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="a12d9-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="a12d9-109">此时， **你无法** 配置租户允许/阻止列表中的允许项。</span><span class="sxs-lookup"><span data-stu-id="a12d9-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="a12d9-110">在具有 Exchange Online 邮箱的 Microsoft 365 组织或具有独立 Exchange Online Protection (EOP) 组织（没有 Exchange Online 邮箱）中，您可能会对 EOP 筛选裁定不一致。</span><span class="sxs-lookup"><span data-stu-id="a12d9-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="a12d9-111">例如，一条好邮件可能标记为错误 (误报) ，或者可能允许错误邮件通过 (误报) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="a12d9-112">安全与合规中心中的租户允许/阻止&提供了一种手动覆盖 Microsoft 365 筛选裁定的方法。</span><span class="sxs-lookup"><span data-stu-id="a12d9-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="a12d9-113">租户允许/阻止列表在邮件流期间和用户单击时使用。</span><span class="sxs-lookup"><span data-stu-id="a12d9-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="a12d9-114">可以指定要始终阻止的 URL 或文件。</span><span class="sxs-lookup"><span data-stu-id="a12d9-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="a12d9-115">本文介绍如何在安全与合规中心或 PowerShell & (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止列表中的条目;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a12d9-116">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="a12d9-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a12d9-117">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="a12d9-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a12d9-118">若要直接转到" **租户允许/阻止列表"** 页，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="a12d9-119">使用文件的 SHA256 哈希值指定文件。</span><span class="sxs-lookup"><span data-stu-id="a12d9-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="a12d9-120">若要在 Windows 中查找文件的 SHA256 哈希值，在命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a12d9-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="a12d9-121">示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="a12d9-122">不支持感知哈希 (哈希) 哈希值。</span><span class="sxs-lookup"><span data-stu-id="a12d9-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="a12d9-123">本文稍后的"租户允许/阻止列表"一节的 [URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍了可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="a12d9-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="a12d9-124">租户允许/阻止列表最多允许 500 个 URL 条目和 500 个文件哈希条目。</span><span class="sxs-lookup"><span data-stu-id="a12d9-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="a12d9-125">每个条目的最大字符数为：</span><span class="sxs-lookup"><span data-stu-id="a12d9-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="a12d9-126">文件哈希 = 64</span><span class="sxs-lookup"><span data-stu-id="a12d9-126">File hashes = 64</span></span>
  - <span data-ttu-id="a12d9-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="a12d9-127">URL = 250</span></span>

- <span data-ttu-id="a12d9-128">条目应在 30 分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a12d9-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="a12d9-129">默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="a12d9-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="a12d9-130">可以指定日期或将其设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="a12d9-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="a12d9-131">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a12d9-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a12d9-132">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a12d9-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a12d9-133">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="a12d9-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a12d9-134">若要在租户允许/阻止列表中添加和删除值，你需要是组织 **管理或\*\*\*\*安全管理员角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="a12d9-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a12d9-135">若要对租户允许/阻止列表进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="a12d9-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a12d9-136">有关详细信息，请参阅 [Exchange Online 中权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="a12d9-136">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="a12d9-137">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="a12d9-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a12d9-138">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a12d9-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="a12d9-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="a12d9-139">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-140">使用安全&合规中心在租户允许/阻止列表中创建 URL 条目</span><span class="sxs-lookup"><span data-stu-id="a12d9-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a12d9-141">有关 URL 条目语法的详细信息，请参阅本文稍后介绍的 ["租户允许/阻止](#url-syntax-for-the-tenant-allowblock-list) 列表"一节的 URL 语法。</span><span class="sxs-lookup"><span data-stu-id="a12d9-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="a12d9-142">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a12d9-143">在 **"租户允许/阻止列表** "页上，验证是否选择了 **"URL"** 选项卡，然后单击"阻止 **"**</span><span class="sxs-lookup"><span data-stu-id="a12d9-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="a12d9-144">在 **出现的"阻止 URL"** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a12d9-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a12d9-145">**添加要阻止的 URL：** 每行输入一个 URL，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="a12d9-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a12d9-146">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="a12d9-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a12d9-147">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="a12d9-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="a12d9-148">或</span><span class="sxs-lookup"><span data-stu-id="a12d9-148">or</span></span>

     - <span data-ttu-id="a12d9-149">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="a12d9-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="a12d9-151">.</span><span class="sxs-lookup"><span data-stu-id="a12d9-151">.</span></span>

   - <span data-ttu-id="a12d9-152">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="a12d9-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a12d9-153">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a12d9-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-154">使用安全&合规中心在租户允许/阻止列表中创建文件条目</span><span class="sxs-lookup"><span data-stu-id="a12d9-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a12d9-155">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a12d9-156">在"**租户允许/阻止列表"** 页上，**选择"** 文件"选项卡，然后单击"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="a12d9-157">在 **"添加文件以阻止** 出现的飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a12d9-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a12d9-158">**添加文件哈希**：每行输入一个 SHA256 哈希值，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="a12d9-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a12d9-159">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="a12d9-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a12d9-160">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="a12d9-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a12d9-161">或</span><span class="sxs-lookup"><span data-stu-id="a12d9-161">or</span></span>

     - <span data-ttu-id="a12d9-162">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="a12d9-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="a12d9-164">.</span><span class="sxs-lookup"><span data-stu-id="a12d9-164">.</span></span>

   - <span data-ttu-id="a12d9-165">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="a12d9-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a12d9-166">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a12d9-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-167">使用安全&合规中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a12d9-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a12d9-168">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a12d9-169">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a12d9-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="a12d9-170">单击以下列标题以按升序或降序排序：</span><span class="sxs-lookup"><span data-stu-id="a12d9-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="a12d9-171">**值**：URL 或文件哈希。</span><span class="sxs-lookup"><span data-stu-id="a12d9-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="a12d9-172">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="a12d9-172">**Last updated date**</span></span>
- <span data-ttu-id="a12d9-173">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="a12d9-173">**Expiration date**</span></span>
- <span data-ttu-id="a12d9-174">**注意**</span><span class="sxs-lookup"><span data-stu-id="a12d9-174">**Note**</span></span>

<span data-ttu-id="a12d9-175">单击 **"搜索**"，输入值的一部分或全部，然后按 Enter 查找特定值。</span><span class="sxs-lookup"><span data-stu-id="a12d9-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="a12d9-176">完成后，单击"清除 **搜索清除** ![ 搜索"图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="a12d9-177">单击 **"筛选"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-177">Click **Filter**.</span></span> <span data-ttu-id="a12d9-178">在 **出现的"** 筛选器"飞出中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="a12d9-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="a12d9-179">**永不过期**： 选择关闭： ![ 关闭 ](../../media/scc-toggle-off.png) 或打开： ![ 打开 ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="a12d9-180">**Last updated**： Select a start date (**From**) ， an end date (**To**) both.</span><span class="sxs-lookup"><span data-stu-id="a12d9-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="a12d9-181">**到期日期：** 选择开始日期 (开始日期) 开始日期，选择结束日期 (") "或同时选择两者。 </span><span class="sxs-lookup"><span data-stu-id="a12d9-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="a12d9-182">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="a12d9-183">若要清除现有筛选器，请单击 **"筛选器**"，在出现的 **"** 筛选器"飞出中，单击 **"清除筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-184">使用安全&合规中心修改租户允许/阻止列表中的阻止条目</span><span class="sxs-lookup"><span data-stu-id="a12d9-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a12d9-185">不能修改条目中的现有阻止 URL 或文件值。</span><span class="sxs-lookup"><span data-stu-id="a12d9-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="a12d9-186">若要修改这些值，需要删除并重新创建条目。</span><span class="sxs-lookup"><span data-stu-id="a12d9-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="a12d9-187">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a12d9-188">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a12d9-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="a12d9-189">选择要修改的阻止条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="a12d9-190">在出现的飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a12d9-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a12d9-191">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="a12d9-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a12d9-192">验证该设置是否 (关闭) 并使用"过期"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="a12d9-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="a12d9-193">或</span><span class="sxs-lookup"><span data-stu-id="a12d9-193">or</span></span>

     - <span data-ttu-id="a12d9-194">将开关向右移动以将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="a12d9-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="a12d9-196">.</span><span class="sxs-lookup"><span data-stu-id="a12d9-196">.</span></span>

   - <span data-ttu-id="a12d9-197">**可选注意**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="a12d9-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="a12d9-198">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="a12d9-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-199">使用安全&合规中心从租户允许/阻止列表中删除阻止条目</span><span class="sxs-lookup"><span data-stu-id="a12d9-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a12d9-200">在安全&，转到 **"威胁管理** \> **策略** \> **租户允许/阻止列表"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a12d9-201">选择 **"URL"** 选项卡或" **文件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a12d9-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="a12d9-202">选择要删除的阻止条目，然后单击"删除 **"** ![ 图标 ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="a12d9-203">在出现的警告对话框中，单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="a12d9-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-204">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="a12d9-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-205">使用 PowerShell 将阻止条目添加到租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="a12d9-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="a12d9-206">若要在租户允许/阻止列表中添加阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a12d9-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a12d9-207">本示例为网站和contoso.com域添加一个阻止 URL 条目 (例如，contoso.com、www.contoso.com和xyz.abc.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="a12d9-208">由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="a12d9-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="a12d9-209">本示例为永不过期的指定文件添加阻止文件条目。</span><span class="sxs-lookup"><span data-stu-id="a12d9-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="a12d9-210">有关语法和参数的详细信息，请参阅[New-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="a12d9-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-211">使用 PowerShell 查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a12d9-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a12d9-212">若要查看租户允许/阻止列表中的条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a12d9-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="a12d9-213">此示例返回所有阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="a12d9-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="a12d9-214">此示例返回指定文件哈希值的信息。</span><span class="sxs-lookup"><span data-stu-id="a12d9-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="a12d9-215">有关语法和参数的详细信息，请参阅[Get-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="a12d9-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-216">使用 PowerShell 修改租户允许/阻止列表中的阻止条目</span><span class="sxs-lookup"><span data-stu-id="a12d9-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a12d9-217">不能修改阻止条目中的现有 URL 或文件值。</span><span class="sxs-lookup"><span data-stu-id="a12d9-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="a12d9-218">若要修改这些值，需要删除并重新创建条目。</span><span class="sxs-lookup"><span data-stu-id="a12d9-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="a12d9-219">若要修改租户允许/阻止列表中的阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a12d9-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a12d9-220">本示例更改指定阻止条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="a12d9-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="a12d9-221">有关语法和参数的详细信息，请参阅[Set-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="a12d9-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-222">使用 PowerShell 从租户允许/阻止列表中删除阻止条目</span><span class="sxs-lookup"><span data-stu-id="a12d9-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a12d9-223">若要从租户允许/阻止列表中删除阻止条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a12d9-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a12d9-224">此示例从租户允许/阻止列表中删除指定的阻止 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="a12d9-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="a12d9-225">有关语法和参数的详细信息，请参阅[Remove-TenantAllowBlockListItems。](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="a12d9-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="a12d9-226">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="a12d9-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="a12d9-227">允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="a12d9-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="a12d9-228">不允许使用文件名扩展名 (例如，test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="a12d9-229">不支持 Unicode，但 Punycode 支持。</span><span class="sxs-lookup"><span data-stu-id="a12d9-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="a12d9-230">如果以下所有语句都为 true，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="a12d9-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="a12d9-231">主机名包含一个时间段。</span><span class="sxs-lookup"><span data-stu-id="a12d9-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="a12d9-232">在时间段的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="a12d9-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="a12d9-233">此期间右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="a12d9-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="a12d9-234">例如， `t.co` 允许; `.com` `contoso.` 或不允许。</span><span class="sxs-lookup"><span data-stu-id="a12d9-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="a12d9-235">不隐含子路径。</span><span class="sxs-lookup"><span data-stu-id="a12d9-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="a12d9-236">例如， `contoso.com` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="a12d9-237">以下 (允许) \*通配符：</span><span class="sxs-lookup"><span data-stu-id="a12d9-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="a12d9-238">左通配符后跟一个时间段以指定子域。</span><span class="sxs-lookup"><span data-stu-id="a12d9-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="a12d9-239">例如， `*.contoso.com` 允许; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="a12d9-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="a12d9-240">右通配符必须按照正斜杠 (/) 指定路径。</span><span class="sxs-lookup"><span data-stu-id="a12d9-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="a12d9-241">例如， `contoso.com/*` 允许; `contoso.com*` `contoso.com/ab*` 或不允许。</span><span class="sxs-lookup"><span data-stu-id="a12d9-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="a12d9-242">右通配符不隐含所有子路径。</span><span class="sxs-lookup"><span data-stu-id="a12d9-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="a12d9-243">例如， `contoso.com/*` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="a12d9-244">`*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="a12d9-245">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="a12d9-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="a12d9-246">tilde (~) 字符在下列情况下可用：</span><span class="sxs-lookup"><span data-stu-id="a12d9-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="a12d9-247">左波浪符表示域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="a12d9-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="a12d9-248">例如， `~contoso.com` 包括 `contoso.com` `*.contoso.com` 和 。</span><span class="sxs-lookup"><span data-stu-id="a12d9-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="a12d9-249">包含协议（例如， (，或) ）的 URL 条目将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="a12d9-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="a12d9-250">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="a12d9-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="a12d9-251">引号 ("或") 无效字符。</span><span class="sxs-lookup"><span data-stu-id="a12d9-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="a12d9-252">URL 应包含所有重定向（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="a12d9-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="a12d9-253">URL 条目方案</span><span class="sxs-lookup"><span data-stu-id="a12d9-253">URL entry scenarios</span></span>

<span data-ttu-id="a12d9-254">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="a12d9-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="a12d9-255">方案：无通配符</span><span class="sxs-lookup"><span data-stu-id="a12d9-255">Scenario: No wildcards</span></span>

<span data-ttu-id="a12d9-256">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a12d9-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="a12d9-257">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="a12d9-258">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="a12d9-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-259">abc-contoso.com</span></span>
  - <span data-ttu-id="a12d9-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a12d9-260">contoso.com/a</span></span>
  - <span data-ttu-id="a12d9-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="a12d9-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="a12d9-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a12d9-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-264">www.contoso.com</span></span>
  - <span data-ttu-id="a12d9-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a12d9-266">**块匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-266">**Block match**:</span></span>

  - <span data-ttu-id="a12d9-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-267">contoso.com</span></span>
  - <span data-ttu-id="a12d9-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a12d9-268">contoso.com/a</span></span>
  - <span data-ttu-id="a12d9-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="a12d9-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="a12d9-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a12d9-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-272">www.contoso.com</span></span>
  - <span data-ttu-id="a12d9-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a12d9-274">**块不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="a12d9-275">方案：将通配符 (子域) </span><span class="sxs-lookup"><span data-stu-id="a12d9-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="a12d9-276">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a12d9-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="a12d9-277">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a12d9-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-278">www.contoso.com</span></span>
  - <span data-ttu-id="a12d9-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a12d9-280">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a12d9-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-281">123contoso.com</span></span>
  - <span data-ttu-id="a12d9-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-282">contoso.com</span></span>
  - <span data-ttu-id="a12d9-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="a12d9-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a12d9-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="a12d9-285">方案：路径顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="a12d9-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="a12d9-286">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="a12d9-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="a12d9-287">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a12d9-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="a12d9-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="a12d9-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a12d9-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a12d9-290">contoso.com/a/？q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="a12d9-291">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a12d9-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-292">contoso.com</span></span>
  - <span data-ttu-id="a12d9-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a12d9-293">contoso.com/a</span></span>
  - <span data-ttu-id="a12d9-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-294">www.contoso.com</span></span>
  - <span data-ttu-id="a12d9-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="a12d9-296">方案：左波浪符</span><span class="sxs-lookup"><span data-stu-id="a12d9-296">Scenario: Left tilde</span></span>

<span data-ttu-id="a12d9-297">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a12d9-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="a12d9-298">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a12d9-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-299">contoso.com</span></span>
  - <span data-ttu-id="a12d9-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-300">www.contoso.com</span></span>
  - <span data-ttu-id="a12d9-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a12d9-302">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a12d9-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-303">123contoso.com</span></span>
  - <span data-ttu-id="a12d9-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a12d9-304">contoso.com/abc</span></span>
  - <span data-ttu-id="a12d9-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a12d9-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="a12d9-306">方案：右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="a12d9-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="a12d9-307">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a12d9-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="a12d9-308">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a12d9-309">contoso.com/？q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="a12d9-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a12d9-310">contoso.com/a</span></span>
  - <span data-ttu-id="a12d9-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a12d9-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a12d9-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a12d9-312">contoso.com/ab</span></span>
  - <span data-ttu-id="a12d9-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a12d9-313">contoso.com/b</span></span>
  - <span data-ttu-id="a12d9-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a12d9-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a12d9-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a12d9-315">contoso.com/ba</span></span>

- <span data-ttu-id="a12d9-316">**允许不匹配和\*\*\*\*阻止不匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="a12d9-317">方案：左通配符子域和右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="a12d9-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="a12d9-318">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a12d9-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="a12d9-319">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a12d9-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a12d9-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="a12d9-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a12d9-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a12d9-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a12d9-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="a12d9-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a12d9-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a12d9-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a12d9-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="a12d9-325">**允许不匹配和\*\*\*\*阻止不匹配**： contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a12d9-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="a12d9-326">方案：左右波浪符</span><span class="sxs-lookup"><span data-stu-id="a12d9-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="a12d9-327">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="a12d9-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="a12d9-328">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a12d9-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-329">contoso.com</span></span>
  - <span data-ttu-id="a12d9-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a12d9-330">contoso.com/a</span></span>
  - <span data-ttu-id="a12d9-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-331">www.contoso.com</span></span>
  - <span data-ttu-id="a12d9-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a12d9-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="a12d9-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a12d9-334">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a12d9-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-335">123contoso.com</span></span>
  - <span data-ttu-id="a12d9-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="a12d9-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="a12d9-337">方案：IP 地址</span><span class="sxs-lookup"><span data-stu-id="a12d9-337">Scenario: IP address</span></span>

<span data-ttu-id="a12d9-338">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="a12d9-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="a12d9-339">**允许匹配** 和 **阻止匹配**：1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a12d9-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="a12d9-340">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a12d9-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a12d9-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="a12d9-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a12d9-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="a12d9-343">具有右通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="a12d9-343">IP address with right wildcard</span></span>

<span data-ttu-id="a12d9-344">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="a12d9-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="a12d9-345">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a12d9-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="a12d9-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="a12d9-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="a12d9-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="a12d9-348">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="a12d9-348">Examples of invalid entries</span></span>

<span data-ttu-id="a12d9-349">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="a12d9-349">The following entries are invalid:</span></span>

- <span data-ttu-id="a12d9-350">**缺少或无效的域值**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="a12d9-351">contoso</span><span class="sxs-lookup"><span data-stu-id="a12d9-351">contoso</span></span>
  - <span data-ttu-id="a12d9-352">\*.contoso。\*</span><span class="sxs-lookup"><span data-stu-id="a12d9-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="a12d9-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-353">\*.com</span></span>
  - <span data-ttu-id="a12d9-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="a12d9-354">\*.pdf</span></span>

- <span data-ttu-id="a12d9-355">**文本上的通配符或不带空格字符的通配符**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="a12d9-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-356">\*contoso.com</span></span>
  - <span data-ttu-id="a12d9-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="a12d9-357">contoso.com\*</span></span>
  - <span data-ttu-id="a12d9-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a12d9-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="a12d9-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="a12d9-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="a12d9-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="a12d9-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="a12d9-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="a12d9-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="a12d9-362">**具有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="a12d9-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="a12d9-363">contoso.com:443</span></span>
  - <span data-ttu-id="a12d9-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="a12d9-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="a12d9-365">**非描述性通配符**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="a12d9-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="a12d9-366">\*.\*</span></span>

- <span data-ttu-id="a12d9-367">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="a12d9-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="a12d9-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-368">conto\*so.com</span></span>
  - <span data-ttu-id="a12d9-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="a12d9-369">conto~so.com</span></span>

- <span data-ttu-id="a12d9-370">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="a12d9-370">**Double wildcards**</span></span>

  - <span data-ttu-id="a12d9-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="a12d9-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="a12d9-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="a12d9-372">contoso.com/\*/\*</span></span>
