---
title: 设置连接器以在 Microsoft 365 中存档以文本分隔的数据
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
description: 管理员可以将连接器设置为将文本分隔的数据从 Globanet 导入并存档到 Microsoft 365 中。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: e57e9693da77a246bafcdf30561fd1414761355f
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399293"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data-preview"></a><span data-ttu-id="66fad-104">设置连接器以存档以文本分隔的数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="66fad-104">Set up a connector to archive text-delimited data (preview)</span></span>

<span data-ttu-id="66fad-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将文本分隔的数据导入到 Microsoft 365 组织中的用户邮箱并进行存档。</span><span class="sxs-lookup"><span data-stu-id="66fad-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive text-delimited data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="66fad-106">[Globanet](https://globanet.com/merge1/) 提供了一个文本分隔的连接器，该连接器配置为定期捕获第三方数据源 (中的项目) 并将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="66fad-106">[Globanet](https://globanet.com/merge1/) provides a Text-Delimited connector that is configured to capture items from a third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="66fad-107">连接器将文本分隔的数据源中的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="66fad-107">The connector converts content from the text-delimited data source to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="66fad-108">将以文本分隔的数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="66fad-108">After text-delimited data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="66fad-109">使用缩放会议连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和管理法规策略。</span><span class="sxs-lookup"><span data-stu-id="66fad-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="66fad-110">存档后，可以保留文本分隔的源通信，以实现合规性，并检索电子数据展示和内部信息治理。</span><span class="sxs-lookup"><span data-stu-id="66fad-110">Once archived, the Text-Delimited source communications can be retained, supervised for compliance, and retrieved for eDiscovery and internal Information Governance.</span></span>

## <a name="overview-of-archiving-the-text-delimited-source"></a><span data-ttu-id="66fad-111">存档以文本分隔的源的概述</span><span class="sxs-lookup"><span data-stu-id="66fad-111">Overview of archiving the Text-Delimited source</span></span>

<span data-ttu-id="66fad-112">以下概述说明使用连接器在 Microsoft 365 中存档文本分隔的源信息的过程。</span><span class="sxs-lookup"><span data-stu-id="66fad-112">The following overview explains the process of using a connector to archive the Text-Delimited source information in Microsoft 365.</span></span>

![用于以文本分隔的数据的存档工作流](../media/TextDelimitedConnectorWorkflow.png)

1. <span data-ttu-id="66fad-114">您的组织使用文本分隔的源来设置和配置以文本分隔的网站。</span><span class="sxs-lookup"><span data-stu-id="66fad-114">Your organization works with the Text-Delimited source to set up and configure a Text-Delimited site.</span></span>

2. <span data-ttu-id="66fad-115">每24小时一次，来自文本分隔源的聊天消息将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="66fad-115">Once every 24 hours, chat messages from the Text-Delimited source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="66fad-116">连接器还会将内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="66fad-116">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="66fad-117">您在 Microsoft 365 合规性中心中创建的文本分隔的连接器每天连接到 Globanet Merge1 网站，并将邮件传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="66fad-117">The Text-Delimited connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="66fad-118">连接器使用自动用户映射的 *电子邮件* 属性的值将已转换的邮件项导入到特定用户的邮箱中，如步骤3中所述。</span><span class="sxs-lookup"><span data-stu-id="66fad-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="66fad-119">将在用户邮箱中创建名为 "以 **文本分隔** 的收件箱" 文件夹中的新子文件夹，并将邮件项目导入该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="66fad-119">A new subfolder in the Inbox folder named **Text- Delimited** will be created in the user mailboxes, and the message items will be imported to that folder.</span></span> <span data-ttu-id="66fad-120">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="66fad-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="66fad-121">每封邮件都包含此属性，该属性由邮件的每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="66fad-121">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="66fad-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="66fad-122">Before you begin</span></span>

- <span data-ttu-id="66fad-123">通过接受以文本分隔的连接符的条款和条件创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="66fad-123">Create a Globanet Merge1 account by accepting the terms and conditions for the Text-Delimited connector.</span></span> <span data-ttu-id="66fad-124">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/contact-us)。</span><span class="sxs-lookup"><span data-stu-id="66fad-124">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="66fad-125">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="66fad-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="66fad-126">在步骤1中创建以文本分隔的连接器 (并在第3步中完成它的用户) 必须分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="66fad-126">The user who creates the Text-Delimited connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="66fad-127">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="66fad-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="66fad-128">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="66fad-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="66fad-129">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="66fad-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="66fad-130">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="66fad-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="66fad-131">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="66fad-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-text-delimited-connector"></a><span data-ttu-id="66fad-132">步骤1：设置以文本分隔的连接符</span><span class="sxs-lookup"><span data-stu-id="66fad-132">Step 1: Set up the Text-Delimited connector</span></span>

<span data-ttu-id="66fad-133">第一步是访问 Microsoft 365 合规性中心中的 " **数据连接器** " 页，并为以文本分隔的数据创建连接器。</span><span class="sxs-lookup"><span data-stu-id="66fad-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for text-delimited data.</span></span>

1. <span data-ttu-id="66fad-134">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**  >  **文本分隔**"。</span><span class="sxs-lookup"><span data-stu-id="66fad-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Text-Delimited**.</span></span>

2. <span data-ttu-id="66fad-135">在 " **文本分隔** 产品说明" 页上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="66fad-135">On the **Text-Delimited** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="66fad-136">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="66fad-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="66fad-137">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="66fad-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="66fad-138">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="66fad-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="66fad-139">步骤2：在 Globanet Merge1 网站上配置文本分隔的连接器</span><span class="sxs-lookup"><span data-stu-id="66fad-139">Step 2: Configure the Text-delimited connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="66fad-140">第二步是在 Merge1 网站中配置文本分隔的连接器。</span><span class="sxs-lookup"><span data-stu-id="66fad-140">The second step is to configure the Text-Delimited connector in the Merge1 site.</span></span> <span data-ttu-id="66fad-141">有关在 Globanet Merge1 网站上配置文本分隔的连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Text-Delimited%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="66fad-141">For information about configuring  the Text-Delimited connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Text-Delimited%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="66fad-142">单击 " **保存" & "完成**" 后，将返回到 Microsoft 365 合规性中心，再到 "连接器向导" 的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="66fad-142">After you click **Save & Finish**, you are returned to the Microsoft 365 compliance center, to the **User mapping** page of the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="66fad-143">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="66fad-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="66fad-144">若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="66fad-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="66fad-145">在 "将 **外部用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="66fad-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="66fad-146">文本分隔的源项包含一个名为 *Email*的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="66fad-146">The Text- Delimited source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="66fad-147">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="66fad-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="66fad-148">在 " **管理员同意** " 页面上，单击 " **提供同意** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="66fad-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="66fad-149">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="66fad-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="66fad-150">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="66fad-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="66fad-151">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="66fad-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="66fad-152">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="66fad-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="66fad-153">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="66fad-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="66fad-154">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="66fad-154">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-text-delimited-connector"></a><span data-ttu-id="66fad-155">步骤4：监视以文本分隔的连接符</span><span class="sxs-lookup"><span data-stu-id="66fad-155">Step 4: Monitor the text-delimited connector</span></span>

<span data-ttu-id="66fad-156">创建文本分隔的连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="66fad-156">After you create the Text- Delimited connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="66fad-157">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="66fad-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="66fad-158">单击 " **连接器** " 选项卡，然后选择 **文本分隔** 的连接线以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="66fad-158">Click the **Connectors** tab and then select the **Text- Delimited** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="66fad-159">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="66fad-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="66fad-160">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="66fad-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="66fad-161">已知问题</span><span class="sxs-lookup"><span data-stu-id="66fad-161">Known issues</span></span>

- <span data-ttu-id="66fad-162">目前，我们不支持导入大于 10 MB 的附件，但稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="66fad-162">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
