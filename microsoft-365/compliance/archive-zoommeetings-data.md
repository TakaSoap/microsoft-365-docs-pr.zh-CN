---
title: 设置连接器以在 Microsoft 365 中存档"缩放会议"数据
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
description: 管理员可以设置连接器，以将数据从"Microsoft 365 放大"会议导入和存档。 这使你可以存档 Microsoft 365 中第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: b67098f3ddb1149927f4b82270c8fa4f14bbe558
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163722"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a><span data-ttu-id="9d358-104">设置连接器以存档"缩放会议"数据</span><span class="sxs-lookup"><span data-stu-id="9d358-104">Set up a connector to archive Zoom Meetings data</span></span>

<span data-ttu-id="9d358-105">使用 Microsoft 365 合规中心中的"Microsoft 365"连接器，将"缩放会议"数据导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="9d358-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from Zoom Meetings to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="9d358-106">Microsoft 提供 [缩放](https://globanet.com/zoom/) 会议连接器，配置为定期捕获第三方数据源 (中的项目) 将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="9d358-106">Veritas provides a [Zoom Meetings](https://globanet.com/zoom/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="9d358-107">连接器将会议内容 (包括聊天、录制的文件和元数据) 从 Zoom Meetings 帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="9d358-107">The connector converts the content of the meetings (including chats, recorded files, and metadata) from the Zoom Meetings account to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="9d358-108">缩放会议数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="9d358-108">After Zoom Meetings data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="9d358-109">使用 Zoom Meetings 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="9d358-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-meetings-data"></a><span data-ttu-id="9d358-110">存档缩放会议数据概述</span><span class="sxs-lookup"><span data-stu-id="9d358-110">Overview of archiving Zoom Meetings data</span></span>

<span data-ttu-id="9d358-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 Zoom Meetings 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="9d358-111">The following overview explains the process of using a connector to archive Zoom Meetings data in Microsoft 365.</span></span>

![缩放会议存档工作流](../media/ZoomMeetingsConnectorWorkflow.png)

1. <span data-ttu-id="9d358-113">你的组织使用"缩放会议"来设置和配置"缩放会议"网站。</span><span class="sxs-lookup"><span data-stu-id="9d358-113">Your organization works with Zoom Meetings to set up and configure a Zoom Meetings site.</span></span>

2. <span data-ttu-id="9d358-114">每 24 小时一次，"缩放会议"中的会议项目将复制到"是否合并 1"网站。</span><span class="sxs-lookup"><span data-stu-id="9d358-114">Once every 24 hours, meeting items from Zoom Meetings are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="9d358-115">连接器还会将会议内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="9d358-115">The connector also converts the content of the meetings to an email message format.</span></span>

3. <span data-ttu-id="9d358-116">在 Microsoft 365 合规中心创建的缩放会议连接器，每天连接到 Microsoft Merge1，将会议消息转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="9d358-116">The Zoom Meetings connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 every day, and transfers the meeting messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="9d358-117">连接器使用 *Email* 属性的值和自动用户映射将转换的会议项目导入特定用户的邮箱，如步骤 3 中所述。</span><span class="sxs-lookup"><span data-stu-id="9d358-117">The connector imports the converted meeting items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="9d358-118">"收件箱"文件夹中名为"缩放会议"的新子文件夹是在用户邮箱中创建的，并且会议项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9d358-118">A new subfolder in the Inbox folder named **Zoom Meetings** is created in user mailboxes, and the meeting items are imported to that folder.</span></span> <span data-ttu-id="9d358-119">连接器使用 *Email* 属性的值实现此操作。</span><span class="sxs-lookup"><span data-stu-id="9d358-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="9d358-120">每个会议项目都包含此属性，其中填充了会议每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9d358-120">Every meeting item contains this property, which is populated with the email address of every participant of the meeting.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9d358-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="9d358-121">Before you begin</span></span>

- <span data-ttu-id="9d358-122">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="9d358-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="9d358-123">若要创建此帐户，请联系["用户支持人员"。](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="9d358-123">To create this account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="9d358-124">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="9d358-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="9d358-125">获取组织的 Zoom Business 或 Zoom Enterprise 帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="9d358-125">Obtain the username and password for your organization's Zoom Business or Zoom Enterprise account.</span></span> <span data-ttu-id="9d358-126">配置"缩放会议"连接器时，需要在步骤 2 中登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="9d358-126">You'll need to sign into this account in Step 2 when you configure the Zoom Meetings connector.</span></span>

- <span data-ttu-id="9d358-127">在缩放市场中创建 [以下应用程序](https://marketplace.zoom.us)：</span><span class="sxs-lookup"><span data-stu-id="9d358-127">Create the following applications in the [Zoom Marketplace](https://marketplace.zoom.us):</span></span>

  - <span data-ttu-id="9d358-128">OAuth 应用程序</span><span class="sxs-lookup"><span data-stu-id="9d358-128">OAuth application</span></span>

  - <span data-ttu-id="9d358-129">JWT 应用程序</span><span class="sxs-lookup"><span data-stu-id="9d358-129">JWT application</span></span>

  <span data-ttu-id="9d358-130">创建这些应用程序后，Zoom 平台将生成一组用于生成令牌的唯一凭据。</span><span class="sxs-lookup"><span data-stu-id="9d358-130">After you create these applications, the Zoom platform generates a set of unique credentials used to generate the tokens.</span></span> <span data-ttu-id="9d358-131">这些令牌用于在连接器连接到 Zoom 帐户，将项目复制到 Merge1 网站时对连接器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9d358-131">These tokens are used to authenticate the connector when it connects to your Zoom account and copies items to the Merge1 site.</span></span> <span data-ttu-id="9d358-132">在步骤 2 中配置缩放连接器时，你将使用这些令牌。</span><span class="sxs-lookup"><span data-stu-id="9d358-132">You will use these tokens when you configure the Zoom connector in Step 2.</span></span>

  <span data-ttu-id="9d358-133">有关如何创建 OAuth 和 JWT 应用程序的分步说明，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="9d358-133">For step-by step instructions on how to create the OAuth and JWT applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="9d358-134">必须在步骤 1 (步骤 3) 创建"缩放会议"连接器的用户分配到 Exchange Online 中的"邮箱导入导出"角色。</span><span class="sxs-lookup"><span data-stu-id="9d358-134">The user who creates the Zoom Meetings connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="9d358-135">在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="9d358-135">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9d358-136">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="9d358-136">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="9d358-137">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="9d358-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="9d358-138">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="9d358-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="9d358-139">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="9d358-139">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-zoom-meetings-connector"></a><span data-ttu-id="9d358-140">步骤 1：设置缩放会议连接器</span><span class="sxs-lookup"><span data-stu-id="9d358-140">Step 1: Set up the Zoom Meetings connector</span></span>

<span data-ttu-id="9d358-141">第一步是访问 Microsoft  365 合规中心的数据连接器并创建"缩放会议"连接器。</span><span class="sxs-lookup"><span data-stu-id="9d358-141">The first step is to access the **Data Connectors** in the Microsoft 365 compliance center and create a Zoom Meetings connector.</span></span>

1. <span data-ttu-id="9d358-142">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器""**  >  **缩放会议"。**</span><span class="sxs-lookup"><span data-stu-id="9d358-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Zoom Meetings**.</span></span>

2. <span data-ttu-id="9d358-143">在"**缩放会议"** 产品说明页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="9d358-143">On the **Zoom Meetings** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="9d358-144">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="9d358-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="9d358-145">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="9d358-145">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="9d358-146">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="9d358-146">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-zoom-meetings-connector"></a><span data-ttu-id="9d358-147">步骤 2：配置缩放会议连接器</span><span class="sxs-lookup"><span data-stu-id="9d358-147">Step 2: Configure the Zoom Meetings connector</span></span>

<span data-ttu-id="9d358-148">第二步是在 Merge1 网站上配置"缩放会议"连接器。</span><span class="sxs-lookup"><span data-stu-id="9d358-148">The second step is to configure the Zoom Meetings connector on the Merge1 site.</span></span> <span data-ttu-id="9d358-149">若要详细了解如何在"一线合并"网站上配置"缩放会议"连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="9d358-149">For more information about how to configure the Zoom Meetings connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="9d358-150">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="9d358-150">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="9d358-151">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="9d358-151">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="9d358-152">在" **将外部用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="9d358-152">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="9d358-153">"缩放会议"项目包括一个称为 *"电子邮件* "的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9d358-153">Zoom Meetings items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="9d358-154">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="9d358-154">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox</span></span>

2. <span data-ttu-id="9d358-155">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="9d358-155">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-zoom-meetings-connector"></a><span data-ttu-id="9d358-156">步骤 4：监视 Zoom 会议连接器</span><span class="sxs-lookup"><span data-stu-id="9d358-156">Step 4: Monitor the Zoom Meetings connector</span></span>

<span data-ttu-id="9d358-157">创建"缩放会议"连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="9d358-157">After you create the Zoom Meetings connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="9d358-158">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="9d358-158">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9d358-159">单击" **连接器"** 选项卡，然后选择" **缩放会议** "连接器以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="9d358-159">Click the **Connectors** tab and then select the **Zoom Meetings** connector to display the flyout page.</span></span> <span data-ttu-id="9d358-160">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="9d358-160">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="9d358-161">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="9d358-161">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="9d358-162">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="9d358-162">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9d358-163">已知问题</span><span class="sxs-lookup"><span data-stu-id="9d358-163">Known issues</span></span>

- <span data-ttu-id="9d358-164">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="9d358-164">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="9d358-165">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="9d358-165">Support for larger items will be available at a later date.</span></span>

- <span data-ttu-id="9d358-166">若要使"缩放会议"连接器正常工作，必须在设置"缩放会议"时启用录制。</span><span class="sxs-lookup"><span data-stu-id="9d358-166">For the Zoom Meetings connector to work, you must enable recordings when setting up Zoom Meetings.</span></span>