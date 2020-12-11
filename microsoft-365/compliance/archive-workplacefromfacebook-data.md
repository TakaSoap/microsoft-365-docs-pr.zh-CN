---
title: 设置连接器以在 Microsoft 365 中存档来自 Facebook 数据的 Workplace
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
description: 管理员可以设置连接器，以将来自 Workplace 的数据从 Facebook 导入和存档，Facebook 在 Globanet 的 Merge1 网站上存档到 Microsoft 365。 设置连接器要求您使用 Globanet 此连接器可以存档 Microsoft 365 中第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 0bcea998e857365b512b2a6f773dca17a85c08f9
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619848"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a><span data-ttu-id="b47b2-104">设置连接器以从 Facebook 数据存档 Workplace</span><span class="sxs-lookup"><span data-stu-id="b47b2-104">Set up a connector to archive Workplace from Facebook data</span></span>

<span data-ttu-id="b47b2-105">使用 Microsoft 365 合规中心中的 Globanet 连接器将工作区数据从 Facebook 导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b47b2-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Workplace from Facebook to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b47b2-106">Globanet 提供 [来自 Facebook](https://globanet.com/workplace/) 的 Workplace 连接器，配置为定期捕获第三方数据源 (中的项目) 将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b47b2-106">Globanet provides a [Workplace from Facebook](https://globanet.com/workplace/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="b47b2-107">连接器将工作区中的聊天、附件、帖子和视频等内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b47b2-107">The connector converts the content such as chats, attachments, posts, and videos from Workplace to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="b47b2-108">在工作区数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="b47b2-108">After Workplace data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="b47b2-109">使用来自 Facebook 连接器的 Workplace 在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规策略。</span><span class="sxs-lookup"><span data-stu-id="b47b2-109">Using Workplace from Facebook connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-workplace-from-facebook-data"></a><span data-ttu-id="b47b2-110">从 Facebook 数据存档工作区概述</span><span class="sxs-lookup"><span data-stu-id="b47b2-110">Overview of archiving Workplace from Facebook data</span></span>

<span data-ttu-id="b47b2-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 Workplace 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="b47b2-111">The following overview explains the process of using a connector to archive Workplace data in Microsoft 365.</span></span>

![从 Facebook 数据存档工作区工作流](../media/WorkplaceConnectorWorkflow.png)

1. <span data-ttu-id="b47b2-113">你的组织与 Facebook 的 Workplace 合作，以设置和配置工作区网站。</span><span class="sxs-lookup"><span data-stu-id="b47b2-113">Your organization works with Workplace from Facebook to set up and configure a Workplace site.</span></span>

2. <span data-ttu-id="b47b2-114">每 24 小时一次，工作区中的项目将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="b47b2-114">Once every 24 hours, items from Workplace are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="b47b2-115">连接器还将这些项目的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="b47b2-115">The connector also converts the content of these items to an email message format.</span></span>

3. <span data-ttu-id="b47b2-116">在 Microsoft 365 合规中心创建的来自 Facebook 连接器的 Workplace 每天连接到 Globanet Merge1，将工作区项目转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="b47b2-116">The Workplace from Facebook connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the Workplace items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b47b2-117">连接器使用自动用户映射的 *Email* 属性值将转换的项目导入特定用户的邮箱，如步骤 3 中所述。</span><span class="sxs-lookup"><span data-stu-id="b47b2-117">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="b47b2-118">从 Facebook 创建名为 **Workplace** 的收件箱文件夹中的子文件夹，工作区项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="b47b2-118">A subfolder in the Inbox folder named **Workplace from Facebook** is created, and the Workplace items are imported to that folder.</span></span> <span data-ttu-id="b47b2-119">连接器通过使用 Email *属性的值来实现* 此操作。</span><span class="sxs-lookup"><span data-stu-id="b47b2-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="b47b2-120">每个 Workplace 项目都包含此属性，此属性填充了每个聊天或帖子参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b47b2-120">Every Workplace item contains this property, which is populated with the email address of every chat or post participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b47b2-121">开始之前</span><span class="sxs-lookup"><span data-stu-id="b47b2-121">Before you begin</span></span>

- <span data-ttu-id="b47b2-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="b47b2-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="b47b2-123">若要创建此帐户，请联系 [Globanet 客户支持部门](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="b47b2-123">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="b47b2-124">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="b47b2-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b47b2-125">创建自定义集成以通过 API 从 Workplace 检索数据，以便实现合规性和 https://my.workplace.com/work/admin/apps/ 电子数据展示目的。</span><span class="sxs-lookup"><span data-stu-id="b47b2-125">Create a custom integration at https://my.workplace.com/work/admin/apps/ to retrieve data from Workplace via APIs for compliance and eDiscovery purposes.</span></span>

   <span data-ttu-id="b47b2-126">创建集成时，Workplace 平台会生成一组用于生成用于身份验证的令牌的唯一凭据。</span><span class="sxs-lookup"><span data-stu-id="b47b2-126">When creating the integration, the Workplace platform generates a set of unique credentials used to generate tokens that are used for authentication.</span></span> <span data-ttu-id="b47b2-127">这些令牌在步骤 2 中来自 Facebook 连接器配置向导的 Workplace 中使用。</span><span class="sxs-lookup"><span data-stu-id="b47b2-127">These tokens are used in the Workplace from Facebook connector configuration wizard in Step 2.</span></span> <span data-ttu-id="b47b2-128">有关如何创建应用程序的分步说明，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b47b2-128">For step-by step instructions about how to create the applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="b47b2-129">在步骤 1 中通过 Facebook 连接器创建工作区 (步骤 3) 必须分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="b47b2-129">The user who creates the Workplace from Facebook connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b47b2-130">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="b47b2-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b47b2-131">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="b47b2-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="b47b2-132">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="b47b2-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b47b2-133">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="b47b2-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b47b2-134">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="b47b2-134">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a><span data-ttu-id="b47b2-135">步骤 1：从 Facebook 连接器设置工作区</span><span class="sxs-lookup"><span data-stu-id="b47b2-135">Step 1: Set up the Workplace from Facebook connector</span></span>

<span data-ttu-id="b47b2-136">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建工作区数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="b47b2-136">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Workplace data.</span></span>

1. <span data-ttu-id="b47b2-137">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) Facebook，然后单击"**数据连接器**  >  **工作区"。**</span><span class="sxs-lookup"><span data-stu-id="b47b2-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Workplace from Facebook**.</span></span>

2. <span data-ttu-id="b47b2-138">在 **"来自 Facebook 产品说明的工作区**"页上，单击 **"添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="b47b2-138">On the **Workplace from Facebook** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b47b2-139">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="b47b2-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b47b2-140">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="b47b2-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="b47b2-141">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="b47b2-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="b47b2-142">步骤 2：在 Globanet Merge1 网站上通过 Facebook 连接器配置 Workplace</span><span class="sxs-lookup"><span data-stu-id="b47b2-142">Step 2: Configure the Workplace from Facebook connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="b47b2-143">第二步是在 Merge1 网站上通过 Facebook 连接器配置 Workplace。</span><span class="sxs-lookup"><span data-stu-id="b47b2-143">The second step is to configure the Workplace from Facebook connector on the Merge1 site.</span></span> <span data-ttu-id="b47b2-144">若要了解如何从 Facebook 连接器配置 Workplace，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b47b2-144">For information about how to configure the Workplace from Facebook connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="b47b2-145">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="b47b2-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="b47b2-146">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="b47b2-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="b47b2-147">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b47b2-147">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="b47b2-148">在 **"将外部用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="b47b2-148">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="b47b2-149">工作区项目包括一个称为 *"电子邮件* "的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b47b2-149">The Workplace items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="b47b2-150">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b47b2-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="b47b2-151">单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="b47b2-151">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a><span data-ttu-id="b47b2-152">步骤 4：通过 Facebook 连接器监视工作区</span><span class="sxs-lookup"><span data-stu-id="b47b2-152">Step 4: Monitor the Workplace from Facebook connector</span></span>

<span data-ttu-id="b47b2-153">通过 Facebook 连接器创建 Workplace 后，可以在 Microsoft 365 合规中心内查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="b47b2-153">After you create the Workplace from Facebook connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b47b2-154">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="b47b2-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b47b2-155">单击 **"连接器"** 选项卡，然后从 **Facebook 连接器中选择工作区** 以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="b47b2-155">Click the **Connectors** tab and then select the **Workplace from Facebook** connector to display the flyout page.</span></span> <span data-ttu-id="b47b2-156">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="b47b2-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b47b2-157">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="b47b2-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b47b2-158">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="b47b2-158">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b47b2-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="b47b2-159">Known issues</span></span>

- <span data-ttu-id="b47b2-160">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="b47b2-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b47b2-161">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="b47b2-161">Support for larger items will be available at a later date.</span></span>
