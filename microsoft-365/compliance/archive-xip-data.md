---
title: 设置连接器以将 XIP 源数据存档在 Microsoft 365
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
description: 管理员可以设置连接器以将 XIP 源数据从 Microsoft 365 导入和存档。 通过此连接器，您可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: a3906d9a79c214ca7cfc25f868c5f24661f40004
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096632"
---
# <a name="set-up-a-connector-to-archive-xip-source-data"></a><span data-ttu-id="16cec-105">设置连接器以存档 XIP 源数据</span><span class="sxs-lookup"><span data-stu-id="16cec-105">Set up a connector to archive XIP source data</span></span>

<span data-ttu-id="16cec-106">使用 Microsoft 365 合规中心 连接器将 XIP 源平台的数据导入并存档到组织中用户Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="16cec-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the XIP source platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="16cec-107">该连接器提供了[一个 XIP](https://globanet.com/xip/)连接器，它允许使用 XIP 文件将项目导入Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="16cec-107">Veritas provides a [XIP](https://globanet.com/xip/) connector that allows using an XIP file to import items to Microsoft 365.</span></span> <span data-ttu-id="16cec-108">XIP 文件类似于 ZIP 文件，但允许使用数字签名。</span><span class="sxs-lookup"><span data-stu-id="16cec-108">An XIP file is similar to a ZIP file, but allows for a digital signature to be used.</span></span> <span data-ttu-id="16cec-109">在提取 XIP 源文件之前，该数字签名由该 XIP Merge 1 进行验证。</span><span class="sxs-lookup"><span data-stu-id="16cec-109">The digital signature is verified by Veritas Merge 1 before the XIP source file is extracted.</span></span> <span data-ttu-id="16cec-110">连接器将 XIP 源文件中的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="16cec-110">The connector converts the content from the XIP source file to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="16cec-111">XIP 源数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="16cec-111">After XIP source data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="16cec-112">使用 XIP 连接器导入数据并存档数据Microsoft 365有助于组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="16cec-112">Using an XIP connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-xip-source-data"></a><span data-ttu-id="16cec-113">对 XIP 源数据进行存档的概述</span><span class="sxs-lookup"><span data-stu-id="16cec-113">Overview of archiving the XIP source data</span></span>

<span data-ttu-id="16cec-114">以下概述介绍使用连接器在 Microsoft 365 中存档 XIP 源数据的过程。</span><span class="sxs-lookup"><span data-stu-id="16cec-114">The following overview explains the process of using a connector to archive the XIP source data in Microsoft 365.</span></span>

![XIP 源数据的存档工作流](../media/XIPConnectorWorkflow.png)

1. <span data-ttu-id="16cec-116">组织与 XIP 源一起设置和配置 XIP 站点。</span><span class="sxs-lookup"><span data-stu-id="16cec-116">Your organization works with the XIP source to set up and configure an XIP site.</span></span>

2. <span data-ttu-id="16cec-117">每 24 小时复制一次 XIP 源项，然后复制到该"是否合并 1"网站。</span><span class="sxs-lookup"><span data-stu-id="16cec-117">Once every 24 hours, XIP source items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="16cec-118">连接器还会将内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="16cec-118">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="16cec-119">在 Microsoft 云中创建的 XIP 连接器Microsoft 365 合规中心、每天连接到一个 Microsoft Merge1 网站，将邮件传输至 Microsoft 云中的Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="16cec-119">The XIP connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="16cec-120">连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="16cec-120">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="16cec-121">在用户邮箱中创建名为 **XIP** 的收件箱文件夹中的子文件夹，项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="16cec-121">A subfolder in the Inbox folder named **XIP** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="16cec-122">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="16cec-122">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="16cec-123">每个源项目都包含此属性，该属性填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="16cec-123">Every source item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="16cec-124">准备工作</span><span class="sxs-lookup"><span data-stu-id="16cec-124">Before you begin</span></span>

- <span data-ttu-id="16cec-125">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="16cec-125">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="16cec-126">若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/)</span><span class="sxs-lookup"><span data-stu-id="16cec-126">To create an account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="16cec-127">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="16cec-127">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="16cec-128">必须在步骤 1 中创建 XIP 连接器 (在步骤 3) 中完成该连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="16cec-128">The user who creates the XIP connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="16cec-129">若要在"数据连接器"页上添加连接器，需要此角色Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="16cec-129">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="16cec-130">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="16cec-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="16cec-131">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="16cec-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="16cec-132">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="16cec-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="16cec-133">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="16cec-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-xip-connector"></a><span data-ttu-id="16cec-134">步骤 1：设置 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="16cec-134">Step 1: Set up the XIP connector</span></span>

<span data-ttu-id="16cec-135">第一步是访问 Microsoft365 合规中心的"数据连接器"页，并创建 XIP 源数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="16cec-135">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the XIP source data.</span></span>

1. <span data-ttu-id="16cec-136">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器** \> **XIP**。</span><span class="sxs-lookup"><span data-stu-id="16cec-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **XIP**.</span></span>

2. <span data-ttu-id="16cec-137">在 **"XIP 产品** 说明"页上，单击"**添加新连接器"。**</span><span class="sxs-lookup"><span data-stu-id="16cec-137">On the **XIP** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="16cec-138">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="16cec-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="16cec-139">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="16cec-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="16cec-140">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="16cec-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-xip-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="16cec-141">步骤 2：在"完成"合并 1 网站中配置 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="16cec-141">Step 2: Configure the XIP connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="16cec-142">第二步是在 Merge1 网站上配置 XIP 连接器。</span><span class="sxs-lookup"><span data-stu-id="16cec-142">The second step is to configure the XIP connector on the Merge1 site.</span></span> <span data-ttu-id="16cec-143">若要了解如何配置 XIP 连接器，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="16cec-143">For information about how to configure the XIP connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="16cec-144">单击"保存 **&完成\*\*\*\*"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。</span><span class="sxs-lookup"><span data-stu-id="16cec-144">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="16cec-145">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="16cec-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="16cec-146">若要映射用户并完成连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="16cec-146">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="16cec-147">在"**将 XIP 用户映射到 Microsoft 365"页上**，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="16cec-147">On the **Map XIP users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="16cec-148">XIP 源项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="16cec-148">The XIP source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="16cec-149">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="16cec-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="16cec-150">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="16cec-150">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xip-connector"></a><span data-ttu-id="16cec-151">步骤 4：监视 XIP 连接器</span><span class="sxs-lookup"><span data-stu-id="16cec-151">Step 4: Monitor the XIP connector</span></span>

<span data-ttu-id="16cec-152">创建 XIP 连接器后，可以查看该连接器在Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="16cec-152">After you create the XIP connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="16cec-153">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="16cec-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="16cec-154">单击 **"连接器"** 选项卡，然后选择 **XIP** 连接器以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="16cec-154">Click the **Connectors** tab and then select the **XIP** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="16cec-155">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="16cec-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="16cec-156">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="16cec-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="16cec-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="16cec-157">Known issues</span></span>

- <span data-ttu-id="16cec-158">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="16cec-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="16cec-159">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="16cec-159">Support for larger items will be available at a later date.</span></span>