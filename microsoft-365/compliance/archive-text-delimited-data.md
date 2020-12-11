---
title: 设置连接器以在 Microsoft 365 中存档文本分隔的数据
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
description: 管理员可以设置连接器以将文本分隔的数据从 Globanet 导入并存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 1c06a1220e597dbf8e278222347a5a5e9c46567e
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619898"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a><span data-ttu-id="d9adb-105">设置连接器以存档文本分隔的数据</span><span class="sxs-lookup"><span data-stu-id="d9adb-105">Set up a connector to archive text-delimited data</span></span>

<span data-ttu-id="d9adb-106">使用 Microsoft 365 合规中心中的 Globanet 连接器将文本分隔数据导入 Microsoft 365 组织的用户邮箱，并存档这些数据。</span><span class="sxs-lookup"><span data-stu-id="d9adb-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive text-delimited data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="d9adb-107">Globanet 提供了[](https://globanet.com/text-delimited)一个文本分隔连接器，配置为定期捕获第三方数据源 (中的项目) 将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d9adb-107">Globanet provides a [text-delimited connector](https://globanet.com/text-delimited) that's configured to capture items from a third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="d9adb-108">连接器将文本分隔的数据源中的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="d9adb-108">The connector converts content from the text-delimited data source to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="d9adb-109">文本分隔的数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="d9adb-109">After text-delimited data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="d9adb-110">使用文本分隔的数据连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规策略。</span><span class="sxs-lookup"><span data-stu-id="d9adb-110">Using a text-delimited data connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-text-delimited-data"></a><span data-ttu-id="d9adb-111">文本分隔数据的存档概述</span><span class="sxs-lookup"><span data-stu-id="d9adb-111">Overview of archiving the text-delimited data</span></span>

<span data-ttu-id="d9adb-112">以下概述介绍了使用连接器在 Microsoft 365 中存档文本分隔的源信息的过程。</span><span class="sxs-lookup"><span data-stu-id="d9adb-112">The following overview explains the process of using a connector to archive text-delimited source information in Microsoft 365.</span></span>

![文本分隔数据的存档工作流](../media/TextDelimitedConnectorWorkflow.png)

1. <span data-ttu-id="d9adb-114">您的组织使用文本分隔的源来设置和配置文本分隔的网站。</span><span class="sxs-lookup"><span data-stu-id="d9adb-114">Your organization works with the text-delimited source to set up and configure a text-delimited site.</span></span>

2. <span data-ttu-id="d9adb-115">每 24 小时一次，来自文本分隔源的聊天消息将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="d9adb-115">Once every 24 hours, chat messages from the text-delimited source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="d9adb-116">连接器还会将内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="d9adb-116">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="d9adb-117">在 Microsoft 365 合规中心创建的文本分隔连接器每天连接到 Globanet Merge1 网站，将邮件转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="d9adb-117">The text-delimited connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="d9adb-118">连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。</span><span class="sxs-lookup"><span data-stu-id="d9adb-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="d9adb-119">收件箱文件夹中名为 **"Text- Delimited"** 的新子文件夹在用户邮箱中创建，邮件项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d9adb-119">A new subfolder in the Inbox folder named **Text- Delimited** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="d9adb-120">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="d9adb-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="d9adb-121">每封邮件都包含此属性，此属性填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d9adb-121">Every message contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d9adb-122">开始之前</span><span class="sxs-lookup"><span data-stu-id="d9adb-122">Before you begin</span></span>

- <span data-ttu-id="d9adb-123">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="d9adb-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="d9adb-124">若要创建此帐户，请联系 [Globanet 客户支持部门](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="d9adb-124">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="d9adb-125">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="d9adb-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="d9adb-126">在步骤 1 (中创建文本分隔连接器的用户必须在步骤 3) 中将其分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="d9adb-126">The user who creates the text-delimited connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="d9adb-127">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="d9adb-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d9adb-128">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="d9adb-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="d9adb-129">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="d9adb-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="d9adb-130">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="d9adb-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="d9adb-131">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="d9adb-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-text-delimited-connector"></a><span data-ttu-id="d9adb-132">步骤 1：设置以文本分隔的连接器</span><span class="sxs-lookup"><span data-stu-id="d9adb-132">Step 1: Set up the text-delimited connector</span></span>

<span data-ttu-id="d9adb-133">第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建文本分隔数据的连接器。 </span><span class="sxs-lookup"><span data-stu-id="d9adb-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for text-delimited data.</span></span>

1. <span data-ttu-id="d9adb-134">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击"**数据连接器**  >  **文本分隔"。**</span><span class="sxs-lookup"><span data-stu-id="d9adb-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Text-Delimited**.</span></span>

2. <span data-ttu-id="d9adb-135">在 **以文本分隔的产品** 说明页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="d9adb-135">On the **text-delimited** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="d9adb-136">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="d9adb-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="d9adb-137">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d9adb-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="d9adb-138">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="d9adb-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="d9adb-139">步骤 2：在 Globanet Merge1 网站上配置文本分隔连接器</span><span class="sxs-lookup"><span data-stu-id="d9adb-139">Step 2: Configure the Text-delimited connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="d9adb-140">第二步是在 Merge1 网站上配置文本分隔的连接器。</span><span class="sxs-lookup"><span data-stu-id="d9adb-140">The second step is to configure the text-delimited connector on the Merge1 site.</span></span> <span data-ttu-id="d9adb-141">有关在 Globanet Merge1 网站上配置文本分隔连接器的信息，请参阅["Merge1 第三方连接器用户指南"。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="d9adb-141">For information about configuring  the text-delimited connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="d9adb-142">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="d9adb-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="d9adb-143">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="d9adb-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="d9adb-144">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d9adb-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="d9adb-145">在 **"将外部用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="d9adb-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="d9adb-146">文本分隔的源项目包括一个称为 *"电子邮件*"的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d9adb-146">The Text- Delimited source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="d9adb-147">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d9adb-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="d9adb-148">单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="d9adb-148">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-text-delimited-connector"></a><span data-ttu-id="d9adb-149">步骤 4：监视以文本分隔的连接器</span><span class="sxs-lookup"><span data-stu-id="d9adb-149">Step 4: Monitor the text-delimited connector</span></span>

<span data-ttu-id="d9adb-150">创建以文本分隔的连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="d9adb-150">After you create the Text- Delimited connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="d9adb-151">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="d9adb-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d9adb-152">单击 **"连接器"** 选项卡，然后选择以 **文本** 分隔的连接器显示飞出页。</span><span class="sxs-lookup"><span data-stu-id="d9adb-152">Click the **Connectors** tab and then select the **Text- Delimited** connector to display the flyout page.</span></span> <span data-ttu-id="d9adb-153">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="d9adb-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="d9adb-154">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="d9adb-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="d9adb-155">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="d9adb-155">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d9adb-156">已知问题</span><span class="sxs-lookup"><span data-stu-id="d9adb-156">Known issues</span></span>

- <span data-ttu-id="d9adb-157">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="d9adb-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="d9adb-158">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="d9adb-158">Support for larger items will be available at a later date.</span></span>
