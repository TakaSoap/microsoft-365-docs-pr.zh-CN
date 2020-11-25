---
title: 在 Microsoft 365 中设置连接器以存档 XIP 源数据
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
description: 管理员可以将连接器设置为将 XIP 源数据从 Globanet 导入和存档到 Microsoft 365。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据。 存档此数据后，您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理第三方数据。
ms.openlocfilehash: 1e2513df8666056f623ef4b5bb42699663d51b64
ms.sourcegitcommit: 95b85a1fdf43e3f0839483fa22e279262703f15f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "49407316"
---
# <a name="set-up-a-connector-to-archive-xip-source-data"></a><span data-ttu-id="fa695-105">设置连接器以存档 XIP 源数据</span><span class="sxs-lookup"><span data-stu-id="fa695-105">Set up a connector to archive XIP source data</span></span>

<span data-ttu-id="fa695-106">使用 Microsoft 365 合规性中心中的 Globanet 连接器将数据从 XIP 源平台导入并存档到 Microsoft 365 组织中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="fa695-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the XIP source platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="fa695-107">Globanet 提供了一个 [XIP](https://globanet.com/xip/) 连接器，允许使用 XIP 文件将项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="fa695-107">Globanet provides a [XIP](https://globanet.com/xip/) connector that allows using an XIP file to import items to Microsoft 365.</span></span> <span data-ttu-id="fa695-108">XIP 文件类似于 ZIP 文件，但允许使用数字签名。</span><span class="sxs-lookup"><span data-stu-id="fa695-108">An XIP file is similar to a ZIP file, but allows for a digital signature to be used.</span></span> <span data-ttu-id="fa695-109">提取 XIP 源文件之前，Globanet Merge 1 将对数字签名进行验证。</span><span class="sxs-lookup"><span data-stu-id="fa695-109">The digital signature is verified by the Globanet Merge 1 before the XIP source file is extracted.</span></span> <span data-ttu-id="fa695-110">连接器将 XIP 源文件中的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="fa695-110">The connector converts the content from the XIP source file to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="fa695-111">将 XIP 源数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="fa695-111">After XIP source data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="fa695-112">使用 XIP 连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="fa695-112">Using an XIP connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-xip-source-data"></a><span data-ttu-id="fa695-113">存档 XIP 源数据概述</span><span class="sxs-lookup"><span data-stu-id="fa695-113">Overview of archiving the XIP source data</span></span>

<span data-ttu-id="fa695-114">以下概述说明使用连接器在 Microsoft 365 中存档 XIP 源数据的过程。</span><span class="sxs-lookup"><span data-stu-id="fa695-114">The following overview explains the process of using a connector to archive the XIP source data in Microsoft 365.</span></span>

![XIP 源数据的存档工作流](../media/XIPConnectorWorkflow.png)

1. <span data-ttu-id="fa695-116">您的组织与 XIP 源协同工作以设置和配置 XIP 网站。</span><span class="sxs-lookup"><span data-stu-id="fa695-116">Your organization works with the XIP source to set up and configure an XIP site.</span></span>

2. <span data-ttu-id="fa695-117">每24小时一次，XIP 源项将被复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="fa695-117">Once every 24 hours, XIP source items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="fa695-118">连接器还会将内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="fa695-118">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="fa695-119">您在 Microsoft 365 合规中心中创建的 XIP 连接器每天连接到 Globanet Merge1 网站，并将邮件传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="fa695-119">The XIP connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="fa695-120">连接器使用自动用户映射的 *电子邮件* 属性的值将已转换的邮件项导入到特定用户的邮箱中，如 [步骤 3](#step-3-map-users-and-complete-the-connector-setup)中所述。</span><span class="sxs-lookup"><span data-stu-id="fa695-120">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="fa695-121">在用户邮箱中创建名为 **XIP** 的 "收件箱" 文件夹中的子文件夹，并将这些项目导入该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fa695-121">A subfolder in the Inbox folder named **XIP** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="fa695-122">连接器通过使用 *Email* 属性的值确定要将项目导入到哪个邮箱。</span><span class="sxs-lookup"><span data-stu-id="fa695-122">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="fa695-123">每个源项目都包含此属性，该属性填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fa695-123">Every source item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fa695-124">准备工作</span><span class="sxs-lookup"><span data-stu-id="fa695-124">Before you begin</span></span>

- <span data-ttu-id="fa695-125">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="fa695-125">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="fa695-126">若要创建帐户，请联系 [Globanet 客户支持](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="fa695-126">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="fa695-127">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="fa695-127">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="fa695-128">在第1步中创建 XIP 连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="fa695-128">The user who creates the XIP connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fa695-129">此角色是在 Microsoft 365 合规性中心中的 "数据连接器" 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="fa695-129">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fa695-130">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="fa695-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fa695-131">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="fa695-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fa695-132">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="fa695-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fa695-133">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="fa695-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-xip-connector"></a><span data-ttu-id="fa695-134">步骤1：设置 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="fa695-134">Step 1: Set up the XIP connector</span></span>

<span data-ttu-id="fa695-135">第一步是访问 Microsoft365 合规性中心中的 " **数据连接器** " 页，并为 XIP 源数据创建一个连接器。</span><span class="sxs-lookup"><span data-stu-id="fa695-135">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the XIP source data.</span></span>

1. <span data-ttu-id="fa695-136">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 " **数据连接器** \> **XIP**"。</span><span class="sxs-lookup"><span data-stu-id="fa695-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **XIP**.</span></span>

2. <span data-ttu-id="fa695-137">在 " **XIP** 产品说明" 页上，单击 " **添加新连接器**"。</span><span class="sxs-lookup"><span data-stu-id="fa695-137">On the **XIP** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="fa695-138">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="fa695-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fa695-139">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fa695-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="fa695-140">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="fa695-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-xip-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="fa695-141">步骤2：在 Globanet Merge1 网站上配置 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="fa695-141">Step 2: Configure the XIP connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="fa695-142">第二步是在 Merge1 网站上配置 XIP 连接器。</span><span class="sxs-lookup"><span data-stu-id="fa695-142">The second step is to configure the XIP connector on the Merge1 site.</span></span> <span data-ttu-id="fa695-143">有关如何配置 XIP 连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="fa695-143">For information about how to configure the XIP connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="fa695-144">单击 " **保存" & 完成** 后，将显示 Microsoft 365 合规性中心的 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="fa695-144">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="fa695-145">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="fa695-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="fa695-146">若要映射用户并完成连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="fa695-146">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="fa695-147">在 "将 **XIP 用户映射到 Microsoft 365 用户** " 页上，启用 "自动用户映射"。</span><span class="sxs-lookup"><span data-stu-id="fa695-147">On the **Map XIP users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="fa695-148">XIP 源项目包含一个名为 *Email* 的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fa695-148">The XIP source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="fa695-149">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="fa695-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="fa695-150">在 " **管理员同意** " 页面上，单击 " **提供同意** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="fa695-150">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="fa695-151">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="fa695-151">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="fa695-152">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="fa695-152">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="fa695-153">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="fa695-153">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="fa695-154">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="fa695-154">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="fa695-155">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="fa695-155">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="fa695-156">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="fa695-156">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xip-connector"></a><span data-ttu-id="fa695-157">步骤4：监视 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="fa695-157">Step 4: Monitor the XIP connector</span></span>

<span data-ttu-id="fa695-158">在创建 XIP 连接器之后，您可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="fa695-158">After you create the XIP connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="fa695-159">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="fa695-159">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="fa695-160">单击 " **连接器** " 选项卡，然后选择 " **XIP** " 连接器以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="fa695-160">Click the **Connectors** tab and then select the **XIP** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="fa695-161">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="fa695-161">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="fa695-162">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="fa695-162">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fa695-163">已知问题</span><span class="sxs-lookup"><span data-stu-id="fa695-163">Known issues</span></span>

- <span data-ttu-id="fa695-164">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="fa695-164">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fa695-165">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="fa695-165">Support for larger items will be available at a later date.</span></span>
