---
title: 设置连接器以在 Microsoft 365 中存档 XIP 源数据
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
description: 管理员可以设置连接器以将 XIP 源数据从 Globanet 导入和存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 0af68177d51f143dd29d953050ae4e18fb8ad62d
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620188"
---
# <a name="set-up-a-connector-to-archive-xip-source-data"></a><span data-ttu-id="995db-105">设置连接器以存档 XIP 源数据</span><span class="sxs-lookup"><span data-stu-id="995db-105">Set up a connector to archive XIP source data</span></span>

<span data-ttu-id="995db-106">使用 Microsoft 365 合规中心中的 Globanet 连接器，将数据从 XIP 源平台导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="995db-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the XIP source platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="995db-107">Globanet 提供了 [一个 XIP](https://globanet.com/xip/) 连接器，允许使用 XIP 文件将项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="995db-107">Globanet provides a [XIP](https://globanet.com/xip/) connector that allows using an XIP file to import items to Microsoft 365.</span></span> <span data-ttu-id="995db-108">XIP 文件类似于 ZIP 文件，但允许使用数字签名。</span><span class="sxs-lookup"><span data-stu-id="995db-108">An XIP file is similar to a ZIP file, but allows for a digital signature to be used.</span></span> <span data-ttu-id="995db-109">在提取 XIP 源文件之前，Globanet Merge 1 会验证数字签名。</span><span class="sxs-lookup"><span data-stu-id="995db-109">The digital signature is verified by the Globanet Merge 1 before the XIP source file is extracted.</span></span> <span data-ttu-id="995db-110">连接器将 XIP 源文件中的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="995db-110">The connector converts the content from the XIP source file to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="995db-111">将 XIP 源数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="995db-111">After XIP source data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="995db-112">使用 XIP 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规策略。</span><span class="sxs-lookup"><span data-stu-id="995db-112">Using an XIP connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-xip-source-data"></a><span data-ttu-id="995db-113">对 XIP 源数据进行存档的概述</span><span class="sxs-lookup"><span data-stu-id="995db-113">Overview of archiving the XIP source data</span></span>

<span data-ttu-id="995db-114">以下概述介绍了使用连接器在 Microsoft 365 中存档 XIP 源数据的过程。</span><span class="sxs-lookup"><span data-stu-id="995db-114">The following overview explains the process of using a connector to archive the XIP source data in Microsoft 365.</span></span>

![XIP 源数据的存档工作流](../media/XIPConnectorWorkflow.png)

1. <span data-ttu-id="995db-116">您的组织与 XIP 源一起设置和配置 XIP 站点。</span><span class="sxs-lookup"><span data-stu-id="995db-116">Your organization works with the XIP source to set up and configure an XIP site.</span></span>

2. <span data-ttu-id="995db-117">每 24 小时一次，XIP 源项目将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="995db-117">Once every 24 hours, XIP source items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="995db-118">连接器还会将内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="995db-118">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="995db-119">在 Microsoft 365 合规中心创建的 XIP 连接器每天连接到 Globanet Merge1 网站，将邮件转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="995db-119">The XIP connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="995db-120">连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="995db-120">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="995db-121">在用户邮箱中创建名为 **XIP** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="995db-121">A subfolder in the Inbox folder named **XIP** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="995db-122">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="995db-122">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="995db-123">每个源项目都包含此属性，此属性用每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="995db-123">Every source item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="995db-124">开始之前</span><span class="sxs-lookup"><span data-stu-id="995db-124">Before you begin</span></span>

- <span data-ttu-id="995db-125">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="995db-125">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="995db-126">若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="995db-126">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="995db-127">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="995db-127">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="995db-128">在步骤 1 中创建 XIP 连接器 (步骤 3) 必须分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="995db-128">The user who creates the XIP connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="995db-129">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="995db-129">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="995db-130">默认情况下，此角色不会分配给 Exchange Online 中任何角色组。</span><span class="sxs-lookup"><span data-stu-id="995db-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="995db-131">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="995db-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="995db-132">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="995db-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="995db-133">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="995db-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-xip-connector"></a><span data-ttu-id="995db-134">步骤 1：设置 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="995db-134">Step 1: Set up the XIP connector</span></span>

<span data-ttu-id="995db-135">第一步是访问 Microsoft365 合规中心中的"数据连接器"页，并创建 XIP 源数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="995db-135">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the XIP source data.</span></span>

1. <span data-ttu-id="995db-136">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击"**数据连接器** \> **XIP"。**</span><span class="sxs-lookup"><span data-stu-id="995db-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **XIP**.</span></span>

2. <span data-ttu-id="995db-137">在 **"XIP** 产品说明"页上，单击 **"添加新连接器"。**</span><span class="sxs-lookup"><span data-stu-id="995db-137">On the **XIP** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="995db-138">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="995db-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="995db-139">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="995db-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="995db-140">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="995db-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-xip-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="995db-141">步骤 2：在 Globanet Merge1 网站上配置 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="995db-141">Step 2: Configure the XIP connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="995db-142">第二步是在 Merge1 网站上配置 XIP 连接器。</span><span class="sxs-lookup"><span data-stu-id="995db-142">The second step is to configure the XIP connector on the Merge1 site.</span></span> <span data-ttu-id="995db-143">若要了解如何配置 XIP 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="995db-143">For information about how to configure the XIP connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="995db-144">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="995db-144">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="995db-145">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="995db-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="995db-146">若要映射用户并完成连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="995db-146">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="995db-147">在 **"将 XIP 用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="995db-147">On the **Map XIP users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="995db-148">XIP 源项目包括一个称为 *"电子邮件*"的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="995db-148">The XIP source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="995db-149">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="995db-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="995db-150">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="995db-150">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xip-connector"></a><span data-ttu-id="995db-151">步骤 4：监视 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="995db-151">Step 4: Monitor the XIP connector</span></span>

<span data-ttu-id="995db-152">创建 XIP 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="995db-152">After you create the XIP connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="995db-153">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="995db-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="995db-154">单击 **"连接器"** 选项卡，然后选择 **XIP** 连接器以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="995db-154">Click the **Connectors** tab and then select the **XIP** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="995db-155">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="995db-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="995db-156">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="995db-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="995db-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="995db-157">Known issues</span></span>

- <span data-ttu-id="995db-158">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="995db-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="995db-159">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="995db-159">Support for larger items will be available at a later date.</span></span>
