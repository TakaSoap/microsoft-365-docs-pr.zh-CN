---
title: 设置连接器以将 XSLT/XML 数据存档在 Microsoft 365
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
description: 管理员可以设置连接器，以从 Microsoft 365 中导入和存档来自 Its 的 XSLT/XML Microsoft 365。 此连接器允许您在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163752"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a><span data-ttu-id="12ff9-104">设置连接器以存档 XSLT/XML 数据</span><span class="sxs-lookup"><span data-stu-id="12ff9-104">Set up a connector to archive XSLT/XML data</span></span>

<span data-ttu-id="12ff9-105">使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从网页源导入并存档到组织的用户Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="12ff9-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Web page source to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="12ff9-106">对于使用 XSLT (可扩展样式表语言转换) 创建的文件，通过[XSLT/XML](https://globanet.com/xslt-xml)连接器，您可以快速开发这些文件 (如 HTML 或文本) ，这些格式可以导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="12ff9-106">Veritas provides you with an [XSLT/XML connector](https://globanet.com/xslt-xml) that allows the rapid development of files created by using XSLT (Extensible Style sheet Language Transformations) to transform XML files into other file formats (such as HTML or text) that can be imported to Microsoft 365.</span></span> <span data-ttu-id="12ff9-107">连接器将项目的内容从 XSLT/XML 源转换为电子邮件格式，然后将转换的项目导入到Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="12ff9-107">The connector converts the content of an item from the XSLT/XML source to an email message format and then imports the converted item to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="12ff9-108">XSLT/XML 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="12ff9-108">After XSLT/XML data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="12ff9-109">使用 XSLT/XML 连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="12ff9-109">Using an XSLT/XML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-xsltxml-data"></a><span data-ttu-id="12ff9-110">存档 XSLT/XML 数据概述</span><span class="sxs-lookup"><span data-stu-id="12ff9-110">Overview of archiving XSLT/XML data</span></span>

<span data-ttu-id="12ff9-111">以下概述介绍使用连接器在数据记录中存档 XSLT/XML 源数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="12ff9-111">The following overview explains the process of using a connector to archive XSLT/XML source data in Microsoft 365.</span></span>

![XSLT/XML 数据的存档工作流](../media/XSLT-XMLConnectorWorkflow.png)

1. <span data-ttu-id="12ff9-113">您的组织使用 XSLT/XML 源来设置和配置 XSLT/XML 网站。</span><span class="sxs-lookup"><span data-stu-id="12ff9-113">Your organization works with the XSLT/XML source to set up and configure an XSLT/XML site.</span></span>

2. <span data-ttu-id="12ff9-114">每 24 小时发送一次，来自 XSLT/XML 源的聊天消息将复制到"完成"合并 1 网站。</span><span class="sxs-lookup"><span data-stu-id="12ff9-114">Once every 24 hours, chat messages from the XSLT/XML source are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="12ff9-115">连接器还会将内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="12ff9-115">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="12ff9-116">在 Microsoft 365 合规中心内创建的 XSLT/XML 连接器每天连接到一个 Microsoft Clouds Merge1 网站，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="12ff9-116">The XSLT/XML connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="12ff9-117">连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。</span><span class="sxs-lookup"><span data-stu-id="12ff9-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="12ff9-118">在用户邮箱中创建名为 **XSLT/XML** 的收件箱文件夹中的新子文件夹，邮件项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="12ff9-118">A new subfolder in the Inbox folder named **XSLT/XML** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="12ff9-119">连接器使用 *Email* 属性的值实现此操作。</span><span class="sxs-lookup"><span data-stu-id="12ff9-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="12ff9-120">每封邮件都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="12ff9-120">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="12ff9-121">开始之前</span><span class="sxs-lookup"><span data-stu-id="12ff9-121">Before you begin</span></span>

- <span data-ttu-id="12ff9-122">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="12ff9-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="12ff9-123">若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/)</span><span class="sxs-lookup"><span data-stu-id="12ff9-123">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="12ff9-124">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="12ff9-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="12ff9-125">必须在步骤 1 中创建 XSLT/XML 连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="12ff9-125">The user who creates the XSLT/XML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="12ff9-126">若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。</span><span class="sxs-lookup"><span data-stu-id="12ff9-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="12ff9-127">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="12ff9-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="12ff9-128">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="12ff9-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="12ff9-129">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="12ff9-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="12ff9-130">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="12ff9-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-xsltxml-connector"></a><span data-ttu-id="12ff9-131">步骤 1：设置 XSLT/XML 连接器</span><span class="sxs-lookup"><span data-stu-id="12ff9-131">Step 1: Set up an XSLT/XML connector</span></span>

<span data-ttu-id="12ff9-132">第一步是在合规性中心内访问Microsoft 365连接器，并创建 XSLT/XML 数据的连接器。</span><span class="sxs-lookup"><span data-stu-id="12ff9-132">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for XSLT/XML data.</span></span>

1. <span data-ttu-id="12ff9-133">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **XSLT/XML**。</span><span class="sxs-lookup"><span data-stu-id="12ff9-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **XSLT/XML**.</span></span>

2. <span data-ttu-id="12ff9-134">在 **"XSLT/XML** 产品说明"页上，单击"**添加新连接器"。**</span><span class="sxs-lookup"><span data-stu-id="12ff9-134">On the **XSLT/XML** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="12ff9-135">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="12ff9-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="12ff9-136">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="12ff9-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="12ff9-137">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="12ff9-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-an-xsltxml-connector"></a><span data-ttu-id="12ff9-138">步骤 2：配置 XSLT/XML 连接器</span><span class="sxs-lookup"><span data-stu-id="12ff9-138">Step 2: Configure an XSLT/XML connector</span></span>

<span data-ttu-id="12ff9-139">第二步是在 Merge1 网站上配置 XSLT/XML 连接器。</span><span class="sxs-lookup"><span data-stu-id="12ff9-139">The second step is to configure the XSLT/XML connector on the Merge1 site.</span></span> <span data-ttu-id="12ff9-140">若要了解如何在"一线合并 1"网站上配置 XSLT/XML 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="12ff9-140">For information about how to configure the XSLT/XML connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="12ff9-141">单击"保存&**完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="12ff9-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="12ff9-142">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="12ff9-142">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="12ff9-143">若要映射用户并完成 Microsoft 365合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="12ff9-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

2. <span data-ttu-id="12ff9-144">在"**将 XSLT/XML 用户映射到用户Microsoft 365，** 启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="12ff9-144">On the **Map XSLT/XML users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="12ff9-145">XSLT/XML 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="12ff9-145">The XSLT/XML items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="12ff9-146">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="12ff9-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

3. <span data-ttu-id="12ff9-147">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="12ff9-147">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xsltxml-connector"></a><span data-ttu-id="12ff9-148">步骤 4：监视 XSLT/XML 连接器</span><span class="sxs-lookup"><span data-stu-id="12ff9-148">Step 4: Monitor the XSLT/XML connector</span></span>

<span data-ttu-id="12ff9-149">创建 XSLT/XML 连接器后，可以在合规性中心内查看Microsoft 365状态。</span><span class="sxs-lookup"><span data-stu-id="12ff9-149">After you create the XSLT/XML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="12ff9-150">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="12ff9-150">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="12ff9-151">单击" **连接器"** 选项卡，然后选择 **XSLT/XML** 连接器以显示飞出页。</span><span class="sxs-lookup"><span data-stu-id="12ff9-151">Click the **Connectors** tab and then select the **XSLT/XML** connector to display the flyout page.</span></span> <span data-ttu-id="12ff9-152">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="12ff9-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="12ff9-153">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="12ff9-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="12ff9-154">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="12ff9-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="12ff9-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="12ff9-155">Known issues</span></span>

- <span data-ttu-id="12ff9-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="12ff9-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="12ff9-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="12ff9-157">Support for larger items will be available at a later date.</span></span>