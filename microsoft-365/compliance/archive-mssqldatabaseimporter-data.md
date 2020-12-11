---
title: 设置连接器以存档 MS 数据库SQL数据
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
description: 管理员可以设置连接器以从 MS 数据库导入和存档SQL数据。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 686575877f788a2c2662024d5fac3e425d08c500
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620379"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a><span data-ttu-id="2ada4-105">设置连接器以存档 MS 数据库SQL数据</span><span class="sxs-lookup"><span data-stu-id="2ada4-105">Set up a connector to archive data from MS SQL Database</span></span>

<span data-ttu-id="2ada4-106">使用 Microsoft 365 合规中心中的 Globanet 连接器，将数据从 MS SQL 数据库导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ada4-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from MS SQL Database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="2ada4-107">Globanet 为您提供了一个 MS SQL 数据库导入程序连接器，该连接器配置为使用 XML 配置文件从数据库中捕获项目，以及将这些项目导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2ada4-107">Globanet provides you with an MS SQL Database Importer connector that's configured to capture items from a database using an XML configuration file and import those items to Microsoft 365.</span></span> <span data-ttu-id="2ada4-108">连接器将 MS SQL 数据库的内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ada4-108">The connector converts content from MS SQL Database to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="2ada4-109">MS SQL 数据库中的内容存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="2ada4-109">After content from MS SQL Database stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="2ada4-110">使用 MS SQL 数据库连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="2ada4-110">Using an MS SQL Database connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-ms-sql-data"></a><span data-ttu-id="2ada4-111">对 MS 数据库数据进行SQL概述</span><span class="sxs-lookup"><span data-stu-id="2ada4-111">Overview of archiving the MS SQL data</span></span>

<span data-ttu-id="2ada4-112">以下概述介绍了使用连接器在 Microsoft 365 中存档 MS SQL数据的过程。</span><span class="sxs-lookup"><span data-stu-id="2ada4-112">The following overview explains the process of using a connector to archive MS SQL data in Microsoft 365.</span></span>

![MS 数据库数据的存档SQL工作流](../media/MSSQLDatabaseConnectorWorkflow.png)

1. <span data-ttu-id="2ada4-114">您的组织与 MS SQL 数据库提供程序一起设置和配置 MS SQL 数据库网站。</span><span class="sxs-lookup"><span data-stu-id="2ada4-114">Your organization works with an MS SQL Database provider to set up and configure an MS SQL Database site.</span></span>

2. <span data-ttu-id="2ada4-115">每 24 小时一次，MS SQL数据库项目复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="2ada4-115">Once every 24 hours, MS SQL Database items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="2ada4-116">连接器还会将此内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="2ada4-116">The connector also converts this content to an email message format.</span></span>

3. <span data-ttu-id="2ada4-117">在 Microsoft 365 合规中心创建的 MS SQL 数据库导入程序连接器每天连接到 Globanet Merge1 网站，将邮件转移到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2ada4-117">The MS SQL Database Importer connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="2ada4-118">连接器使用自动用户映射的 Email 属性值将已转换的 MS SQL 数据库项目导入到特定用户的邮箱，如步骤[3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="2ada4-118">The connector imports the converted MS SQL Database items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="2ada4-119">收件箱文件夹中名为 MS SQL **数据库** 导入程序中的子文件夹在用户邮箱中创建，并且项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2ada4-119">A subfolder in the Inbox folder named **MS SQL Database Importer** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="2ada4-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="2ada4-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="2ada4-121">MS SQL 数据库的每一项都包含此属性，此属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="2ada4-121">Every item from the MS SQL Database contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2ada4-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="2ada4-122">Before you begin</span></span>

- <span data-ttu-id="2ada4-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="2ada4-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="2ada4-124">若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="2ada4-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="2ada4-125">在步骤 1 中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="2ada4-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="2ada4-126">在步骤 1 (中创建 MS SQL 数据库导入程序连接器并将其在步骤 3) 中完成的用户必须分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="2ada4-126">The user who creates the MS SQL Database Importer connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="2ada4-127">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="2ada4-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2ada4-128">默认情况下，此角色不会分配给 Exchange Online 中任何角色组。</span><span class="sxs-lookup"><span data-stu-id="2ada4-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="2ada4-129">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="2ada4-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="2ada4-130">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="2ada4-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="2ada4-131">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="2ada4-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a><span data-ttu-id="2ada4-132">步骤 1：设置 MS SQL数据库导入程序连接器</span><span class="sxs-lookup"><span data-stu-id="2ada4-132">Step 1: Set up the MS SQL Database Importer connector</span></span>

<span data-ttu-id="2ada4-133">第一步是访问 Microsoft365 合规中心中的"数据连接器"页，并创建 MS SQL 数据库的连接器。 </span><span class="sxs-lookup"><span data-stu-id="2ada4-133">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the MS SQL Database.</span></span>

1. <span data-ttu-id="2ada4-134">转到" [https://compliance.microsoft.com](https://compliance.microsoft.com) 数据库导入程序  >  **"，SQL"数据连接器"。**</span><span class="sxs-lookup"><span data-stu-id="2ada4-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** > **MS SQL Database Importer**.</span></span>

2. <span data-ttu-id="2ada4-135">在 **"MS SQL导入** 程序产品说明"页上，单击 **"添加新连接器"。**</span><span class="sxs-lookup"><span data-stu-id="2ada4-135">On the **MS SQL Database Importer** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="2ada4-136">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="2ada4-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="2ada4-137">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2ada4-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="2ada4-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="2ada4-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="2ada4-139">步骤 2：在 Globanet Merge1 SQL配置 MS 数据库导入程序连接器</span><span class="sxs-lookup"><span data-stu-id="2ada4-139">Step 2: Configure the MS SQL Database Importer connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="2ada4-140">第二步是在 Merge1 SQL配置 MS 数据库导入程序连接器。</span><span class="sxs-lookup"><span data-stu-id="2ada4-140">The second step is to configure the MS SQL Database Importer connector on the Merge1 site.</span></span> <span data-ttu-id="2ada4-141">若要了解如何配置 MS 数据库导入SQL，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="2ada4-141">For information about how to configure the MS SQL Database Importer, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="2ada4-142">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="2ada4-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="2ada4-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="2ada4-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="2ada4-144">若要映射用户并完成连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="2ada4-144">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="2ada4-145">在 **"将 MS SQL数据库导入程序用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="2ada4-145">On the **Map MS SQL Database Importer users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="2ada4-146">MS SQL 数据库项目包括一个称为 *"电子邮件*"的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2ada4-146">The MS SQL Database items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="2ada4-147">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ada4-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="2ada4-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="2ada4-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a><span data-ttu-id="2ada4-149">步骤 4：监视 MS SQL数据库导入程序连接器</span><span class="sxs-lookup"><span data-stu-id="2ada4-149">Step 4: Monitor the MS SQL Database Importer connector</span></span>

<span data-ttu-id="2ada4-150">创建 MS SQL数据库导入程序连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="2ada4-150">After you create the MS SQL Database Importer connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="2ada4-151">转到 <https://compliance.microsoft.com/> 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="2ada4-151">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="2ada4-152">单击 **"连接器"** 选项卡，然后选择 **"MS SQL 数据库** 导入程序连接器"以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="2ada4-152">Click the **Connectors** tab and then select the **MS SQL Database** **Importer** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="2ada4-153">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="2ada4-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="2ada4-154">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="2ada4-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2ada4-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="2ada4-155">Known issues</span></span>

- <span data-ttu-id="2ada4-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="2ada4-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="2ada4-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="2ada4-157">Support for larger items will be available at a later date.</span></span>
