---
title: 在 Microsoft 365 中设置用于存档 .EML 数据的连接器
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
description: 管理员可以将连接器设置为将 .EML 数据从 Globanet 导入并存档到 Microsoft 365。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 9a2b473f258973dcbe9cb0e6a155671c80b1f552
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47362063"
---
# <a name="set-up-a-connector-to-archive-eml-data-preview"></a><span data-ttu-id="bc35b-104">设置连接器以存档 .EML 数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="bc35b-104">Set up a connector to archive EML data (preview)</span></span>

<span data-ttu-id="bc35b-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将 .EML 数据导入到 Microsoft 365 组织中的用户邮箱并将其存档。</span><span class="sxs-lookup"><span data-stu-id="bc35b-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive EML data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="bc35b-106">.EML 是保存到文件的电子邮件的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="bc35b-106">EML is the file extension for an email message saved to a file.</span></span> <span data-ttu-id="bc35b-107">连接器将项的内容从源格式转换为电子邮件格式，然后将该项目导入到用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="bc35b-107">The connector converts the content of an item from the source format to an email message format and then imports the item to a user mailbox.</span></span>

<span data-ttu-id="bc35b-108">在将 .EML 邮件存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="bc35b-108">After EML messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="bc35b-109">使用您在 Microsoft 365 中导入和存档数据的 .EML 连接器可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="bc35b-109">Using an EML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-eml-data"></a><span data-ttu-id="bc35b-110">存档 .EML 数据概述</span><span class="sxs-lookup"><span data-stu-id="bc35b-110">Overview of archiving EML data</span></span>

<span data-ttu-id="bc35b-111">以下概述说明了使用连接器在 Microsoft 365 中存档 .EML 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="bc35b-111">The following overview explains the process of using a connector to archive EML data in Microsoft 365.</span></span>

![对 .EML 数据的存档工作流](../media/EMLConnectorWorkflow.png)

1. <span data-ttu-id="bc35b-113">您的组织与 .EML 源协同工作以设置和配置 .EML 网站。</span><span class="sxs-lookup"><span data-stu-id="bc35b-113">Your organization works with the EML source to set up and configure an EML site.</span></span>

2. <span data-ttu-id="bc35b-114">每24小时一次，将 .EML 源中的内容项复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="bc35b-114">Once every 24 hours, content items from the EML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="bc35b-115">在此过程中，将 .EML 文件的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="bc35b-115">During this process, the content of an EML file is converted to an email message format.</span></span>

3. <span data-ttu-id="bc35b-116">您在 Microsoft 365 合规中心中创建的 .EML 连接器每天连接到 Globanet Merge1 网站，并将邮件传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="bc35b-116">The EML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="bc35b-117">连接器使用[步骤 3](#step-3-map-users-and-complete-the-connector-setup)中所述的自动用户映射过程的*电子邮件*属性的值，将已转换的邮件项导入到特定用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="bc35b-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping process that's described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="bc35b-118">在此过程中，将在用户邮箱中创建名为 " **.eml**" 的 "收件箱" 文件夹中的子文件夹，并将 .eml 项目导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="bc35b-118">During this process, a subfolder in the Inbox folder named **EML**is created in the user mailboxes, and the EML items are imported to that folder.</span></span> <span data-ttu-id="bc35b-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="bc35b-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="bc35b-120">每封邮件都包含此属性，该属性由内容项目的每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="bc35b-120">Every message contains this property, which is populated with the email address of every participant of the content item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bc35b-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="bc35b-121">Before you begin</span></span>

- <span data-ttu-id="bc35b-122">通过接受您的 .EML 连接器的条款和条件创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="bc35b-122">Create a Globanet Merge1 account by accepting the terms and conditions for an EML connector.</span></span> <span data-ttu-id="bc35b-123">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/contact-us)。</span><span class="sxs-lookup"><span data-stu-id="bc35b-123">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="bc35b-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="bc35b-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="bc35b-125">在步骤1中创建 .EML 连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="bc35b-125">The user who creates the EML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="bc35b-126">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="bc35b-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="bc35b-127">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="bc35b-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="bc35b-128">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="bc35b-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="bc35b-129">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="bc35b-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="bc35b-130">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="bc35b-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-eml-connector"></a><span data-ttu-id="bc35b-131">步骤1：设置 .EML 连接器</span><span class="sxs-lookup"><span data-stu-id="bc35b-131">Step 1: Set up an EML Connector</span></span>

<span data-ttu-id="bc35b-132">第一步是访问 Microsoft 365 合规性中心中的 " **数据连接器** " 页，并为您的 .eml 数据创建一个连接器。</span><span class="sxs-lookup"><span data-stu-id="bc35b-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for EML data.</span></span>

1. <span data-ttu-id="bc35b-133">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**  >  **.eml**"。</span><span class="sxs-lookup"><span data-stu-id="bc35b-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **EML**.</span></span>

2. <span data-ttu-id="bc35b-134">在 " **.eml** 产品说明" 页上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="bc35b-134">On the **EML** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="bc35b-135">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="bc35b-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="bc35b-136">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bc35b-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="bc35b-137">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="bc35b-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="bc35b-138">步骤2：在 Globanet Merge1 网站上配置 .EML 连接器</span><span class="sxs-lookup"><span data-stu-id="bc35b-138">Step 2: Configure the EML connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="bc35b-139">第二步是在 Globanet Merge1 网站上配置 .EML 连接器。</span><span class="sxs-lookup"><span data-stu-id="bc35b-139">The second step is to configure the EML connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="bc35b-140">有关配置 .EML 连接器的详细信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="bc35b-140">For information about configuring  the EML connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="bc35b-141">单击 " **保存" & "完成**" 后，将返回到 Microsoft 365 合规性中心，再到 "连接器向导" 的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="bc35b-141">After you click **Save & Finish**, you are returned to the Microsoft 365 compliance center, to the **User mapping** page of the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="bc35b-142">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="bc35b-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="bc35b-143">若要映射用户并完成 Microsoft 365 合规性中心中设置的连接器，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bc35b-143">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="bc35b-144">在 "将 **外部用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="bc35b-144">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="bc35b-145">.EML 源项目包含一个名为 *Email*的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bc35b-145">The EML source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="bc35b-146">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将 .EML 项目导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="bc35b-146">If the connector can associate this address with a Microsoft 365 user, the EML items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="bc35b-147">在 " **管理员同意** " 页面上，单击 " **提供同意** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="bc35b-147">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="bc35b-148">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="bc35b-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="bc35b-149">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="bc35b-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="bc35b-150">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="bc35b-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="bc35b-151">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="bc35b-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="bc35b-152">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="bc35b-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="bc35b-153">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="bc35b-153">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-eml-connector"></a><span data-ttu-id="bc35b-154">步骤4：监视 .EML 连接器</span><span class="sxs-lookup"><span data-stu-id="bc35b-154">Step 4: Monitor the EML connector</span></span>

<span data-ttu-id="bc35b-155">创建 .EML 连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="bc35b-155">After you create the EML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="bc35b-156">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="bc35b-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="bc35b-157">单击 " **连接器** " 选项卡，然后选择 " **.eml** 连接器" 以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="bc35b-157">Click the **Connectors** tab and then select the **EML** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="bc35b-158">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="bc35b-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="bc35b-159">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="bc35b-159">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="bc35b-160">已知问题</span><span class="sxs-lookup"><span data-stu-id="bc35b-160">Known issues</span></span>

- <span data-ttu-id="bc35b-161">目前，我们不支持导入大于 10 MB 的附件，但稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="bc35b-161">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
