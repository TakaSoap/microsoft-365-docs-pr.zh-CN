---
title: 从我的自定义域试点 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何仅使用两个测试帐户将电子邮件功能试点从我的自定义域到 Microsoft 365 邮箱的电子邮件功能。
ms.openlocfilehash: 6cc5b1163f666af4bd13047ab3b1fda7fd747b5f
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688213"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="deff9-103">从我的自定义域试点 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="deff9-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="deff9-104">可以按照以下要求和限制试用 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="deff9-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="deff9-105">你的当前电子邮件提供商必须提供电子邮件转发功能。</span><span class="sxs-lookup"><span data-stu-id="deff9-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="deff9-106">必须在 DNS 托管提供商处管理 Microsoft 365 DNS记录，而不是让 Microsoft 365 为你管理这些记录。</span><span class="sxs-lookup"><span data-stu-id="deff9-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="deff9-107">要了解更多信息，请参阅[添加 DNS 记录以连接你的域](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="deff9-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="deff9-108">没有其他电子邮件服务器上的用户的忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="deff9-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="deff9-109">管理员无法从单个位置管理所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="deff9-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="deff9-110">用户可能无法使用 Microsoft 365 垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="deff9-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="deff9-111">推荐少数用户使用，仅适用于使用电子邮件作为试点。</span><span class="sxs-lookup"><span data-stu-id="deff9-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="deff9-112">设置 Microsoft 365 试点</span><span class="sxs-lookup"><span data-stu-id="deff9-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="deff9-113">请按照以下步骤设置 Microsoft 365 试点：</span><span class="sxs-lookup"><span data-stu-id="deff9-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="deff9-114">步骤 1：登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="deff9-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="deff9-115">使用你的工作或学校帐户登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="deff9-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="deff9-116">在左侧导航窗格中，选择“**设置**” > “**域**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="deff9-117">步骤 2：验证你是否拥有要使用的域</span><span class="sxs-lookup"><span data-stu-id="deff9-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="deff9-118">在“**域**”页面上，选择“**添加域**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="deff9-119">在框中键入域名，选择“**使用此域**”，然后选择“**继续**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="deff9-120">选择要在你的域中测试的服务，例如电子邮件和即时消息。</span><span class="sxs-lookup"><span data-stu-id="deff9-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="deff9-121">在“**验证域**”页面上，按照分步说明进行操作，然后选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="deff9-122">DNS 更改需要几分钟到 72 小时才会生效。</span><span class="sxs-lookup"><span data-stu-id="deff9-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="deff9-123">如果验证成功，系统将要求你修改 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="deff9-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="deff9-124">步骤 3：在 Exchange Online 中将域标记为共享</span><span class="sxs-lookup"><span data-stu-id="deff9-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="deff9-125">在 Exchange 管理中心的“**邮件流**”部分，选择“**接受的域**”，然后选择要修改的域。</span><span class="sxs-lookup"><span data-stu-id="deff9-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="deff9-126">双击以打开窗口，然后选择“**内部中继**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-126">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="deff9-127">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-127">Select **Save**.</span></span>

    <span data-ttu-id="deff9-128">此设置可能需要几分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="deff9-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="deff9-129">步骤 4：取消阻止现有电子邮件服务器（可选）</span><span class="sxs-lookup"><span data-stu-id="deff9-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="deff9-130">Microsoft 365 使用 Exchange Online Protection (EOP) 进行垃圾邮件防护。</span><span class="sxs-lookup"><span data-stu-id="deff9-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="deff9-131">如果 EOP 检测到当前邮件服务器转发了大量垃圾邮件，它可能会阻止你现有的邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="deff9-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="deff9-132">如果你信任适用于其他电子邮件提供商的垃圾邮件保护，则可以在 Microsoft 365 中取消阻止服务器。</span><span class="sxs-lookup"><span data-stu-id="deff9-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="deff9-133">通过取消阻止现有电子邮件服务器，通过原始服务器送达的任何垃圾邮件都会进入 Microsoft 365 邮箱，而且无法评估 Microsoft 365 防止垃圾邮件的效果。</span><span class="sxs-lookup"><span data-stu-id="deff9-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="deff9-134">在 Exchange 管理中心导航窗格中，选择“**保护**”，然后选择“**连接筛选器**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="deff9-135">在“**IP 允许列表**”中，选择 **+**，然后添加当前电子邮件提供商的邮件服务器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="deff9-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="deff9-136">步骤 5：创建用户帐户和设置主答复地址</span><span class="sxs-lookup"><span data-stu-id="deff9-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="deff9-137">在 Microsoft 365 管理中心的左侧窗格，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="deff9-138">通过添加两个现有用户，创建两个测试帐户。</span><span class="sxs-lookup"><span data-stu-id="deff9-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="deff9-139">对于每个帐户，请选择“**+ 添加用户**”，然后填写所需的信息，包括要测试的密码方法。</span><span class="sxs-lookup"><span data-stu-id="deff9-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="deff9-140">若要确保用户的电子邮件保持不变，“**用户名**”字段必须与用户的当前电子邮件地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="deff9-140">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="deff9-141">选择相应的许可证，单击“**下一步**”，然后单击“**完成添加**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="deff9-142">在“**用户名**”旁边，从下拉列表中选择你的自定义域名。</span><span class="sxs-lookup"><span data-stu-id="deff9-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="deff9-143">选择“**创建**” > “**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="deff9-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="deff9-144">步骤6： \* \* 将邮件配置为从 Microsoft 365 或 Office 365 传输到电子邮件服务器</span><span class="sxs-lookup"><span data-stu-id="deff9-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="deff9-145">此部分包含以下两个步骤：</span><span class="sxs-lookup"><span data-stu-id="deff9-145">There are two steps for this:</span></span>

1. <span data-ttu-id="deff9-146">配置 Microsoft 365 或 Office 365 环境。</span><span class="sxs-lookup"><span data-stu-id="deff9-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="deff9-147">设置从 Microsoft 365 或 Office 365 指向电子邮件服务器的连接器。</span><span class="sxs-lookup"><span data-stu-id="deff9-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="deff9-148">1. 配置 Microsoft 365 或 Office 365 环境</span><span class="sxs-lookup"><span data-stu-id="deff9-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="deff9-149">请务必在 Microsoft 365 或 Office365 中完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="deff9-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="deff9-150">如需设置连接器，则必须先获得分配的权限，然后才能开始设置。</span><span class="sxs-lookup"><span data-stu-id="deff9-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="deff9-151">若要查看您需要获得哪些权限，请参阅 [Feature permissions in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop) 主题中的“Microsoft 365 和 Office 365 连接器”条目。</span><span class="sxs-lookup"><span data-stu-id="deff9-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop) topic.</span></span>

2. <span data-ttu-id="deff9-152">如果你希望 EOP 或 Exchange Online 将电子邮件从你的电子邮件服务器中继到互联网，则：</span><span class="sxs-lookup"><span data-stu-id="deff9-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="deff9-153">使用在 Microsoft 365 或 Office 365 中用与接受的域相匹配的主题名称配置的证书。</span><span class="sxs-lookup"><span data-stu-id="deff9-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="deff9-154">我们建议证书的公用名或者使用者备用名称与您组织的主 SMTP 域相匹配。</span><span class="sxs-lookup"><span data-stu-id="deff9-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="deff9-155">有关详细信息，请参阅[本地电子邮件环境](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment)的必备组件。</span><span class="sxs-lookup"><span data-stu-id="deff9-155">For details, see [Prerequisites for your on-premises email environment](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="deff9-156">- 或者 -</span><span class="sxs-lookup"><span data-stu-id="deff9-156">-OR-</span></span>

   - <span data-ttu-id="deff9-157">确保所有组织发件人域和子域配置为 Microsoft 365 或 Office 365 中的接受域。</span><span class="sxs-lookup"><span data-stu-id="deff9-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="deff9-158">有关定义接受域的详细信息，请参阅[在 Exchange Online 中管理接受的域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 和 [在 Exchange Online 中为子域启用邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。</span><span class="sxs-lookup"><span data-stu-id="deff9-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="deff9-159">确定是否希望使用邮件流规则（也称为传输规则）或域名将邮件从 Microsoft 365 或 Office 365 传递到你的电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="deff9-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="deff9-160">大多数企业都会选择针对所有接受的域传递邮件。</span><span class="sxs-lookup"><span data-stu-id="deff9-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="deff9-161">有关详细信息，请参阅[方案： Exchange Online 中的条件邮件路由](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)。</span><span class="sxs-lookup"><span data-stu-id="deff9-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="deff9-162">可按照 [Exchange Online 中邮件流规则操作](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)中所述设置邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="deff9-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="deff9-163">例如，如果当前你的邮件通过通讯组列表定向到多个站点，那么你不妨结合使用邮件流规则和连接器。</span><span class="sxs-lookup"><span data-stu-id="deff9-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="deff9-164">2. 设置从 Microsoft 365 或 Office 365 指向你的电子邮件服务器的连接器</span><span class="sxs-lookup"><span data-stu-id="deff9-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="deff9-165">若要在 Microsoft 365 或 Office 365 中创建连接器，单击" **管理**"，然后单击" **Exchange**"转到 Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="deff9-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="deff9-166">接下来，依次单击 **“邮件流”** 和 **“连接器”**。</span><span class="sxs-lookup"><span data-stu-id="deff9-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="deff9-167">使用向导设置连接器。</span><span class="sxs-lookup"><span data-stu-id="deff9-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="deff9-168">若要启动向导，请单击加号“+”**+**。</span><span class="sxs-lookup"><span data-stu-id="deff9-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="deff9-169">在第一个屏幕上，选择 **从** Office 365 和 **至** 组织邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="deff9-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="deff9-170">单击“下一步”，然后按照向导中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="deff9-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="deff9-171">如需了解详细信息，请单击“帮助”或“了解详情”链接。</span><span class="sxs-lookup"><span data-stu-id="deff9-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="deff9-172">此向导会指导您逐步完成设置。</span><span class="sxs-lookup"><span data-stu-id="deff9-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="deff9-173">结束时，请务必验证您的连接器。</span><span class="sxs-lookup"><span data-stu-id="deff9-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="deff9-174">如果您无法验证此连接器，请双击所显示的消息了解详细信息，并参阅[验证服务器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)了解如何解决问题。</span><span class="sxs-lookup"><span data-stu-id="deff9-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="deff9-175">步骤 7：更新 DNS 托管提供商处的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="deff9-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="deff9-176">登录到 DNS 托管提供商的网站，然后按照[添加 DNS 记录以连接你的域](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="deff9-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="deff9-177">**注意以下两项例外：**</span><span class="sxs-lookup"><span data-stu-id="deff9-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="deff9-178">请勿创建新 MX 记录或更改现有 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="deff9-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="deff9-179">如果你已经有了上一个电子邮件提供商的发件人策略框架 (SPF) 记录，请不要为 Exchange Online 创建新 SPF (TXT) 记录，而是向当前 TXT 记录添加“include:spf.protection.outlook.com”。</span><span class="sxs-lookup"><span data-stu-id="deff9-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="deff9-180">例如，"v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="deff9-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="deff9-181">如果你还没有 SPF 记录，请修改 Microsoft 365 推荐的 SPF 记录，以包括你的当前电子邮件提供商的域并添加 protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="deff9-181">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="deff9-182">这样将为来自这两个电子邮件系统的传出邮件授权。</span><span class="sxs-lookup"><span data-stu-id="deff9-182">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="deff9-183">步骤 8：在当前提供商处设置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="deff9-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="deff9-184">在当前电子邮件提供商处，将用户电子邮件帐户的转发设置为你的 onmicrosoft.com 域：</span><span class="sxs-lookup"><span data-stu-id="deff9-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="deff9-185">将用户 A 邮箱转发到 usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="deff9-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="deff9-186">将用户 B 邮箱转发到 userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="deff9-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="deff9-187">完成此步骤后，所有发送到 usera@yourcompany.com 和 userb@yourcompany.com 的电子邮件均可在 Microsoft 365 中使用。</span><span class="sxs-lookup"><span data-stu-id="deff9-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="deff9-188">有关如何设置邮件转发的确切步骤，请联系你当前的电子邮件提供商。</span><span class="sxs-lookup"><span data-stu-id="deff9-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="deff9-189">无需在当前电子邮件提供商处保留邮件副本。</span><span class="sxs-lookup"><span data-stu-id="deff9-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="deff9-190">大多数提供商在转发电子邮件时会保留发件人的答复地址，所以答复会发送给原始发件人。</span><span class="sxs-lookup"><span data-stu-id="deff9-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="deff9-191">步骤 9：测试邮件流</span><span class="sxs-lookup"><span data-stu-id="deff9-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="deff9-192">使用用户 A 的凭据登录 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="deff9-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="deff9-193">执行以下测试：</span><span class="sxs-lookup"><span data-stu-id="deff9-193">Perform these tests:</span></span>

    - <span data-ttu-id="deff9-194">通过向用户 B 发送电子邮件来测试本地 Microsoft 电子邮件。该电子邮件将立即送达。</span><span class="sxs-lookup"><span data-stu-id="deff9-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="deff9-195">在此方案中，该邮件不会路由到原始服务器上用户 B 的邮箱，因为 Microsoft 365 邮箱是本地的。</span><span class="sxs-lookup"><span data-stu-id="deff9-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="deff9-196">通过发送电子邮件（例如，发送给用户 C）来测试在现有电子邮件系统上向用户发送的电子邮件。该电子邮件将传送到原始邮件服务器上用户 C 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="deff9-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="deff9-197">验证是否从外部帐户或现有电子邮件系统上的员工电子邮件帐户正确设置了转发。</span><span class="sxs-lookup"><span data-stu-id="deff9-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="deff9-198">例如，从用户 C 的原始服务器帐户或 Hotmail 帐户向用户 A 发送一封电子邮件，并验证电子邮件是否到达用户 A 的 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="deff9-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="deff9-199">步骤 10：移动邮箱内容</span><span class="sxs-lookup"><span data-stu-id="deff9-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="deff9-200">因为你仅移动两个测试用户，并且用户 A 和用户 B 都在使用Outlook，因此可以通过在新的 Outlook 配置文件中打开旧的 .PST 文件并复制邮件、日历项、联系人等来移动电子邮件。</span><span class="sxs-lookup"><span data-stu-id="deff9-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="deff9-201">有关更多信息，请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。</span><span class="sxs-lookup"><span data-stu-id="deff9-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="deff9-202">将项目导入到 Microsoft 365 邮箱中的适当位置后，可以从任何位置的任何设备访问这些项目。</span><span class="sxs-lookup"><span data-stu-id="deff9-202">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

