---
title: Office 365 中的攻击模拟器
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
description: 作为 Office 365 全局管理员，你可以使用攻击模拟器在你的组织中运行实际的攻击方案。 这可帮助你在真正的攻击击中你的业务之前识别和查找易受攻击的用户。
ms.openlocfilehash: 6fb88e6b79c0949c7ddc26eabda2bb04ea1fa3bf
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957407"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="77f97-104">Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="77f97-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="77f97-105">**摘要**如果您是 Office 365 全局管理员或安全管理员，并且您的组织具有 Office 365 高级威胁防护计划2（其中包括[威胁调查和响应功能](office-365-ti.md)），则可以使用攻击模拟器在组织中运行实际的攻击方案。</span><span class="sxs-lookup"><span data-stu-id="77f97-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="77f97-106">这可以帮助您识别和查找易受攻击的用户，在真正的攻击影响你的底线之前。</span><span class="sxs-lookup"><span data-stu-id="77f97-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="77f97-107">阅读本文以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="77f97-107">Read this article to learn more.</span></span>

## <a name="the-attacks"></a><span data-ttu-id="77f97-108">攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-108">The Attacks</span></span>

<span data-ttu-id="77f97-109">目前提供三种攻击模拟：</span><span class="sxs-lookup"><span data-stu-id="77f97-109">Three kinds of attack simulations are currently available:</span></span>

- [<span data-ttu-id="77f97-110">凭据收集 spear-网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-110">Credential harvest spear-phishing attack</span></span>](#credential-harvest-spear-phishing-attack)

- [<span data-ttu-id="77f97-111">附件 spear-网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-111">Attachment spear-phishing attack</span></span>](#attachment-spear-phishing-attack)

- [<span data-ttu-id="77f97-112">密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-112">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="77f97-113">强力密码攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-113">Brute-force password attack</span></span>](#brute-force-password-attack)

<span data-ttu-id="77f97-114">为成功启动攻击，请确保用于运行模拟攻击的帐户使用多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="77f97-114">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="77f97-115">此外，您必须是 Office 365 全局管理员或安全管理员。</span><span class="sxs-lookup"><span data-stu-id="77f97-115">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="77f97-116">（若要了解有关角色和权限的详细信息，请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。）</span><span class="sxs-lookup"><span data-stu-id="77f97-116">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="77f97-117">若要访问攻击模拟器，请在&amp; "安全合规性中心" 中，选择 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="77f97-117">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="77f97-118">开始之前...</span><span class="sxs-lookup"><span data-stu-id="77f97-118">Before you begin...</span></span>

<span data-ttu-id="77f97-119">请确保您和您的组织满足以下攻击模拟器的要求：</span><span class="sxs-lookup"><span data-stu-id="77f97-119">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>

- <span data-ttu-id="77f97-120">您的组织的电子邮件托管在 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="77f97-120">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="77f97-121">（攻击模拟器对本地电子邮件服务器不可用。）</span><span class="sxs-lookup"><span data-stu-id="77f97-121">(Attack Simulator is not available for on-premises email servers.)</span></span>

- <span data-ttu-id="77f97-122">您是 Office 365 全局管理员或安全管理员</span><span class="sxs-lookup"><span data-stu-id="77f97-122">You are an Office 365 global administrator or security administrator</span></span>

- <span data-ttu-id="77f97-123">网络钓鱼活动将在30天内收集和处理事件，历史宣传活动数据将在市场活动启动后最长90天可用。</span><span class="sxs-lookup"><span data-stu-id="77f97-123">Phishing campaigns will collect and process events for a period of 30 days, historical campaign data will be available for up to 90 days after the campaign is launched.</span></span>

- <span data-ttu-id="77f97-124">[多因素身份验证/条件访问](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)已打开，至少适用于将使用攻击模拟器的 Office 365 全局管理员帐户和安全管理员。</span><span class="sxs-lookup"><span data-stu-id="77f97-124">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="77f97-125">（理想情况下，为组织中的所有用户启用多重身份验证/条件访问。）</span><span class="sxs-lookup"><span data-stu-id="77f97-125">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

- <span data-ttu-id="77f97-126">您的组织[具有 Office 365 高级威胁防护计划 2](office-365-atp.md)，在&amp;安全合规性中心中显示攻击模拟器（转到**威胁管理** \> **攻击模拟器**）</span><span class="sxs-lookup"><span data-stu-id="77f97-126">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![威胁管理-攻击模拟器](../media/ThreatMgmt-AttackSimulator.png)

## <a name="credential-harvest-spear-phishing-attack"></a><span data-ttu-id="77f97-128">凭据收集 spear-网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-128">Credential harvest spear-phishing attack</span></span>

<span data-ttu-id="77f97-129">网络钓鱼是一种通用术语，用于作为社会工程手段攻击的广泛攻击组 classed。</span><span class="sxs-lookup"><span data-stu-id="77f97-129">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="77f97-130">此攻击主要针对 spear 网络钓鱼，这是一种更有针对性的攻击，面向一组特定的个人或组织。</span><span class="sxs-lookup"><span data-stu-id="77f97-130">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="77f97-131">通常，自定义攻击会执行某些侦测，并使用将在收件人中生成信任的显示名称，例如看起来像来自组织中的执行者的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77f97-131">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="77f97-132">此攻击的重点在于通过更改显示名称和源地址，使您能够操纵发件人显示的来源。</span><span class="sxs-lookup"><span data-stu-id="77f97-132">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="77f97-133">如果 spear 攻击成功，cyberattackers 将获得对用户凭据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="77f97-133">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>

### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="77f97-134">模拟 spear 网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-134">To simulate a spear-phishing attack</span></span>

![撰写电子邮件正文](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

<span data-ttu-id="77f97-136">您可以直接在**电子邮件正文**字段中手工创建丰富的 HTML 编辑器，或使用 HTML 源。</span><span class="sxs-lookup"><span data-stu-id="77f97-136">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>

1. <span data-ttu-id="77f97-137">在 "[安全&amp;合规性中心](https://protection.office.com)" 中，选择 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="77f97-137">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="77f97-138">为攻击指定有意义的市场活动名称或选择一个模板。</span><span class="sxs-lookup"><span data-stu-id="77f97-138">Specify a meaningful campaign name for the attack or select a template.</span></span>

   ![网络钓鱼起始页](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. <span data-ttu-id="77f97-140">指定目标收件人。</span><span class="sxs-lookup"><span data-stu-id="77f97-140">Specify the target recipients.</span></span> <span data-ttu-id="77f97-141">它可以是组织中的个人或组。</span><span class="sxs-lookup"><span data-stu-id="77f97-141">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="77f97-142">每个目标收件人都必须具有 Exchange Online 邮箱，攻击才会成功。</span><span class="sxs-lookup"><span data-stu-id="77f97-142">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>

   ![收件人选择](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. <span data-ttu-id="77f97-144">配置网络钓鱼电子邮件详细信息。</span><span class="sxs-lookup"><span data-stu-id="77f97-144">Configure the Phishing email details.</span></span>

   ![配置电子邮件详细信息](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   <span data-ttu-id="77f97-146">HTML 格式可以是复杂的，也可以是基本的活动需求。</span><span class="sxs-lookup"><span data-stu-id="77f97-146">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="77f97-147">由于电子邮件格式为 HTML，因此您可以插入图像和文本，以增强 believability。</span><span class="sxs-lookup"><span data-stu-id="77f97-147">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="77f97-148">您可以控制收到的邮件在接收电子邮件客户端中的显示形式。</span><span class="sxs-lookup"><span data-stu-id="77f97-148">You have control on what the received message will look like in the receiving email client.</span></span>

5. <span data-ttu-id="77f97-149">指定 "**发件人" （名称）** 域的文本。</span><span class="sxs-lookup"><span data-stu-id="77f97-149">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="77f97-150">这是在接收电子邮件客户端的**显示名称**中显示的字段。</span><span class="sxs-lookup"><span data-stu-id="77f97-150">This is the field that shows in the **Display Name** in the receiving email client.</span></span>

6. <span data-ttu-id="77f97-151">指定文本或 "**发件人**" 字段。</span><span class="sxs-lookup"><span data-stu-id="77f97-151">Specify text or the **From** field.</span></span> <span data-ttu-id="77f97-152">这是在接收电子邮件客户端中显示为发件人的电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="77f97-152">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

   <span data-ttu-id="77f97-153">您可以在组织中输入现有的电子邮件命名空间（这样做将使电子邮件地址在接收客户端中实际解析，从而便于实现非常高的信任模型），也可以输入外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77f97-153">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="77f97-154">您指定的电子邮件地址不一定确实存在，但需要遵循有效 SMTP 地址的格式，例如`user@domainname.extension`。</span><span class="sxs-lookup"><span data-stu-id="77f97-154">The email address that you specify does not have to actually exist, but it does need to follow the format of a valid SMTP address, such as `user@domainname.extension`.</span></span>

7. <span data-ttu-id="77f97-155">使用下拉选择器，选择一个网络钓鱼登录服务器 URL，该 URL 反映你将在攻击中遇到的内容的类型。</span><span class="sxs-lookup"><span data-stu-id="77f97-155">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="77f97-156">提供了多个主题 Url 供您选择，例如文档交付、技术、工资等。实际上，这是要求目标用户单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="77f97-156">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>

8. <span data-ttu-id="77f97-157">指定自定义登陆页面 URL。</span><span class="sxs-lookup"><span data-stu-id="77f97-157">Specify a custom landing page URL.</span></span> <span data-ttu-id="77f97-158">使用此将会将用户重定向到成功攻击结束时指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="77f97-158">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="77f97-159">例如，如果您具有内部意识培训，可以在此处指定。</span><span class="sxs-lookup"><span data-stu-id="77f97-159">If you have internal awareness training, for example, you can specify that here.</span></span>

9. <span data-ttu-id="77f97-160">指定 "**主题**" 字段的文本。</span><span class="sxs-lookup"><span data-stu-id="77f97-160">Specify text for the **Subject** field.</span></span> <span data-ttu-id="77f97-161">这是在接收电子邮件客户端中显示为**主题名称**的字段。</span><span class="sxs-lookup"><span data-stu-id="77f97-161">This is the field that shows as the **Subject Name** in the receiving email client.</span></span>

10. <span data-ttu-id="77f97-162">撰写目标将接收的**电子邮件正文**。</span><span class="sxs-lookup"><span data-stu-id="77f97-162">Compose the **Email body** that the target will receive.</span></span>

    <span data-ttu-id="77f97-163">`${username}`将目标名称插入到电子邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="77f97-163">`${username}` inserts the targets name into the Email body.</span></span>

    <span data-ttu-id="77f97-164">`${loginserverurl}`插入要让目标用户单击的 URL</span><span class="sxs-lookup"><span data-stu-id="77f97-164">`${loginserverurl}` inserts the URL we want target users to click</span></span>

11. <span data-ttu-id="77f97-165">选择 **"下一步"，** 然后单击 "**完成**" 以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="77f97-165">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="77f97-166">将 spear 网络钓鱼电子邮件传递到目标收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="77f97-166">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span>

## <a name="attachment-spear-phishing-attack"></a><span data-ttu-id="77f97-167">附件 spear-网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-167">Attachment spear-phishing attack</span></span>

<span data-ttu-id="77f97-168">网络钓鱼是一种通用术语，用于作为社会工程手段攻击的广泛攻击组 classed。</span><span class="sxs-lookup"><span data-stu-id="77f97-168">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="77f97-169">此攻击重点关注附件 spear 网络钓鱼，这是一种更有针对性的攻击，面向一组特定的个人或组织。</span><span class="sxs-lookup"><span data-stu-id="77f97-169">This attack is focused on attachment spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="77f97-170">通常，自定义攻击会执行某些侦测，并使用将在收件人中生成信任的显示名称，例如看起来像来自组织中的执行者的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77f97-170">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="77f97-171">此攻击的重点在于通过更改显示名称和源地址，使您能够操作显示的发件人的来源，但这次是，我们提供了尝试获取 t 的附件，而不是提供用于尝试和引诱最终用户单击的 URL。最终用户打开。</span><span class="sxs-lookup"><span data-stu-id="77f97-171">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address, but this time as opposed to offering a URL to try and lure the end user to click, we offer an attachment that we are trying to get the end user to open.</span></span> 

### <a name="to-simulate-a-attachment-spear-phishing-attack"></a><span data-ttu-id="77f97-172">模拟附件 spear 网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-172">To simulate a Attachment spear-phishing attack</span></span>

1. <span data-ttu-id="77f97-173">按照上面的步骤操作，让此时间在登陆页面上单击 "**附件攻击**"。</span><span class="sxs-lookup"><span data-stu-id="77f97-173">Follow the steps from above, having this time clicked on **Attachment Attack** on the landing page.</span></span>

2. <span data-ttu-id="77f97-174">在完成向导的过程中，您将看到两个要配置的选项。</span><span class="sxs-lookup"><span data-stu-id="77f97-174">As you progress through the wizard, you see two options to configure.</span></span> <span data-ttu-id="77f97-175">**附件类型**，我们支持两种附件类型： **.docx**或 **.pdf**。</span><span class="sxs-lookup"><span data-stu-id="77f97-175">The **Attachment Type**, we support two attachment types, **.docx** or **.pdf**.</span></span> <span data-ttu-id="77f97-176">**附件名称**，请使用此字段为市场活动创建有意义的附件名称。</span><span class="sxs-lookup"><span data-stu-id="77f97-176">The **Attachment Name**, use this field to create a meaningful attachment name for the campaign.</span></span>

## <a name="password-spray-attack"></a><span data-ttu-id="77f97-177">密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-177">Password-spray attack</span></span>

<span data-ttu-id="77f97-178">对组织的密码喷涂攻击通常在损坏的主角成功从租户获取有效用户列表之后使用。</span><span class="sxs-lookup"><span data-stu-id="77f97-178">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="77f97-179">错误参与者知道用户使用的常见密码。</span><span class="sxs-lookup"><span data-stu-id="77f97-179">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="77f97-180">这是一种广泛使用的攻击，因为它是运行的廉价攻击，并且比强力方法更难检测。</span><span class="sxs-lookup"><span data-stu-id="77f97-180">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>

<span data-ttu-id="77f97-181">此攻击的重点是让您可以为用户的大型目标群体指定一个公用密码。</span><span class="sxs-lookup"><span data-stu-id="77f97-181">This attack focuses on letting you specify a common password against a large target base of users.</span></span>

<span data-ttu-id="77f97-182">**重要说明**针对已具有多重身份验证的最终用户帐户运行密码喷涂攻击，将导致在报告中对这些帐户执行不成功的尝试。</span><span class="sxs-lookup"><span data-stu-id="77f97-182">**Important Note** running the password spray attack against end user accounts that already have multi-factor authentication, will result in a unsuccessful attempt for those accounts in the reporting.</span></span> <span data-ttu-id="77f97-183">这是因为多重身份验证是主 mechanims 中的一个，可帮助防止出现密码喷涂攻击，因此应该这样做。</span><span class="sxs-lookup"><span data-stu-id="77f97-183">This is due to multi-factor authentication being one of the primary mechanims to help protect against password spray attacks, so is expected.</span></span>

### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="77f97-184">模拟密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-184">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="77f97-185">在 "[安全&amp;合规性中心](https://protection.office.com)" 中，选择 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="77f97-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="77f97-186">为攻击指定有意义的市场活动名称。</span><span class="sxs-lookup"><span data-stu-id="77f97-186">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="77f97-187">指定目标收件人。</span><span class="sxs-lookup"><span data-stu-id="77f97-187">Specify the target recipients.</span></span> <span data-ttu-id="77f97-188">它可以是组织中的个人或组。</span><span class="sxs-lookup"><span data-stu-id="77f97-188">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="77f97-189">目标收件人必须具有 Exchange Online 邮箱，攻击才会成功。</span><span class="sxs-lookup"><span data-stu-id="77f97-189">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="77f97-190">指定用于攻击的密码。</span><span class="sxs-lookup"><span data-stu-id="77f97-190">Specify a password to use for the attack.</span></span> <span data-ttu-id="77f97-191">例如，您可以尝试的`Summer2019`一个常见的相关密码。</span><span class="sxs-lookup"><span data-stu-id="77f97-191">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="77f97-192">另一个可能`Fall2019`是或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="77f97-192">Another might be `Fall2019`, or `Password1`.</span></span>

5. <span data-ttu-id="77f97-193">选择 "**完成**" 以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="77f97-193">Choose **Finish** to launch the attack.</span></span>

## <a name="brute-force-password-attack"></a><span data-ttu-id="77f97-194">强力密码攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-194">Brute-force password attack</span></span>

<span data-ttu-id="77f97-195">对组织的强力密码攻击通常在已损坏的主角成功从租户获取关键用户列表之后使用。</span><span class="sxs-lookup"><span data-stu-id="77f97-195">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="77f97-196">此攻击主要针对单个用户的帐户尝试使用一组密码。</span><span class="sxs-lookup"><span data-stu-id="77f97-196">This attack focuses on trying a set of passwords on a single user's account.</span></span>

<span data-ttu-id="77f97-197">**重要说明**对已经具有多重身份验证的最终用户帐户运行强力密码攻击将导致对报告中这些帐户的尝试失败。</span><span class="sxs-lookup"><span data-stu-id="77f97-197">**Important Note** running the brute-force password attacks against end user accounts that already have multi-factor authentication, will result in a unsuccessful attempt for those accounts in the reporting.</span></span> <span data-ttu-id="77f97-198">这是因为多重身份验证是主 mechanims 中的一个，可帮助防止强力密码攻击，因此应该这样做。</span><span class="sxs-lookup"><span data-stu-id="77f97-198">This is due to multi-factor authentication being one of the primary mechanims to help protect against brute-force password attacks, so is expected.</span></span>

### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="77f97-199">模拟强力密码攻击</span><span class="sxs-lookup"><span data-stu-id="77f97-199">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="77f97-200">在 "[安全&amp;合规性中心](https://protection.office.com)" 中，选择 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="77f97-200">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="77f97-201">为攻击指定有意义的市场活动名称。</span><span class="sxs-lookup"><span data-stu-id="77f97-201">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="77f97-202">指定目标收件人。</span><span class="sxs-lookup"><span data-stu-id="77f97-202">Specify the target recipient.</span></span> <span data-ttu-id="77f97-203">目标收件人必须具有 Exchange Online 邮箱，攻击才会成功。</span><span class="sxs-lookup"><span data-stu-id="77f97-203">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="77f97-204">指定用于攻击的一组密码。</span><span class="sxs-lookup"><span data-stu-id="77f97-204">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="77f97-205">为此，您可以对密码列表使用文本（.txt）文件。</span><span class="sxs-lookup"><span data-stu-id="77f97-205">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="77f97-206">文件大小中的文本文件不能超过 10 MB。</span><span class="sxs-lookup"><span data-stu-id="77f97-206">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="77f97-207">每行使用一个密码，并确保在列表中的最后一个密码后面包含一个硬回车。</span><span class="sxs-lookup"><span data-stu-id="77f97-207">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>

5. <span data-ttu-id="77f97-208">选择 "**完成**" 以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="77f97-208">Choose **Finish** to launch the attack.</span></span>



<span data-ttu-id="77f97-209">请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看正在开发的内容、正在滚动的内容以及已启动的内容。</span><span class="sxs-lookup"><span data-stu-id="77f97-209">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="77f97-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77f97-210">See also</span></span>

[<span data-ttu-id="77f97-211">Office 365 高级威胁防护服务说明</span><span class="sxs-lookup"><span data-stu-id="77f97-211">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="77f97-212">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="77f97-212">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
