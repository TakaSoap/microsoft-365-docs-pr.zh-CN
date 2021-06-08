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
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809175"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-103">管理租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="a4006-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a4006-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="a4006-104">**Applies to**</span></span>
- [<span data-ttu-id="a4006-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a4006-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a4006-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="a4006-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a4006-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4006-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="a4006-108">本文中所述的功能在预览版中，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="a4006-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="a4006-109">如果你的组织没有本文中所述的欺骗功能，请参阅使用欺骗智能策略和 EOP 中的欺骗智能见解管理欺骗发件人中的旧版欺骗 [管理体验](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="a4006-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="a4006-110">目前，你 **无法** 配置租户允许/阻止列表中的允许 URL 或文件项。</span><span class="sxs-lookup"><span data-stu-id="a4006-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="a4006-111">在Microsoft 365没有邮箱的 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，您可能会与 EOP 筛选裁定不一致。</span><span class="sxs-lookup"><span data-stu-id="a4006-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="a4006-112">例如，一条好邮件可能标记为 (误报) ，或者可能允许错误消息通过 (漏报) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="a4006-113">安全与合规中心中的租户&/阻止列表提供了一种手动覆盖Microsoft 365裁定的方法。</span><span class="sxs-lookup"><span data-stu-id="a4006-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="a4006-114">租户允许/阻止列表在邮件流期间和用户单击时使用。</span><span class="sxs-lookup"><span data-stu-id="a4006-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="a4006-115">可以指定以下类型的替代：</span><span class="sxs-lookup"><span data-stu-id="a4006-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="a4006-116">要阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="a4006-116">URLs to block.</span></span>
- <span data-ttu-id="a4006-117">要阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="a4006-117">Files to block.</span></span>
- <span data-ttu-id="a4006-118">允许或阻止欺骗发件人。</span><span class="sxs-lookup"><span data-stu-id="a4006-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="a4006-119">如果替代欺骗智能见解中的允许或阻止裁定[](learn-about-spoof-intelligence.md)，欺骗发件人将成为仅出现在租户允许/阻止列表中的"欺骗"选项卡上的手动允许或阻止条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="a4006-120">在欺骗智能检测到欺骗性发件人之前，还可以在此处手动创建允许或阻止欺骗发件人的允许或阻止条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="a4006-121">本文介绍如何在安全& 合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置租户允许/阻止Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a4006-122">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="a4006-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a4006-123">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="a4006-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a4006-124">若要直接转到租户 **允许/阻止列表** 页面，请使用 <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="a4006-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="a4006-125">使用文件的 SHA256 哈希值指定文件。</span><span class="sxs-lookup"><span data-stu-id="a4006-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="a4006-126">若要在命令提示符中查找文件的 SHA256 哈希Windows，在命令提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a4006-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="a4006-127">示例值为 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="a4006-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="a4006-128">不支持感知哈希 (pHash) 值。</span><span class="sxs-lookup"><span data-stu-id="a4006-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="a4006-129">本文稍后的租户允许/阻止列表一节的 [URL](#url-syntax-for-the-tenant-allowblock-list) 语法中介绍了可用的 URL 值。</span><span class="sxs-lookup"><span data-stu-id="a4006-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="a4006-130">租户允许/阻止列表允许最多 500 个 URL 条目和 500 个文件哈希条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="a4006-131">每个条目的最大字符数为：</span><span class="sxs-lookup"><span data-stu-id="a4006-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="a4006-132">文件哈希 = 64</span><span class="sxs-lookup"><span data-stu-id="a4006-132">File hashes = 64</span></span>
  - <span data-ttu-id="a4006-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="a4006-133">URL = 250</span></span>

- <span data-ttu-id="a4006-134">条目应在 30 分钟内处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a4006-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="a4006-135">默认情况下，租户允许/阻止列表中的条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="a4006-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="a4006-136">可以指定日期或将其设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="a4006-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="a4006-137">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a4006-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a4006-138">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a4006-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a4006-139">在 Exchange Online 网站中 分配 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="a4006-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a4006-140">**URL 和文件**：</span><span class="sxs-lookup"><span data-stu-id="a4006-140">**URLs and files**:</span></span>
    - <span data-ttu-id="a4006-141">若要在租户允许/阻止列表中添加和删除值，你需要是组织管理或安全 **管理员角色\*\*\*\*组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="a4006-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="a4006-142">若要对租户允许/阻止列表进行只读访问，你需要是全局读取 **者** 或安全读者 **角色组的成员** 。</span><span class="sxs-lookup"><span data-stu-id="a4006-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="a4006-143">**欺骗**：以下组合之一：</span><span class="sxs-lookup"><span data-stu-id="a4006-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="a4006-144">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="a4006-144">**Organization Management**</span></span>
    - <span data-ttu-id="a4006-145">**安全管理员**<u>和</u>**仅查看配置** 或 **仅查看组织管理**。</span><span class="sxs-lookup"><span data-stu-id="a4006-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="a4006-146">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="a4006-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="a4006-147">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="a4006-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a4006-148">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a4006-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="a4006-149">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="a4006-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-150">使用安全&中心在租户允许/阻止列表中创建阻止 URL 条目</span><span class="sxs-lookup"><span data-stu-id="a4006-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a4006-151">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="a4006-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a4006-152">在" **租户允许/阻止列表** "页上，验证 **"URL"** 选项卡是否被选中，然后单击"阻止 **"**</span><span class="sxs-lookup"><span data-stu-id="a4006-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="a4006-153">在 **出现的"阻止 URL"** 飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a4006-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a4006-154">**添加要阻止的 URL：** 每行输入一个 URL，最多输入 20 个。</span><span class="sxs-lookup"><span data-stu-id="a4006-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="a4006-155">有关 URL 条目的语法的详细信息，请参阅本文稍后介绍的租户 [允许/阻止列表的 URL](#url-syntax-for-the-tenant-allowblock-list) 语法部分。</span><span class="sxs-lookup"><span data-stu-id="a4006-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="a4006-156">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="a4006-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a4006-157">验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="a4006-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="a4006-158">或</span><span class="sxs-lookup"><span data-stu-id="a4006-158">or</span></span>

     - <span data-ttu-id="a4006-159">将开关移到右侧，将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="a4006-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="a4006-161">.</span><span class="sxs-lookup"><span data-stu-id="a4006-161">.</span></span>

   - <span data-ttu-id="a4006-162">**可选说明**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="a4006-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a4006-163">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a4006-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-164">使用安全&中心在租户允许/阻止列表中创建阻止文件条目</span><span class="sxs-lookup"><span data-stu-id="a4006-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a4006-165">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="a4006-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a4006-166">在"**租户允许/阻止列表"** 页上，选择"**文件"** 选项卡，然后单击"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="a4006-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="a4006-167">在 **"添加文件以阻止** 出现的飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a4006-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a4006-168">**添加文件哈希**：每行输入一个 SHA256 哈希值，最多 20 个。</span><span class="sxs-lookup"><span data-stu-id="a4006-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a4006-169">**永不过期**：执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="a4006-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a4006-170">验证是否关闭该设置 (关闭) 并使用"过期时间"框指定条目 ![ ](../../media/scc-toggle-off.png) 的到期日期。 </span><span class="sxs-lookup"><span data-stu-id="a4006-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a4006-171">或</span><span class="sxs-lookup"><span data-stu-id="a4006-171">or</span></span>

     - <span data-ttu-id="a4006-172">将开关移到右侧，将条目配置为永不过期：</span><span class="sxs-lookup"><span data-stu-id="a4006-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![切换开关打开](../../media/scc-toggle-on.png)<span data-ttu-id="a4006-174">.</span><span class="sxs-lookup"><span data-stu-id="a4006-174">.</span></span>

   - <span data-ttu-id="a4006-175">**可选说明**：输入条目的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="a4006-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a4006-176">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a4006-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-177">使用安全&中心在租户允许/阻止列表中创建允许或阻止欺骗发件人条目</span><span class="sxs-lookup"><span data-stu-id="a4006-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-178">**注意**：</span><span class="sxs-lookup"><span data-stu-id="a4006-178">**Notes**:</span></span>

- <span data-ttu-id="a4006-179">仅 _明确_ 允许或阻止欺骗用户和域对中定义的发送基础结构的组合。</span><span class="sxs-lookup"><span data-stu-id="a4006-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="a4006-180">为域对配置允许或阻止条目时，来自该域对的邮件将不再显示在欺骗智能见解中。</span><span class="sxs-lookup"><span data-stu-id="a4006-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="a4006-181">欺骗性发件人的条目永不过期。</span><span class="sxs-lookup"><span data-stu-id="a4006-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="a4006-182">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="a4006-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a4006-183">在"**租户允许/阻止列表"** 页上，选择"**欺骗"** 选项卡，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a4006-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="a4006-184">在出现的 **"添加新域对** "飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a4006-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a4006-185">**使用通配符添加新域对**：每行输入一个域对，最多输入 20 个域对。</span><span class="sxs-lookup"><span data-stu-id="a4006-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="a4006-186">有关欺骗性发件人条目的语法的详细信息，请参阅本文稍后的租户允许 [/](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 阻止列表部分中的欺骗性发件人条目的域对语法。</span><span class="sxs-lookup"><span data-stu-id="a4006-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="a4006-187">**欺骗类型**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="a4006-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="a4006-188">**内部**：欺骗性发件人位于组织所属的域中， ([接受的) 。](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="a4006-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="a4006-189">**外部**：欺骗性发件人位于外部域中。</span><span class="sxs-lookup"><span data-stu-id="a4006-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="a4006-190">**操作**：选择 **"允许"** 或"**阻止"。**</span><span class="sxs-lookup"><span data-stu-id="a4006-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="a4006-191">完成后，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a4006-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-192">使用安全&中心查看租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a4006-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a4006-193">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="a4006-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a4006-194">选择您想要的选项卡。</span><span class="sxs-lookup"><span data-stu-id="a4006-194">Select the tab you want.</span></span> <span data-ttu-id="a4006-195">可用的列取决于所选的选项卡：</span><span class="sxs-lookup"><span data-stu-id="a4006-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="a4006-196">**URL：**</span><span class="sxs-lookup"><span data-stu-id="a4006-196">**URLs**:</span></span>
     - <span data-ttu-id="a4006-197">**值**：URL。</span><span class="sxs-lookup"><span data-stu-id="a4006-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="a4006-198">**操作**：值 **Block**。</span><span class="sxs-lookup"><span data-stu-id="a4006-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="a4006-199">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-199">**Last updated date**</span></span>
     - <span data-ttu-id="a4006-200">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-200">**Expiration date**</span></span>
     - <span data-ttu-id="a4006-201">**注意**</span><span class="sxs-lookup"><span data-stu-id="a4006-201">**Note**</span></span>

   - <span data-ttu-id="a4006-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="a4006-202">**Files**</span></span>
     - <span data-ttu-id="a4006-203">**值**：文件哈希。</span><span class="sxs-lookup"><span data-stu-id="a4006-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="a4006-204">**操作**：值 **Block**。</span><span class="sxs-lookup"><span data-stu-id="a4006-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="a4006-205">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-205">**Last updated date**</span></span>
     - <span data-ttu-id="a4006-206">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-206">**Expiration date**</span></span>
     - <span data-ttu-id="a4006-207">**注意**</span><span class="sxs-lookup"><span data-stu-id="a4006-207">**Note**</span></span>

   - <span data-ttu-id="a4006-208">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="a4006-208">**Spoofing**</span></span>
     - <span data-ttu-id="a4006-209">**欺骗用户**</span><span class="sxs-lookup"><span data-stu-id="a4006-209">**Spoofed user**</span></span>
     - <span data-ttu-id="a4006-210">**发送基础结构**</span><span class="sxs-lookup"><span data-stu-id="a4006-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="a4006-211">**欺骗类型**：值 **Internal** 或 **External**。</span><span class="sxs-lookup"><span data-stu-id="a4006-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="a4006-212">**操作**：值 **Block** 或 **Allow**。</span><span class="sxs-lookup"><span data-stu-id="a4006-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="a4006-213">可以单击列标题以按升序或降序排序。</span><span class="sxs-lookup"><span data-stu-id="a4006-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="a4006-214">可以单击 **"分组** "对结果进行分组。</span><span class="sxs-lookup"><span data-stu-id="a4006-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="a4006-215">可用的值取决于所选的选项卡：</span><span class="sxs-lookup"><span data-stu-id="a4006-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="a4006-216">**URL**：可以按操作 对结果 **进行分组**。</span><span class="sxs-lookup"><span data-stu-id="a4006-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="a4006-217">**文件**：可以按操作 对结果 **进行分组**。</span><span class="sxs-lookup"><span data-stu-id="a4006-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="a4006-218">**BCL 绕过的** 发件人域 **：** 此选项卡上未提供组。</span><span class="sxs-lookup"><span data-stu-id="a4006-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="a4006-219">**欺骗：** 你可以按操作或欺骗 **类型\*\*\*\*对结果进行分组**。</span><span class="sxs-lookup"><span data-stu-id="a4006-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="a4006-220">单击 **"搜索**"，输入值的全部或一部分，然后按 Enter 查找特定值。</span><span class="sxs-lookup"><span data-stu-id="a4006-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="a4006-221">完成后，单击"清除搜索 **""** ![ 清除搜索图标 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) "。</span><span class="sxs-lookup"><span data-stu-id="a4006-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="a4006-222">单击 **"筛选** "筛选结果。</span><span class="sxs-lookup"><span data-stu-id="a4006-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="a4006-223">显示在"筛选器 **"飞出** 控件中的可用值取决于所选的选项卡：</span><span class="sxs-lookup"><span data-stu-id="a4006-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="a4006-224">**URL**</span><span class="sxs-lookup"><span data-stu-id="a4006-224">**URLs**</span></span>
     - <span data-ttu-id="a4006-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="a4006-225">**Action**</span></span>
     - <span data-ttu-id="a4006-226">**永不过期**</span><span class="sxs-lookup"><span data-stu-id="a4006-226">**Never expire**</span></span>
     - <span data-ttu-id="a4006-227">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-227">**Last updated date**</span></span>
     - <span data-ttu-id="a4006-228">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-228">**Expiration date**</span></span>

   - <span data-ttu-id="a4006-229">**Files**</span><span class="sxs-lookup"><span data-stu-id="a4006-229">**Files**</span></span>
     - <span data-ttu-id="a4006-230">**Action**</span><span class="sxs-lookup"><span data-stu-id="a4006-230">**Action**</span></span>
     - <span data-ttu-id="a4006-231">**永不过期**</span><span class="sxs-lookup"><span data-stu-id="a4006-231">**Never expire**</span></span>
     - <span data-ttu-id="a4006-232">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-232">**Last updated date**</span></span>
     - <span data-ttu-id="a4006-233">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-233">**Expiration date**</span></span>

   - <span data-ttu-id="a4006-234">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="a4006-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="a4006-235">**永不过期**</span><span class="sxs-lookup"><span data-stu-id="a4006-235">**Never expire**</span></span>
     - <span data-ttu-id="a4006-236">**上次更新日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-236">**Last updated date**</span></span>
     - <span data-ttu-id="a4006-237">**到期日期**</span><span class="sxs-lookup"><span data-stu-id="a4006-237">**Expiration date**</span></span>

   - <span data-ttu-id="a4006-238">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="a4006-238">**Spoofing**</span></span>
     - <span data-ttu-id="a4006-239">**Action**</span><span class="sxs-lookup"><span data-stu-id="a4006-239">**Action**</span></span>
     - <span data-ttu-id="a4006-240">**欺骗类型**</span><span class="sxs-lookup"><span data-stu-id="a4006-240">**Spoof type**</span></span>

   <span data-ttu-id="a4006-241">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="a4006-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="a4006-242">若要清除现有筛选器，请单击 **"筛选器"，** 在出现的"筛选器"飞出中，单击"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="a4006-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-243">使用安全&中心修改租户允许/阻止列表中的条目</span><span class="sxs-lookup"><span data-stu-id="a4006-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a4006-244">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="a4006-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a4006-245">选择包含要修改的条目类型的选项卡：</span><span class="sxs-lookup"><span data-stu-id="a4006-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="a4006-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="a4006-246">**URLs**</span></span>
   - <span data-ttu-id="a4006-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="a4006-247">**Files**</span></span>
   - <span data-ttu-id="a4006-248">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="a4006-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="a4006-249">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="a4006-249">**Spoofing**</span></span>

3. <span data-ttu-id="a4006-250">选择要修改的条目，然后单击"编辑 **编辑"** ![ 图标 ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="a4006-251">可以在出现的飞出控件中修改的值取决于您在上一步中所选的选项卡：</span><span class="sxs-lookup"><span data-stu-id="a4006-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="a4006-252">**URL**</span><span class="sxs-lookup"><span data-stu-id="a4006-252">**URLs**</span></span>
     - <span data-ttu-id="a4006-253">**永不过期** 和/或到期日期。</span><span class="sxs-lookup"><span data-stu-id="a4006-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="a4006-254">**可选注释**</span><span class="sxs-lookup"><span data-stu-id="a4006-254">**Optional note**</span></span>

   - <span data-ttu-id="a4006-255">**Files**</span><span class="sxs-lookup"><span data-stu-id="a4006-255">**Files**</span></span>
     - <span data-ttu-id="a4006-256">**永不过期** 和/或到期日期。</span><span class="sxs-lookup"><span data-stu-id="a4006-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="a4006-257">**可选注释**</span><span class="sxs-lookup"><span data-stu-id="a4006-257">**Optional note**</span></span>

   - <span data-ttu-id="a4006-258">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="a4006-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="a4006-259">**永不过期** 和/或到期日期。</span><span class="sxs-lookup"><span data-stu-id="a4006-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="a4006-260">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="a4006-260">**Spoofing**</span></span>
     - <span data-ttu-id="a4006-261">**操作**：可以将值更改为"允许 **"或**"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="a4006-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="a4006-262">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="a4006-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-263">使用安全&中心从租户允许/阻止列表中删除条目</span><span class="sxs-lookup"><span data-stu-id="a4006-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a4006-264">在安全与&中心，转到威胁 **管理** \> **策略** \> **租户允许/阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="a4006-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a4006-265">选择包含要删除的条目类型的选项卡：</span><span class="sxs-lookup"><span data-stu-id="a4006-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="a4006-266">**URL**</span><span class="sxs-lookup"><span data-stu-id="a4006-266">**URLs**</span></span>
   - <span data-ttu-id="a4006-267">**Files**</span><span class="sxs-lookup"><span data-stu-id="a4006-267">**Files**</span></span>
   - <span data-ttu-id="a4006-268">**用于 BCL 绕过的发件人域**</span><span class="sxs-lookup"><span data-stu-id="a4006-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="a4006-269">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="a4006-269">**Spoofing**</span></span>

3. <span data-ttu-id="a4006-270">选择要删除的条目，然后单击"删除 **删除图标** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) "。</span><span class="sxs-lookup"><span data-stu-id="a4006-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="a4006-271">在出现的警告对话框中，单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="a4006-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-272">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="a4006-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-273">使用 PowerShell 将阻止文件或 URL 条目添加到租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="a4006-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-274">若要在租户允许/阻止列表中添加阻止文件或 URL 条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a4006-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="a4006-275">本示例为永不过期的指定文件添加阻止文件条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="a4006-276">此示例为 contoso.com 及其所有子域（例如， (、contoso.com、www.contoso.com 和 xyz.abc.contoso.com) ）添加一个阻止 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="a4006-277">由于我们没有使用 ExpirationDate 或 NoExpiration 参数，因此条目将在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="a4006-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="a4006-278">有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a4006-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-279">使用 PowerShell 将允许或阻止欺骗发件人条目添加到租户允许/阻止列表</span><span class="sxs-lookup"><span data-stu-id="a4006-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-280">若要在租户允许/阻止列表中添加欺骗性发件人条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a4006-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="a4006-281">有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="a4006-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-282">使用 PowerShell 查看租户允许/阻止列表中的阻止文件或 URL 条目</span><span class="sxs-lookup"><span data-stu-id="a4006-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-283">若要查看租户允许/阻止列表中的阻止文件或 URL 条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a4006-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="a4006-284">此示例返回指定文件哈希值的信息。</span><span class="sxs-lookup"><span data-stu-id="a4006-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="a4006-285">此示例返回所有阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="a4006-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="a4006-286">有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a4006-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-287">使用 PowerShell 查看租户允许/阻止列表中的允许或阻止欺骗发件人条目</span><span class="sxs-lookup"><span data-stu-id="a4006-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-288">若要查看租户允许/阻止列表中的欺骗性发件人条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a4006-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="a4006-289">此示例返回租户允许/阻止列表中所有欺骗性发件人条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="a4006-290">此示例返回所有允许内部欺骗发件人条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="a4006-291">此示例返回外部的所有阻止的欺骗发件人条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="a4006-292">有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="a4006-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-293">使用 PowerShell 修改租户允许/阻止列表中的阻止文件和 URL 条目</span><span class="sxs-lookup"><span data-stu-id="a4006-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-294">若要修改租户允许/阻止列表中的阻止文件和 URL 条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a4006-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="a4006-295">此示例更改指定阻止 URL 条目的到期日期。</span><span class="sxs-lookup"><span data-stu-id="a4006-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="a4006-296">有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a4006-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-297">使用 PowerShell 修改租户允许/阻止列表中的允许或阻止欺骗发件人条目</span><span class="sxs-lookup"><span data-stu-id="a4006-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-298">若要修改租户允许/阻止列表中的允许或阻止欺骗发件人条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a4006-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="a4006-299">本示例将欺骗性发件人条目从"允许"更改为"阻止"。</span><span class="sxs-lookup"><span data-stu-id="a4006-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="a4006-300">有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="a4006-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-301">使用 PowerShell 从租户允许/阻止列表中删除 URL 或文件条目</span><span class="sxs-lookup"><span data-stu-id="a4006-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-302">若要从租户允许/阻止列表中删除文件和 URL 条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a4006-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a4006-303">此示例从租户允许/阻止列表中删除指定的阻止 URL 条目。</span><span class="sxs-lookup"><span data-stu-id="a4006-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="a4006-304">有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="a4006-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-305">使用 PowerShell 从租户允许/阻止列表中删除允许或阻止欺骗发件人条目</span><span class="sxs-lookup"><span data-stu-id="a4006-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-306">若要从租户允许/阻止列表中删除允许或阻止欺骗发件人条目，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a4006-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a4006-307">有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="a4006-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-308">租户允许/阻止列表的 URL 语法</span><span class="sxs-lookup"><span data-stu-id="a4006-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="a4006-309">允许 IP4v 和 IPv6 地址，但不允许 TCP/UDP 端口。</span><span class="sxs-lookup"><span data-stu-id="a4006-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="a4006-310">例如，不允许使用文件名 (，例如test.pdf) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="a4006-311">不支持 Unicode，但 Punycode 支持。</span><span class="sxs-lookup"><span data-stu-id="a4006-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="a4006-312">如果下列所有语句都为 true，则允许使用主机名：</span><span class="sxs-lookup"><span data-stu-id="a4006-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="a4006-313">主机名包含一个时间段。</span><span class="sxs-lookup"><span data-stu-id="a4006-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="a4006-314">在周期的左侧至少有一个字符。</span><span class="sxs-lookup"><span data-stu-id="a4006-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="a4006-315">此期间右侧至少有两个字符。</span><span class="sxs-lookup"><span data-stu-id="a4006-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="a4006-316">例如， `t.co` 是允许的 `.com` ; `contoso.` 或者是不允许的。</span><span class="sxs-lookup"><span data-stu-id="a4006-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="a4006-317">不隐含子路径。</span><span class="sxs-lookup"><span data-stu-id="a4006-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="a4006-318">例如， `contoso.com` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a4006-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="a4006-319">在 () 允许使用通配符或\*通配符：</span><span class="sxs-lookup"><span data-stu-id="a4006-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="a4006-320">左通配符后面必须后跟一个时间段，以指定子域。</span><span class="sxs-lookup"><span data-stu-id="a4006-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="a4006-321">例如， `*.contoso.com` 允许 ; `*contoso.com` 不允许。</span><span class="sxs-lookup"><span data-stu-id="a4006-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="a4006-322">右通配符必须按照正斜杠 (/) 指定路径。</span><span class="sxs-lookup"><span data-stu-id="a4006-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="a4006-323">例如， `contoso.com/*` 是允许的 `contoso.com*` ; `contoso.com/ab*` 或者是不允许的。</span><span class="sxs-lookup"><span data-stu-id="a4006-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="a4006-324">右通配符不隐含所有子路径。</span><span class="sxs-lookup"><span data-stu-id="a4006-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="a4006-325">例如， `contoso.com/*` 不包括 `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="a4006-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="a4006-326">`*.com*` 无效 (不可解决的域，并且右通配符不遵循正斜杠) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="a4006-327">IP 地址中不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="a4006-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="a4006-328">在下列 (提供了) ~ 字符：</span><span class="sxs-lookup"><span data-stu-id="a4006-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="a4006-329">左波浪符表示域及其所有子域。</span><span class="sxs-lookup"><span data-stu-id="a4006-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="a4006-330">例如， `~contoso.com` 包括 `contoso.com` `*.contoso.com` 和 。</span><span class="sxs-lookup"><span data-stu-id="a4006-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="a4006-331">包含协议（如 、 (）的 URL) 将失败，因为 URL 条目 `http://` `https://` `ftp://` 适用于所有协议。</span><span class="sxs-lookup"><span data-stu-id="a4006-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="a4006-332">不支持或不需要用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="a4006-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="a4006-333">引号 ("或") 无效字符。</span><span class="sxs-lookup"><span data-stu-id="a4006-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="a4006-334">如果可能，URL 应包含所有重定向。</span><span class="sxs-lookup"><span data-stu-id="a4006-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="a4006-335">URL 条目方案</span><span class="sxs-lookup"><span data-stu-id="a4006-335">URL entry scenarios</span></span>

<span data-ttu-id="a4006-336">以下各节介绍了有效的 URL 条目及其结果。</span><span class="sxs-lookup"><span data-stu-id="a4006-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="a4006-337">方案：无通配符</span><span class="sxs-lookup"><span data-stu-id="a4006-337">Scenario: No wildcards</span></span>

<span data-ttu-id="a4006-338">**条目**： `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a4006-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="a4006-339">**允许匹配**： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="a4006-340">**允许不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="a4006-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-341">abc-contoso.com</span></span>
  - <span data-ttu-id="a4006-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a4006-342">contoso.com/a</span></span>
  - <span data-ttu-id="a4006-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="a4006-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="a4006-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a4006-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-346">www.contoso.com</span></span>
  - <span data-ttu-id="a4006-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a4006-348">**阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-348">**Block match**:</span></span>

  - <span data-ttu-id="a4006-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-349">contoso.com</span></span>
  - <span data-ttu-id="a4006-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a4006-350">contoso.com/a</span></span>
  - <span data-ttu-id="a4006-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="a4006-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="a4006-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a4006-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-354">www.contoso.com</span></span>
  - <span data-ttu-id="a4006-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a4006-356">**阻止不匹配**： abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="a4006-357">方案：将通配符 (子域) </span><span class="sxs-lookup"><span data-stu-id="a4006-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="a4006-358">**条目**： `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a4006-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="a4006-359">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a4006-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-360">www.contoso.com</span></span>
  - <span data-ttu-id="a4006-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a4006-362">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a4006-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-363">123contoso.com</span></span>
  - <span data-ttu-id="a4006-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-364">contoso.com</span></span>
  - <span data-ttu-id="a4006-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="a4006-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a4006-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="a4006-367">方案：路径顶部的右通配符</span><span class="sxs-lookup"><span data-stu-id="a4006-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="a4006-368">**条目**： `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="a4006-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="a4006-369">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a4006-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="a4006-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="a4006-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a4006-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a4006-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="a4006-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="a4006-373">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a4006-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-374">contoso.com</span></span>
  - <span data-ttu-id="a4006-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a4006-375">contoso.com/a</span></span>
  - <span data-ttu-id="a4006-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-376">www.contoso.com</span></span>
  - <span data-ttu-id="a4006-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="a4006-378">应用场景：左波浪符</span><span class="sxs-lookup"><span data-stu-id="a4006-378">Scenario: Left tilde</span></span>

<span data-ttu-id="a4006-379">**条目**： `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a4006-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="a4006-380">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a4006-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-381">contoso.com</span></span>
  - <span data-ttu-id="a4006-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-382">www.contoso.com</span></span>
  - <span data-ttu-id="a4006-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a4006-384">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a4006-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-385">123contoso.com</span></span>
  - <span data-ttu-id="a4006-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a4006-386">contoso.com/abc</span></span>
  - <span data-ttu-id="a4006-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a4006-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="a4006-388">应用场景：右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="a4006-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="a4006-389">**条目**： `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a4006-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="a4006-390">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a4006-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a4006-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="a4006-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a4006-392">contoso.com/a</span></span>
  - <span data-ttu-id="a4006-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a4006-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a4006-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a4006-394">contoso.com/ab</span></span>
  - <span data-ttu-id="a4006-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a4006-395">contoso.com/b</span></span>
  - <span data-ttu-id="a4006-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a4006-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a4006-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a4006-397">contoso.com/ba</span></span>

- <span data-ttu-id="a4006-398">**允许不匹配和\*\*\*\*阻止不匹配**：contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="a4006-399">应用场景：左通配符子域和右通配符后缀</span><span class="sxs-lookup"><span data-stu-id="a4006-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="a4006-400">**条目**： `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a4006-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="a4006-401">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a4006-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a4006-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="a4006-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a4006-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a4006-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a4006-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="a4006-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a4006-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a4006-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a4006-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="a4006-407">**允许不匹配和\*\*\*\*阻止不匹配**：contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a4006-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="a4006-408">应用场景：左右波浪符</span><span class="sxs-lookup"><span data-stu-id="a4006-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="a4006-409">**条目**： `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="a4006-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="a4006-410">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a4006-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-411">contoso.com</span></span>
  - <span data-ttu-id="a4006-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a4006-412">contoso.com/a</span></span>
  - <span data-ttu-id="a4006-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-413">www.contoso.com</span></span>
  - <span data-ttu-id="a4006-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a4006-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="a4006-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a4006-416">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a4006-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-417">123contoso.com</span></span>
  - <span data-ttu-id="a4006-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="a4006-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="a4006-419">方案：IP 地址</span><span class="sxs-lookup"><span data-stu-id="a4006-419">Scenario: IP address</span></span>

<span data-ttu-id="a4006-420">**条目**： `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="a4006-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="a4006-421">**允许匹配** 和 **阻止匹配**：1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a4006-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="a4006-422">**允许不匹配和\*\*\*\*阻止不匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a4006-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a4006-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="a4006-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a4006-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="a4006-425">具有右通配符的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="a4006-425">IP address with right wildcard</span></span>

<span data-ttu-id="a4006-426">**条目**： `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="a4006-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="a4006-427">**允许匹配** 和 **阻止匹配**：</span><span class="sxs-lookup"><span data-stu-id="a4006-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a4006-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="a4006-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="a4006-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="a4006-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="a4006-430">无效条目的示例</span><span class="sxs-lookup"><span data-stu-id="a4006-430">Examples of invalid entries</span></span>

<span data-ttu-id="a4006-431">以下条目无效：</span><span class="sxs-lookup"><span data-stu-id="a4006-431">The following entries are invalid:</span></span>

- <span data-ttu-id="a4006-432">**域值缺失或无效**：</span><span class="sxs-lookup"><span data-stu-id="a4006-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="a4006-433">contoso</span><span class="sxs-lookup"><span data-stu-id="a4006-433">contoso</span></span>
  - <span data-ttu-id="a4006-434">\*.contoso。\*</span><span class="sxs-lookup"><span data-stu-id="a4006-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="a4006-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="a4006-435">\*.com</span></span>
  - <span data-ttu-id="a4006-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="a4006-436">\*.pdf</span></span>

- <span data-ttu-id="a4006-437">**文本上的通配符或不带空格字符的通配符**：</span><span class="sxs-lookup"><span data-stu-id="a4006-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="a4006-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="a4006-438">\*contoso.com</span></span>
  - <span data-ttu-id="a4006-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="a4006-439">contoso.com\*</span></span>
  - <span data-ttu-id="a4006-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a4006-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="a4006-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="a4006-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="a4006-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="a4006-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="a4006-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="a4006-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="a4006-444">**具有端口的 IP 地址**：</span><span class="sxs-lookup"><span data-stu-id="a4006-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="a4006-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="a4006-445">contoso.com:443</span></span>
  - <span data-ttu-id="a4006-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="a4006-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="a4006-447">**非描述性通配符**：</span><span class="sxs-lookup"><span data-stu-id="a4006-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="a4006-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="a4006-448">\*.\*</span></span>

- <span data-ttu-id="a4006-449">**中间通配符**：</span><span class="sxs-lookup"><span data-stu-id="a4006-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="a4006-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="a4006-450">conto\*so.com</span></span>
  - <span data-ttu-id="a4006-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="a4006-451">conto~so.com</span></span>

- <span data-ttu-id="a4006-452">**双通配符**</span><span class="sxs-lookup"><span data-stu-id="a4006-452">**Double wildcards**</span></span>

  - <span data-ttu-id="a4006-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="a4006-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="a4006-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="a4006-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a4006-455">租户允许/阻止列表中欺骗发件人条目的域对语法</span><span class="sxs-lookup"><span data-stu-id="a4006-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a4006-456">租户允许/阻止列表中欺骗发件人的域对使用以下语法： `<Spoofed user>, <Sending infrastructure>` 。</span><span class="sxs-lookup"><span data-stu-id="a4006-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="a4006-457">**欺骗用户**：此值涉及在电子邮件客户端的"来源"框中显示的欺骗用户的电子邮件地址。 </span><span class="sxs-lookup"><span data-stu-id="a4006-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="a4006-458">此地址也称为 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="a4006-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="a4006-459">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="a4006-459">Valid values include:</span></span>
  - <span data-ttu-id="a4006-460">个人电子邮件地址 (例如，chris@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="a4006-461">电子邮件域 (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="a4006-462">通配符 (例如 \* ，) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="a4006-463">**发送基础结构**：此值指示来自欺骗用户的邮件来源。</span><span class="sxs-lookup"><span data-stu-id="a4006-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="a4006-464">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="a4006-464">Valid values include:</span></span>
  - <span data-ttu-id="a4006-465">反向 DNS 查找中的域 (PTR 记录) 源电子邮件服务器的 IP 地址的 IP 地址 (例如，fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="a4006-466">如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="a4006-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="a4006-467">下面是用于标识欺骗性发件人的有效域对的一些示例：</span><span class="sxs-lookup"><span data-stu-id="a4006-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="a4006-468">欺骗性发件人条目的最大数量为 1000。</span><span class="sxs-lookup"><span data-stu-id="a4006-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="a4006-469">添加域对仅允许或阻止欺骗用户 *和发送* 基础结构的组合。</span><span class="sxs-lookup"><span data-stu-id="a4006-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="a4006-470">它不允许来自任何来源的欺骗用户的电子邮件，也不允许来自任何欺骗用户的发送基础结构源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a4006-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="a4006-471">例如，为以下域对添加允许条目：</span><span class="sxs-lookup"><span data-stu-id="a4006-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="a4006-472">**域**： gmail.com</span><span class="sxs-lookup"><span data-stu-id="a4006-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="a4006-473">**基础结构**：tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="a4006-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="a4006-474">仅允许 *来自该域* 的邮件和发送基础结构对进行欺骗。</span><span class="sxs-lookup"><span data-stu-id="a4006-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="a4006-475">不允许其他发件人 gmail.com 欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="a4006-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="a4006-476">来自来自其他域的其他域中发件人 tms.mx.com 反欺骗智能进行检查。</span><span class="sxs-lookup"><span data-stu-id="a4006-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
