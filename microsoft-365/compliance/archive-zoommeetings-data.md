---
title: 设置连接器以存档 Microsoft 365 中的缩放会议数据
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
description: 管理员可以将连接器设置为将数据从 Globanet Zoom 会议导入到 Microsoft 365。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: ef153ec0a14a257f1f46b011e4c15d2b3b704ed3
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408940"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a><span data-ttu-id="aca30-104">设置连接器以存档缩放会议数据</span><span class="sxs-lookup"><span data-stu-id="aca30-104">Set up a connector to archive Zoom Meetings data</span></span>

<span data-ttu-id="aca30-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将数据从缩放会议导入到 Microsoft 365 组织中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="aca30-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Zoom Meetings to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="aca30-106">Globanet 提供了一个 [缩放会议](https://globanet.com/zoom/) 连接器，该连接器配置为定期捕获第三方数据源中的项目 () 并将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="aca30-106">Globanet provides a [Zoom Meetings](https://globanet.com/zoom/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="aca30-107">连接器将会议的内容 (（包括聊天、录制的文件和元) 数据）从 "缩放会议" 帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的 "用户邮箱" 中。</span><span class="sxs-lookup"><span data-stu-id="aca30-107">The connector converts the content of the meetings (including chats, recorded files, and metadata) from the Zoom Meetings account to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="aca30-108">将 "缩放会议" 数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="aca30-108">After Zoom Meetings data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="aca30-109">使用缩放会议连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和管理法规策略。</span><span class="sxs-lookup"><span data-stu-id="aca30-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-meetings-data"></a><span data-ttu-id="aca30-110">存档缩放会议数据概述</span><span class="sxs-lookup"><span data-stu-id="aca30-110">Overview of archiving Zoom Meetings data</span></span>

<span data-ttu-id="aca30-111">以下概述介绍了使用连接器在 Microsoft 365 中存档缩放会议数据的过程。</span><span class="sxs-lookup"><span data-stu-id="aca30-111">The following overview explains the process of using a connector to archive Zoom Meetings data in Microsoft 365.</span></span>

![缩放会议存档工作流](../media/ZoomMeetingsConnectorWorkflow.png)

1. <span data-ttu-id="aca30-113">您的组织可以使用缩放会议来设置和配置缩放会议网站。</span><span class="sxs-lookup"><span data-stu-id="aca30-113">Your organization works with Zoom Meetings to set up and configure a Zoom Meetings site.</span></span>

2. <span data-ttu-id="aca30-114">每24小时一次，来自缩放会议的会议项目将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="aca30-114">Once every 24 hours, meeting items from Zoom Meetings are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="aca30-115">连接器还将会议的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="aca30-115">The connector also converts the content of the meetings to an email message format.</span></span>

3. <span data-ttu-id="aca30-116">您在 Microsoft 365 合规中心中创建的缩放会议连接器每天连接到 Globanet Merge1，并将会议邮件传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="aca30-116">The Zoom Meetings connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the meeting messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="aca30-117">连接器使用 *电子邮件* 属性和自动用户映射的值将已转换的会议项目导入到特定用户的邮箱中，如步骤3中所述。</span><span class="sxs-lookup"><span data-stu-id="aca30-117">The connector imports the converted meeting items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="aca30-118">在用户邮箱中创建名为 " **缩放会议** " 的 "收件箱" 文件夹中的新子文件夹，并将会议项目导入该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="aca30-118">A new subfolder in the Inbox folder named **Zoom Meetings** is created in user mailboxes, and the meeting items are imported to that folder.</span></span> <span data-ttu-id="aca30-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="aca30-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="aca30-120">每个会议项目都包含此属性，该属性填充会议的每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aca30-120">Every meeting item contains this property, which is populated with the email address of every participant of the meeting.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="aca30-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="aca30-121">Before you begin</span></span>

- <span data-ttu-id="aca30-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="aca30-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="aca30-123">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="aca30-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="aca30-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="aca30-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="aca30-125">获取组织的缩放企业帐户或缩放企业帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="aca30-125">Obtain the username and password for your organization's Zoom Business or Zoom Enterprise account.</span></span> <span data-ttu-id="aca30-126">配置缩放会议连接器时，您需要登录到步骤2中的此帐户。</span><span class="sxs-lookup"><span data-stu-id="aca30-126">You'll need to sign into this account in Step 2 when you configure the Zoom Meetings connector.</span></span>

- <span data-ttu-id="aca30-127">在 [缩放 Marketplace](https://marketplace.zoom.us)中创建以下应用程序：</span><span class="sxs-lookup"><span data-stu-id="aca30-127">Create the following applications in the [Zoom Marketplace](https://marketplace.zoom.us):</span></span>

  - <span data-ttu-id="aca30-128">OAuth 应用程序</span><span class="sxs-lookup"><span data-stu-id="aca30-128">OAuth application</span></span>

  - <span data-ttu-id="aca30-129">JWT 应用程序</span><span class="sxs-lookup"><span data-stu-id="aca30-129">JWT application</span></span>

  <span data-ttu-id="aca30-130">创建这些应用程序后，缩放平台将生成一组用于生成令牌的唯一凭据。</span><span class="sxs-lookup"><span data-stu-id="aca30-130">After you create these applications, the Zoom platform generates a set of unique credentials used to generate the tokens.</span></span> <span data-ttu-id="aca30-131">当连接到缩放帐户并将项目复制到 Merge1 站点时，这些令牌用于对连接器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="aca30-131">These tokens are used to authenticate the connector when it connects to your Zoom account and copies items to the Merge1 site.</span></span> <span data-ttu-id="aca30-132">当您在步骤2中配置缩放连接器时，将使用这些令牌。</span><span class="sxs-lookup"><span data-stu-id="aca30-132">You will use these tokens when you configure the Zoom connector in Step 2.</span></span>

  <span data-ttu-id="aca30-133">有关如何创建 OAuth 和 JWT 应用程序的分步说明，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="aca30-133">For step-by step instructions on how to create the OAuth and JWT applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="aca30-134">在步骤1中创建缩放会议连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="aca30-134">The user who creates the Zoom Meetings connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="aca30-135">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="aca30-135">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="aca30-136">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="aca30-136">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="aca30-137">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="aca30-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="aca30-138">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="aca30-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="aca30-139">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="aca30-139">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-zoom-meetings-connector"></a><span data-ttu-id="aca30-140">步骤1：设置缩放会议连接器</span><span class="sxs-lookup"><span data-stu-id="aca30-140">Step 1: Set up the Zoom Meetings connector</span></span>

<span data-ttu-id="aca30-141">第一步是访问 Microsoft 365 合规性中心中的 **数据连接器** ，并创建一个缩放会议连接器。</span><span class="sxs-lookup"><span data-stu-id="aca30-141">The first step is to access the **Data Connectors** in the Microsoft 365 compliance center and create a Zoom Meetings connector.</span></span>

1. <span data-ttu-id="aca30-142">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**" "  >  **缩放会议**"。</span><span class="sxs-lookup"><span data-stu-id="aca30-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Zoom Meetings**.</span></span>

2. <span data-ttu-id="aca30-143">在 " **缩放会议** 产品说明" 页上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="aca30-143">On the **Zoom Meetings** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="aca30-144">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="aca30-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="aca30-145">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="aca30-145">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="aca30-146">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="aca30-146">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-zoom-meetings-connector"></a><span data-ttu-id="aca30-147">步骤2：配置缩放会议连接器</span><span class="sxs-lookup"><span data-stu-id="aca30-147">Step 2: Configure the Zoom Meetings connector</span></span>

<span data-ttu-id="aca30-148">第二步是在 Merge1 网站上配置缩放会议连接器。</span><span class="sxs-lookup"><span data-stu-id="aca30-148">The second step is to configure the Zoom Meetings connector on the Merge1 site.</span></span> <span data-ttu-id="aca30-149">有关如何在 Globanet Merge1 网站上配置缩放会议连接器的详细信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="aca30-149">For more information about how to configure the Zoom Meetings connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="aca30-150">单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="aca30-150">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="aca30-151">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="aca30-151">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="aca30-152">在 "将 **外部用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="aca30-152">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="aca30-153">"缩放会议项目" 包含一个名为 *电子邮件* 的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="aca30-153">Zoom Meetings items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="aca30-154">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="aca30-154">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox</span></span>

2. <span data-ttu-id="aca30-155">在 " **管理员同意** " 页上，单击 " **提供同意**"。</span><span class="sxs-lookup"><span data-stu-id="aca30-155">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="aca30-156">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="aca30-156">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="aca30-157">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="aca30-157">Click **Accept** to provide the consent.</span></span>
  
   <span data-ttu-id="aca30-158">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="aca30-158">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="aca30-159">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="aca30-159">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="aca30-160">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="aca30-160">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="aca30-161">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="aca30-161">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-zoom-meetings-connector"></a><span data-ttu-id="aca30-162">步骤4：监视缩放会议连接器</span><span class="sxs-lookup"><span data-stu-id="aca30-162">Step 4: Monitor the Zoom Meetings connector</span></span>

<span data-ttu-id="aca30-163">创建缩放会议连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="aca30-163">After you create the Zoom Meetings connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="aca30-164">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="aca30-164">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="aca30-165">单击 " **连接器** " 选项卡，然后选择 " **缩放会议** 连接器" 以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="aca30-165">Click the **Connectors** tab and then select the **Zoom Meetings** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="aca30-166">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="aca30-166">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="aca30-167">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="aca30-167">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="aca30-168">已知问题</span><span class="sxs-lookup"><span data-stu-id="aca30-168">Known issues</span></span>

- <span data-ttu-id="aca30-169">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="aca30-169">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="aca30-170">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="aca30-170">Support for larger items will be available at a later date.</span></span>

- <span data-ttu-id="aca30-171">若要使缩放会议连接器正常工作，必须在设置缩放会议时启用录制。</span><span class="sxs-lookup"><span data-stu-id="aca30-171">For the Zoom Meetings connector to work, you must enable recordings when setting up Zoom Meetings.</span></span>
