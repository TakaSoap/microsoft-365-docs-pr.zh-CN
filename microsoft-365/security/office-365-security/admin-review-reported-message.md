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
ms.openlocfilehash: 9e6969b6dee38135ee2d1d41bbcdb2561943d1fe
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878708"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="b0e61-103">管理员审阅报告邮件</span><span class="sxs-lookup"><span data-stu-id="b0e61-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="b0e61-104">本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。</span><span class="sxs-lookup"><span data-stu-id="b0e61-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b0e61-105">本文档仅供评估和探索之用。</span><span class="sxs-lookup"><span data-stu-id="b0e61-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="b0e61-106">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="b0e61-106">**Applies to**</span></span>
- [<span data-ttu-id="b0e61-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="b0e61-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b0e61-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0e61-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b0e61-109">在Microsoft 365邮箱Exchange Online Microsoft Defender for Office 365 的组织中，管理员现在可以在查看报告的邮件后将模板邮件发送回最终用户。</span><span class="sxs-lookup"><span data-stu-id="b0e61-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="b0e61-110">这可以根据管理员裁定针对你的组织进行自定义。</span><span class="sxs-lookup"><span data-stu-id="b0e61-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="b0e61-111">此功能旨在为用户提供反馈，但不更改系统中邮件裁定。</span><span class="sxs-lookup"><span data-stu-id="b0e61-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="b0e61-112">为了帮助 Microsoft 更新和改进其筛选器，你将需要使用管理员提交 提交[邮件进行分析。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="b0e61-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="b0e61-113">只有在邮件被报告为误报或漏报时，你才能标记和通知 [用户审阅结果](report-false-positives-and-false-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e61-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b0e61-114">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b0e61-114">What do you need to know before you begin?</span></span>


- <span data-ttu-id="b0e61-115">在 打开Microsoft 365安全中心 <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="b0e61-115">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="b0e61-116">若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="b0e61-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="b0e61-117">若要修改用户提交的配置，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="b0e61-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="b0e61-118">组织管理或安全中心[Microsoft 365管理员](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e61-118">Organization Management or Security Administrator in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="b0e61-119">中的组织[Exchange Online。](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="b0e61-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>


- <span data-ttu-id="b0e61-120">你还需要访问 PowerShell Exchange Online权限。</span><span class="sxs-lookup"><span data-stu-id="b0e61-120">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="b0e61-121">如果您尝试使用的帐户无法访问 Exchange Online PowerShell，您将收到错误消息，指出"在域中指定 *电子邮件地址"。*</span><span class="sxs-lookup"><span data-stu-id="b0e61-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="b0e61-122">有关启用或禁用对 PowerShell Exchange Online，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b0e61-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="b0e61-123">启用或禁用对 Exchange Online PowerShell 的访问</span><span class="sxs-lookup"><span data-stu-id="b0e61-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="b0e61-124">客户端访问规则Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b0e61-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="b0e61-125">配置用于通知用户的消息</span><span class="sxs-lookup"><span data-stu-id="b0e61-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="b0e61-126">In the Microsoft 365 Defender portal， go to **Email & collaboration Policies** & \> **rules** Threat \> **policies** \> **Others** section User \> **reported message settings**.</span><span class="sxs-lookup"><span data-stu-id="b0e61-126">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="b0e61-127">在"用户提交"页面上，如果要指定发件人 显示名称，请选中"管理员审阅结果的电子邮件通知"部分下的"指定要用作发件人的 **Office 365** 电子邮件地址"框，然后输入想要使用的名称。</span><span class="sxs-lookup"><span data-stu-id="b0e61-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="b0e61-128">这是将在电子邮件中显示的电子邮件地址Outlook以及答复将转到的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b0e61-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="b0e61-129">如果要自定义任何模板，请单击"**自定义电子邮件通知"。**</span><span class="sxs-lookup"><span data-stu-id="b0e61-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="b0e61-130">在此飞出中，你只能自定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="b0e61-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="b0e61-131">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="b0e61-131">Phishing</span></span>
    - <span data-ttu-id="b0e61-132">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="b0e61-132">Junk</span></span>
    - <span data-ttu-id="b0e61-133">未发现威胁</span><span class="sxs-lookup"><span data-stu-id="b0e61-133">No threats found</span></span>
    - <span data-ttu-id="b0e61-134">意识培训</span><span class="sxs-lookup"><span data-stu-id="b0e61-134">Awareness training</span></span>
    - <span data-ttu-id="b0e61-135">页脚</span><span class="sxs-lookup"><span data-stu-id="b0e61-135">Footer</span></span>

4. <span data-ttu-id="b0e61-136">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="b0e61-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="b0e61-137">若要清除这些值，请单击" **用户提交** "页面上的"放弃"。</span><span class="sxs-lookup"><span data-stu-id="b0e61-137">To clear these values, click **Discard** on the User submissions page.</span></span>
