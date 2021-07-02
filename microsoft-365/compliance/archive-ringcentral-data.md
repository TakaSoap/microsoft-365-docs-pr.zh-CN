---
title: 设置连接器以在邮箱中存档 RingCentral Microsoft 365
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
description: 管理员可以设置连接器，以将 RingCentral 数据从 Microsoft 365 导入和存档。 通过此连接器，您可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、电子数据展示和保留策略）管理第三方数据。
ms.openlocfilehash: b5e98df50b0610c9fb583a8521c7a6d6fdb48e44
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276853"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data-preview"></a><span data-ttu-id="d5584-105">设置连接器以存档 RingCentral 数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="d5584-105">Set up a connector to archive RingCentral data (preview)</span></span>

<span data-ttu-id="d5584-106">使用企业中心中的 Microsoft 365 合规中心，将数据从 RingCentral 平台导入并存档到组织Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="d5584-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the RingCentral platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d5584-107">该[连接器配置为捕获](https://www.veritas.com/insights/merge1/ringcentral)第三方数据源中的项目，并导入这些项以Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d5584-107">Veritas provides a [RingCentral](https://www.veritas.com/insights/merge1/ringcentral) connector that is configured to capture items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="d5584-108">连接器将聊天、附件、任务、笔记和帖子等内容从 RingCentral 转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="d5584-108">The connector converts content such as chats, attachments, tasks, notes, and posts from RingCentral to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="d5584-109">将 RingCentral 数据存储在用户邮箱中后，Microsoft 365诉讼保留、电子数据展示、保留策略和保留标签等合规性功能。</span><span class="sxs-lookup"><span data-stu-id="d5584-109">After RingCentral data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="d5584-110">使用 RingCentral 连接器在组织中导入和存档Microsoft 365可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="d5584-110">Using a RingCentral connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ringcentral-data"></a><span data-ttu-id="d5584-111">存档 RingCentral 数据概述</span><span class="sxs-lookup"><span data-stu-id="d5584-111">Overview of archiving RingCentral data</span></span>

<span data-ttu-id="d5584-112">以下概述介绍使用连接器在邮箱中存档 RingCentral 数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d5584-112">The following overview explains the process of using a connector to archive the RingCentral data in Microsoft 365.</span></span>

![RingCentral 数据的存档工作流](../media/RingCentralConnectorWorkflow.png)

1. <span data-ttu-id="d5584-114">你的组织与 RingCentral 一起设置和配置 RingCentral 站点。</span><span class="sxs-lookup"><span data-stu-id="d5584-114">Your organization works with RingCentral to set up and configure a RingCentral site.</span></span>

2. <span data-ttu-id="d5584-115">每 24 小时一次，将 RingCentral 项目复制到"是否合并 1"网站。</span><span class="sxs-lookup"><span data-stu-id="d5584-115">Once every 24 hours, RingCentral items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="d5584-116">连接器还会将 RingCentral 项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="d5584-116">The connector also converts RingCentral items to an email message format.</span></span>

3. <span data-ttu-id="d5584-117">在 Microsoft 365 合规中心 创建的 RingCentral 连接器，每天连接到 Microsoft 云中的 Microsoft Merge1 网站，将 RingCentral 内容传输至安全的 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="d5584-117">The RingCentral connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the RingCentral content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d5584-118">连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="d5584-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="d5584-119">在用户邮箱中创建名为 **RingCentral** 的收件箱文件夹中的子文件夹，项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5584-119">A subfolder in the Inbox folder named **RingCentral** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="d5584-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="d5584-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="d5584-121">每个 RingCentral 项目都包含此属性，该属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="d5584-121">Every RingCentral item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="d5584-122">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="d5584-122">Before you set up a connector</span></span>

- <span data-ttu-id="d5584-123">为 Microsoft 连接器创建 Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="d5584-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="d5584-124">若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/form/requestacall/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="d5584-124">To create this account, contact [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact).</span></span> <span data-ttu-id="d5584-125">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="d5584-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d5584-126">创建 RingCentral 应用程序以从 RingCentral 帐户提取数据。</span><span class="sxs-lookup"><span data-stu-id="d5584-126">Create a RingCentral application to fetch data from your RingCentral account.</span></span> <span data-ttu-id="d5584-127">有关创建应用程序的分步说明，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="d5584-127">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).</span></span>

- <span data-ttu-id="d5584-128">必须在步骤 1 中创建 RingCentral 连接器 (在步骤 3) 中完成该连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="d5584-128">The user who creates the RingCentral connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d5584-129">若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="d5584-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d5584-130">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d5584-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d5584-131">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d5584-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d5584-132">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="d5584-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d5584-133">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="d5584-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-ringcentral-connector"></a><span data-ttu-id="d5584-134">步骤 1：设置 RingCentral 连接器</span><span class="sxs-lookup"><span data-stu-id="d5584-134">Step 1: Set up the RingCentral connector</span></span>

<span data-ttu-id="d5584-135">第一步是访问数据中心中的"数据连接器"Microsoft 365 合规中心为 RingCentral 数据创建连接器。</span><span class="sxs-lookup"><span data-stu-id="d5584-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for RingCentral data.</span></span>

1. <span data-ttu-id="d5584-136">转到 ， <https://compliance.microsoft.com> 然后单击数据 **连接器**  >  **圈中心**。</span><span class="sxs-lookup"><span data-stu-id="d5584-136">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **RingCentral**.</span></span>

2. <span data-ttu-id="d5584-137">在 **"RingCentral** 产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="d5584-137">On the **RingCentral** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="d5584-138">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="d5584-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d5584-139">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="d5584-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="d5584-140">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="d5584-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a><span data-ttu-id="d5584-141">步骤 2：在"完成"合并 1 网站中配置 RingCentral</span><span class="sxs-lookup"><span data-stu-id="d5584-141">Step 2: Configure the RingCentral on the Veritas Merge1 site</span></span>

<span data-ttu-id="d5584-142">第二步是在"完成"合并 1 网站中配置 RingCentral 连接器。</span><span class="sxs-lookup"><span data-stu-id="d5584-142">The second step is to configure the RingCentral connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="d5584-143">若要了解如何配置 RingCentral 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="d5584-143">For information about how to configure the RingCentral connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).</span></span>

<span data-ttu-id="d5584-144">单击"保存&**完成"** 后，将显示连接器向导中的"用户Microsoft 365 合规中心页。</span><span class="sxs-lookup"><span data-stu-id="d5584-144">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="d5584-145">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="d5584-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="d5584-146">若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d5584-146">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="d5584-147">在"**将圈中心用户映射到Microsoft 365"页上**，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="d5584-147">On the **Map RingCentral users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="d5584-148">RingCentral 项目包括一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d5584-148">The RingCentral items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="d5584-149">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d5584-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="d5584-150">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="d5584-150">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-ringcentral-connector"></a><span data-ttu-id="d5584-151">步骤 4：监视 RingCentral 连接器</span><span class="sxs-lookup"><span data-stu-id="d5584-151">Step 4: Monitor the RingCentral connector</span></span>

<span data-ttu-id="d5584-152">创建 RingCentral 连接器后，可以查看连接器在Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="d5584-152">After you create the RingCentral connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d5584-153">转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="d5584-153">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d5584-154">单击 **"连接器"** 选项卡，然后选择 **RingCentral** 连接器以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="d5584-154">Click the **Connectors** tab and then select the **RingCentral** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d5584-155">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="d5584-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d5584-156">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="d5584-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d5584-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="d5584-157">Known issues</span></span>

- <span data-ttu-id="d5584-158">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="d5584-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d5584-159">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="d5584-159">Support for larger items will be available at a later date.</span></span>
