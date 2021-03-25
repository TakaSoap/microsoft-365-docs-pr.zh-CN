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
description: 管理员可以设置连接器，以将来自 Microsoft 365 的 Reuters 交易数据导入和存档。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 8625ea5e90304287955c357cca3036f9863f9ba5
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164123"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data"></a><span data-ttu-id="8d212-105">设置连接器以存档 Reuters 交易数据</span><span class="sxs-lookup"><span data-stu-id="8d212-105">Set up a connector to archive Reuters Dealing data</span></span>

<span data-ttu-id="8d212-106">使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从 Reuters 处理平台导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="8d212-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Reuters Dealing platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="8d212-107">对于配置为定期捕获第三方数据源 (中的项目，) 然后将这些项目导入到 Microsoft 365 的 [一个显示](https://globanet.com/reuters-dealing/) 连接器。</span><span class="sxs-lookup"><span data-stu-id="8d212-107">Veritas provides you with a [Reuters Dealing](https://globanet.com/reuters-dealing/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="8d212-108">连接器将处理通信从 Reuters 处理帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="8d212-108">The connector converts Dealing communications from the Reuters Dealing account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="8d212-109">在 Reuters 处理数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="8d212-109">After Reuters Dealing data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="8d212-110">使用 Reuters 处理连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="8d212-110">Using a Reuters Dealing connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-dealing-data"></a><span data-ttu-id="8d212-111">Archiving Reuters Dealing data 概述</span><span class="sxs-lookup"><span data-stu-id="8d212-111">Overview of archiving Reuters Dealing data</span></span>

<span data-ttu-id="8d212-112">以下概述介绍了使用连接器在 Microsoft 365 中存档 Reuters 交易数据的过程。</span><span class="sxs-lookup"><span data-stu-id="8d212-112">The following overview explains the process of using a connector to archive the Reuters Dealing data in Microsoft 365.</span></span>

![Archiving workflow for Reuters Dealing data](../media/ReuetersDealingConnectorWorkflow.png)

1. <span data-ttu-id="8d212-114">您的组织与 Reuters Dealing 合作，以设置和配置一个 Reuters 处理网站。</span><span class="sxs-lookup"><span data-stu-id="8d212-114">Your organization works with Reuters Dealing to set up and configure a Reuters Dealing site.</span></span>

2. <span data-ttu-id="8d212-115">一次每 24 小时一次，Reuters 处理项目将复制到"是否合并 1"网站。</span><span class="sxs-lookup"><span data-stu-id="8d212-115">Once every 24 hours, Reuters Dealing items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="8d212-116">连接器还会将项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="8d212-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="8d212-117">你在 Microsoft 365 合规中心创建的 Reuters 处理连接器每天连接到一个 Microsoft Merge1 网站，将内容转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="8d212-117">The Reuters Dealing connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="8d212-118">连接器使用自动用户映射的 *Email* 属性值将项目导入特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="8d212-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="8d212-119">在用户邮箱中创建名为 **"Reuters Dealing"** 的"收件箱"文件夹中的子文件夹，项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="8d212-119">A subfolder in the Inbox folder named **Reuters Dealing** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="8d212-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="8d212-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="8d212-121">每个 Reuters 处理项目都包含此属性，该属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="8d212-121">Every Reuters Dealing item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8d212-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="8d212-122">Before you begin</span></span>

- <span data-ttu-id="8d212-123">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="8d212-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="8d212-124">若要创建帐户，请联系["用户支持人员"。](https://globanet.com/contact-us)</span><span class="sxs-lookup"><span data-stu-id="8d212-124">To create an account, contact [Veritas Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="8d212-125">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="8d212-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="8d212-126">必须在步骤 1 (步骤 3) 创建并完成该连接器的用户分配到 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="8d212-126">The user who creates the Reuters Dealing connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8d212-127">在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="8d212-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8d212-128">默认情况下，此角色不会分配给 Exchange Online 中任何角色组。</span><span class="sxs-lookup"><span data-stu-id="8d212-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8d212-129">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="8d212-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8d212-130">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="8d212-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8d212-131">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="8d212-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-dealing-connector"></a><span data-ttu-id="8d212-132">步骤 1：设置 Reuters 处理连接器</span><span class="sxs-lookup"><span data-stu-id="8d212-132">Step 1: Set up the Reuters Dealing connector</span></span>

<span data-ttu-id="8d212-133">第一步是访问 Microsoft 365 中的"数据连接器"页，并创建一个 Connector for Reuters Dealing data。 </span><span class="sxs-lookup"><span data-stu-id="8d212-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters Dealing data.</span></span>

1. <span data-ttu-id="8d212-134">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器""**  >  **数据连接器""处理"。**</span><span class="sxs-lookup"><span data-stu-id="8d212-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Dealing**.</span></span>

2. <span data-ttu-id="8d212-135">在 **"Reuters 处理产品** 说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="8d212-135">On the **Reuters Dealing** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="8d212-136">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="8d212-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="8d212-137">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="8d212-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="8d212-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="8d212-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="8d212-139">步骤 2：在"完成"合并 1 网站中配置"Reuters 处理"连接器</span><span class="sxs-lookup"><span data-stu-id="8d212-139">Step 2: Configure the Reuters Dealing connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="8d212-140">第二步是在"Merge1"网站上配置"Reuters 处理连接器"。</span><span class="sxs-lookup"><span data-stu-id="8d212-140">The second step is to configure the Reuters Dealing connector on Veritas the Merge1 site.</span></span> <span data-ttu-id="8d212-141">有关配置 Reuters 处理连接器的信息，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="8d212-141">For information about configuring the Reuters Dealing connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="8d212-142">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="8d212-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="8d212-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="8d212-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="8d212-144">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8d212-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="8d212-145">在 **"Map Reuters Dealing users to Microsoft 365 users"** 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="8d212-145">On the **Map Reuters Dealing users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="8d212-146">Reuters 交易项目包括一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8d212-146">Reuters Dealing items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="8d212-147">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8d212-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="8d212-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="8d212-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-dealing-connector"></a><span data-ttu-id="8d212-149">第 4 步：监视"视频处理"连接器</span><span class="sxs-lookup"><span data-stu-id="8d212-149">Step 4: Monitor the Reuters Dealing connector</span></span>

<span data-ttu-id="8d212-150">创建 Reuters 处理连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="8d212-150">After you create the Reuters Dealing connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="8d212-151">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="8d212-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8d212-152">单击 **"连接器"** 选项卡，然后选择 **"Reuters 处理** 连接器"以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="8d212-152">Click the **Connectors** tab and then select the **Reuters Dealing** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="8d212-153">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="8d212-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="8d212-154">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="8d212-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8d212-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="8d212-155">Known issues</span></span>

- <span data-ttu-id="8d212-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="8d212-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="8d212-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="8d212-157">Support for larger items will be available at a later date.</span></span>