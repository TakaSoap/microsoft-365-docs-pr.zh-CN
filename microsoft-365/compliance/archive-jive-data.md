---
title: 设置连接器以在 Microsoft 365 中存档 Jive 数据
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
description: 管理员可以设置连接器，在 Microsoft 365 中导入和存档来自 Microsoft 365 的 Jive 数据。 此连接器允许你在 Microsoft 365 中存档第三方数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 35e6d8ee75d14943ea07fc1f6bce82f826b91297
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164234"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a><span data-ttu-id="6bfa0-104">设置连接器以存档 Jive 数据</span><span class="sxs-lookup"><span data-stu-id="6bfa0-104">Set up a connector to archive Jive data</span></span>

<span data-ttu-id="6bfa0-105">使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从协作平台导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="6bfa0-106">Microsoft 提供 [Jive](https://globanet.com/jive/) 连接器，配置为定期捕获第三方数据源 (中的项目) 然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-106">Veritas provides a [Jive](https://globanet.com/jive/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="6bfa0-107">连接器将用户 Jive 帐户中的电子邮件、聊天和附件等内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-107">The connector converts content such as email messages, chats, and attachments from a user's Jive account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="6bfa0-108">Jive 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-108">After Jive data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="6bfa0-109">使用 Jive 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-109">Using a Jive connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-jive-data"></a><span data-ttu-id="6bfa0-110">存档 Jive 数据概述</span><span class="sxs-lookup"><span data-stu-id="6bfa0-110">Overview of archiving Jive data</span></span>

<span data-ttu-id="6bfa0-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 Jive 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-111">The following overview explains the process of using a connector to archive the Jive data in Microsoft 365.</span></span>

![Jive 数据的存档工作流](../media/JiveConnectorWorkflow.png)

1. <span data-ttu-id="6bfa0-113">你的组织与 Jive 一起设置和配置 Jive 网站。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-113">Your organization works with Jive to set up and configure a Jive site.</span></span>

2. <span data-ttu-id="6bfa0-114">每 24 小时一次，Jive 中的项目将复制到"改进"合并 1 网站。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-114">Once every 24 hours, items from Jive are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="6bfa0-115">连接器还会将 Jive 项目的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-115">The connector also converts the content of Jive items to an email message format.</span></span>

3. <span data-ttu-id="6bfa0-116">在 Microsoft 365 合规中心创建的 Jive 连接器每天连接到 Microsoft Merge1 网站，将内容传输至 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-116">The Jive connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="6bfa0-117">连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-117">The connector imports the converted items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="6bfa0-118">在用户邮箱中创建名为 **Jive** 的收件箱文件夹中的新子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-118">A new subfolder in the Inbox folder named **Jive** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="6bfa0-119">连接器使用 *Email* 属性的值实现此操作。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="6bfa0-120">每个 Jive 项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-120">Every Jive item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6bfa0-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="6bfa0-121">Before you begin</span></span>

- <span data-ttu-id="6bfa0-122">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="6bfa0-123">若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/)</span><span class="sxs-lookup"><span data-stu-id="6bfa0-123">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="6bfa0-124">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="6bfa0-125">必须在步骤 1 (步骤 3) 创建 Jive 连接器的用户分配到 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-125">The user who creates the Jive connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6bfa0-126">在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6bfa0-127">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="6bfa0-128">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6bfa0-129">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6bfa0-130">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-jive-connector"></a><span data-ttu-id="6bfa0-131">步骤 1：设置 Jive 连接器</span><span class="sxs-lookup"><span data-stu-id="6bfa0-131">Step 1: Set up the Jive connector</span></span>

<span data-ttu-id="6bfa0-132">第一步是访问 Microsoft 365 合规中心的数据连接器页面，并创建 Jive 数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="6bfa0-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jive data.</span></span>

1. <span data-ttu-id="6bfa0-133">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **Jive**。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Jive**.</span></span>

2. <span data-ttu-id="6bfa0-134">在 **"Jive** 产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="6bfa0-134">On the **Jive** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="6bfa0-135">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="6bfa0-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="6bfa0-136">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="6bfa0-137">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-jive-connector"></a><span data-ttu-id="6bfa0-138">步骤 2：配置 Jive 连接器</span><span class="sxs-lookup"><span data-stu-id="6bfa0-138">Step 2: Configure the Jive connector</span></span>

<span data-ttu-id="6bfa0-139">第二步是在 Merge1 网站上配置 Jive 连接器。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-139">The second step is to configure the Jive connector on the Merge1 site.</span></span> <span data-ttu-id="6bfa0-140">若要了解如何配置 Jive 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-140">For information about how to configure the Jive connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf).</span></span>

<span data-ttu-id="6bfa0-141">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="6bfa0-142">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="6bfa0-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="6bfa0-143">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="6bfa0-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="6bfa0-144">在" **将 Jive 用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-144">On the **Map Jive users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="6bfa0-145">Jive 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-145">The Jive items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="6bfa0-146">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="6bfa0-147">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-147">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-jive-connector"></a><span data-ttu-id="6bfa0-148">步骤 4：监视 Jive 连接器</span><span class="sxs-lookup"><span data-stu-id="6bfa0-148">Step 4: Monitor the Jive connector</span></span>

<span data-ttu-id="6bfa0-149">创建 Jive 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-149">After you create the Jive connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="6bfa0-150">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-150">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="6bfa0-151">单击 **"连接器"** 选项卡，然后选择 **Jive** 连接器以显示飞出页。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-151">Click the **Connectors** tab and then select the **Jive** connector to display the flyout page.</span></span> <span data-ttu-id="6bfa0-152">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="6bfa0-153">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="6bfa0-154">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-154">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6bfa0-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="6bfa0-155">Known issues</span></span>

- <span data-ttu-id="6bfa0-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="6bfa0-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="6bfa0-157">Support for larger items will be available at a later date.</span></span>