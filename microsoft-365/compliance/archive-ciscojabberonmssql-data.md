---
title: 设置连接器以将 Cisco Jabber 存档在 MS SQL数据中Microsoft 365
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
description: 管理员可以设置连接器，在 MS 上导入和存档 Cisco Jabber SQL来自 Microsoft 365。 通过此连接器，您可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 01899e4142d6e60fb10a101f7af8e9b4143a38c8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764295"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a><span data-ttu-id="b8e9b-105">设置连接器以在 MS 数据上存档 Cisco Jabber SQL数据</span><span class="sxs-lookup"><span data-stu-id="b8e9b-105">Set up a connector to archive Cisco Jabber on MS SQL data</span></span>

<span data-ttu-id="b8e9b-106">使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从 Cisco Jabber 平台导入并存档到贵组织的用户Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b8e9b-107">该连接器配置为从[Jabber](https://globanet.com/jabber/)的 MS SQL 数据库 捕获项目（如一对一聊天消息和群聊）并导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-107">Veritas provides you with a [Cisco Jabber](https://globanet.com/jabber/) connector that is configured to capture items from the Jabber's MS SQL Database, such as 1:1 chat messages and group chats and then import those items to Microsoft 365.</span></span> <span data-ttu-id="b8e9b-108">连接器从 Cisco Jabber 的 MS SQL 数据库 检索数据，处理数据，并将内容从用户的 Cisco Jabber 帐户转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-108">The connector retrieves data from the Cisco Jabber's MS SQL Database, processes it, and the converts the content from a user's Cisco Jabber account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="b8e9b-109">Cisco Jabber 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-109">After Cisco Jabber data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="b8e9b-110">使用 Cisco Jabber 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-110">Using a Cisco Jabber connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-data"></a><span data-ttu-id="b8e9b-111">存档 Cisco Jabber 数据概述</span><span class="sxs-lookup"><span data-stu-id="b8e9b-111">Overview of archiving Cisco Jabber data</span></span>

<span data-ttu-id="b8e9b-112">以下概述介绍了使用连接器在 MS 上存档 Cisco Jabber 以在 Microsoft 365 中存储SQL的过程。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-112">The following overview explains the process of using a connector to archive Cisco Jabber on MS SQL data in Microsoft 365.</span></span>

![Cisco Jabber 数据的存档工作流](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. <span data-ttu-id="b8e9b-114">你的组织与 Cisco 合作，在 MS 客户端上设置和配置 Cisco Jabber SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-114">Your organization works with Cisco to set up and configure a Cisco Jabber on MS SQL Database.</span></span>

2. <span data-ttu-id="b8e9b-115">Cisco Jabber 项目每 24 小时复制一次，从 MS SQL 数据库到"完成"合并 1 网站。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-115">Once every 24 hours, Cisco Jabber items are copied from the MS SQL Database to the Veritas Merge1 site.</span></span> <span data-ttu-id="b8e9b-116">连接器还会将聊天消息的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-116">The connector also converts the content of chat messages to an email message format.</span></span>

3. <span data-ttu-id="b8e9b-117">在 Microsoft 365 合规中心创建的 Cisco Jabber 连接器每天连接到 Microsoft 云中的一个安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-117">The Cisco Jabber connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b8e9b-118">作为连接器的自动用户映射使用步骤 [3](#step-3-map-users-and-complete-the-connector-setup)中所述 *的 Email* 属性的值将项目导入特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="b8e9b-119">在 MS 邮箱上名为 **Cisco Jabber 的**"收件箱"文件夹中SQL在用户邮箱中创建，邮件项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-119">A subfolder in the Inbox folder named **Cisco Jabber on MS SQL** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="b8e9b-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="b8e9b-121">每个 Cisco Jabber 项都包含此属性，其中填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-121">Every Cisco Jabber item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b8e9b-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="b8e9b-122">Before you begin</span></span>

- <span data-ttu-id="b8e9b-123">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="b8e9b-124">若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/)</span><span class="sxs-lookup"><span data-stu-id="b8e9b-124">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="b8e9b-125">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b8e9b-126">设置 MS SQL 数据库在步骤 1 中创建连接器之前从检索 Jabber 项目。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-126">Set up an MS SQL Database to retrieve Jabber items from before creating the connector in Step 1.</span></span> <span data-ttu-id="b8e9b-127">在步骤 2 中配置 Cisco Jabber 连接器时，SQL 数据库 MS 服务器的连接设置。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-127">You will specify the connection settings for the MS SQL Database when configuring the Cisco Jabber connector in Step 2.</span></span> <span data-ttu-id="b8e9b-128">有关详细信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-128">For more information, see the [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="b8e9b-129">必须在步骤 1 中创建 Cisco Jabber 连接器 (在步骤 3) 中完成此连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-129">The user who creates the Cisco Jabber connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b8e9b-130">若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b8e9b-131">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="b8e9b-132">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b8e9b-133">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b8e9b-134">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-134">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a><span data-ttu-id="b8e9b-135">步骤 1：在 MS 连接器上设置 Cisco Jabber SQL连接器</span><span class="sxs-lookup"><span data-stu-id="b8e9b-135">Step 1: Set up the Cisco Jabber on MS SQL connector</span></span>

<span data-ttu-id="b8e9b-136">第一步是访问 Microsoft 365 合规中心内的数据连接器，在 MS 上为 Cisco Jabber 创建SQL连接器。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-136">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for Cisco Jabber on MS SQL data.</span></span>

1. <span data-ttu-id="b8e9b-137">转到 ，然后单击 MS 上的 [https://compliance.microsoft.com](https://compliance.microsoft.com/) "数据 **连接器**  >  **""Cisco Jabber SQL"。**</span><span class="sxs-lookup"><span data-stu-id="b8e9b-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/)and then click **Data connectors** > **Cisco Jabber on MS SQL**.</span></span>

2. <span data-ttu-id="b8e9b-138">在 **MS 产品说明页上的 Cisco Jabber SQL，** 单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="b8e9b-138">On the **Cisco Jabber on MS SQL** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b8e9b-139">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="b8e9b-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b8e9b-140">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-140">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="b8e9b-141">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="b8e9b-142">步骤 2：在 Ms SQL 1 网站上配置 Cisco Jabber 连接器</span><span class="sxs-lookup"><span data-stu-id="b8e9b-142">Step 2: Configure the Cisco Jabber on MS SQL connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="b8e9b-143">第二步是在 Ms SQL Merge1 网站上配置 Cisco Jabber。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-143">The second step is to configure the Cisco Jabber on MS SQL connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="b8e9b-144">若要了解如何在 MS 连接器上配置 Cisco Jabber SQL，请参阅[Merge1 第](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)三方连接器用户指南。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-144">For information about how to configure the Cisco Jabber on MS SQL connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="b8e9b-145">单击"保存&**完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="b8e9b-146">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="b8e9b-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="b8e9b-147">若要映射用户并完成在 Microsoft 365 中心中设置的连接器，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b8e9b-147">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="b8e9b-148">在 **MS 上的 Map Cisco Jabber SQL用户Microsoft 365用户"** 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-148">On the **Map Cisco Jabber on MS SQL users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="b8e9b-149">MS 上的 Cisco Jabber SQL包含一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-149">The Cisco Jabber on MS SQL items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="b8e9b-150">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="b8e9b-151">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-151">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-connector"></a><span data-ttu-id="b8e9b-152">步骤 4：监视 Cisco Jabber 连接器</span><span class="sxs-lookup"><span data-stu-id="b8e9b-152">Step 4: Monitor the Cisco Jabber connector</span></span>

<span data-ttu-id="b8e9b-153">在 MS 连接器上创建 Cisco Jabber SQL后，可以在合规性中心查看Microsoft 365状态。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-153">After you create the Cisco Jabber on MS SQL connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b8e9b-154">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b8e9b-155">单击"**连接器"** 选项卡，然后选择 MS 连接器上的 **Cisco Jabber SQL** 显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-155">Click the **Connectors** tab and then select the **Cisco Jabber on MS SQL** connector to display the flyout page.</span></span> <span data-ttu-id="b8e9b-156">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b8e9b-157">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b8e9b-158">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-158">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b8e9b-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="b8e9b-159">Known issues</span></span>

- <span data-ttu-id="b8e9b-160">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b8e9b-161">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="b8e9b-161">Support for larger items will be available at a later date.</span></span>
