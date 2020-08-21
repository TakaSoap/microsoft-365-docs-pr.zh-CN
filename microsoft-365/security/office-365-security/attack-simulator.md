---
title: ATP 中的攻击模拟器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用攻击模拟器在其 Microsoft 365 E5 或 ATP 计划 2 组织中运行模拟的钓鱼和密码攻击。
ms.openlocfilehash: 017376d8002811398fe3ce2d94f7c207cd718a78
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825829"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="0db26-103">ATP 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="0db26-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="0db26-104">如果贵组织拥有 Office 365 高级威胁防护 (ATP) 计划 2（包括威 [胁调查和响应功能](office-365-ti.md)），可使用安全 & 合规中心中的攻击模拟器在组织中运行真实的攻击方案。</span><span class="sxs-lookup"><span data-stu-id="0db26-104">If your organization has Office 365 Advanced Threat Protection (ATP) Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="0db26-105">这些模拟的攻击可以帮助你在真实的攻击影响你的底线之前识别并找出易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="0db26-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="0db26-106">请阅读本文了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="0db26-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0db26-107">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="0db26-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0db26-108">若要打开安全与合规中心，请转到 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="0db26-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="0db26-109">攻击模拟器可在威 **胁**管理 \> **攻击模拟器上使用**。</span><span class="sxs-lookup"><span data-stu-id="0db26-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="0db26-110">直接转到攻击模拟器，打开 <https://protection.office.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="0db26-110">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="0db26-111">有关跨不同 Microsoft 365 订阅的攻击模拟器可用性的详细信息，请参阅 [Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="0db26-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="0db26-112">你必须是组织管理或**安全\*\*\*\*管理员角色**组的成员。</span><span class="sxs-lookup"><span data-stu-id="0db26-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="0db26-113">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0db26-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0db26-114">你的帐户需要针对 MFA 的多 (身份验证) 在攻击模拟器中创建和管理活动。</span><span class="sxs-lookup"><span data-stu-id="0db26-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="0db26-115">有关说明，请参阅["设置多重身份验证"。](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="0db26-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="0db26-116">网络钓鱼活动将在 30 天内收集并处理事件。</span><span class="sxs-lookup"><span data-stu-id="0db26-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="0db26-117">在你启动市场活动后，将可在 90 天内使用历史市场活动数据。</span><span class="sxs-lookup"><span data-stu-id="0db26-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="0db26-118">没有适用于攻击模拟器的 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0db26-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="0db26-119">鱼性网络钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="0db26-119">Spear phishing campaigns</span></span>

<span data-ttu-id="0db26-120">*网络钓鱼是* 一个一个用于电子邮件攻击的通用术语，尝试从合法的发件人或受信任的发件人访问感受邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="0db26-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="0db26-121">*鱼站点钓鱼是* 一种有针对性的网络钓鱼攻击，该攻击使用专为目标收件人 (专门定制的专门自定义内容，攻击者设定对) 。</span><span class="sxs-lookup"><span data-stu-id="0db26-121">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="0db26-122">在攻击模拟器中，提供两种不同类型的鱼垃圾邮件钓鱼活动：</span><span class="sxs-lookup"><span data-stu-id="0db26-122">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="0db26-123">\*\*鱼类网络钓鱼 (中的凭据) ： \*\*该攻击尝试转说收件人点击邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-123">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="0db26-124">如果用户单击此链接，系统会要求他们输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="0db26-124">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="0db26-125">如果选择正确，则会转到以下其中一个位置：</span><span class="sxs-lookup"><span data-stu-id="0db26-125">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="0db26-126">默认页面将说明这是一个测试，并提供识别网络钓鱼邮件的提示。</span><span class="sxs-lookup"><span data-stu-id="0db26-126">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![用户在单击网络钓鱼链接后输入其凭据时会看到什么内容](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="0db26-128">您所 (的自定义) URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-128">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="0db26-129">\*\*使用附件 (的反) ： \*\*攻击尝试传感收件人以在邮件中打开 .docx 或 .pdf 附件。</span><span class="sxs-lookup"><span data-stu-id="0db26-129">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="0db26-130">此附件包含来自默认的网络钓鱼链接中的相同内容，但第一句是从" \<Display Name\> " 开头，您将看到此邮件显示为最近打开的电子邮件...</span><span class="sxs-lookup"><span data-stu-id="0db26-130">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="0db26-131">目前，攻击模拟器中的鱼取式网络钓鱼活动不会过期。</span><span class="sxs-lookup"><span data-stu-id="0db26-131">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="0db26-132">创建鱼垃圾邮件钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="0db26-132">Create a spear phishing campaign</span></span>

<span data-ttu-id="0db26-133">任何鱼站点钓鱼活动的重要部分是发送给目标收件人的电子邮件的外观和感觉。</span><span class="sxs-lookup"><span data-stu-id="0db26-133">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="0db26-134">若要创建和配置该电子邮件，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="0db26-134">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="0db26-135">**使用内置电子邮件模板：两**个内置模板可供使用 **：Prize Giveaway**和**Payroll Update。**</span><span class="sxs-lookup"><span data-stu-id="0db26-135">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="0db26-136">创建和启动市场活动时，可以进一步自定义模板中的某些、全部或全部，或不自定义任何电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="0db26-136">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="0db26-137">**创建可重用电子邮件模板**：创建并保存电子邮件模板后，可以在将来的鱼机钓鱼活动中再次使用它。</span><span class="sxs-lookup"><span data-stu-id="0db26-137">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="0db26-138">创建和启动市场活动时，可以进一步自定义模板中的某些、全部或全部，或不自定义任何电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="0db26-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="0db26-139">**在向导中创建电子邮件**：可以在你创建和启动鱼垃圾邮件网络钓鱼活动时在向导中直接创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0db26-139">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="0db26-140">步骤 1 (可选) ：创建自定义电子邮件模板</span><span class="sxs-lookup"><span data-stu-id="0db26-140">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="0db26-141">如果要使用其中一个内置模板或直接在向导中创建电子邮件，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="0db26-141">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="0db26-142">在安全与&中心 **内，转到** \> **威胁管理攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="0db26-142">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0db26-143">在 **"模拟攻击"** 页上，在 **"鱼述鱼网络钓鱼（ (）"哈希希值和) "** 西班 (附件 **) "** 部分，单击 **"攻击详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="0db26-143">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="0db26-144">创建模板并不重要。</span><span class="sxs-lookup"><span data-stu-id="0db26-144">It doesn't matter where you create the template.</span></span> <span data-ttu-id="0db26-145">模板中的可用选项对于两种类型的网络钓鱼攻击是相同的。</span><span class="sxs-lookup"><span data-stu-id="0db26-145">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="0db26-146">在**打开的"攻击详细信息"页**的"**网络钓鱼模板"** 部分的 **"创建模板"** 区域中，单击"**新建模板"。**</span><span class="sxs-lookup"><span data-stu-id="0db26-146">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="0db26-147">" **配置网络钓鱼模板"** 向导会在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="0db26-147">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="0db26-148">在"**开始"** 步骤中，为模板显示名称唯一，然后单击"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="0db26-148">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="0db26-149">在" **配置电子邮件详细信息"** 步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0db26-149">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="0db26-150">\*\*由 (名) ： \*\*用于邮件发件人的 显示名称。</span><span class="sxs-lookup"><span data-stu-id="0db26-150">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="0db26-151">\*\*发件人 () 联系人： \*\*发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0db26-151">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="0db26-152">**网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-152">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="0db26-153">这是将临时单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-153">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="0db26-154">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="0db26-154">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="0db26-155">所有 URL 都专门为 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="0db26-155">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="0db26-156">一个 URL 信誉服务可能将其中一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="0db26-156">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="0db26-157">先检查支持的 Web 浏览器中的 URL 可用性，然后再在网络钓鱼活动中使用该 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-157">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="0db26-158">**自定义登录页面 URL：** 输入一个可选登录页面，如果用户单击网络钓鱼链接并输入其凭据，用户将在此页面中进行输入。</span><span class="sxs-lookup"><span data-stu-id="0db26-158">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="0db26-159">此链接将替换默认的凭据页。</span><span class="sxs-lookup"><span data-stu-id="0db26-159">This link replaces the default landing page.</span></span> <span data-ttu-id="0db26-160">例如，如果你有内部意识培训，可以在此处指定该 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-160">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="0db26-161">**类别**：目前，不会使用此设置 (输入的任何内容均不) 。</span><span class="sxs-lookup"><span data-stu-id="0db26-161">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="0db26-162">**Subject**： **电子邮件** 的"主题"字段。</span><span class="sxs-lookup"><span data-stu-id="0db26-162">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="0db26-163">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0db26-163">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0db26-164">在" **撰写** 电子邮件"步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="0db26-164">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="0db26-165">您可以使用"电子邮件 **"选项卡** (丰富 HTML 编辑器和) **Source** HTML 代码 (的"源") 。</span><span class="sxs-lookup"><span data-stu-id="0db26-165">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="0db26-166">HTML 格式可以根据您需要简单或复杂。</span><span class="sxs-lookup"><span data-stu-id="0db26-166">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="0db26-167">您可以插入图像和文本，增强邮件在收件人电子邮件客户端中的信用性。</span><span class="sxs-lookup"><span data-stu-id="0db26-167">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="0db26-168">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="0db26-168">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="0db26-169">`${loginserverurl}` 插入上 **一步中的"钓鱼登录服务器 URL"** 值。</span><span class="sxs-lookup"><span data-stu-id="0db26-169">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="0db26-170">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0db26-170">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="0db26-171">在"**确认"** 步骤中，单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="0db26-171">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="0db26-172">步骤 2：创建并启动鱼垃圾邮件钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="0db26-172">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="0db26-173">在安全与&中心 **内，转到** \> **威胁管理攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="0db26-173">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0db26-174">在 **模拟攻击页面上，** 根据你要创建的市场活动类型，进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="0db26-174">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="0db26-175">In the \*\*Spear Phishing (Credentials Harvest) \*\* section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="0db26-175">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="0db26-176">在 **"关于第一 (网络钓鱼) "** 部分，单击"启动**攻击"** 或**单击"攻击详细信息**启动 \> **攻击"。**</span><span class="sxs-lookup"><span data-stu-id="0db26-176">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="0db26-177">" **配置网络钓鱼攻击"** 向导会在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="0db26-177">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="0db26-178">在 **开始步骤** 中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0db26-178">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0db26-179">在 **"名称** "框中，输入显示名称唯一事件。</span><span class="sxs-lookup"><span data-stu-id="0db26-179">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="0db26-180">不要单击" **使用模板**"，因为您稍后将在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0db26-180">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="0db26-181">单击 **"使用** 模板"并选择内置或自定义电子邮件模板。</span><span class="sxs-lookup"><span data-stu-id="0db26-181">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="0db26-182">选择模板后，" **名称"** 框将自动基于模板进行填充，但你可以更改名称。</span><span class="sxs-lookup"><span data-stu-id="0db26-182">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![网络钓鱼开始页面](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="0db26-184">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0db26-184">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0db26-185">在目标 **收件人步骤** 中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0db26-185">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0db26-186">单击 **"** 通讯簿"， (活动的用户) 组"选项。</span><span class="sxs-lookup"><span data-stu-id="0db26-186">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="0db26-187">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0db26-187">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="0db26-188">如果单击 **"筛选\*\*\*\*"且**没有输入搜索条件，将返回所有收件人并将其添加到活动中。</span><span class="sxs-lookup"><span data-stu-id="0db26-188">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="0db26-189">单击 **"** 导入 **"，** 可以导入 CSV 文件或电子邮件地址的 (行) 分隔文件中的逗号分隔值。</span><span class="sxs-lookup"><span data-stu-id="0db26-189">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="0db26-190">每行都必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0db26-190">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="0db26-191">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0db26-191">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0db26-192">在" **配置电子邮件详细信息"** 步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0db26-192">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="0db26-193">如果在"开始"步骤中 **选择** 了一个模板，则大部分值都已配置，但您可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="0db26-193">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="0db26-194">\*\*由 (名) ： \*\*用于邮件发件人的 显示名称。</span><span class="sxs-lookup"><span data-stu-id="0db26-194">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="0db26-195">\*\*发件人 () 联系人： \*\*发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0db26-195">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="0db26-196">您可以从您组织的电子邮件域输入真实或虚假电子邮件地址，也可以输入真实或虚假的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0db26-196">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="0db26-197">您组织的有效发件人电子邮件地址实际将在收件人的电子邮件客户端中进行解析。</span><span class="sxs-lookup"><span data-stu-id="0db26-197">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="0db26-198">**网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-198">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="0db26-199">这是将临时单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-199">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="0db26-200">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="0db26-200">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="0db26-201">所有 URL 都专门为 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="0db26-201">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="0db26-202">一个 URL 信誉服务可能将其中一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="0db26-202">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="0db26-203">先检查支持的 Web 浏览器中的 URL 可用性，然后再在网络钓鱼活动中使用该 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-203">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="0db26-204">必须选择 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-204">You are required to select a URL.</span></span> <span data-ttu-id="0db26-205">对于 \*\*西班者网络钓鱼 (附件) \*\* 活动，您可以在下一步 (中删除邮件正文中的链接，否则，邮件将 **包含链接和** 附件) 。</span><span class="sxs-lookup"><span data-stu-id="0db26-205">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="0db26-206">**附件**类型：此设置仅适用于 \*\*添加到活动市场活动和 (网络) \*\* 自定义设置。</span><span class="sxs-lookup"><span data-stu-id="0db26-206">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="0db26-207">单击下拉列表并选择 **。DOCX**或者 **。列表中的 PDF。**</span><span class="sxs-lookup"><span data-stu-id="0db26-207">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="0db26-208">**附件**名称：此设置仅适用于 \*\*"附件 (附件") \*\* 附件。</span><span class="sxs-lookup"><span data-stu-id="0db26-208">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="0db26-209">输入 .docx 或 .pdf 附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="0db26-209">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="0db26-210">**自定义登录页面 URL：** 输入一个可选登录页面，如果用户单击网络钓鱼链接并输入其凭据，用户将在此页面中进行输入。</span><span class="sxs-lookup"><span data-stu-id="0db26-210">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="0db26-211">此链接将替换默认的凭据页。</span><span class="sxs-lookup"><span data-stu-id="0db26-211">This link replaces the default landing page.</span></span> <span data-ttu-id="0db26-212">例如，如果你有内部意识培训，可以在此处指定该 URL。</span><span class="sxs-lookup"><span data-stu-id="0db26-212">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="0db26-213">**Subject**： **电子邮件** 的"主题"字段。</span><span class="sxs-lookup"><span data-stu-id="0db26-213">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="0db26-214">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0db26-214">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0db26-215">在" **撰写** 电子邮件"步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="0db26-215">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="0db26-216">如果在"开始"步骤中 **选择** 了一个模板，则已经配置了邮件正文，但您可以自定义该页面。</span><span class="sxs-lookup"><span data-stu-id="0db26-216">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="0db26-217">您可以使用"电子邮件 **"选项卡** (丰富 HTML 编辑器和) **Source** HTML 代码 (的"源") 。</span><span class="sxs-lookup"><span data-stu-id="0db26-217">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="0db26-218">HTML 格式可以根据您需要简单或复杂。</span><span class="sxs-lookup"><span data-stu-id="0db26-218">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="0db26-219">您可以插入图像和文本，增强邮件在收件人电子邮件客户端中的信用性。</span><span class="sxs-lookup"><span data-stu-id="0db26-219">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="0db26-220">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="0db26-220">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="0db26-221">`${loginserverurl}` 插入 **网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="0db26-221">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="0db26-222">对于 \*\*鱼语 (附件) \*\* 活动，应从邮件 (其他任何活动中删除链接，邮件将 **包含链接和** 附件，且不会在附件活动活动中跟踪链接单击) 。</span><span class="sxs-lookup"><span data-stu-id="0db26-222">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![撰写电子邮件正文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="0db26-224">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0db26-224">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="0db26-225">在"**确认\*\*\*\*"步骤**中，单击"完成"以启动该市场活动。</span><span class="sxs-lookup"><span data-stu-id="0db26-225">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="0db26-226">网络钓鱼邮件将传递给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="0db26-226">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="0db26-227">密码攻击活动</span><span class="sxs-lookup"><span data-stu-id="0db26-227">Password attack campaigns</span></span>

<span data-ttu-id="0db26-228">*密码攻击将尝试*为组织中用户帐户的密码进行攻击（通常在攻击者标识了一个或多个有效的用户帐户之后）。</span><span class="sxs-lookup"><span data-stu-id="0db26-228">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="0db26-229">在攻击模拟器中，可以使用两种不同类型的密码攻击活动来测试用户密码的复杂性：</span><span class="sxs-lookup"><span data-stu-id="0db26-229">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="0db26-230">\*\*Brute password (dictionary attack) ： \*\**亚克力*或字典攻击在用户帐户中使用大型密码典文件，该典型证定其中一个的用户将针对一个帐户) 工作 (许多密码。 *dictionary*</span><span class="sxs-lookup"><span data-stu-id="0db26-230">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="0db26-231">不正确的密码锁定有助于防止使用方块的强制密码攻击。</span><span class="sxs-lookup"><span data-stu-id="0db26-231">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="0db26-232">对于字典攻击，你可以指定一个或多个密码以尝试 (手动输入或在已上载的文件) 中进行尝试，并可指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="0db26-232">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="0db26-233">**密码反信攻击**： *密码：密码* 反机攻击针对用户帐户列表仔细考虑使用同名密码，针对多个帐户输入的 (一个) 密码。</span><span class="sxs-lookup"><span data-stu-id="0db26-233">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="0db26-234">密码泄漏攻击较为难以检测力密码攻击 (如果攻击者跨数十个或数百个帐户尝试输入一个密码而产生成功的可能性增加，而不会引起用户不正确的密码锁定) 。</span><span class="sxs-lookup"><span data-stu-id="0db26-234">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="0db26-235">对于密码间括性攻击，您只能指定要尝试的密码，并且您可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="0db26-235">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="0db26-236">攻击模拟器中的密码攻击会将用户名和密码基本身份验证请求传递至终结点，因此它们还可与其他身份验证方法 (AD FS、密码哈希同步、直通、PingFederate 等一起 ) 使用。</span><span class="sxs-lookup"><span data-stu-id="0db26-236">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="0db26-237">对于已启用 MFA 的用户，即使密码攻击尝试实际密码，尝试将始终注册为失败 (以其他方式显示，MFA 用户永远不会在 **活动** 域域域的成功尝试计数中显示) 。</span><span class="sxs-lookup"><span data-stu-id="0db26-237">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="0db26-238">这是预期的结果。</span><span class="sxs-lookup"><span data-stu-id="0db26-238">This is the expected result.</span></span> <span data-ttu-id="0db26-239">MFA 是帮助抵御密码攻击的主要方法。</span><span class="sxs-lookup"><span data-stu-id="0db26-239">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="0db26-240">创建和启动密码攻击活动</span><span class="sxs-lookup"><span data-stu-id="0db26-240">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="0db26-241">在安全与&中心 **内，转到** \> **威胁管理攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="0db26-241">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0db26-242">在 **模拟攻击页面上，** 根据你要创建的市场活动类型，进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="0db26-242">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="0db26-243">在 **"Brute Force Password (Dictionary Attack) "** 部分，单击 **"启动**攻击"或单击"**攻击详细信息** \> **启动攻击"。**</span><span class="sxs-lookup"><span data-stu-id="0db26-243">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="0db26-244">在 **"密码数据库攻击"** 部分，单击 **"启动攻击"** 或单击"**攻击详细信息** \> **启动攻击"。**</span><span class="sxs-lookup"><span data-stu-id="0db26-244">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="0db26-245">" **配置密码攻击"向导** 会在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="0db26-245">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="0db26-246">在"**开始**"步中，为显示名称输入唯一的市场活动，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="0db26-246">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="0db26-247">在目标 **用户步骤** 中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0db26-247">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0db26-248">单击 **"** 通讯簿"， (活动的用户) 组"选项。</span><span class="sxs-lookup"><span data-stu-id="0db26-248">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="0db26-249">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0db26-249">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="0db26-250">如果单击 **"筛选\*\*\*\*"且**没有输入搜索条件，将返回所有收件人并将其添加到活动中。</span><span class="sxs-lookup"><span data-stu-id="0db26-250">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="0db26-251">单击 **"** 导入 **"，** 可以导入 CSV 文件或电子邮件地址的 (行) 分隔文件中的逗号分隔值。</span><span class="sxs-lookup"><span data-stu-id="0db26-251">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="0db26-252">每行都必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0db26-252">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="0db26-253">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0db26-253">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0db26-254">在 **"选择攻击设置"** 步骤中，基于市场活动类型选择要执行的操作：</span><span class="sxs-lookup"><span data-stu-id="0db26-254">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="0db26-255">\*\*使用自动力密码 (收字攻击（) \*\*执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0db26-255">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="0db26-256">**手动输入密码：在**"按 **Enter 键"添加密码框** 时，键入密码，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="0db26-256">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="0db26-257">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="0db26-257">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="0db26-258">**从字典文件上传密码：** 单击" **上传"可** 导入每行包含一个密码的现有文本文件和空的最后一行。</span><span class="sxs-lookup"><span data-stu-id="0db26-258">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="0db26-259">文本文件的大小必须为 10 MB 或更小，并且包含的密码不能超过 30000。</span><span class="sxs-lookup"><span data-stu-id="0db26-259">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="0db26-260">**密码反网络攻击：在**密码 (**显示) 在攻击框中使用的** 密码输入一个密码。</span><span class="sxs-lookup"><span data-stu-id="0db26-260">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="0db26-261">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0db26-261">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0db26-262">在"**确认\*\*\*\*"步骤**中，单击"完成"以启动该市场活动。</span><span class="sxs-lookup"><span data-stu-id="0db26-262">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="0db26-263">对指定的用户尝试指定的密码。</span><span class="sxs-lookup"><span data-stu-id="0db26-263">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="0db26-264">查看市场活动结果</span><span class="sxs-lookup"><span data-stu-id="0db26-264">View campaign results</span></span>

<span data-ttu-id="0db26-265">启动市场活动后，你可以检查主模拟攻击页面上的 **进度和** 结果。</span><span class="sxs-lookup"><span data-stu-id="0db26-265">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="0db26-266">活动市场活动将显示状态栏、已完成的百分比值和 (完成的用户) 用户总 (数) "计数。</span><span class="sxs-lookup"><span data-stu-id="0db26-266">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="0db26-267">单击" **刷新** "按钮将更新任何活动市场活动的进度。</span><span class="sxs-lookup"><span data-stu-id="0db26-267">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="0db26-268">你还可以 **单击"终止** "来停止活动的市场活动。</span><span class="sxs-lookup"><span data-stu-id="0db26-268">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="0db26-269">市场活动完成后，将对攻击完成 **的状态更改**。</span><span class="sxs-lookup"><span data-stu-id="0db26-269">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="0db26-270">可以通过执行以下任一操作来查看市场活动的结果：</span><span class="sxs-lookup"><span data-stu-id="0db26-270">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="0db26-271">在主 **模拟攻击页面，单击** 市场 **活动名称下** 的"查看报告"。</span><span class="sxs-lookup"><span data-stu-id="0db26-271">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="0db26-272">在 **主模拟攻击页面上，** 单击 **"攻击详细信息** "部分以获取攻击类型。</span><span class="sxs-lookup"><span data-stu-id="0db26-272">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="0db26-273">在 **打开的攻击详细信息** 页面上，选择攻击历史记录 **部分中的市场活动** 。</span><span class="sxs-lookup"><span data-stu-id="0db26-273">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="0db26-274">上述任一操作都将转到名为 **"攻击详细信息"的页面**。</span><span class="sxs-lookup"><span data-stu-id="0db26-274">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="0db26-275">以下各部分分别介绍了此页面上每种市场活动的信息。</span><span class="sxs-lookup"><span data-stu-id="0db26-275">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="0db26-276">鱼增的鱼 (的学习和) 中的凭据</span><span class="sxs-lookup"><span data-stu-id="0db26-276">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="0db26-277">每项活动可在 **"攻击详细信息** "页面上获取以下信息：</span><span class="sxs-lookup"><span data-stu-id="0db26-277">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0db26-278">活动 (期的开始日期/时间) 结束日期/时间。</span><span class="sxs-lookup"><span data-stu-id="0db26-278">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0db26-279">**针对目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="0db26-279">**Total users targeted**</span></span>

- <span data-ttu-id="0db26-280">**成功尝试**：单击链接并输入其凭据且用户输入的用户**and**的数量 (*用户*名和密码) 。</span><span class="sxs-lookup"><span data-stu-id="0db26-280">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="0db26-281">**总体成功率：** 由"成功尝试计算的总用户**数"**  /  **所针对的百分比**。</span><span class="sxs-lookup"><span data-stu-id="0db26-281">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0db26-282">**最快单击**：启动市场活动后第一个用户单击链接所用的时间。</span><span class="sxs-lookup"><span data-stu-id="0db26-282">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="0db26-283">**Average Click**： 每个人单击链接所用时间的总和除以单击链接的用户数。</span><span class="sxs-lookup"><span data-stu-id="0db26-283">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="0db26-284">**单击"成功率：** 按链接选择的 (点击"的用户数"/"目标用户数"计算) 的 **百分比**。</span><span class="sxs-lookup"><span data-stu-id="0db26-284">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="0db26-285">**最快的凭据**：第一个用户在启动市场活动后输入其凭据所用的时间。</span><span class="sxs-lookup"><span data-stu-id="0db26-285">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="0db26-286">**Average Credentials**：每个人输入凭据的时间与输入其凭据的用户数的平均值的平均值。</span><span class="sxs-lookup"><span data-stu-id="0db26-286">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="0db26-287">**凭据成功率：** 输入其凭据的用户数计算的 (百分比/目标) 用户总**数"**</span><span class="sxs-lookup"><span data-stu-id="0db26-287">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="0db26-288">条形图显示**单击链接和\*\*\*\*每天提供的**凭据。</span><span class="sxs-lookup"><span data-stu-id="0db26-288">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="0db26-289">圆形图显示**链接单击、** 所提供的凭据**和\*\*\*\*活动**的无百分比。</span><span class="sxs-lookup"><span data-stu-id="0db26-289">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="0db26-290">" **受到欢迎的用户** "部分列出了单击链接的用户的详细信息：</span><span class="sxs-lookup"><span data-stu-id="0db26-290">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="0db26-291">用户的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="0db26-291">The user's email address</span></span>

  - <span data-ttu-id="0db26-292">单击链接时的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="0db26-292">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="0db26-293">客户端 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0db26-293">The client IP address.</span></span>

  - <span data-ttu-id="0db26-294">有关用户版本的 Windows 和 Web 浏览器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0db26-294">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="0db26-295">你可以单击 **"导出** "将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0db26-295">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="0db26-296">对活动市场 (的) 最高版本钓鱼</span><span class="sxs-lookup"><span data-stu-id="0db26-296">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="0db26-297">每项活动可在 **"攻击详细信息** "页面上获取以下信息：</span><span class="sxs-lookup"><span data-stu-id="0db26-297">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0db26-298">活动 (期的开始日期/时间) 结束日期/时间。</span><span class="sxs-lookup"><span data-stu-id="0db26-298">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0db26-299">**针对目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="0db26-299">**Total users targeted**</span></span>

- <span data-ttu-id="0db26-300">**成功尝试**：打开或下载和打开附件或打开附件（ (数不计) 。</span><span class="sxs-lookup"><span data-stu-id="0db26-300">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="0db26-301">**总体成功率：** 由"成功尝试计算的总用户**数"**  /  **所针对的百分比**。</span><span class="sxs-lookup"><span data-stu-id="0db26-301">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0db26-302">**最快的附件打开时间**：第一个用户在启动市场活动后打开附件所用的时间。</span><span class="sxs-lookup"><span data-stu-id="0db26-302">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="0db26-303">**附件打开时间**：每个人打开附件的时间与打开附件的用户数相加所用时间的总和。</span><span class="sxs-lookup"><span data-stu-id="0db26-303">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="0db26-304">**附件打开成功率：** 由打开附件的用户 (**数/目标**用户数计算的) 百分比。</span><span class="sxs-lookup"><span data-stu-id="0db26-304">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="0db26-305">使用强力密码 (词典) 的帐户</span><span class="sxs-lookup"><span data-stu-id="0db26-305">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="0db26-306">每项活动可在 **"攻击详细信息** "页面上获取以下信息：</span><span class="sxs-lookup"><span data-stu-id="0db26-306">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0db26-307">活动 (期的开始日期/时间) 结束日期/时间。</span><span class="sxs-lookup"><span data-stu-id="0db26-307">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0db26-308">**针对目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="0db26-308">**Total users targeted**</span></span>

- <span data-ttu-id="0db26-309">**成功尝试**：找到要使用其中一个指定密码的用户数量。</span><span class="sxs-lookup"><span data-stu-id="0db26-309">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="0db26-310">**总体成功率：** 由"成功尝试计算的总用户**数"**  /  **所针对的百分比**。</span><span class="sxs-lookup"><span data-stu-id="0db26-310">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0db26-311">" **受到权限用户"** 部分列出受影响用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0db26-311">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="0db26-312">你可以单击 **"导出** "将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0db26-312">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="0db26-313">密码子攻击活动结果</span><span class="sxs-lookup"><span data-stu-id="0db26-313">Password spray attack campaign results</span></span>

<span data-ttu-id="0db26-314">每项活动可在 **"攻击详细信息** "页面上获取以下信息：</span><span class="sxs-lookup"><span data-stu-id="0db26-314">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0db26-315">活动 (期的开始日期/时间) 结束日期/时间。</span><span class="sxs-lookup"><span data-stu-id="0db26-315">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0db26-316">**针对目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="0db26-316">**Total users targeted**</span></span>

- <span data-ttu-id="0db26-317">**成功尝试**：已找到正在使用指定密码的用户数量。</span><span class="sxs-lookup"><span data-stu-id="0db26-317">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="0db26-318">**总体成功率：** 由"成功尝试计算的总用户**数"**  /  **所针对的百分比**。</span><span class="sxs-lookup"><span data-stu-id="0db26-318">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
