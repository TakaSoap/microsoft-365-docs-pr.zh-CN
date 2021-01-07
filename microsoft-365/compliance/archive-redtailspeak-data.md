---
title: 设置连接器以在 Microsoft 365 中存档红色尾字数据
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
description: 管理员可以设置一个连接器，以将 Red tail Speak 数据从 Globanet 导入并存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: ff66f00348bd3e73bdbd607bd4bd0c0f922786cc
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769207"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a><span data-ttu-id="a39f4-105">设置连接器以存档 Redtail Speak 数据</span><span class="sxs-lookup"><span data-stu-id="a39f4-105">Set up a connector to archive Redtail Speak data</span></span>

<span data-ttu-id="a39f4-106">使用 Microsoft 365 合规中心中的 Globanet 连接器从 Redtail Speak 向 Microsoft 365 组织的用户邮箱导入和存档数据。</span><span class="sxs-lookup"><span data-stu-id="a39f4-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Redtail Speak to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="a39f4-107">Globanet 为您提供了一个 [Redtail Speak](https://globanet.com/redtail/) 连接器，该连接器配置为从从 Redtail 接收项目的组织的 SFTP 服务器捕获项目。</span><span class="sxs-lookup"><span data-stu-id="a39f4-107">Globanet provides you with a [Redtail Speak](https://globanet.com/redtail/) connector that's configured to capture items from your organization’s SFTP server where the items are received from Redtail.</span></span> <span data-ttu-id="a39f4-108">连接器将 Redtail Speak 中的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="a39f4-108">The connector converts the content from Redtail Speak to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="a39f4-109">Redtail Speak 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="a39f4-109">After Redtail Speak data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="a39f4-110">使用 Redtail Speak 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="a39f4-110">Using a Redtail Speak connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-redtail-speak-data"></a><span data-ttu-id="a39f4-111">存档 Redtail Speak 数据概述</span><span class="sxs-lookup"><span data-stu-id="a39f4-111">Overview of archiving the Redtail Speak data</span></span>

<span data-ttu-id="a39f4-112">以下概述介绍了使用连接器在 Microsoft 365 中存档 Redtail Speak 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="a39f4-112">The following overview explains the process of using a connector to archive the Redtail Speak data in Microsoft 365.</span></span>

![Redtail Speak 数据的存档工作流](../media/RedtailSpeakConnectorWorkflow.png)

1. <span data-ttu-id="a39f4-114">贵组织与 Redtail Speak 合作，以设置和配置 SMTP 网关，其中邮件每天从 Redtail Speak 转发到组织的 SFTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="a39f4-114">Your organization works with Redtail Speak to set up and configure an SMTP gateway where messages are forwarded from Redtail Speak to your organization's SFTP server on a daily basis.</span></span>

2. <span data-ttu-id="a39f4-115">每 24 小时一次，Redtail Speak 项目将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="a39f4-115">Once every 24 hours, the Redtail Speak items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="a39f4-116">连接器还会将 Redtail Speak 项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="a39f4-116">The connector also converts the Redtail Speak items to an email message format.</span></span>

3. <span data-ttu-id="a39f4-117">你在 Microsoft 365 合规中心创建的 Redtail Speak 连接器每天连接到 Globanet Merge1 网站，将邮件转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="a39f4-117">The Redtail Speak connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="a39f4-118">连接器使用自动用户映射的 *Email* 属性值将转换后的 Redtail Speak 项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="a39f4-118">The connector imports the converted Redtail Speak items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="a39f4-119">在用户邮箱中创建名为 **Redtail Speak** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a39f4-119">A subfolder in the Inbox folder named **Redtail Speak** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="a39f4-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="a39f4-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="a39f4-121">每个 Redtail Speak 项目都包含此属性，此属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="a39f4-121">Every Redtail Speak item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a39f4-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="a39f4-122">Before you begin</span></span>

- <span data-ttu-id="a39f4-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="a39f4-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="a39f4-124">若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="a39f4-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="a39f4-125">在步骤 1 中创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="a39f4-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="a39f4-126">在步骤 2 中，需要指定组织的 SFTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="a39f4-126">In Step 2, you need to specify your organization's SFTP server.</span></span> <span data-ttu-id="a39f4-127">此步骤是必需的，以便 Globanet Merge1 可以联系它以通过 SFTP 收集 Redtail Speak 数据。</span><span class="sxs-lookup"><span data-stu-id="a39f4-127">This step is necessary so that Globanet Merge1 can contact it to collect Redtail Speak data via SFTP.</span></span>

- <span data-ttu-id="a39f4-128">在步骤 1 (创建 Redtail Speak 导入程序连接器) 步骤 3 中完成它的用户必须分配到 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="a39f4-128">The user who creates the Redtail Speak Importer connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a39f4-129">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="a39f4-129">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a39f4-130">默认情况下，此角色不会分配给 Exchange Online 中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="a39f4-130">This role is not assigned to any role group in Exchange Online by default.</span></span> <span data-ttu-id="a39f4-131">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="a39f4-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a39f4-132">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="a39f4-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a39f4-133">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="a39f4-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-redtail-speak-connector"></a><span data-ttu-id="a39f4-134">步骤 1：设置 Redtail Speak 连接器</span><span class="sxs-lookup"><span data-stu-id="a39f4-134">Step 1: Set up the Redtail Speak connector</span></span>

<span data-ttu-id="a39f4-135">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建 Redtail Speak 数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="a39f4-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for the Redtail Speak data.</span></span>

1. <span data-ttu-id="a39f4-136">转到并选择 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 数据 **连接器** &gt; **Redtail Speak。**</span><span class="sxs-lookup"><span data-stu-id="a39f4-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and select **Data connectors** &gt; **Redtail Speak**.</span></span>

2. <span data-ttu-id="a39f4-137">在 **"Redtail Speak** 产品说明"页上，选择 **"添加新连接器"。**</span><span class="sxs-lookup"><span data-stu-id="a39f4-137">On the **Redtail Speak** product description page, select **Add new connector**.</span></span>

3. <span data-ttu-id="a39f4-138">在"**服务条款"页上**，选择"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="a39f4-138">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="a39f4-139">输入标识连接器的唯一名称，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a39f4-139">Enter a unique name that identifies the connector, and then select **Next**.</span></span>

5. <span data-ttu-id="a39f4-140">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="a39f4-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="a39f4-141">步骤 2：在 Globanet Merge1 网站上配置 Redtail Speak 连接器</span><span class="sxs-lookup"><span data-stu-id="a39f4-141">Step 2: Configure the Redtail Speak connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="a39f4-142">第二步是在 Merge1 网站上配置 Redtail Speak 连接器。</span><span class="sxs-lookup"><span data-stu-id="a39f4-142">The second step is to configure the Redtail Speak connector on the Merge1 site.</span></span> <span data-ttu-id="a39f4-143">若要了解如何配置 Redtail Speak 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="a39f4-143">For information about how to configure the Redtail Speak connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="a39f4-144">选择 **"保存**&完成"后，将显示Microsoft 365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="a39f4-144">After you select **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="a39f4-145">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="a39f4-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="a39f4-146">若要映射用户并完成连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="a39f4-146">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="a39f4-147">在 **"将用户映射到 Microsoft 365 用户** "页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="a39f4-147">On the **Map Redtail Speak users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="a39f4-148">Redtail Speak 项目包括一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a39f4-148">The Redtail Speak items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="a39f4-149">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a39f4-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="a39f4-150">选择 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="a39f4-150">Select **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-redtail-speak-connector"></a><span data-ttu-id="a39f4-151">步骤 4：监视 Redtail Speak 连接器</span><span class="sxs-lookup"><span data-stu-id="a39f4-151">Step 4: Monitor the Redtail Speak connector</span></span>

<span data-ttu-id="a39f4-152">创建 Redtail Speak 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="a39f4-152">After you create the Redtail Speak connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a39f4-153">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 左侧导航 **中并选择** 数据连接器。</span><span class="sxs-lookup"><span data-stu-id="a39f4-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and select **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a39f4-154">选择 **"连接器"** 选项卡，然后选择 **"Redtail Speak"** 连接器以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="a39f4-154">Select the **Connectors** tab and then select the **Redtail Speak** connector to display the flyout page.</span></span> <span data-ttu-id="a39f4-155">此页面显示有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="a39f4-155">This page displays properties and information about the connector.</span></span>

3. <span data-ttu-id="a39f4-156">在 **"源的** 连接器状态"下，选择"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="a39f4-156">Under **Connector status with source**, select the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="a39f4-157">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="a39f4-157">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a39f4-158">已知问题</span><span class="sxs-lookup"><span data-stu-id="a39f4-158">Known issues</span></span>

- <span data-ttu-id="a39f4-159">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="a39f4-159">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="a39f4-160">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="a39f4-160">Support for larger items will be available at a later date.</span></span>
