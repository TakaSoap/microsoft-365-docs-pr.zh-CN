---
title: 设置连接器以在 Microsoft 365 中存档 Reuters 交易数据
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
description: 管理员可以设置连接器，将 Globanet 中的处理数据导入并存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 24ecbc8a6073835e45958191c87f95854fee8db1
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619968"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data"></a><span data-ttu-id="77d0d-105">设置连接器以存档 Reuters 交易数据</span><span class="sxs-lookup"><span data-stu-id="77d0d-105">Set up a connector to archive Reuters Dealing data</span></span>

<span data-ttu-id="77d0d-106">使用 Microsoft 365 合规中心中的 Globanet 连接器，将数据从"Reuters 处理"平台导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="77d0d-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters Dealing platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="77d0d-107">Globanet 为您提供了一个配置为定期捕获第三方数据源 (中的项目，然后将这些项导入到 Microsoft 365 的 [") "](https://globanet.com/reuters-dealing/) 处理连接器。</span><span class="sxs-lookup"><span data-stu-id="77d0d-107">Globanet provides you with a [Reuters Dealing](https://globanet.com/reuters-dealing/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="77d0d-108">该连接器将处理通信从"其他客户"帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="77d0d-108">The connector converts Dealing communications from the Reuters Dealing account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="77d0d-109">在将处理数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="77d0d-109">After Reuters Dealing data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="77d0d-110">使用 Reuters 处理连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规政策。</span><span class="sxs-lookup"><span data-stu-id="77d0d-110">Using a Reuters Dealing connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-dealing-data"></a><span data-ttu-id="77d0d-111">Archiving Reuters Dealing data 概述</span><span class="sxs-lookup"><span data-stu-id="77d0d-111">Overview of archiving Reuters Dealing data</span></span>

<span data-ttu-id="77d0d-112">以下概述介绍了使用连接器在 Microsoft 365 中存档"Reuters 交易"数据的过程。</span><span class="sxs-lookup"><span data-stu-id="77d0d-112">The following overview explains the process of using a connector to archive the Reuters Dealing data in Microsoft 365.</span></span>

![Archiving workflow for Reuters Dealing data](../media/ReuetersDealingConnectorWorkflow.png)

1. <span data-ttu-id="77d0d-114">你的组织与一起处理，以设置和配置一个一个"一些处理"网站。</span><span class="sxs-lookup"><span data-stu-id="77d0d-114">Your organization works with Reuters Dealing to set up and configure a Reuters Dealing site.</span></span>

2. <span data-ttu-id="77d0d-115">每 24 小时一次，将一次，将一些处理项目复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="77d0d-115">Once every 24 hours, Reuters Dealing items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="77d0d-116">连接器还会将项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="77d0d-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="77d0d-117">你在 Microsoft 365 合规中心创建的 Connector 每天连接到 Globanet Merge1 网站，将内容转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="77d0d-117">The Reuters Dealing connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="77d0d-118">连接器使用自动用户映射的 *Email* 属性值将项目导入特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="77d0d-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="77d0d-119">在用户邮箱中创建名为 **"Reuters Dealing"** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="77d0d-119">A subfolder in the Inbox folder named **Reuters Dealing** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="77d0d-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="77d0d-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="77d0d-121">每个一项的处理项目都包含此属性，该属性用该项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="77d0d-121">Every Reuters Dealing item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="77d0d-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="77d0d-122">Before you begin</span></span>

- <span data-ttu-id="77d0d-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="77d0d-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="77d0d-124">若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/contact-us)。</span><span class="sxs-lookup"><span data-stu-id="77d0d-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="77d0d-125">在步骤 1 中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="77d0d-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="77d0d-126">在步骤 1 (创建并完成步骤 3) 的用户必须分配到 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="77d0d-126">The user who creates the Reuters Dealing connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="77d0d-127">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="77d0d-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="77d0d-128">默认情况下，此角色不会分配给 Exchange Online 中任何角色组。</span><span class="sxs-lookup"><span data-stu-id="77d0d-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="77d0d-129">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="77d0d-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="77d0d-130">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="77d0d-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="77d0d-131">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="77d0d-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-dealing-connector"></a><span data-ttu-id="77d0d-132">步骤 1：设置 Reuters 处理连接器</span><span class="sxs-lookup"><span data-stu-id="77d0d-132">Step 1: Set up the Reuters Dealing connector</span></span>

<span data-ttu-id="77d0d-133">第一步是访问 Microsoft 365 中的"数据连接器"页，并创建一个 Connector for Reuters Dealing 数据。 </span><span class="sxs-lookup"><span data-stu-id="77d0d-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters Dealing data.</span></span>

1. <span data-ttu-id="77d0d-134">转到， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击 **数据连接器**  >  **。。**</span><span class="sxs-lookup"><span data-stu-id="77d0d-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Dealing**.</span></span>

2. <span data-ttu-id="77d0d-135">在 **"处理产品说明**"页上，单击 **"添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="77d0d-135">On the **Reuters Dealing** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="77d0d-136">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="77d0d-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="77d0d-137">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="77d0d-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="77d0d-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="77d0d-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="77d0d-139">步骤 2：在 Globanet Merge1 网站上配置 Reuters 处理连接器</span><span class="sxs-lookup"><span data-stu-id="77d0d-139">Step 2: Configure the Reuters Dealing connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="77d0d-140">第二步是在 Globanet 上的 Merge1 网站上配置 Reuters 处理连接器。</span><span class="sxs-lookup"><span data-stu-id="77d0d-140">The second step is to configure the Reuters Dealing connector on Globanet the Merge1 site.</span></span> <span data-ttu-id="77d0d-141">有关配置 Connectors 处理连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="77d0d-141">For information about configuring the Reuters Dealing connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="77d0d-142">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="77d0d-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="77d0d-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="77d0d-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="77d0d-144">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="77d0d-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="77d0d-145">在 **"将用户与 Microsoft 365 用户进行交易** "页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="77d0d-145">On the **Map Reuters Dealing users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="77d0d-146">处理项目包括一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="77d0d-146">Reuters Dealing items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="77d0d-147">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="77d0d-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="77d0d-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="77d0d-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-dealing-connector"></a><span data-ttu-id="77d0d-149">步骤 4：监视"中国处理"连接器</span><span class="sxs-lookup"><span data-stu-id="77d0d-149">Step 4: Monitor the Reuters Dealing connector</span></span>

<span data-ttu-id="77d0d-150">创建后，您可以在 Microsoft 365 合规中心内查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="77d0d-150">After you create the Reuters Dealing connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="77d0d-151">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="77d0d-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="77d0d-152">单击 **"连接器"** 选项卡，然后选择 **"Connectors 处理** 连接器"以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="77d0d-152">Click the **Connectors** tab and then select the **Reuters Dealing** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="77d0d-153">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="77d0d-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="77d0d-154">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="77d0d-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="77d0d-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="77d0d-155">Known issues</span></span>

- <span data-ttu-id="77d0d-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="77d0d-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="77d0d-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="77d0d-157">Support for larger items will be available at a later date.</span></span>
