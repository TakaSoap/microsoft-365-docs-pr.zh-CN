---
title: Microsoft Defender for Office 365 中的攻击模拟器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用攻击模拟器在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织中运行模拟网络钓鱼和密码攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85b376701ffa0c567fd66aa629371e9f69b354e9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407464"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8068a-103">Microsoft Defender for Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="8068a-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8068a-104">**适用于** [Microsoft Defender for Office 365 计划 2](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="8068a-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="8068a-105">如果你的组织具有 Microsoft Defender for Office 365 计划[](office-365-ti.md)& 2（包括威胁调查和响应功能），可以在安全与合规中心内使用攻击模拟器在组织中运行真实的攻击方案。</span><span class="sxs-lookup"><span data-stu-id="8068a-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="8068a-106">这些模拟攻击可以帮助你在真实攻击影响你的最后一线之前识别并找到易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="8068a-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="8068a-107">阅读本文可了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="8068a-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="8068a-108">攻击模拟器 v1 体验已切换到只读模式，并替换为攻击模拟器培训，如使用攻击模拟培训入门 [中所述](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="8068a-108">Attack Simulator v1 experience has been switched to read-only mode and replaced by Attack simulator training that's described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
> <span data-ttu-id="8068a-109">已禁用从此站点启动新模拟的能力。</span><span class="sxs-lookup"><span data-stu-id="8068a-109">The ability to launch new simulations from this site has been disabled.</span></span> <span data-ttu-id="8068a-110">但是，您仍可以访问自 2021 年 1 月 24 日起运行 90 天的模拟报告。</span><span class="sxs-lookup"><span data-stu-id="8068a-110">However, you can still access reports for simulations run for a period of 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8068a-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8068a-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8068a-112">若要打开安全与合规中心，请转到 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="8068a-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="8068a-113">攻击模拟器可用于 **威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="8068a-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="8068a-114">转到直接攻击模拟器，打开 <https://protection.office.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="8068a-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="8068a-115">有关不同 Microsoft 365 订阅中攻击模拟器的可用性详细信息，请参阅 [Microsoft Defender for Office 365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8068a-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="8068a-116">您必须是组织管理或 **安全管理员角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="8068a-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="8068a-117">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8068a-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="8068a-118">你的帐户需要配置为使用 MFA (多重) ，以在攻击模拟器中创建和管理市场活动。</span><span class="sxs-lookup"><span data-stu-id="8068a-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="8068a-119">有关说明，请参阅["设置多重身份验证"。](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="8068a-119">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="8068a-120">攻击模拟器仅适用于基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8068a-120">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="8068a-121">网络钓鱼活动将在 30 天内收集和处理事件。</span><span class="sxs-lookup"><span data-stu-id="8068a-121">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="8068a-122">历史市场活动数据将在你启动市场活动后最多 90 天内可用。</span><span class="sxs-lookup"><span data-stu-id="8068a-122">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="8068a-123">攻击模拟和培训相关的数据存储在 Microsoft 365 服务的其他客户数据中。</span><span class="sxs-lookup"><span data-stu-id="8068a-123">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="8068a-124">有关详细信息，请参阅 [Microsoft 365 数据位置](/microsoft-365/enterprise/o365-data-locations)。</span><span class="sxs-lookup"><span data-stu-id="8068a-124">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="8068a-125">攻击模拟器没有对应的 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8068a-125">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="8068a-126">网络钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="8068a-126">Spear phishing campaigns</span></span>

<span data-ttu-id="8068a-127">*网络钓鱼* 是电子邮件攻击的一般术语，它尝试窃取看似来自合法或受信任的发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="8068a-127">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="8068a-128">*网络钓鱼* 是一种有针对性的网络钓鱼攻击，它使用专门针对目标收件人定制的重点和自定义内容 (通常是在攻击者重新识别收件人之后) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-128">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="8068a-129">在攻击模拟器中，提供了两种不同类型的钓鱼活动：</span><span class="sxs-lookup"><span data-stu-id="8068a-129">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="8068a-130">**网络钓鱼 (凭据**) ：攻击试图说服收件人单击邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-130">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="8068a-131">如果用户单击该链接，则要求他们输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="8068a-131">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="8068a-132">如果是，则他们被带至以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="8068a-132">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="8068a-133">一个默认页面，说明这只是一个测试，并提供了识别网络钓鱼邮件的提示。</span><span class="sxs-lookup"><span data-stu-id="8068a-133">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![用户单击网络钓鱼链接并输入其凭据时所看到的内容](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="8068a-135">自定义页面 (指定) URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-135">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="8068a-136">**网络钓鱼 (附件**) ：攻击试图说服收件人在邮件中打开 .docx 或 .pdf 附件。</span><span class="sxs-lookup"><span data-stu-id="8068a-136">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="8068a-137">附件包含来自默认网络钓鱼链接的相同内容，但第一句以"开头，你将看到此邮件为您打开的最近电子邮件 \<Display Name\> ..."。</span><span class="sxs-lookup"><span data-stu-id="8068a-137">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="8068a-138">目前，攻击模拟器中的网络钓鱼活动不会过期。</span><span class="sxs-lookup"><span data-stu-id="8068a-138">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="8068a-139">创建钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="8068a-139">Create a spear phishing campaign</span></span>

<span data-ttu-id="8068a-140">任何钓鱼活动的重要部分是发送给目标收件人的电子邮件的外观。</span><span class="sxs-lookup"><span data-stu-id="8068a-140">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="8068a-141">若要创建和配置电子邮件，有以下选项：</span><span class="sxs-lookup"><span data-stu-id="8068a-141">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="8068a-142">**使用内置电子邮件模板：** 有两个内置模板可用： **产品** 奖励和工资 **单更新**。</span><span class="sxs-lookup"><span data-stu-id="8068a-142">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="8068a-143">创建和启动市场活动时，可以进一步自定义模板中的部分、全部或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="8068a-143">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="8068a-144">**创建可重用的电子邮件模板**：创建并保存电子邮件模板后，可以在将来的网络钓鱼活动中再次使用它。</span><span class="sxs-lookup"><span data-stu-id="8068a-144">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="8068a-145">创建和启动市场活动时，可以进一步自定义模板中的部分、全部或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="8068a-145">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="8068a-146">**在向导中** 创建电子邮件：可以在创建和启动钓鱼活动时直接在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8068a-146">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="8068a-147">步骤 1 (可选) ：创建自定义电子邮件模板</span><span class="sxs-lookup"><span data-stu-id="8068a-147">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="8068a-148">如果要使用其中一个内置模板或直接在向导中创建电子邮件，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="8068a-148">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="8068a-149">在安全&，转到 **威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="8068a-149">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="8068a-150">在"模拟攻击"页上，在 **"Spear 钓鱼 (凭据** 收集) 或"钓鱼 (附件) 部分中，单击"攻击 **详细信息\*\*\*\*"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-150">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="8068a-151">在哪里创建模板并不重要。</span><span class="sxs-lookup"><span data-stu-id="8068a-151">It doesn't matter where you create the template.</span></span> <span data-ttu-id="8068a-152">模板中的可用选项对于这两种类型的网络钓鱼攻击是相同的。</span><span class="sxs-lookup"><span data-stu-id="8068a-152">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="8068a-153">在打开 **的**"攻击详细信息"页的"网络钓鱼模板"部分，**在"创建** 模板"区域中，单击 **"新建模板"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-153">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="8068a-154">" **配置网络钓鱼模板"** 向导从新的飞出控件开始。</span><span class="sxs-lookup"><span data-stu-id="8068a-154">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="8068a-155">在 **"开始**"步骤中，显示名称模板的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-155">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="8068a-156">在 **"配置电子邮件详细信息** "步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="8068a-156">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="8068a-157">**发件人 (名称) ：显示名称** 发件人使用的发件人名称。</span><span class="sxs-lookup"><span data-stu-id="8068a-157">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="8068a-158">**发件人 (电子邮件) ：** 发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8068a-158">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="8068a-159">**网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-159">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="8068a-160">这是用户将尝试单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-160">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="8068a-161">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="8068a-161">The choices are:</span></span>

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
     > <span data-ttu-id="8068a-162">URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="8068a-162">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="8068a-163">在网络钓鱼活动中使用 URL 之前，请检查受支持的 Web 浏览器中 URL 的可用性。</span><span class="sxs-lookup"><span data-stu-id="8068a-163">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="8068a-164">**自定义登** 陆页面 URL：输入可选登录页，如果用户单击网络钓鱼链接并输入其凭据，将在此页面进行登录。</span><span class="sxs-lookup"><span data-stu-id="8068a-164">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="8068a-165">此链接将替换默认登录页面。</span><span class="sxs-lookup"><span data-stu-id="8068a-165">This link replaces the default landing page.</span></span> <span data-ttu-id="8068a-166">例如，如果你有内部意识培训，你可以在此处指定该 URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-166">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="8068a-167">**类别**：目前，此设置不会用于 (输入的项将被忽略) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-167">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="8068a-168">**主题**： **电子邮件** 的主题字段。</span><span class="sxs-lookup"><span data-stu-id="8068a-168">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="8068a-169">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8068a-169">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="8068a-170">在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="8068a-170">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="8068a-171">可以使用"电子邮件"**选项卡 (** 富 HTML 编辑器) 或源选项卡 (原始 HTML代码) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-171">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="8068a-172">HTML 格式可以像需要一样简单或复杂。</span><span class="sxs-lookup"><span data-stu-id="8068a-172">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="8068a-173">您可以插入图像和文本，以增强邮件在收件人的电子邮件客户端中的可信度。</span><span class="sxs-lookup"><span data-stu-id="8068a-173">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="8068a-174">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="8068a-174">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="8068a-175">`${loginserverurl}` 插入上 **一步中的网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="8068a-175">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="8068a-176">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8068a-176">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="8068a-177">在 **"确认"** 步骤中，单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-177">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="8068a-178">步骤 2：创建和启动钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="8068a-178">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="8068a-179">在安全&，转到 **威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="8068a-179">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="8068a-180">在 **"模拟** 攻击"页上，根据要创建的市场活动类型进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="8068a-180">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="8068a-181">在 **"Spear 网络钓鱼 (凭据** 获取) ，单击"启动攻击 **"或单击**"**攻击详细信息** \> **启动攻击"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-181">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="8068a-182">在 **"钓鱼邮件 (附件**) ，单击"启动攻击"或"攻击 **详细信息** 启动 \> **攻击"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-182">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="8068a-183">" **配置网络钓鱼攻击"** 向导从新的飞出控件开始。</span><span class="sxs-lookup"><span data-stu-id="8068a-183">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="8068a-184">在 **"开始** "步骤中，执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8068a-184">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="8068a-185">在 **"名称** "框中，输入显示名称的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="8068a-185">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="8068a-186">请勿单击 **"使用模板"，** 因为稍后您将在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8068a-186">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="8068a-187">单击 **"使用** 模板"，然后选择内置或自定义电子邮件模板。</span><span class="sxs-lookup"><span data-stu-id="8068a-187">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="8068a-188">选择模板后，根据模板自动填充"名称"框，但可以更改名称。</span><span class="sxs-lookup"><span data-stu-id="8068a-188">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8068a-189">![网络钓鱼起始页](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="8068a-189">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="8068a-190">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8068a-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8068a-191">在 **"目标收件人"** 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8068a-191">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="8068a-192">单击 **"通讯簿** "以选择 (或组) 的收件人。</span><span class="sxs-lookup"><span data-stu-id="8068a-192">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="8068a-193">每个目标收件人必须具有 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="8068a-193">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="8068a-194">如果在 **未输入搜索** 条件的情况下单击 **"** 筛选和应用"，将返回所有收件人并添加到市场活动。</span><span class="sxs-lookup"><span data-stu-id="8068a-194">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="8068a-195">单击 **"导入\*\*\*\*"，** 再单击"文件导入"， (CSV) 或电子邮件地址的行分隔文件中导入逗号分隔值。</span><span class="sxs-lookup"><span data-stu-id="8068a-195">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="8068a-196">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8068a-196">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="8068a-197">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8068a-197">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8068a-198">在 **"配置电子邮件详细信息** "步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="8068a-198">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="8068a-199">如果在"开始"步骤中选择了模板，则大部分这些值已配置，但您可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="8068a-199">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="8068a-200">**发件人 (名称) ：显示名称** 发件人使用的发件人名称。</span><span class="sxs-lookup"><span data-stu-id="8068a-200">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="8068a-201">**发件人 (电子邮件) ：** 发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8068a-201">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="8068a-202">你可以从组织的电子邮件域输入真实或虚假的电子邮件地址，也可以输入真实或虚假的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8068a-202">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="8068a-203">您组织的有效发件人电子邮件地址实际上将在收件人的电子邮件客户端中解析。</span><span class="sxs-lookup"><span data-stu-id="8068a-203">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="8068a-204">**网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-204">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="8068a-205">这是用户将尝试单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-205">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="8068a-206">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="8068a-206">The choices are:</span></span>

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
     > - <span data-ttu-id="8068a-207">所有 URL 都是有意 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="8068a-207">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="8068a-208">URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="8068a-208">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="8068a-209">在网络钓鱼活动中使用 URL 之前，请检查受支持的 Web 浏览器中 URL 的可用性。</span><span class="sxs-lookup"><span data-stu-id="8068a-209">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="8068a-210">您必须选择一个 URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-210">You are required to select a URL.</span></span> <span data-ttu-id="8068a-211">对于 **Spear 钓鱼** (附件) 活动，可以在下一步 (中删除邮件正文中的链接，否则邮件将同时包含链接和附件) 。 </span><span class="sxs-lookup"><span data-stu-id="8068a-211">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="8068a-212">**附件类型**：此设置仅在网络钓鱼和附件 (**活动)** 可用。</span><span class="sxs-lookup"><span data-stu-id="8068a-212">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="8068a-213">单击下拉列表并选择 **。DOCX** **或 。列表中的 PDF。**</span><span class="sxs-lookup"><span data-stu-id="8068a-213">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="8068a-214">**附件名称**：此设置仅在 **Spear 钓鱼** 和附件 (活动) 可用。</span><span class="sxs-lookup"><span data-stu-id="8068a-214">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="8068a-215">输入 .docx 或 .pdf 附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="8068a-215">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="8068a-216">**自定义登** 陆页面 URL：输入可选登录页，如果用户单击网络钓鱼链接并输入其凭据，将在此页面进行登录。</span><span class="sxs-lookup"><span data-stu-id="8068a-216">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="8068a-217">此链接将替换默认登录页面。</span><span class="sxs-lookup"><span data-stu-id="8068a-217">This link replaces the default landing page.</span></span> <span data-ttu-id="8068a-218">例如，如果你有内部意识培训，你可以在此处指定该 URL。</span><span class="sxs-lookup"><span data-stu-id="8068a-218">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="8068a-219">**主题**： **电子邮件** 的主题字段。</span><span class="sxs-lookup"><span data-stu-id="8068a-219">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="8068a-220">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8068a-220">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="8068a-221">在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="8068a-221">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="8068a-222">如果在"开始"步骤中选择了模板，则邮件正文已配置，但您可以对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="8068a-222">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="8068a-223">可以使用"电子邮件"**选项卡 (** 富 HTML 编辑器) 或源选项卡 (原始 HTML代码) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-223">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="8068a-224">HTML 格式可以像需要一样简单或复杂。</span><span class="sxs-lookup"><span data-stu-id="8068a-224">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="8068a-225">您可以插入图像和文本，以增强邮件在收件人的电子邮件客户端中的可信度。</span><span class="sxs-lookup"><span data-stu-id="8068a-225">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="8068a-226">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="8068a-226">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="8068a-227">`${loginserverurl}` 插入 **网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="8068a-227">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="8068a-228">对于 **Spear 网络钓鱼 (** 附件) 活动，应从邮件正文中删除链接 (否则，邮件将同时包含链接和附件，并且不会在附件市场活动) 中跟踪链接单击。</span><span class="sxs-lookup"><span data-stu-id="8068a-228">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8068a-229">![撰写电子邮件正文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="8068a-229">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="8068a-230">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8068a-230">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="8068a-231">在 **"确认** "步骤中，单击 **"完成** "以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="8068a-231">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="8068a-232">网络钓鱼邮件将传递给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="8068a-232">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="8068a-233">密码攻击活动</span><span class="sxs-lookup"><span data-stu-id="8068a-233">Password attack campaigns</span></span>

<span data-ttu-id="8068a-234">*密码攻击* 通常会在攻击者识别一个或多个有效用户帐户后，尝试猜测组织中用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="8068a-234">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="8068a-235">在攻击模拟器中，有两种不同类型的密码攻击活动可供你测试用户密码的复杂性：</span><span class="sxs-lookup"><span data-stu-id="8068a-235">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="8068a-236">暴力密码 (字典攻击 **) ：** 暴力或字典攻击使用用户帐户上的大型字典密码文件，希望其中一个密码 (对一个帐户) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-236">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="8068a-237">错误的密码锁定有助于阻止暴力密码攻击。</span><span class="sxs-lookup"><span data-stu-id="8068a-237">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="8068a-238">对于字典攻击，你可以指定一个或多个密码来尝试 (输入或输入上传的文件) ，也可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="8068a-238">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="8068a-239">\**密码攻击\*\*\*：密码攻击* 对用户帐户列表使用相同的经过仔细考虑的密码， (多个帐户使用一) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-239">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="8068a-240">密码感染攻击比暴力密码攻击更难检测 (当攻击者在数十个或数百个帐户上尝试一个密码，而不会降低用户不正确的密码锁定风险时，成功) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-240">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="8068a-241">对于密码攻击，只能指定一个要尝试的密码，也可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="8068a-241">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="8068a-242">攻击模拟器中的密码攻击将用户名和密码基本身份验证请求传递到终结点，因此它们还与其他身份验证方法 (AD FS、密码哈希同步、传递、PingFederate 等) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-242">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="8068a-243">对于已启用 MFA 的用户，即使密码攻击尝试其实际密码，尝试将始终注册为失败 (换句话说，MFA 用户永远不会显示在活动尝试成功尝试计数中) 。 </span><span class="sxs-lookup"><span data-stu-id="8068a-243">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="8068a-244">这是预期结果。</span><span class="sxs-lookup"><span data-stu-id="8068a-244">This is the expected result.</span></span> <span data-ttu-id="8068a-245">MFA 是帮助防止密码攻击的主要方法。</span><span class="sxs-lookup"><span data-stu-id="8068a-245">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="8068a-246">创建并启动密码攻击活动</span><span class="sxs-lookup"><span data-stu-id="8068a-246">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="8068a-247">在安全&，转到 **威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="8068a-247">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="8068a-248">在 **"模拟** 攻击"页上，根据要创建的市场活动类型进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="8068a-248">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="8068a-249">在"**暴力密码 (字典** 攻击) ，单击"启动攻击 **"或"\*\*\*\*攻击详细信息** 启动 \> **攻击"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-249">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="8068a-250">在"**密码攻击"部分**，单击 **"启动攻击**"或单击"**攻击详细信息** \> **启动攻击"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-250">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="8068a-251">" **配置密码攻击"** 向导从新的飞出控件开始。</span><span class="sxs-lookup"><span data-stu-id="8068a-251">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="8068a-252">在 **"开始**"步骤中，显示名称市场活动的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="8068a-252">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="8068a-253">在 **"目标用户"** 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="8068a-253">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="8068a-254">单击 **"通讯簿** "以选择 (或组) 的收件人。</span><span class="sxs-lookup"><span data-stu-id="8068a-254">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="8068a-255">每个目标收件人必须具有 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="8068a-255">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="8068a-256">如果在 **未输入搜索** 条件的情况下单击 **"** 筛选和应用"，将返回所有收件人并添加到市场活动。</span><span class="sxs-lookup"><span data-stu-id="8068a-256">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="8068a-257">单击 **"导入\*\*\*\*"，** 再单击"文件导入"， (CSV) 或电子邮件地址的行分隔文件中导入逗号分隔值。</span><span class="sxs-lookup"><span data-stu-id="8068a-257">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="8068a-258">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8068a-258">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="8068a-259">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8068a-259">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8068a-260">在 **"选择攻击设置** "步骤中，根据市场活动类型选择要执行什么操作：</span><span class="sxs-lookup"><span data-stu-id="8068a-260">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="8068a-261">**暴力使用密码 (字典**) ：执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="8068a-261">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="8068a-262">**手动输入密码**：在 **按 Enter** 添加密码框中，键入密码，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="8068a-262">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="8068a-263">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="8068a-263">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="8068a-264">**从字典文件** 上载密码 **：单击"** 上载"以导入每行包含一个密码和一个空最后一行的现有文本文件。</span><span class="sxs-lookup"><span data-stu-id="8068a-264">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="8068a-265">文本文件的大小必须小于或小于 10 MB，并且不能包含超过 30000 个密码。</span><span class="sxs-lookup"><span data-stu-id="8068a-265">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="8068a-266">**密码攻击**：在 **密码 () ，输入一** 个密码。</span><span class="sxs-lookup"><span data-stu-id="8068a-266">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="8068a-267">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8068a-267">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="8068a-268">在 **"确认** "步骤中，单击 **"完成** "以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="8068a-268">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="8068a-269">您指定的密码将尝试用于指定的用户。</span><span class="sxs-lookup"><span data-stu-id="8068a-269">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="8068a-270">查看市场活动结果</span><span class="sxs-lookup"><span data-stu-id="8068a-270">View campaign results</span></span>

<span data-ttu-id="8068a-271">启动市场活动后，可以在主"模拟攻击"页上检查进度 **和** 结果。</span><span class="sxs-lookup"><span data-stu-id="8068a-271">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="8068a-272">活动市场活动将显示状态栏、已完成百分比值和"已完成 (用户数) 占 (用户数) "计数。</span><span class="sxs-lookup"><span data-stu-id="8068a-272">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="8068a-273">单击 **"刷新** "按钮将更新任何活动市场活动的进度。</span><span class="sxs-lookup"><span data-stu-id="8068a-273">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="8068a-274">还可以单击" **终止"** 停止活动的市场活动。</span><span class="sxs-lookup"><span data-stu-id="8068a-274">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="8068a-275">活动完成后，状态将更改为 **攻击已完成**。</span><span class="sxs-lookup"><span data-stu-id="8068a-275">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="8068a-276">可以通过执行以下操作之一查看市场活动的结果：</span><span class="sxs-lookup"><span data-stu-id="8068a-276">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="8068a-277">在主 **"模拟攻击"** 页上 **，** 单击活动名称下的"查看报告"。</span><span class="sxs-lookup"><span data-stu-id="8068a-277">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="8068a-278">在主 **"模拟攻击"** 页上，单击部分中的"攻击详细信息"，了解攻击类型。</span><span class="sxs-lookup"><span data-stu-id="8068a-278">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="8068a-279">在打开 **的** "攻击详细信息"页上，在"攻击历史记录" **部分选择** 活动。</span><span class="sxs-lookup"><span data-stu-id="8068a-279">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="8068a-280">以上任一操作都会将你带至名为"攻击 **详细信息"的页面**。</span><span class="sxs-lookup"><span data-stu-id="8068a-280">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="8068a-281">以下各节介绍了此页上提供的每种市场活动类型的信息。</span><span class="sxs-lookup"><span data-stu-id="8068a-281">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="8068a-282">Spear Phishing (Credentials Harvest) campaign results</span><span class="sxs-lookup"><span data-stu-id="8068a-282">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="8068a-283">每个活动的"攻击详细信息 **"** 页上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8068a-283">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="8068a-284">市场活动 (开始日期/时间和结束日期/) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="8068a-284">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="8068a-285">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="8068a-285">**Total users targeted**</span></span>

- <span data-ttu-id="8068a-286">**成功尝试**：单击链接并输入其凭据 *(用户名和密码值* 的用户) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-286">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="8068a-287">**总体成功率**：成功尝试目标用户总数  /  **计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="8068a-287">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="8068a-288">**最快单击**：启动市场活动后，第一个用户单击链接需要多久。</span><span class="sxs-lookup"><span data-stu-id="8068a-288">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="8068a-289">**Average Click**： The sum of how long of everyone to click the link divided by the number of users who clicked the link.</span><span class="sxs-lookup"><span data-stu-id="8068a-289">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="8068a-290">**单击"** 成功率：由单击 (/目标用户总数"链接) 计算 **得出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="8068a-290">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="8068a-291">**最快凭据**：启动市场活动后，第一个用户输入其凭据需要多久。</span><span class="sxs-lookup"><span data-stu-id="8068a-291">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="8068a-292">**平均凭据**：每个人输入其凭据所用时间的总和除以输入其凭据的用户数。</span><span class="sxs-lookup"><span data-stu-id="8068a-292">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="8068a-293">**凭据成功率**：由输入其凭据的用户 (/目标用户总数) 百 **分比**。</span><span class="sxs-lookup"><span data-stu-id="8068a-293">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="8068a-294">显示单击的链接和凭据 **每天提供的号码** 的条形图。 </span><span class="sxs-lookup"><span data-stu-id="8068a-294">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="8068a-295">一个圆形图，显示活动的单击 **链接**、**提供的** 凭据和无百分比。</span><span class="sxs-lookup"><span data-stu-id="8068a-295">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="8068a-296">" **遭到入侵的用户** "部分列出了单击链接的用户的详细信息：</span><span class="sxs-lookup"><span data-stu-id="8068a-296">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="8068a-297">用户的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="8068a-297">The user's email address</span></span>

  - <span data-ttu-id="8068a-298">他们单击链接的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="8068a-298">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="8068a-299">客户端 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8068a-299">The client IP address.</span></span>

  - <span data-ttu-id="8068a-300">有关用户版本的 Windows 和 Web 浏览器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8068a-300">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="8068a-301">可以单击 **"导出** "将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="8068a-301">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="8068a-302">钓鱼邮件 (活动) 附件</span><span class="sxs-lookup"><span data-stu-id="8068a-302">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="8068a-303">每个活动的"攻击详细信息 **"** 页上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8068a-303">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="8068a-304">市场活动 (开始日期/时间和结束日期/) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="8068a-304">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="8068a-305">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="8068a-305">**Total users targeted**</span></span>

- <span data-ttu-id="8068a-306">**成功尝试**：打开或下载并打开附件 (预览版的用户) 。</span><span class="sxs-lookup"><span data-stu-id="8068a-306">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="8068a-307">**总体成功率**：成功尝试目标用户总数  /  **计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="8068a-307">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="8068a-308">**最短附件打开时间**：启动市场活动后第一个用户打开附件所花时间。</span><span class="sxs-lookup"><span data-stu-id="8068a-308">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="8068a-309">**平均附件打开时间**：每个人打开附件所花时间的总和除以打开附件的用户数。</span><span class="sxs-lookup"><span data-stu-id="8068a-309">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="8068a-310">**附件打开成功率**：由打开附件 (用户数/目标用户总数) 百 **分比**。</span><span class="sxs-lookup"><span data-stu-id="8068a-310">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="8068a-311">使用暴力密码 (字典攻击) 活动结果</span><span class="sxs-lookup"><span data-stu-id="8068a-311">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="8068a-312">每个活动的"攻击详细信息 **"** 页上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8068a-312">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="8068a-313">市场活动 (开始日期/时间和结束日期/) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="8068a-313">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="8068a-314">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="8068a-314">**Total users targeted**</span></span>

- <span data-ttu-id="8068a-315">**成功尝试**：发现正在使用指定密码之一的用户数。</span><span class="sxs-lookup"><span data-stu-id="8068a-315">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="8068a-316">**总体成功率**：成功尝试目标用户总数  /  **计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="8068a-316">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="8068a-317">" **遭到入侵的用户** "部分列出了受影响用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8068a-317">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="8068a-318">可以单击 **"导出** "将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="8068a-318">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="8068a-319">密码攻击活动结果</span><span class="sxs-lookup"><span data-stu-id="8068a-319">Password spray attack campaign results</span></span>

<span data-ttu-id="8068a-320">每个活动的"攻击详细信息 **"** 页上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8068a-320">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="8068a-321">市场活动 (开始日期/时间和结束日期/) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="8068a-321">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="8068a-322">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="8068a-322">**Total users targeted**</span></span>

- <span data-ttu-id="8068a-323">**成功尝试**：发现使用指定密码的用户数。</span><span class="sxs-lookup"><span data-stu-id="8068a-323">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="8068a-324">**总体成功率**：成功尝试目标用户总数  /  **计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="8068a-324">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
