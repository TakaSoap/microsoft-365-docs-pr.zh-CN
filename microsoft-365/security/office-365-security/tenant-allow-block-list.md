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
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538959"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-103">管理租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="f18dd-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f18dd-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="f18dd-104">**Applies to**</span></span>
- [<span data-ttu-id="f18dd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f18dd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f18dd-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="f18dd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f18dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f18dd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="f18dd-108">本文中所述的功能在预览版中，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="f18dd-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="f18dd-109">如果你的组织没有本文中所述的欺骗功能，请参阅使用欺骗智能策略和 EOP 中的欺骗智能见解管理欺骗发件人中的旧版欺骗 [管理体验](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="f18dd-110">目前，你 **无法** 配置租户允许/阻止列表中的允许 URL 或文件项。</span><span class="sxs-lookup"><span data-stu-id="f18dd-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="f18dd-111">在Microsoft 365没有邮箱的 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，您可能会与 EOP 筛选裁定不一致。</span><span class="sxs-lookup"><span data-stu-id="f18dd-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f18dd-112">例如，一条好邮件可能标记为 (误报) ，或者可能允许错误消息通过 (漏报) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f18dd-113">安全与合规中心中的租户&/阻止列表提供了一种手动覆盖Microsoft 365裁定的方法。</span><span class="sxs-lookup"><span data-stu-id="f18dd-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f18dd-114">租户允许/阻止列表在邮件流期间和用户单击时使用。</span><span class="sxs-lookup"><span data-stu-id="f18dd-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f18dd-115">可以指定以下类型的替代：</span><span class="sxs-lookup"><span data-stu-id="f18dd-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="f18dd-116">要阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="f18dd-116">URLs to block.</span></span>
- <span data-ttu-id="f18dd-117">要阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="f18dd-117">Files to block.</span></span>
- <span data-ttu-id="f18dd-118">要允许的批量邮件发件人域。</span><span class="sxs-lookup"><span data-stu-id="f18dd-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="f18dd-119">有关批量邮件、批量可信度 (BCL) 以及反垃圾邮件策略的批量邮件筛选详细信息，请参阅批量投诉级别 [ (BCL) in EOP](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="f18dd-120">允许或阻止欺骗发件人。</span><span class="sxs-lookup"><span data-stu-id="f18dd-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="f18dd-121">如果替代欺骗智能见解中的允许或阻止裁定[](learn-about-spoof-intelligence.md)，欺骗发件人将成为仅出现在租户允许/阻止列表中的"欺骗"选项卡上的手动允许或阻止条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="f18dd-122">在欺骗智能检测到欺骗性发件人之前，还可以在此处手动创建允许或阻止欺骗发件人的允许或阻止条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="f18dd-123">本文介绍如何在安全& 合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f18dd-124">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="f18dd-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f18dd-125">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="f18dd-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f18dd-126">若要直接转到租户 **允许/阻止列表** 页面，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f18dd-127">使用文件的 SHA256 哈希值指定文件。</span><span class="sxs-lookup"><span data-stu-id="f18dd-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="f18dd-128">若要在命令提示符中查找文件的 SHA256 哈希Windows，在命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f18dd-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="f18dd-129">示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="f18dd-130">不支持感知哈希 (pHash) 值。</span><span class="sxs-lookup"><span data-stu-id="f18dd-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="f18dd-131">本文稍后的租户允许/阻止列表一节的 [URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍了可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="f18dd-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="f18dd-132">租户允许/阻止列表允许最多 500 个 URL 条目和 500 个文件哈希条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="f18dd-133">每个条目的最大字符数为：</span><span class="sxs-lookup"><span data-stu-id="f18dd-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="f18dd-134">文件哈希 = 64</span><span class="sxs-lookup"><span data-stu-id="f18dd-134">File hashes = 64</span></span>
  - <span data-ttu-id="f18dd-135">URL = 250</span><span class="sxs-lookup"><span data-stu-id="f18dd-135">URL = 250</span></span>

- <span data-ttu-id="f18dd-136">条目应在 30 分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="f18dd-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="f18dd-137">默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f18dd-138">可以指定日期或将其设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f18dd-139">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f18dd-140">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f18dd-141">在 Exchange Online 网站中 分配 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="f18dd-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f18dd-142">**URL、文件和允许批量发件人**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="f18dd-143">若要在租户允许/阻止列表中添加和删除值，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="f18dd-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="f18dd-144">若要对租户允许/阻止列表进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="f18dd-145">**欺骗**：以下组合之一：</span><span class="sxs-lookup"><span data-stu-id="f18dd-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="f18dd-146">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="f18dd-146">**Organization Management**</span></span>
    - <span data-ttu-id="f18dd-147">**安全管理员**<u>和</u>**仅查看配置** 或 **仅查看组织管理**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="f18dd-148">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="f18dd-149">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="f18dd-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f18dd-150">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="f18dd-151">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="f18dd-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-152">使用安全&中心在租户允许/阻止列表中创建阻止 URL 条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f18dd-153">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f18dd-154">在" **租户允许/阻止列表** "页上，验证 **"URL"** 选项卡是否被选中，然后单击"阻止 **"**</span><span class="sxs-lookup"><span data-stu-id="f18dd-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="f18dd-155">在 **出现的"阻止 URL"** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f18dd-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f18dd-156">**添加要阻止的 URL：** 每行输入一个 URL，最多输入 20 个。</span><span class="sxs-lookup"><span data-stu-id="f18dd-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="f18dd-157">有关 URL 条目的语法的详细信息，请参阅本文稍后介绍的租户 [允许/阻止列表的 URL](#url-syntax-for-the-tenant-allowblock-list) 语法部分。</span><span class="sxs-lookup"><span data-stu-id="f18dd-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="f18dd-158">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="f18dd-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f18dd-159">验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="f18dd-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="f18dd-160">或</span><span class="sxs-lookup"><span data-stu-id="f18dd-160">or</span></span>

     - <span data-ttu-id="f18dd-161">将开关移到右侧，将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="f18dd-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="f18dd-163">.</span><span class="sxs-lookup"><span data-stu-id="f18dd-163">.</span></span>

   - <span data-ttu-id="f18dd-164">**可选说明**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="f18dd-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f18dd-165">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="f18dd-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-166">使用安全&中心在租户允许/阻止列表中创建阻止文件条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f18dd-167">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f18dd-168">在"**租户允许/阻止列表"** 页上，选择"**文件"** 选项卡，然后单击"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="f18dd-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="f18dd-169">在 **"添加文件以阻止** 出现的飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f18dd-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f18dd-170">**添加文件哈希**：每行输入一个 SHA256 哈希值，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="f18dd-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f18dd-171">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="f18dd-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f18dd-172">验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="f18dd-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f18dd-173">或</span><span class="sxs-lookup"><span data-stu-id="f18dd-173">or</span></span>

     - <span data-ttu-id="f18dd-174">将开关移到右侧，将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="f18dd-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="f18dd-176">.</span><span class="sxs-lookup"><span data-stu-id="f18dd-176">.</span></span>

   - <span data-ttu-id="f18dd-177">**可选说明**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="f18dd-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f18dd-178">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="f18dd-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-179">使用安全&中心在租户允许/阻止列表中创建允许批量邮件发件人域条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f18dd-180">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f18dd-181">在"**租户允许/阻止列表"** 页上，选择 **"BCL** 绕过"选项卡的"发件人域"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="f18dd-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="f18dd-182">在出现的 **"为 BCL 旁路添加** 发件人域"飞出区中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f18dd-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f18dd-183">**为 BCL 旁路** 添加发件人域：每行输入一个包含良好批量邮件的源域，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="f18dd-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f18dd-184">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="f18dd-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f18dd-185">验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="f18dd-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f18dd-186">或</span><span class="sxs-lookup"><span data-stu-id="f18dd-186">or</span></span>

     - <span data-ttu-id="f18dd-187">将开关移到右侧，将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="f18dd-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="f18dd-189">.</span><span class="sxs-lookup"><span data-stu-id="f18dd-189">.</span></span>

4. <span data-ttu-id="f18dd-190">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="f18dd-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-191">使用安全&中心在租户允许/阻止列表中创建允许或阻止欺骗发件人条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-192">**注意**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-192">**Notes**:</span></span>

- <span data-ttu-id="f18dd-193">仅 _明确_ 允许或阻止欺骗用户和域对中定义的发送基础结构的组合。</span><span class="sxs-lookup"><span data-stu-id="f18dd-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="f18dd-194">为域对配置允许或阻止条目时，来自该域对的邮件将不再显示在欺骗智能见解中。</span><span class="sxs-lookup"><span data-stu-id="f18dd-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="f18dd-195">欺骗性发件人的条目永不过期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="f18dd-196">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f18dd-197">在"**租户允许/阻止列表"** 页上，选择"**欺骗"** 选项卡，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="f18dd-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="f18dd-198">在出现的 **"添加新域对** "飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f18dd-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f18dd-199">**使用通配符添加新域对**：每行输入一个域对，最多输入 20 个域对。</span><span class="sxs-lookup"><span data-stu-id="f18dd-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="f18dd-200">有关欺骗性发件人条目的语法的详细信息，请参阅本文稍后的租户允许 [/](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 阻止列表部分中的欺骗性发件人条目的域对语法。</span><span class="sxs-lookup"><span data-stu-id="f18dd-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="f18dd-201">**欺骗类型**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="f18dd-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="f18dd-202">**内部**：欺骗性发件人位于组织所属的域中， ([接受的) 。](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="f18dd-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="f18dd-203">**外部**：欺骗性发件人位于外部域中。</span><span class="sxs-lookup"><span data-stu-id="f18dd-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="f18dd-204">**操作**：选择 **"允许"** 或"**阻止"。**</span><span class="sxs-lookup"><span data-stu-id="f18dd-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="f18dd-205">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="f18dd-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-206">使用安全&中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f18dd-207">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f18dd-208">选择您想要的选项卡。</span><span class="sxs-lookup"><span data-stu-id="f18dd-208">Select the tab you want.</span></span> <span data-ttu-id="f18dd-209">可用的列取决于所选的选项卡：</span><span class="sxs-lookup"><span data-stu-id="f18dd-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="f18dd-210">**URL：**</span><span class="sxs-lookup"><span data-stu-id="f18dd-210">**URLs**:</span></span>
     - <span data-ttu-id="f18dd-211">**值**：URL。</span><span class="sxs-lookup"><span data-stu-id="f18dd-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="f18dd-212">**操作**：值 **Block**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="f18dd-213">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-213">**Last updated date**</span></span>
     - <span data-ttu-id="f18dd-214">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-214">**Expiration date**</span></span>
     - <span data-ttu-id="f18dd-215">**注意**</span><span class="sxs-lookup"><span data-stu-id="f18dd-215">**Note**</span></span>

   - <span data-ttu-id="f18dd-216">**Files**</span><span class="sxs-lookup"><span data-stu-id="f18dd-216">**Files**</span></span>
     - <span data-ttu-id="f18dd-217">**值**：文件哈希。</span><span class="sxs-lookup"><span data-stu-id="f18dd-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="f18dd-218">**操作**：值 **Block**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="f18dd-219">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-219">**Last updated date**</span></span>
     - <span data-ttu-id="f18dd-220">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-220">**Expiration date**</span></span>
     - <span data-ttu-id="f18dd-221">**注意**</span><span class="sxs-lookup"><span data-stu-id="f18dd-221">**Note**</span></span>

   - <span data-ttu-id="f18dd-222">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="f18dd-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="f18dd-223">**值**：批量邮件发件人的域。</span><span class="sxs-lookup"><span data-stu-id="f18dd-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="f18dd-224">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-224">**Last updated date**</span></span>
     - <span data-ttu-id="f18dd-225">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-225">**Expiration date**</span></span>

   - <span data-ttu-id="f18dd-226">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="f18dd-226">**Spoofing**</span></span>
     - <span data-ttu-id="f18dd-227">**欺骗用户**</span><span class="sxs-lookup"><span data-stu-id="f18dd-227">**Spoofed user**</span></span>
     - <span data-ttu-id="f18dd-228">**发送基础结构**</span><span class="sxs-lookup"><span data-stu-id="f18dd-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="f18dd-229">**欺骗类型**：值 **Internal** 或 **External**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="f18dd-230">**操作**：值 **Block** 或 **Allow**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="f18dd-231">可以单击列标题以按升序或降序排序。</span><span class="sxs-lookup"><span data-stu-id="f18dd-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="f18dd-232">可以单击 **"分组** "对结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="f18dd-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="f18dd-233">可用的值取决于所选的选项卡：</span><span class="sxs-lookup"><span data-stu-id="f18dd-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="f18dd-234">**URL**：可以按操作 对结果 **进行分组**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="f18dd-235">**文件**：可以按操作 对结果 **进行分组**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="f18dd-236">**BCL 绕过的** 发件人域 **：** 此选项卡上未提供组。</span><span class="sxs-lookup"><span data-stu-id="f18dd-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="f18dd-237">**欺骗：** 你可以按操作或欺骗 **类型\*\*\*\*对结果进行分组**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="f18dd-238">单击 **"搜索**"，输入值的全部或一部分，然后按 Enter 查找特定值。</span><span class="sxs-lookup"><span data-stu-id="f18dd-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f18dd-239">完成后，单击"清除搜索 **""** ![ 清除搜索图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) "。</span><span class="sxs-lookup"><span data-stu-id="f18dd-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="f18dd-240">单击 **"筛选** "筛选结果。</span><span class="sxs-lookup"><span data-stu-id="f18dd-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="f18dd-241">显示在"筛选器 **"飞出** 控件中的可用值取决于所选的选项卡：</span><span class="sxs-lookup"><span data-stu-id="f18dd-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="f18dd-242">**URL**</span><span class="sxs-lookup"><span data-stu-id="f18dd-242">**URLs**</span></span>
     - <span data-ttu-id="f18dd-243">**Action**</span><span class="sxs-lookup"><span data-stu-id="f18dd-243">**Action**</span></span>
     - <span data-ttu-id="f18dd-244">**永不过期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-244">**Never expire**</span></span>
     - <span data-ttu-id="f18dd-245">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-245">**Last updated date**</span></span>
     - <span data-ttu-id="f18dd-246">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-246">**Expiration date**</span></span>

   - <span data-ttu-id="f18dd-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="f18dd-247">**Files**</span></span>
     - <span data-ttu-id="f18dd-248">**Action**</span><span class="sxs-lookup"><span data-stu-id="f18dd-248">**Action**</span></span>
     - <span data-ttu-id="f18dd-249">**永不过期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-249">**Never expire**</span></span>
     - <span data-ttu-id="f18dd-250">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-250">**Last updated date**</span></span>
     - <span data-ttu-id="f18dd-251">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-251">**Expiration date**</span></span>

   - <span data-ttu-id="f18dd-252">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="f18dd-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="f18dd-253">**永不过期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-253">**Never expire**</span></span>
     - <span data-ttu-id="f18dd-254">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-254">**Last updated date**</span></span>
     - <span data-ttu-id="f18dd-255">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="f18dd-255">**Expiration date**</span></span>

   - <span data-ttu-id="f18dd-256">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="f18dd-256">**Spoofing**</span></span>
     - <span data-ttu-id="f18dd-257">**Action**</span><span class="sxs-lookup"><span data-stu-id="f18dd-257">**Action**</span></span>
     - <span data-ttu-id="f18dd-258">**欺骗类型**</span><span class="sxs-lookup"><span data-stu-id="f18dd-258">**Spoof type**</span></span>

   <span data-ttu-id="f18dd-259">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="f18dd-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="f18dd-260">若要清除现有筛选器，请单击 **"筛选器"，** 在出现的"筛选器"飞出中，单击"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="f18dd-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-261">使用安全&中心修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f18dd-262">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f18dd-263">选择包含要修改的条目类型的选项卡：</span><span class="sxs-lookup"><span data-stu-id="f18dd-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="f18dd-264">**URL**</span><span class="sxs-lookup"><span data-stu-id="f18dd-264">**URLs**</span></span>
   - <span data-ttu-id="f18dd-265">**Files**</span><span class="sxs-lookup"><span data-stu-id="f18dd-265">**Files**</span></span>
   - <span data-ttu-id="f18dd-266">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="f18dd-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="f18dd-267">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="f18dd-267">**Spoofing**</span></span>

3. <span data-ttu-id="f18dd-268">选择要修改的条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="f18dd-269">可以在出现的飞出控件中修改的值取决于您在上一步中所选的选项卡：</span><span class="sxs-lookup"><span data-stu-id="f18dd-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="f18dd-270">**URL**</span><span class="sxs-lookup"><span data-stu-id="f18dd-270">**URLs**</span></span>
     - <span data-ttu-id="f18dd-271">**永不过期** 和/或到期日期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="f18dd-272">**可选注释**</span><span class="sxs-lookup"><span data-stu-id="f18dd-272">**Optional note**</span></span>

   - <span data-ttu-id="f18dd-273">**Files**</span><span class="sxs-lookup"><span data-stu-id="f18dd-273">**Files**</span></span>
     - <span data-ttu-id="f18dd-274">**永不过期** 和/或到期日期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="f18dd-275">**可选注释**</span><span class="sxs-lookup"><span data-stu-id="f18dd-275">**Optional note**</span></span>

   - <span data-ttu-id="f18dd-276">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="f18dd-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="f18dd-277">**永不过期** 和/或到期日期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="f18dd-278">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="f18dd-278">**Spoofing**</span></span>
     - <span data-ttu-id="f18dd-279">**操作**：可以将值更改为"允许 **"或**"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="f18dd-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="f18dd-280">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f18dd-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-281">使用安全&中心从租户允许/阻止列表中删除条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f18dd-282">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="f18dd-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f18dd-283">选择包含要删除的条目类型的选项卡：</span><span class="sxs-lookup"><span data-stu-id="f18dd-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="f18dd-284">**URL**</span><span class="sxs-lookup"><span data-stu-id="f18dd-284">**URLs**</span></span>
   - <span data-ttu-id="f18dd-285">**Files**</span><span class="sxs-lookup"><span data-stu-id="f18dd-285">**Files**</span></span>
   - <span data-ttu-id="f18dd-286">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="f18dd-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="f18dd-287">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="f18dd-287">**Spoofing**</span></span>

3. <span data-ttu-id="f18dd-288">选择要删除的条目，然后单击"删除 **删除图标** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) "。</span><span class="sxs-lookup"><span data-stu-id="f18dd-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f18dd-289">在出现的警告对话框中，单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="f18dd-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-290">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="f18dd-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-291">使用 PowerShell 将阻止文件或 URL 条目添加到租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="f18dd-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-292">若要在租户允许/阻止列表中添加阻止文件或 URL 条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="f18dd-293">本示例为永不过期的指定文件添加阻止文件条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="f18dd-294">此示例为 contoso.com 及其所有子域（例如， (、contoso.com、www.contoso.com 和 xyz.abc.contoso.com) ）添加一个阻止 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f18dd-295">由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="f18dd-296">有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-297">使用 PowerShell 将允许批量邮件发件人域条目添加到租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="f18dd-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-298">若要在租户允许/阻止列表中添加允许批量邮件发件人域条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="f18dd-299">本示例为永不过期的指定域添加允许的批量发件人条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="f18dd-300">有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-301">使用 PowerShell 将允许或阻止欺骗发件人条目添加到租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="f18dd-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-302">若要在租户允许/阻止列表中添加欺骗性发件人条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="f18dd-303">有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-304">使用 PowerShell 查看租户允许/阻止列表中的阻止文件或 URL 条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-305">若要查看租户允许/阻止列表中的阻止文件或 URL 条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="f18dd-306">此示例返回指定文件哈希值的信息。</span><span class="sxs-lookup"><span data-stu-id="f18dd-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="f18dd-307">此示例返回所有阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="f18dd-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="f18dd-308">有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-309">使用 PowerShell 查看租户允许/阻止列表中的允许批量邮件发件人域条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-310">若要查看租户允许/阻止列表中的允许批量邮件发件人域条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="f18dd-311">本示例返回所有允许的批量邮件发件人域。</span><span class="sxs-lookup"><span data-stu-id="f18dd-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="f18dd-312">本示例返回指定批量发件人域的信息。</span><span class="sxs-lookup"><span data-stu-id="f18dd-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="f18dd-313">有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-314">使用 PowerShell 查看租户允许/阻止列表中的允许或阻止欺骗发件人条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-315">若要查看租户允许/阻止列表中的欺骗性发件人条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="f18dd-316">此示例返回租户允许/阻止列表中所有欺骗性发件人条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="f18dd-317">此示例返回所有允许内部欺骗发件人条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="f18dd-318">此示例返回外部的所有阻止的欺骗发件人条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="f18dd-319">有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-320">使用 PowerShell 修改租户允许/阻止列表中的阻止文件和 URL 条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-321">若要修改租户允许/阻止列表中的阻止文件和 URL 条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="f18dd-322">此示例更改指定阻止 URL 条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="f18dd-323">有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-324">使用 PowerShell 修改租户允许/阻止列表中的允许批量邮件发件人域条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-325">若要修改租户允许/阻止列表中允许批量邮件发件人域条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="f18dd-326">本示例将指定允许批量邮件发件人域条目的过期时间更改为永不过期。</span><span class="sxs-lookup"><span data-stu-id="f18dd-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="f18dd-327">有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-328">使用 PowerShell 修改租户允许/阻止列表中的允许或阻止欺骗发件人条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-329">若要修改租户允许/阻止列表中的允许或阻止欺骗发件人条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="f18dd-330">本示例将欺骗性发件人条目从"允许"更改为"阻止"。</span><span class="sxs-lookup"><span data-stu-id="f18dd-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="f18dd-331">有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-332">使用 PowerShell 从租户允许/阻止列表中删除批量邮件发件人域、文件和域条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-333">若要从租户允许/阻止列表中删除允许批量邮件发件人域条目、阻止文件条目和阻止 URL 条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f18dd-334">此示例从租户允许/阻止列表中删除指定的阻止 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="f18dd-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f18dd-335">有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-336">使用 PowerShell 从租户允许/阻止列表中删除允许或阻止欺骗发件人条目</span><span class="sxs-lookup"><span data-stu-id="f18dd-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-337">若要从租户允许/阻止列表中删除允许或阻止欺骗发件人条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f18dd-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f18dd-338">有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="f18dd-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-339">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="f18dd-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f18dd-340">允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="f18dd-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f18dd-341">例如，不允许使用文件名 (，例如test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f18dd-342">不支持 Unicode，但 Punycode 支持。</span><span class="sxs-lookup"><span data-stu-id="f18dd-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f18dd-343">如果下列所有语句都为 true，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="f18dd-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="f18dd-344">主机名包含一个时间段。</span><span class="sxs-lookup"><span data-stu-id="f18dd-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="f18dd-345">在周期的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="f18dd-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f18dd-346">此期间右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="f18dd-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f18dd-347">例如， `t.co` 是允许的 `.com` ; `contoso.` 或者是不允许的。</span><span class="sxs-lookup"><span data-stu-id="f18dd-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f18dd-348">不隐含子路径。</span><span class="sxs-lookup"><span data-stu-id="f18dd-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="f18dd-349">例如， `contoso.com` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f18dd-350">在 () 允许使用通配符或\*通配符：</span><span class="sxs-lookup"><span data-stu-id="f18dd-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f18dd-351">左通配符后面必须后跟一个时间段，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="f18dd-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f18dd-352">例如， `*.contoso.com` 允许 ; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="f18dd-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f18dd-353">右通配符必须按照正斜杠 (/) 指定路径。</span><span class="sxs-lookup"><span data-stu-id="f18dd-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f18dd-354">例如， `contoso.com/*` 是允许的 `contoso.com*` ; `contoso.com/ab*` 或者是不允许的。</span><span class="sxs-lookup"><span data-stu-id="f18dd-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f18dd-355">右通配符不隐含所有子路径。</span><span class="sxs-lookup"><span data-stu-id="f18dd-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f18dd-356">例如， `contoso.com/*` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f18dd-357">`*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f18dd-358">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="f18dd-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f18dd-359">在下列 (提供了) ~ 字符：</span><span class="sxs-lookup"><span data-stu-id="f18dd-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f18dd-360">左波浪符表示域及其所有子域。</span><span class="sxs-lookup"><span data-stu-id="f18dd-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f18dd-361">例如， `~contoso.com` 包括 `contoso.com` `*.contoso.com` 和 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f18dd-362">包含协议（如 、 (）的 URL) 将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="f18dd-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f18dd-363">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="f18dd-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f18dd-364">引号 ("或") 无效字符。</span><span class="sxs-lookup"><span data-stu-id="f18dd-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f18dd-365">如果可能，URL 应包含所有重定向。</span><span class="sxs-lookup"><span data-stu-id="f18dd-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f18dd-366">URL 条目方案</span><span class="sxs-lookup"><span data-stu-id="f18dd-366">URL entry scenarios</span></span>

<span data-ttu-id="f18dd-367">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="f18dd-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f18dd-368">方案：无通配符</span><span class="sxs-lookup"><span data-stu-id="f18dd-368">Scenario: No wildcards</span></span>

<span data-ttu-id="f18dd-369">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f18dd-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f18dd-370">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f18dd-371">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="f18dd-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-372">abc-contoso.com</span></span>
  - <span data-ttu-id="f18dd-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f18dd-373">contoso.com/a</span></span>
  - <span data-ttu-id="f18dd-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="f18dd-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="f18dd-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f18dd-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-377">www.contoso.com</span></span>
  - <span data-ttu-id="f18dd-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f18dd-379">**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-379">**Block match**:</span></span>

  - <span data-ttu-id="f18dd-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-380">contoso.com</span></span>
  - <span data-ttu-id="f18dd-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f18dd-381">contoso.com/a</span></span>
  - <span data-ttu-id="f18dd-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="f18dd-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="f18dd-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f18dd-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-385">www.contoso.com</span></span>
  - <span data-ttu-id="f18dd-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f18dd-387">**阻止不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f18dd-388">方案：将通配符 (子域) </span><span class="sxs-lookup"><span data-stu-id="f18dd-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f18dd-389">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f18dd-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f18dd-390">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f18dd-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-391">www.contoso.com</span></span>
  - <span data-ttu-id="f18dd-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f18dd-393">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f18dd-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-394">123contoso.com</span></span>
  - <span data-ttu-id="f18dd-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-395">contoso.com</span></span>
  - <span data-ttu-id="f18dd-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="f18dd-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f18dd-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f18dd-398">方案：路径顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="f18dd-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f18dd-399">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f18dd-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f18dd-400">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f18dd-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f18dd-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="f18dd-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f18dd-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f18dd-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f18dd-404">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f18dd-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-405">contoso.com</span></span>
  - <span data-ttu-id="f18dd-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f18dd-406">contoso.com/a</span></span>
  - <span data-ttu-id="f18dd-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-407">www.contoso.com</span></span>
  - <span data-ttu-id="f18dd-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="f18dd-409">应用场景：左波浪符</span><span class="sxs-lookup"><span data-stu-id="f18dd-409">Scenario: Left tilde</span></span>

<span data-ttu-id="f18dd-410">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f18dd-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f18dd-411">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f18dd-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-412">contoso.com</span></span>
  - <span data-ttu-id="f18dd-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-413">www.contoso.com</span></span>
  - <span data-ttu-id="f18dd-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f18dd-415">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f18dd-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-416">123contoso.com</span></span>
  - <span data-ttu-id="f18dd-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f18dd-417">contoso.com/abc</span></span>
  - <span data-ttu-id="f18dd-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f18dd-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f18dd-419">应用场景：右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="f18dd-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f18dd-420">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f18dd-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f18dd-421">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f18dd-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f18dd-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f18dd-423">contoso.com/a</span></span>
  - <span data-ttu-id="f18dd-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f18dd-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f18dd-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f18dd-425">contoso.com/ab</span></span>
  - <span data-ttu-id="f18dd-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f18dd-426">contoso.com/b</span></span>
  - <span data-ttu-id="f18dd-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f18dd-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f18dd-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f18dd-428">contoso.com/ba</span></span>

- <span data-ttu-id="f18dd-429">**允许不匹配和\*\*\*\*阻止不匹配**：contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f18dd-430">应用场景：左通配符子域和右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="f18dd-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f18dd-431">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f18dd-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f18dd-432">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f18dd-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f18dd-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f18dd-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f18dd-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f18dd-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f18dd-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="f18dd-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f18dd-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f18dd-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f18dd-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f18dd-438">**允许不匹配和\*\*\*\*阻止不匹配**：contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f18dd-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f18dd-439">应用场景：左右波浪符</span><span class="sxs-lookup"><span data-stu-id="f18dd-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f18dd-440">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f18dd-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f18dd-441">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f18dd-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-442">contoso.com</span></span>
  - <span data-ttu-id="f18dd-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f18dd-443">contoso.com/a</span></span>
  - <span data-ttu-id="f18dd-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-444">www.contoso.com</span></span>
  - <span data-ttu-id="f18dd-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f18dd-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="f18dd-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f18dd-447">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f18dd-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-448">123contoso.com</span></span>
  - <span data-ttu-id="f18dd-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f18dd-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f18dd-450">方案：IP 地址</span><span class="sxs-lookup"><span data-stu-id="f18dd-450">Scenario: IP address</span></span>

<span data-ttu-id="f18dd-451">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f18dd-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f18dd-452">**允许匹配** 和 **阻止匹配**：1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f18dd-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f18dd-453">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f18dd-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f18dd-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="f18dd-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f18dd-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f18dd-456">具有右通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="f18dd-456">IP address with right wildcard</span></span>

<span data-ttu-id="f18dd-457">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f18dd-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f18dd-458">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f18dd-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f18dd-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="f18dd-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f18dd-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f18dd-461">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="f18dd-461">Examples of invalid entries</span></span>

<span data-ttu-id="f18dd-462">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="f18dd-462">The following entries are invalid:</span></span>

- <span data-ttu-id="f18dd-463">**域值缺失或无效**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f18dd-464">contoso</span><span class="sxs-lookup"><span data-stu-id="f18dd-464">contoso</span></span>
  - <span data-ttu-id="f18dd-465">\*.contoso。\*</span><span class="sxs-lookup"><span data-stu-id="f18dd-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="f18dd-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-466">\*.com</span></span>
  - <span data-ttu-id="f18dd-467">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="f18dd-467">\*.pdf</span></span>

- <span data-ttu-id="f18dd-468">**文本上的通配符或不带空格字符的通配符**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f18dd-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-469">\*contoso.com</span></span>
  - <span data-ttu-id="f18dd-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f18dd-470">contoso.com\*</span></span>
  - <span data-ttu-id="f18dd-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f18dd-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="f18dd-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f18dd-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="f18dd-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f18dd-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="f18dd-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f18dd-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="f18dd-475">**具有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f18dd-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f18dd-476">contoso.com:443</span></span>
  - <span data-ttu-id="f18dd-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f18dd-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="f18dd-478">**非描述性通配符**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f18dd-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f18dd-479">\*.\*</span></span>

- <span data-ttu-id="f18dd-480">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="f18dd-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f18dd-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-481">conto\*so.com</span></span>
  - <span data-ttu-id="f18dd-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-482">conto~so.com</span></span>

- <span data-ttu-id="f18dd-483">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="f18dd-483">**Double wildcards**</span></span>

  - <span data-ttu-id="f18dd-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f18dd-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f18dd-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f18dd-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f18dd-486">租户允许/阻止列表中欺骗发件人条目的域对语法</span><span class="sxs-lookup"><span data-stu-id="f18dd-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f18dd-487">租户允许/阻止列表中欺骗发件人的域对使用以下语法： `<Spoofed user>, <Sending infrastructure>` 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="f18dd-488">**欺骗用户**：此值涉及在电子邮件客户端的"来源"框中显示的欺骗用户的电子邮件地址。 </span><span class="sxs-lookup"><span data-stu-id="f18dd-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="f18dd-489">此地址也称为 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="f18dd-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="f18dd-490">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="f18dd-490">Valid values include:</span></span>
  - <span data-ttu-id="f18dd-491">个人电子邮件地址 (例如，chris@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="f18dd-492">电子邮件域 (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="f18dd-493">通配符 (例如 \* ，) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="f18dd-494">**发送基础结构**：此值指示来自欺骗用户的邮件来源。</span><span class="sxs-lookup"><span data-stu-id="f18dd-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="f18dd-495">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="f18dd-495">Valid values include:</span></span>
  - <span data-ttu-id="f18dd-496">反向 DNS 查找中的域 (PTR 记录) 源电子邮件服务器的 IP 地址的 IP 地址 (例如，fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="f18dd-497">如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="f18dd-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="f18dd-498">下面是用于标识欺骗性发件人的有效域对的一些示例：</span><span class="sxs-lookup"><span data-stu-id="f18dd-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="f18dd-499">添加域对仅允许或阻止欺骗用户 *和发送* 基础结构的组合。</span><span class="sxs-lookup"><span data-stu-id="f18dd-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="f18dd-500">它不允许来自任何来源的欺骗用户的电子邮件，也不允许来自任何欺骗用户的发送基础结构源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f18dd-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="f18dd-501">例如，为以下域对添加允许条目：</span><span class="sxs-lookup"><span data-stu-id="f18dd-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="f18dd-502">**域**： gmail.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="f18dd-503">**基础结构**：tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="f18dd-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="f18dd-504">仅允许 *来自该域* 的邮件和发送基础结构对进行欺骗。</span><span class="sxs-lookup"><span data-stu-id="f18dd-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="f18dd-505">不允许其他发件人 gmail.com 欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="f18dd-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="f18dd-506">来自来自其他域的其他域中发件人 tms.mx.com 反欺骗智能进行检查。</span><span class="sxs-lookup"><span data-stu-id="f18dd-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
