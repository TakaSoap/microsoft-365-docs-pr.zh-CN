---
title: Exchange Online 中的安全发件人和阻止发件人列表
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: 作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。
ms.openlocfilehash: 9c281460aeff64226343af5e5608ccf42fc83799
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238389"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="50a46-104">Exchange Online 中的安全发件人和阻止发件人列表</span><span class="sxs-lookup"><span data-stu-id="50a46-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="50a46-p102">作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。</span><span class="sxs-lookup"><span data-stu-id="50a46-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="50a46-107">若要了解如何在 Office 365 中将电子邮件标记为垃圾邮件，*请参阅更新版本的提示和过程。有关如何在* [Office 中阻止将电子邮件标记为垃圾邮件](prevent-email-from-being-marked-as-spam.md)的管理员。</span><span class="sxs-lookup"><span data-stu-id="50a46-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="50a46-108">如果你不是管理员，并且只想使用安全发件人列表在 Outlook 中管理自己的垃圾邮件，请查看[垃圾邮件筛选器概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="50a46-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="50a46-109">Exchange Online 中的安全发件人限制和阻止发件人限制是什么？</span><span class="sxs-lookup"><span data-stu-id="50a46-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="50a46-p103">Exchange Online 中的安全发件人限制和阻止发件人限制与 Active Directory 和 Outlook 限制不同。区别在于：</span><span class="sxs-lookup"><span data-stu-id="50a46-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>

- <span data-ttu-id="50a46-112">安全发件人限制：1024</span><span class="sxs-lookup"><span data-stu-id="50a46-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="50a46-113">阻止的发件人限制：500</span><span class="sxs-lookup"><span data-stu-id="50a46-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="50a46-114">注意：</span><span class="sxs-lookup"><span data-stu-id="50a46-114">Note:</span></span>

<span data-ttu-id="50a46-115">您可能会遇到[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)中所述的错误。</span><span class="sxs-lookup"><span data-stu-id="50a46-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="50a46-116">若要解决此问题，请清除 "信任来自我的联系人的电子邮件" 复选框。</span><span class="sxs-lookup"><span data-stu-id="50a46-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="50a46-117">或者，减少默认 "联系人" 文件夹中的电子邮件地址量，使其在 Exchange Online 中为 "MaxSafeSenders" 属性设置的最大允许限制为1024。</span><span class="sxs-lookup"><span data-stu-id="50a46-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="50a46-118">有关此属性和 Set 邮箱 cmdlet 的详细信息，请 seethe 以下主题：</span><span class="sxs-lookup"><span data-stu-id="50a46-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="50a46-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="50a46-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="50a46-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50a46-120">See also</span></span>

[<span data-ttu-id="50a46-121">Exchange Server 中的发件人筛选</span><span class="sxs-lookup"><span data-stu-id="50a46-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
