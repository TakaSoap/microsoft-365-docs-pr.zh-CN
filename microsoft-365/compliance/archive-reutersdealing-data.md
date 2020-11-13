---
title: 将连接器设置为在 Microsoft 365 中处理数据的存档 Reuters
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
description: 管理员可以设置连接器以导入和存档 Reuters 处理从 Globanet 到 Microsoft 365 的数据。 此连接器允许您在 Microsoft 365 中存档第三方数据源中的数据。 存档此数据后，您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理第三方数据。
ms.openlocfilehash: bd3eefb1054d8ef9302ffa6f94ddce740bd55a70
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002738"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data-preview"></a><span data-ttu-id="ce62b-105">将连接器设置为存档数据 (预览的 Reuters) </span><span class="sxs-lookup"><span data-stu-id="ce62b-105">Set up a connector to archive Reuters Dealing data (preview)</span></span>

<span data-ttu-id="ce62b-106">使用 Microsoft 365 合规性中心中的 Globanet 连接器导入和存档来自 Microsoft 365 组织中的平台到用户邮箱的 Reuters 中的数据。</span><span class="sxs-lookup"><span data-stu-id="ce62b-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters Dealing platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="ce62b-107">Globanet 为您提供了一个 [Reuters 处理](https://globanet.com/reuters-dealing/) 连接器，该连接器配置为定期从第三方数据源捕获项目 () 然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ce62b-107">Globanet provides you with a [Reuters Dealing](https://globanet.com/reuters-dealing/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="ce62b-108">连接器将处理通信从 Reuters 处理帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ce62b-108">The connector converts Dealing communications from the Reuters Dealing account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="ce62b-109">在 Reuters 处理数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签，以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="ce62b-109">After Reuters Dealing data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="ce62b-110">使用 Reuters 处理连接器以在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="ce62b-110">Using a Reuters Dealing connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-dealing-data"></a><span data-ttu-id="ce62b-111">处理数据的存档 Reuters 概述</span><span class="sxs-lookup"><span data-stu-id="ce62b-111">Overview of archiving Reuters Dealing data</span></span>

<span data-ttu-id="ce62b-112">以下概述说明使用连接器存档在 Microsoft 365 中处理数据的 Reuters 的过程。</span><span class="sxs-lookup"><span data-stu-id="ce62b-112">The following overview explains the process of using a connector to archive the Reuters Dealing data in Microsoft 365.</span></span>

![处理数据的 Reuters 的存档工作流](../media/ReuetersDealingConnectorWorkflow.png)

1. <span data-ttu-id="ce62b-114">您的组织使用 Reuters 来处理设置和配置 Reuters 处理网站的过程。</span><span class="sxs-lookup"><span data-stu-id="ce62b-114">Your organization works with Reuters Dealing to set up and configure a Reuters Dealing site.</span></span>

2. <span data-ttu-id="ce62b-115">每24小时一次，Reuters 处理项目将被复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="ce62b-115">Once every 24 hours, Reuters Dealing items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="ce62b-116">连接器还将项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="ce62b-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="ce62b-117">处理在 Microsoft 365 合规性中心中创建的连接器的 Reuters 每日连接到 Globanet Merge1 网站，并将内容传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="ce62b-117">The Reuters Dealing connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="ce62b-118">连接器使用自动用户映射的 *电子邮件* 属性的值将项目导入到特定用户的邮箱中，如 [步骤 3](#step-3-map-users-and-complete-the-connector-setup)中所述。</span><span class="sxs-lookup"><span data-stu-id="ce62b-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="ce62b-119">名为 " **Reuters** " 的 "收件箱" 文件夹中的子文件夹在用户邮箱中创建，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ce62b-119">A subfolder in the Inbox folder named **Reuters Dealing** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="ce62b-120">连接器通过使用 *Email* 属性的值确定要将项目导入到哪个邮箱。</span><span class="sxs-lookup"><span data-stu-id="ce62b-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="ce62b-121">每个 Reuters 处理的项目都包含此属性，该属性填入项目的每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ce62b-121">Every Reuters Dealing item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ce62b-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="ce62b-122">Before you begin</span></span>

- <span data-ttu-id="ce62b-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="ce62b-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="ce62b-124">若要创建帐户，请联系 [Globanet 客户支持](https://globanet.com/contact-us)。</span><span class="sxs-lookup"><span data-stu-id="ce62b-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="ce62b-125">当您在步骤1中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="ce62b-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="ce62b-126">在步骤1中创建 Reuters 处理连接器的用户 (并在步骤3中完成) 必须将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="ce62b-126">The user who creates the Reuters Dealing connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ce62b-127">此角色是在 Microsoft 365 合规性中心中的 " **数据连接器** " 页上添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="ce62b-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ce62b-128">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="ce62b-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="ce62b-129">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="ce62b-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ce62b-130">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="ce62b-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ce62b-131">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="ce62b-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-dealing-connector"></a><span data-ttu-id="ce62b-132">步骤1：设置 Reuters 处理连接器</span><span class="sxs-lookup"><span data-stu-id="ce62b-132">Step 1: Set up the Reuters Dealing connector</span></span>

<span data-ttu-id="ce62b-133">第一步是访问 Microsoft 365 中的 " **数据连接器** " 页，并为处理数据的 Reuters 创建一个连接器。</span><span class="sxs-lookup"><span data-stu-id="ce62b-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters Dealing data.</span></span>

1. <span data-ttu-id="ce62b-134">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 " **数据连接器**  >  **Reuters 处理** "。</span><span class="sxs-lookup"><span data-stu-id="ce62b-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Dealing**.</span></span>

2. <span data-ttu-id="ce62b-135">在 " **Reuters 处理** 产品说明" 页上，单击 " **添加连接器** "。</span><span class="sxs-lookup"><span data-stu-id="ce62b-135">On the **Reuters Dealing** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="ce62b-136">在 " **服务条款** " 页上，单击 " **接受** "。</span><span class="sxs-lookup"><span data-stu-id="ce62b-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="ce62b-137">输入标识连接器的唯一名称，然后单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="ce62b-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="ce62b-138">登录到您的 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="ce62b-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="ce62b-139">步骤2：在 Globanet Merge1 网站上配置 Reuters 处理连接器</span><span class="sxs-lookup"><span data-stu-id="ce62b-139">Step 2: Configure the Reuters Dealing connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="ce62b-140">第二步是在 Globanet 上配置 Merge1 站点上的 Reuters 处理连接器。</span><span class="sxs-lookup"><span data-stu-id="ce62b-140">The second step is to configure the Reuters Dealing connector on Globanet the Merge1 site.</span></span> <span data-ttu-id="ce62b-141">有关配置 Reuters 处理连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="ce62b-141">For information about configuring the Reuters Dealing connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="ce62b-142">单击 " **保存" & 完成** 后，将显示 Microsoft 365 合规性中心的 "连接器向导" 中的 " **用户映射** " 页。</span><span class="sxs-lookup"><span data-stu-id="ce62b-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="ce62b-143">步骤3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="ce62b-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="ce62b-144">若要映射用户并完成 Microsoft 365 合规性中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ce62b-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="ce62b-145">在 "将 **用户处理为 Microsoft 365 用户** " 页上的 "映射 Reuters" 下，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="ce62b-145">On the **Map Reuters Dealing users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="ce62b-146">Reuters 处理项目包括名为 " *电子邮件* " 的属性，其中包含组织中的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ce62b-146">Reuters Dealing items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="ce62b-147">如果连接器可以将此地址与 Microsoft 365 用户相关联，则会将这些项目导入该用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ce62b-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="ce62b-148">在 " **管理员同意** " 页面上，单击 " **提供同意** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="ce62b-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="ce62b-149">你将被重定向到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="ce62b-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="ce62b-150">单击 " **接受** " 以提供许可。</span><span class="sxs-lookup"><span data-stu-id="ce62b-150">Click **Accept** to provide the consent.</span></span>

    <span data-ttu-id="ce62b-151">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="ce62b-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="ce62b-152">若要提供管理员同意，必须使用 Microsoft 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="ce62b-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="ce62b-153">如果你未以全局管理员身份登录，则可以转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="ce62b-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="ce62b-154">单击 " **下一步** "，查看设置，然后转到 " **数据连接器** " 页，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="ce62b-154">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-dealing-connector"></a><span data-ttu-id="ce62b-155">步骤4：监视 Reuters 处理连接器</span><span class="sxs-lookup"><span data-stu-id="ce62b-155">Step 4: Monitor the Reuters Dealing connector</span></span>

<span data-ttu-id="ce62b-156">创建 Reuters 处理连接器后，可以在 Microsoft 365 合规性中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="ce62b-156">After you create the Reuters Dealing connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="ce62b-157">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 并单击左侧导航中的 " **数据连接器** "。</span><span class="sxs-lookup"><span data-stu-id="ce62b-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ce62b-158">单击 " **连接器** " 选项卡，然后选择 " **Reuters 处理** 连接器" 以显示弹出页面，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="ce62b-158">Click the **Connectors** tab and then select the **Reuters Dealing** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="ce62b-159">在 " **连接器状态与源** " 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="ce62b-159">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="ce62b-160">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="ce62b-160">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ce62b-161">已知问题</span><span class="sxs-lookup"><span data-stu-id="ce62b-161">Known issues</span></span>

- <span data-ttu-id="ce62b-162">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="ce62b-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="ce62b-163">较大项目的支持将在以后提供。</span><span class="sxs-lookup"><span data-stu-id="ce62b-163">Support for larger items will be available at a later date.</span></span>
