---
title: 设置连接器以在 Microsoft 365 中存档 EML 数据
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
description: 管理员可以设置连接器以将 EML 数据从 Globanet 导入和存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: a7495ea4accd2a40b188f92a75336f81a8f527f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924430"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a><span data-ttu-id="f5abc-105">设置连接器以存档 EML 数据</span><span class="sxs-lookup"><span data-stu-id="f5abc-105">Set up a connector to archive EML data</span></span>

<span data-ttu-id="f5abc-106">使用 Microsoft 365 合规中心中的 Globanet 连接器将 EML 数据导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="f5abc-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive EML data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="f5abc-107">EML 是保存到文件的电子邮件的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="f5abc-107">EML is the file extension for an email message saved to a file.</span></span> <span data-ttu-id="f5abc-108">连接器将项目的内容从源格式转换为电子邮件格式，然后将该项目导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="f5abc-108">The connector converts the content of an item from the source format to an email message format and then imports the item to a user mailbox.</span></span>

<span data-ttu-id="f5abc-109">在 EML 邮件存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="f5abc-109">After EML messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="f5abc-110">使用 EML 连接器在 Microsoft 365 中导入和存档数据可帮助你的组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="f5abc-110">Using an EML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-eml-data"></a><span data-ttu-id="f5abc-111">存档 EML 数据概述</span><span class="sxs-lookup"><span data-stu-id="f5abc-111">Overview of archiving EML data</span></span>

<span data-ttu-id="f5abc-112">以下概述介绍使用连接器在 Microsoft 365 中存档 EML 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="f5abc-112">The following overview explains the process of using a connector to archive EML data in Microsoft 365.</span></span>

![EML 数据的存档工作流](../media/EMLConnectorWorkflow.png)

1. <span data-ttu-id="f5abc-114">您的组织与 EML 源一起设置和配置 EML 站点。</span><span class="sxs-lookup"><span data-stu-id="f5abc-114">Your organization works with the EML source to set up and configure an EML site.</span></span>

2. <span data-ttu-id="f5abc-115">每 24 小时一次，EML 源中的内容项将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="f5abc-115">Once every 24 hours, content items from the EML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="f5abc-116">在此过程中，EML 文件的内容将转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="f5abc-116">During this process, the content of an EML file is converted to an email message format.</span></span>

3. <span data-ttu-id="f5abc-117">在 Microsoft 365 合规中心创建的 EML 连接器每天连接到 Globanet Merge1 网站，将邮件传输至 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="f5abc-117">The EML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="f5abc-118">连接器使用步骤 [3](#step-3-map-users-and-complete-the-connector-setup)中所述的自动用户映射过程的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f5abc-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping process that's described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="f5abc-119">在此过程中，在用户邮箱中创建名为 **EML** 的收件箱文件夹中的子文件夹，EML 项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="f5abc-119">During this process, a subfolder in the Inbox folder named **EML** is created in the user mailboxes, and the EML items are imported to that folder.</span></span> <span data-ttu-id="f5abc-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="f5abc-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="f5abc-121">每封邮件都包含此属性，其中填充了内容项每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f5abc-121">Every message contains this property, which is populated with the email address of every participant of the content item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f5abc-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="f5abc-122">Before you begin</span></span>

- <span data-ttu-id="f5abc-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="f5abc-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="f5abc-124">若要创建帐户，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="f5abc-124">To create an account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="f5abc-125">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="f5abc-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="f5abc-126">必须在步骤 1 (步骤 3) 创建 EML 连接器的用户分配到 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="f5abc-126">The user who creates the EML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="f5abc-127">在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="f5abc-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f5abc-128">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="f5abc-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="f5abc-129">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="f5abc-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="f5abc-130">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="f5abc-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="f5abc-131">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="f5abc-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-eml-connector"></a><span data-ttu-id="f5abc-132">步骤 1：设置 EML 连接器</span><span class="sxs-lookup"><span data-stu-id="f5abc-132">Step 1: Set up an EML Connector</span></span>

<span data-ttu-id="f5abc-133">第一步是访问 Microsoft 365 合规中心的"数据连接器"页面，并创建 EML 数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="f5abc-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for EML data.</span></span>

1. <span data-ttu-id="f5abc-134">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器**  >  **EML"。**</span><span class="sxs-lookup"><span data-stu-id="f5abc-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **EML**.</span></span>

2. <span data-ttu-id="f5abc-135">在 **"EML 产品** 说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="f5abc-135">On the **EML** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="f5abc-136">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="f5abc-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="f5abc-137">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="f5abc-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="f5abc-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="f5abc-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="f5abc-139">步骤 2：在 Globanet Merge1 网站上配置 EML 连接器</span><span class="sxs-lookup"><span data-stu-id="f5abc-139">Step 2: Configure the EML connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="f5abc-140">第二步是在 Globanet Merge1 网站上配置 EML 连接器。</span><span class="sxs-lookup"><span data-stu-id="f5abc-140">The second step is to configure the EML connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="f5abc-141">有关配置 EML 连接器的信息，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="f5abc-141">For information about configuring  the EML connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="f5abc-142">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="f5abc-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="f5abc-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="f5abc-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="f5abc-144">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f5abc-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="f5abc-145">在" **将外部用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="f5abc-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="f5abc-146">EML 源项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f5abc-146">The EML source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="f5abc-147">如果连接器可以将此地址与 Microsoft 365 用户关联，EML 项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f5abc-147">If the connector can associate this address with a Microsoft 365 user, the EML items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="f5abc-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="f5abc-148">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-eml-connector"></a><span data-ttu-id="f5abc-149">步骤 4：监视 EML 连接器</span><span class="sxs-lookup"><span data-stu-id="f5abc-149">Step 4: Monitor the EML connector</span></span>

<span data-ttu-id="f5abc-150">创建 EML 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="f5abc-150">After you create the EML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="f5abc-151">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="f5abc-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="f5abc-152">单击" **连接器"** 选项卡，然后选择 **EML** 连接器以显示飞出页。</span><span class="sxs-lookup"><span data-stu-id="f5abc-152">Click the **Connectors** tab and then select the **EML** connector to display the flyout page.</span></span> <span data-ttu-id="f5abc-153">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="f5abc-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="f5abc-154">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="f5abc-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="f5abc-155">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="f5abc-155">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f5abc-156">已知问题</span><span class="sxs-lookup"><span data-stu-id="f5abc-156">Known issues</span></span>

- <span data-ttu-id="f5abc-157">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="f5abc-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="f5abc-158">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="f5abc-158">Support for larger items will be available at a later date.</span></span>