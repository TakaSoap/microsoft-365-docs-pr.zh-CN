---
title: 设置连接器以将 Salesforce Chatter 数据存档在 Microsoft 365
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
description: 管理员可以设置连接器以将 Salesforce Chatter 数据从 Microsoft 365 导入和存档。 通过此连接器，您可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: c04dc3026eaa5abb23b332dbae826c052344da31
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164052"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a><span data-ttu-id="10388-105">设置连接器以存档 Salesforce Chatter 数据</span><span class="sxs-lookup"><span data-stu-id="10388-105">Set up a connector to archive Salesforce Chatter data</span></span>

<span data-ttu-id="10388-106">使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从 Salesforce Chatter 平台导入并存档到组织Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="10388-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Salesforce Chatter platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="10388-107">该连接器提供[Salesforce Chatter](http://globanet.com/chatter/)连接器，用于捕获第三方数据源中的项目，并导入这些项以Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="10388-107">Veritas provides a [Salesforce Chatter](http://globanet.com/chatter/) connector that captures items from the third-party data source and imports those items to Microsoft 365.</span></span> <span data-ttu-id="10388-108">连接器将内容（如聊天、附件和帖子）从 Salesforce Chatter 转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="10388-108">The connector converts the content such as chats, attachments, and posts from Salesforce Chatter to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="10388-109">将 Salesforce Chatter 数据存储在用户邮箱中后，Microsoft 365诉讼保留、电子数据展示、保留策略和保留标签等合规性功能。</span><span class="sxs-lookup"><span data-stu-id="10388-109">After Salesforce Chatter data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="10388-110">使用 Salesforce Chatter 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="10388-110">Using a Salesforce Chatter connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-salesforce-chatter-data"></a><span data-ttu-id="10388-111">存档 Salesforce Chatter 数据概述</span><span class="sxs-lookup"><span data-stu-id="10388-111">Overview of archiving Salesforce Chatter data</span></span>

<span data-ttu-id="10388-112">以下概述介绍使用连接器在 Microsoft 365 中存档 Salesforce Chatter 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="10388-112">The following overview explains the process of using a connector to archive the Salesforce Chatter data in Microsoft 365.</span></span>

![Salesforce Chatter 数据的存档工作流](../media/SalesforceChatterConnectorWorkflow.png)

1. <span data-ttu-id="10388-114">您的组织与 Salesforce Chatter 合作，以设置和配置 Salesforce Chatter 网站。</span><span class="sxs-lookup"><span data-stu-id="10388-114">Your organization works with Salesforce Chatter to set up and configure a Salesforce Chatter site.</span></span>

2. <span data-ttu-id="10388-115">每 24 小时复制一次 Salesforce Chatter 项，然后复制到该网吧。</span><span class="sxs-lookup"><span data-stu-id="10388-115">Once every 24 hours, Salesforce Chatter items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="10388-116">连接器还会将 Salesforce Chatter 项目作为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="10388-116">The connector also Salesforce Chatter items to an email message format.</span></span>

3. <span data-ttu-id="10388-117">在 Microsoft 365 合规中心创建的 Salesforce Chatter 连接器每天连接到一个 Microsoft Clouds Merge1 网站，将 Chatter 内容传输至 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="10388-117">The Salesforce Chatter connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the Chatter content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="10388-118">连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="10388-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="10388-119">在用户邮箱中创建名为 **Salesforce Chatter** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="10388-119">A subfolder in the Inbox folder named **Salesforce Chatter** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="10388-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="10388-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="10388-121">每个 Chatter 项目都包含此属性，该属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="10388-121">Every Chatter item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="10388-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="10388-122">Before you begin</span></span>

- <span data-ttu-id="10388-123">为 Microsoft 连接器创建 Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="10388-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="10388-124">若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/)</span><span class="sxs-lookup"><span data-stu-id="10388-124">To create an account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="10388-125">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="10388-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="10388-126">创建 Salesforce 应用程序，并获取 令牌 [https://salesforce.com](https://salesforce.com) 。</span><span class="sxs-lookup"><span data-stu-id="10388-126">Create a Salesforce application and acquire a token at [https://salesforce.com](https://salesforce.com).</span></span> <span data-ttu-id="10388-127">你将需要以管理员角色登录到 Salesforce 帐户，并获取用户个人令牌以导入数据。</span><span class="sxs-lookup"><span data-stu-id="10388-127">You'll need to log into the Salesforce account as an admin and get a user personal token to import data.</span></span> <span data-ttu-id="10388-128">此外，需要在 Chatter 网站上发布触发器，以捕获更新、删除和编辑。</span><span class="sxs-lookup"><span data-stu-id="10388-128">Also, triggers need to be published on the Chatter site to capture updates, deletes, and edits.</span></span> <span data-ttu-id="10388-129">这些触发器将在频道上创建帖子，Merge1 将捕获该频道的信息。</span><span class="sxs-lookup"><span data-stu-id="10388-129">These triggers will create a post on a channel, and Merge1 will capture the information from the channel.</span></span> <span data-ttu-id="10388-130">有关如何创建应用程序和获取令牌的分步说明，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="10388-130">For step-by-step instructions about how to create the application and acquire the token, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="10388-131">必须在步骤 1 中创建 Salesforce Chatter 连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="10388-131">The user who creates the Salesforce Chatter connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="10388-132">若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。</span><span class="sxs-lookup"><span data-stu-id="10388-132">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="10388-133">默认情况下，不会为此角色组分配此角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="10388-133">By default, this role isn’t assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="10388-134">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="10388-134">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="10388-135">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="10388-135">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="10388-136">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="10388-136">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a><span data-ttu-id="10388-137">步骤 1：设置 Salesforce Chatter 连接器</span><span class="sxs-lookup"><span data-stu-id="10388-137">Step 1: Set up the Salesforce Chatter connector</span></span>

<span data-ttu-id="10388-138">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页面，并创建用于 Chatter 数据的连接器。</span><span class="sxs-lookup"><span data-stu-id="10388-138">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Chatter data.</span></span>

1. <span data-ttu-id="10388-139">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **Salesforce Chatter**。</span><span class="sxs-lookup"><span data-stu-id="10388-139">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Salesforce Chatter**.</span></span>

2. <span data-ttu-id="10388-140">在 **"Salesforce Chatter** 产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="10388-140">On the **Salesforce Chatter** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="10388-141">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="10388-141">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="10388-142">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="10388-142">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="10388-143">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="10388-143">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-salesforce-chatter-on-the-veritas-merge1-site"></a><span data-ttu-id="10388-144">步骤 2：在"完成"合并 1 网站中配置 Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="10388-144">Step 2: Configure the Salesforce Chatter on the Veritas Merge1 site</span></span>

<span data-ttu-id="10388-145">第二步是在"网吧 Merge1"网站上配置 Salesforce Chatter 连接器。</span><span class="sxs-lookup"><span data-stu-id="10388-145">The second step is to configure the Salesforce Chatter connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="10388-146">若要了解如何配置 Salesforce Chatter 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="10388-146">For information about how to configure the Salesforce Chatter connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="10388-147">单击"保存 **&完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="10388-147">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="10388-148">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="10388-148">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="10388-149">若要映射用户并完成 Microsoft 365设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="10388-149">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="10388-150">在"**将 Salesforce Chatter 用户映射到用户Microsoft 365，** 启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="10388-150">On the **Map Salesforce Chatter users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="10388-151">Salesforce Chatter 项目包括一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="10388-151">The Salesforce Chatter items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="10388-152">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="10388-152">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="10388-153">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="10388-153">click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a><span data-ttu-id="10388-154">步骤 4：监视 Salesforce Chatter 连接器</span><span class="sxs-lookup"><span data-stu-id="10388-154">Step 4: Monitor the Salesforce Chatter connector</span></span>

<span data-ttu-id="10388-155">创建 Salesforce Chatter 连接器后，可以在合规性中心内查看Microsoft 365状态。</span><span class="sxs-lookup"><span data-stu-id="10388-155">After you create the Salesforce Chatter connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="10388-156">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="10388-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="10388-157">单击 **"连接器"** 选项卡，然后单击 **"Salesforce Chatter"** 连接器以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="10388-157">click the **Connectors** tab and then click the **Salesforce Chatter** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="10388-158">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="10388-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="10388-159">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="10388-159">This log contains data that's been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="10388-160">已知问题</span><span class="sxs-lookup"><span data-stu-id="10388-160">Known issues</span></span>

- <span data-ttu-id="10388-161">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="10388-161">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="10388-162">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="10388-162">Support for larger items will be available at a later date.</span></span>