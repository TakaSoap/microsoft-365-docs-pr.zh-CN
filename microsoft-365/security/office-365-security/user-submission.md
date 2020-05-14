---
title: 为用户提交的垃圾邮件和网络钓鱼邮件指定邮箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.openlocfilehash: 38fa16b5270273813b4549b0c3c9baaa1b05b098
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224549"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="3cc83-103">为 Exchange Online 中的垃圾邮件和网络钓鱼邮件的用户提交指定邮箱</span><span class="sxs-lookup"><span data-stu-id="3cc83-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="3cc83-104">在使用 Exchange Online 邮箱的 Microsoft 365 组织中，您可以指定接收用户报告为恶意或非恶意邮件的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3cc83-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="3cc83-105">当用户使用各种报告选项提交邮件时，您可以使用此邮箱来拦截邮件（仅发送到自定义邮箱）或接收邮件副本（发送到自定义邮箱和 Microsoft）。</span><span class="sxs-lookup"><span data-stu-id="3cc83-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="3cc83-106">此功能适用于以下邮件报告选项：</span><span class="sxs-lookup"><span data-stu-id="3cc83-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="3cc83-107">报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="3cc83-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="3cc83-108">[Outlook 网页网站中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)（以前称为 "Outlook web App"）</span><span class="sxs-lookup"><span data-stu-id="3cc83-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="3cc83-109">如果[在 web 上的 Outlook 中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 web 上再次报告 Outlook 中的邮件。</span><span class="sxs-lookup"><span data-stu-id="3cc83-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="3cc83-110">您还可以配置第三方邮件报告工具，以便将邮件转发到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3cc83-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="3cc83-111">将用户报告的邮件传递到自定义邮箱，而不是直接发送到 Microsoft，使管理员可以有选择性地将邮件报告给 Microsoft，并使用[管理员提交](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc83-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3cc83-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="3cc83-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3cc83-113">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="3cc83-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3cc83-114">若要直接转到 "**用户提交**" 页，请使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="3cc83-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="3cc83-115">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3cc83-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3cc83-116">若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3cc83-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3cc83-117">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="3cc83-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="3cc83-118">若要为用户提交配置邮箱，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="3cc83-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="3cc83-119">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc83-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="3cc83-120">使用安全 & 合规性中心配置用户提交邮箱</span><span class="sxs-lookup"><span data-stu-id="3cc83-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="3cc83-121">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> **用户提交**"。</span><span class="sxs-lookup"><span data-stu-id="3cc83-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="3cc83-122">在出现的 "**用户提交**" 页面中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="3cc83-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="3cc83-123">**为 Outlook 启用 "报告邮件" 功能（推荐）**：如果您在 outlook 网页版中使用报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3cc83-123">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="3cc83-124">**自定义最终用户确认消息**：单击此链接。</span><span class="sxs-lookup"><span data-stu-id="3cc83-124">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="3cc83-125">在出现的 "**自定义确认消息**" 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3cc83-125">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="3cc83-126">**提交前**：在 "**标题**" 和 "**确认消息**" 框中，输入用户在使用报告邮件外接程序报告邮件之前看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="3cc83-126">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="3cc83-127">您可以使用变量% type% 来包含提交类型（垃圾邮件、非垃圾邮件、网络钓鱼等）。</span><span class="sxs-lookup"><span data-stu-id="3cc83-127">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="3cc83-128">如前所述，还会将以下文本添加到通知中：</span><span class="sxs-lookup"><span data-stu-id="3cc83-128">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="3cc83-129">你的电子邮件将按与 Microsoft 的相同方式提交到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="3cc83-129">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="3cc83-130">有些电子邮件可能包含个人信息或敏感信息。</span><span class="sxs-lookup"><span data-stu-id="3cc83-130">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="3cc83-131">**提交后**：单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="3cc83-131">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="3cc83-132">在 "**标题**" 和 "**确认消息**" 框中，输入用户在使用报告邮件外接程序报告邮件后看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="3cc83-132">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="3cc83-133">您可以使用变量% type% 来包括提交类型。</span><span class="sxs-lookup"><span data-stu-id="3cc83-133">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="3cc83-134">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3cc83-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="3cc83-135">若要清除这些值，请单击 "**用户提交**" 页上的 "**还原**回"。</span><span class="sxs-lookup"><span data-stu-id="3cc83-135">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="3cc83-136">**将报告的邮件发送到**：执行下列任一选择：</span><span class="sxs-lookup"><span data-stu-id="3cc83-136">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="3cc83-137">**Microsoft （推荐）**：不使用用户提交邮箱（所有报告的邮件都转到 Microsoft）。</span><span class="sxs-lookup"><span data-stu-id="3cc83-137">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="3cc83-138">**Microsoft 和自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3cc83-138">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="3cc83-139">不允许使用通讯组。</span><span class="sxs-lookup"><span data-stu-id="3cc83-139">Distribution groups are not allowed.</span></span>

     - <span data-ttu-id="3cc83-140">**自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3cc83-140">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="3cc83-141">不允许使用通讯组。</span><span class="sxs-lookup"><span data-stu-id="3cc83-141">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="3cc83-142">完成后，请单击 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="3cc83-142">When you're finished, click **Confirm**.</span></span>

     ![将报告的邮件发送到 Microsoft 和自定义邮箱](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="3cc83-144">**禁用 outlook 的报告邮件功能**：如果您在 outlook 网页版中使用第三方报告工具而不是报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3cc83-144">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="3cc83-145">选择 "**使用此自定义邮箱" 可接收用户报告的提交**。</span><span class="sxs-lookup"><span data-stu-id="3cc83-145">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="3cc83-146">在出现的框中，输入现有邮箱的电子邮件地址，或要创建的邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3cc83-146">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="3cc83-147">完成后，请单击 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="3cc83-147">When you're finished, click **Confirm**.</span></span>

     ![使用第三方工具将报告的邮件发送到自定义邮箱](../../media/user-submission-disable-outlook-report-message.png)
