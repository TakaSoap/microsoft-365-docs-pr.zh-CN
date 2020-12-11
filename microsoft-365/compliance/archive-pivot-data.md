---
title: 设置连接器以在 Microsoft 365 中存档透视数据
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
description: 管理员可以设置连接器以在 Microsoft 365 中从 Globanet 导入和存档透视数据。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 23badcb2a8d2873f03b86499ccfd4c9a96b81090
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620369"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a><span data-ttu-id="b7a23-104">设置连接器以存档数据透视表数据</span><span class="sxs-lookup"><span data-stu-id="b7a23-104">Set up a connector to archive Pivot data</span></span>

<span data-ttu-id="b7a23-105">使用 Microsoft 365 合规中心中的 Globanet 连接器将数据从透视平台导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b7a23-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Pivot platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b7a23-106">Globanet 为您提供了一[](https://globanet.com/pivot/)个数据透视连接器，该连接器配置为定期捕获第三方数据源 (中的项目) 然后将这些项目导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b7a23-106">Globanet provides you with a [Pivot](https://globanet.com/pivot/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="b7a23-107">Pivot 是一个即时消息平台，允许与金融市场参与者进行协作。</span><span class="sxs-lookup"><span data-stu-id="b7a23-107">Pivot is an instant messaging platform that allows collaboration with financial market participants.</span></span> <span data-ttu-id="b7a23-108">连接器将聊天消息等项目从用户的透视帐户转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b7a23-108">The connector converts items such as chat messages, from a users' Pivot accounts to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="b7a23-109">在用户邮箱中存储透视数据后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="b7a23-109">After Pivot data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="b7a23-110">使用透视连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规策略。</span><span class="sxs-lookup"><span data-stu-id="b7a23-110">Using a Pivot connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-pivot-data"></a><span data-ttu-id="b7a23-111">存档数据透视表数据概述</span><span class="sxs-lookup"><span data-stu-id="b7a23-111">Overview of archiving Pivot data</span></span>

<span data-ttu-id="b7a23-112">以下概述介绍了使用连接器在 Microsoft 365 中存档数据透视表数据的过程。</span><span class="sxs-lookup"><span data-stu-id="b7a23-112">The following overview explains the process of using a connector to archive the Pivot data in Microsoft 365.</span></span>

![透视表数据的存档工作流](../media/PivotConnectorWorkflow.png)

1. <span data-ttu-id="b7a23-114">您的组织与 Pivot 一起设置和配置透视源网站。</span><span class="sxs-lookup"><span data-stu-id="b7a23-114">Your organization works with Pivot to set up and configure a Pivot source site.</span></span>

2. <span data-ttu-id="b7a23-115">每 24 小时复制一次数据透视表项到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="b7a23-115">Once every 24 hours, Pivot items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="b7a23-116">连接器还会将透视表项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="b7a23-116">The connector also converts the Pivot items to an email message format.</span></span>

3. <span data-ttu-id="b7a23-117">在 Microsoft 365 合规中心创建的透视连接器每天连接到 Globanet Merge1 网站，将透视表项目转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="b7a23-117">The Pivot connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the Pivot items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b7a23-118">连接器使用自动用户映射的 *Email* 属性值将透视项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="b7a23-118">The connector imports the Pivot items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="b7a23-119">在用户邮箱中创建名为 **Pivot** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b7a23-119">A subfolder in the Inbox folder named **Pivot** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="b7a23-120">连接器通过使用 Email *属性的值来实现* 此操作。</span><span class="sxs-lookup"><span data-stu-id="b7a23-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="b7a23-121">每个透视表项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="b7a23-121">Every Pivot item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b7a23-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="b7a23-122">Before you begin</span></span>

- <span data-ttu-id="b7a23-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="b7a23-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="b7a23-124">若要创建此帐户，请联系 [Globanet 客户支持部门](https://globanet.com/ms-connectors-contact/)。</span><span class="sxs-lookup"><span data-stu-id="b7a23-124">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="b7a23-125">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="b7a23-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b7a23-126">在步骤 1 中创建透视连接器的用户 (步骤 3) 必须分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="b7a23-126">The user who creates the Pivot connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b7a23-127">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="b7a23-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b7a23-128">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="b7a23-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="b7a23-129">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="b7a23-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b7a23-130">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="b7a23-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b7a23-131">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="b7a23-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-pivot-connector"></a><span data-ttu-id="b7a23-132">步骤 1：设置透视表连接器</span><span class="sxs-lookup"><span data-stu-id="b7a23-132">Step 1: Set up the Pivot connector</span></span>

<span data-ttu-id="b7a23-133">第一步是访问 Microsoft 合规中心中的"数据连接器"页，并创建数据透视表数据的连接器。</span><span class="sxs-lookup"><span data-stu-id="b7a23-133">The first step is to access to the **Data Connectors** page in the Microsoft compliance center and create a connector for Pivot data.</span></span>

1. <span data-ttu-id="b7a23-134">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击"**数据连接器透视**  >  **表"。**</span><span class="sxs-lookup"><span data-stu-id="b7a23-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Pivot**.</span></span>

2. <span data-ttu-id="b7a23-135">在"**数据透视** 表产品说明"页上，单击 **"添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="b7a23-135">On the **Pivot** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b7a23-136">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="b7a23-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b7a23-137">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="b7a23-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="b7a23-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="b7a23-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-pivot-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="b7a23-139">步骤 2：在 Globanet Merge1 网站上配置透视连接器</span><span class="sxs-lookup"><span data-stu-id="b7a23-139">Step 2: Configure the Pivot connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="b7a23-140">第二步是在 Merge1 网站上配置数据透视连接器。</span><span class="sxs-lookup"><span data-stu-id="b7a23-140">The second step is to configure the Pivot connector on the Merge1 site.</span></span> <span data-ttu-id="b7a23-141">若要了解如何在 Globanet Merge1 网站上配置透视连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b7a23-141">For information about how to configure the Pivot connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="b7a23-142">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="b7a23-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="b7a23-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="b7a23-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="b7a23-144">若要映射用户并完成 Microsoft 356 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b7a23-144">To map users and complete the connector setup in the Microsoft 356 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="b7a23-145">在" **将 Pivot 用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="b7a23-145">On the **Map Pivot users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="b7a23-146">透视表项目包括一个称为 *"电子邮件*"的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b7a23-146">The Pivot items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="b7a23-147">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b7a23-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="b7a23-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="b7a23-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-pivot-connector"></a><span data-ttu-id="b7a23-149">步骤 4：监视透视表连接器</span><span class="sxs-lookup"><span data-stu-id="b7a23-149">Step 4: Monitor the Pivot connector</span></span>

<span data-ttu-id="b7a23-150">创建透视连接器后，可以在 Microsoft 365 合规中心内查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="b7a23-150">After you create the Pivot connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b7a23-151">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="b7a23-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b7a23-152">单击 **"连接器"** 选项卡，然后选择 **透视** 连接器以显示飞出页。</span><span class="sxs-lookup"><span data-stu-id="b7a23-152">Click the **Connectors** tab and then select the **Pivot** connector to display the flyout page.</span></span> <span data-ttu-id="b7a23-153">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="b7a23-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b7a23-154">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="b7a23-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b7a23-155">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="b7a23-155">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b7a23-156">已知问题</span><span class="sxs-lookup"><span data-stu-id="b7a23-156">Known issues</span></span>

- <span data-ttu-id="b7a23-157">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="b7a23-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b7a23-158">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="b7a23-158">Support for larger items will be available at a later date.</span></span>
