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
ms.openlocfilehash: 824ee04e2fcf0757a7eb32b48246bf1a1c638926
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175879"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7180b-103">Microsoft Defender for Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="7180b-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7180b-104">**适用于** [Microsoft Defender for Office 365 计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span><span class="sxs-lookup"><span data-stu-id="7180b-104">**Applies to** [Microsoft Defender for Office 365 plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span></span>

<span data-ttu-id="7180b-105">如果你的组织具有 Microsoft Defender for Office 365 计划 2（包括威胁调查和响应 & [功能](office-365-ti.md)），可以使用安全与合规中心中的攻击模拟器在组织中运行真实的攻击方案。</span><span class="sxs-lookup"><span data-stu-id="7180b-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="7180b-106">这些模拟攻击可以帮助你在真正的攻击影响你的最后一线之前识别和查找易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="7180b-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="7180b-107">阅读本文可了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="7180b-107">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7180b-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="7180b-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7180b-109">若要打开安全与合规中心，请转到 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="7180b-109">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="7180b-110">攻击模拟器在 **威胁管理攻击** \> **模拟器中可用**。</span><span class="sxs-lookup"><span data-stu-id="7180b-110">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="7180b-111">转到直接进入攻击模拟器，打开 <https://protection.office.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="7180b-111">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="7180b-112">有关不同 Microsoft 365 订阅中攻击模拟器的可用性详细信息，请参阅 [Microsoft Defender for Office 365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="7180b-112">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="7180b-113">您必须是组织管理或 **安全管理员角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="7180b-113">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="7180b-114">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7180b-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7180b-115">你的帐户需要配置为使用 MFA (多重身份验证) 在攻击模拟器中创建和管理市场活动。</span><span class="sxs-lookup"><span data-stu-id="7180b-115">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="7180b-116">有关说明，请参阅["设置多重身份验证"。](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="7180b-116">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="7180b-117">网络钓鱼活动将在 30 天内收集和处理事件。</span><span class="sxs-lookup"><span data-stu-id="7180b-117">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="7180b-118">历史市场活动数据将在你启动市场活动后最多 90 天内可用。</span><span class="sxs-lookup"><span data-stu-id="7180b-118">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="7180b-119">攻击模拟和培训相关的数据存储在 Microsoft 365 服务的其他客户数据中。</span><span class="sxs-lookup"><span data-stu-id="7180b-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="7180b-120">有关详细信息，请参阅 [Microsoft 365 数据位置](/microsoft-365/enterprise/o365-data-locations)。</span><span class="sxs-lookup"><span data-stu-id="7180b-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="7180b-121">攻击模拟器没有对应的 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7180b-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="7180b-122">网络钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="7180b-122">Spear phishing campaigns</span></span>

<span data-ttu-id="7180b-123">*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7180b-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="7180b-124">*网络钓鱼* 是一种目标网络钓鱼攻击，它使用专门针对目标收件人定制的重点和自定义内容 (通常，在攻击者重新识别收件人后) 。</span><span class="sxs-lookup"><span data-stu-id="7180b-124">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="7180b-125">在攻击模拟器中，提供了两种不同类型的网络钓鱼活动：</span><span class="sxs-lookup"><span data-stu-id="7180b-125">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="7180b-126">**Spear phishing (credentials harvest) ：** the attack tries to tries the recipients to click a URL in the message.</span><span class="sxs-lookup"><span data-stu-id="7180b-126">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="7180b-127">如果用户单击该链接，将要求他们输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="7180b-127">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="7180b-128">如果已设置，则他们被带至以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="7180b-128">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="7180b-129">一个默认页面，说明这只是一个测试，并提供了识别网络钓鱼邮件的提示。</span><span class="sxs-lookup"><span data-stu-id="7180b-129">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![用户单击网络钓鱼链接并输入其凭据时所看到的内容](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="7180b-131">您指定的 (URL) 自定义页面。</span><span class="sxs-lookup"><span data-stu-id="7180b-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="7180b-132">**Spear phishing (attachment)**： the attack tries to tries the recipients to open a .docx or .pdf attachment in the message.</span><span class="sxs-lookup"><span data-stu-id="7180b-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="7180b-133">附件包含来自默认网络钓鱼链接的相同内容，但第一句以"开头，你将看到此邮件是打开的最近电子邮件 \<Display Name\> ..."。</span><span class="sxs-lookup"><span data-stu-id="7180b-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="7180b-134">目前，攻击模拟器中的网络钓鱼活动不会过期。</span><span class="sxs-lookup"><span data-stu-id="7180b-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="7180b-135">创建网络钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="7180b-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="7180b-136">任何钓鱼活动的重要组成部分是发送给目标收件人的电子邮件的外观。</span><span class="sxs-lookup"><span data-stu-id="7180b-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="7180b-137">若要创建和配置电子邮件，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="7180b-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="7180b-138">**使用内置电子邮件模板：** 有两个内置模板可用 **：Give Giveaway** 和 Payroll **Update。**</span><span class="sxs-lookup"><span data-stu-id="7180b-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="7180b-139">创建和启动市场活动时，可以进一步自定义模板中的部分、所有或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="7180b-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="7180b-140">**创建可重用的电子邮件模板**：创建并保存电子邮件模板后，可以在将来的网络钓鱼活动中再次使用它。</span><span class="sxs-lookup"><span data-stu-id="7180b-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="7180b-141">创建和启动市场活动时，可以进一步自定义模板中的部分、所有或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="7180b-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="7180b-142">**在向导中** 创建电子邮件：可以在创建和启动网络钓鱼活动时直接在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7180b-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="7180b-143">步骤 1 (可选) ：创建自定义电子邮件模板</span><span class="sxs-lookup"><span data-stu-id="7180b-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="7180b-144">如果要使用内置模板之一或直接在向导中创建电子邮件，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="7180b-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="7180b-145">在安全&中心，转到 **威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="7180b-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7180b-146">在"模拟攻击"页上的 **"Spear Phishing (Credentials Harvest)** 或 **Spear Phish (Attachment)** 部分中，单击"攻击 **详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="7180b-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="7180b-147">从何处创建模板并不重要。</span><span class="sxs-lookup"><span data-stu-id="7180b-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="7180b-148">模板中的可用选项对于这两种类型的网络钓鱼攻击是相同的。</span><span class="sxs-lookup"><span data-stu-id="7180b-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="7180b-149">在打开 **的**"攻击详细信息"页的"网络钓鱼模板"部分，**在"创建** 模板"区域中，单击 **"新建模板"。**</span><span class="sxs-lookup"><span data-stu-id="7180b-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="7180b-150">" **配置网络钓鱼模板"** 向导将启动一个新的飞出控件。</span><span class="sxs-lookup"><span data-stu-id="7180b-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="7180b-151">在 **"开始**"步骤中，显示名称模板的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="7180b-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="7180b-152">在 **"配置电子邮件详细信息** "步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="7180b-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="7180b-153">**From (Name)**： the 显示名称 the 显示名称 that's used for the message sender.</span><span class="sxs-lookup"><span data-stu-id="7180b-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="7180b-154">**发件人 (电子邮件) ：** 发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7180b-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="7180b-155">**网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="7180b-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="7180b-156">这是用户将尝试单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="7180b-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="7180b-157">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="7180b-157">The choices are:</span></span>

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
     > <span data-ttu-id="7180b-158">URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="7180b-158">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="7180b-159">在网络钓鱼活动中使用 URL 之前，请检查受支持的 Web 浏览器中 URL 的可用性。</span><span class="sxs-lookup"><span data-stu-id="7180b-159">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="7180b-160">**自定义登** 陆页面 URL：输入可选登录页面，如果用户单击网络钓鱼链接并输入其凭据，将在此页面进行登录。</span><span class="sxs-lookup"><span data-stu-id="7180b-160">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="7180b-161">此链接将替换默认登录页面。</span><span class="sxs-lookup"><span data-stu-id="7180b-161">This link replaces the default landing page.</span></span> <span data-ttu-id="7180b-162">例如，如果你有内部意识培训，你可以在此处指定该 URL。</span><span class="sxs-lookup"><span data-stu-id="7180b-162">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="7180b-163">**类别**：当前，此设置不会用于 (输入的项都被忽略) 。</span><span class="sxs-lookup"><span data-stu-id="7180b-163">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="7180b-164">**主题**： **电子邮件** 的主题字段。</span><span class="sxs-lookup"><span data-stu-id="7180b-164">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="7180b-165">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7180b-165">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7180b-166">在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="7180b-166">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="7180b-167">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code) .</span><span class="sxs-lookup"><span data-stu-id="7180b-167">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="7180b-168">HTML 格式可以像需要一样简单或复杂。</span><span class="sxs-lookup"><span data-stu-id="7180b-168">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="7180b-169">您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的可信度。</span><span class="sxs-lookup"><span data-stu-id="7180b-169">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="7180b-170">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="7180b-170">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="7180b-171">`${loginserverurl}` 插入上 **一步中的网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="7180b-171">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="7180b-172">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7180b-172">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="7180b-173">在"**确认"** 步骤中，单击"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="7180b-173">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="7180b-174">步骤 2：创建和启动网络钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="7180b-174">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="7180b-175">在安全&中心，转到 **威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="7180b-175">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7180b-176">在 **"模拟** 攻击"页上，根据要创建的市场活动类型进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="7180b-176">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="7180b-177">在 **"网络钓鱼凭据 (** 获取) 部分，单击"启动攻击"**或"攻击** 详细信息启动攻击 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="7180b-177">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="7180b-178">在 **"网络钓鱼 (附件**) ，单击"启动攻击"或"攻击详细信息启动攻击 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="7180b-178">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="7180b-179">" **配置网络钓鱼攻击"** 向导从新的飞出控件开始。</span><span class="sxs-lookup"><span data-stu-id="7180b-179">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="7180b-180">在 **"开始** "步骤中，执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="7180b-180">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7180b-181">在 **"名称** "框中，为显示名称一个唯一名称。</span><span class="sxs-lookup"><span data-stu-id="7180b-181">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="7180b-182">请勿单击 **"使用模板"，** 因为稍后您将在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7180b-182">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="7180b-183">单击 **"使用** 模板"，然后选择内置或自定义电子邮件模板。</span><span class="sxs-lookup"><span data-stu-id="7180b-183">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="7180b-184">选择模板后，根据模板自动填充"名称"框，但可以更改名称。</span><span class="sxs-lookup"><span data-stu-id="7180b-184">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7180b-185">![网络钓鱼起始页](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="7180b-185">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="7180b-186">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7180b-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7180b-187">在 **"目标收件人"** 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="7180b-187">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7180b-188">单击 **"通讯簿** "以选择 (活动) 或组的收件人。</span><span class="sxs-lookup"><span data-stu-id="7180b-188">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="7180b-189">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="7180b-189">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="7180b-190">如果在 **未输入搜索\*\*\*\*条件** 的情况下单击"筛选和应用"，将返回所有收件人并添加到活动。</span><span class="sxs-lookup"><span data-stu-id="7180b-190">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="7180b-191">单击 **"** 导入然后文件 **导入** "以将逗号分隔值 (CSV) 或电子邮件地址的行分隔文件中。</span><span class="sxs-lookup"><span data-stu-id="7180b-191">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="7180b-192">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7180b-192">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="7180b-193">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7180b-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7180b-194">在 **"配置电子邮件详细信息** "步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="7180b-194">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="7180b-195">如果在"开始"步骤中选择了模板，则其中大多数值已配置，但您可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="7180b-195">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="7180b-196">**From (Name)**： the 显示名称 the 显示名称 that's used for the message sender.</span><span class="sxs-lookup"><span data-stu-id="7180b-196">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="7180b-197">**发件人 (电子邮件) ：** 发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7180b-197">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="7180b-198">你可以从组织的电子邮件域输入真实或假的电子邮件地址，也可以输入真实或假的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7180b-198">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="7180b-199">您组织的有效发件人电子邮件地址实际上将在收件人的电子邮件客户端中解析。</span><span class="sxs-lookup"><span data-stu-id="7180b-199">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="7180b-200">**网络钓鱼登录服务器 URL：** 单击下拉列表，然后从列表中选择一个可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="7180b-200">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="7180b-201">这是用户将尝试单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="7180b-201">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="7180b-202">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="7180b-202">The choices are:</span></span>

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
     > - <span data-ttu-id="7180b-203">所有 URL 都是有意 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="7180b-203">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="7180b-204">URL 信誉服务可能会将其中一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="7180b-204">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="7180b-205">在网络钓鱼活动中使用 URL 之前，请检查受支持的 Web 浏览器中 URL 的可用性。</span><span class="sxs-lookup"><span data-stu-id="7180b-205">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="7180b-206">您需要选择 URL。</span><span class="sxs-lookup"><span data-stu-id="7180b-206">You are required to select a URL.</span></span> <span data-ttu-id="7180b-207">对于 **网络钓鱼** (附件) 活动，可以在下一步骤中删除邮件正文中的链接 (否则，邮件将同时包含链接和附件) 。 </span><span class="sxs-lookup"><span data-stu-id="7180b-207">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="7180b-208">**附件类型**：此设置仅在网络钓鱼和附件 (**活动)** 可用。</span><span class="sxs-lookup"><span data-stu-id="7180b-208">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="7180b-209">单击下拉列表并选择 **。DOCX** **或 。列表中的 PDF。**</span><span class="sxs-lookup"><span data-stu-id="7180b-209">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="7180b-210">**附件名称**：此设置仅适用于网络钓鱼 (**活动**) 活动。</span><span class="sxs-lookup"><span data-stu-id="7180b-210">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="7180b-211">输入 .docx 或 .pdf 附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="7180b-211">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="7180b-212">**自定义登** 陆页面 URL：输入可选登录页面，如果用户单击网络钓鱼链接并输入其凭据，将在此页面进行登录。</span><span class="sxs-lookup"><span data-stu-id="7180b-212">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="7180b-213">此链接将替换默认登录页面。</span><span class="sxs-lookup"><span data-stu-id="7180b-213">This link replaces the default landing page.</span></span> <span data-ttu-id="7180b-214">例如，如果你有内部意识培训，你可以在此处指定该 URL。</span><span class="sxs-lookup"><span data-stu-id="7180b-214">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="7180b-215">**主题**： **电子邮件** 的主题字段。</span><span class="sxs-lookup"><span data-stu-id="7180b-215">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="7180b-216">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7180b-216">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7180b-217">在 **"撰写电子邮件** "步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="7180b-217">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="7180b-218">如果在"开始"步骤 **中** 选择了模板，则邮件正文已配置，但您可以对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="7180b-218">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="7180b-219">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code) .</span><span class="sxs-lookup"><span data-stu-id="7180b-219">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="7180b-220">HTML 格式可以像需要一样简单或复杂。</span><span class="sxs-lookup"><span data-stu-id="7180b-220">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="7180b-221">您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的可信度。</span><span class="sxs-lookup"><span data-stu-id="7180b-221">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="7180b-222">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="7180b-222">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="7180b-223">`${loginserverurl}` 插入 **网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="7180b-223">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="7180b-224">对于 **网络钓鱼 (** 附件) 活动，应删除邮件正文中的链接 (否则，邮件将同时包含链接和附件，并且不会在附件市场活动) 中跟踪链接单击。 </span><span class="sxs-lookup"><span data-stu-id="7180b-224">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7180b-225">![撰写电子邮件正文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="7180b-225">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="7180b-226">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7180b-226">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="7180b-227">在 **"确认** "步骤中， **单击"完成** "以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="7180b-227">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="7180b-228">网络钓鱼邮件将传递给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="7180b-228">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="7180b-229">密码攻击活动</span><span class="sxs-lookup"><span data-stu-id="7180b-229">Password attack campaigns</span></span>

<span data-ttu-id="7180b-230">*密码攻击* 通常会在攻击者识别一个或多个有效用户帐户后，尝试猜测组织中用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="7180b-230">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="7180b-231">在攻击模拟器中，有两种不同类型的密码攻击活动可供你测试用户密码的复杂性：</span><span class="sxs-lookup"><span data-stu-id="7180b-231">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="7180b-232">暴力密码 (字典攻击 **) ：** 暴力或字典攻击对用户帐户使用较大的字典密码文件，希望其中一个可以针对一个帐户 (多个密码) 。</span><span class="sxs-lookup"><span data-stu-id="7180b-232">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="7180b-233">错误的密码锁定有助于阻止暴力密码攻击。</span><span class="sxs-lookup"><span data-stu-id="7180b-233">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="7180b-234">对于字典攻击，你可以指定一个或多个密码来尝试 (手动输入或在上载的文件中) ，也可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="7180b-234">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="7180b-235">\**密码攻击\*\*\*：密码攻击* 对用户帐户列表使用同一个经过仔细考虑的密码， (多个帐户使用一) 。</span><span class="sxs-lookup"><span data-stu-id="7180b-235">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="7180b-236">密码感染攻击比暴力密码攻击更难检测 (当攻击者在数十个或数百个帐户上尝试一个密码时，成功的可能性会提高，而不会降低用户密码锁定错误) 。</span><span class="sxs-lookup"><span data-stu-id="7180b-236">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="7180b-237">对于密码攻击，只能指定一个要尝试的密码，也可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="7180b-237">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="7180b-238">攻击模拟器中的密码攻击将用户名和密码基本身份验证请求传递到终结点，因此它们还与其他身份验证方法 (AD FS、密码哈希同步、传递、PingFederate 等) 。</span><span class="sxs-lookup"><span data-stu-id="7180b-238">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="7180b-239">对于启用了 MFA 的用户，即使密码攻击尝试其实际密码，尝试将始终注册为失败 (换句话说，MFA 用户永远不会显示在活动成功尝试计数中) 。 </span><span class="sxs-lookup"><span data-stu-id="7180b-239">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="7180b-240">这是预期结果。</span><span class="sxs-lookup"><span data-stu-id="7180b-240">This is the expected result.</span></span> <span data-ttu-id="7180b-241">MFA 是帮助防止密码攻击的主要方法。</span><span class="sxs-lookup"><span data-stu-id="7180b-241">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="7180b-242">创建和启动密码攻击活动</span><span class="sxs-lookup"><span data-stu-id="7180b-242">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="7180b-243">在安全&中心，转到 **威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="7180b-243">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7180b-244">在 **"模拟** 攻击"页上，根据要创建的市场活动类型进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="7180b-244">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="7180b-245">在 **"暴力密码 (字典**) 部分，单击"启动攻击"或"攻击详细信息启动攻击 \> **"。**</span><span class="sxs-lookup"><span data-stu-id="7180b-245">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="7180b-246">在"**密码攻击"部分**，单击 **"启动攻击"** 或"**攻击详细信息** \> **启动攻击"。**</span><span class="sxs-lookup"><span data-stu-id="7180b-246">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="7180b-247">配置 **密码攻击** 向导将启动一个新的飞出控件。</span><span class="sxs-lookup"><span data-stu-id="7180b-247">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="7180b-248">在 **"开始**"步骤中，为显示名称输入唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="7180b-248">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="7180b-249">在 **"目标用户"** 步骤中，执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="7180b-249">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7180b-250">单击 **"通讯簿** "以选择 (活动) 或组的收件人。</span><span class="sxs-lookup"><span data-stu-id="7180b-250">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="7180b-251">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="7180b-251">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="7180b-252">如果在 **未输入搜索\*\*\*\*条件** 的情况下单击"筛选和应用"，将返回所有收件人并添加到活动。</span><span class="sxs-lookup"><span data-stu-id="7180b-252">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="7180b-253">单击 **"** 导入然后文件 **导入** "以将逗号分隔值 (CSV) 或电子邮件地址的行分隔文件中。</span><span class="sxs-lookup"><span data-stu-id="7180b-253">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="7180b-254">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7180b-254">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="7180b-255">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7180b-255">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7180b-256">在 **"选择攻击设置** "步骤中，根据市场活动类型选择要执行哪些操作：</span><span class="sxs-lookup"><span data-stu-id="7180b-256">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="7180b-257">**暴力密码 (字典)** 攻击：执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="7180b-257">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="7180b-258">**手动输入密码**：在 **按 Enter** 添加密码框中，键入密码，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="7180b-258">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="7180b-259">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="7180b-259">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="7180b-260">**从字典文件** 上载密码 **：单击"** 上载"以导入每行包含一个密码和一个空最后一行的现有文本文件。</span><span class="sxs-lookup"><span data-stu-id="7180b-260">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="7180b-261">文本文件的大小必须小于或小于 10 MB，并且不能包含超过 30000 个密码。</span><span class="sxs-lookup"><span data-stu-id="7180b-261">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="7180b-262">**密码攻击**：在 **密码 () ，输入一** 个密码。</span><span class="sxs-lookup"><span data-stu-id="7180b-262">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="7180b-263">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7180b-263">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7180b-264">在 **"确认** "步骤中， **单击"完成** "以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="7180b-264">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="7180b-265">您指定的密码将尝试用于指定的用户。</span><span class="sxs-lookup"><span data-stu-id="7180b-265">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="7180b-266">查看市场活动结果</span><span class="sxs-lookup"><span data-stu-id="7180b-266">View campaign results</span></span>

<span data-ttu-id="7180b-267">启动市场活动后，可以在主"模拟攻击"页上检查进度 **和** 结果。</span><span class="sxs-lookup"><span data-stu-id="7180b-267">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="7180b-268">活动市场活动将显示状态栏、已完成百分比值和"已完成 (用户数) 占 (用户数) "计数。</span><span class="sxs-lookup"><span data-stu-id="7180b-268">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="7180b-269">单击 **"刷新** "按钮将更新任何活动市场活动的进度。</span><span class="sxs-lookup"><span data-stu-id="7180b-269">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="7180b-270">还可以单击" **终止"** 停止活动市场活动。</span><span class="sxs-lookup"><span data-stu-id="7180b-270">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="7180b-271">活动完成后，状态将更改为 **攻击已完成**。</span><span class="sxs-lookup"><span data-stu-id="7180b-271">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="7180b-272">可以通过执行以下操作之一查看市场活动的结果：</span><span class="sxs-lookup"><span data-stu-id="7180b-272">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="7180b-273">在主 **"模拟攻击"** 页上 **，单击** 活动名称下的"查看报告"。</span><span class="sxs-lookup"><span data-stu-id="7180b-273">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="7180b-274">在主 **"模拟攻击"** 页上，单击部分中有关攻击类型的"攻击详细信息"。</span><span class="sxs-lookup"><span data-stu-id="7180b-274">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="7180b-275">在打开 **的** "攻击详细信息"页上，在"攻击历史记录"部分 **选择** 活动。</span><span class="sxs-lookup"><span data-stu-id="7180b-275">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="7180b-276">以上任一操作都会将你带至一个名为"攻击详细信息 **"的页面**。</span><span class="sxs-lookup"><span data-stu-id="7180b-276">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="7180b-277">以下各节介绍了此页上提供的每种市场活动类型的信息。</span><span class="sxs-lookup"><span data-stu-id="7180b-277">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="7180b-278">Spear Phishing (Credentials Harvest) campaign results</span><span class="sxs-lookup"><span data-stu-id="7180b-278">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="7180b-279">每个市场活动的"攻击详细信息 **"** 页上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="7180b-279">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7180b-280">市场活动 (开始日期/时间和结束日期/时间) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="7180b-280">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7180b-281">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="7180b-281">**Total users targeted**</span></span>

- <span data-ttu-id="7180b-282">**成功尝试**：单击链接并输入其凭据 (*用户名和密码* 值的用户) 。</span><span class="sxs-lookup"><span data-stu-id="7180b-282">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="7180b-283">**总体成功率**：由目标用户总数 **成功尝试**  /  **计算得出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="7180b-283">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7180b-284">**最快单击**：启动市场活动后，第一个用户单击链接需要多久。</span><span class="sxs-lookup"><span data-stu-id="7180b-284">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="7180b-285">**Average Click**： The sum of how long of everyone to click the link divided by the number of users who clicked the link.</span><span class="sxs-lookup"><span data-stu-id="7180b-285">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="7180b-286">**单击"** 成功率：由单击链接 (/目标用户总数) 计算 **得出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="7180b-286">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="7180b-287">**最快凭据**：启动市场活动后，第一个用户输入其凭据需要多久。</span><span class="sxs-lookup"><span data-stu-id="7180b-287">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="7180b-288">**平均凭据**：每个人输入其凭据所用时间的总和除以输入其凭据的用户数。</span><span class="sxs-lookup"><span data-stu-id="7180b-288">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="7180b-289">**凭据成功** 率：一个百分比， (输入其凭据的用户数/目标) 用户 **总数**。</span><span class="sxs-lookup"><span data-stu-id="7180b-289">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="7180b-290">显示每天单击的链接 **和\*\*\*\*凭据提供的号码** 的条形图。</span><span class="sxs-lookup"><span data-stu-id="7180b-290">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="7180b-291">一个圆形图 **，显示活动** 单击的链接 **、提供的凭据\*\*\*\*和** 无百分比。</span><span class="sxs-lookup"><span data-stu-id="7180b-291">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="7180b-292">" **遭到入侵的用户** "部分列出了单击链接的用户的详细信息：</span><span class="sxs-lookup"><span data-stu-id="7180b-292">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="7180b-293">用户的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="7180b-293">The user's email address</span></span>

  - <span data-ttu-id="7180b-294">他们单击链接的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="7180b-294">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="7180b-295">客户端 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7180b-295">The client IP address.</span></span>

  - <span data-ttu-id="7180b-296">有关用户版本的 Windows 和 Web 浏览器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7180b-296">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="7180b-297">可以单击 **"导出** "将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="7180b-297">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="7180b-298">网络钓鱼 (活动) 附件</span><span class="sxs-lookup"><span data-stu-id="7180b-298">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="7180b-299">每个市场活动的"攻击详细信息 **"** 页上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="7180b-299">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7180b-300">市场活动 (开始日期/时间和结束日期/时间) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="7180b-300">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7180b-301">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="7180b-301">**Total users targeted**</span></span>

- <span data-ttu-id="7180b-302">**成功尝试**：在预览版中打开或下载并打开 (用户数) 。</span><span class="sxs-lookup"><span data-stu-id="7180b-302">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="7180b-303">**总体成功率**：由目标用户总数 **成功尝试**  /  **计算得出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="7180b-303">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7180b-304">**最快附件打开时间**：启动活动后第一个用户打开附件所花时间。</span><span class="sxs-lookup"><span data-stu-id="7180b-304">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="7180b-305">**平均附件打开** 时间：每个人打开附件所花时间的总和除以打开附件的用户数。</span><span class="sxs-lookup"><span data-stu-id="7180b-305">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="7180b-306">**附件打开成功率**：由打开附件 (用户数/目标) 用户总数计算 **得出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="7180b-306">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="7180b-307">暴力密码 (字典攻击) 结果</span><span class="sxs-lookup"><span data-stu-id="7180b-307">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="7180b-308">每个市场活动的"攻击详细信息 **"** 页上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="7180b-308">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7180b-309">市场活动 (开始日期/时间和结束日期/时间) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="7180b-309">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7180b-310">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="7180b-310">**Total users targeted**</span></span>

- <span data-ttu-id="7180b-311">**成功尝试**：发现正在使用指定密码之一的用户数。</span><span class="sxs-lookup"><span data-stu-id="7180b-311">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="7180b-312">**总体成功率**：由目标用户总数 **成功尝试**  /  **计算得出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="7180b-312">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7180b-313">" **受到威胁的用户"** 部分列出了受影响用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7180b-313">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="7180b-314">可以单击 **"导出** "将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="7180b-314">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="7180b-315">密码攻击活动结果</span><span class="sxs-lookup"><span data-stu-id="7180b-315">Password spray attack campaign results</span></span>

<span data-ttu-id="7180b-316">每个市场活动的"攻击详细信息 **"** 页上提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="7180b-316">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7180b-317">市场活动 (开始日期/时间和结束日期/时间) 持续时间。</span><span class="sxs-lookup"><span data-stu-id="7180b-317">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7180b-318">**目标用户总数**</span><span class="sxs-lookup"><span data-stu-id="7180b-318">**Total users targeted**</span></span>

- <span data-ttu-id="7180b-319">**成功尝试**：找到使用指定密码的用户数。</span><span class="sxs-lookup"><span data-stu-id="7180b-319">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="7180b-320">**总体成功率**：由目标用户总数 **成功尝试**  /  **计算得出的百分比**。</span><span class="sxs-lookup"><span data-stu-id="7180b-320">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
