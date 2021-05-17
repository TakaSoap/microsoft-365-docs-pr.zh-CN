---
title: 设置连接器以在邮箱中存档Microsoft 365
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
description: 管理员可以设置一个连接器，以将数据从用户云中导入和Microsoft 365。 通过此连接器，您可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: b3ddb6826f7ef68808a819ee1d860b020efea98a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163972"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a><span data-ttu-id="39729-105">设置连接器以存档云数据</span><span class="sxs-lookup"><span data-stu-id="39729-105">Set up a connector to archive Symphony data</span></span>

<span data-ttu-id="39729-106">使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将"百年"数据导入并存档到组织Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="39729-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive Symphony data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="39729-107">百年是金融服务行业使用的消息和协作平台。</span><span class="sxs-lookup"><span data-stu-id="39729-107">Symphony is a messaging and collaboration platform used in the financial services industry.</span></span> <span data-ttu-id="39729-108">在 Microsoft 365[](https://globanet.com/symphony)合规中心中，为第三方数据源 (中定期捕获项目进行配置) 然后将这些项目导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="39729-108">Veritas provides a [Symphony](https://globanet.com/symphony) data connector in the Microsoft 365 compliance center that you can configure to capture items from the third-party data source (on a regular basis) and then import those items to user mailboxes.</span></span> <span data-ttu-id="39729-109">连接器将项目的内容从"百分百"帐户转换为电子邮件格式，然后将该项目导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="39729-109">The connector converts the content of an item from the Symphony account to an email message format and then imports the item to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="39729-110">在将百年通信存储在用户邮箱中后，你可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="39729-110">After Symphony communications are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="39729-111">使用一个百年连接器导入数据并存档Microsoft 365可帮助你的组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="39729-111">Using a Symphony connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-symphony-data"></a><span data-ttu-id="39729-112">存档百年数据概述</span><span class="sxs-lookup"><span data-stu-id="39729-112">Overview of archiving Symphony data</span></span>

<span data-ttu-id="39729-113">以下概述介绍使用数据连接器在云中存档 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="39729-113">The following overview explains the process of using a data connector to archive Symphony communications in Microsoft 365.</span></span>

![监控存档工作流](../media/SymphonyConnectorWorkflow.png)

1. <span data-ttu-id="39729-115">你的组织与用户一起设置和配置一个"百年"网站。</span><span class="sxs-lookup"><span data-stu-id="39729-115">Your organization works with Symphony to set up and configure a Symphony site.</span></span>

2. <span data-ttu-id="39729-116">每 24 小时发送一次，来自 Everyy 的聊天消息将复制到"改进""合并 1"网站。</span><span class="sxs-lookup"><span data-stu-id="39729-116">Once every 24 hours, chat messages from Symphony are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="39729-117">连接器还会将聊天消息的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="39729-117">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="39729-118">在 Microsoft 365 合规中心内创建的部署连接器每天连接到一个 Microsoft Clouds Merge1 网站，将邮件Azure 存储 Microsoft 云中的安全位置。</span><span class="sxs-lookup"><span data-stu-id="39729-118">The Symphony connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="39729-119">连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。</span><span class="sxs-lookup"><span data-stu-id="39729-119">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="39729-120">在用户邮箱中创建名为 **"Inboxy"** 的"收件箱"文件夹中的新子文件夹，邮件项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="39729-120">A new subfolder in the Inbox folder named **Symphony** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="39729-121">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="39729-121">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="39729-122">每个聊天消息都包含此属性，其中填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="39729-122">Every chat message contains this property, which is populated with the email address for every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="39729-123">开始之前</span><span class="sxs-lookup"><span data-stu-id="39729-123">Before you begin</span></span>

- <span data-ttu-id="39729-124">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="39729-124">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="39729-125">若要创建帐户，请联系["用户支持人员"。](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="39729-125">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="39729-126">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="39729-126">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="39729-127">必须在步骤 1 (步骤 3) 创建"邮箱导入导出"角色的用户分配到 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="39729-127">The user who creates the Symphony connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="39729-128">若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。</span><span class="sxs-lookup"><span data-stu-id="39729-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="39729-129">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="39729-129">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="39729-130">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="39729-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="39729-131">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="39729-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="39729-132">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="39729-132">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-symphony-connector"></a><span data-ttu-id="39729-133">步骤 1：设置安装连接器</span><span class="sxs-lookup"><span data-stu-id="39729-133">Step 1: Set up the Symphony connector</span></span>

<span data-ttu-id="39729-134">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页面，并创建一个连接器以用于"安装"数据。</span><span class="sxs-lookup"><span data-stu-id="39729-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Symphony data.</span></span>

1. <span data-ttu-id="39729-135">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"**数据连接器**  >  **""百年"。**</span><span class="sxs-lookup"><span data-stu-id="39729-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Symphony**.</span></span>

2. <span data-ttu-id="39729-136">在 **"百** 年产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="39729-136">On the **Symphony** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="39729-137">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="39729-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="39729-138">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="39729-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="39729-139">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="39729-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="configure-the-symphony-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="39729-140">在"部署合并 1"网站上配置"百年"连接器</span><span class="sxs-lookup"><span data-stu-id="39729-140">Configure the Symphony connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="39729-141">第二步是在 Merge1 网站上配置部署连接器。</span><span class="sxs-lookup"><span data-stu-id="39729-141">The second step is to configure the Symphony connector on the Merge1 site.</span></span> <span data-ttu-id="39729-142">有关在"网吧 Merge1"网站上配置"安装连接器"的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="39729-142">For information about configuring  the Symphony connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="39729-143">单击"保存&**完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="39729-143">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="39729-144">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="39729-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="39729-145">若要映射用户并完成 Microsoft 365设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="39729-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="39729-146">在"**将外部用户映射到 Microsoft 365"页上**，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="39729-146">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="39729-147">"百年"项目包含一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="39729-147">The Symphony items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="39729-148">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="39729-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="39729-149">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="39729-149">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-symphony-connector"></a><span data-ttu-id="39729-150">步骤 4：监视安装连接器</span><span class="sxs-lookup"><span data-stu-id="39729-150">Step 4: Monitor the Symphony connector</span></span>

<span data-ttu-id="39729-151">创建安装连接器后，可以在合规性中心内查看Microsoft 365状态。</span><span class="sxs-lookup"><span data-stu-id="39729-151">After you create the Symphony connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="39729-152">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="39729-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="39729-153">单击" **连接器"** 选项卡，然后选择 **"百** 年"连接器以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="39729-153">Click the **Connectors** tab and then select the **Symphony** connector to display the flyout page.</span></span> <span data-ttu-id="39729-154">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="39729-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="39729-155">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="39729-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="39729-156">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="39729-156">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="39729-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="39729-157">Known issues</span></span>

- <span data-ttu-id="39729-158">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="39729-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="39729-159">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="39729-159">Support for larger items will be available at a later date.</span></span>