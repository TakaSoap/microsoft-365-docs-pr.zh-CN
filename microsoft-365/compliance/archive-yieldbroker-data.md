---
title: 设置连接器以将 Yieldbroker 数据存档到 Microsoft 365
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
description: 管理员可以设置连接器以将 Yieldbroker 数据从 Microsoft 365 导入和存档。 通过此连接器，您可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 1f2ca6850057112cc0a97b08811532961a213e89
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163773"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a><span data-ttu-id="d7bf0-105">设置连接器以存档 Yieldbroker 数据</span><span class="sxs-lookup"><span data-stu-id="d7bf0-105">Set up a connector to archive Yieldbroker data</span></span>

<span data-ttu-id="d7bf0-106">使用合规性中心中的 Microsoft 365 连接器，将数据从 Yieldbroker 导入并存档到组织的用户Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Yieldbroker to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d7bf0-107">对于配置为捕获第三方数据源中的项目，以及将这些项目导入到第三方数据源的[Yieldbroker](https://globanet.com/yieldbroker/)连接器，Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-107">Veritas provides you with a [Yieldbroker](https://globanet.com/yieldbroker/) connector that's configured to capture items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="d7bf0-108">连接器将 Yieldbroker 的内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-108">The connector converts the content from Yieldbroker to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="d7bf0-109">在 Yieldbroker 存储在用户邮箱中后，Microsoft 365诉讼保留、电子数据展示、保留策略和保留标签等合规性功能。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-109">After Yieldbroker is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="d7bf0-110">使用 Yieldbroker 连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-110">Using a Yieldbroker connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-yieldbroker-data"></a><span data-ttu-id="d7bf0-111">存档 Yieldbroker 数据概述</span><span class="sxs-lookup"><span data-stu-id="d7bf0-111">Overview of archiving Yieldbroker data</span></span>

<span data-ttu-id="d7bf0-112">以下概述介绍使用连接器在数据记录中存档 Yieldbroker 数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-112">The following overview explains the process of using a connector to archive the Yieldbroker data in Microsoft 365.</span></span>

![Yieldbroker 数据的存档工作流](../media/YieldbrokerConnectorWorkflow.png)

1. <span data-ttu-id="d7bf0-114">您的组织与 Yieldbroker 合作，以设置和配置 Yieldbroker 站点。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-114">Your organization works with the Yieldbroker to set up and configure a Yieldbroker site.</span></span>

2. <span data-ttu-id="d7bf0-115">每 24 小时复制一次 Yieldbroker 项，然后复制到该"是否合并 1"网站。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-115">Once every 24 hours, Yieldbroker items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="d7bf0-116">连接器还会将内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-116">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="d7bf0-117">在 Microsoft 365 合规中心内创建的 Yieldbroker 连接器每天连接到一个 Microsoft Clouds Merge1 网站，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-117">The Yieldbroker connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d7bf0-118">连接器使用自动用户映射的 *Email* 属性值将转换后的 Yieldbroker 项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-118">The connector imports the converted Yieldbroker items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="d7bf0-119">在用户邮箱中创建名为 **Yieldbroker** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-119">A subfolder in the Inbox folder named **Yieldbroker** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="d7bf0-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="d7bf0-121">每个 Yieldbroker 都包含此属性，该属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-121">Every Yieldbroker contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d7bf0-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="d7bf0-122">Before you begin</span></span>

- <span data-ttu-id="d7bf0-123">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="d7bf0-124">若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/)</span><span class="sxs-lookup"><span data-stu-id="d7bf0-124">To create an account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="d7bf0-125">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d7bf0-126">必须在步骤 1 中创建 Yieldbroker 连接器 (在步骤 3) 中完成此连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-126">The user who creates the Yieldbroker connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d7bf0-127">若要在合规性中心的"数据连接器"页上添加连接器，Microsoft 365此角色。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d7bf0-128">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d7bf0-129">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d7bf0-130">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d7bf0-131">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-yieldbroker-connector"></a><span data-ttu-id="d7bf0-132">步骤 1：设置 Yieldbroker 连接器</span><span class="sxs-lookup"><span data-stu-id="d7bf0-132">Step 1: Set up the Yieldbroker connector</span></span>

<span data-ttu-id="d7bf0-133">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建 Yieldbroker 的连接器。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for the Yieldbroker.</span></span>

1. <span data-ttu-id="d7bf0-134">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器** &gt; **Yieldbroker**。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** &gt; **Yieldbroker**.</span></span>

2. <span data-ttu-id="d7bf0-135">在 **"Yieldbroker** 产品说明"页上，单击"**添加新连接器"。**</span><span class="sxs-lookup"><span data-stu-id="d7bf0-135">On the **Yieldbroker** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="d7bf0-136">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="d7bf0-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d7bf0-137">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="d7bf0-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-yieldbroker-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="d7bf0-139">第 2 步：配置位于以下位置的 Yieldbroker 连接器：</span><span class="sxs-lookup"><span data-stu-id="d7bf0-139">Step 2: Configure the Yieldbroker connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="d7bf0-140">第二步是在 Merge1 站点上配置 Yieldbroker 连接器。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-140">The second step is to configure the Yieldbroker connector on the Merge1 site.</span></span> <span data-ttu-id="d7bf0-141">若要了解如何配置 Yieldbroker，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="d7bf0-141">For information about how to configure the Yieldbroker, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="d7bf0-142">单击"保存&**完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="d7bf0-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="d7bf0-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="d7bf0-144">若要映射用户并完成连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d7bf0-144">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="d7bf0-145">在"**将 Yieldbroker 用户映射到用户Microsoft 365，** 启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-145">On the **Map Yieldbroker users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="d7bf0-146">Yieldbroker 项目包括一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-146">The Yieldbroker items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="d7bf0-147">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="d7bf0-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-yieldbroker-connector"></a><span data-ttu-id="d7bf0-149">步骤 4：监视 Yieldbroker 连接器</span><span class="sxs-lookup"><span data-stu-id="d7bf0-149">Step 4: Monitor the Yieldbroker connector</span></span>

<span data-ttu-id="d7bf0-150">创建 Yieldbroker 连接器后，可以在合规性中心内查看Microsoft 365状态。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-150">After you create the Yieldbroker connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d7bf0-151">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d7bf0-152">单击 **"连接器"** 选项卡，然后选择 **"Yieldbroker** 连接器"以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-152">Click the **Connectors** tab and then select the **Yieldbroker** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d7bf0-153">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d7bf0-154">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d7bf0-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="d7bf0-155">Known issues</span></span>

- <span data-ttu-id="d7bf0-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d7bf0-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="d7bf0-157">Support for larger items will be available at a later date.</span></span>