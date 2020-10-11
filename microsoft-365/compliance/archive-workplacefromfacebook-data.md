---
title: 在 Microsoft 365 中设置连接器以存档来自 Facebook 数据的工作区
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
description: 管理员可以设置连接器以将来自 Facebook 的工作区中的数据导入和存档（存档在 Globanet 的 Merge1 网站上）到 Microsoft 365。 设置连接器时，需要使用 Globanet 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: f8fadda12136d50f092dd86081b1186ab01c6e4e
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408644"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a><span data-ttu-id="903fa-104">设置连接器以存档来自 Facebook 数据的工作区</span><span class="sxs-lookup"><span data-stu-id="903fa-104">Set up a connector to archive Workplace from Facebook data</span></span>

<span data-ttu-id="903fa-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器在 Microsoft 365 组织中将来自 Facebook 的工作区中的数据导入和存档到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="903fa-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Workplace from Facebook to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="903fa-106">Globanet 提供 [来自 Facebook 连接器的工作区](https://globanet.com/workplace/) ，该连接器配置为定期捕获第三方数据源 (中的项目) 并将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="903fa-106">Globanet provides a [Workplace from Facebook](https://globanet.com/workplace/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="903fa-107">连接器将内容（如聊天、附件、帖子和视频）从工作区转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="903fa-107">The connector converts the content such as chats, attachments, posts, and videos from Workplace to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="903fa-108">在将工作区数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="903fa-108">After Workplace data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="903fa-109">使用 Facebook connector 中的工作区在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和管理法规策略。</span><span class="sxs-lookup"><span data-stu-id="903fa-109">Using Workplace from Facebook connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-workplace-from-facebook-data"></a><span data-ttu-id="903fa-110">从 Facebook 数据存档工作区概述</span><span class="sxs-lookup"><span data-stu-id="903fa-110">Overview of archiving Workplace from Facebook data</span></span>

<span data-ttu-id="903fa-111">以下概述介绍了使用连接器在 Microsoft 365 中存档工作区数据的过程。</span><span class="sxs-lookup"><span data-stu-id="903fa-111">The following overview explains the process of using a connector to archive Workplace data in Microsoft 365.</span></span>

![为来自 Facebook 数据的工作区存档工作流](../media/WorkplaceConnectorWorkflow.png)

1. <span data-ttu-id="903fa-113">你的组织使用 Facebook 中的工作区来设置和配置工作区网站。</span><span class="sxs-lookup"><span data-stu-id="903fa-113">Your organization works with Workplace from Facebook to set up and configure a Workplace site.</span></span>

2. <span data-ttu-id="903fa-114">每24小时一次，将工作区中的项目复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="903fa-114">Once every 24 hours, items from Workplace are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="903fa-115">连接器还将这些项目的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="903fa-115">The connector also converts the content of these items to an email message format.</span></span>

3. <span data-ttu-id="903fa-116">你在 Microsoft 365 合规性中心创建的 Facebook 连接器中的工作区将每天连接到 Globanet Merge1，并将工作区项传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="903fa-116">The Workplace from Facebook connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the Workplace items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="903fa-117">连接器使用自动用户映射的 *电子邮件* 属性的值将转换后的项目导入到特定用户的邮箱中，如步骤3中所述。</span><span class="sxs-lookup"><span data-stu-id="903fa-117">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="903fa-118">创建一个名为 " **来自 Facebook 的工作区** " 的 "收件箱" 文件夹中的子文件夹，并将工作区项目导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="903fa-118">A subfolder in the Inbox folder named **Workplace from Facebook** is created, and the Workplace items are imported to that folder.</span></span> <span data-ttu-id="903fa-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="903fa-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="903fa-120">每个工作区项都包含此属性，该属性由每个聊天或帖子参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="903fa-120">Every Workplace item contains this property, which is populated with the email address of every chat or post participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="903fa-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="903fa-121">Before you begin</span></span>

- <span data-ttu-id="903fa-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="903fa-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="903fa-123">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="903fa-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="903fa-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="903fa-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="903fa-125">在中创建自定义集成， https://my.workplace.com/work/admin/apps/ 以通过 api 从工作区检索数据，以实现遵从性和 eDiscovery 目的。</span><span class="sxs-lookup"><span data-stu-id="903fa-125">Create a custom integration at https://my.workplace.com/work/admin/apps/ to retrieve data from Workplace via APIs for compliance and eDiscovery purposes.</span></span>

   <span data-ttu-id="903fa-126">在创建集成时，工作区平台将生成一组唯一的凭据，用于生成用于身份验证的令牌。</span><span class="sxs-lookup"><span data-stu-id="903fa-126">When creating the integration, the Workplace platform generates a set of unique credentials used to generate tokens that are used for authentication.</span></span> <span data-ttu-id="903fa-127">这些令牌在步骤2中的 "Facebook 连接器配置向导" 中使用。</span><span class="sxs-lookup"><span data-stu-id="903fa-127">These tokens are used in the Workplace from Facebook connector configuration wizard in Step 2.</span></span> <span data-ttu-id="903fa-128">有关如何创建应用程序的分步说明，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="903fa-128">For step-by step instructions about how to create the applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="903fa-129">在步骤1中从 Facebook 连接器创建工作区的用户 (并在第3步中完成此操作) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="903fa-129">The user who creates the Workplace from Facebook connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="903fa-130">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="903fa-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="903fa-131">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="903fa-131">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="903fa-132">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="903fa-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="903fa-133">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="903fa-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="903fa-134">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="903fa-134">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a><span data-ttu-id="903fa-135">步骤1：设置来自 Facebook 连接器的工作区</span><span class="sxs-lookup"><span data-stu-id="903fa-135">Step 1: Set up the Workplace from Facebook connector</span></span>

<span data-ttu-id="903fa-136">第一步是访问 Microsoft 365 合规性中心中的 " **数据连接器** " 页，并为工作区数据创建连接器。</span><span class="sxs-lookup"><span data-stu-id="903fa-136">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Workplace data.</span></span>

1. <span data-ttu-id="903fa-137">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击**Data connectors**  >  **Facebook 中的**"数据连接器工作区"。</span><span class="sxs-lookup"><span data-stu-id="903fa-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Workplace from Facebook**.</span></span>

2. <span data-ttu-id="903fa-138">在 " **来自 Facebook 的工作区** 产品说明" 页上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="903fa-138">On the **Workplace from Facebook** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="903fa-139">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="903fa-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="903fa-140">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="903fa-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="903fa-141">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="903fa-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="903fa-142">步骤2：在 Globanet Merge1 网站上的 Facebook 连接器中配置工作区</span><span class="sxs-lookup"><span data-stu-id="903fa-142">Step 2: Configure the Workplace from Facebook connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="903fa-143">第二步是在 Merge1 网站上的 Facebook 连接器中配置工作区。</span><span class="sxs-lookup"><span data-stu-id="903fa-143">The second step is to configure the Workplace from Facebook connector on the Merge1 site.</span></span> <span data-ttu-id="903fa-144">有关如何从 Facebook 连接器配置工作区的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="903fa-144">For information about how to configure the Workplace from Facebook connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="903fa-145">单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="903fa-145">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="903fa-146">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="903fa-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="903fa-147">若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="903fa-147">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="903fa-148">在 "将 **外部用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="903fa-148">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="903fa-149">工作区项目包含一个名为 *电子邮件* 的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="903fa-149">The Workplace items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="903fa-150">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="903fa-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="903fa-151">在 " **管理员同意** " 页上，单击 " **提供同意**"。</span><span class="sxs-lookup"><span data-stu-id="903fa-151">On the **Admin Consent** page, click **Provide Consent**.</span></span> <span data-ttu-id="903fa-152">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="903fa-152">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="903fa-153">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="903fa-153">Click **Accept** to provide the consent.</span></span>
  
   <span data-ttu-id="903fa-154">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="903fa-154">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="903fa-155">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="903fa-155">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="903fa-156">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="903fa-156">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="903fa-157">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="903fa-157">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a><span data-ttu-id="903fa-158">步骤4：从 Facebook 连接器监视工作区</span><span class="sxs-lookup"><span data-stu-id="903fa-158">Step 4: Monitor the Workplace from Facebook connector</span></span>

<span data-ttu-id="903fa-159">从 Facebook 连接器创建工作区后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="903fa-159">After you create the Workplace from Facebook connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="903fa-160">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="903fa-160">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="903fa-161">单击 " **连接器** " 选项卡，然后从 "Facebook 连接器" 中选择 " **工作区** " 以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="903fa-161">Click the **Connectors** tab and then select the **Workplace from Facebook** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="903fa-162">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="903fa-162">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="903fa-163">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="903fa-163">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="903fa-164">已知问题</span><span class="sxs-lookup"><span data-stu-id="903fa-164">Known issues</span></span>

- <span data-ttu-id="903fa-165">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="903fa-165">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="903fa-166">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="903fa-166">Support for larger items will be available at a later date.</span></span>
