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
description: 管理员可以了解如何使用攻击模拟器在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织中运行模拟钓鱼和密码攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 105ca66cdfacaab3b73d8bf89c3a05207b673a3c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921356"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="23597-103">Microsoft Defender for Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="23597-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="23597-104">**适用于** [Microsoft Defender for Office 365 计划 2](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="23597-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="23597-105">如果你的组织拥有 Microsoft Defender for Office 365 计划[](office-365-ti.md)2（包括威胁调查和响应功能）。可以使用安全 & 合规中心中的攻击模拟器在组织中运行真实的攻击方案。</span><span class="sxs-lookup"><span data-stu-id="23597-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="23597-106">这些模拟攻击可以帮助你在真实攻击影响你的最后一线之前识别和查找易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="23597-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="23597-107">阅读本文可了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="23597-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="23597-108">攻击模拟器（如本文中所述）现在是只读的，已替换为[Microsoft 365](https://security.microsoft.com)安全中心中"电子邮件&协作"节点中的攻击模拟培训。 </span><span class="sxs-lookup"><span data-stu-id="23597-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="23597-109">有关详细信息，请参阅使用攻击 [模拟培训入门](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="23597-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="23597-110">已禁用从此版本的攻击模拟器启动新模拟的能力。</span><span class="sxs-lookup"><span data-stu-id="23597-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="23597-111">但是，您仍然可以访问自 2021 年 1 月 24 日起最多 90 天的报告。</span><span class="sxs-lookup"><span data-stu-id="23597-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="23597-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="23597-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="23597-113">若要打开安全与合规中心，请转到 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="23597-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="23597-114">攻击模拟器位于威胁管理 **攻击** \> **模拟器 中**。</span><span class="sxs-lookup"><span data-stu-id="23597-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="23597-115">转到直接转到攻击模拟器，打开 <https://protection.office.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="23597-115">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="23597-116">有关不同 Microsoft 365 订阅中攻击模拟器的可用性详细信息，请参阅 [Microsoft Defender for Office 365 服务说明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="23597-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="23597-117">您必须是组织管理或 **安全管理员\*\*\*\*角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="23597-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="23597-118">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="23597-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="23597-119">你的帐户需要配置为使用 MFA (多重) ，以在攻击模拟器中创建和管理市场活动。</span><span class="sxs-lookup"><span data-stu-id="23597-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="23597-120">有关说明，请参阅 [设置多重身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="23597-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="23597-121">攻击模拟器仅适用于基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="23597-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="23597-122">网络钓鱼活动将在 30 天内收集和处理事件。</span><span class="sxs-lookup"><span data-stu-id="23597-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="23597-123">历史市场活动数据将在你启动市场活动后最多 90 天内可用。</span><span class="sxs-lookup"><span data-stu-id="23597-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="23597-124">攻击模拟和培训相关的数据与 Microsoft 365 服务的其他客户数据存储在一起。</span><span class="sxs-lookup"><span data-stu-id="23597-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="23597-125">有关详细信息，请参阅 [Microsoft 365 数据位置](../../enterprise/o365-data-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="23597-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="23597-126">攻击模拟器没有对应的 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="23597-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="23597-127">Pear phishing campaigns</span><span class="sxs-lookup"><span data-stu-id="23597-127">Spear phishing campaigns</span></span>

<span data-ttu-id="23597-128">*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="23597-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="23597-129">*Spear 网络钓鱼* 是一种有针对性的网络钓鱼攻击，它使用专为目标收件人定制的重点和自定义内容 (通常发生在攻击者对收件人重新) 之后。</span><span class="sxs-lookup"><span data-stu-id="23597-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="23597-130">在攻击模拟器中，提供了两种不同类型的钓鱼活动：</span><span class="sxs-lookup"><span data-stu-id="23597-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="23597-131">**Spear phishing (credentials harvest)**： the attack tries to tries the recipients to click a URL in the message.</span><span class="sxs-lookup"><span data-stu-id="23597-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="23597-132">如果用户单击该链接，则要求他们输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="23597-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="23597-133">如果已设置，则他们被带至以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="23597-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="23597-134">说明这只是一个测试的默认页面，并提供了识别网络钓鱼邮件的提示。</span><span class="sxs-lookup"><span data-stu-id="23597-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![用户单击网络钓鱼链接并输入其凭据时会看到什么](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="23597-136">自定义页面 (指定的) URL。</span><span class="sxs-lookup"><span data-stu-id="23597-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="23597-137">**Spear phishing (attachment)**： The attack tries to tries the recipients to open a .docx or .pdf attachment in the message.</span><span class="sxs-lookup"><span data-stu-id="23597-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="23597-138">附件包含来自默认网络钓鱼链接的相同内容，但第一句以" 开头，你将看到此邮件为打开 \<Display Name\> 的最近电子邮件..."。</span><span class="sxs-lookup"><span data-stu-id="23597-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="23597-139">目前，攻击模拟器中的钓鱼活动不会到期。</span><span class="sxs-lookup"><span data-stu-id="23597-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="23597-140">创建钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="23597-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="23597-141">任何网络钓鱼活动的一个重要部分是发送给目标收件人的电子邮件的外观。</span><span class="sxs-lookup"><span data-stu-id="23597-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="23597-142">若要创建和配置电子邮件，有以下选项：</span><span class="sxs-lookup"><span data-stu-id="23597-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="23597-143">**使用内置电子邮件模板**：有两个内置模板可用 **：Giveaway 和** **Payroll Update**。</span><span class="sxs-lookup"><span data-stu-id="23597-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="23597-144">创建和启动市场活动时，可以进一步自定义模板中的部分、全部或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="23597-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="23597-145">**创建可重用的电子邮件模板**：创建并保存电子邮件模板后，可以在将来的网络钓鱼活动中再次使用它。</span><span class="sxs-lookup"><span data-stu-id="23597-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="23597-146">创建和启动市场活动时，可以进一步自定义模板中的部分、全部或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="23597-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="23597-147">**在向导中创建** 电子邮件：可以在创建和启动网络钓鱼活动时直接在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="23597-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="23597-148">步骤 1 (可选) ：创建自定义电子邮件模板</span><span class="sxs-lookup"><span data-stu-id="23597-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="23597-149">如果要使用其中一个内置模板或直接在向导中创建电子邮件，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="23597-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="23597-150">在安全与&中心，转到威胁 **管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="23597-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="23597-151">在"**模拟** 攻击"页面上，在 **"Spear Phishing (Credentials Harvest) "** 或 **"Spear Phishing (Attachment) "** 部分中，单击"**攻击详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="23597-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="23597-152">在哪里创建模板并不重要。</span><span class="sxs-lookup"><span data-stu-id="23597-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="23597-153">模板中的可用选项对于这两种类型的网络钓鱼攻击是相同的。</span><span class="sxs-lookup"><span data-stu-id="23597-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="23597-154">在打开 **的"** 攻击详细信息"页的"网络钓鱼模板"部分，**在"创建** 模板"区域中，单击"新建 **模板"。**</span><span class="sxs-lookup"><span data-stu-id="23597-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="23597-155">" **配置网络钓鱼模板"** 向导将启动一个新的飞出控件。</span><span class="sxs-lookup"><span data-stu-id="23597-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="23597-156">在"**开始**"步骤中，为显示名称输入唯一名称，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="23597-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="23597-157">在" **配置电子邮件详细信息** "步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="23597-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="23597-158">**From (Name)**： the 显示名称 that's used for the message sender.</span><span class="sxs-lookup"><span data-stu-id="23597-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="23597-159">**发件人 (电子邮件) ：** 发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23597-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="23597-160">**网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="23597-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="23597-161">这是用户将尝试单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="23597-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="23597-162">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="23597-162">The choices are:</span></span>

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
     > <span data-ttu-id="23597-163">URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="23597-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="23597-164">在网络钓鱼活动中使用该 URL 之前，请检查 URL 在受支持的 Web 浏览器中的可用性。</span><span class="sxs-lookup"><span data-stu-id="23597-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="23597-165">**自定义登陆页面 URL：** 输入可选登陆页面，如果用户单击网络钓鱼链接并输入其凭据，将在此进行登录。</span><span class="sxs-lookup"><span data-stu-id="23597-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="23597-166">此链接将替换默认登陆页面。</span><span class="sxs-lookup"><span data-stu-id="23597-166">This link replaces the default landing page.</span></span> <span data-ttu-id="23597-167">例如，如果你有内部意识培训，可以在此处指定该 URL。</span><span class="sxs-lookup"><span data-stu-id="23597-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="23597-168">**类别**：当前，此设置不用于 (输入的项将被忽略) 。</span><span class="sxs-lookup"><span data-stu-id="23597-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="23597-169">**主题**： **电子邮件** 的主题字段。</span><span class="sxs-lookup"><span data-stu-id="23597-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="23597-170">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="23597-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="23597-171">在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="23597-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="23597-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code) .</span><span class="sxs-lookup"><span data-stu-id="23597-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="23597-173">HTML 格式可以像您所需的一样简单或复杂。</span><span class="sxs-lookup"><span data-stu-id="23597-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="23597-174">您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的可信度。</span><span class="sxs-lookup"><span data-stu-id="23597-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="23597-175">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="23597-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="23597-176">`${loginserverurl}` 插入上 **一步中的网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="23597-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="23597-177">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="23597-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="23597-178">在"**确认"** 步骤中，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="23597-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="23597-179">步骤 2：创建和启动网络钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="23597-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="23597-180">在安全与&中心，转到威胁 **管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="23597-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="23597-181">在 **"模拟攻击** "页上，根据要创建的市场活动类型进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="23597-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="23597-182">在 **"Spear Phishing (Credentials Harvest) "** 部分中，单击"启动攻击"或 **单击"\*\*\*\*攻击详细信息** 启动攻击 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="23597-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="23597-183">在 **"Spear Phishing (Attachment) "** 部分中，单击"启动攻击"或 **单击"\*\*\*\*攻击详细信息** 启动攻击 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="23597-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="23597-184">" **配置网络钓鱼攻击"** 向导从新的飞出控件开始。</span><span class="sxs-lookup"><span data-stu-id="23597-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="23597-185">在 **"开始** "步骤中，执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="23597-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="23597-186">在" **名称** "框中，为显示名称输入唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="23597-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="23597-187">不要单击" **使用模板"，** 因为稍后您将在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="23597-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="23597-188">单击 **"使用** 模板"，然后选择内置或自定义电子邮件模板。</span><span class="sxs-lookup"><span data-stu-id="23597-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="23597-189">选择模板后，"名称"框将基于模板自动填充，但您可以更改名称。</span><span class="sxs-lookup"><span data-stu-id="23597-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="23597-190">![网络钓鱼起始页](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="23597-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="23597-191">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="23597-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="23597-192">在 **"目标收件人"** 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="23597-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="23597-193">单击 **"通讯簿** "以选择 (活动) 或组的用户或组。</span><span class="sxs-lookup"><span data-stu-id="23597-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="23597-194">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="23597-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="23597-195">如果在 **未输入搜索\*\*\*\*条件** 的情况下单击"筛选"和"应用"，将返回所有收件人并添加到活动。</span><span class="sxs-lookup"><span data-stu-id="23597-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="23597-196">单击 **"** 导入 **"，** 然后单击"文件导入"，以 (CSV) 或电子邮件地址的行分隔文件导入逗号分隔值。</span><span class="sxs-lookup"><span data-stu-id="23597-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="23597-197">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23597-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="23597-198">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="23597-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="23597-199">在" **配置电子邮件详细信息** "步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="23597-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="23597-200">如果在"开始"步骤 **中** 选择了模板，则大部分这些值已配置，但您可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="23597-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="23597-201">**From (Name)**： the 显示名称 that's used for the message sender.</span><span class="sxs-lookup"><span data-stu-id="23597-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="23597-202">**发件人 (电子邮件) ：** 发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23597-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="23597-203">你可以从组织的电子邮件域输入真实或假的电子邮件地址，也可以输入真实或假的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23597-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="23597-204">您组织的有效发件人电子邮件地址实际上将在收件人的电子邮件客户端中解析。</span><span class="sxs-lookup"><span data-stu-id="23597-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="23597-205">**网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="23597-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="23597-206">这是用户将尝试单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="23597-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="23597-207">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="23597-207">The choices are:</span></span>

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
     > - <span data-ttu-id="23597-208">所有 URL 都是有意的 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="23597-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="23597-209">URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="23597-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="23597-210">在网络钓鱼活动中使用该 URL 之前，请检查 URL 在受支持的 Web 浏览器中的可用性。</span><span class="sxs-lookup"><span data-stu-id="23597-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="23597-211">您需要选择 URL。</span><span class="sxs-lookup"><span data-stu-id="23597-211">You are required to select a URL.</span></span> <span data-ttu-id="23597-212">对于 **网络钓鱼** (附件) 活动，可以在下一步中删除邮件正文中的链接 (否则邮件将包含链接和附件) 。 </span><span class="sxs-lookup"><span data-stu-id="23597-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="23597-213">**附件类型**：此设置仅在网络网络钓鱼和附件 (**活动中)** 可用。</span><span class="sxs-lookup"><span data-stu-id="23597-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="23597-214">单击下拉列表并选择 **。DOCX** 或 **。列表中的 PDF。**</span><span class="sxs-lookup"><span data-stu-id="23597-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="23597-215">**附件名称**：此设置仅在网络网络钓鱼和附件 (**活动中)** 可用。</span><span class="sxs-lookup"><span data-stu-id="23597-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="23597-216">输入 .docx 或 .pdf 附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="23597-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="23597-217">**自定义登陆页面 URL：** 输入可选登陆页面，如果用户单击网络钓鱼链接并输入其凭据，将在此进行登录。</span><span class="sxs-lookup"><span data-stu-id="23597-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="23597-218">此链接将替换默认登陆页面。</span><span class="sxs-lookup"><span data-stu-id="23597-218">This link replaces the default landing page.</span></span> <span data-ttu-id="23597-219">例如，如果你有内部意识培训，可以在此处指定该 URL。</span><span class="sxs-lookup"><span data-stu-id="23597-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="23597-220">**主题**： **电子邮件** 的主题字段。</span><span class="sxs-lookup"><span data-stu-id="23597-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="23597-221">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="23597-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="23597-222">在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="23597-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="23597-223">如果在"开始"步骤 **中** 选择了模板，则消息正文已配置，但您可以对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="23597-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="23597-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code) .</span><span class="sxs-lookup"><span data-stu-id="23597-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="23597-225">HTML 格式可以像您所需的一样简单或复杂。</span><span class="sxs-lookup"><span data-stu-id="23597-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="23597-226">您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的可信度。</span><span class="sxs-lookup"><span data-stu-id="23597-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="23597-227">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="23597-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="23597-228">`${loginserverurl}` 插入 **网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="23597-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="23597-229">对于网络钓鱼 (附件 **)** 活动，应从邮件正文中删除链接 (否则，邮件将同时包含链接和附件，并且附件市场活动) 中不会跟踪链接单击。 </span><span class="sxs-lookup"><span data-stu-id="23597-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="23597-230">![撰写电子邮件正文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="23597-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="23597-231">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="23597-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="23597-232">在" **确认"** 步骤中，单击 **"完成** "以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="23597-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="23597-233">网络钓鱼邮件将传递到目标收件人。</span><span class="sxs-lookup"><span data-stu-id="23597-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="23597-234">密码攻击活动</span><span class="sxs-lookup"><span data-stu-id="23597-234">Password attack campaigns</span></span>

<span data-ttu-id="23597-235">*密码攻击* 通常会在攻击者标识一个或多个有效用户帐户后，尝试猜测组织中用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="23597-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="23597-236">在攻击模拟器中，有两种不同类型的密码攻击活动可供你测试用户密码的复杂性：</span><span class="sxs-lookup"><span data-stu-id="23597-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="23597-237">暴力密码 (字典攻击 **) ：** 暴力或字典攻击使用用户帐户上的大型字典密码文件，希望其中一个能够 (一个帐户密码) 。</span><span class="sxs-lookup"><span data-stu-id="23597-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="23597-238">不正确的密码锁定有助于阻止暴力密码攻击。</span><span class="sxs-lookup"><span data-stu-id="23597-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="23597-239">对于字典攻击，你可以指定一个或多个密码来尝试手动输入 (或上传的文件) ，你可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="23597-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="23597-240">\**密码加密\*\*\*攻击：密码* 攻击针对用户帐户列表使用同一个仔细考虑的密码， (多个帐户使用一) 。</span><span class="sxs-lookup"><span data-stu-id="23597-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="23597-241">密码增强攻击比暴力密码攻击更难检测 (攻击者在数十个或数百个帐户上尝试一个密码时，成功的可能性会提高，而不会消除用户错误的密码锁定) 。</span><span class="sxs-lookup"><span data-stu-id="23597-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="23597-242">对于密码攻击，你只能指定一个要尝试的密码，并且可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="23597-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="23597-243">攻击模拟器中的密码攻击将用户名和密码 基本身份验证请求传递到终结点，因此它们还与其他身份验证方法 (AD FS、密码哈希同步、传递、PingFederate 等一起) 。</span><span class="sxs-lookup"><span data-stu-id="23597-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="23597-244">对于启用了 MFA 的用户，即使密码攻击尝试其实际密码，尝试将始终注册为失败 (换句话说，MFA 用户永远不会显示在活动) 的成功尝试计数中。 </span><span class="sxs-lookup"><span data-stu-id="23597-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="23597-245">这是预期结果。</span><span class="sxs-lookup"><span data-stu-id="23597-245">This is the expected result.</span></span> <span data-ttu-id="23597-246">MFA 是帮助防止密码攻击的主要方法。</span><span class="sxs-lookup"><span data-stu-id="23597-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="23597-247">创建并启动密码攻击活动</span><span class="sxs-lookup"><span data-stu-id="23597-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="23597-248">在安全与&中心，转到威胁 **管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="23597-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="23597-249">在 **"模拟攻击** "页上，根据要创建的市场活动类型进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="23597-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="23597-250">在"**暴力密码 (字典**) 攻击"部分，单击"启动攻击"或单击"攻击 **详细信息** 启动攻击 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="23597-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="23597-251">在"**密码攻击"部分**，单击 **"启动攻击"** 或单击"**攻击详细信息** \> **启动攻击"。**</span><span class="sxs-lookup"><span data-stu-id="23597-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="23597-252">配置 **密码攻击** 向导将启动一个新的飞出控件。</span><span class="sxs-lookup"><span data-stu-id="23597-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="23597-253">在"**开始**"步骤中，为显示名称输入唯一名称，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="23597-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="23597-254">在 **"目标用户"** 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="23597-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="23597-255">单击 **"通讯簿** "以选择 (活动) 或组的用户或组。</span><span class="sxs-lookup"><span data-stu-id="23597-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="23597-256">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="23597-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="23597-257">如果在 **未输入搜索\*\*\*\*条件** 的情况下单击"筛选"和"应用"，将返回所有收件人并添加到活动。</span><span class="sxs-lookup"><span data-stu-id="23597-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="23597-258">单击 **"** 导入 **"，** 然后单击"文件导入"，以 (CSV) 或电子邮件地址的行分隔文件导入逗号分隔值。</span><span class="sxs-lookup"><span data-stu-id="23597-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="23597-259">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23597-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="23597-260">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="23597-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="23597-261">在 **"选择攻击设置"** 步骤中，根据市场活动类型选择要执行哪些操作：</span><span class="sxs-lookup"><span data-stu-id="23597-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="23597-262">**暴力密码 (字典) ：** 执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="23597-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="23597-263">**手动输入密码**：在 **"按 Enter 添加密码"框中** ，键入密码，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="23597-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="23597-264">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="23597-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="23597-265">**从字典文件上载** 密码：单击"上载"导入现有文本文件，其中包含每行一个密码和一个空最后一行。</span><span class="sxs-lookup"><span data-stu-id="23597-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="23597-266">文本文件的大小必须小于或小于 10 MB，并且不能超过 30000 个密码。</span><span class="sxs-lookup"><span data-stu-id="23597-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="23597-267">**密码攻击**：在 **密码 () 攻击框中输入** 一个密码。</span><span class="sxs-lookup"><span data-stu-id="23597-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="23597-268">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="23597-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="23597-269">在" **确认"** 步骤中，单击 **"完成** "以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="23597-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="23597-270">指定的密码将尝试用于指定的用户。</span><span class="sxs-lookup"><span data-stu-id="23597-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="23597-271">查看市场活动结果</span><span class="sxs-lookup"><span data-stu-id="23597-271">View campaign results</span></span>

<span data-ttu-id="23597-272">启动市场活动后，可以在主"模拟攻击"页面上查看 **进度和** 结果。</span><span class="sxs-lookup"><span data-stu-id="23597-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="23597-273">活动市场活动将显示状态栏、完成的百分比值和"已完成 (用户数)  (用户数) "计数。</span><span class="sxs-lookup"><span data-stu-id="23597-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="23597-274">单击 **"刷新** "按钮将更新任何活动市场活动的进度。</span><span class="sxs-lookup"><span data-stu-id="23597-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="23597-275">还可以单击"终止 **"** 停止活动市场活动。</span><span class="sxs-lookup"><span data-stu-id="23597-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="23597-276">市场活动完成后，状态将更改为 **"攻击已完成"。**</span><span class="sxs-lookup"><span data-stu-id="23597-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="23597-277">可以通过执行以下操作之一查看市场活动的结果：</span><span class="sxs-lookup"><span data-stu-id="23597-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="23597-278">在主" **模拟攻击"** 页上， **单击活动** 名称下的"查看报告"。</span><span class="sxs-lookup"><span data-stu-id="23597-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="23597-279">在主" **模拟攻击"** 页面上，单击 **部分中的"** 攻击详细信息"，了解攻击类型。</span><span class="sxs-lookup"><span data-stu-id="23597-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="23597-280">在打开 **的"** 攻击详细信息"页面上，选择"攻击 **历史记录"部分中的** 活动。</span><span class="sxs-lookup"><span data-stu-id="23597-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="23597-281">以上任一操作都会将你带至名为"攻击详细信息 **"的页面**。</span><span class="sxs-lookup"><span data-stu-id="23597-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="23597-282">以下各节介绍了此页面上提供的每种市场活动类型的信息。</span><span class="sxs-lookup"><span data-stu-id="23597-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="23597-283">Spear Phishing (Credentials Harvest) campaign results</span><span class="sxs-lookup"><span data-stu-id="23597-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="23597-284">每个市场活动的"攻击 **详细信息** "页面上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="23597-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="23597-285">市场活动 (/时间和结束日期/时间) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="23597-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="23597-286">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="23597-286">**Total users targeted**</span></span>

- <span data-ttu-id="23597-287">**成功尝试**：单击链接并输入其凭据的用户 (*用户名和密码* 值) 。</span><span class="sxs-lookup"><span data-stu-id="23597-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="23597-288">**总体成功** 率：成功尝试总目标用户数  /  **计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="23597-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="23597-289">**最快单击**：启动市场活动后，第一个用户单击链接所用时间。</span><span class="sxs-lookup"><span data-stu-id="23597-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="23597-290">**平均单击** 次数：单击链接所用时间与单击链接的用户数之和。</span><span class="sxs-lookup"><span data-stu-id="23597-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="23597-291">**单击"** 成功率"：单击链接 (用户数/目标用户总数) 计算 **得出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="23597-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="23597-292">**最快凭据**：启动市场活动后，第一个用户输入其凭据所用时间。</span><span class="sxs-lookup"><span data-stu-id="23597-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="23597-293">**平均凭据**：每个人输入凭据所用时间与输入凭据的用户数之和。</span><span class="sxs-lookup"><span data-stu-id="23597-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="23597-294">**凭据成功** 率：一个百分比，由 (凭据的用户数/目标) 用户 **总数计算** 得出的百分比。</span><span class="sxs-lookup"><span data-stu-id="23597-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="23597-295">显示单击的链接 **和\*\*\*\*凭据提供的号码** 每天的条形图。</span><span class="sxs-lookup"><span data-stu-id="23597-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="23597-296">一个圆形图，显示活动的 **单击链接**、**提供凭据** 和无百分比。</span><span class="sxs-lookup"><span data-stu-id="23597-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="23597-297">" **遭到入侵的用户** "部分列出了单击链接的用户的详细信息：</span><span class="sxs-lookup"><span data-stu-id="23597-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="23597-298">用户的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="23597-298">The user's email address</span></span>

  - <span data-ttu-id="23597-299">用户单击链接时的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="23597-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="23597-300">客户端 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="23597-300">The client IP address.</span></span>

  - <span data-ttu-id="23597-301">有关用户版本的 Windows 和 Web 浏览器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="23597-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="23597-302">可以单击 **"导出** "将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="23597-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="23597-303">Spear Phishing (Attachment) campaign results</span><span class="sxs-lookup"><span data-stu-id="23597-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="23597-304">每个市场活动的"攻击 **详细信息** "页面上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="23597-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="23597-305">市场活动 (/时间和结束日期/时间) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="23597-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="23597-306">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="23597-306">**Total users targeted**</span></span>

- <span data-ttu-id="23597-307">**成功尝试**：在预览版中打开或下载并打开附件 (用户数) 。</span><span class="sxs-lookup"><span data-stu-id="23597-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="23597-308">**总体成功** 率：成功尝试总目标用户数  /  **计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="23597-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="23597-309">**最快附件打开时间**：启动市场活动后第一个用户打开附件所花时间。</span><span class="sxs-lookup"><span data-stu-id="23597-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="23597-310">**平均附件打开时间**：每个人打开附件所花时间与打开附件的用户数之和。</span><span class="sxs-lookup"><span data-stu-id="23597-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="23597-311">**附件打开成功率**：由打开附件 (的用户数/目标) 用户 **总数计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="23597-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="23597-312">暴力密码 (字典) 活动结果</span><span class="sxs-lookup"><span data-stu-id="23597-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="23597-313">每个市场活动的"攻击 **详细信息** "页面上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="23597-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="23597-314">市场活动 (/时间和结束日期/时间) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="23597-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="23597-315">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="23597-315">**Total users targeted**</span></span>

- <span data-ttu-id="23597-316">**成功尝试**：发现使用指定密码之一的用户数。</span><span class="sxs-lookup"><span data-stu-id="23597-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="23597-317">**总体成功** 率：成功尝试总目标用户数  /  **计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="23597-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="23597-318">" **遭到入侵的用户** "部分列出了受影响用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="23597-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="23597-319">可以单击 **"导出** "将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="23597-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="23597-320">密码化攻击活动结果</span><span class="sxs-lookup"><span data-stu-id="23597-320">Password spray attack campaign results</span></span>

<span data-ttu-id="23597-321">每个市场活动的"攻击 **详细信息** "页面上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="23597-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="23597-322">市场活动 (/时间和结束日期/时间) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="23597-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="23597-323">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="23597-323">**Total users targeted**</span></span>

- <span data-ttu-id="23597-324">**成功尝试**：发现使用指定密码的用户数。</span><span class="sxs-lookup"><span data-stu-id="23597-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="23597-325">**总体成功** 率：成功尝试总目标用户数  /  **计算出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="23597-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>