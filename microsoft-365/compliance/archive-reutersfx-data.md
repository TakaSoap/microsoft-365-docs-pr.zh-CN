---
title: 设置连接器以在 Microsoft 365 中存档 Reuters FX 数据
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
description: 管理员可以设置连接器，以将 Globanet 中的 Reuters FX 数据导入和存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 40988b103f0130c78d9450e0ce4ea2d848c891a0
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619798"
---
# <a name="set-up-a-connector-to-archive-reuters-fx-data"></a><span data-ttu-id="ca205-105">设置连接器以存档 Reuters FX 数据</span><span class="sxs-lookup"><span data-stu-id="ca205-105">Set up a connector to archive Reuters FX data</span></span>

<span data-ttu-id="ca205-106">使用 Microsoft 365 合规中心中的 Globanet 连接器，将数据从 Reuters FX 平台导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="ca205-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters FX platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="ca205-107">Globanet 为您提供了一个配置为定期捕获第三方数据源 (中的项的 [) ](https://globanet.com/reuters-fx/) 然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ca205-107">Globanet provides you with a [Reuters FX](https://globanet.com/reuters-fx/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="ca205-108">该连接器将货币和汇率从 Reuters FX 帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="ca205-108">The connector converts the currencies and FX rates from the Reuters FX account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="ca205-109">在将 Reuters FX 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="ca205-109">After Reuters FX data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="ca205-110">使用 Reuters FX 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规政策。</span><span class="sxs-lookup"><span data-stu-id="ca205-110">Using a Reuters FX connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-fx-data"></a><span data-ttu-id="ca205-111">存档 Reuters FX 数据概述</span><span class="sxs-lookup"><span data-stu-id="ca205-111">Overview of archiving Reuters FX data</span></span>

<span data-ttu-id="ca205-112">以下概述介绍了使用连接器在 Microsoft 365 中存档 Reuters FX 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="ca205-112">The following overview explains the process of using a connector to archive Reuters FX data in Microsoft 365.</span></span>

![Archiving workflow for Reuters FX data](../media/ReutersFXConnectorWorkflow.png)

1. <span data-ttu-id="ca205-114">贵组织与 Reuters FX 合作，以设置和配置一个 Reuters FX 网站。</span><span class="sxs-lookup"><span data-stu-id="ca205-114">Your organization works with Reuters FX to set up and configure a Reuters FX site.</span></span>

2. <span data-ttu-id="ca205-115">每 24 小时一次，将一次，将一次"其他"项目复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="ca205-115">Once every 24 hours, Reuters FX items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="ca205-116">连接器还会将项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="ca205-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="ca205-117">你在 Microsoft 365 合规中心创建的 Reuters FX 连接器每天连接到 Globanet Merge1 网站，将内容转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="ca205-117">The Reuters FX connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="ca205-118">连接器使用自动用户映射的 *Email* 属性值将项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="ca205-118">The connector imports the items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="ca205-119">在用户邮箱中创建名为 **"Reuters FX"** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ca205-119">A subfolder in the Inbox folder named **Reuters FX** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="ca205-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="ca205-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="ca205-121">每个"美国"FX 项目都包含此属性，该属性填充了该项目每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ca205-121">Every Reuters FX item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ca205-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="ca205-122">Before you begin</span></span>

- <span data-ttu-id="ca205-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="ca205-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="ca205-124">若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/contact-us)。</span><span class="sxs-lookup"><span data-stu-id="ca205-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="ca205-125">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="ca205-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="ca205-126">在步骤 1 (创建并完成步骤 3) 的用户必须分配到 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="ca205-126">The user who creates the Reuters FX connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ca205-127">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="ca205-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ca205-128">默认情况下，此角色不会分配给 Exchange Online 中任何角色组。</span><span class="sxs-lookup"><span data-stu-id="ca205-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="ca205-129">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="ca205-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ca205-130">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="ca205-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ca205-131">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="ca205-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-fx-connector"></a><span data-ttu-id="ca205-132">步骤 1：设置 Connectors FX 连接器</span><span class="sxs-lookup"><span data-stu-id="ca205-132">Step 1: Set up the Reuters FX connector</span></span>

<span data-ttu-id="ca205-133">第一步是访问 Microsoft 365 中的"数据连接器"页，并创建一个 Connector for Reuters FX 数据。 </span><span class="sxs-lookup"><span data-stu-id="ca205-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters FX data.</span></span>

1. <span data-ttu-id="ca205-134">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击"**数据连接器**  >  **"。。**</span><span class="sxs-lookup"><span data-stu-id="ca205-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters FX**.</span></span>

2. <span data-ttu-id="ca205-135">在 **"单击此处的 FX** 产品说明"页上，单击 **"添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="ca205-135">On the **Reuters FX** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="ca205-136">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="ca205-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="ca205-137">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ca205-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="ca205-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="ca205-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-fx-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="ca205-139">步骤 2：在 Globanet Merge1 网站上配置一个位于其他位置的"英国"FX 连接器</span><span class="sxs-lookup"><span data-stu-id="ca205-139">Step 2: Configure the Reuters FX connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="ca205-140">第二步是在 Globanet Merge1 网站上配置 Reuters FX 连接器。</span><span class="sxs-lookup"><span data-stu-id="ca205-140">The second step is to configure the Reuters FX connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="ca205-141">有关配置 Connectors FX 连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="ca205-141">For information about configuring the Reuters FX connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="ca205-142">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="ca205-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="ca205-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="ca205-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="ca205-144">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ca205-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="ca205-145">在 **"将 Fx 用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="ca205-145">On the **Map Reuters FX users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="ca205-146">美国货币货币项目包括一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ca205-146">Reuters FX items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="ca205-147">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ca205-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="ca205-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="ca205-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-fx-connector"></a><span data-ttu-id="ca205-149">步骤 4：监视英国 FX 连接器</span><span class="sxs-lookup"><span data-stu-id="ca205-149">Step 4: Monitor the Reuters FX connector</span></span>

<span data-ttu-id="ca205-150">创建后，您可以在 Microsoft 365 合规中心内查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="ca205-150">After you create the Reuters FX connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="ca205-151">转到 <https://compliance.microsoft.com/> 左侧导航 **中的"数据连接器** "，然后单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="ca205-151">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ca205-152">单击 **"连接器"** 选项卡，然后选择 **"更新** 的 FX 连接器"以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="ca205-152">Click the **Connectors** tab and then select the **Reuters FX** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="ca205-153">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="ca205-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="ca205-154">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="ca205-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ca205-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca205-155">Known issues</span></span>

- <span data-ttu-id="ca205-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="ca205-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="ca205-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="ca205-157">Support for larger items will be available at a later date.</span></span>
