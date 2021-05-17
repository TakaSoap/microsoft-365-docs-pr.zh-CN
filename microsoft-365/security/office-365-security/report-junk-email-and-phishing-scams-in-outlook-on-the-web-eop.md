---
title: 报告 Web 上Outlook垃圾邮件和钓鱼电子邮件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online 中 Outlook 网页 (Outlook Web App) 中的内置垃圾邮件报告选项、非垃圾邮件和网络钓鱼电子邮件报告选项，以及如何为用户禁用这些报告选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615205"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="dc198-103">在电子邮件中报告Outlook网页中的垃圾邮件Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dc198-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dc198-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="dc198-104">**Applies to**</span></span>
- [<span data-ttu-id="dc198-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dc198-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="dc198-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="dc198-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="dc198-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc198-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="dc198-108">在 Microsoft 365 组织中，如果邮箱位于 Exchange Online 或本地邮箱使用混合新式身份验证，可以将[](../../enterprise/hybrid-modern-auth-overview.md)误报 (标记为垃圾邮件) 、漏报 (允许的) 错误电子邮件以及网络钓鱼邮件提交到 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="dc198-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dc198-109">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="dc198-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dc198-110">为了获得最佳用户提交体验，我们建议使用报告邮件和报告网络钓鱼外接程序。有关详细信息 [，请参阅启用报告邮件](./enable-the-report-message-add-in.md) 外接程序 [和启用报告](./enable-the-report-phish-add-in.md) 网络钓鱼外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc198-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="dc198-111">如果你是拥有多个邮箱Exchange Online管理员，我们建议你使用安全与合规中心&提交门户。</span><span class="sxs-lookup"><span data-stu-id="dc198-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="dc198-112">有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="dc198-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="dc198-113">管理员可以禁用或启用用户在 Web 上向 Microsoft 报告Outlook功能。</span><span class="sxs-lookup"><span data-stu-id="dc198-113">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="dc198-114">有关详细信息，请参阅本文稍后介绍的在 web Outlook[中](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)禁用或启用垃圾邮件报告部分。</span><span class="sxs-lookup"><span data-stu-id="dc198-114">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="dc198-115">可以将报告的邮件配置为复制或重定向到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="dc198-115">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="dc198-116">有关详细信息，请参阅用户 [提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="dc198-116">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="dc198-117">有关向 Microsoft 报告邮件的信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="dc198-117">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="dc198-118">禁用或启用 Web 上Outlook垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="dc198-118">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="dc198-119">默认情况下，用户可以将垃圾邮件误报、漏报和钓鱼邮件报告给 Microsoft，以便Outlook中进行分析。</span><span class="sxs-lookup"><span data-stu-id="dc198-119">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="dc198-120">管理员可以在 PowerShell Outlook Web 邮箱策略Exchange Online，以防止用户向 Microsoft 报告垃圾邮件误报和垃圾邮件漏报。</span><span class="sxs-lookup"><span data-stu-id="dc198-120">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="dc198-121">无法禁用用户向 Microsoft 报告网络钓鱼邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="dc198-121">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dc198-122">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="dc198-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dc198-123">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dc198-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="dc198-124">您需在 Exchange Online权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="dc198-124">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="dc198-125">具体来说，您需要 **收件人策略** 或 **邮件收件人** 角色，这些角色默认分配给组织管理角色组和 **收件人** 管理角色组。</span><span class="sxs-lookup"><span data-stu-id="dc198-125">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="dc198-126">有关角色组中角色组Exchange Online，请参阅 Exchange Online[中的权限](/exchange/permissions-exo/permissions-exo)和修改[角色Exchange Online。](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="dc198-126">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="dc198-127">每个组织都有一个名为 OwaMailboxPolicy-Default 的默认策略，但您可以创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="dc198-127">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="dc198-128">自定义策略应用于默认策略之前的范围用户。</span><span class="sxs-lookup"><span data-stu-id="dc198-128">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="dc198-129">有关 Web 邮箱策略Outlook，请参阅 Outlook 中的[Web 邮箱策略Exchange Online。](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="dc198-129">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="dc198-130">禁用垃圾邮件报告不会删除在 Web 上的垃圾邮件中将Outlook标记为垃圾邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="dc198-130">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="dc198-131">选择"垃圾邮件"文件夹中的邮件并单击"**非** 垃圾邮件""非垃圾邮件"仍将 \> 该邮件移回收件箱。</span><span class="sxs-lookup"><span data-stu-id="dc198-131">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="dc198-132">选择任何其他电子邮件文件夹中的邮件并单击 **"垃圾邮件**"仍将 \> 该邮件移动到"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dc198-132">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="dc198-133">不再可用的是向 Microsoft 报告邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="dc198-133">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="dc198-134">使用 Exchange Online PowerShell 禁用或启用 Web 上Outlook垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="dc198-134">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="dc198-135">若要查找现有Outlook Web 邮箱策略和垃圾邮件报告状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dc198-135">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="dc198-136">若要在 Web 上的Outlook或启用垃圾邮件报告，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="dc198-136">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="dc198-137">本示例在默认策略中禁用垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="dc198-137">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="dc198-138">此示例在名为 Contoso Managers 的自定义策略中启用垃圾邮件报告。</span><span class="sxs-lookup"><span data-stu-id="dc198-138">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="dc198-139">有关语法和参数的详细信息，请参阅[Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy)和[Set-OwaMailboxPolicy。](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="dc198-139">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="dc198-140">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="dc198-140">How do you know this worked?</span></span>

<span data-ttu-id="dc198-141">若要验证您是否已成功启用或禁用 Web 上的Outlook垃圾邮件报告，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="dc198-141">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="dc198-142">在 Exchange Online PowerShell 中，运行以下命令并验证 **ReportJunkEmailEnabled** 属性值：</span><span class="sxs-lookup"><span data-stu-id="dc198-142">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="dc198-143">在 Web 上的 Outlook 中打开受影响的用户的邮箱，选择"收件箱"中的邮件，单击"垃圾邮件"并验证向 Microsoft 报告邮件的 \> 提示是否显示。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dc198-143">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="dc198-144">在 Web 上的 Outlook 中打开受影响的用户的邮箱，选择"垃圾邮件"文件夹中的邮件，单击"垃圾邮件"并验证向 Microsoft 报告邮件的 \> 提示是否显示。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dc198-144">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="dc198-145"><sup>\*</sup> 用户可以隐藏报告邮件的提示，同时仍报告邮件。</span><span class="sxs-lookup"><span data-stu-id="dc198-145"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="dc198-146">若要在 Web Outlook中检查此设置：</span><span class="sxs-lookup"><span data-stu-id="dc198-146">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="dc198-147">单击 ![ 设置Outlook"Web 设置"图标"查看所有Outlook ](../../media/owa-settings-icon.png) \> **设置** \> **垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="dc198-147">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="dc198-148">在" **报告** "部分，验证值： **在发送报告之前询问我**。</span><span class="sxs-lookup"><span data-stu-id="dc198-148">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook垃圾邮件报告设置](../../media/owa-junk-email-reporting-options.png)