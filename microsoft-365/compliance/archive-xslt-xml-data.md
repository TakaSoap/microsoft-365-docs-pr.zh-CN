---
title: 在 Microsoft 365 中设置连接器以存档 XSLT/XML 数据
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
description: 管理员可以设置连接器，以便在 Microsoft 365 中从 Globanet 导入和存档 XSLT/XML 数据。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据，因此您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: ac31fa147e19ac0d7f36d31651a8e0b4ec5f359f
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409100"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data-preview"></a><span data-ttu-id="c598e-104">设置连接器以存档 XSLT/XML 数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="c598e-104">Set up a connector to archive XSLT/XML data (preview)</span></span>

<span data-ttu-id="c598e-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将网页源中的数据导入并存档到 Microsoft 365 组织中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="c598e-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Web page source to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c598e-106">Globanet 为您提供 [xslt/XML 连接器](https://globanet.com/xslt-xml) ，该连接器允许快速开发使用 Xslt (可扩展样式表语言转换) 创建的文件，以将 XML 文件转换为其他文件格式 (如可以导入到 Microsoft 365 的 HTML 或文本) ）。</span><span class="sxs-lookup"><span data-stu-id="c598e-106">Globanet provides you with an [XSLT/XML connector](https://globanet.com/xslt-xml) that allows the rapid development of files created by using XSLT (Extensible Style sheet Language Transformations) to transform XML files into other file formats (such as HTML or text) that can be imported to Microsoft 365.</span></span> <span data-ttu-id="c598e-107">连接器将项的内容从 XSLT/XML 源转换为电子邮件格式，然后将转换后的项导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c598e-107">The connector converts the content of an item from the XSLT/XML source to an email message format and then imports the converted item to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="c598e-108">在将 XSLT/XML 数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="c598e-108">After XSLT/XML data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="c598e-109">使用 XSLT/XML 连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="c598e-109">Using an XSLT/XML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-xsltxml-data"></a><span data-ttu-id="c598e-110">存档 XSLT/XML 数据概述</span><span class="sxs-lookup"><span data-stu-id="c598e-110">Overview of archiving XSLT/XML data</span></span>

<span data-ttu-id="c598e-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 XSLT/XML 源数据的过程。</span><span class="sxs-lookup"><span data-stu-id="c598e-111">The following overview explains the process of using a connector to archive XSLT/XML source data in Microsoft 365.</span></span>

![XSLT/XML 数据的存档工作流](../media/XSLT-XMLConnectorWorkflow.png)

1. <span data-ttu-id="c598e-113">您的组织与 XSLT/XML 源配合使用，设置和配置 XSLT/XML 网站。</span><span class="sxs-lookup"><span data-stu-id="c598e-113">Your organization works with the XSLT/XML source to set up and configure an XSLT/XML site.</span></span>

2. <span data-ttu-id="c598e-114">每24小时一次，将 XSLT/XML 源中的聊天消息复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="c598e-114">Once every 24 hours, chat messages from the XSLT/XML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="c598e-115">连接器还会将内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="c598e-115">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="c598e-116">您在 Microsoft 365 合规中心中创建的 XSLT/XML 连接器每天连接到 Globanet Merge1 网站，并将邮件传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="c598e-116">The XSLT/XML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="c598e-117">连接器使用自动用户映射的 *电子邮件* 属性的值将已转换的邮件项导入到特定用户的邮箱中，如步骤3中所述。</span><span class="sxs-lookup"><span data-stu-id="c598e-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="c598e-118">在用户邮箱中创建名为 " **XSLT/XML** " 的 "收件箱" 文件夹中的新子文件夹，并将邮件项目导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="c598e-118">A new subfolder in the Inbox folder named **XSLT/XML** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="c598e-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="c598e-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="c598e-120">每封邮件都包含此属性，该属性由邮件的每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="c598e-120">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c598e-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="c598e-121">Before you begin</span></span>

- <span data-ttu-id="c598e-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="c598e-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="c598e-123">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="c598e-123">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="c598e-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="c598e-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="c598e-125">在步骤1中创建 XSLT/XML 连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="c598e-125">The user who creates the XSLT/XML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c598e-126">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="c598e-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c598e-127">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="c598e-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c598e-128">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="c598e-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c598e-129">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="c598e-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c598e-130">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="c598e-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-xsltxml-connector"></a><span data-ttu-id="c598e-131">步骤1：设置 XSLT/XML 连接器</span><span class="sxs-lookup"><span data-stu-id="c598e-131">Step 1: Set up an XSLT/XML connector</span></span>

<span data-ttu-id="c598e-132">第一步是访问 Microsoft 365 合规性中心中的 **数据连接器** ，并为 XSLT/XML 数据创建连接器。</span><span class="sxs-lookup"><span data-stu-id="c598e-132">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for XSLT/XML data.</span></span>

1. <span data-ttu-id="c598e-133">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**  >  **XSLT/XML**"。</span><span class="sxs-lookup"><span data-stu-id="c598e-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **XSLT/XML**.</span></span>

2. <span data-ttu-id="c598e-134">在 " **XSLT/XML** 产品说明" 页上，单击 " **添加新连接器**"。</span><span class="sxs-lookup"><span data-stu-id="c598e-134">On the **XSLT/XML** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="c598e-135">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="c598e-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="c598e-136">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c598e-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="c598e-137">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="c598e-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-an-xsltxml-connector"></a><span data-ttu-id="c598e-138">步骤2：配置 XSLT/XML 连接器</span><span class="sxs-lookup"><span data-stu-id="c598e-138">Step 2: Configure an XSLT/XML connector</span></span>

<span data-ttu-id="c598e-139">第二步是在 Merge1 网站上配置 XSLT/XML 连接器。</span><span class="sxs-lookup"><span data-stu-id="c598e-139">The second step is to configure the XSLT/XML connector on the Merge1 site.</span></span> <span data-ttu-id="c598e-140">有关如何在 Globanet Merge1 网站上配置 XSLT/XML 连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="c598e-140">For information about how to configure the XSLT/XML connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="c598e-141">单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="c598e-141">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="c598e-142">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="c598e-142">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="c598e-143">若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c598e-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

2. <span data-ttu-id="c598e-144">在 "将 **XSLT/XML 用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="c598e-144">On the **Map XSLT/XML users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="c598e-145">XSLT/XML 项包含一个名为 *Email*的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c598e-145">The XSLT/XML items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="c598e-146">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="c598e-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

3. <span data-ttu-id="c598e-147">在 " **管理员同意** " 页上，单击 " **提供同意**"。</span><span class="sxs-lookup"><span data-stu-id="c598e-147">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="c598e-148">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="c598e-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="c598e-149">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="c598e-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="c598e-150">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="c598e-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="c598e-151">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="c598e-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="c598e-152">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="c598e-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

4. <span data-ttu-id="c598e-153">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="c598e-153">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xsltxml-connector"></a><span data-ttu-id="c598e-154">步骤4：监视 XSLT/XML 连接器</span><span class="sxs-lookup"><span data-stu-id="c598e-154">Step 4: Monitor the XSLT/XML connector</span></span>

<span data-ttu-id="c598e-155">创建 XSLT/XML 连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="c598e-155">After you create the XSLT/XML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="c598e-156">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="c598e-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="c598e-157">单击 " **连接器** " 选项卡，然后选择 " **XSLT/XML** 连接器" 以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="c598e-157">Click the **Connectors** tab and then select the **XSLT/XML** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="c598e-158">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="c598e-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="c598e-159">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="c598e-159">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="c598e-160">已知问题</span><span class="sxs-lookup"><span data-stu-id="c598e-160">Known issues</span></span>

- <span data-ttu-id="c598e-161">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="c598e-161">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="c598e-162">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="c598e-162">Support for larger items will be available at a later date.</span></span>
