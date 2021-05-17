---
title: 设置连接器以在 Microsoft 365 中存档 Reuters Eikon Microsoft 365
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
description: 管理员可以设置连接器，以从 Microsoft 365 中导入和存档来自Microsoft 365。 通过此连接器，您可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: f3e0c9d542f54a46703b4acd0c1f154d3ab84cb8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164093"
---
# <a name="set-up-a-connector-to-archive-reuters-eikon-data"></a><span data-ttu-id="0cdef-105">设置连接器以存档 Reuters Eikon 数据</span><span class="sxs-lookup"><span data-stu-id="0cdef-105">Set up a connector to archive Reuters Eikon data</span></span>

<span data-ttu-id="0cdef-106">使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从 Reuters Eikon 平台导入并存档到组织Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="0cdef-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Reuters Eikon platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="0cdef-107">该连接器配置为定期[](https://globanet.com/eikon/)捕获第三方数据源 (中的项目，) 将这些项目导入Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0cdef-107">Veritas provides a [Reuters Eikon](https://globanet.com/eikon/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="0cdef-108">连接器将用户的 Reuters Eikon 帐户的内容（如人对人消息、群聊、附件和免责声明）转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="0cdef-108">The connector converts the content such as person-to-person messages, group chats, attachments, and disclaimers from a user's Reuters Eikon account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="0cdef-109">在将 Reuters Eikon 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="0cdef-109">After Reuters Eikon data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="0cdef-110">使用 Reuters Eikon 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="0cdef-110">Using a Reuters Eikon connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-eikon-data"></a><span data-ttu-id="0cdef-111">Archiving Reuters Eikon 数据概述</span><span class="sxs-lookup"><span data-stu-id="0cdef-111">Overview of archiving Reuters Eikon data</span></span>

<span data-ttu-id="0cdef-112">以下概述说明了使用连接器在数据记录中存档 Reuters Eikon 数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0cdef-112">The following overview explains the process of using a connector to archive Reuters Eikon data in Microsoft 365.</span></span>

![用于 Reuters Eikon 数据的存档工作流](../media/ReutersEikonConnectorWorkflow.png)

1. <span data-ttu-id="0cdef-114">贵组织与 Reuters Eikon 合作，以设置和配置一个 Reuters Eikon 网站。</span><span class="sxs-lookup"><span data-stu-id="0cdef-114">Your organization works with Reuters Eikon to set up and configure a Reuters Eikon site.</span></span>

2. <span data-ttu-id="0cdef-115">每隔 24 小时一次，将 Reuters Eikon 项目复制到该"改进 24 小时"网站。</span><span class="sxs-lookup"><span data-stu-id="0cdef-115">Once every 24 hours, Reuters Eikon items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="0cdef-116">连接器还会将 Reuters Eikon 项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="0cdef-116">The connector also converts Reuters Eikon items to an email message format.</span></span>

3. <span data-ttu-id="0cdef-117">在 Microsoft 365 合规中心创建的 Reuters Eikon 连接器每天连接到一个位于 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="0cdef-117">The Reuters Eikon connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="0cdef-118">连接器使用自动用户映射的 *Email* 属性值将项目导入特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="0cdef-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="0cdef-119">"收件箱"文件夹中名为 **"Reuters Eikon"** 的子文件夹是在用户邮箱中创建的，并且项目会导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0cdef-119">A subfolder in the Inbox folder named **Reuters Eikon** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="0cdef-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="0cdef-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="0cdef-121">每个 Reuters Eikon 项目都包含此属性，该属性用该项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="0cdef-121">Every Reuters Eikon item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0cdef-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="0cdef-122">Before you begin</span></span>

- <span data-ttu-id="0cdef-123">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="0cdef-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="0cdef-124">若要创建帐户，请联系["用户支持人员"。](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="0cdef-124">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="0cdef-125">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="0cdef-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="0cdef-126">必须在步骤 1 (步骤 3) 创建一个 Reuters Eikon 连接器并将其完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="0cdef-126">The user who creates the Reuters Eikon connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="0cdef-127">若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。</span><span class="sxs-lookup"><span data-stu-id="0cdef-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0cdef-128">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0cdef-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="0cdef-129">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0cdef-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="0cdef-130">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="0cdef-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="0cdef-131">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="0cdef-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-reuters-eikon-connector"></a><span data-ttu-id="0cdef-132">步骤 1：设置 Reuters Eikon 连接器</span><span class="sxs-lookup"><span data-stu-id="0cdef-132">Step 1: Set up the Reuters Eikon connector</span></span>

<span data-ttu-id="0cdef-133">第一步是访问 Microsoft 365 合规中心的"数据连接器"页，并创建一个 Connector for Reuters Eikon 数据。</span><span class="sxs-lookup"><span data-stu-id="0cdef-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Reuters Eikon data.</span></span>

1. <span data-ttu-id="0cdef-134">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击 Data **connectors**  >  **Reuters Eikon**。</span><span class="sxs-lookup"><span data-stu-id="0cdef-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Eikon**.</span></span>

2. <span data-ttu-id="0cdef-135">在 **"Reuters Eikon** 产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="0cdef-135">On the **Reuters Eikon** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="0cdef-136">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="0cdef-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="0cdef-137">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="0cdef-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="0cdef-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="0cdef-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-eikon-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="0cdef-139">步骤 2：在"都斯合并 1"网站上配置 Reuters Eikon 连接器</span><span class="sxs-lookup"><span data-stu-id="0cdef-139">Step 2: Configure the Reuters Eikon connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="0cdef-140">第二步是在 Merge1 网站上配置 Reuters Eikon 连接器。</span><span class="sxs-lookup"><span data-stu-id="0cdef-140">The second step is to configure the Reuters Eikon connector on the Merge1 site.</span></span> <span data-ttu-id="0cdef-141">若要了解如何在"一线合并"网站上配置 Reuters Eikon 连接器，请参阅 [Merge1 第](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf)三方连接器用户指南。</span><span class="sxs-lookup"><span data-stu-id="0cdef-141">For information about how to configure the Reuters Eikon connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="0cdef-142">单击"保存&**完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="0cdef-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="0cdef-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="0cdef-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="0cdef-144">若要映射用户并完成 Microsoft 365设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="0cdef-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="0cdef-145">在"**将外部用户映射到 Microsoft 365"页上**，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="0cdef-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="0cdef-146">Reuters Eikon 项目包含一个称为 *Email* 的属性，其中包含您组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0cdef-146">The Reuters Eikon items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="0cdef-147">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="0cdef-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="0cdef-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="0cdef-148">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-eikon-connector"></a><span data-ttu-id="0cdef-149">步骤 4：监视 Reuters Eikon 连接器</span><span class="sxs-lookup"><span data-stu-id="0cdef-149">Step 4: Monitor the Reuters Eikon connector</span></span>

<span data-ttu-id="0cdef-150">创建 Reuters Eikon 连接器后，可以在合规性中心内查看Microsoft 365状态。</span><span class="sxs-lookup"><span data-stu-id="0cdef-150">After you create the Reuters Eikon connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="0cdef-151">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="0cdef-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="0cdef-152">单击" **连接器"** 选项卡，然后选择 **"Reuters Eikon"** 连接器以显示飞出页。</span><span class="sxs-lookup"><span data-stu-id="0cdef-152">Click the **Connectors** tab and then select the **Reuters Eikon** connector to display the flyout page.</span></span> <span data-ttu-id="0cdef-153">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="0cdef-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="0cdef-154">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="0cdef-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="0cdef-155">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="0cdef-155">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0cdef-156">已知问题</span><span class="sxs-lookup"><span data-stu-id="0cdef-156">Known issues</span></span>

- <span data-ttu-id="0cdef-157">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="0cdef-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="0cdef-158">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="0cdef-158">Support for larger items will be available at a later date.</span></span>