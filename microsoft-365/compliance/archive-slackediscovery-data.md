---
title: 在 Microsoft 365 中设置指向存档可宽延时间的电子数据展示数据的连接器
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以将连接器设置为将数据从 Globanet 时差电子数据展示导入 Microsoft 365。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据，因此您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 175ce5a5e419d3af621fa9b1eb3d55621314e186
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405573"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data-preview"></a><span data-ttu-id="3d336-104">设置连接器以存档可宽延时间的电子数据展示数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="3d336-104">Set up a connector to archive Slack eDiscovery data (preview)</span></span>

<span data-ttu-id="3d336-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将第三方数据从社交媒体、即时消息和文档协作平台导入并存档到 Microsoft 365 组织中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3d336-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive third-party data from social media, instant messaging, and document collaboration platforms to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="3d336-106">Globanet 提供了一个可宽延时间的电子数据展示连接器，该连接器配置为定期从第三方数据源捕获项目 () 然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3d336-106">Globanet provides a Slack eDiscovery connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="3d336-107">可宽延时间电子数据展示从可宽延时间 API 中提取邮件和文件并将其转换为电子邮件格式，然后将项目导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="3d336-107">Slack eDiscovery pulls messages and files from the Slack API and converts them to an email message format and then imports the item to user mailboxes.</span></span>

<span data-ttu-id="3d336-108">在可宽延时间的电子数据展示数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="3d336-108">After Slack eDiscovery data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="3d336-109">使用可宽延时间的电子数据展示连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="3d336-109">Using a Slack eDiscovery connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-ediscovery-data"></a><span data-ttu-id="3d336-110">存档可宽延的电子数据展示数据概述</span><span class="sxs-lookup"><span data-stu-id="3d336-110">Overview of archiving Slack eDiscovery data</span></span>

<span data-ttu-id="3d336-111">以下概述说明使用连接器在 Microsoft 365 中存档可宽延时间的电子数据展示信息的过程。</span><span class="sxs-lookup"><span data-stu-id="3d336-111">The following overview explains the process of using a connector to archive the Slack eDiscovery information in Microsoft 365.</span></span>

![可宽延电子数据展示存档工作流](../media/SlackeDiscoveryConnectorWorkflow.png)

1. <span data-ttu-id="3d336-113">您的组织使用可宽延时间电子数据展示设置和配置时差电子数据展示网站。</span><span class="sxs-lookup"><span data-stu-id="3d336-113">Your organization works with Slack eDiscovery to set up and configure a Slack eDiscovery site.</span></span>

2. <span data-ttu-id="3d336-114">每24小时一次，从可宽延时间电子数据展示的聊天邮件将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="3d336-114">Once every 24 hours, chat messages from Slack eDiscovery are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="3d336-115">连接器还将聊天消息的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="3d336-115">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="3d336-116">您在 Microsoft 365 合规中心创建的可宽延电子数据展示连接器每天连接到 Globanet Merge1 网站，并将聊天邮件传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="3d336-116">The Slack eDiscovery connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the chat messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="3d336-117">连接器使用 *电子邮件* 属性和自动用户映射的值将转换后的聊天邮件项目导入到特定用户的邮箱中，如步骤3中所述。</span><span class="sxs-lookup"><span data-stu-id="3d336-117">The connector imports the converted chat message items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="3d336-118">在用户邮箱中创建名为 "可 **宽延时间电子数据展示** " 的 "收件箱" 文件夹中的新子文件夹，并将聊天邮件项目导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d336-118">A new subfolder in the Inbox folder named **Slack eDiscovery** is created in the user mailboxes, and the chat message items will be imported to that folder.</span></span> <span data-ttu-id="3d336-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="3d336-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="3d336-120">每个聊天邮件都包含此属性，该属性由聊天消息的每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="3d336-120">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3d336-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="3d336-121">Before you begin</span></span>

- <span data-ttu-id="3d336-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="3d336-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="3d336-123">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="3d336-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="3d336-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="3d336-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="3d336-125">获取组织的可宽延时间企业帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="3d336-125">Obtain the username and password for your organization's Slack enterprise account.</span></span> <span data-ttu-id="3d336-126">在配置可宽延时间电子数据展示时，您需要登录到步骤2中的此帐户。</span><span class="sxs-lookup"><span data-stu-id="3d336-126">You'll need to sign into this account in Step 2 when you configure Slack eDiscovery.</span></span>

- <span data-ttu-id="3d336-127">在步骤1中创建可宽延电子数据展示连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="3d336-127">The user who creates the Slack eDiscovery connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="3d336-128">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="3d336-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3d336-129">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="3d336-129">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="3d336-130">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="3d336-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3d336-131">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="3d336-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="3d336-132">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="3d336-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a><span data-ttu-id="3d336-133">步骤1：设置可宽延时间电子数据展示连接器</span><span class="sxs-lookup"><span data-stu-id="3d336-133">Step 1: Set up the Slack eDiscovery connector</span></span>

<span data-ttu-id="3d336-134">第一步是访问 Microsoft 365 合规性中心中的 " **数据连接器** " 页，并为可宽延性电子数据展示数据创建连接器。</span><span class="sxs-lookup"><span data-stu-id="3d336-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Slack eDiscovery data.</span></span>

1. <span data-ttu-id="3d336-135">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**可  >  **宽延时间" 电子数据展示**。</span><span class="sxs-lookup"><span data-stu-id="3d336-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Slack eDiscovery**.</span></span>

2. <span data-ttu-id="3d336-136">在 " **时差" 电子数据展示** 产品说明页面上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="3d336-136">On the **Slack eDiscovery** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="3d336-137">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="3d336-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="3d336-138">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3d336-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="3d336-139">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="3d336-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-slack-ediscovery"></a><span data-ttu-id="3d336-140">步骤2：配置宽延时间电子数据展示</span><span class="sxs-lookup"><span data-stu-id="3d336-140">Step 2: Configure Slack eDiscovery</span></span>

<span data-ttu-id="3d336-141">第二步是在 Merge1 网站上配置可宽延时间电子数据展示连接器。</span><span class="sxs-lookup"><span data-stu-id="3d336-141">The second step is to configure the Slack eDiscovery connector on the Merge1 site.</span></span> <span data-ttu-id="3d336-142">有关如何在 Globanet Merge1 网站上配置可宽延电子数据展示连接器的详细信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="3d336-142">For more information about how to configure the Slack eDiscovery connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span></span>

<span data-ttu-id="3d336-143">单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="3d336-143">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="3d336-144">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="3d336-144">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="3d336-145">在 "将 **外部用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="3d336-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="3d336-146">可宽延时间的电子数据展示项目包含一个名为 *Email*的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3d336-146">Slack eDiscovery items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="3d336-147">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="3d336-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="3d336-148">在 " **管理员同意** " 页面上，单击 " **提供同意** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="3d336-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="3d336-149">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="3d336-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="3d336-150">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="3d336-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="3d336-151">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="3d336-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="3d336-152">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="3d336-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="3d336-153">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="3d336-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="3d336-154">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="3d336-154">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a><span data-ttu-id="3d336-155">步骤4：监视可宽延时间电子数据展示连接器</span><span class="sxs-lookup"><span data-stu-id="3d336-155">Step 4: Monitor the Slack eDiscovery connector</span></span>

<span data-ttu-id="3d336-156">在创建可宽延时间电子数据展示连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="3d336-156">After you create the Slack eDiscovery connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3d336-157">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="3d336-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3d336-158">单击 " **连接器** " 选项卡，然后选择 "可 **宽延时间电子数据展示** " 连接线以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="3d336-158">Click the **Connectors** tab and then select the **Slack eDiscovery** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="3d336-159">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="3d336-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="3d336-160">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="3d336-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3d336-161">已知问题</span><span class="sxs-lookup"><span data-stu-id="3d336-161">Known issues</span></span>

- <span data-ttu-id="3d336-162">目前，我们不支持导入大于 10 MB 的附件，但稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="3d336-162">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
