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
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186037"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="e6115-103">从我的自定义域试点 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6115-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="e6115-104">可以按照以下要求和限制试用 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="e6115-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="e6115-105">你的当前电子邮件提供商必须提供电子邮件转发功能。</span><span class="sxs-lookup"><span data-stu-id="e6115-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="e6115-106">必须在 DNS 托管提供商处管理 Microsoft 365 DNS记录，而不是让 Microsoft 365 为你管理这些记录。</span><span class="sxs-lookup"><span data-stu-id="e6115-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="e6115-107">要了解更多信息，请参阅[添加 DNS 记录以连接你的域](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="e6115-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="e6115-108">没有其他电子邮件服务器上的用户的忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="e6115-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="e6115-109">管理员无法从单个位置管理所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e6115-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="e6115-110">用户可能无法使用 Microsoft 365 垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="e6115-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="e6115-111">设置 Microsoft 365 试点</span><span class="sxs-lookup"><span data-stu-id="e6115-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="e6115-112">请按照以下步骤设置 Microsoft 365 试点：</span><span class="sxs-lookup"><span data-stu-id="e6115-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="e6115-113">步骤 1：登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="e6115-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e6115-114">使用你的工作或学校帐户登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e6115-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="e6115-115">在左侧导航窗格中，选择“**设置**” > “**域**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="e6115-116">步骤 2：验证你是否拥有要使用的域</span><span class="sxs-lookup"><span data-stu-id="e6115-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="e6115-117">在“**域**”页面上，选择“**添加域**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="e6115-118">在框中键入域名，选择“**使用此域**”，然后选择“**继续**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="e6115-119">选择要在你的域中测试的服务，例如电子邮件和即时消息。</span><span class="sxs-lookup"><span data-stu-id="e6115-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="e6115-120">在“**验证域**”页面上，按照分步说明进行操作，然后选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="e6115-121">DNS 更改需要几分钟到 72 小时才会生效。</span><span class="sxs-lookup"><span data-stu-id="e6115-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="e6115-122">如果验证成功，系统将要求你修改 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="e6115-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="e6115-123">步骤 3：在 Exchange Online 中将域标记为共享</span><span class="sxs-lookup"><span data-stu-id="e6115-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="e6115-124">在 Exchange 管理中心的“**邮件流**”部分，选择“**接受的域**”，然后选择要修改的域。</span><span class="sxs-lookup"><span data-stu-id="e6115-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="e6115-125">双击以打开窗口，然后选择“**内部中继**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="e6115-126">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-126">Select **Save**.</span></span>

    <span data-ttu-id="e6115-127">此设置可能需要几分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="e6115-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="e6115-128">步骤 4：取消阻止现有电子邮件服务器（可选）</span><span class="sxs-lookup"><span data-stu-id="e6115-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="e6115-129">Microsoft 365 使用 Exchange Online Protection (EOP) 进行垃圾邮件防护。</span><span class="sxs-lookup"><span data-stu-id="e6115-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="e6115-130">如果 EOP 检测到当前邮件服务器转发了大量垃圾邮件，它可能会阻止你现有的邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="e6115-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="e6115-131">如果你信任适用于其他电子邮件提供商的垃圾邮件保护，则可以在 Microsoft 365 中取消阻止服务器。</span><span class="sxs-lookup"><span data-stu-id="e6115-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="e6115-132">通过取消阻止现有电子邮件服务器，通过原始服务器送达的任何垃圾邮件都会进入 Microsoft 365 邮箱，而且无法评估 Microsoft 365 防止垃圾邮件的效果。</span><span class="sxs-lookup"><span data-stu-id="e6115-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="e6115-133">在 Exchange 管理中心导航窗格中，选择“**保护**”，然后选择“**连接筛选器**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="e6115-134">在“**IP 允许列表**”中，选择 **+**，然后添加当前电子邮件提供商的邮件服务器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e6115-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="e6115-135">步骤 5：创建用户帐户和设置主答复地址</span><span class="sxs-lookup"><span data-stu-id="e6115-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="e6115-136">在 Microsoft 365 管理中心的左侧窗格，选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="e6115-137">通过添加两个现有用户，创建两个测试帐户。</span><span class="sxs-lookup"><span data-stu-id="e6115-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="e6115-138">对于每个帐户，请选择“**+ 添加用户**”，然后填写所需的信息，包括要测试的密码方法。</span><span class="sxs-lookup"><span data-stu-id="e6115-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="e6115-139">若要确保用户的电子邮件保持不变，“**用户名**”字段必须与用户的当前电子邮件地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="e6115-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="e6115-140">选择相应的许可证，单击“**下一步**”，然后单击“**完成添加**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="e6115-141">在“**用户名**”旁边，从下拉列表中选择你的自定义域名。</span><span class="sxs-lookup"><span data-stu-id="e6115-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="e6115-142">选择“**创建**” > “**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="e6115-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="e6115-143">步骤 6：更新 DNS 托管提供商处的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="e6115-143">Step 6: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="e6115-144">登录到 DNS 托管提供商的网站，然后按照[添加 DNS 记录以连接你的域](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e6115-144">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="e6115-145">**注意以下两项例外：**</span><span class="sxs-lookup"><span data-stu-id="e6115-145">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="e6115-146">请勿创建新 MX 记录或更改现有 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="e6115-146">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="e6115-147">如果你已经有了上一个电子邮件提供商的发件人策略框架 (SPF) 记录，请不要为 Exchange Online 创建新 SPF (TXT) 记录，而是向当前 TXT 记录添加“include:spf.protection.outlook.com”。</span><span class="sxs-lookup"><span data-stu-id="e6115-147">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="e6115-148">例如，"v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="e6115-148">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="e6115-149">如果你还没有 SPF 记录，请修改 Microsoft 365 推荐的 SPF 记录，以包括你的当前电子邮件提供商的域并添加 protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="e6115-149">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="e6115-150">这样将为来自这两个电子邮件系统的传出邮件授权。</span><span class="sxs-lookup"><span data-stu-id="e6115-150">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="e6115-151">步骤 7：在当前提供商处设置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="e6115-151">Step 7: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="e6115-152">在当前电子邮件提供商处，将用户电子邮件帐户的转发设置为你的 onmicrosoft.com 域：</span><span class="sxs-lookup"><span data-stu-id="e6115-152">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="e6115-153">将用户 A 邮箱转发到 usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e6115-153">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="e6115-154">将用户 B 邮箱转发到 userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e6115-154">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="e6115-155">完成此步骤后，所有发送到 usera@yourcompany.com 和 userb@yourcompany.com 的电子邮件均可在 Microsoft 365 中使用。</span><span class="sxs-lookup"><span data-stu-id="e6115-155">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="e6115-156">有关如何设置邮件转发的确切步骤，请联系你当前的电子邮件提供商。</span><span class="sxs-lookup"><span data-stu-id="e6115-156">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="e6115-157">无需在当前电子邮件提供商处保留邮件副本。</span><span class="sxs-lookup"><span data-stu-id="e6115-157">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="e6115-158">大多数提供商在转发电子邮件时会保留发件人的答复地址，所以答复会发送给原始发件人。</span><span class="sxs-lookup"><span data-stu-id="e6115-158">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-8-test-mail-flow"></a><span data-ttu-id="e6115-159">步骤 8：测试邮件流</span><span class="sxs-lookup"><span data-stu-id="e6115-159">Step 8: Test mail flow</span></span>

1. <span data-ttu-id="e6115-160">使用用户 A 的凭据登录 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="e6115-160">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="e6115-161">执行以下测试：</span><span class="sxs-lookup"><span data-stu-id="e6115-161">Perform these tests:</span></span>

    - <span data-ttu-id="e6115-162">通过向用户 B 发送电子邮件来测试本地 Microsoft 电子邮件。该电子邮件将立即送达。</span><span class="sxs-lookup"><span data-stu-id="e6115-162">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="e6115-163">在此方案中，该邮件不会路由到原始服务器上用户 B 的邮箱，因为 Microsoft 365 邮箱是本地的。</span><span class="sxs-lookup"><span data-stu-id="e6115-163">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="e6115-164">通过发送电子邮件（例如，发送给用户 C）来测试在现有电子邮件系统上向用户发送的电子邮件。该电子邮件将传送到原始邮件服务器上用户 C 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e6115-164">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="e6115-165">验证是否从外部帐户或现有电子邮件系统上的员工电子邮件帐户正确设置了转发。</span><span class="sxs-lookup"><span data-stu-id="e6115-165">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="e6115-166">例如，从用户 C 的原始服务器帐户或 Hotmail 帐户向用户 A 发送一封电子邮件，并验证电子邮件是否到达用户 A 的 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="e6115-166">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-9-move-mailbox-contents"></a><span data-ttu-id="e6115-167">步骤 9：移动邮箱内容</span><span class="sxs-lookup"><span data-stu-id="e6115-167">Step 9: Move mailbox contents</span></span>

<span data-ttu-id="e6115-168">因为你仅移动两个测试用户，并且用户 A 和用户 B 都在使用Outlook，因此可以通过在新的 Outlook 配置文件中打开旧的 .PST 文件并复制邮件、日历项、联系人等来移动电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e6115-168">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="e6115-169">有关更多信息，请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)。</span><span class="sxs-lookup"><span data-stu-id="e6115-169">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="e6115-170">将项目导入到 Microsoft 365 邮箱中的适当位置后，可以从任何位置的任何设备访问这些项目。</span><span class="sxs-lookup"><span data-stu-id="e6115-170">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="e6115-171">如果涉及更多邮箱，或者员工未使用 Outlook，则可以使用 Exchange 管理中心中提供的迁移工具。</span><span class="sxs-lookup"><span data-stu-id="e6115-171">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="e6115-172">首先，请转到 Exchange 管理中心，然后按照[将电子邮件从 IMAP 服务器迁移到 Exchange Online 邮箱 – 我们需要新的文章资源]中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e6115-172">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes – we need a new article resource].</span></span>