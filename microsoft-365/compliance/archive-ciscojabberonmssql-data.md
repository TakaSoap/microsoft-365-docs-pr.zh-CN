---
title: 在 Microsoft 365 中设置连接器以存档 Cisco Jabber on MS SQL 数据
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
description: 管理员可以设置连接器，以便在 Microsoft 365 中从 Globanet 导入和存档 Cisco Jabber 数据。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据，因此您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: c87449c35d588fd886d9d108f136eea0a4799ccf
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409102"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data-preview"></a><span data-ttu-id="a5186-104">设置连接器以存档 Cisco Jabber 数据 (preview) </span><span class="sxs-lookup"><span data-stu-id="a5186-104">Set up a connector to archive Cisco Jabber data (preview)</span></span>

<span data-ttu-id="a5186-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将数据从 Cisco Jabber 平台导入并存档到 Microsoft 365 组织中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="a5186-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="a5186-106">Globanet 为您提供了一个 [Cisco Jabber](https://globanet.com/jabber/) 连接器，该连接器配置为从 JABBER 的 MS SQL 数据库捕获项目，如1:1 聊天消息和组聊天，然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a5186-106">Globanet provides you with a [Cisco Jabber](https://globanet.com/jabber/) connector that is configured to capture items from the Jabber’s MS SQL database, such as 1:1 chat messages and group chats and then import those items to Microsoft 365.</span></span> <span data-ttu-id="a5186-107">连接器检索 Cisco Jabber 的 MS SQL 数据库中的数据，并对其进行处理，并将内容从用户的 Cisco Jabber 帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="a5186-107">The connector retrieves data from the Cisco Jabber’s MS SQL database, processes it, and the converts the content from a user's Cisco Jabber account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="a5186-108">在将 Cisco Jabber 数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="a5186-108">After Cisco Jabber data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="a5186-109">使用 Cisco Jabber 连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="a5186-109">Using a Cisco Jabber connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-data"></a><span data-ttu-id="a5186-110">存档 Cisco Jabber 数据概述</span><span class="sxs-lookup"><span data-stu-id="a5186-110">Overview of archiving Cisco Jabber data</span></span>

<span data-ttu-id="a5186-111">以下概述说明了使用连接器在 Microsoft 365 中存档 Cisco Jabber 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="a5186-111">The following overview explains the process of using a connector to archive Cisco Jabber data in Microsoft 365.</span></span>

![Cisco Jabber 数据的存档工作流](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. <span data-ttu-id="a5186-113">您的组织与 Cisco 合作，在 MS SQL 数据库上设置和配置 Cisco Jabber。</span><span class="sxs-lookup"><span data-stu-id="a5186-113">Your organization works with Cisco to set up and configure a Cisco Jabber on MS SQL database.</span></span>

2. <span data-ttu-id="a5186-114">每24小时一次，Cisco Jabber 项目都将从 MS SQL 数据库复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="a5186-114">Once every 24 hours, Cisco Jabber items are copied from the MS SQL database to the Globanet Merge1 site.</span></span> <span data-ttu-id="a5186-115">连接器还将聊天消息的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="a5186-115">The connector also converts the content of chat messages to an email message format.</span></span>

3. <span data-ttu-id="a5186-116">您在 Microsoft 365 合规性中心中创建的 Cisco Jabber 连接器每天连接到 Globanet Merge1 网站，并将项目传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="a5186-116">The Cisco Jabber connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="a5186-117">自动用户映射作为连接器使用[步骤 3](#step-3-map-users-and-complete-the-connector-setup)中所述的*Email*属性的值将项目导入特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a5186-117">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="a5186-118">在用户邮箱中创建名为 " **Cisco Jabber** " 的 "收件箱" 文件夹中的子文件夹，并将邮件项目导入该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a5186-118">A subfolder in the Inbox folder named **Cisco Jabber on MS SQL** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="a5186-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="a5186-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="a5186-120">每个 Cisco Jabber 项都包含此属性，该属性填充了邮件的每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a5186-120">Every Cisco Jabber item contains this property, which is populated with the email address of every participant of the messages.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a5186-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="a5186-121">Before you begin</span></span>

- <span data-ttu-id="a5186-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="a5186-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="a5186-123">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact/)。</span><span class="sxs-lookup"><span data-stu-id="a5186-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="a5186-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="a5186-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="a5186-125">在步骤1中创建连接器之前，必须设置 MS SQL 数据库以检索 Jabber 项目。</span><span class="sxs-lookup"><span data-stu-id="a5186-125">You must set up an MS SQL database to retrieve Jabber items from before creating the connector in Step 1.</span></span> <span data-ttu-id="a5186-126">在步骤2中配置 Cisco Jabber 连接器时，您将指定 MS SQL 数据库的连接设置。</span><span class="sxs-lookup"><span data-stu-id="a5186-126">You will specify the connection settings for the MS SQL database when configuring the Cisco Jabber connector in Step 2.</span></span> <span data-ttu-id="a5186-127">有关详细信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="a5186-127">For more information, see the [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="a5186-128">在步骤1中创建 Cisco Jabber 连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="a5186-128">The user who creates the Cisco Jabber connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a5186-129">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="a5186-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a5186-130">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="a5186-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="a5186-131">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="a5186-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a5186-132">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="a5186-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a5186-133">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="a5186-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-connector"></a><span data-ttu-id="a5186-134">步骤1：设置 Cisco Jabber 连接器</span><span class="sxs-lookup"><span data-stu-id="a5186-134">Step 1: Set up the Cisco Jabber connector</span></span>

<span data-ttu-id="a5186-135">第一步是访问 Microsoft 365 合规性中心中的 **数据连接器** ，并在 MS SQL 数据中为 Cisco Jabber 创建连接器。</span><span class="sxs-lookup"><span data-stu-id="a5186-135">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for Cisco Jabber on MS SQL data.</span></span>

1. <span data-ttu-id="a5186-136">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击**Data connectors**  >  **MS SQL 上的 Data 连接器 Cisco Jabber**。</span><span class="sxs-lookup"><span data-stu-id="a5186-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/)and then click **Data connectors** > **Cisco Jabber on MS SQL**.</span></span>

2. <span data-ttu-id="a5186-137">在 " **Cisco Jabber ON MS SQL** 产品说明" 页面上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="a5186-137">On the **Cisco Jabber on MS SQL** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="a5186-138">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="a5186-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="a5186-139">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a5186-139">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="a5186-140">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="a5186-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="a5186-141">步骤2：在 Globanet Merge1 网站上配置 Cisco Jabber 连接器</span><span class="sxs-lookup"><span data-stu-id="a5186-141">Step 2: Configure the Cisco Jabber connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="a5186-142">第二步是在 Globanet Merge1 站点上配置 MS SQL connector 上的 Cisco Jabber。</span><span class="sxs-lookup"><span data-stu-id="a5186-142">The second step is to configure the Cisco Jabber on MS SQL connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="a5186-143">有关如何在 MS SQL connector 上配置 Cisco Jabber 的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="a5186-143">For information about how to configure the Cisco Jabber on MS SQL connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="a5186-144">单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="a5186-144">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance centre, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="a5186-145">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="a5186-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="a5186-146">若要映射用户并完成 Microsoft 365 合规性中心中设置的连接器，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a5186-146">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="a5186-147">在 "将 **Cisco Jabber 上的 Cisco 用户映射到 Microsoft 365 用户** " 页上的 "启用自动用户映射"。</span><span class="sxs-lookup"><span data-stu-id="a5186-147">On the **Map Cisco Jabber on MS SQL users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="a5186-148">MS SQL 项目上的 Cisco Jabber 包含一个名为 *Email*的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a5186-148">The Cisco Jabber on MS SQL items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="a5186-149">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="a5186-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="a5186-150">在 " **管理员同意** " 页上，单击 " **提供同意**"。</span><span class="sxs-lookup"><span data-stu-id="a5186-150">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="a5186-151">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="a5186-151">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="a5186-152">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="a5186-152">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="a5186-153">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="a5186-153">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="a5186-154">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="a5186-154">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="a5186-155">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="a5186-155">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="a5186-156">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="a5186-156">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-connector"></a><span data-ttu-id="a5186-157">步骤4：监视 Cisco Jabber 连接器</span><span class="sxs-lookup"><span data-stu-id="a5186-157">Step 4: Monitor the Cisco Jabber connector</span></span>

<span data-ttu-id="a5186-158">在 MS SQL 连接器上创建 Cisco Jabber 之后，您可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="a5186-158">After you create the Cisco Jabber on MS SQL connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a5186-159">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="a5186-159">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a5186-160">单击 " **连接器** " 选项卡，然后选择 " **CISCO JABBER on MS SQL** connector" 以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="a5186-160">Click the **Connectors** tab and then select the **Cisco Jabber on MS SQL** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="a5186-161">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="a5186-161">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="a5186-162">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="a5186-162">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a5186-163">已知问题</span><span class="sxs-lookup"><span data-stu-id="a5186-163">Known issues</span></span>

- <span data-ttu-id="a5186-164">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="a5186-164">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="a5186-165">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="a5186-165">Support for larger items will be available at a later date.</span></span>
