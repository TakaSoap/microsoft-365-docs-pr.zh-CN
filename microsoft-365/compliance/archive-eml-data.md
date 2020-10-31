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
description: 管理员可以将连接器设置为将 .EML 数据从 Globanet 导入并存档到 Microsoft 365。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据。 存档此数据后，您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理第三方数据。
ms.openlocfilehash: edf9673d19340179f992f830da4256556e8d04e5
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816807"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a><span data-ttu-id="58dbd-105">设置连接器以存档 .EML 数据</span><span class="sxs-lookup"><span data-stu-id="58dbd-105">Set up a connector to archive EML data</span></span>

<span data-ttu-id="58dbd-106">使用 Microsoft 365 合规性中心中的 Globanet 连接器将 .EML 数据导入到 Microsoft 365 组织中的用户邮箱并将其存档。</span><span class="sxs-lookup"><span data-stu-id="58dbd-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive EML data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="58dbd-107">.EML 是保存到文件的电子邮件的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="58dbd-107">EML is the file extension for an email message saved to a file.</span></span> <span data-ttu-id="58dbd-108">连接器将项的内容从源格式转换为电子邮件格式，然后将该项目导入到用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="58dbd-108">The connector converts the content of an item from the source format to an email message format and then imports the item to a user mailbox.</span></span>

<span data-ttu-id="58dbd-109">在将 .EML 邮件存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="58dbd-109">After EML messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="58dbd-110">使用您在 Microsoft 365 中导入和存档数据的 .EML 连接器可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="58dbd-110">Using an EML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-eml-data"></a><span data-ttu-id="58dbd-111">存档 .EML 数据概述</span><span class="sxs-lookup"><span data-stu-id="58dbd-111">Overview of archiving EML data</span></span>

<span data-ttu-id="58dbd-112">以下概述说明了使用连接器在 Microsoft 365 中存档 .EML 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="58dbd-112">The following overview explains the process of using a connector to archive EML data in Microsoft 365.</span></span>

![对 .EML 数据的存档工作流](../media/EMLConnectorWorkflow.png)

1. <span data-ttu-id="58dbd-114">您的组织与 .EML 源协同工作以设置和配置 .EML 网站。</span><span class="sxs-lookup"><span data-stu-id="58dbd-114">Your organization works with the EML source to set up and configure an EML site.</span></span>

2. <span data-ttu-id="58dbd-115">每24小时一次，将 .EML 源中的内容项复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="58dbd-115">Once every 24 hours, content items from the EML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="58dbd-116">在此过程中，将 .EML 文件的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="58dbd-116">During this process, the content of an EML file is converted to an email message format.</span></span>

3. <span data-ttu-id="58dbd-117">您在 Microsoft 365 合规中心中创建的 .EML 连接器每天连接到 Globanet Merge1 网站，并将邮件传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="58dbd-117">The EML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="58dbd-118">连接器使用 [步骤 3](#step-3-map-users-and-complete-the-connector-setup)中所述的自动用户映射过程的 *电子邮件* 属性的值，将已转换的邮件项导入到特定用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="58dbd-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping process that's described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="58dbd-119">在此过程中，将在用户邮箱中创建名为 " **.eml** " 的 "收件箱" 文件夹中的子文件夹，并将 .eml 项目导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="58dbd-119">During this process, a subfolder in the Inbox folder named **EML** is created in the user mailboxes, and the EML items are imported to that folder.</span></span> <span data-ttu-id="58dbd-120">连接器通过使用 *Email* 属性的值确定要将项目导入到哪个邮箱。</span><span class="sxs-lookup"><span data-stu-id="58dbd-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="58dbd-121">每封邮件都包含此属性，该属性由内容项目的每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="58dbd-121">Every message contains this property, which is populated with the email address of every participant of the content item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="58dbd-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="58dbd-122">Before you begin</span></span>

- <span data-ttu-id="58dbd-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="58dbd-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="58dbd-124">若要创建帐户，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="58dbd-124">To create an account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="58dbd-125">当您在步骤1中创建连接器时，您将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="58dbd-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="58dbd-126">在步骤1中创建 .EML 连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="58dbd-126">The user who creates the EML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="58dbd-127">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="58dbd-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="58dbd-128">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="58dbd-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="58dbd-129">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="58dbd-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="58dbd-130">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="58dbd-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="58dbd-131">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="58dbd-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-eml-connector"></a><span data-ttu-id="58dbd-132">步骤1：设置 .EML 连接器</span><span class="sxs-lookup"><span data-stu-id="58dbd-132">Step 1: Set up an EML Connector</span></span>

<span data-ttu-id="58dbd-133">第一步是访问 Microsoft 365 合规性中心中的 " **数据连接器** " 页，并为您的 .eml 数据创建一个连接器。</span><span class="sxs-lookup"><span data-stu-id="58dbd-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for EML data.</span></span>

1. <span data-ttu-id="58dbd-134">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 " **数据连接器**  >  **.eml** "。</span><span class="sxs-lookup"><span data-stu-id="58dbd-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **EML** .</span></span>

2. <span data-ttu-id="58dbd-135">在 " **.eml** 产品说明" 页上，单击 " **添加连接器** "。</span><span class="sxs-lookup"><span data-stu-id="58dbd-135">On the **EML** product description page, click **Add connector** .</span></span>

3. <span data-ttu-id="58dbd-136">在 " **服务条款** " 页上，单击 " **接受** "。</span><span class="sxs-lookup"><span data-stu-id="58dbd-136">On the **Terms of service** page, click **Accept** .</span></span>

4. <span data-ttu-id="58dbd-137">输入标识连接器的唯一名称，然后单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="58dbd-137">Enter a unique name that identifies the connector, and then click **Next** .</span></span>

5. <span data-ttu-id="58dbd-138">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="58dbd-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="58dbd-139">步骤2：在 Globanet Merge1 网站上配置 .EML 连接器</span><span class="sxs-lookup"><span data-stu-id="58dbd-139">Step 2: Configure the EML connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="58dbd-140">第二步是在 Globanet Merge1 网站上配置 .EML 连接器。</span><span class="sxs-lookup"><span data-stu-id="58dbd-140">The second step is to configure the EML connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="58dbd-141">有关配置 .EML 连接器的详细信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="58dbd-141">For information about configuring  the EML connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="58dbd-142">单击 " **保存" & 完成** 后，将显示 Microsoft 365 合规性中心的 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="58dbd-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="58dbd-143">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="58dbd-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="58dbd-144">若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="58dbd-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="58dbd-145">在 "将 **外部用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="58dbd-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="58dbd-146">.EML 源项目包含一个名为 *Email* 的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="58dbd-146">The EML source items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="58dbd-147">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将 .EML 项目导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="58dbd-147">If the connector can associate this address with a Microsoft 365 user, the EML items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="58dbd-148">在 " **管理员同意** " 页上，单击 " **提供同意** "。</span><span class="sxs-lookup"><span data-stu-id="58dbd-148">On the **Admin Consent** page, click **Provide Consent** .</span></span> <span data-ttu-id="58dbd-149">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="58dbd-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="58dbd-150">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="58dbd-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="58dbd-151">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="58dbd-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="58dbd-152">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="58dbd-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="58dbd-153">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="58dbd-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="58dbd-154">单击 " **下一步** "，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="58dbd-154">Click **Next** , review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-eml-connector"></a><span data-ttu-id="58dbd-155">步骤4：监视 .EML 连接器</span><span class="sxs-lookup"><span data-stu-id="58dbd-155">Step 4: Monitor the EML connector</span></span>

<span data-ttu-id="58dbd-156">创建 .EML 连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="58dbd-156">After you create the EML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="58dbd-157">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="58dbd-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="58dbd-158">单击 " **连接器** " 选项卡，然后选择 " **.eml** 连接器" 以显示弹出页面。</span><span class="sxs-lookup"><span data-stu-id="58dbd-158">Click the **Connectors** tab and then select the **EML** connector to display the flyout page.</span></span> <span data-ttu-id="58dbd-159">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="58dbd-159">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="58dbd-160">在 " **连接器状态与源** " 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="58dbd-160">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="58dbd-161">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="58dbd-161">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="58dbd-162">已知问题</span><span class="sxs-lookup"><span data-stu-id="58dbd-162">Known issues</span></span>

- <span data-ttu-id="58dbd-163">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="58dbd-163">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="58dbd-164">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="58dbd-164">Support for larger items will be available at a later date.</span></span>
