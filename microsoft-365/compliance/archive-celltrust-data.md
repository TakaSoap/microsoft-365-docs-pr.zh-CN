---
title: 设置连接器以在 Microsoft 365 中存档 CellTrust 数据
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
description: 管理员可以设置连接器以将 CellTrust 数据从 Globanet 导入和存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 59477fd413a93c70606f4059671ae771c00c8a84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919930"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a><span data-ttu-id="71517-105">设置连接器以存档 CellTrust 数据</span><span class="sxs-lookup"><span data-stu-id="71517-105">Set up a connector to archive CellTrust data</span></span>

<span data-ttu-id="71517-106">使用 Microsoft 365 合规中心中的 Globanet 连接器，将数据从 CellTrust 平台导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="71517-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the CellTrust platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="71517-107">Globanet 提供了 [CellTrust](https://globanet.com/celltrust/) 连接器，用于捕获第三方数据源中的项目，并导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="71517-107">Globanet provides a [CellTrust](https://globanet.com/celltrust/) connector that captures items from the third-party data source and imports those items to Microsoft 365.</span></span> <span data-ttu-id="71517-108">连接器将短信的内容从 CellTrust 帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="71517-108">The connector converts the content of SMS messages from CellTrust accounts to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="71517-109">将 CellTrust 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="71517-109">After CellTrust data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="71517-110">使用 CellTrust 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="71517-110">Using a CellTrust connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-celltrust-data"></a><span data-ttu-id="71517-111">存档 CellTrust 数据概述</span><span class="sxs-lookup"><span data-stu-id="71517-111">Overview of archiving CellTrust data</span></span>

<span data-ttu-id="71517-112">以下概述介绍使用连接器在 Microsoft 365 中存档 CellTrust 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="71517-112">The following overview explains the process of using a connector to archive CellTrust data in Microsoft 365.</span></span>

![CellTrust 数据的存档工作流](../media/CellTrustConnectorWorkflow.png)

1. <span data-ttu-id="71517-114">您的组织与 CellTrust 一起设置和配置 CellTrust 网站。</span><span class="sxs-lookup"><span data-stu-id="71517-114">Your organization works with CellTrust to set up and configure a CellTrust site.</span></span>

2. <span data-ttu-id="71517-115">每 24 小时一次，CellTrust 项目将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="71517-115">Once every 24 hours, CellTrust items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="71517-116">连接器还会将邮件内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="71517-116">The connector also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="71517-117">在 Microsoft 365 合规中心创建的 CellTrust 连接器每天连接到 Globanet Merge1 网站，将邮件传输至 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="71517-117">The CellTrust connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="71517-118">作为连接器的自动用户映射使用步骤 [3](#step-3-map-users-and-complete-the-connector-setup)中所述 *的 Email* 属性的值将项目导入特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="71517-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="71517-119">在用户邮箱中创建名为 **CellTrust** 的收件箱文件夹中的子文件夹，邮件项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="71517-119">A subfolder in the Inbox folder named **CellTrust** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="71517-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="71517-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="71517-121">每个 CellTrust 项目都包含此属性，该属性填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="71517-121">Every CellTrust item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="71517-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="71517-122">Before you begin</span></span>

- <span data-ttu-id="71517-123">为 Microsoft 连接器创建 Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="71517-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="71517-124">若要创建帐户，请联系 [Globanet 客户支持](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="71517-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="71517-125">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="71517-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="71517-126">必须在步骤 1 中创建 CellTrust 连接器 (在步骤 3) 中完成该连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="71517-126">The user who creates the CellTrust connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="71517-127">在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="71517-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="71517-128">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="71517-128">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="71517-129">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="71517-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="71517-130">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="71517-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="71517-131">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="71517-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-celltrust-connector"></a><span data-ttu-id="71517-132">步骤 1：设置 CellTrust 连接器</span><span class="sxs-lookup"><span data-stu-id="71517-132">Step 1: Set up the CellTrust connector</span></span>

<span data-ttu-id="71517-133">第一步是访问 Microsoft 365 合规中心内的数据连接器，并创建 CellTrust 数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="71517-133">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for CellTrust data.</span></span>

1. <span data-ttu-id="71517-134">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器""** \> **单元格信任"。**</span><span class="sxs-lookup"><span data-stu-id="71517-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **CellTrust**.</span></span>

2. <span data-ttu-id="71517-135">在 **"CellTrust** 产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="71517-135">On the **CellTrust** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="71517-136">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="71517-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="71517-137">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="71517-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="71517-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="71517-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-celltrust-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="71517-139">步骤 2：在 Globanet Merge1 网站上配置 CellTrust 连接器</span><span class="sxs-lookup"><span data-stu-id="71517-139">Step 2: Configure the CellTrust connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="71517-140">第二步是在 Globanet Merge1 网站上配置 CellTrust 连接器。</span><span class="sxs-lookup"><span data-stu-id="71517-140">The second step is to configure the CellTrust connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="71517-141">若要了解如何配置 CellTrust 连接器，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="71517-141">For information about how to configure the CellTrust connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="71517-142">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="71517-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="71517-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="71517-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="71517-144">若要映射用户并完成在 Microsoft 365 合规中心中设置的连接器，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="71517-144">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="71517-145">在" **将 CellTrust 用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="71517-145">On the **Map CellTrust users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="71517-146">CellTrust 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="71517-146">The CellTrust items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="71517-147">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="71517-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="71517-148">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="71517-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-celltrust-connector"></a><span data-ttu-id="71517-149">步骤 4：监视 CellTrust 连接器</span><span class="sxs-lookup"><span data-stu-id="71517-149">Step 4: Monitor the CellTrust connector</span></span>

<span data-ttu-id="71517-150">创建 CellTrust 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="71517-150">After you create the CellTrust connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="71517-151">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="71517-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="71517-152">单击 **"连接器"** 选项卡，然后选择 **CellTrust** 连接器以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="71517-152">Click the **Connectors** tab and then select the **CellTrust** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="71517-153">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="71517-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="71517-154">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="71517-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="71517-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="71517-155">Known issues</span></span>

- <span data-ttu-id="71517-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="71517-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="71517-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="71517-157">Support for larger items will be available at a later date.</span></span>