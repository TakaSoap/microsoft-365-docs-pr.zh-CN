---
title: 设置连接器以在 Microsoft 365 中存档安装数据
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
description: 管理员可以设置连接器，将数据从 Globanet 管理中心导入和存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 94bd9bb8f2b7586e685769af389d6cd0a0ea18ac
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619828"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a><span data-ttu-id="d5f20-105">设置连接器以存档云数据</span><span class="sxs-lookup"><span data-stu-id="d5f20-105">Set up a connector to archive Symphony data</span></span>

<span data-ttu-id="d5f20-106">使用 Microsoft 365 合规中心中的 Globanet 连接器，向 Microsoft 365 组织的用户邮箱导入和存档安装数据。</span><span class="sxs-lookup"><span data-stu-id="d5f20-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive Symphony data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d5f20-107">云是金融服务行业使用的消息和协作平台。</span><span class="sxs-lookup"><span data-stu-id="d5f20-107">Symphony is a messaging and collaboration platform used in the financial services industry.</span></span> <span data-ttu-id="d5f20-108">Globanet 在 Microsoft 365 合规中心提供一个 [可](https://globanet.com/symphony) 配置以定期捕获第三方数据源 (中的项目) 然后将这些项目导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="d5f20-108">Globanet provides a [Symphony](https://globanet.com/symphony) data connector in the Microsoft 365 compliance center that you can configure to capture items from the third-party data source (on a regular basis) and then import those items to user mailboxes.</span></span> <span data-ttu-id="d5f20-109">连接器将项目的内容从"安装时间"帐户转换为电子邮件格式，然后将该项目导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d5f20-109">The connector converts the content of an item from the Symphony account to an email message format and then imports the item to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="d5f20-110">在用户邮箱中存储了功能通信后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="d5f20-110">After Symphony communications are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="d5f20-111">使用安装连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="d5f20-111">Using a Symphony connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-symphony-data"></a><span data-ttu-id="d5f20-112">存档云数据概述</span><span class="sxs-lookup"><span data-stu-id="d5f20-112">Overview of archiving Symphony data</span></span>

<span data-ttu-id="d5f20-113">以下概述介绍了使用数据连接器在 Microsoft 365 中存档"安装"通信的过程。</span><span class="sxs-lookup"><span data-stu-id="d5f20-113">The following overview explains the process of using a data connector to archive Symphony communications in Microsoft 365.</span></span>

![分步存档工作流](../media/SymphonyConnectorWorkflow.png)

1. <span data-ttu-id="d5f20-115">你的组织与安装公司合作来设置和配置一个安装网站。</span><span class="sxs-lookup"><span data-stu-id="d5f20-115">Your organization works with Symphony to set up and configure a Symphony site.</span></span>

2. <span data-ttu-id="d5f20-116">每 24 小时一次，来自"一线"的聊天消息将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="d5f20-116">Once every 24 hours, chat messages from Symphony are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="d5f20-117">连接器还会将聊天消息的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="d5f20-117">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="d5f20-118">你在 Microsoft 365 合规中心创建的部署连接器每天连接到 Globanet Merge1 网站，将邮件转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="d5f20-118">The Symphony connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d5f20-119">连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。</span><span class="sxs-lookup"><span data-stu-id="d5f20-119">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="d5f20-120">在用户邮箱中创建名为 **"Inboxy"** 的收件箱文件夹中的新子文件夹，邮件项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5f20-120">A new subfolder in the Inbox folder named **Symphony** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="d5f20-121">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="d5f20-121">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="d5f20-122">每个聊天消息都包含此属性，此属性填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d5f20-122">Every chat message contains this property, which is populated with the email address for every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d5f20-123">开始之前</span><span class="sxs-lookup"><span data-stu-id="d5f20-123">Before you begin</span></span>

- <span data-ttu-id="d5f20-124">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="d5f20-124">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="d5f20-125">若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="d5f20-125">To create an account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="d5f20-126">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="d5f20-126">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d5f20-127">必须在步骤 1 (步骤 3 中创建并完成安装连接器) 必须分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="d5f20-127">The user who creates the Symphony connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d5f20-128">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="d5f20-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d5f20-129">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="d5f20-129">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="d5f20-130">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="d5f20-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d5f20-131">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="d5f20-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d5f20-132">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="d5f20-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-symphony-connector"></a><span data-ttu-id="d5f20-133">步骤 1：设置安装连接器</span><span class="sxs-lookup"><span data-stu-id="d5f20-133">Step 1: Set up the Symphony connector</span></span>

<span data-ttu-id="d5f20-134">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建一个连接器以用于"安全"数据。 </span><span class="sxs-lookup"><span data-stu-id="d5f20-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Symphony data.</span></span>

1. <span data-ttu-id="d5f20-135">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击"**数据连接器**  >  **安装"。**</span><span class="sxs-lookup"><span data-stu-id="d5f20-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Symphony**.</span></span>

2. <span data-ttu-id="d5f20-136">在 **"百年** 产品说明"页上，单击 **"添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="d5f20-136">On the **Symphony** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="d5f20-137">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="d5f20-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d5f20-138">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d5f20-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="d5f20-139">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="d5f20-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="d5f20-140">在 Globanet Merge1 网站上配置部署连接器</span><span class="sxs-lookup"><span data-stu-id="d5f20-140">Configure the Symphony connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="d5f20-141">第二步是在 Merge1 网站上配置安装连接器。</span><span class="sxs-lookup"><span data-stu-id="d5f20-141">The second step is to configure the Symphony connector on the Merge1 site.</span></span> <span data-ttu-id="d5f20-142">有关在 Globanet Merge1 网站上配置安装连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="d5f20-142">For information about configuring  the Symphony connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="d5f20-143">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="d5f20-143">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="d5f20-144">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="d5f20-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="d5f20-145">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d5f20-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="d5f20-146">在 **"将外部用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="d5f20-146">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="d5f20-147">该邮件包括一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d5f20-147">The Symphony items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="d5f20-148">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d5f20-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="d5f20-149">单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="d5f20-149">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-symphony-connector"></a><span data-ttu-id="d5f20-150">步骤 4：监视安装连接器</span><span class="sxs-lookup"><span data-stu-id="d5f20-150">Step 4: Monitor the Symphony connector</span></span>

<span data-ttu-id="d5f20-151">创建安装连接器后，可以在 Microsoft 365 合规中心内查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="d5f20-151">After you create the Symphony connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d5f20-152">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="d5f20-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d5f20-153">单击 **"连接器"** 选项卡，然后选择 **"安装** 连接器"以显示飞出页。</span><span class="sxs-lookup"><span data-stu-id="d5f20-153">Click the **Connectors** tab and then select the **Symphony** connector to display the flyout page.</span></span> <span data-ttu-id="d5f20-154">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="d5f20-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d5f20-155">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="d5f20-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d5f20-156">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="d5f20-156">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d5f20-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="d5f20-157">Known issues</span></span>

- <span data-ttu-id="d5f20-158">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="d5f20-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d5f20-159">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="d5f20-159">Support for larger items will be available at a later date.</span></span>
