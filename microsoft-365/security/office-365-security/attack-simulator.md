---
title: ATP 中的攻击模拟器
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
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
description: 了解如何使用攻击模拟器在 Microsoft 365 E5 或 ATP Plan 2 组织中运行模拟的网络钓鱼和密码攻击。
ms.openlocfilehash: 166a8ab9f6ef08ca089bc8924b686e392e870526
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587564"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="0b923-103">ATP 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="0b923-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="0b923-104">**摘要**如果您是全局管理员或安全管理员，并且您的组织具有 Office 365 高级威胁防护计划2（其中包括[威胁调查和响应功能](office-365-ti.md)），则可以使用攻击模拟器在组织中运行实际的攻击方案。</span><span class="sxs-lookup"><span data-stu-id="0b923-104">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="0b923-105">这可以帮助你在实际攻击影响你的底线之前识别并找出易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="0b923-105">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="0b923-106">阅读本文以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b923-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b923-107">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="0b923-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b923-108">若要打开安全与合规中心，请转到 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="0b923-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="0b923-109">攻击模拟器在**威胁管理** \> **攻击模拟器**中可用。</span><span class="sxs-lookup"><span data-stu-id="0b923-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![威胁管理-攻击模拟器](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="0b923-111">有关跨不同 Microsoft 365 订阅的攻击模拟器的可用性的详细信息，请参阅[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="0b923-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="0b923-112">您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="0b923-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="0b923-113">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0b923-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0b923-114">您的帐户需要配置用于多重身份验证（MFA），以在攻击模拟器中创建和管理市场活动。</span><span class="sxs-lookup"><span data-stu-id="0b923-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="0b923-115">有关说明，请参阅[设置多因素身份验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="0b923-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="0b923-116">为成功启动攻击，请确保用于运行模拟攻击的帐户使用多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="0b923-116">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="0b923-117">此外，您必须是全局管理员或安全管理员。</span><span class="sxs-lookup"><span data-stu-id="0b923-117">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="0b923-118">（若要了解有关角色和权限的详细信息，请参阅[安全性 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。）</span><span class="sxs-lookup"><span data-stu-id="0b923-118">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="0b923-119">网络钓鱼活动将收集和处理30天的事件。</span><span class="sxs-lookup"><span data-stu-id="0b923-119">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="0b923-120">在你启动市场活动后，历史宣传活动数据将在最长90天内可用。</span><span class="sxs-lookup"><span data-stu-id="0b923-120">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="0b923-121">没有对应的 PowerShell cmdlet 用于攻击模拟器。</span><span class="sxs-lookup"><span data-stu-id="0b923-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="0b923-122">Spear 仿冒活动</span><span class="sxs-lookup"><span data-stu-id="0b923-122">Spear phishing campaigns</span></span>

<span data-ttu-id="0b923-123">*仿冒*是电子邮件攻击的一般性术语，试图窃取看似合法或受信任发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="0b923-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="0b923-124">*Spear 仿冒*是一种目标网络钓鱼攻击，它使用专门为目标收件人（通常是攻击者在收件人上的侦测之后）量身定制的重点和自定义内容。</span><span class="sxs-lookup"><span data-stu-id="0b923-124">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="0b923-125">您是全局管理员或安全管理员</span><span class="sxs-lookup"><span data-stu-id="0b923-125">You are a global administrator or security administrator</span></span>

<span data-ttu-id="0b923-126">在攻击模拟器中，可以使用两种不同类型的 spear 网络钓鱼活动：</span><span class="sxs-lookup"><span data-stu-id="0b923-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="0b923-127">[多因素身份验证/条件访问](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)已打开，至少为全局管理员帐户和将使用攻击模拟器的安全管理员。</span><span class="sxs-lookup"><span data-stu-id="0b923-127">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="0b923-128">（理想情况下，为组织中的所有用户启用多重身份验证/条件访问。）</span><span class="sxs-lookup"><span data-stu-id="0b923-128">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="0b923-129">一个说明这只是一个测试的默认页面，并提供了有关识别网络钓鱼邮件的提示。</span><span class="sxs-lookup"><span data-stu-id="0b923-129">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![用户在单击 "仿冒" 链接并输入其凭据时看到的内容](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="0b923-131">您指定的自定义页面（URL）。</span><span class="sxs-lookup"><span data-stu-id="0b923-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="0b923-132">**Spear 网络钓鱼（附件）**：攻击试图说服收件人在邮件中打开 .docx 或 .pdf 附件。</span><span class="sxs-lookup"><span data-stu-id="0b923-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="0b923-133">附件包含来自默认仿冒链接的相同内容，但第一句以 "" \<Display Name\> ，您将看到此邮件是您打开的最近的电子邮件 ... "。</span><span class="sxs-lookup"><span data-stu-id="0b923-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="0b923-134">目前，攻击模拟器中的 spear 网络钓鱼活动不会过期。</span><span class="sxs-lookup"><span data-stu-id="0b923-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="0b923-135">创建 spear 网络钓鱼活动</span><span class="sxs-lookup"><span data-stu-id="0b923-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="0b923-136">任何 spear 仿冒活动的一个重要部分是发送给目标收件人的电子邮件的外观和感觉。</span><span class="sxs-lookup"><span data-stu-id="0b923-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="0b923-137">若要创建和配置电子邮件，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="0b923-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="0b923-138">**使用内置电子邮件模板**：提供了两个内置模板：**奖品 Giveaway**和**工资更新**。</span><span class="sxs-lookup"><span data-stu-id="0b923-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="0b923-139">创建和启动市场活动时，可以进一步自定义模板中的部分、全部或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="0b923-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="0b923-140">**创建可重用的电子邮件模板**：创建并保存电子邮件模板之后，可以在将来的 spear 仿冒活动中再次使用它。</span><span class="sxs-lookup"><span data-stu-id="0b923-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="0b923-141">创建和启动市场活动时，可以进一步自定义模板中的部分、全部或无电子邮件属性。</span><span class="sxs-lookup"><span data-stu-id="0b923-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="0b923-142">**在向导中创建电子**邮件：创建和启动 spear 仿冒活动时，可以在向导中直接创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0b923-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="0b923-143">步骤1（可选）：创建自定义电子邮件模板</span><span class="sxs-lookup"><span data-stu-id="0b923-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="0b923-144">如果要使用内置模板之一或直接在向导中创建电子邮件，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="0b923-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="0b923-145">在安全 & 合规性中心中，转到 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0b923-146">在 "**模拟攻击**" 页上的 " **Spear 仿冒（凭据收集）** " 或 " **Spear 仿冒（附件）** " 部分，单击 "**攻击详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="0b923-147">在何处创建模板无关紧要。</span><span class="sxs-lookup"><span data-stu-id="0b923-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="0b923-148">对于这两种类型的网络钓鱼攻击，模板中的可用选项都是相同的。</span><span class="sxs-lookup"><span data-stu-id="0b923-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="0b923-149">在打开的 "**攻击详细信息**" 页上的 "**仿冒模板**" 部分的 "**创建模板**" 区域中，单击 "**新建模板**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="0b923-150">"**配置仿冒模板**向导" 将在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="0b923-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="0b923-151">在 "**开始**" 步骤中，为模板输入一个唯一的显示名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="0b923-152">在 "**配置电子邮件详细信息**" 步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0b923-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="0b923-153">**From （Name）**：用于邮件发件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0b923-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="0b923-154">发件人 **（电子邮件）**：发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0b923-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="0b923-155">**网络钓鱼登录服务器 URL**：单击下拉列表，并从列表中选择一个可用的 url。</span><span class="sxs-lookup"><span data-stu-id="0b923-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="0b923-156">这是用户将被引诱单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="0b923-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="0b923-157">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="0b923-157">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="0b923-158">所有 Url 都是有意的 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="0b923-158">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="0b923-159">URL 信誉服务可能会将这些 Url 中的一个或多个标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="0b923-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="0b923-160">在网络仿冒活动中使用 URL 之前，请先检查受支持的 web 浏览器中的 URL 是否可用。</span><span class="sxs-lookup"><span data-stu-id="0b923-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="0b923-161">**自定义登陆页面 URL**：输入用户在单击 "仿冒" 链接并输入其凭据时使用的可选登录页。</span><span class="sxs-lookup"><span data-stu-id="0b923-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="0b923-162">此链接将替换默认登录页。</span><span class="sxs-lookup"><span data-stu-id="0b923-162">This link replaces the default landing page.</span></span> <span data-ttu-id="0b923-163">例如，如果您有内部意识培训，则可以在此指定 URL。</span><span class="sxs-lookup"><span data-stu-id="0b923-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="0b923-164">**类别**：当前未使用此设置（输入的任何内容都将被忽略）。</span><span class="sxs-lookup"><span data-stu-id="0b923-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="0b923-165">**主题**：电子邮件的 "**主题**" 字段。</span><span class="sxs-lookup"><span data-stu-id="0b923-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="0b923-166">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b923-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0b923-167">在 "**撰写电子邮件**" 步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="0b923-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="0b923-168">您可以使用 "**电子邮件**" 选项卡（丰富的 html 编辑器）或 "**源**" 选项卡（原始 HTML 代码）。</span><span class="sxs-lookup"><span data-stu-id="0b923-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="0b923-169">HTML 格式可以简单，也可以复杂，因为您需要它。</span><span class="sxs-lookup"><span data-stu-id="0b923-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="0b923-170">您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的 believability。</span><span class="sxs-lookup"><span data-stu-id="0b923-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="0b923-171">`${username}`插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="0b923-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="0b923-172">`${loginserverurl}`插入上一步中的**网络钓鱼登录服务器 URL**值。</span><span class="sxs-lookup"><span data-stu-id="0b923-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="0b923-173">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b923-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="0b923-174">在 "**确认**" 步骤中，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="0b923-175">步骤2：创建和启动 spear 仿冒活动</span><span class="sxs-lookup"><span data-stu-id="0b923-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="0b923-176">在安全 & 合规性中心中，转到 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0b923-177">在 "**模拟攻击**" 页面上，根据您要创建的市场活动类型，进行下列选择之一：</span><span class="sxs-lookup"><span data-stu-id="0b923-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="0b923-178">在 " **Spear 仿冒（凭据收集）** " 部分，单击 "**启动攻击**" 或单击 "**攻击详细信息** \> **启动攻击**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="0b923-179">在 " **Spear 仿冒（附件）** " 部分，单击 "**启动攻击**" 或单击 "**攻击详细信息** \> **启动攻击**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="0b923-180">"**配置网络钓鱼攻击**向导" 将在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="0b923-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="0b923-181">在 "**开始**" 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0b923-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0b923-182">在 "**名称**" 框中，为市场活动输入唯一的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0b923-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="0b923-183">不要单击 "**使用模板**"，因为稍后将在向导中创建电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0b923-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="0b923-184">单击 "**使用模板**"，然后选择一个内置或自定义电子邮件模板。</span><span class="sxs-lookup"><span data-stu-id="0b923-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="0b923-185">选择模板后，将根据模板自动填充 "**名称**" 框，但您可以更改名称。</span><span class="sxs-lookup"><span data-stu-id="0b923-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![网络钓鱼起始页](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="0b923-187">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b923-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0b923-188">在 "**目标收件人**" 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0b923-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0b923-189">单击 "**通讯簿**" 选择市场活动的收件人（用户或组）。</span><span class="sxs-lookup"><span data-stu-id="0b923-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="0b923-190">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0b923-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="0b923-191">如果在未输入搜索条件的情况下单击 "**筛选**和**应用**"，则将返回所有收件人并将其添加到市场活动中。</span><span class="sxs-lookup"><span data-stu-id="0b923-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="0b923-192">单击 "**导**入"，然后单击 "**文件导**入" 以导入逗号分隔值（CSV）或电子邮件地址的行分隔文件。</span><span class="sxs-lookup"><span data-stu-id="0b923-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="0b923-193">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0b923-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="0b923-194">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b923-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0b923-195">在 "**配置电子邮件详细信息**" 步骤中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0b923-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="0b923-196">如果您在 "**开始**" 步骤中选择了一个模板，则这些值中的大多数已配置，但您可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="0b923-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="0b923-197">**From （Name）**：用于邮件发件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0b923-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="0b923-198">发件人 **（电子邮件）**：发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0b923-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="0b923-199">您可以输入组织的电子邮件域中的真实或虚假电子邮件地址，也可以输入真实或虚假的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0b923-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="0b923-200">组织中的有效发件人电子邮件地址将在收件人的电子邮件客户端中实际解析。</span><span class="sxs-lookup"><span data-stu-id="0b923-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="0b923-201">**网络钓鱼登录服务器 URL**：单击下拉列表，并从列表中选择一个可用的 url。</span><span class="sxs-lookup"><span data-stu-id="0b923-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="0b923-202">这是用户将被引诱单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="0b923-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="0b923-203">）这三个选项包括：</span><span class="sxs-lookup"><span data-stu-id="0b923-203">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="0b923-204">所有 Url 都是有意的 http，而不是 https。</span><span class="sxs-lookup"><span data-stu-id="0b923-204">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="0b923-205">URL 信誉服务可能会将这些 Url 中的一个或多个标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="0b923-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="0b923-206">在网络仿冒活动中使用 URL 之前，请先检查受支持的 web 浏览器中的 URL 是否可用。</span><span class="sxs-lookup"><span data-stu-id="0b923-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="0b923-207">您需要选择一个 URL。</span><span class="sxs-lookup"><span data-stu-id="0b923-207">You are required to select a URL.</span></span> <span data-ttu-id="0b923-208">对于<b>Spear 仿冒（附件）</b>市场活动，您可以在下一步中删除邮件正文中的链接（否则，邮件将同时包含链接<b>和</b>附件）。</span><span class="sxs-lookup"><span data-stu-id="0b923-208">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="0b923-209">**附件类型**：此设置仅在**Spear 仿冒（附件）** 市场活动中可用。</span><span class="sxs-lookup"><span data-stu-id="0b923-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="0b923-210">单击下拉箭头，然后选择 "" **。.DOCX**或 **。PDF**中的列表。</span><span class="sxs-lookup"><span data-stu-id="0b923-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="0b923-211">**附件名称**：此设置仅在**Spear 仿冒（附件）** 市场活动中可用。</span><span class="sxs-lookup"><span data-stu-id="0b923-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="0b923-212">输入 .docx 或 .pdf 附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="0b923-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="0b923-213">**自定义登陆页面 URL**：输入用户在单击 "仿冒" 链接并输入其凭据时使用的可选登录页。</span><span class="sxs-lookup"><span data-stu-id="0b923-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="0b923-214">此链接将替换默认登录页。</span><span class="sxs-lookup"><span data-stu-id="0b923-214">This link replaces the default landing page.</span></span> <span data-ttu-id="0b923-215">例如，如果您有内部意识培训，则可以在此指定 URL。</span><span class="sxs-lookup"><span data-stu-id="0b923-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="0b923-216">**主题**：电子邮件的 "**主题**" 字段。</span><span class="sxs-lookup"><span data-stu-id="0b923-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="0b923-217">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b923-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0b923-218">在 "**撰写电子邮件**" 步骤中，创建电子邮件的邮件正文。</span><span class="sxs-lookup"><span data-stu-id="0b923-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="0b923-219">如果在 "**开始**" 步骤中选择了一个模板，则表示已配置邮件正文，但您可以对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="0b923-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="0b923-220">您可以使用 "**电子邮件**" 选项卡（丰富的 html 编辑器）或 "**源**" 选项卡（原始 HTML 代码）。</span><span class="sxs-lookup"><span data-stu-id="0b923-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="0b923-221">HTML 格式可以简单，也可以复杂，因为您需要它。</span><span class="sxs-lookup"><span data-stu-id="0b923-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="0b923-222">您可以插入图像和文本，以增强收件人的电子邮件客户端中邮件的 believability。</span><span class="sxs-lookup"><span data-stu-id="0b923-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="0b923-223">`${username}`插入收件人的姓名。</span><span class="sxs-lookup"><span data-stu-id="0b923-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="0b923-224">`${loginserverurl}`插入**网络钓鱼登录服务器 URL**值。</span><span class="sxs-lookup"><span data-stu-id="0b923-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="0b923-225">对于**Spear 仿冒（附件）** 市场活动，应删除邮件正文中的链接（否则，邮件将同时包含链接**和**附件，附件市场活动中不会跟踪链接单击）。</span><span class="sxs-lookup"><span data-stu-id="0b923-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![撰写电子邮件正文](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="0b923-227">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b923-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="0b923-228">在 "**确认**" 步骤中，单击 "**完成**" 以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="0b923-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="0b923-229">将仿冒邮件传递给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="0b923-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="0b923-230">密码攻击市场活动</span><span class="sxs-lookup"><span data-stu-id="0b923-230">Password attack campaigns</span></span>

<span data-ttu-id="0b923-231">*密码攻击*尝试猜测组织中的用户帐户的密码，通常是在攻击者标识了一个或多个有效的用户帐户之后。</span><span class="sxs-lookup"><span data-stu-id="0b923-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="0b923-232">在攻击模拟器中，可以使用两种不同类型的密码攻击活动来测试用户密码的复杂性：</span><span class="sxs-lookup"><span data-stu-id="0b923-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="0b923-233">**强力密码（字典攻击）**：*强力*攻击或*字典*攻击在用户帐户上使用密码的大型字典文件，希望其中一个密码可以使用（针对一个帐户的多个密码）。</span><span class="sxs-lookup"><span data-stu-id="0b923-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="0b923-234">不正确的密码锁定帮助阻止强力密码攻击。</span><span class="sxs-lookup"><span data-stu-id="0b923-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="0b923-235">对于字典攻击，可以指定要尝试的一个或多个密码（手动输入或在上载的文件中），并且可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="0b923-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="0b923-236">**密码喷涂攻击**：*密码喷涂*攻击对用户帐户列表使用相同的仔细考虑密码（针对多个帐户使用一个密码）。</span><span class="sxs-lookup"><span data-stu-id="0b923-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="0b923-237">密码喷涂攻击比强力密码攻击更难检测（当攻击者在几十个或数百个帐户之间尝试一个密码，而不会导致用户不正确的密码锁定的风险时，成功的概率也会增加。</span><span class="sxs-lookup"><span data-stu-id="0b923-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="0b923-238">对于密码喷涂攻击，只能指定一个密码进行尝试，并且您可以指定一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="0b923-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="0b923-239">攻击模拟器中的密码攻击会将用户名和密码的基本身份验证请求传递给终结点，以便它们也适用于其他身份验证方法（AD FS、密码哈希同步、传递、PingFederate 等）。</span><span class="sxs-lookup"><span data-stu-id="0b923-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="0b923-240">对于启用了 MFA 的用户（即使密码攻击尝试其实际密码），尝试将始终注册为失败（换句话说，MFA 用户永远不会出现在市场活动的**成功尝试**计数中）。</span><span class="sxs-lookup"><span data-stu-id="0b923-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="0b923-241">这是预期的结果。</span><span class="sxs-lookup"><span data-stu-id="0b923-241">This is the expected result.</span></span> <span data-ttu-id="0b923-242">MFA 是一种帮助防止密码攻击的主要方法。</span><span class="sxs-lookup"><span data-stu-id="0b923-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="0b923-243">创建和启动密码攻击市场活动</span><span class="sxs-lookup"><span data-stu-id="0b923-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="0b923-244">在安全 & 合规性中心中，转到 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0b923-245">在 "**模拟攻击**" 页面上，根据您要创建的市场活动类型，进行下列选择之一：</span><span class="sxs-lookup"><span data-stu-id="0b923-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="0b923-246">在**强力密码（字典攻击）** 部分，单击 "**启动攻击**" 或单击 "**攻击详细信息** \> **启动攻击**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="0b923-247">在 "**密码喷涂攻击**" 部分，单击 "**启动攻击**" 或单击 "**攻击详细信息** \> **启动攻击**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="0b923-248">"**配置密码攻击**向导" 将在新的浮出控件中启动。</span><span class="sxs-lookup"><span data-stu-id="0b923-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="0b923-249">在 "**开始**" 步骤中，为市场活动输入一个唯一的显示名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="0b923-250">在 "**目标用户**" 步骤中，执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0b923-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0b923-251">单击 "**通讯簿**" 选择市场活动的收件人（用户或组）。</span><span class="sxs-lookup"><span data-stu-id="0b923-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="0b923-252">每个目标收件人都必须有一个 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0b923-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="0b923-253">如果在未输入搜索条件的情况下单击 "**筛选**和**应用**"，则将返回所有收件人并将其添加到市场活动中。</span><span class="sxs-lookup"><span data-stu-id="0b923-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="0b923-254">单击 "**导**入"，然后单击 "**文件导**入" 以导入逗号分隔值（CSV）或电子邮件地址的行分隔文件。</span><span class="sxs-lookup"><span data-stu-id="0b923-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="0b923-255">每行必须包含收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0b923-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="0b923-256">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b923-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0b923-257">在 "**选择攻击设置**" 步骤中，选择要基于市场活动类型执行的操作：</span><span class="sxs-lookup"><span data-stu-id="0b923-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="0b923-258">**强力密码（字典攻击）**：执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="0b923-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="0b923-259">**手动输入密码**：在**按 enter 以添加密码**框中，键入一个密码，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="0b923-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="0b923-260">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="0b923-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="0b923-261">**上载字典文件中的密码**：单击 "**上传**" 以导入每行包含一个密码的现有文本文件和一个空白的最后一行。</span><span class="sxs-lookup"><span data-stu-id="0b923-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="0b923-262">文本文件的大小必须为 10 MB 或更小，并且不能包含超过30000个密码。</span><span class="sxs-lookup"><span data-stu-id="0b923-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="0b923-263">**密码喷涂攻击**：在 "**攻击中使用的密码**" 框中，输入一个密码。</span><span class="sxs-lookup"><span data-stu-id="0b923-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="0b923-264">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b923-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0b923-265">在 "**确认**" 步骤中，单击 "**完成**" 以启动市场活动。</span><span class="sxs-lookup"><span data-stu-id="0b923-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="0b923-266">您指定的密码将尝试您指定的用户。</span><span class="sxs-lookup"><span data-stu-id="0b923-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="0b923-267">查看市场活动结果</span><span class="sxs-lookup"><span data-stu-id="0b923-267">View campaign results</span></span>

<span data-ttu-id="0b923-268">启动市场活动后，可以在 "主**模拟攻击**" 页上查看进度和结果。</span><span class="sxs-lookup"><span data-stu-id="0b923-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="0b923-269">活动的市场活动将显示状态栏、已完成的百分比值和 "（全部用户的用户）" 的计数。</span><span class="sxs-lookup"><span data-stu-id="0b923-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="0b923-270">单击 "**刷新**" 按钮将更新任何活动活动的进度。</span><span class="sxs-lookup"><span data-stu-id="0b923-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="0b923-271">您还可以单击 "**终止**" 以停止活动的市场活动。</span><span class="sxs-lookup"><span data-stu-id="0b923-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="0b923-272">在市场活动完成后，状态将更改为 "**已完成攻击**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="0b923-273">您可以通过执行以下任一操作来查看市场活动的结果：</span><span class="sxs-lookup"><span data-stu-id="0b923-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="0b923-274">在 "主**模拟攻击**" 页面上，单击市场活动名称下的 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="0b923-275">在 "主**模拟攻击**" 页面上，单击攻击类型部分中的 "**攻击详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="0b923-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="0b923-276">在打开的 "**攻击详细信息**" 页上，选择 "**攻击历史记录**" 部分中的 "活动"。</span><span class="sxs-lookup"><span data-stu-id="0b923-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="0b923-277">上述任一操作都将转到名为 "**攻击详细信息**" 的页面。</span><span class="sxs-lookup"><span data-stu-id="0b923-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="0b923-278">以下各节介绍了在此页面上为每种类型的市场活动提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0b923-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="0b923-279">Spear 网络钓鱼（凭据收集）市场活动结果</span><span class="sxs-lookup"><span data-stu-id="0b923-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="0b923-280">以下信息在每个市场活动的 "**攻击详细信息**" 页上提供：</span><span class="sxs-lookup"><span data-stu-id="0b923-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0b923-281">市场活动的持续时间（开始日期/时间和结束日期/时间）。</span><span class="sxs-lookup"><span data-stu-id="0b923-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0b923-282">**目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="0b923-282">**Total users targeted**</span></span>

- <span data-ttu-id="0b923-283">**成功的尝试**：单击链接的用户数 **，并**输入其凭据（*任何*用户名和密码值）。</span><span class="sxs-lookup"><span data-stu-id="0b923-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="0b923-284">**总体成功率**：由**成功尝试**的  /  **用户的目标总数**计算所得的百分比。</span><span class="sxs-lookup"><span data-stu-id="0b923-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0b923-285">**最快的点击**次数：启动市场活动后，第一个用户单击链接所需的时间。</span><span class="sxs-lookup"><span data-stu-id="0b923-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="0b923-286">**平均单击**次数：每个人单击链接所花的时间除以单击链接的用户数。</span><span class="sxs-lookup"><span data-stu-id="0b923-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="0b923-287">**单击 "成功率**：计算人" （单击链接的用户数）/**目标的用户总数**的百分比。</span><span class="sxs-lookup"><span data-stu-id="0b923-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="0b923-288">**最快的凭据**：在启动市场活动后，第一个用户输入其凭据所需的时间。</span><span class="sxs-lookup"><span data-stu-id="0b923-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="0b923-289">**平均凭据**：每个人输入其凭据所花的时间除以输入其凭据的用户数量的总和。</span><span class="sxs-lookup"><span data-stu-id="0b923-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="0b923-290">**凭据成功率**：计算的百分比（输入其凭据的用户数）/**目标的用户总数**。</span><span class="sxs-lookup"><span data-stu-id="0b923-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="0b923-291">显示**链接已单击**的条形图，以及**凭据**每日提供的数字。</span><span class="sxs-lookup"><span data-stu-id="0b923-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="0b923-292">显示**链接已单击**、**提供凭据**和**无**市场活动百分比的圆形图。</span><span class="sxs-lookup"><span data-stu-id="0b923-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="0b923-293">"已**损坏的用户**" 部分列出了单击该链接的用户的详细信息：</span><span class="sxs-lookup"><span data-stu-id="0b923-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="0b923-294">用户的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="0b923-294">The user's email address</span></span>

  - <span data-ttu-id="0b923-295">单击链接时的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="0b923-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="0b923-296">客户端 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0b923-296">The client IP address.</span></span>

  - <span data-ttu-id="0b923-297">有关用户的 Windows 和 web 浏览器的版本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b923-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="0b923-298">您可以单击 "**导出**" 将结果导出到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="0b923-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="0b923-299">Spear 仿冒（附件）市场活动结果</span><span class="sxs-lookup"><span data-stu-id="0b923-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="0b923-300">以下信息在每个市场活动的 "**攻击详细信息**" 页上提供：</span><span class="sxs-lookup"><span data-stu-id="0b923-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0b923-301">市场活动的持续时间（开始日期/时间和结束日期/时间）。</span><span class="sxs-lookup"><span data-stu-id="0b923-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0b923-302">**目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="0b923-302">**Total users targeted**</span></span>

- <span data-ttu-id="0b923-303">**成功的尝试**：打开或下载并打开附件的用户数（预览不计数）。</span><span class="sxs-lookup"><span data-stu-id="0b923-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="0b923-304">**总体成功率**：由**成功尝试**的  /  **用户的目标总数**计算所得的百分比。</span><span class="sxs-lookup"><span data-stu-id="0b923-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0b923-305">**最快的附件打开时间**：启动市场活动后，首个用户打开附件所需的时间。</span><span class="sxs-lookup"><span data-stu-id="0b923-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="0b923-306">**平均附件打开时间**：每个人打开附件所花的时间除以打开附件的用户数。</span><span class="sxs-lookup"><span data-stu-id="0b923-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="0b923-307">**附件打开成功比率**：计算的百分比（打开附件的用户数）/**目标的用户总数**。</span><span class="sxs-lookup"><span data-stu-id="0b923-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="0b923-308">强力密码（字典攻击）市场活动结果</span><span class="sxs-lookup"><span data-stu-id="0b923-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="0b923-309">以下信息在每个市场活动的 "**攻击详细信息**" 页上提供：</span><span class="sxs-lookup"><span data-stu-id="0b923-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0b923-310">市场活动的持续时间（开始日期/时间和结束日期/时间）。</span><span class="sxs-lookup"><span data-stu-id="0b923-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0b923-311">**目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="0b923-311">**Total users targeted**</span></span>

- <span data-ttu-id="0b923-312">**成功的尝试**：找到的使用指定密码之一的用户数。</span><span class="sxs-lookup"><span data-stu-id="0b923-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="0b923-313">**总体成功率**：由**成功尝试**的  /  **用户的目标总数**计算所得的百分比。</span><span class="sxs-lookup"><span data-stu-id="0b923-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0b923-314">"已**损坏的用户**" 部分列出了受影响的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0b923-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="0b923-315">您可以单击 "**导出**" 将结果导出到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="0b923-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="0b923-316">密码喷涂攻击活动结果</span><span class="sxs-lookup"><span data-stu-id="0b923-316">Password spray attack campaign results</span></span>

<span data-ttu-id="0b923-317">以下信息在每个市场活动的 "**攻击详细信息**" 页上提供：</span><span class="sxs-lookup"><span data-stu-id="0b923-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0b923-318">市场活动的持续时间（开始日期/时间和结束日期/时间）。</span><span class="sxs-lookup"><span data-stu-id="0b923-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0b923-319">**目标的用户总数**</span><span class="sxs-lookup"><span data-stu-id="0b923-319">**Total users targeted**</span></span>

- <span data-ttu-id="0b923-320">**成功的尝试**：找到的使用指定密码的用户数量。</span><span class="sxs-lookup"><span data-stu-id="0b923-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="0b923-321">**总体成功率**：由**成功尝试**的  /  **用户的目标总数**计算所得的百分比。</span><span class="sxs-lookup"><span data-stu-id="0b923-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
