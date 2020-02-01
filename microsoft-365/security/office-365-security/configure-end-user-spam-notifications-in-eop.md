---
title: 在 EOP 中配置最终用户垃圾邮件通知
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
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: 您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: 2bbeaf48fc0d17b2df97f794956b65e090a06e1d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599639"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="00414-103">在 EOP 中配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="00414-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="00414-104">该主题适用于要保护本地邮箱的 Exchange Online Protection (EOP) 独立客户。</span><span class="sxs-lookup"><span data-stu-id="00414-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="00414-105">正在保护云托管邮箱的 Exchange Online 客户应阅读以下主题：[在 Exchange Online 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="00414-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="00414-106">您可以为默认的公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="00414-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="00414-107">启用最终用户垃圾邮件通知邮件，使用户可以管理自己的垃圾邮件隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="00414-107">Enabling end-user spam notification messages lets your users manage their own spam-quarantined messages.</span></span> 
  
<span data-ttu-id="00414-p103">最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。</span><span class="sxs-lookup"><span data-stu-id="00414-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="00414-110">收到通知邮件后，最终用户可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="00414-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="00414-111">如果希望 Office 365 将发件人添加到阻止发件人列表，请**阻止发件人**。</span><span class="sxs-lookup"><span data-stu-id="00414-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="00414-112">如果邮件不是垃圾邮件，并且您希望 Office 365 将邮件发送到您的邮箱，则**释放**。</span><span class="sxs-lookup"><span data-stu-id="00414-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="00414-113">如果要执行其他操作，如预览或发布，请**查看**以导航到安全与合规中心内的隔离门户。</span><span class="sxs-lookup"><span data-stu-id="00414-113">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="00414-114">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="00414-114">What do you need to know before you begin?</span></span>
<span data-ttu-id="00414-115"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="00414-115"><a name="sectionSection0"> </a></span></span>

<span data-ttu-id="00414-116">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="00414-116">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="00414-p104">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"反垃圾邮件"条目。</span><span class="sxs-lookup"><span data-stu-id="00414-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="00414-119">有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="00414-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="00414-120">使用 EAC 配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="00414-120">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="00414-121">在 Exchange 管理中心（EAC）中，导航到 "**保护** > **垃圾邮件筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="00414-121">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="00414-122">选择您想要启用最终用户垃圾邮件通知（默认禁用）的内容筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="00414-122">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="00414-123">在显示您的策略摘要信息的右窗格中，单击“配置最终用户垃圾邮件通知”\*\*\*\* 链接。</span><span class="sxs-lookup"><span data-stu-id="00414-123">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="00414-124">在随后出现的对话框中，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="00414-124">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="00414-125">**启用最终用户垃圾邮件通知**选中此复选框，以便为此策略启用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="00414-125">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="00414-126">）</span><span class="sxs-lookup"><span data-stu-id="00414-126">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="00414-127">**每隔（天）发送最终用户垃圾邮件通知**指定发送最终用户垃圾邮件通知的频率。</span><span class="sxs-lookup"><span data-stu-id="00414-127">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="00414-128">默认值为 3 天。</span><span class="sxs-lookup"><span data-stu-id="00414-128">The default is 3 days.</span></span> <span data-ttu-id="00414-129">您可以指定一个介于 1 到 15 天之间的值。</span><span class="sxs-lookup"><span data-stu-id="00414-129">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="00414-130">例如，如果您指定 7 天，则该通知将包括在过去 7 天内预期发送给该用户但实际发送到垃圾邮件隔离邮箱的所有邮件列表。</span><span class="sxs-lookup"><span data-stu-id="00414-130">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="00414-131">**通知语言**使用下拉列表，选择为此策略编写最终用户垃圾邮件通知所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="00414-131">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="00414-132">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00414-132">Click **save**.</span></span> <span data-ttu-id="00414-133">右窗格中将显示内容筛选器策略设置的摘要，包括您的最终用户垃圾邮件通知设置。</span><span class="sxs-lookup"><span data-stu-id="00414-133">A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="00414-p108">最终用户垃圾邮件通知只对已启用的内容筛选器策略可用。 >  每天只发送一次最终用户垃圾邮件通知。无法保证和配置任何特定客户的通知发送时间。</span><span class="sxs-lookup"><span data-stu-id="00414-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="00414-137">**提示：** 如果要在完全实现最终用户垃圾邮件通知之前将其发送给一组有限的用户，请创建自定义内容筛选器策略，为用户驻留的域启用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="00414-137">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="00414-138">然后，在 EAC 中的 "**邮件流\>规则**" 下，创建邮件流规则（也称为传输规则），以阻止来自 quarantine@messaging.microsoft.com （发送通知的电子邮件地址）的邮件，但要接收通知的用户例外。</span><span class="sxs-lookup"><span data-stu-id="00414-138">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="00414-139">下图是为 Contoso.com 域中的两个用户（SaraD 和 AlexD）创建一个异常的示例：</span><span class="sxs-lookup"><span data-stu-id="00414-139">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![测试最终用户垃圾邮件通知的传输规则](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="00414-141">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="00414-141">For more information</span></span>

[<span data-ttu-id="00414-142">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="00414-142">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
