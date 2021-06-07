---
title: 管理员审阅报告邮件
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 了解如何查看报告的消息，并为用户提供反馈。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7386f5b283e2bfabb76eee91d33dfda0e42ec7b1
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769121"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="2d326-103">管理员审阅报告邮件</span><span class="sxs-lookup"><span data-stu-id="2d326-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="2d326-104">本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。</span><span class="sxs-lookup"><span data-stu-id="2d326-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2d326-105">本文档仅供评估和探索之用。</span><span class="sxs-lookup"><span data-stu-id="2d326-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="2d326-106">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2d326-106">**Applies to**</span></span>
- [<span data-ttu-id="2d326-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2d326-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2d326-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d326-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2d326-109">在Microsoft 365邮箱Exchange Online Microsoft Defender for Office 365 的组织中，管理员现在可以在查看报告的邮件后将模板邮件发送回最终用户。</span><span class="sxs-lookup"><span data-stu-id="2d326-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="2d326-110">这可以根据管理员裁定针对你的组织进行自定义。</span><span class="sxs-lookup"><span data-stu-id="2d326-110">This can be customized for your organization and based on your admin’s verdict as well.</span></span>

<span data-ttu-id="2d326-111">此功能旨在为用户提供反馈，但不更改系统中邮件裁定。</span><span class="sxs-lookup"><span data-stu-id="2d326-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="2d326-112">为了帮助 Microsoft 更新和改进其筛选器，你将需要使用管理员提交 提交[邮件进行分析。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="2d326-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="2d326-113">只有在邮件被报告为误报或漏报时，你才能标记和通知 [用户审阅结果](report-false-positives-and-false-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="2d326-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2d326-114">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2d326-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2d326-115">若要修改用户提交的配置，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="2d326-115">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="2d326-116">组织管理或安全中心[Microsoft 365管理员](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2d326-116">Organization Management or Security Administrator in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="2d326-117">中的组织[Exchange Online。](/Exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="2d326-117">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span></span>

- <span data-ttu-id="2d326-118">你还需要访问 PowerShell Exchange Online权限。</span><span class="sxs-lookup"><span data-stu-id="2d326-118">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="2d326-119">如果您尝试使用的帐户无法访问 Exchange Online PowerShell，您将收到错误消息，指出"在域中指定 *电子邮件地址"。*</span><span class="sxs-lookup"><span data-stu-id="2d326-119">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="2d326-120">有关启用或禁用对 PowerShell Exchange Online，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="2d326-120">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="2d326-121">启用或禁用对 Exchange Online PowerShell 的访问</span><span class="sxs-lookup"><span data-stu-id="2d326-121">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="2d326-122">客户端访问规则Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2d326-122">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="2d326-123">配置用于通知用户的消息</span><span class="sxs-lookup"><span data-stu-id="2d326-123">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="2d326-124">在安全 [Microsoft 365中](../defender/overview-security-center.md)，转到"策略 **"&"** \> **威胁策略** \> **""用户报告的邮件设置"。**</span><span class="sxs-lookup"><span data-stu-id="2d326-124">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Policies & rules** \> **Threat policies** \> **User reported message settings**.</span></span>

2. <span data-ttu-id="2d326-125">如果要指定发件人显示名称，请选中"管理员审阅结果的电子邮件通知"部分下的"指定要用作发件人的 **Office 365** 电子邮件地址"框，然后输入想要使用的名称。</span><span class="sxs-lookup"><span data-stu-id="2d326-125">If you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="2d326-126">这是将在电子邮件中显示的电子邮件地址Outlook以及答复将转到的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2d326-126">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="2d326-127">如果要自定义任何模板，请单击"**自定义电子邮件通知"。**</span><span class="sxs-lookup"><span data-stu-id="2d326-127">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="2d326-128">在此飞出中，你只能自定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="2d326-128">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="2d326-129">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="2d326-129">Phishing</span></span>
    - <span data-ttu-id="2d326-130">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2d326-130">Junk</span></span>
    - <span data-ttu-id="2d326-131">未发现威胁</span><span class="sxs-lookup"><span data-stu-id="2d326-131">No threats found</span></span>
    - <span data-ttu-id="2d326-132">意识培训</span><span class="sxs-lookup"><span data-stu-id="2d326-132">Awareness training</span></span>
    - <span data-ttu-id="2d326-133">页脚</span><span class="sxs-lookup"><span data-stu-id="2d326-133">Footer</span></span>

4. <span data-ttu-id="2d326-134">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="2d326-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="2d326-135">若要清除这些值，请单击" **用户提交** "页面上的"放弃"。</span><span class="sxs-lookup"><span data-stu-id="2d326-135">To clear these values, click **Discard** on the User submissions page.</span></span>
