---
title: 设置连接器以将 Slack 电子数据展示数据存档在 Microsoft 365
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
description: 管理员可以设置连接器，以将数据从 Slack 电子数据展示导入和存档到Microsoft 365。 通过此连接器，您可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 48b0a6d4d5e8f6eafaaf900aa5c773cf4f99fe72
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163952"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a><span data-ttu-id="95f78-105">设置连接器以存档 Slack 电子数据展示数据</span><span class="sxs-lookup"><span data-stu-id="95f78-105">Set up a connector to archive Slack eDiscovery data</span></span>

<span data-ttu-id="95f78-106">使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将第三方数据从社交媒体、即时消息和文档协作平台导入并存档到 Microsoft 365 组织中。</span><span class="sxs-lookup"><span data-stu-id="95f78-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive third-party data from social media, instant messaging, and document collaboration platforms to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="95f78-107">对于第三方数据源[ (](https://globanet.com/slack/)项目，则配置 Slack 连接器) 然后将这些项目导入到Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="95f78-107">Veritas provides a [Slack](https://globanet.com/slack/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="95f78-108">Slack 从 Slack API 提取邮件和文件，并将其转换为电子邮件格式，然后将项目导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="95f78-108">Slack pulls messages and files from the Slack API and converts them to an email message format and then imports the item to user mailboxes.</span></span>

<span data-ttu-id="95f78-109">Slack 电子数据展示数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="95f78-109">After Slack eDiscovery data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="95f78-110">使用 Slack 连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="95f78-110">Using a Slack connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-ediscovery-data"></a><span data-ttu-id="95f78-111">存档 Slack 电子数据展示数据概述</span><span class="sxs-lookup"><span data-stu-id="95f78-111">Overview of archiving Slack eDiscovery data</span></span>

<span data-ttu-id="95f78-112">以下概述介绍使用连接器将 Slack 信息存档在 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="95f78-112">The following overview explains the process of using a connector to archive the Slack information in Microsoft 365.</span></span>

![Slack 存档工作流](../media/SlackConnectorWorkflow.png)

1. <span data-ttu-id="95f78-114">你的组织与 Slack 一起设置和配置 Slack 网站。</span><span class="sxs-lookup"><span data-stu-id="95f78-114">Your organization works with Slack to set up and configure a Slack site.</span></span>

2. <span data-ttu-id="95f78-115">每 24 小时发送一次，Slack 电子数据展示中的聊天消息会复制到"改进"功能合并 1 网站。</span><span class="sxs-lookup"><span data-stu-id="95f78-115">Once every 24 hours, chat messages from Slack eDiscovery are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="95f78-116">连接器还会将聊天消息的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="95f78-116">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="95f78-117">在 Microsoft 365 合规中心内创建的 Slack 电子数据展示连接器每天连接到一次，并会将聊天消息转移到 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="95f78-117">The Slack eDiscovery connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the chat messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="95f78-118">连接器使用 *Email* 属性的值和自动用户映射将转换后的聊天消息项目导入特定用户的邮箱，如步骤 3 中所述。</span><span class="sxs-lookup"><span data-stu-id="95f78-118">The connector imports the converted chat message items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="95f78-119">在用户邮箱中创建名为 **Slack 电子** 数据展示的"收件箱"文件夹中的新子文件夹，聊天消息项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="95f78-119">A new subfolder in the Inbox folder named **Slack eDiscovery** is created in the user mailboxes, and the chat message items are imported to that folder.</span></span> <span data-ttu-id="95f78-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="95f78-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="95f78-121">每个聊天消息都包含此属性，该属性用聊天消息每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="95f78-121">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="95f78-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="95f78-122">Before you begin</span></span>

- <span data-ttu-id="95f78-123">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="95f78-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="95f78-124">若要创建帐户，请联系["用户支持人员"。](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="95f78-124">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="95f78-125">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="95f78-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="95f78-126">获取组织的 Slack 企业帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="95f78-126">Obtain the username and password for your organization's Slack enterprise account.</span></span> <span data-ttu-id="95f78-127">配置 Slack 时，需要在步骤 2 中登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="95f78-127">You'll need to sign into this account in Step 2 when you configure Slack.</span></span>

- <span data-ttu-id="95f78-128">必须在步骤 1 中创建 Slack 电子数据展示连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="95f78-128">The user who creates the Slack eDiscovery connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="95f78-129">若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。</span><span class="sxs-lookup"><span data-stu-id="95f78-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="95f78-130">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95f78-130">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="95f78-131">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95f78-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="95f78-132">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="95f78-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="95f78-133">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="95f78-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a><span data-ttu-id="95f78-134">步骤 1：设置 Slack 电子数据展示连接器</span><span class="sxs-lookup"><span data-stu-id="95f78-134">Step 1: Set up the Slack eDiscovery connector</span></span>

<span data-ttu-id="95f78-135">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建 Slack 数据的连接器。</span><span class="sxs-lookup"><span data-stu-id="95f78-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Slack data.</span></span>

1. <span data-ttu-id="95f78-136">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **Slack 电子数据展示**。</span><span class="sxs-lookup"><span data-stu-id="95f78-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Slack eDiscovery**.</span></span>

2. <span data-ttu-id="95f78-137">在 **Slack 电子数据展示产品** 说明页面上，单击添加 **连接器**。</span><span class="sxs-lookup"><span data-stu-id="95f78-137">On the **Slack eDiscovery** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="95f78-138">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="95f78-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="95f78-139">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="95f78-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="95f78-140">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="95f78-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-slack-ediscovery"></a><span data-ttu-id="95f78-141">步骤 2：配置 Slack 电子数据展示</span><span class="sxs-lookup"><span data-stu-id="95f78-141">Step 2: Configure Slack eDiscovery</span></span>

<span data-ttu-id="95f78-142">第二步是在 Merge1 网站上配置 Slack 电子数据展示连接器。</span><span class="sxs-lookup"><span data-stu-id="95f78-142">The second step is to configure the Slack eDiscovery connector on the Merge1 site.</span></span> <span data-ttu-id="95f78-143">若要详细了解如何在"一线合并"网站上配置 Slack 电子数据展示连接器，请参阅 [Merge1 第](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)三方连接器用户指南。</span><span class="sxs-lookup"><span data-stu-id="95f78-143">For more information about how to configure the Slack eDiscovery connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span></span>

<span data-ttu-id="95f78-144">单击"保存&**完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="95f78-144">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="95f78-145">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="95f78-145">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="95f78-146">在"**将外部用户映射到 Microsoft 365"页上**，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="95f78-146">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="95f78-147">Slack 电子数据展示项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="95f78-147">Slack eDiscovery items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="95f78-148">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="95f78-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="95f78-149">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="95f78-149">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a><span data-ttu-id="95f78-150">步骤 4：监视 Slack 电子数据展示连接器</span><span class="sxs-lookup"><span data-stu-id="95f78-150">Step 4: Monitor the Slack eDiscovery connector</span></span>

<span data-ttu-id="95f78-151">创建 Slack 电子数据展示连接器后，可以在合规性中心内查看Microsoft 365状态。</span><span class="sxs-lookup"><span data-stu-id="95f78-151">After you create the Slack eDiscovery connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="95f78-152">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="95f78-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="95f78-153">单击" **连接器"** 选项卡，然后选择 **Slack 电子数据展示连接器** 以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="95f78-153">Click the **Connectors** tab and then select the **Slack eDiscovery** connector to display the flyout page.</span></span> <span data-ttu-id="95f78-154">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="95f78-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="95f78-155">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="95f78-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="95f78-156">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="95f78-156">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="95f78-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="95f78-157">Known issues</span></span>

- <span data-ttu-id="95f78-158">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="95f78-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="95f78-159">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="95f78-159">Support for larger items will be available at a later date.</span></span>