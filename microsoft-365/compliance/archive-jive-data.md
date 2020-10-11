---
title: 设置连接器以在 Microsoft 365 中存档 Jive 数据
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
description: 管理员可以设置连接器，以便从 Microsoft 365 中的 Globanet 导入和存档 Jive 数据。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据，因此您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: d04a211e97ddce18165fe62e46f76303b4590524
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409095"
---
# <a name="set-up-a-connector-to-archive-jive-data-preview"></a><span data-ttu-id="92d88-104">设置连接器以存档 Jive 数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="92d88-104">Set up a connector to archive Jive data (preview)</span></span>

<span data-ttu-id="92d88-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将数据从协作平台导入并存档到 Microsoft 365 组织中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="92d88-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="92d88-106">Globanet 提供了一个 [Jive](https://globanet.com/jive/) 连接器，该连接器配置为定期捕获第三方数据源 (中的项目) 然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="92d88-106">Globanet provides a [Jive](https://globanet.com/jive/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="92d88-107">连接器将内容（如电子邮件、聊天和附件）从用户的 Jive 帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="92d88-107">The connector converts content such as email messages, chats, and attachments from a user's Jive account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="92d88-108">在用户邮箱中存储了 Jive 数据之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="92d88-108">After Jive data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="92d88-109">使用 Jive 连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="92d88-109">Using a Jive connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-jive-data"></a><span data-ttu-id="92d88-110">存档 Jive 数据概述</span><span class="sxs-lookup"><span data-stu-id="92d88-110">Overview of archiving Jive data</span></span>

<span data-ttu-id="92d88-111">以下概述说明了使用连接器在 Microsoft 365 中存档 Jive 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="92d88-111">The following overview explains the process of using a connector to archive the Jive data in Microsoft 365.</span></span>

![用于 Jive 数据的存档工作流](../media/JiveConnectorWorkflow.png)

1. <span data-ttu-id="92d88-113">你的组织与 Jive 配合使用来设置和配置 Jive 网站。</span><span class="sxs-lookup"><span data-stu-id="92d88-113">Your organization works with Jive to set up and configure a Jive site.</span></span>

2. <span data-ttu-id="92d88-114">每24小时一次，将 Jive 中的项目复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="92d88-114">Once every 24 hours, items from Jive are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="92d88-115">连接器还将 Jive 项目的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="92d88-115">The connector also converts the content of Jive items to an email message format.</span></span>

3. <span data-ttu-id="92d88-116">您在 Microsoft 365 合规性中心中创建的 Jive 连接器每天连接到 Globanet Merge1 网站，并将内容传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="92d88-116">The Jive connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="92d88-117">连接器使用自动用户映射的 *电子邮件* 属性的值将转换后的项目导入到特定用户的邮箱中，如 [步骤 3](#step-3-map-users-and-complete-the-connector-setup)中所述。</span><span class="sxs-lookup"><span data-stu-id="92d88-117">The connector imports the converted items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="92d88-118">在用户邮箱中创建名为 **Jive** 的 "收件箱" 文件夹中的一个新子文件夹，然后将这些项目导入该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="92d88-118">A new subfolder in the Inbox folder named **Jive** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="92d88-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="92d88-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="92d88-120">每个 Jive 项都包含此属性，该属性用项目的每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="92d88-120">Every Jive item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="92d88-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="92d88-121">Before you begin</span></span>

- <span data-ttu-id="92d88-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="92d88-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="92d88-123">若要执行此操作，请联系 [globanet 客户支持](https://globanet.com/ms-connectors-contact/)。</span><span class="sxs-lookup"><span data-stu-id="92d88-123">To do this, contact [globanet customer support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="92d88-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="92d88-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="92d88-125">在步骤1中创建 Jive 连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="92d88-125">The user who creates the Jive connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="92d88-126">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="92d88-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="92d88-127">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="92d88-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="92d88-128">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="92d88-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="92d88-129">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="92d88-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="92d88-130">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="92d88-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-jive-connector"></a><span data-ttu-id="92d88-131">步骤1：设置 Jive 连接器</span><span class="sxs-lookup"><span data-stu-id="92d88-131">Step 1: Set up the Jive connector</span></span>

<span data-ttu-id="92d88-132">第一步是访问 Microsoft 365 合规性中心中的 " **数据连接器** " 页，并为 Jive 数据创建连接器。</span><span class="sxs-lookup"><span data-stu-id="92d88-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jive data.</span></span>

1. <span data-ttu-id="92d88-133">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**  >  **Jive**"。</span><span class="sxs-lookup"><span data-stu-id="92d88-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Jive**.</span></span>

2. <span data-ttu-id="92d88-134">在 " **Jive** 产品说明" 页上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="92d88-134">On the **Jive** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="92d88-135">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="92d88-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="92d88-136">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="92d88-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="92d88-137">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="92d88-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-jive-connector"></a><span data-ttu-id="92d88-138">步骤2：配置 Jive 连接器</span><span class="sxs-lookup"><span data-stu-id="92d88-138">Step 2: Configure the Jive connector</span></span>

<span data-ttu-id="92d88-139">第二步是在 Merge1 站点上配置 Jive 连接器。</span><span class="sxs-lookup"><span data-stu-id="92d88-139">The second step is to configure the Jive connector on the Merge1 site.</span></span> <span data-ttu-id="92d88-140">有关如何配置 Jive 连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="92d88-140">For information about how to configure the Jive connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf).</span></span>

<span data-ttu-id="92d88-141">单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="92d88-141">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="92d88-142">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="92d88-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="92d88-143">若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="92d88-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="92d88-144">在 "将 **Jive 用户映射到 Microsoft 365 用户** " 页上，启用 "自动用户映射"。</span><span class="sxs-lookup"><span data-stu-id="92d88-144">On the **Map Jive users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="92d88-145">Jive 项包含一个名为 *Email*的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="92d88-145">The Jive items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="92d88-146">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="92d88-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="92d88-147">在 " **管理员同意** " 页上，单击 " **提供同意**"。</span><span class="sxs-lookup"><span data-stu-id="92d88-147">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="92d88-148">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="92d88-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="92d88-149">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="92d88-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="92d88-150">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="92d88-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="92d88-151">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="92d88-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="92d88-152">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="92d88-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="92d88-153">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="92d88-153">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-jive-connector"></a><span data-ttu-id="92d88-154">步骤4：监视 Jive 连接器</span><span class="sxs-lookup"><span data-stu-id="92d88-154">Step 4: Monitor the Jive connector</span></span>

<span data-ttu-id="92d88-155">创建 Jive 连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="92d88-155">After you create the Jive connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="92d88-156">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="92d88-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="92d88-157">单击 " **连接器** " 选项卡，然后选择 " **Jive** 连接器" 以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="92d88-157">Click the **Connectors** tab and then select the **Jive** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="92d88-158">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="92d88-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="92d88-159">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="92d88-159">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="92d88-160">已知问题</span><span class="sxs-lookup"><span data-stu-id="92d88-160">Known issues</span></span>

- <span data-ttu-id="92d88-161">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="92d88-161">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="92d88-162">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="92d88-162">Support for larger items will be available at a later date.</span></span>
