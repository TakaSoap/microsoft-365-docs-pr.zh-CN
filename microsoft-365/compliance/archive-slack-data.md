---
title: 设置连接器以在 Microsoft 365 中存档 Slack 电子数据展示数据
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
description: 管理员可以设置连接器，将数据从 Globanet Slack 电子数据展示导入和存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: b6c2e49710a1c7342cfcd45c85912ba9e0dc1027
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620329"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a><span data-ttu-id="a49f6-105">设置连接器以存档 Slack 电子数据展示数据</span><span class="sxs-lookup"><span data-stu-id="a49f6-105">Set up a connector to archive Slack eDiscovery data</span></span>

<span data-ttu-id="a49f6-106">使用 Microsoft 365 合规中心中的 Globanet 连接器将社交媒体、即时消息和文档协作平台的第三方数据导入和存档到 Microsoft 365 组织的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a49f6-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive third-party data from social media, instant messaging, and document collaboration platforms to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="a49f6-107">Globanet 提供了 [一](https://globanet.com/slack/) 个 Slack 连接器，配置为定期捕获第三方数据源 (中的项目) 然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a49f6-107">Globanet provides a [Slack](https://globanet.com/slack/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="a49f6-108">Slack 从 Slack API 拉取邮件和文件，并将其转换为电子邮件格式，然后将项目导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="a49f6-108">Slack pulls messages and files from the Slack API and converts them to an email message format and then imports the item to user mailboxes.</span></span>

<span data-ttu-id="a49f6-109">Slack 电子数据展示数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="a49f6-109">After Slack eDiscovery data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="a49f6-110">使用 Slack 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="a49f6-110">Using a Slack connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-ediscovery-data"></a><span data-ttu-id="a49f6-111">Slack 电子数据展示数据的存档概述</span><span class="sxs-lookup"><span data-stu-id="a49f6-111">Overview of archiving Slack eDiscovery data</span></span>

<span data-ttu-id="a49f6-112">以下概述介绍了使用连接器在 Microsoft 365 中存档 Slack 信息的过程。</span><span class="sxs-lookup"><span data-stu-id="a49f6-112">The following overview explains the process of using a connector to archive the Slack information in Microsoft 365.</span></span>

![Slack 存档工作流](../media/SlackConnectorWorkflow.png)

1. <span data-ttu-id="a49f6-114">你的组织与 Slack 合作来设置和配置 Slack 网站。</span><span class="sxs-lookup"><span data-stu-id="a49f6-114">Your organization works with Slack to set up and configure a Slack site.</span></span>

2. <span data-ttu-id="a49f6-115">每 24 小时一次，Slack 电子数据展示中的聊天消息将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="a49f6-115">Once every 24 hours, chat messages from Slack eDiscovery are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="a49f6-116">连接器还会将聊天消息的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="a49f6-116">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="a49f6-117">你在 Microsoft 365 合规中心创建的 Slack 电子数据展示连接器每天连接到 Globanet Merge1 网站，将聊天消息转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="a49f6-117">The Slack eDiscovery connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the chat messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="a49f6-118">连接器使用 Email 属性的值和自动用户映射将转换后的聊天消息项目导入特定用户的邮箱，如步骤 3 中所述。</span><span class="sxs-lookup"><span data-stu-id="a49f6-118">The connector imports the converted chat message items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="a49f6-119">在用户邮箱中创建名为 **Slack 电子** 数据展示的收件箱文件夹中的新子文件夹，聊天消息项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="a49f6-119">A new subfolder in the Inbox folder named **Slack eDiscovery** is created in the user mailboxes, and the chat message items are imported to that folder.</span></span> <span data-ttu-id="a49f6-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="a49f6-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="a49f6-121">每个聊天消息都包含此属性，此属性用聊天消息每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="a49f6-121">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a49f6-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="a49f6-122">Before you begin</span></span>

- <span data-ttu-id="a49f6-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="a49f6-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="a49f6-124">若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="a49f6-124">To create an account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="a49f6-125">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="a49f6-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="a49f6-126">获取组织的 Slack 企业帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="a49f6-126">Obtain the username and password for your organization's Slack enterprise account.</span></span> <span data-ttu-id="a49f6-127">配置 Slack 时，需要在步骤 2 中登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="a49f6-127">You'll need to sign into this account in Step 2 when you configure Slack.</span></span>

- <span data-ttu-id="a49f6-128">在步骤 1 中创建 Slack 电子数据展示连接器 (在步骤 3) 中完成该连接器的用户必须分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="a49f6-128">The user who creates the Slack eDiscovery connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a49f6-129">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="a49f6-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a49f6-130">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="a49f6-130">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="a49f6-131">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="a49f6-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a49f6-132">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="a49f6-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a49f6-133">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="a49f6-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a><span data-ttu-id="a49f6-134">步骤 1：设置 Slack 电子数据展示连接器</span><span class="sxs-lookup"><span data-stu-id="a49f6-134">Step 1: Set up the Slack eDiscovery connector</span></span>

<span data-ttu-id="a49f6-135">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建 Slack 数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="a49f6-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Slack data.</span></span>

1. <span data-ttu-id="a49f6-136">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击数据 **连接器**  >  **Slack 电子数据展示**。</span><span class="sxs-lookup"><span data-stu-id="a49f6-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Slack eDiscovery**.</span></span>

2. <span data-ttu-id="a49f6-137">在 **Slack 电子数据展示产品** 说明页上，单击 **"添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="a49f6-137">On the **Slack eDiscovery** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="a49f6-138">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="a49f6-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="a49f6-139">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a49f6-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="a49f6-140">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="a49f6-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-slack-ediscovery"></a><span data-ttu-id="a49f6-141">步骤 2：配置 Slack 电子数据展示</span><span class="sxs-lookup"><span data-stu-id="a49f6-141">Step 2: Configure Slack eDiscovery</span></span>

<span data-ttu-id="a49f6-142">第二步是在 Merge1 网站上配置 Slack 电子数据展示连接器。</span><span class="sxs-lookup"><span data-stu-id="a49f6-142">The second step is to configure the Slack eDiscovery connector on the Merge1 site.</span></span> <span data-ttu-id="a49f6-143">若要详细了解如何在 Globanet Merge1 网站上配置 Slack 电子数据展示连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="a49f6-143">For more information about how to configure the Slack eDiscovery connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span></span>

<span data-ttu-id="a49f6-144">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="a49f6-144">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="a49f6-145">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="a49f6-145">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="a49f6-146">在 **"将外部用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="a49f6-146">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="a49f6-147">Slack 电子数据展示项目包括一个称为 *"电子邮件*"的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a49f6-147">Slack eDiscovery items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="a49f6-148">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a49f6-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="a49f6-149">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="a49f6-149">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a><span data-ttu-id="a49f6-150">步骤 4：监视 Slack 电子数据展示连接器</span><span class="sxs-lookup"><span data-stu-id="a49f6-150">Step 4: Monitor the Slack eDiscovery connector</span></span>

<span data-ttu-id="a49f6-151">创建 Slack 电子数据展示连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="a49f6-151">After you create the Slack eDiscovery connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a49f6-152">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="a49f6-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a49f6-153">单击 **"连接器"** 选项卡，然后选择 **Slack 电子数据展示** 连接器以显示该飞出页。</span><span class="sxs-lookup"><span data-stu-id="a49f6-153">Click the **Connectors** tab and then select the **Slack eDiscovery** connector to display the flyout page.</span></span> <span data-ttu-id="a49f6-154">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="a49f6-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="a49f6-155">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="a49f6-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="a49f6-156">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="a49f6-156">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a49f6-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="a49f6-157">Known issues</span></span>

- <span data-ttu-id="a49f6-158">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="a49f6-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="a49f6-159">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="a49f6-159">Support for larger items will be available at a later date.</span></span>
