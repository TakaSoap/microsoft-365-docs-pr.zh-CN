---
title: 在 Exchange Online 中配置最终用户垃圾邮件通知
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 您可以为适用于域的默认公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: f7ef916eea8d9c926f53ef073874dfb299cb92f8
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957387"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="fe78b-103">在 Exchange Online 中配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="fe78b-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe78b-104">该主题适用于希望保护在云中托管的邮箱的 Exchange Online 客户。</span><span class="sxs-lookup"><span data-stu-id="fe78b-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="fe78b-105">Exchange Online Protection （EOP）保护本地邮箱的独立客户应阅读以下主题：[在 EOP 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="fe78b-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="fe78b-106">您可以为默认的公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="fe78b-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="fe78b-107">启用最终用户垃圾邮件通知邮件，使用户可以管理其自己的隔离垃圾邮件、批量邮件和网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="fe78b-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span>   
  
<span data-ttu-id="fe78b-p103">最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。</span><span class="sxs-lookup"><span data-stu-id="fe78b-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="fe78b-110">收到通知邮件后，最终用户可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="fe78b-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="fe78b-111">如果希望 Office 365 将发件人添加到阻止发件人列表，请**阻止发件人**。</span><span class="sxs-lookup"><span data-stu-id="fe78b-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="fe78b-112">如果邮件不是垃圾邮件，并且您希望 Office 365 将邮件发送到您的邮箱，则**释放**。</span><span class="sxs-lookup"><span data-stu-id="fe78b-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="fe78b-113">如果要执行其他操作，如预览或发布，请**查看**以导航到安全 & 合规性中心内的隔离门户。</span><span class="sxs-lookup"><span data-stu-id="fe78b-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fe78b-114">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="fe78b-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="fe78b-115">估计完成时间：2 分钟</span><span class="sxs-lookup"><span data-stu-id="fe78b-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="fe78b-116">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="fe78b-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="fe78b-117">若要查看所需的权限，请参阅[Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)主题中的 "反垃圾邮件" 条目。</span><span class="sxs-lookup"><span data-stu-id="fe78b-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="fe78b-118">有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="fe78b-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="fe78b-119">使用 EAC 配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="fe78b-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="fe78b-120">在 Exchange 管理中心（EAC）中，导航到 "**保护** \> **垃圾邮件筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="fe78b-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="fe78b-121">选择要为其启用最终用户垃圾邮件通知的垃圾邮件筛选器策略（默认情况下禁用）。</span><span class="sxs-lookup"><span data-stu-id="fe78b-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="fe78b-122">在显示您的策略摘要信息的右窗格中，单击“配置最终用户垃圾邮件通知”\*\*\*\* 链接。</span><span class="sxs-lookup"><span data-stu-id="fe78b-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="fe78b-123">在随后出现的对话框中，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="fe78b-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="fe78b-124">**启用最终用户垃圾邮件通知**选中此复选框，以便为此策略启用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="fe78b-124">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="fe78b-125">）</span><span class="sxs-lookup"><span data-stu-id="fe78b-125">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="fe78b-126">**每隔（天）发送最终用户垃圾邮件通知**指定发送最终用户垃圾邮件通知的频率。</span><span class="sxs-lookup"><span data-stu-id="fe78b-126">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="fe78b-127">默认值为 3 天。</span><span class="sxs-lookup"><span data-stu-id="fe78b-127">The default is 3 days.</span></span> <span data-ttu-id="fe78b-128">您可以指定一个介于 1 到 15 天之间的值。</span><span class="sxs-lookup"><span data-stu-id="fe78b-128">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="fe78b-129">例如，如果您指定 7 天，则该通知将包括在过去 7 天内预期发送给该用户但实际发送到垃圾邮件隔离邮箱的所有邮件列表。</span><span class="sxs-lookup"><span data-stu-id="fe78b-129">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="fe78b-130">**通知语言**使用下拉列表，选择为此策略编写最终用户垃圾邮件通知所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="fe78b-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="fe78b-131">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fe78b-131">Click **Save**.</span></span> <span data-ttu-id="fe78b-132">在右侧窗格中将显示垃圾邮件筛选器策略设置的摘要，包括您的最终用户垃圾邮件通知设置。</span><span class="sxs-lookup"><span data-stu-id="fe78b-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="fe78b-133">最终用户垃圾邮件通知将仅适用于启用的垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="fe78b-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="fe78b-134">>  每天只发送一次最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="fe78b-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="fe78b-135">无法保证和配置任何特定客户的通知发送时间。</span><span class="sxs-lookup"><span data-stu-id="fe78b-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="fe78b-136">**提示：** 如果要在完全实现最终用户垃圾邮件通知之前将其发送给一组有限的用户，请创建自定义垃圾邮件筛选器策略，为用户驻留的域启用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="fe78b-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="fe78b-137">然后，在 EAC 中的 "**邮件流\>规则**" 下，创建邮件流规则（也称为传输规则），以阻止来自 quarantine@messaging.microsoft.com （发送通知的电子邮件地址）的邮件，但要接收通知的用户例外。</span><span class="sxs-lookup"><span data-stu-id="fe78b-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="fe78b-138">下图是为 Contoso.com 域中的两个用户（SaraD 和 AlexD）创建一个异常的示例：</span><span class="sxs-lookup"><span data-stu-id="fe78b-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![测试最终用户垃圾邮件通知的传输规则](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="fe78b-140">使用 SCC 配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="fe78b-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="fe78b-141">您还可以使用安全与合规中心（SCC）配置最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="fe78b-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="fe78b-142">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="fe78b-142">Follow these steps:</span></span>

1. <span data-ttu-id="fe78b-143">打开 "安全与合规中心"，导航到 "**威胁管理** \> **策略** \> **反垃圾邮件**" 或 " https://protection.office.com/antispam使用直接链接"。</span><span class="sxs-lookup"><span data-stu-id="fe78b-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="fe78b-144">单击要为其启用最终用户垃圾邮件通知的垃圾邮件筛选器策略旁边的向下箭头。</span><span class="sxs-lookup"><span data-stu-id="fe78b-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="fe78b-145">单击 "**配置最终用户垃圾邮件通知**" 链接。</span><span class="sxs-lookup"><span data-stu-id="fe78b-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="fe78b-146">在随后出现的对话框中，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="fe78b-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="fe78b-147">**启用最终用户垃圾邮件通知**选中此复选框，以便为此策略启用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="fe78b-147">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="fe78b-148">）</span><span class="sxs-lookup"><span data-stu-id="fe78b-148">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="fe78b-149">**每隔（天）发送最终用户垃圾邮件通知**指定发送最终用户垃圾邮件通知的频率。</span><span class="sxs-lookup"><span data-stu-id="fe78b-149">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="fe78b-150">默认值为 3 天。</span><span class="sxs-lookup"><span data-stu-id="fe78b-150">The default is 3 days.</span></span> <span data-ttu-id="fe78b-151">您可以指定一个介于 1 到 15 天之间的值。</span><span class="sxs-lookup"><span data-stu-id="fe78b-151">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="fe78b-152">例如，如果您指定 7 天，则该通知将包括在过去 7 天内预期发送给该用户但实际发送到垃圾邮件隔离邮箱的所有邮件列表。</span><span class="sxs-lookup"><span data-stu-id="fe78b-152">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="fe78b-153">**通知语言**使用下拉列表，选择为此策略编写最终用户垃圾邮件通知所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="fe78b-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="fe78b-154">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fe78b-154">Click **Save**.</span></span> <span data-ttu-id="fe78b-155">包含最终用户垃圾邮件通知设置的垃圾邮件筛选器策略设置摘要将显示在 "" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="fe78b-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="fe78b-156">更多信息</span><span class="sxs-lookup"><span data-stu-id="fe78b-156">For more information</span></span>

[<span data-ttu-id="fe78b-157">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="fe78b-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
