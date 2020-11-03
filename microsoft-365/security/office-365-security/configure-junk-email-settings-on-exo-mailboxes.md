---
title: 配置 Exchange Online 邮箱上的垃圾邮件设置
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online 邮箱中配置垃圾邮件设置。 Outlook 或 web 上的 Outlook 中的用户可以使用这些设置中的很多。
ms.openlocfilehash: 59106567e18895f5983b692bbdd03c6853b92341
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845836"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a><span data-ttu-id="de7ba-104">配置 Exchange Online 邮箱上的垃圾邮件设置</span><span class="sxs-lookup"><span data-stu-id="de7ba-104">Configure junk email settings on Exchange Online mailboxes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="de7ba-105">在 Exchange Online 中有邮箱的 Microsoft 365 组织中，组织反垃圾邮件设置由 Exchange Online Protection (EOP) 进行控制。</span><span class="sxs-lookup"><span data-stu-id="de7ba-105">In Microsoft 365 organizations with mailboxes in Exchange Online, organizational anti-spam settings are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="de7ba-106">有关详细信息，请参阅 [EOP 中的反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-106">For more information, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

<span data-ttu-id="de7ba-107">但是，管理员还可以在 Exchange Online 中的各个邮箱上配置特定的反垃圾邮件设置：</span><span class="sxs-lookup"><span data-stu-id="de7ba-107">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="de7ba-108">**启用或禁用垃圾邮件规则** ： "垃圾邮件" 规则是一个隐藏的 "收件箱" 规则，默认情况下，在每个邮箱中启用该规则。</span><span class="sxs-lookup"><span data-stu-id="de7ba-108">**Enable or disable the junk email rule** : The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="de7ba-109">垃圾邮件规则控制以下功能：</span><span class="sxs-lookup"><span data-stu-id="de7ba-109">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="de7ba-110">**根据反垃圾邮件策略将邮件移动到 "垃圾邮件" 文件夹** ：当使用 "操作 **将邮件移动到垃圾邮件" 文件夹** 中的垃圾邮件策略筛选判定时，垃圾邮件筛选规则会在邮件传递到邮箱后将邮件移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="de7ba-110">**Move messages to the Junk Email folder based on anti-spam policies** : When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="de7ba-111">有关反垃圾邮件策略中的垃圾邮件筛选 verdicts 的详细信息，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-111">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="de7ba-112">同样，如果零小时自动清除 (ZAP) 确定传递的邮件是垃圾邮件或网络钓鱼，垃圾邮件筛选规则会将邮件移动到 "垃圾邮件" 文件夹，以便 **将邮件移动到 "垃圾** 邮件" 文件夹。垃圾邮件筛选判定操作。</span><span class="sxs-lookup"><span data-stu-id="de7ba-112">Similarly, if zero-hour auto purge (ZAP) determines a delivered message is spam or phish, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="de7ba-113">有关 ZAP 的详细信息，请参阅 [Exchange Online 中的零小时自动清除 (ZAP) ](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-113">For more information about ZAP, see [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).</span></span>

  - <span data-ttu-id="de7ba-114">**用户在 outlook 或 web 上的 outlook 中为自己配置的垃圾邮件设置** ：安全列表 _集合_ 是安全发件人列表、安全收件人列表和每个邮箱的阻止发件人列表。</span><span class="sxs-lookup"><span data-stu-id="de7ba-114">**Junk email settings that users configure for themselves in Outlook or Outlook on the web** : The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Blocked Senders list on each mailbox.</span></span> <span data-ttu-id="de7ba-115">这些列表中的条目确定垃圾邮件规则是否将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="de7ba-115">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="de7ba-116">用户可以在 Outlook 或 web 上的 Outlook 中为其自己的邮箱配置安全列表集合， (以前称为 Outlook Web App) 。</span><span class="sxs-lookup"><span data-stu-id="de7ba-116">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="de7ba-117">管理员可以在任何用户的邮箱上配置安全列表集合。</span><span class="sxs-lookup"><span data-stu-id="de7ba-117">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="de7ba-118">在邮箱上启用垃圾邮件规则时，EOP 可以将邮件移动到 "垃圾邮件" 文件夹，具体取决于垃圾邮件筛选判定操作 " **将邮件移至垃圾邮件" 文件夹** 或邮箱中的阻止发件人列表，并阻止邮件传递到 "垃圾邮件" 文件夹 (基于邮箱) 上的 "安全发件人" 列表。</span><span class="sxs-lookup"><span data-stu-id="de7ba-118">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="de7ba-119">在邮箱上禁用垃圾邮件规则时，EOP 无法根据垃圾邮件筛选判定操作将邮件移动到 "垃圾邮件" 文件夹。 **将邮件移动到 "垃圾邮件" 文件夹** 或邮箱中的 "安全列表" 集合。</span><span class="sxs-lookup"><span data-stu-id="de7ba-119">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="de7ba-120">管理员可以使用 Exchange Online PowerShell 禁用、启用和查看邮箱上的垃圾邮件规则的状态。</span><span class="sxs-lookup"><span data-stu-id="de7ba-120">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="de7ba-121">管理员还可以使用 Exchange Online PowerShell 在邮箱 (安全发件人列表、安全收件人列表和阻止发件人列表) 中的 "安全发件人" 列表中配置安全列表集合中的条目。</span><span class="sxs-lookup"><span data-stu-id="de7ba-121">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Blocked Senders list).</span></span>

> [!NOTE]
> <span data-ttu-id="de7ba-122">来自用户添加到其自己的安全发件人列表中的发件人发来的邮件将跳过连接筛选作为 EOP 的一部分 (SCL 为-1) 。</span><span class="sxs-lookup"><span data-stu-id="de7ba-122">Messages from senders that users have added to their own Safe Senders lists will skip connection filtering as part of EOP (the SCL is -1).</span></span> <span data-ttu-id="de7ba-123">若要阻止用户在 Outlook 中向其安全发件人列表添加条目，请按照本主题后面的  [关于 Outlook 中的垃圾邮件设置](#about-junk-email-settings-in-outlook) 一节中所述的那样使用组策略。</span><span class="sxs-lookup"><span data-stu-id="de7ba-123">To prevent users from adding entries to their Safe Senders list in Outlook, use Group Policy as mentioned in the  [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section later in this topic.</span></span> <span data-ttu-id="de7ba-124">策略筛选、Office 365 的内容筛选和 Defender 检查仍将应用于邮件。</span><span class="sxs-lookup"><span data-stu-id="de7ba-124">Policy filtering, Content filtering and Defender for Office 365 checks will still be applied to the messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="de7ba-125">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="de7ba-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="de7ba-126">只能使用 Exchange Online PowerShell 执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="de7ba-126">You can only use Exchange Online PowerShell to perform these procedures.</span></span> <span data-ttu-id="de7ba-127">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="de7ba-128">您需要先分配权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="de7ba-128">You need to be assigned permissions before you can do these procedures.</span></span> <span data-ttu-id="de7ba-129">具体来说，您需要 " **邮件收件人** " 角色 (默认情况下，该角色分配给 " **组织管理** "、" **收件人管理** " 和 " **自定义邮件收件人** " 角色组) 或者 " **用户选项** " 角色 (默认情况下分配给 " **组织管理** " 和 " **技术支持** " 角色组) 。</span><span class="sxs-lookup"><span data-stu-id="de7ba-129">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management** , **Recipient Management** , and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="de7ba-130">若要向 Exchange Online 中的角色组添加用户，请参阅 [在 Exchange online 中修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-130">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="de7ba-131">请注意，拥有默认权限的用户可以在其自己的邮箱上执行这些相同的过程，只要他们有 [权访问 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)即可。</span><span class="sxs-lookup"><span data-stu-id="de7ba-131">Note that a user with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="de7ba-132">在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="de7ba-132">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="de7ba-133">有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-133">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

- <span data-ttu-id="de7ba-134">共享邮箱的安全发件人在设计时不会同步到 Azure AD 和 EOP。</span><span class="sxs-lookup"><span data-stu-id="de7ba-134">Safe Senders for shared mailboxes are not synchronized to Azure AD and EOP by design.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="de7ba-135">使用 Exchange Online PowerShell 启用或禁用邮箱中的垃圾邮件规则</span><span class="sxs-lookup"><span data-stu-id="de7ba-135">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="de7ba-136">您只能使用 **Set-MailboxJunkEmailConfiguration** cmdlet 来禁用在 Outlook（在"缓存"Exchange 模式中）或 Web 上的 Outlook 中打开的邮箱上的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="de7ba-136">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="de7ba-137">如果尚未打开邮箱，则会收到错误： `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` 如果要对批量操作禁止显示此错误，可以添加 `-ErrorAction SilentlyContinue` 到 **set-mailboxjunkemailconfiguration** 命令。</span><span class="sxs-lookup"><span data-stu-id="de7ba-137">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

<span data-ttu-id="de7ba-138">若要启用或禁用邮箱上的垃圾邮件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="de7ba-138">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="de7ba-139">本示例禁用 Ori Epstein 邮箱上的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="de7ba-139">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="de7ba-140">本示例禁用组织中的所有用户邮箱上的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="de7ba-140">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="de7ba-141">有关语法和参数的详细信息，请参阅 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-141">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="de7ba-142">如果用户从未打开过其邮箱，则在运行以前的命令时可能会收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="de7ba-142">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="de7ba-143">若要取消批量操作的此错误，请添加 `-ErrorAction SilentlyContinue` 到 **set-mailboxjunkemailconfiguration** 命令。</span><span class="sxs-lookup"><span data-stu-id="de7ba-143">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="de7ba-144">即使禁用垃圾邮件规则，Outlook 垃圾邮件筛选器 (取决于其配置) 还可以确定邮件是否为垃圾邮件，并且可以根据其自身的垃圾邮件结论和邮箱上的安全列表集合，将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="de7ba-144">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="de7ba-145">有关详细信息，请参阅本主题中的[有关 Outlook 中的垃圾邮件设置](#about-junk-email-settings-in-outlook)部分。</span><span class="sxs-lookup"><span data-stu-id="de7ba-145">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="de7ba-146">您如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="de7ba-146">How do you know this worked?</span></span>

<span data-ttu-id="de7ba-147">若要验证是否已成功启用或禁用邮箱的垃圾邮件规则，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="de7ba-147">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="de7ba-148">_\<MailboxIdentity\>_ 将替换为邮箱的名称、别名或电子邮件地址，然后运行以下命令来验证 **Enabled** 属性值：</span><span class="sxs-lookup"><span data-stu-id="de7ba-148">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="de7ba-149">使用 Exchange Online PowerShell 在邮箱上配置安全列表集合</span><span class="sxs-lookup"><span data-stu-id="de7ba-149">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="de7ba-150">邮箱的安全列表集合包括"安全发件人"列表、"安全收件人"列表和"阻止的发件人"列表。</span><span class="sxs-lookup"><span data-stu-id="de7ba-150">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="de7ba-151">默认情况下，用户可以在 Outlook 或 web 上的 Outlook 中的自己的邮箱上配置安全列表集合。</span><span class="sxs-lookup"><span data-stu-id="de7ba-151">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="de7ba-152">管理员可以使用 **Set-MailboxJunkEmailConfiguration** cmdlet 上对应的参数在用户的邮箱上配置安全列表集合。</span><span class="sxs-lookup"><span data-stu-id="de7ba-152">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="de7ba-153">下表介绍了这些参数。</span><span class="sxs-lookup"><span data-stu-id="de7ba-153">These parameters are described in the following table.</span></span>

****

|<span data-ttu-id="de7ba-154">Set-MailboxJunkEmailConfiguration 上的参数</span><span class="sxs-lookup"><span data-stu-id="de7ba-154">Parameter on Set-MailboxJunkEmailConfiguration</span></span>|<span data-ttu-id="de7ba-155">Outlook 网页设置</span><span class="sxs-lookup"><span data-stu-id="de7ba-155">Outlook on the web setting</span></span>|
|---|---|
|<span data-ttu-id="de7ba-156">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="de7ba-156">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="de7ba-157">**将来自这些发件人或域的邮件移到我的"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="de7ba-157">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="de7ba-158">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="de7ba-158">_ContactsTrusted_</span></span>|<span data-ttu-id="de7ba-159">**信任来自我的联系人的邮件**</span><span class="sxs-lookup"><span data-stu-id="de7ba-159">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="de7ba-160">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="de7ba-160">_TrustedListsOnly_</span></span>|<span data-ttu-id="de7ba-161">**仅信任来自安全发件人和域列表和安全邮件列表中的地址的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="de7ba-161">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="de7ba-162">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="de7ba-162">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="de7ba-163">**不将来自这些发件人的电子邮件移动到我的垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="de7ba-163">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="de7ba-164"><sup>\*</sup>**备注** ：</span><span class="sxs-lookup"><span data-stu-id="de7ba-164"><sup>\*</sup> **Notes** :</span></span>

- <span data-ttu-id="de7ba-165">在 Exchange Online 中，不能识别安全发件人列表或 _TrustedSendersAndDomains_ 参数中的 **域条目** ，因此只能使用电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="de7ba-165">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="de7ba-166">在具有目录同步的独立 EOP 中，默认情况下不会同步域条目，但可以为域启用同步。</span><span class="sxs-lookup"><span data-stu-id="de7ba-166">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="de7ba-167">有关详细信息，请参阅 [KB3019657](https://support.microsoft.com/help/3019657)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-167">For more information, see [KB3019657](https://support.microsoft.com/help/3019657).</span></span>

- <span data-ttu-id="de7ba-168">您不能使用 **set-mailboxjunkemailconfiguration** cmdlet 直接修改安全收件人列表 ( _TrustedRecipientsAndDomains_ 参数不起作用) 。</span><span class="sxs-lookup"><span data-stu-id="de7ba-168">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="de7ba-169">修改"安全发件人"列表后，这些更改将同步到"安全收件人"列表。</span><span class="sxs-lookup"><span data-stu-id="de7ba-169">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="de7ba-170">若要配置邮箱的安全列表集合，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="de7ba-170">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="de7ba-171">若要输入多个值，并覆盖 _BlockedSendersAndDomains_ 和 _TrustedSendersAndDomains_ 参数的任何现有条目，请使用以下语法： `"<Value1>","<Value2>"...` 。</span><span class="sxs-lookup"><span data-stu-id="de7ba-171">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="de7ba-172">若要在不影响其他现有条目的情况下添加或删除一个或多个值，请使用以下语法： `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="de7ba-172">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="de7ba-173">本示例在 Ori Epstein 的邮箱上配置以下安全列表集合的设置：</span><span class="sxs-lookup"><span data-stu-id="de7ba-173">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="de7ba-174">将值 shopping@fabrikam.com 添加到阻止的发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="de7ba-174">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="de7ba-175">从 "安全发件人" 列表和 "安全收件人" 列表中删除值 chris@fourthcoffee.com。</span><span class="sxs-lookup"><span data-stu-id="de7ba-175">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="de7ba-176">在"联系人"文件夹中配置被视为受信任的发件人的联系人。</span><span class="sxs-lookup"><span data-stu-id="de7ba-176">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="de7ba-177">本示例将域 contoso.com 从组织中所有用户的邮箱的"阻止的发件人"名单中删除。</span><span class="sxs-lookup"><span data-stu-id="de7ba-177">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="de7ba-178">有关语法和参数的详细信息，请参阅 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-178">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="de7ba-179">如果用户从未打开过其邮箱，则在运行以前的命令时可能会收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="de7ba-179">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="de7ba-180">若要取消批量操作的此错误，请添加 `-ErrorAction SilentlyContinue` 到 **set-mailboxjunkemailconfiguration** 命令。</span><span class="sxs-lookup"><span data-stu-id="de7ba-180">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="de7ba-181">即使在邮箱上禁用了垃圾邮件规则，仍可以配置安全列表集合，并且 Outlook 垃圾邮件筛选器能够将邮件移动到 "收件箱" 或 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="de7ba-181">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="de7ba-182">有关详细信息，请参阅本主题中的[关于 Outlook 中的配置垃圾邮件设置](#about-junk-email-settings-in-outlook)部分。</span><span class="sxs-lookup"><span data-stu-id="de7ba-182">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>
>
> - <span data-ttu-id="de7ba-183">Outlook 垃圾邮件筛选器包含其他安全列表集合设置 (例如， **自动将我的电子邮件添加到 "安全发件人" 列表** ) 。</span><span class="sxs-lookup"><span data-stu-id="de7ba-183">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list** ).</span></span> <span data-ttu-id="de7ba-184">For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).</span><span class="sxs-lookup"><span data-stu-id="de7ba-184">For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="de7ba-185">您如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="de7ba-185">How do you know this worked?</span></span>

<span data-ttu-id="de7ba-186">若要验证是否已成功配置邮箱的安全列表集合，请执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="de7ba-186">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="de7ba-187">_\<MailboxIdentity\>_ 将替换为邮箱的名称、别名或电子邮件地址，然后运行以下命令来验证属性值：</span><span class="sxs-lookup"><span data-stu-id="de7ba-187">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="de7ba-188">如果值列表太长，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="de7ba-188">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="de7ba-189">关于 Outlook 中的配置垃圾邮件设置</span><span class="sxs-lookup"><span data-stu-id="de7ba-189">About junk email settings in Outlook</span></span>

<span data-ttu-id="de7ba-190">若要启用、禁用及配置在 Outlook 中可以使用的客户端"垃圾邮件筛选器"设置，请使用"组策略"。</span><span class="sxs-lookup"><span data-stu-id="de7ba-190">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="de7ba-191">有关详细信息，请参阅 [管理模板文件 (ADMX/ADML) 和 Office 自定义工具 For Microsoft 365 Apps for enterprise、office 2019 和 office 2016](https://www.microsoft.com/download/details.aspx?id=49030) 以及 [如何使用组策略部署垃圾邮件设置（如安全发件人列表](https://support.microsoft.com/help/2252421)）。</span><span class="sxs-lookup"><span data-stu-id="de7ba-191">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) and [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy](https://support.microsoft.com/help/2252421).</span></span>

<span data-ttu-id="de7ba-192">将 "Outlook 垃圾邮件筛选器" 设置为默认值 "在 **家庭** 垃圾邮件中 **不自动筛选** " "垃圾 \> **Junk** \> **邮件选项** \> " **选项** 时，Outlook 不会尝试将 massages 归类为垃圾邮件，但仍 (使用安全发件人列表、安全收件人列表和阻止发件人列表) 将邮件移动到 "垃圾邮件" 文件夹中的邮件传递。</span><span class="sxs-lookup"><span data-stu-id="de7ba-192">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options** , Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="de7ba-193">有关这些设置的详细信息，请参阅 [垃圾邮件筛选器概述](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-193">For more information about these settings, see [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="de7ba-194">When the Outlook Junk Email Filter is set to **Low** or **High** , the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span><span class="sxs-lookup"><span data-stu-id="de7ba-194">When the Outlook Junk Email Filter is set to **Low** or **High** , the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="de7ba-195">此垃圾邮件分类与由 EOP 确定的 SCL)  (的垃圾邮件信任级别不同。</span><span class="sxs-lookup"><span data-stu-id="de7ba-195">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="de7ba-196">事实上，除非 EOP 将邮件标记为跳过垃圾邮件) 筛选，否则 Outlook 将忽略 EOP (中的 SCL，并使用其自己的条件来确定邮件是否为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="de7ba-196">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="de7ba-197">当然，可能会出现来自 EOP 和 Outlook 的垃圾邮件结论。</span><span class="sxs-lookup"><span data-stu-id="de7ba-197">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="de7ba-198">有关这些设置的详细信息，请参阅在 [垃圾邮件筛选器中更改保护级别](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-198">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="de7ba-199">在2016年11月，Microsoft 已停止为 Exchange 和 Outlook 中的 SmartScreen 筛选器生成垃圾邮件定义更新。</span><span class="sxs-lookup"><span data-stu-id="de7ba-199">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="de7ba-200">现有的 SmartScreen 垃圾邮件定义保留不变，但其有效性可能会随着时间的推移而下降。</span><span class="sxs-lookup"><span data-stu-id="de7ba-200">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="de7ba-201">有关详细信息，请参阅“[停止为 Outlook 和 Exchange 中的 SmartScreen 提供支持](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)”。</span><span class="sxs-lookup"><span data-stu-id="de7ba-201">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="de7ba-202">因此，Outlook 垃圾邮件筛选器能够使用邮箱的安全列表集合及其自己的垃圾邮件分类将邮件移动到 "垃圾邮件" 文件夹，即使邮箱中禁用了垃圾邮件规则也是如此。</span><span class="sxs-lookup"><span data-stu-id="de7ba-202">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="de7ba-203">Outlook 和 Web 上的 Outlook 同等支持安全列表集合。</span><span class="sxs-lookup"><span data-stu-id="de7ba-203">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="de7ba-204">安全列表集合保存在 Exchange Online 邮箱中，因此对 Outlook 中的安全列表集合的更改会显示在 web 上的 Outlook 中，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="de7ba-204">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

## <a name="limits-for-junk-email-settings"></a><span data-ttu-id="de7ba-205">垃圾邮件设置的限制</span><span class="sxs-lookup"><span data-stu-id="de7ba-205">Limits for junk email settings</span></span>

<span data-ttu-id="de7ba-206">用户邮箱中存储的安全发件人列表、安全收件人列表和阻止发件人列表) 的安全列表集合 (也会同步到 EOP。</span><span class="sxs-lookup"><span data-stu-id="de7ba-206">The safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) that's stored in the user's mailbox is also synchronized to EOP.</span></span> <span data-ttu-id="de7ba-207">通过目录同步，安全列表集合将同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="de7ba-207">With directory synchronization, the safelist collection is synchronized to Azure AD.</span></span>

- <span data-ttu-id="de7ba-208">用户邮箱中的安全列表集合的限制为 510 KB，其中包含所有列表以及其他垃圾邮件筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="de7ba-208">The safelist collection in the user's mailbox has a limit of 510 KB, which includes all lists, plus additional junk email filter settings.</span></span> <span data-ttu-id="de7ba-209">如果用户超过此限制，将收到如下所示的 Outlook 错误：</span><span class="sxs-lookup"><span data-stu-id="de7ba-209">If a user exceeds this limit, they will receive an Outlook error that looks like this:</span></span>

  > <span data-ttu-id="de7ba-210">无法/无法将添加到 "垃圾邮件" 的服务器列表。</span><span class="sxs-lookup"><span data-stu-id="de7ba-210">Cannot/Unable add to the server Junk E-mail lists.</span></span> <span data-ttu-id="de7ba-211">您已超出服务器允许的大小。</span><span class="sxs-lookup"><span data-stu-id="de7ba-211">You are over the size allowed on the server.</span></span> <span data-ttu-id="de7ba-212">服务器上的垃圾邮件筛选器将被禁用，直到垃圾邮件列表缩小到服务器允许的大小。</span><span class="sxs-lookup"><span data-stu-id="de7ba-212">The Junk E-mail filter on the server will be disabled until your Junk E-mail lists have been reduced to the size allowed by the server.</span></span>

  <span data-ttu-id="de7ba-213">有关此限制以及如何更改此限制的详细信息，请参阅 [KB2669081](https://support.microsoft.com/help/2669081)。</span><span class="sxs-lookup"><span data-stu-id="de7ba-213">For more information about this limit and how to change it, see [KB2669081](https://support.microsoft.com/help/2669081).</span></span>

- <span data-ttu-id="de7ba-214">EOP 中的同步安全列表集合具有以下同步限制：</span><span class="sxs-lookup"><span data-stu-id="de7ba-214">The synchronized safelist collection in EOP has the following synchronization limits:</span></span>

  - <span data-ttu-id="de7ba-215">1024如果启用了 **"来自我的联系人的信任电子邮件** "，则安全发件人列表、安全收件人列表和外部联系人中的条目总数。</span><span class="sxs-lookup"><span data-stu-id="de7ba-215">1024 total entries in the Safe Senders list, the Safe Recipients list, and external contacts if **Trust email from my contacts** is enabled.</span></span>
  - <span data-ttu-id="de7ba-216">500阻止的发件人列表和阻止的域列表中的条目总数。</span><span class="sxs-lookup"><span data-stu-id="de7ba-216">500 total entries in the Blocked Senders list and Blocked Domains list.</span></span>

  <span data-ttu-id="de7ba-217">达到1024项限制时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="de7ba-217">When the 1024 entry limit is reached, the following things happen:</span></span>

  - <span data-ttu-id="de7ba-218">该列表将停止接受 PowerShell 中的条目和 web 上的 Outlook，但不会显示任何错误。</span><span class="sxs-lookup"><span data-stu-id="de7ba-218">The list stops accepting entries in PowerShell and Outlook on the web, but no error is displayed.</span></span>

    <span data-ttu-id="de7ba-219">Outlook 用户可以继续添加1024个以上的条目，直到达到 Outlook 限制值 510 KB。</span><span class="sxs-lookup"><span data-stu-id="de7ba-219">Outlook users can continue to add more than 1024 entries until they reach the Outlook limit of 510 KB.</span></span> <span data-ttu-id="de7ba-220">Outlook 可以使用这些额外的条目，只要 EOP 筛选器在传递到邮箱 (邮件流规则、反欺骗等 ) 之前不会阻止邮件。</span><span class="sxs-lookup"><span data-stu-id="de7ba-220">Outlook can use these additional entries, as long as an EOP filter doesn't block the message before delivery to the mailbox (mail flow rules, anti-spoofing, etc.).</span></span>

- <span data-ttu-id="de7ba-221">通过目录同步，这些项将按以下顺序同步到 Azure AD：</span><span class="sxs-lookup"><span data-stu-id="de7ba-221">With directory synchronization, the entries are synchronized to Azure AD in the following order:</span></span>

  1. <span data-ttu-id="de7ba-222">如果启用了 **"来自我的联系人的信任电子邮件"** ，则为邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="de7ba-222">Mail contacts if **Trust email from my contacts** is enabled.</span></span>
  2. <span data-ttu-id="de7ba-223">只要对前1024个条目进行了更改，就会对安全发件人列表和安全收件人列表进行组合、消除重复并按字母顺序对其进行排序。</span><span class="sxs-lookup"><span data-stu-id="de7ba-223">The Safe Sender list and Safe Recipient list are combined, de-duplicated, and sorted alphabetically whenever a change is made for the first 1024 entries.</span></span>

  <span data-ttu-id="de7ba-224">使用前1024个条目，并在邮件头中标记相关信息。</span><span class="sxs-lookup"><span data-stu-id="de7ba-224">The first 1024 entries are used, and relevant information is stamped in the message headers.</span></span>

  <span data-ttu-id="de7ba-225">1024以上未同步到 Azure AD 的条目是由 Outlook (不是 Outlook 在 web) 上进行处理的，并且在邮件头中不标记任何信息。</span><span class="sxs-lookup"><span data-stu-id="de7ba-225">Entries over 1024 that weren't synchronized to Azure AD are processed by Outlook (not Outlook on the web), and no information is stamped in the message headers.</span></span>

<span data-ttu-id="de7ba-226">您可以看到，启用 " **来自我的联系人的信任电子邮件** " 设置可以减少可同步的安全发件人和安全收件人的数量。</span><span class="sxs-lookup"><span data-stu-id="de7ba-226">As you can see, enabling the **Trust email from my contacts** setting reduces the number of Safe Senders and Safe Recipients that can be synchronized.</span></span> <span data-ttu-id="de7ba-227">如果这是个问题，我们建议使用组策略关闭此功能：</span><span class="sxs-lookup"><span data-stu-id="de7ba-227">If this is a concern, then we recommend using Group Policy to turn this feature off:</span></span>

- <span data-ttu-id="de7ba-228">文件名： outlk16。 opax</span><span class="sxs-lookup"><span data-stu-id="de7ba-228">File name: outlk16.opax</span></span>
- <span data-ttu-id="de7ba-229">策略设置： **信任来自联系人的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="de7ba-229">Policy setting: **Trust e-mail from contacts**</span></span>
