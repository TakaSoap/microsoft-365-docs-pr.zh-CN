---
title: 配置 Exchange Online 邮箱上的垃圾邮件设置
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online 邮箱中配置垃圾邮件设置。 其中许多设置可供 Outlook 或 Outlook 网页中的用户使用。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7e5d99198e539a46c240fadd2a7a8201236026f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203168"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a><span data-ttu-id="bcf79-104">配置 Exchange Online 邮箱上的垃圾邮件设置</span><span class="sxs-lookup"><span data-stu-id="bcf79-104">Configure junk email settings on Exchange Online mailboxes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bcf79-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="bcf79-105">**Applies to**</span></span>
- [<span data-ttu-id="bcf79-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bcf79-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bcf79-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="bcf79-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bcf79-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcf79-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bcf79-109">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，组织反垃圾邮件设置由 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="bcf79-109">In Microsoft 365 organizations with mailboxes in Exchange Online, organizational anti-spam settings are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="bcf79-110">有关详细信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-110">For more information, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

<span data-ttu-id="bcf79-111">但是，管理员还可以在 Exchange Online 中的单个邮箱上配置特定的反垃圾邮件设置：</span><span class="sxs-lookup"><span data-stu-id="bcf79-111">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="bcf79-112">**启用或禁用垃圾邮件规则**：垃圾邮件规则是隐藏的收件箱规则，名为"垃圾邮件规则"，默认在邮箱中启用。</span><span class="sxs-lookup"><span data-stu-id="bcf79-112">**Enable or disable the junk email rule**: The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="bcf79-113">垃圾邮件规则控制以下功能：</span><span class="sxs-lookup"><span data-stu-id="bcf79-113">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="bcf79-114">**根据** 反垃圾邮件策略将邮件移动到"垃圾邮件"文件夹：当使用"将邮件移动到垃圾邮件文件夹"操作配置反垃圾邮件策略以做出垃圾邮件筛选裁定时，垃圾邮件筛选器规则在邮件传递到邮箱后将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bcf79-114">**Move messages to the Junk Email folder based on anti-spam policies**: When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="bcf79-115">有关反垃圾邮件策略中的垃圾邮件筛选裁定详细信息，请参阅在 [EOP](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="bcf79-115">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="bcf79-116">同样，如果零时差自动清除 (ZAP) 确定已传递的邮件是垃圾邮件或网络钓鱼邮件，垃圾邮件筛选器规则会将邮件移动到"垃圾邮件"文件夹，以执行"将邮件移动到垃圾邮件文件夹垃圾邮件筛选裁定"操作。</span><span class="sxs-lookup"><span data-stu-id="bcf79-116">Similarly, if zero-hour auto purge (ZAP) determines a delivered message is spam or phish, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="bcf79-117">有关 ZAP 有关详细信息，请参阅[Zero-hour auto purge (ZAP) in Exchange Online。](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="bcf79-117">For more information about ZAP, see [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).</span></span>

  - <span data-ttu-id="bcf79-118">**用户在 Outlook** 或 Web 上的 Outlook 中为自己配置的垃圾邮件设置：安全列表集合是每个邮箱的安全发件人列表、安全收件人列表和阻止的发件人列表。</span><span class="sxs-lookup"><span data-stu-id="bcf79-118">**Junk email settings that users configure for themselves in Outlook or Outlook on the web**: The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Blocked Senders list on each mailbox.</span></span> <span data-ttu-id="bcf79-119">这些列表的条目确定垃圾邮件规则是将邮件移动到"收件箱"还是"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bcf79-119">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="bcf79-120">用户可以在 Outlook 或 Web 上的 Outlook 中为他们自己的邮箱配置安全列表集合 (以前称为Outlook Web App) 。</span><span class="sxs-lookup"><span data-stu-id="bcf79-120">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="bcf79-121">管理员可以在任何用户的邮箱上配置安全列表集合。</span><span class="sxs-lookup"><span data-stu-id="bcf79-121">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="bcf79-122">在邮箱上启用垃圾邮件规则后，EOP 能够根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱上的"阻止的发件人"列表，并基于邮箱) 上的"安全发件人"列表阻止邮件传递到"垃圾邮件"文件夹 (。</span><span class="sxs-lookup"><span data-stu-id="bcf79-122">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="bcf79-123">在邮箱上禁用垃圾邮件规则后，EOP 无法根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱的安全列表集合，将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bcf79-123">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="bcf79-124">管理员可以使用 Exchange Online PowerShell 禁用、启用和查看邮箱上垃圾邮件规则的状态。</span><span class="sxs-lookup"><span data-stu-id="bcf79-124">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="bcf79-125">管理员还可使用 Exchange Online PowerShell 配置邮箱的安全列表集合中的条目 (安全发件人列表、安全收件人列表和阻止的发件人列表) 。</span><span class="sxs-lookup"><span data-stu-id="bcf79-125">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Blocked Senders list).</span></span>

> [!NOTE]
> <span data-ttu-id="bcf79-126">来自用户已添加到其自己的安全发件人列表的发件人的邮件将跳过作为 EOP 的一部分的连接筛选 (SCL 为 -1) 。</span><span class="sxs-lookup"><span data-stu-id="bcf79-126">Messages from senders that users have added to their own Safe Senders lists will skip connection filtering as part of EOP (the SCL is -1).</span></span> <span data-ttu-id="bcf79-127">若要阻止用户在 Outlook 中将条目添加到其安全发件人列表中，请使用组策略，如本文稍后的关于  [Outlook](#about-junk-email-settings-in-outlook) 中的垃圾邮件设置部分所述。</span><span class="sxs-lookup"><span data-stu-id="bcf79-127">To prevent users from adding entries to their Safe Senders list in Outlook, use Group Policy as mentioned in the  [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section later in this article.</span></span> <span data-ttu-id="bcf79-128">策略筛选、内容筛选和适用于 Office 365 的 Defender 检查仍将应用于邮件。</span><span class="sxs-lookup"><span data-stu-id="bcf79-128">Policy filtering, Content filtering and Defender for Office 365 checks will still be applied to the messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bcf79-129">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="bcf79-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bcf79-130">只能使用 Exchange Online PowerShell 执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="bcf79-130">You can only use Exchange Online PowerShell to do the procedures in this article.</span></span> <span data-ttu-id="bcf79-131">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="bcf79-132">您需在 Exchange Online 中获得权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="bcf79-132">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="bcf79-133">具体来说，您需要"邮件收件人"角色 (该角色默认情况下分配给"组织管理"、"收件人管理"和"自定义邮件收件人"角色组) 或"用户选项"角色 (该角色默认分配给"组织管理"和"技术支持"角色组) 。     </span><span class="sxs-lookup"><span data-stu-id="bcf79-133">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management**, **Recipient Management**, and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="bcf79-134">若要将用户添加到 Exchange Online 中的角色组，请参阅 [修改 Exchange Online 中的角色组](/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-134">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="bcf79-135">请注意，具有默认权限的用户可以在自己的邮箱上执行这些相同的过程，只要他们有权访问 [Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-135">Note that users with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="bcf79-136">在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bcf79-136">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="bcf79-137">有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-137">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

- <span data-ttu-id="bcf79-138">共享邮箱的安全发件人在设计上不会同步到 Azure AD 和 EOP。</span><span class="sxs-lookup"><span data-stu-id="bcf79-138">Safe Senders for shared mailboxes are not synchronized to Azure AD and EOP by design.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="bcf79-139">使用 Exchange Online PowerShell 启用或禁用邮箱中的垃圾邮件规则</span><span class="sxs-lookup"><span data-stu-id="bcf79-139">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="bcf79-140">您只能使用 **Set-MailboxJunkEmailConfiguration** cmdlet 来禁用在 Outlook（在"缓存"Exchange 模式中）或 Web 上的 Outlook 中打开的邮箱上的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="bcf79-140">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="bcf79-141">如果尚未打开邮箱，您将收到错误：如果要禁止批量操作出现此错误，可以将其添加到 `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration** 命令中。</span><span class="sxs-lookup"><span data-stu-id="bcf79-141">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

<span data-ttu-id="bcf79-142">若要启用或禁用邮箱上的垃圾邮件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bcf79-142">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="bcf79-143">本示例禁用 Ori Epstein 邮箱上的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="bcf79-143">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="bcf79-144">本示例禁用组织中的所有用户邮箱上的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="bcf79-144">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="bcf79-145">有关语法和参数的详细信息，请参阅 [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-145">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="bcf79-146">如果用户从未打开过其邮箱，则当您运行上一个命令时，您可能会收到错误。</span><span class="sxs-lookup"><span data-stu-id="bcf79-146">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="bcf79-147">若要禁止批量操作出现此错误，请 `-ErrorAction SilentlyContinue` 添加到 **Set-MailboxJunkEmailConfiguration** 命令。</span><span class="sxs-lookup"><span data-stu-id="bcf79-147">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="bcf79-148">即使您禁用垃圾邮件规则，Outlook 垃圾邮件筛选器 (根据其配置方式) 也可以确定邮件是否是垃圾邮件，并可以基于自己的垃圾邮件裁定和邮箱的安全列表集合将邮件移动到收件箱或垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="bcf79-148">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="bcf79-149">有关详细信息，请参阅本文中的 [关于 Outlook 中的](#about-junk-email-settings-in-outlook) 垃圾邮件设置部分。</span><span class="sxs-lookup"><span data-stu-id="bcf79-149">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this article.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bcf79-150">您如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="bcf79-150">How do you know this worked?</span></span>

<span data-ttu-id="bcf79-151">若要验证是否已成功启用或禁用邮箱的垃圾邮件规则，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="bcf79-151">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="bcf79-152">将 替换为邮箱的名称、别名或电子邮件地址，并运行以下命令 _\<MailboxIdentity\>_ 来验证 **Enabled** 属性值：</span><span class="sxs-lookup"><span data-stu-id="bcf79-152">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="bcf79-153">使用 Exchange Online PowerShell 配置邮箱的安全列表集合</span><span class="sxs-lookup"><span data-stu-id="bcf79-153">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="bcf79-154">邮箱的安全列表集合包括"安全发件人"列表、"安全收件人"列表和"阻止的发件人"列表。</span><span class="sxs-lookup"><span data-stu-id="bcf79-154">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="bcf79-155">默认情况下，用户可以在 Outlook 或 Web 上的 Outlook 中配置自己的邮箱的安全列表集合。</span><span class="sxs-lookup"><span data-stu-id="bcf79-155">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="bcf79-156">管理员可以使用 **Set-MailboxJunkEmailConfiguration** cmdlet 上对应的参数在用户的邮箱上配置安全列表集合。</span><span class="sxs-lookup"><span data-stu-id="bcf79-156">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="bcf79-157">下表介绍了这些参数。</span><span class="sxs-lookup"><span data-stu-id="bcf79-157">These parameters are described in the following table.</span></span>

****

|<span data-ttu-id="bcf79-158">上Set-MailboxJunkEmailConfiguration</span><span class="sxs-lookup"><span data-stu-id="bcf79-158">Parameter on Set-MailboxJunkEmailConfiguration</span></span>|<span data-ttu-id="bcf79-159">Outlook 网页应用设置</span><span class="sxs-lookup"><span data-stu-id="bcf79-159">Outlook on the web setting</span></span>|
|---|---|
|<span data-ttu-id="bcf79-160">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="bcf79-160">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="bcf79-161">**将来自这些发件人或域的邮件移到我的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="bcf79-161">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="bcf79-162">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="bcf79-162">_ContactsTrusted_</span></span>|<span data-ttu-id="bcf79-163">**信任来自我的联系人的邮件**</span><span class="sxs-lookup"><span data-stu-id="bcf79-163">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="bcf79-164">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="bcf79-164">_TrustedListsOnly_</span></span>|<span data-ttu-id="bcf79-165">**仅信任来自安全发件人和域列表和安全邮件列表中地址的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="bcf79-165">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="bcf79-166">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bcf79-166">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="bcf79-167">**不要将来自这些发件人的电子邮件移动到我的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="bcf79-167">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="bcf79-168"><sup>\*</sup>**注意**：</span><span class="sxs-lookup"><span data-stu-id="bcf79-168"><sup>\*</sup> **Notes**:</span></span>

- <span data-ttu-id="bcf79-169">在 Exchange Online **中** ，无法识别安全发件人列表或 _TrustedSendersAndDomains_ 参数中的域条目，因此只能使用电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bcf79-169">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="bcf79-170">在具有目录同步的独立 EOP 中，默认情况下不会同步域条目，但您可以为域启用同步。</span><span class="sxs-lookup"><span data-stu-id="bcf79-170">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="bcf79-171">有关详细信息，请参阅[KB3019657。](https://support.microsoft.com/help/3019657)</span><span class="sxs-lookup"><span data-stu-id="bcf79-171">For more information, see [KB3019657](https://support.microsoft.com/help/3019657).</span></span>

- <span data-ttu-id="bcf79-172">使用 **Set-MailboxJunkEmailConfiguration** cmdlet (_TrustedRecipientsAndDomains_ 参数不能直接修改安全收件人列表) 。</span><span class="sxs-lookup"><span data-stu-id="bcf79-172">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="bcf79-173">修改"安全发件人"列表后，这些更改将同步到"安全收件人"列表。</span><span class="sxs-lookup"><span data-stu-id="bcf79-173">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="bcf79-174">若要配置邮箱的安全列表集合，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bcf79-174">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="bcf79-175">若要输入多个值并覆盖 _BlockedSendersAndDomains_ 和 _TrustedSendersAndDomains_ 参数的任何现有条目，请使用以下语法： `"<Value1>","<Value2>"...` 。</span><span class="sxs-lookup"><span data-stu-id="bcf79-175">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="bcf79-176">若要添加或删除一个或多个值而不影响其他现有条目，请使用以下语法： `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="bcf79-176">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="bcf79-177">本示例在 Ori Epstein 的邮箱上配置以下安全列表集合的设置：</span><span class="sxs-lookup"><span data-stu-id="bcf79-177">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="bcf79-178">将值 shopping@fabrikam.com 阻止的发件人列表。</span><span class="sxs-lookup"><span data-stu-id="bcf79-178">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="bcf79-179">从"安全 chris@fourthcoffee.com"列表和安全收件人列表中删除"安全收件人"列表中的值。</span><span class="sxs-lookup"><span data-stu-id="bcf79-179">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="bcf79-180">在"联系人"文件夹中配置被视为受信任的发件人的联系人。</span><span class="sxs-lookup"><span data-stu-id="bcf79-180">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="bcf79-181">本示例将域 contoso.com 从组织中所有用户的邮箱的"阻止的发件人"名单中删除。</span><span class="sxs-lookup"><span data-stu-id="bcf79-181">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="bcf79-182">有关语法和参数的详细信息，请参阅 [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-182">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="bcf79-183">如果用户从未打开过邮箱，则当您运行之前的命令时，您可能会收到错误。</span><span class="sxs-lookup"><span data-stu-id="bcf79-183">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="bcf79-184">若要禁止批量操作出现此错误，请 `-ErrorAction SilentlyContinue` 添加到 **Set-MailboxJunkEmailConfiguration** 命令。</span><span class="sxs-lookup"><span data-stu-id="bcf79-184">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="bcf79-185">即使对邮箱禁用了垃圾邮件规则，您仍可以配置安全列表集合，并且 Outlook 垃圾邮件筛选器可以将邮件移动到收件箱或"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bcf79-185">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="bcf79-186">有关详细信息，请参阅本文中的 [关于 Outlook 中的](#about-junk-email-settings-in-outlook) 垃圾邮件设置部分。</span><span class="sxs-lookup"><span data-stu-id="bcf79-186">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this article.</span></span>
>
> - <span data-ttu-id="bcf79-187">Outlook 垃圾邮件筛选器具有其他安全列表集合 (例如，自动 **将** 我的电子邮件添加到安全发件人列表) 。</span><span class="sxs-lookup"><span data-stu-id="bcf79-187">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list**).</span></span> <span data-ttu-id="bcf79-188">For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).</span><span class="sxs-lookup"><span data-stu-id="bcf79-188">For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bcf79-189">您如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="bcf79-189">How do you know this worked?</span></span>

<span data-ttu-id="bcf79-190">若要验证是否已成功配置邮箱的安全列表集合，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="bcf79-190">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="bcf79-191">将 替换为邮箱的名称、别名或电子邮件地址，并运行以下命令 _\<MailboxIdentity\>_ 来验证属性值：</span><span class="sxs-lookup"><span data-stu-id="bcf79-191">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="bcf79-192">如果值列表太长，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bcf79-192">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="bcf79-193">关于 Outlook 中的配置垃圾邮件设置</span><span class="sxs-lookup"><span data-stu-id="bcf79-193">About junk email settings in Outlook</span></span>

<span data-ttu-id="bcf79-194">若要启用、禁用及配置在 Outlook 中可以使用的客户端"垃圾邮件筛选器"设置，请使用"组策略"。</span><span class="sxs-lookup"><span data-stu-id="bcf79-194">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="bcf79-195">有关详细信息，请参阅管理模板文件[ (ADMX/ADML) 和适用于 Microsoft 365 企业应用版、Office 2019 和 Office 2016](https://www.microsoft.com/download/details.aspx?id=49030)的 Office 自定义工具以及如何使用组策略部署垃圾邮件设置（如安全发件人[列表）。](https://support.microsoft.com/help/2252421)</span><span class="sxs-lookup"><span data-stu-id="bcf79-195">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) and [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy](https://support.microsoft.com/help/2252421).</span></span>

<span data-ttu-id="bcf79-196">当 Outlook 垃圾邮件筛选器设置为默认值"主页垃圾邮件选项选项"中"无自动筛选 \>  \>  \> "时，Outlook 不会尝试将垃圾邮件分类为垃圾邮件，但仍使用安全列表集合 (安全发件人列表、安全收件人列表和阻止的发件人列表) 在邮件传递后将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bcf79-196">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="bcf79-197">有关这些设置详细信息，请参阅 [垃圾邮件筛选器概述](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-197">For more information about these settings, see [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="bcf79-198">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span><span class="sxs-lookup"><span data-stu-id="bcf79-198">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="bcf79-199">此垃圾邮件分类独立于由 EOP (SCL) 的垃圾邮件可信度。</span><span class="sxs-lookup"><span data-stu-id="bcf79-199">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="bcf79-200">事实上，Outlook 会忽略 EOP (除非 EOP 将邮件标记为跳过垃圾邮件筛选) 并使用自己的条件来确定邮件是否是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="bcf79-200">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="bcf79-201">当然，来自 EOP 和 Outlook 的垃圾邮件裁定可能相同。</span><span class="sxs-lookup"><span data-stu-id="bcf79-201">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="bcf79-202">有关这些设置详细信息，请参阅更改垃圾邮件 [筛选器中的保护级别](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。</span><span class="sxs-lookup"><span data-stu-id="bcf79-202">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="bcf79-203">2016 年 11 月，Microsoft 停止为 Exchange 和 Outlook 中的 SmartScreen 筛选器生成垃圾邮件定义更新。</span><span class="sxs-lookup"><span data-stu-id="bcf79-203">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="bcf79-204">现有的 SmartScreen 垃圾邮件定义已就位，但其有效性可能会随着时间的推移而降低。</span><span class="sxs-lookup"><span data-stu-id="bcf79-204">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="bcf79-205">有关详细信息，请参阅“[停止为 Outlook 和 Exchange 中的 SmartScreen 提供支持](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)”。</span><span class="sxs-lookup"><span data-stu-id="bcf79-205">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="bcf79-206">因此，Outlook 垃圾邮件筛选器可以使用邮箱的安全列表集合及其自己的垃圾邮件分类将邮件移动到"垃圾邮件"文件夹，即使邮箱中已禁用垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="bcf79-206">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="bcf79-207">Outlook 和 Web 上的 Outlook 同等支持安全列表集合。</span><span class="sxs-lookup"><span data-stu-id="bcf79-207">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="bcf79-208">安全列表集合保存在 Exchange Online 邮箱中，因此对 Outlook 中的安全列表集合的更改显示在 Outlook 网页版中，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="bcf79-208">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

## <a name="limits-for-junk-email-settings"></a><span data-ttu-id="bcf79-209">垃圾邮件设置的限制</span><span class="sxs-lookup"><span data-stu-id="bcf79-209">Limits for junk email settings</span></span>

<span data-ttu-id="bcf79-210">安全列表集合 (用户邮箱中存储的安全发件人列表、安全收件人列表和阻止的发件人列表) 也会同步到 EOP。</span><span class="sxs-lookup"><span data-stu-id="bcf79-210">The safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) that's stored in the user's mailbox is also synchronized to EOP.</span></span> <span data-ttu-id="bcf79-211">通过目录同步，安全列表集合将同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="bcf79-211">With directory synchronization, the safelist collection is synchronized to Azure AD.</span></span>

- <span data-ttu-id="bcf79-212">用户邮箱中的安全列表集合限制为 510 KB，其中包括所有列表，以及其他垃圾邮件筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="bcf79-212">The safelist collection in the user's mailbox has a limit of 510 KB, which includes all lists, plus additional junk email filter settings.</span></span> <span data-ttu-id="bcf79-213">如果用户超过此限制，他们将收到如下所示的 Outlook 错误：</span><span class="sxs-lookup"><span data-stu-id="bcf79-213">If a user exceeds this limit, they will receive an Outlook error that looks like this:</span></span>

  > <span data-ttu-id="bcf79-214">无法/无法添加到服务器垃圾邮件列表。</span><span class="sxs-lookup"><span data-stu-id="bcf79-214">Cannot/Unable add to the server Junk E-mail lists.</span></span> <span data-ttu-id="bcf79-215">您超过服务器上允许的大小。</span><span class="sxs-lookup"><span data-stu-id="bcf79-215">You are over the size allowed on the server.</span></span> <span data-ttu-id="bcf79-216">在服务器上禁用垃圾邮件筛选器，直到垃圾邮件列表减小到服务器允许的大小。</span><span class="sxs-lookup"><span data-stu-id="bcf79-216">The Junk E-mail filter on the server will be disabled until your Junk E-mail lists have been reduced to the size allowed by the server.</span></span>

  <span data-ttu-id="bcf79-217">有关此限制以及如何更改它的信息，请参阅[KB2669081。](https://support.microsoft.com/help/2669081)</span><span class="sxs-lookup"><span data-stu-id="bcf79-217">For more information about this limit and how to change it, see [KB2669081](https://support.microsoft.com/help/2669081).</span></span>

- <span data-ttu-id="bcf79-218">EOP 中的同步安全列表集合具有以下同步限制：</span><span class="sxs-lookup"><span data-stu-id="bcf79-218">The synchronized safelist collection in EOP has the following synchronization limits:</span></span>

  - <span data-ttu-id="bcf79-219">如果启用了"信任来自我的联系人的电子邮件"，则"安全发件人"列表、"安全收件人"列表和外部联系人的总条目数为 1024。</span><span class="sxs-lookup"><span data-stu-id="bcf79-219">1024 total entries in the Safe Senders list, the Safe Recipients list, and external contacts if **Trust email from my contacts** is enabled.</span></span>
  - <span data-ttu-id="bcf79-220">"阻止的发件人"列表和"阻止的域"列表中的总条目数为 500。</span><span class="sxs-lookup"><span data-stu-id="bcf79-220">500 total entries in the Blocked Senders list and Blocked Domains list.</span></span>

  <span data-ttu-id="bcf79-221">当达到 1024 条目限制时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="bcf79-221">When the 1024 entry limit is reached, the following things happen:</span></span>

  - <span data-ttu-id="bcf79-222">该列表将停止接受 PowerShell 和 Web 上的 Outlook 中的条目，但不显示任何错误。</span><span class="sxs-lookup"><span data-stu-id="bcf79-222">The list stops accepting entries in PowerShell and Outlook on the web, but no error is displayed.</span></span>

    <span data-ttu-id="bcf79-223">Outlook 用户可以继续添加超过 1024 个条目，直到达到 Outlook 限制 510 KB。</span><span class="sxs-lookup"><span data-stu-id="bcf79-223">Outlook users can continue to add more than 1024 entries until they reach the Outlook limit of 510 KB.</span></span> <span data-ttu-id="bcf79-224">Outlook 可以使用这些附加条目，只要 EOP 筛选器在发送到邮箱之前没有阻止邮件 (邮件流规则、反欺骗等) 。</span><span class="sxs-lookup"><span data-stu-id="bcf79-224">Outlook can use these additional entries, as long as an EOP filter doesn't block the message before delivery to the mailbox (mail flow rules, anti-spoofing, etc.).</span></span>

- <span data-ttu-id="bcf79-225">通过目录同步，条目按以下顺序同步到 Azure AD：</span><span class="sxs-lookup"><span data-stu-id="bcf79-225">With directory synchronization, the entries are synchronized to Azure AD in the following order:</span></span>

  1. <span data-ttu-id="bcf79-226">如果启用" **信任来自我的联系人的电子邮件"，则邮件** 联系人。</span><span class="sxs-lookup"><span data-stu-id="bcf79-226">Mail contacts if **Trust email from my contacts** is enabled.</span></span>
  2. <span data-ttu-id="bcf79-227">只要对前 1024 个条目进行了更改，就会组合安全发件人列表和安全收件人列表、取消重复列表并按字母顺序排序。</span><span class="sxs-lookup"><span data-stu-id="bcf79-227">The Safe Sender list and Safe Recipient list are combined, de-duplicated, and sorted alphabetically whenever a change is made for the first 1024 entries.</span></span>

  <span data-ttu-id="bcf79-228">使用前 1024 个条目，相关信息标记在邮件头中。</span><span class="sxs-lookup"><span data-stu-id="bcf79-228">The first 1024 entries are used, and relevant information is stamped in the message headers.</span></span>

  <span data-ttu-id="bcf79-229">超过 1024 个且未同步到 Azure AD 的条目由 Outlook (而不是 Outlook 网页版) 处理，并且邮件头中不会标记任何信息。</span><span class="sxs-lookup"><span data-stu-id="bcf79-229">Entries over 1024 that weren't synchronized to Azure AD are processed by Outlook (not Outlook on the web), and no information is stamped in the message headers.</span></span>

<span data-ttu-id="bcf79-230">可以看到，启用"信任来自我的联系人的电子邮件"设置可以减少可以同步的安全发件人和安全收件人的数量。</span><span class="sxs-lookup"><span data-stu-id="bcf79-230">As you can see, enabling the **Trust email from my contacts** setting reduces the number of Safe Senders and Safe Recipients that can be synchronized.</span></span> <span data-ttu-id="bcf79-231">如果这是一个问题，我们建议使用组策略关闭此功能：</span><span class="sxs-lookup"><span data-stu-id="bcf79-231">If this is a concern, then we recommend using Group Policy to turn this feature off:</span></span>

- <span data-ttu-id="bcf79-232">文件名：outlk16.opax</span><span class="sxs-lookup"><span data-stu-id="bcf79-232">File name: outlk16.opax</span></span>
- <span data-ttu-id="bcf79-233">策略设置 **：信任来自联系人的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="bcf79-233">Policy setting: **Trust e-mail from contacts**</span></span>