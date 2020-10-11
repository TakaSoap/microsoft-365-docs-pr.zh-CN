---
title: 在 Microsoft 365 中设置用于存档网页数据的连接器
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
description: 管理员可以设置连接器，以便在 Microsoft 365 中从 Globanet 导入和存档网页捕获数据。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据，因此您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: b3f622a63e4f4dfe550f481bee6b3a56dfd3bdb1
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409092"
---
# <a name="set-up-a-connector-to-archive-webpage-data-preview"></a><span data-ttu-id="fbd8c-104">设置连接器以存档网页数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="fbd8c-104">Set up a connector to archive webpage data (preview)</span></span>

<span data-ttu-id="fbd8c-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将网页中的数据导入和存档到 Microsoft 365 组织中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from webpages to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="fbd8c-106">Globanet 提供一个 [网页捕获](https://globanet.com/webpage-capture) 连接器，用于捕获特定网站或整个域中) 的特定网页 (和这些页面上的任何链接。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-106">Globanet provides a [Webpage Capture](https://globanet.com/webpage-capture) connector that captures specific webpages (and any links on those pages) in a specific website or an entire domain.</span></span> <span data-ttu-id="fbd8c-107">连接器将网页内容转换为 PDF、PNG 或自定义文件格式，然后将转换后的文件附加到电子邮件，然后将这些电子邮件项目导入到 Microsoft 365 中的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-107">The connector converts the webpage content to a PDF, PNG, or custom file format and then attaches the converted files to an email message and then imports those email items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="fbd8c-108">将网页内容存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-108">After webpage content is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="fbd8c-109">使用网页捕获连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-109">Using a Webpage Capture connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webpage-data"></a><span data-ttu-id="fbd8c-110">存档网页数据概述</span><span class="sxs-lookup"><span data-stu-id="fbd8c-110">Overview of archiving webpage data</span></span>

<span data-ttu-id="fbd8c-111">以下概述介绍了使用连接器在 Microsoft 365 中存档网页内容的过程。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-111">The following overview explains the process of using a connector to archive webpage content in Microsoft 365.</span></span>

![网页数据的存档工作流](../media/WebPageCaptureConnectorWorkflow.png)

1. <span data-ttu-id="fbd8c-113">您的组织与网页源协同工作以设置和配置网页捕获网站。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-113">Your organization works with the webpage source to set up and configure a Webpage Capture site.</span></span>

2. <span data-ttu-id="fbd8c-114">每24小时一次，将网页源项目复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-114">Once every 24 hours, the webpage sources items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="fbd8c-115">连接器还将网页的内容转换为电子邮件并将其附加到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-115">The connector also converts and attaches the content of a webpage to an email message.</span></span>

3. <span data-ttu-id="fbd8c-116">您在 Microsoft 365 合规性中心中创建的网页捕获连接器每天连接到 Globanet Merge1 网站，并将网页项传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-116">The Webpage Capture connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the webpage items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="fbd8c-117">连接器使用自动用户映射的 *电子邮件* 属性的值将转换后的网页项导入到特定用户的邮箱中，如 [步骤 3](#step-3-map-users-and-complete-the-connector-setup)中所述。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-117">The connector imports the converted webpage items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="fbd8c-118">在用户邮箱中创建名为 " **网页捕获** " 的 "收件箱" 文件夹中的子文件夹，并将网页项导入该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-118">A subfolder in the Inbox folder named **Webpage Capture** is created in the user mailboxes, and the webpage items are imported to that folder.</span></span> <span data-ttu-id="fbd8c-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="fbd8c-120">每个网页项都包含此属性，该属性由您在 [步骤 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)中配置网页捕获连接器时提供的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-120">Every webpage item contains this property, which is populated with the email addresses provided when you configure the Webpage Capture connector in [Step 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fbd8c-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="fbd8c-121">Before you begin</span></span>

- <span data-ttu-id="fbd8c-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="fbd8c-123">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact/)。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="fbd8c-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="fbd8c-125">您需要使用 Globanet 支持来设置自定义文件格式，以将网页项转换为。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-125">You need to work with Globanet support to set up a custom file format to convert the webpage items to.</span></span> <span data-ttu-id="fbd8c-126">有关详细信息，请参阅《 Merge1 第三方连接器用户指南》中的。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-126">For more information, see the Merge1 Third-Party Connectors User Guide in</span></span> 

- <span data-ttu-id="fbd8c-127">在步骤1中创建网页捕获连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-127">The user who creates the Webpage Capture connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fbd8c-128">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fbd8c-129">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-129">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fbd8c-130">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fbd8c-131">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fbd8c-132">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webpage-capture-connector"></a><span data-ttu-id="fbd8c-133">步骤1：设置网页捕获连接器</span><span class="sxs-lookup"><span data-stu-id="fbd8c-133">Step 1: Set up the Webpage Capture connector</span></span>

<span data-ttu-id="fbd8c-134">第一步是访问 **数据连接器** 并为网页源数据创建连接器。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-134">The first step is to access to the **Data Connectors** and create a connector for Web Page source data.</span></span>

1. <span data-ttu-id="fbd8c-135">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**  >  **网页捕获**"。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webpage Capture**.</span></span>

2. <span data-ttu-id="fbd8c-136">在 " **网页获取** 产品说明" 页上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-136">On the **Webpage Capture** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="fbd8c-137">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fbd8c-138">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="fbd8c-139">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="fbd8c-140">步骤2：在 Globanet Merge1 网站上配置网页捕获连接器</span><span class="sxs-lookup"><span data-stu-id="fbd8c-140">Step 2: Configure the Webpage Capture connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="fbd8c-141">第二步是在 Globanet Merge1 网站上配置网页捕获连接器。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-141">The second step is to configure the Webpage Capture connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="fbd8c-142">有关如何配置网页捕获连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-142">For information about how to configure the Webpage Capture connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="fbd8c-143">单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-143">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="fbd8c-144">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="fbd8c-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="fbd8c-145">若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fbd8c-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="fbd8c-146">在 "将 **用户捕获到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-146">On the **Map Webpage Capture users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="fbd8c-147">网页捕获项目包含一个名为 " *电子邮件*" 的属性，其中包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-147">The Webpage Capture items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="fbd8c-148">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="fbd8c-149">在 " **管理员同意** " 页上，单击 " **提供同意**"。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-149">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="fbd8c-150">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-150">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="fbd8c-151">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-151">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="fbd8c-152">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-152">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="fbd8c-153">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-153">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="fbd8c-154">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-154">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="fbd8c-155">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-155">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webpage-capture-connector"></a><span data-ttu-id="fbd8c-156">步骤4：监视网页捕获连接器</span><span class="sxs-lookup"><span data-stu-id="fbd8c-156">Step 4: Monitor the Webpage Capture connector</span></span>

<span data-ttu-id="fbd8c-157">创建网页捕获连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-157">After you create the Webpage Capture connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="fbd8c-158">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-158">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="fbd8c-159">单击 " **连接器** " 选项卡，然后选择 **网页捕获** 连接器以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-159">Click the **Connectors** tab and then select the **Webpage Capture** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="fbd8c-160">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-160">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="fbd8c-161">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-161">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fbd8c-162">已知问题</span><span class="sxs-lookup"><span data-stu-id="fbd8c-162">Known issues</span></span>

- <span data-ttu-id="fbd8c-163">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-163">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fbd8c-164">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="fbd8c-164">Support for larger items will be available at a later date.</span></span>
