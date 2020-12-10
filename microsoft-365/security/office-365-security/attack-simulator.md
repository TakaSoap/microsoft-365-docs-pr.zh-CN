---
title: Microsoft Defender for Office 365 中的攻击模拟器
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
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用攻击模拟器在其 Microsoft 365 E5 或 Microsoft Defender for Office 365 Plan 2 组织中运行模拟的网络钓鱼和密码攻击。
ms.openlocfilehash: b1c2ad265c4812f67aee66f0f59664480b4db229
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615200"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b427b-103">Microsoft Defender for Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="b427b-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b427b-104">如果您的组织具有 Microsoft Defender for Office 365 计划2，其中包括 [威胁调查和响应功能](office-365-ti.md)，则您可以使用安全 & 合规性中心中的攻击模拟器在您的组织中运行实际的攻击方案。</span><span class="sxs-lookup"><span data-stu-id="b427b-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="b427b-105">这些模拟攻击可帮助您识别易受攻击的用户，并在真正的攻击影响你的底线之前找到这些用户。</span><span class="sxs-lookup"><span data-stu-id="b427b-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="b427b-106">阅读本文以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b427b-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="b427b-107">与 Microsoft 365 服务的其他客户数据一起存储的攻击模拟和培训相关数据。</span><span class="sxs-lookup"><span data-stu-id="b427b-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="b427b-108">有关详细信息，请参阅 [Microsoft 365 数据位置](/microsoft-365/enterprise/o365-data-locations)。</span><span class="sxs-lookup"><span data-stu-id="b427b-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="b427b-109">Microsoft 365 安全中心中的公共预览版提供了攻击模拟培训。</span><span class="sxs-lookup"><span data-stu-id="b427b-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="b427b-110">请查看 [使用 Microsoft Defender For Office 365 模拟网络钓鱼攻击](attack-simulation-training.md) ，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b427b-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b427b-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b427b-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b427b-112">若要打开安全与合规中心，请转到 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="b427b-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="b427b-113">攻击模拟器在 **威胁管理** \> **攻击模拟器** 中可用。</span><span class="sxs-lookup"><span data-stu-id="b427b-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="b427b-114">请直接转到 "攻击模拟器"，打开 <https://protection.office.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="b427b-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="b427b-115">有关跨不同 Microsoft 365 订阅的攻击模拟器的可用性的详细信息，请参阅 [Microsoft Defender For Office 365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="b427b-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="b427b-116">您必须是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="b427b-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="b427b-117">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b427b-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b427b-118">需要为你的帐户配置 (MFA) 的多重身份验证，以在攻击模拟器中创建和管理市场活动。</span><span class="sxs-lookup"><span data-stu-id="b427b-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="b427b-119">有关说明，请参阅 [设置多因素身份验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="b427b-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="b427b-120">网络钓鱼活动将收集和处理30天的事件。</span><span class="sxs-lookup"><span data-stu-id="b427b-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="b427b-121">在你启动市场活动后，历史宣传活动数据将在最长90天内可用。</span><span class="sxs-lookup"><span data-stu-id="b427b-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="b427b-122">没有对应的 PowerShell cmdlet 用于攻击模拟器。</span><span class="sxs-lookup"><span data-stu-id="b427b-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="b427b-123">Spear 仿冒活动</span><span class="sxs-lookup"><span data-stu-id="b427b-123">Spear phishing campaigns</span></span>

<span data-ttu-id="b427b-124">*仿冒* 是电子邮件攻击的一般性术语，试图窃取看似合法或受信任发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="b427b-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="b427b-125">*Spear 仿冒* 是一种目标仿冒攻击，它使用专门为目标收件人量身定制的重点和自定义内容 (通常是由攻击者) 的收件人的侦测之后。</span><span class="sxs-lookup"><span data-stu-id="b427b-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="b427b-126">在攻击模拟器中，可以使用两种不同类型的 spear 网络钓鱼活动：</span><span class="sxs-lookup"><span data-stu-id="b427b-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="b427b-127">**Spear 网络钓鱼 (凭据搜集)**：攻击试图说服收件人单击邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="b427b-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="b427b-128">如果他们单击该链接，系统将要求他们输入凭据。</span><span class="sxs-lookup"><span data-stu-id="b427b-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="b427b-129">如果是这样，则会将它们转到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="b427b-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="b427b-130">一个说明这只是一个测试的默认页面，并提供了有关识别网络钓鱼邮件的提示。</span><span class="sxs-lookup"><span data-stu-id="b427b-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![用户在单击 "仿冒" 链接并输入其凭据时看到的内容](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="b427b-132">您指定的自定义页面 (URL) 。</span><span class="sxs-lookup"><span data-stu-id="b427b-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="b427b-133">**Spear 网络钓鱼 (附件)**：攻击试图说服收件人打开邮件中的 .docx 或 .pdf 附件。</span><span class="sxs-lookup"><span data-stu-id="b427b-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="b427b-134">附件包含来自默认仿冒链接的相同内容，但第一句以 "" \<Display Name\> ，您将看到此邮件是您打开的最近的电子邮件 ... "。</span><span class="sxs-lookup"><span data-stu-id="b427b-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="b427b-135">目前，攻击模拟器中的 spear 网络钓鱼活动不会过期。</span><span class="sxs-lookup"><span data-stu-id="b427b-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="b427b-136">创建 spear 网络钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="b427b-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="b427b-137">任何 spear 仿冒活动的一个重要部分是发送给目标收件人的电子邮件的外观和感觉。</span><span class="sxs-lookup"><span data-stu-id="b427b-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="b427b-138">若要创建和配置电子邮件，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="b427b-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="b427b-139">**使用内置电子邮件模板**：提供了两个内置模板： **奖品 Giveaway** 和 **工资更新**。</span><span class="sxs-lookup"><span data-stu-id="b427b-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="b427b-140">创建和启动市场活动时，可以进一步自定义模板中的部分、全部或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="b427b-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="b427b-141">**创建可重用的电子邮件模板**：创建并保存电子邮件模板之后，可以在将来的 spear 仿冒活动中再次使用它。</span><span class="sxs-lookup"><span data-stu-id="b427b-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="b427b-142">创建和启动市场活动时，可以进一步自定义模板中的部分、全部或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="b427b-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="b427b-143">**在向导中创建电子** 邮件：创建和启动 spear 仿冒活动时，可以在向导中直接创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b427b-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="b427b-144">步骤 1 (可选) ：创建自定义电子邮件模板</span><span class="sxs-lookup"><span data-stu-id="b427b-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="b427b-145">如果要使用内置模板之一或直接在向导中创建电子邮件，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="b427b-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="b427b-146">在安全 & 合规性中心中，转到 " **威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b427b-147">在 " **模拟攻击** " 页上的 " **Spear 仿冒 (凭据搜集)** 或 **Spear 仿冒 (附件)** 部分中，单击" **攻击详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="b427b-148">在何处创建模板无关紧要。</span><span class="sxs-lookup"><span data-stu-id="b427b-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="b427b-149">对于这两种类型的网络钓鱼攻击，模板中的可用选项都是相同的。</span><span class="sxs-lookup"><span data-stu-id="b427b-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="b427b-150">在打开的 " **攻击详细信息** " 页上的 " **仿冒模板** " 部分的 " **创建模板** " 区域中，单击 " **新建模板**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="b427b-151">" **配置仿冒模板** 向导" 将在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="b427b-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="b427b-152">在 " **开始** " 步骤中，为模板输入一个唯一的显示名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="b427b-153">在 " **配置电子邮件详细信息** " 步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b427b-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="b427b-154">**从 (名称)**：用于邮件发件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b427b-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="b427b-155">**从 (电子邮件)**：发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b427b-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="b427b-156">**网络钓鱼登录服务器 URL**：单击下拉列表，并从列表中选择一个可用的 url。</span><span class="sxs-lookup"><span data-stu-id="b427b-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="b427b-157">这是用户将被引诱单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="b427b-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="b427b-158">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="b427b-158">The choices are:</span></span>

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
     > - <span data-ttu-id="b427b-159">所有 Url 都是有意的 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="b427b-159">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="b427b-160">URL 信誉服务可能会将这些 Url 中的一个或多个标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="b427b-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="b427b-161">在网络仿冒活动中使用 URL 之前，请先检查受支持的 web 浏览器中的 URL 是否可用。</span><span class="sxs-lookup"><span data-stu-id="b427b-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="b427b-162">**自定义登陆页面 URL**：输入用户在单击 "仿冒" 链接并输入其凭据时使用的可选登录页。</span><span class="sxs-lookup"><span data-stu-id="b427b-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="b427b-163">此链接将替换默认登录页。</span><span class="sxs-lookup"><span data-stu-id="b427b-163">This link replaces the default landing page.</span></span> <span data-ttu-id="b427b-164">例如，如果您有内部意识培训，则可以在此指定 URL。</span><span class="sxs-lookup"><span data-stu-id="b427b-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="b427b-165">**类别**：当前) 忽略输入的任何内容，则不使用此设置 (。</span><span class="sxs-lookup"><span data-stu-id="b427b-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="b427b-166">**主题**：电子邮件的 " **主题** " 字段。</span><span class="sxs-lookup"><span data-stu-id="b427b-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="b427b-167">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b427b-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b427b-168">在 " **撰写电子邮件** " 步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="b427b-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="b427b-169">您可以使用 " **电子邮件** " 选项卡 (丰富的 html 编辑器) 或 (原始 HTML 代码) 的 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b427b-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="b427b-170">HTML 格式可以简单，也可以复杂，因为您需要它。</span><span class="sxs-lookup"><span data-stu-id="b427b-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="b427b-171">您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的 believability。</span><span class="sxs-lookup"><span data-stu-id="b427b-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="b427b-172">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="b427b-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="b427b-173">`${loginserverurl}` 插入上一步中的 **网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="b427b-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="b427b-174">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b427b-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b427b-175">在 " **确认** " 步骤中，单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="b427b-176">步骤2：创建和启动 spear 仿冒活动</span><span class="sxs-lookup"><span data-stu-id="b427b-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="b427b-177">在安全 & 合规性中心中，转到 " **威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b427b-178">在 " **模拟攻击** " 页面上，根据您要创建的市场活动类型，进行下列选择之一：</span><span class="sxs-lookup"><span data-stu-id="b427b-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="b427b-179">在 " **Spear 仿冒 (凭据收集)** " 部分，单击 " **启动攻击** " 或 " **攻击详细信息** \> **启动攻击**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="b427b-180">在 " **Spear 仿冒 (附件)** " 部分，单击 " **启动攻击** " 或 " **攻击详细信息** \> **启动攻击**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="b427b-181">" **配置网络钓鱼攻击** 向导" 将在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="b427b-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="b427b-182">在 " **开始** " 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="b427b-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b427b-183">在 " **名称** " 框中，为市场活动输入唯一的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b427b-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="b427b-184">不要单击 " **使用模板**"，因为稍后将在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b427b-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="b427b-185">单击 " **使用模板** "，然后选择一个内置或自定义电子邮件模板。</span><span class="sxs-lookup"><span data-stu-id="b427b-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="b427b-186">选择模板后，将根据模板自动填充 " **名称** " 框，但您可以更改名称。</span><span class="sxs-lookup"><span data-stu-id="b427b-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![网络钓鱼起始页](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="b427b-188">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b427b-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b427b-189">在 " **目标收件人** " 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="b427b-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b427b-190">单击 " **通讯簿** " 以选择市场活动 (用户或组) 的收件人。</span><span class="sxs-lookup"><span data-stu-id="b427b-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="b427b-191">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="b427b-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="b427b-192">如果在未输入搜索条件的情况下单击 " **筛选** 和 **应用** "，则将返回所有收件人并将其添加到市场活动中。</span><span class="sxs-lookup"><span data-stu-id="b427b-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="b427b-193">单击 " **导** 入"，然后单击 " **文件导** 入" 以将逗号分隔的值导入 (CSV) 或电子邮件地址的行分隔文件。</span><span class="sxs-lookup"><span data-stu-id="b427b-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="b427b-194">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b427b-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="b427b-195">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b427b-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b427b-196">在 " **配置电子邮件详细信息** " 步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b427b-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="b427b-197">如果您在 " **开始** " 步骤中选择了一个模板，则这些值中的大多数已配置，但您可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="b427b-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="b427b-198">**从 (名称)**：用于邮件发件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b427b-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="b427b-199">**从 (电子邮件)**：发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b427b-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="b427b-200">您可以输入组织的电子邮件域中的真实或虚假电子邮件地址，也可以输入真实或虚假的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b427b-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="b427b-201">组织中的有效发件人电子邮件地址将在收件人的电子邮件客户端中实际解析。</span><span class="sxs-lookup"><span data-stu-id="b427b-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="b427b-202">**网络钓鱼登录服务器 URL**：单击下拉列表，并从列表中选择一个可用的 url。</span><span class="sxs-lookup"><span data-stu-id="b427b-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="b427b-203">这是用户将被引诱单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="b427b-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="b427b-204">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="b427b-204">The choices are:</span></span>

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
     > - <span data-ttu-id="b427b-205">所有 Url 都是有意的 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="b427b-205">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="b427b-206">URL 信誉服务可能会将这些 Url 中的一个或多个标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="b427b-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="b427b-207">在网络仿冒活动中使用 URL 之前，请先检查受支持的 web 浏览器中的 URL 是否可用。</span><span class="sxs-lookup"><span data-stu-id="b427b-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="b427b-208">您需要选择一个 URL。</span><span class="sxs-lookup"><span data-stu-id="b427b-208">You are required to select a URL.</span></span> <span data-ttu-id="b427b-209">对于 **Spear 网络钓鱼 (附件)** 市场活动，您可以在下一步中删除邮件正文中的链接 (否则，邮件将同时包含链接 **和** 附件) 。</span><span class="sxs-lookup"><span data-stu-id="b427b-209">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="b427b-210">**附件类型**：此设置仅在 **Spear 仿冒 (附件)** 市场活动中可用。</span><span class="sxs-lookup"><span data-stu-id="b427b-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="b427b-211">单击下拉箭头，然后选择 "" **。.DOCX** 或 **。PDF** 中的列表。</span><span class="sxs-lookup"><span data-stu-id="b427b-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="b427b-212">**附件名称**：此设置仅在 **Spear 仿冒 (附件)** 市场活动中可用。</span><span class="sxs-lookup"><span data-stu-id="b427b-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="b427b-213">输入 .docx 或 .pdf 附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="b427b-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="b427b-214">**自定义登陆页面 URL**：输入用户在单击 "仿冒" 链接并输入其凭据时使用的可选登录页。</span><span class="sxs-lookup"><span data-stu-id="b427b-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="b427b-215">此链接将替换默认登录页。</span><span class="sxs-lookup"><span data-stu-id="b427b-215">This link replaces the default landing page.</span></span> <span data-ttu-id="b427b-216">例如，如果您有内部意识培训，则可以在此指定 URL。</span><span class="sxs-lookup"><span data-stu-id="b427b-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="b427b-217">**主题**：电子邮件的 " **主题** " 字段。</span><span class="sxs-lookup"><span data-stu-id="b427b-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="b427b-218">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b427b-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b427b-219">在 " **撰写电子邮件** " 步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="b427b-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="b427b-220">如果在 " **开始** " 步骤中选择了一个模板，则表示已配置邮件正文，但您可以对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="b427b-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="b427b-221">您可以使用 " **电子邮件** " 选项卡 (丰富的 html 编辑器) 或 (原始 HTML 代码) 的 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b427b-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="b427b-222">HTML 格式可以简单，也可以复杂，因为您需要它。</span><span class="sxs-lookup"><span data-stu-id="b427b-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="b427b-223">您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的 believability。</span><span class="sxs-lookup"><span data-stu-id="b427b-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="b427b-224">`${username}` 插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="b427b-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="b427b-225">`${loginserverurl}` 插入 **网络钓鱼登录服务器 URL** 值。</span><span class="sxs-lookup"><span data-stu-id="b427b-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="b427b-226">对于 **Spear 网络钓鱼 (附件)** 市场活动，应删除邮件正文中的链接 (否则，邮件将同时包含链接 **和** 附件，并且不会在附件活动) 中跟踪链接单击。</span><span class="sxs-lookup"><span data-stu-id="b427b-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![撰写电子邮件正文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="b427b-228">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b427b-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b427b-229">在 " **确认** " 步骤中，单击 " **完成** " 以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="b427b-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="b427b-230">将仿冒邮件传递给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="b427b-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="b427b-231">密码攻击市场活动</span><span class="sxs-lookup"><span data-stu-id="b427b-231">Password attack campaigns</span></span>

<span data-ttu-id="b427b-232">*密码攻击* 尝试猜测组织中的用户帐户的密码，通常是在攻击者标识了一个或多个有效的用户帐户之后。</span><span class="sxs-lookup"><span data-stu-id="b427b-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="b427b-233">在攻击模拟器中，可以使用两种不同类型的密码攻击活动来测试用户密码的复杂性：</span><span class="sxs-lookup"><span data-stu-id="b427b-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="b427b-234">**强力密码 (字典攻击)**： *强力* 攻击或 *字典* 攻击对用户帐户使用大量的密码字典文件，希望其中的一个用户 (可以在一个帐户) 中使用多个密码。</span><span class="sxs-lookup"><span data-stu-id="b427b-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="b427b-235">不正确的密码锁定帮助阻止强力密码攻击。</span><span class="sxs-lookup"><span data-stu-id="b427b-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="b427b-236">对于字典攻击，您可以指定一个或多个密码来尝试 (手动输入或上载的文件) ，并且您可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="b427b-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="b427b-237">**密码喷涂攻击**： *密码喷涂* 攻击对用户帐户列表使用相同的密码仔细考虑， (对许多帐户) 的一个密码。</span><span class="sxs-lookup"><span data-stu-id="b427b-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="b427b-238">密码喷涂攻击比强力密码攻击更难检测 (如果攻击者在几十个或数百个帐户之间尝试一个密码，而不会导致用户不正确的密码锁定) 的风险，则会导致成功的概率。</span><span class="sxs-lookup"><span data-stu-id="b427b-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="b427b-239">对于密码喷涂攻击，只能指定一个密码进行尝试，并且您可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="b427b-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="b427b-240">攻击模拟器中的密码攻击会将用户名和密码的基本身份验证请求传递给终结点，因此它们还可以使用 (AD FS、密码哈希同步、传递 PingFederate 等其他身份验证方法 ) 。</span><span class="sxs-lookup"><span data-stu-id="b427b-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="b427b-241">对于已启用 MFA 的用户（即使密码攻击尝试其实际密码），尝试将始终注册为故障 (换句话说，MFA 用户永远不会出现在市场活动) 的 **成功尝试** 计数中。</span><span class="sxs-lookup"><span data-stu-id="b427b-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="b427b-242">这是预期的结果。</span><span class="sxs-lookup"><span data-stu-id="b427b-242">This is the expected result.</span></span> <span data-ttu-id="b427b-243">MFA 是一种帮助防止密码攻击的主要方法。</span><span class="sxs-lookup"><span data-stu-id="b427b-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="b427b-244">创建和启动密码攻击市场活动</span><span class="sxs-lookup"><span data-stu-id="b427b-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="b427b-245">在安全 & 合规性中心中，转到 " **威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b427b-246">在 " **模拟攻击** " 页面上，根据您要创建的市场活动类型，进行下列选择之一：</span><span class="sxs-lookup"><span data-stu-id="b427b-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="b427b-247">在 **强力密码 (字典攻击)** 部分，单击 " **启动攻击** " 或 " **攻击详细信息** \> **启动攻击**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="b427b-248">在 " **密码喷涂攻击** " 部分，单击 " **启动攻击** " 或单击 " **攻击详细信息** \> **启动攻击**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="b427b-249">" **配置密码攻击** 向导" 将在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="b427b-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="b427b-250">在 " **开始** " 步骤中，为市场活动输入一个唯一的显示名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="b427b-251">在 " **目标用户** " 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="b427b-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b427b-252">单击 " **通讯簿** " 以选择市场活动 (用户或组) 的收件人。</span><span class="sxs-lookup"><span data-stu-id="b427b-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="b427b-253">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="b427b-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="b427b-254">如果在未输入搜索条件的情况下单击 " **筛选** 和 **应用** "，则将返回所有收件人并将其添加到市场活动中。</span><span class="sxs-lookup"><span data-stu-id="b427b-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="b427b-255">单击 " **导** 入"，然后单击 " **文件导** 入" 以将逗号分隔的值导入 (CSV) 或电子邮件地址的行分隔文件。</span><span class="sxs-lookup"><span data-stu-id="b427b-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="b427b-256">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b427b-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="b427b-257">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b427b-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b427b-258">在 " **选择攻击设置** " 步骤中，选择要基于市场活动类型执行的操作：</span><span class="sxs-lookup"><span data-stu-id="b427b-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="b427b-259">**强力密码 (字典攻击)**：执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="b427b-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="b427b-260">**手动输入密码**：在 **按 enter 以添加密码** 框中，键入一个密码，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="b427b-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="b427b-261">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="b427b-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="b427b-262">**上载字典文件中的密码**：单击 " **上传** " 以导入每行包含一个密码的现有文本文件和一个空白的最后一行。</span><span class="sxs-lookup"><span data-stu-id="b427b-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="b427b-263">文本文件的大小必须为 10 MB 或更小，并且不能包含超过30000个密码。</span><span class="sxs-lookup"><span data-stu-id="b427b-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="b427b-264">**密码喷涂攻击**：在 " **攻击 (s) " 的密码中使用。在 "攻击** " 框中，输入一个密码。</span><span class="sxs-lookup"><span data-stu-id="b427b-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="b427b-265">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b427b-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b427b-266">在 " **确认** " 步骤中，单击 " **完成** " 以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="b427b-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="b427b-267">您指定的密码将尝试您指定的用户。</span><span class="sxs-lookup"><span data-stu-id="b427b-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="b427b-268">查看市场活动结果</span><span class="sxs-lookup"><span data-stu-id="b427b-268">View campaign results</span></span>

<span data-ttu-id="b427b-269">启动市场活动后，可以在 "主 **模拟攻击** " 页上查看进度和结果。</span><span class="sxs-lookup"><span data-stu-id="b427b-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="b427b-270">活动的市场活动将显示状态栏、已完成的百分比值和 " (已完成用户的用户)  (总用户数) " 计数。</span><span class="sxs-lookup"><span data-stu-id="b427b-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="b427b-271">单击 " **刷新** " 按钮将更新任何活动活动的进度。</span><span class="sxs-lookup"><span data-stu-id="b427b-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="b427b-272">您还可以单击 " **终止** " 以停止活动的市场活动。</span><span class="sxs-lookup"><span data-stu-id="b427b-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="b427b-273">在市场活动完成后，状态将更改为 " **已完成攻击**"。</span><span class="sxs-lookup"><span data-stu-id="b427b-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="b427b-274">您可以通过执行以下任一操作来查看市场活动的结果：</span><span class="sxs-lookup"><span data-stu-id="b427b-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="b427b-275">在 "主 **模拟攻击** " 页面上，单击市场活动名称下的 " **查看报告** "。</span><span class="sxs-lookup"><span data-stu-id="b427b-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="b427b-276">在 "主 **模拟攻击** " 页面上，单击攻击类型部分中的 " **攻击详细信息** "。</span><span class="sxs-lookup"><span data-stu-id="b427b-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="b427b-277">在打开的 " **攻击详细信息** " 页上，选择 " **攻击历史记录** " 部分中的 "活动"。</span><span class="sxs-lookup"><span data-stu-id="b427b-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="b427b-278">上述任一操作都将转到名为 " **攻击详细信息**" 的页面。</span><span class="sxs-lookup"><span data-stu-id="b427b-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="b427b-279">以下各节介绍了在此页面上为每种类型的市场活动提供的信息。</span><span class="sxs-lookup"><span data-stu-id="b427b-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="b427b-280">Spear 仿冒 (凭据收集) 市场活动结果</span><span class="sxs-lookup"><span data-stu-id="b427b-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="b427b-281">以下信息在每个市场活动的 " **攻击详细信息** " 页上提供：</span><span class="sxs-lookup"><span data-stu-id="b427b-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b427b-282">市场活动的持续时间 (开始日期/时间和结束日期/时间) 。</span><span class="sxs-lookup"><span data-stu-id="b427b-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b427b-283">**目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="b427b-283">**Total users targeted**</span></span>

- <span data-ttu-id="b427b-284">**成功的尝试**：单击链接 **并** 输入凭据的用户数 () 的 *任何* 用户名和密码值。</span><span class="sxs-lookup"><span data-stu-id="b427b-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="b427b-285">**总体成功率**：由 **成功尝试** 的  /  **用户的目标总数** 计算所得的百分比。</span><span class="sxs-lookup"><span data-stu-id="b427b-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b427b-286">**最快的点击** 次数：启动市场活动后，第一个用户单击链接所需的时间。</span><span class="sxs-lookup"><span data-stu-id="b427b-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="b427b-287">**平均单击** 次数：每个人单击链接所花的时间除以单击链接的用户数。</span><span class="sxs-lookup"><span data-stu-id="b427b-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="b427b-288">**单击 "成功率**：由单击链接的用户数) / **目标用户** 数 (计算的百分比。</span><span class="sxs-lookup"><span data-stu-id="b427b-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="b427b-289">**最快的凭据**：在启动市场活动后，第一个用户输入其凭据所需的时间。</span><span class="sxs-lookup"><span data-stu-id="b427b-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="b427b-290">**平均凭据**：每个人输入其凭据所花的时间除以输入其凭据的用户数量的总和。</span><span class="sxs-lookup"><span data-stu-id="b427b-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="b427b-291">**凭据成功率**：由 (个用户输入其凭据的用户数) / **目标用户** 数计算得出的百分比。</span><span class="sxs-lookup"><span data-stu-id="b427b-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="b427b-292">显示 **链接已单击** 的条形图，以及 **凭据** 每日提供的数字。</span><span class="sxs-lookup"><span data-stu-id="b427b-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="b427b-293">显示 **链接已单击**、 **提供凭据** 和 **无** 市场活动百分比的圆形图。</span><span class="sxs-lookup"><span data-stu-id="b427b-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="b427b-294">"已 **损坏的用户** " 部分列出了单击该链接的用户的详细信息：</span><span class="sxs-lookup"><span data-stu-id="b427b-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="b427b-295">用户的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="b427b-295">The user's email address</span></span>

  - <span data-ttu-id="b427b-296">单击链接时的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="b427b-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="b427b-297">客户端 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b427b-297">The client IP address.</span></span>

  - <span data-ttu-id="b427b-298">有关用户的 Windows 和 web 浏览器的版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b427b-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="b427b-299">您可以单击 " **导出** " 将结果导出到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="b427b-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="b427b-300">Spear 仿冒 (附件) 市场活动结果</span><span class="sxs-lookup"><span data-stu-id="b427b-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="b427b-301">以下信息在每个市场活动的 " **攻击详细信息** " 页上提供：</span><span class="sxs-lookup"><span data-stu-id="b427b-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b427b-302">市场活动的持续时间 (开始日期/时间和结束日期/时间) 。</span><span class="sxs-lookup"><span data-stu-id="b427b-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b427b-303">**目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="b427b-303">**Total users targeted**</span></span>

- <span data-ttu-id="b427b-304">**成功的尝试**：打开或下载并打开附件的用户数 (预览不会计算) 。</span><span class="sxs-lookup"><span data-stu-id="b427b-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="b427b-305">**总体成功率**：由 **成功尝试** 的  /  **用户的目标总数** 计算所得的百分比。</span><span class="sxs-lookup"><span data-stu-id="b427b-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b427b-306">**最快的附件打开时间**：启动市场活动后，首个用户打开附件所需的时间。</span><span class="sxs-lookup"><span data-stu-id="b427b-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="b427b-307">**平均附件打开时间**：每个人打开附件所花的时间除以打开附件的用户数。</span><span class="sxs-lookup"><span data-stu-id="b427b-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="b427b-308">**附件打开成功率**：由 (打开附件的用户数) / **目标的用户** 数计算的百分比。</span><span class="sxs-lookup"><span data-stu-id="b427b-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="b427b-309">强力密码 (字典攻击) 市场活动结果</span><span class="sxs-lookup"><span data-stu-id="b427b-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="b427b-310">以下信息在每个市场活动的 " **攻击详细信息** " 页上提供：</span><span class="sxs-lookup"><span data-stu-id="b427b-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b427b-311">市场活动的持续时间 (开始日期/时间和结束日期/时间) 。</span><span class="sxs-lookup"><span data-stu-id="b427b-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b427b-312">**目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="b427b-312">**Total users targeted**</span></span>

- <span data-ttu-id="b427b-313">**成功的尝试**：找到的使用指定密码之一的用户数。</span><span class="sxs-lookup"><span data-stu-id="b427b-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="b427b-314">**总体成功率**：由 **成功尝试** 的  /  **用户的目标总数** 计算所得的百分比。</span><span class="sxs-lookup"><span data-stu-id="b427b-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b427b-315">"已 **损坏的用户** " 部分列出了受影响的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b427b-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="b427b-316">您可以单击 " **导出** " 将结果导出到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="b427b-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="b427b-317">密码喷涂攻击活动结果</span><span class="sxs-lookup"><span data-stu-id="b427b-317">Password spray attack campaign results</span></span>

<span data-ttu-id="b427b-318">以下信息在每个市场活动的 " **攻击详细信息** " 页上提供：</span><span class="sxs-lookup"><span data-stu-id="b427b-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b427b-319">市场活动的持续时间 (开始日期/时间和结束日期/时间) 。</span><span class="sxs-lookup"><span data-stu-id="b427b-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b427b-320">**目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="b427b-320">**Total users targeted**</span></span>

- <span data-ttu-id="b427b-321">**成功的尝试**：找到的使用指定密码的用户数量。</span><span class="sxs-lookup"><span data-stu-id="b427b-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="b427b-322">**总体成功率**：由 **成功尝试** 的  /  **用户的目标总数** 计算所得的百分比。</span><span class="sxs-lookup"><span data-stu-id="b427b-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
