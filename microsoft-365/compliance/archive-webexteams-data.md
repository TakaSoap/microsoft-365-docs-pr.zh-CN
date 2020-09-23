---
title: 在 Microsoft 365 中设置与 Webex 团队数据的连接器
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
description: 管理员可以设置连接器，以便在 Microsoft 365 中的 Globanet 的 Webex 团队连接器中导入和存档数据。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据，因此您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 3d9693fd1baf990ba3ca956c8a24d8d796e80995
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196561"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a><span data-ttu-id="d7154-104">设置连接器以存档 Webex 团队数据</span><span class="sxs-lookup"><span data-stu-id="d7154-104">Set up a connector to archive Webex Teams data</span></span>

<span data-ttu-id="d7154-105">使用 Microsoft 365 合规性中心中的 Globanet 连接器将 Webex 团队中的数据导入和存档到 Microsoft 365 组织中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="d7154-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Webex Teams to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d7154-106">Globanet 提供了一个 [Webex 团队](https://globanet.com/webex-teams/) 连接器，该连接器配置为捕获 Webex 团队通信项并将其导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d7154-106">Globanet provides a [Webex Teams](https://globanet.com/webex-teams/) connector that is configured to capture Webex Teams communication items and import them to Microsoft 365.</span></span> <span data-ttu-id="d7154-107">连接器将内容从 Webex 团队（如1:1 聊天、组对话、频道对话和组织的 Webex 团队帐户中的附件）转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="d7154-107">The connector converts content from Webex Teams, such as 1:1 chats, group conversations, channel conversations, and attachments from your organization's Webex Teams account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="d7154-108">在将 Webex 团队数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="d7154-108">After Webex Teams data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="d7154-109">使用 Webex 团队连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="d7154-109">Using a Webex Teams connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webex-teams-data"></a><span data-ttu-id="d7154-110">存档 Webex 团队数据概述</span><span class="sxs-lookup"><span data-stu-id="d7154-110">Overview of archiving Webex Teams data</span></span>

<span data-ttu-id="d7154-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 Webex 团队数据的过程。</span><span class="sxs-lookup"><span data-stu-id="d7154-111">The following overview explains the process of using a connector to archive Webex Teams data in Microsoft 365.</span></span>

![针对 Webex 团队数据的存档工作流](../media/WebexTeamsConnectorWorkflow.png)

1. <span data-ttu-id="d7154-113">您的组织与 Webex 团队合作，以设置和配置 Webex 团队网站。</span><span class="sxs-lookup"><span data-stu-id="d7154-113">Your organization works with Webex Teams to set up and configure a Webex Teams site.</span></span>

2. <span data-ttu-id="d7154-114">每24小时一次，Webex 团队项目将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="d7154-114">Once every 24 hours, Webex Teams items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="d7154-115">连接器还将 Webex 团队项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="d7154-115">The connector also converts the Webex Teams items to an email message format.</span></span>

3. <span data-ttu-id="d7154-116">您在 Microsoft 365 合规中心中创建的 Webex 团队连接器会每天连接到 Globanet Merge1，并将 Webex 团队项目传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="d7154-116">The Webex Teams connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the Webex Teams items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d7154-117">连接器使用自动用户映射的 *电子邮件* 属性的值将项目导入到特定用户的邮箱中，如 [步骤 3](#step-3-map-users-and-complete-the-connector-setup)中所述。</span><span class="sxs-lookup"><span data-stu-id="d7154-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="d7154-118">在用户邮箱中创建名为 **Webex 团队** 的 "收件箱" 文件夹中的子文件夹，并将这些项目导入该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d7154-118">A subfolder in the Inbox folder named **Webex Teams** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="d7154-119">连接器通过使用 *电子邮件* 属性的值来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="d7154-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="d7154-120">每个 Webex 团队项目都包含此属性，该属性填充了项目的每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d7154-120">Every Webex Teams item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d7154-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="d7154-121">Before you begin</span></span>

- <span data-ttu-id="d7154-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="d7154-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="d7154-123">若要执行此操作，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="d7154-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="d7154-124">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="d7154-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d7154-125">在中创建一个应用程序 [https://developer.webex.com/](https://developer.webex.com) 以从 Webex 团队帐户中获取数据。</span><span class="sxs-lookup"><span data-stu-id="d7154-125">Create an application at [https://developer.webex.com/](https://developer.webex.com) to fetch data from your Webex Teams account.</span></span> <span data-ttu-id="d7154-126">有关创建应用程序的分步说明，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="d7154-126">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span></span>

   <span data-ttu-id="d7154-127">创建此应用程序时，Webex 平台将生成一组唯一的凭据。</span><span class="sxs-lookup"><span data-stu-id="d7154-127">When you create this application, the Webex platform generates a set of unique credentials.</span></span> <span data-ttu-id="d7154-128">当您在全局 Merge1 网站上配置 Webex 团队连接器时，将在步骤2中使用这些凭据。</span><span class="sxs-lookup"><span data-stu-id="d7154-128">These credentials are used in Step 2 when you configure the Webex Teams connector on the Global Merge1 site.</span></span>

- <span data-ttu-id="d7154-129">在步骤1中创建 Webex 团队连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="d7154-129">The user who creates the Webex Teams connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d7154-130">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="d7154-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d7154-131">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="d7154-131">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d7154-132">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="d7154-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d7154-133">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="d7154-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d7154-134">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="d7154-134">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webex-teams-connector"></a><span data-ttu-id="d7154-135">步骤1：设置 Webex 团队连接器</span><span class="sxs-lookup"><span data-stu-id="d7154-135">Step 1: Set up the Webex Teams connector</span></span>

<span data-ttu-id="d7154-136">第一步是获取对 **数据连接器** 的访问权限，并设置 [Webex 团队](https://globanet.com/webex-teams/) 连接器。</span><span class="sxs-lookup"><span data-stu-id="d7154-136">The first step is to gain access to the **Data Connectors** and set up the [Webex Teams](https://globanet.com/webex-teams/) connector.</span></span>

1. <span data-ttu-id="d7154-137">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 "**数据连接器**  >  **Webex 团队**"。</span><span class="sxs-lookup"><span data-stu-id="d7154-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webex Teams**.</span></span>

2. <span data-ttu-id="d7154-138">在 " **Webex 团队** 产品说明" 页上，单击 " **添加连接器**"。</span><span class="sxs-lookup"><span data-stu-id="d7154-138">On the **Webex Teams** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="d7154-139">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="d7154-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d7154-140">输入标识连接器的唯一名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d7154-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="d7154-141">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="d7154-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webex-teams-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="d7154-142">步骤2：在 Globanet Merge1 网站上配置 Webex 团队连接器</span><span class="sxs-lookup"><span data-stu-id="d7154-142">Step 2: Configure the Webex Teams connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="d7154-143">第二步是在 Merge1 网站上配置 Webex 团队连接器。</span><span class="sxs-lookup"><span data-stu-id="d7154-143">The second step is to configure the Webex Teams connector on the Merge1 site.</span></span> <span data-ttu-id="d7154-144">有关如何配置 Webex 团队连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="d7154-144">For information about how to configure the Webex Teams connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="d7154-145">单击 " **保存" & "完成**" 后，将转回到 Microsoft 365 合规性中心，转到 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="d7154-145">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="d7154-146">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="d7154-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="d7154-147">若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d7154-147">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="d7154-148">在 "将 **Webex 团队用户映射到 Microsoft 365 用户** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="d7154-148">On the **Map Webex Teams users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="d7154-149">Webex 团队项目包含一个名为 *Email*的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d7154-149">The Webex Teams items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="d7154-150">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="d7154-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="d7154-151">在 " **管理员同意** " 页面上，单击 " **提供同意** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="d7154-151">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="d7154-152">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="d7154-152">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="d7154-153">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="d7154-153">Click **Accept** to provide the consent.</span></span>
  
   <span data-ttu-id="d7154-154">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="d7154-154">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="d7154-155">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="d7154-155">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="d7154-156">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="d7154-156">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="d7154-157">单击 " **下一步**"，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="d7154-157">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webex-teams-connector"></a><span data-ttu-id="d7154-158">步骤4：监视 Webex 团队连接器</span><span class="sxs-lookup"><span data-stu-id="d7154-158">Step 4: Monitor the Webex Teams connector</span></span>

<span data-ttu-id="d7154-159">创建 Webex 团队连接器后，可以在 Microsoft 365 合规性中心中查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="d7154-159">After you create the Webex Teams connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d7154-160">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="d7154-160">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d7154-161">单击 " **连接器** " 选项卡，然后选择 " **Webex 团队** 连接器" 以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="d7154-161">Click the **Connectors** tab and then select the **Webex Teams** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d7154-162">在 " **连接器状态与源**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="d7154-162">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d7154-163">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="d7154-163">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d7154-164">已知问题</span><span class="sxs-lookup"><span data-stu-id="d7154-164">Known issues</span></span>

- <span data-ttu-id="d7154-165">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="d7154-165">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d7154-166">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="d7154-166">Support for larger items will be available at a later date.</span></span>
