---
title: 设置连接器以在 Skype for Business中存档Microsoft 365
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
description: 了解如何在 Microsoft 365 合规中心 中设置和使用连接器，以将数据从 Skype for Business 导入Microsoft 365。
ms.openlocfilehash: 93128af0c7f305cb2bef55efd5520de77555a222
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054810"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data-preview"></a><span data-ttu-id="e3fba-103">设置连接器以存档Skype for Business数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="e3fba-103">Set up a connector to archive Skype for Business data (preview)</span></span>

<span data-ttu-id="e3fba-104">使用 Microsoft 365 合规中心 中的一个 Skype for Business 连接器，将数据从 Skype for Business 平台导入并存档到组织Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="e3fba-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Skype for Business platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="e3fba-105">该[连接器Skype for Business连接器](https://www.veritas.com/en/au/insights/merge1/skype-for-business)，配置为定期捕获第三方数据源 (中的项目，) 将这些项目导入Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e3fba-105">Veritas provides a [Skype for Business](https://www.veritas.com/en/au/insights/merge1/skype-for-business) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="e3fba-106">连接器将用户之间的消息、持久聊天和会议消息等内容从 Skype for Business 转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="e3fba-106">The connector converts the content such as messages between users, persistent chats, and conference messages from Skype for Business to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="e3fba-107">在Skype for Business邮箱中存储数据后，可以应用Microsoft 365保留、电子数据展示、保留策略和保留标签等合规性功能。</span><span class="sxs-lookup"><span data-stu-id="e3fba-107">After Skype for Business data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="e3fba-108">使用 Skype for Business 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="e3fba-108">Using a Skype for Business connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-skype-for-business-data"></a><span data-ttu-id="e3fba-109">存档数据Skype for Business概述</span><span class="sxs-lookup"><span data-stu-id="e3fba-109">Overview of archiving Skype for Business data</span></span>

<span data-ttu-id="e3fba-110">以下概述介绍使用连接器在 Microsoft 365 中Skype for Business数据的过程。</span><span class="sxs-lookup"><span data-stu-id="e3fba-110">The following overview explains the process of using a connector to archive the Skype for Business data in Microsoft 365.</span></span>

![存档数据Skype for Business工作流](../media/SkypeforBusinessConnectorWorkflow.png)

1. <span data-ttu-id="e3fba-112">您的组织与 Skype for Business一起设置和配置Skype for Business网站。</span><span class="sxs-lookup"><span data-stu-id="e3fba-112">Your organization works with Skype for Business to set up and configure a Skype for Business site.</span></span>

2. <span data-ttu-id="e3fba-113">每 24 小时Skype for Business一次，所有项目都会复制到"是否合并 1"网站。</span><span class="sxs-lookup"><span data-stu-id="e3fba-113">Once every 24 hours, Skype for Business items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="e3fba-114">连接器还会将Skype for Business转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="e3fba-114">The connector also converts Skype for Business items to an email message format.</span></span>

3. <span data-ttu-id="e3fba-115">在 Microsoft 365 合规中心 中创建的 Skype for Business 连接器，每天连接到一次 Microsoft 合并 1 网站，将 Skype for Business 内容传输至 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="e3fba-115">The Skype for Business connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the Skype for Business content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="e3fba-116">连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="e3fba-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="e3fba-117">在用户邮箱中创建名为 **Skype for Business** 收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e3fba-117">A subfolder in the Inbox folder named **Skype for Business** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="e3fba-118">连接器使用 *Email* 属性的值实现此操作。</span><span class="sxs-lookup"><span data-stu-id="e3fba-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="e3fba-119">每个Skype for Business项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="e3fba-119">Every Skype for Business item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="e3fba-120">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="e3fba-120">Before you set up a connector</span></span>

- <span data-ttu-id="e3fba-121">为 Microsoft 连接器创建 Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="e3fba-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="e3fba-122">若要进行此操作，请联系["用户支持人员"。](https://www.veritas.com/form/requestacall/ms-connectors-contact.html)</span><span class="sxs-lookup"><span data-stu-id="e3fba-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact.html).</span></span> <span data-ttu-id="e3fba-123">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="e3fba-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="e3fba-124">必须在步骤 1 (步骤 1 中创建 Skype for Business 连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="e3fba-124">The user who creates the Skype for Business connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e3fba-125">若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="e3fba-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e3fba-126">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e3fba-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="e3fba-127">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e3fba-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e3fba-128">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="e3fba-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e3fba-129">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="e3fba-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-skype-for-business-connector"></a><span data-ttu-id="e3fba-130">步骤 1：设置Skype for Business连接器</span><span class="sxs-lookup"><span data-stu-id="e3fba-130">Step 1: Set up the Skype for Business connector</span></span>

<span data-ttu-id="e3fba-131">第一步是访问"数据连接器"页，Microsoft 365 合规中心数据创建一个Skype for Business连接器。</span><span class="sxs-lookup"><span data-stu-id="e3fba-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Skype for Business data.</span></span>

1. <span data-ttu-id="e3fba-132">转到 ， <https://compliance.microsoft.com> 然后单击"数据 **连接器**  >  **Skype for Business"。**</span><span class="sxs-lookup"><span data-stu-id="e3fba-132">Go to <https://compliance.microsoft.com> and click **Data connectors** > **Skype for Business**.</span></span>

2. <span data-ttu-id="e3fba-133">在 **"Skype for Business** 说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="e3fba-133">On the **Skype for Business** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="e3fba-134">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="e3fba-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="e3fba-135">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="e3fba-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="e3fba-136">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="e3fba-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a><span data-ttu-id="e3fba-137">步骤 2：在 Skype for Business Merge1 网站上配置网站集</span><span class="sxs-lookup"><span data-stu-id="e3fba-137">Step 2: Configure the Skype for Business on the Veritas Merge1 site</span></span>

<span data-ttu-id="e3fba-138">第二步是在"Skype for Business Merge1"网站上配置连接器。</span><span class="sxs-lookup"><span data-stu-id="e3fba-138">The second step is to configure the Skype for Business connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="e3fba-139">若要了解如何配置连接器Skype for Business，请参阅[Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="e3fba-139">For information about how to configure the Skype for Business connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf).</span></span>

<span data-ttu-id="e3fba-140">单击"保存 **&完成\*\*\*\*"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。</span><span class="sxs-lookup"><span data-stu-id="e3fba-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="e3fba-141">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="e3fba-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="e3fba-142">若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="e3fba-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="e3fba-143">在"**将Skype for Business用户映射到Microsoft 365页上**，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="e3fba-143">On the **Map Skype for Business users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="e3fba-144">这些Skype for Business包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e3fba-144">The Skype for Business items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="e3fba-145">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e3fba-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="e3fba-146">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="e3fba-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-skype-for-business-connector"></a><span data-ttu-id="e3fba-147">步骤 4：监视Skype for Business连接器</span><span class="sxs-lookup"><span data-stu-id="e3fba-147">Step 4: Monitor the Skype for Business connector</span></span>

<span data-ttu-id="e3fba-148">创建连接器Skype for Business，可以查看连接器在连接器Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="e3fba-148">After you create the Skype for Business connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="e3fba-149">转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="e3fba-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="e3fba-150">单击 **"连接器"** 选项卡，然后选择"Skype for Business连接器"以显示包含有关连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="e3fba-150">Click the **Connectors** tab and then select the **Skype for Business** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="e3fba-151">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="e3fba-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="e3fba-152">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="e3fba-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e3fba-153">已知问题</span><span class="sxs-lookup"><span data-stu-id="e3fba-153">Known issues</span></span>

- <span data-ttu-id="e3fba-154">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="e3fba-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="e3fba-155">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="e3fba-155">Support for larger items will be available at a later date.</span></span>
