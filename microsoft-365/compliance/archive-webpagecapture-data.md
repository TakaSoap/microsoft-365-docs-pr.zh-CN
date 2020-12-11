---
title: 设置连接器以在 Microsoft 365 中存档网页数据
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
description: 管理员可以设置连接器以在 Microsoft 365 中导入和存档来自 Globanet 的网页捕获数据。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 5d793bea8a22d9908551fff67c9d27afffdf1d86
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619818"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a><span data-ttu-id="2805e-104">设置连接器以存档网页数据</span><span class="sxs-lookup"><span data-stu-id="2805e-104">Set up a connector to archive webpage data</span></span>

<span data-ttu-id="2805e-105">使用 Microsoft 365 合规中心中的 Globanet 连接器将网页数据导入和存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="2805e-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from webpages to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="2805e-106">Globanet 提供了[](https://globanet.com/webpage-capture)一个网页捕获连接器，该连接器可 (特定网站或整个域中) 网页上的任何链接。</span><span class="sxs-lookup"><span data-stu-id="2805e-106">Globanet provides a [Webpage Capture](https://globanet.com/webpage-capture) connector that captures specific webpages (and any links on those pages) in a specific website or an entire domain.</span></span> <span data-ttu-id="2805e-107">连接器将网页内容转换为 PDF、PNG 或自定义文件格式，然后将转换后的文件附加到电子邮件，然后将这些电子邮件项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="2805e-107">The connector converts the webpage content to a PDF, PNG, or custom file format and then attaches the converted files to an email message and then imports those email items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="2805e-108">网页内容存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="2805e-108">After webpage content is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="2805e-109">使用网页捕获连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="2805e-109">Using a Webpage Capture connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webpage-data"></a><span data-ttu-id="2805e-110">存档网页数据概述</span><span class="sxs-lookup"><span data-stu-id="2805e-110">Overview of archiving webpage data</span></span>

<span data-ttu-id="2805e-111">以下概述介绍了使用连接器在 Microsoft 365 中存档网页内容的过程。</span><span class="sxs-lookup"><span data-stu-id="2805e-111">The following overview explains the process of using a connector to archive webpage content in Microsoft 365.</span></span>

![网页数据的存档工作流](../media/WebPageCaptureConnectorWorkflow.png)

1. <span data-ttu-id="2805e-113">您的组织与网页源一起设置和配置网页捕获网站。</span><span class="sxs-lookup"><span data-stu-id="2805e-113">Your organization works with the webpage source to set up and configure a Webpage Capture site.</span></span>

2. <span data-ttu-id="2805e-114">每 24 小时一次，网页源项目将复制到 Globanet Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="2805e-114">Once every 24 hours, the webpage sources items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="2805e-115">连接器还会将网页内容转换并附加到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2805e-115">The connector also converts and attaches the content of a webpage to an email message.</span></span>

3. <span data-ttu-id="2805e-116">在 Microsoft 365 合规中心创建的网页捕获连接器每天连接到 Globanet Merge1 网站，将网页项转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2805e-116">The Webpage Capture connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the webpage items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="2805e-117">连接器使用自动用户映射的 *Email* 属性值将转换的网页项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="2805e-117">The connector imports the converted webpage items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="2805e-118">在用户邮箱中创建名为 **"** 网页捕获"的收件箱文件夹中的子文件夹，网页项目将导入该文件夹。</span><span class="sxs-lookup"><span data-stu-id="2805e-118">A subfolder in the Inbox folder named **Webpage Capture** is created in the user mailboxes, and the webpage items are imported to that folder.</span></span> <span data-ttu-id="2805e-119">连接器通过使用 Email *属性的值来实现* 此操作。</span><span class="sxs-lookup"><span data-stu-id="2805e-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="2805e-120">每个网页项目都包含此属性，该属性用在步骤 2 中配置网页捕获连接器时提供 [的电子邮件地址填充](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)。</span><span class="sxs-lookup"><span data-stu-id="2805e-120">Every webpage item contains this property, which is populated with the email addresses provided when you configure the Webpage Capture connector in [Step 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2805e-121">开始之前</span><span class="sxs-lookup"><span data-stu-id="2805e-121">Before you begin</span></span>

- <span data-ttu-id="2805e-122">为 Microsoft 连接器创建 Globanet Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="2805e-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="2805e-123">若要创建此帐户，请联系 [Globanet 客户支持部门](https://globanet.com/ms-connectors-contact/)。</span><span class="sxs-lookup"><span data-stu-id="2805e-123">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="2805e-124">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="2805e-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="2805e-125">您需要与 Globanet 支持合作，以设置要将网页项目转换为的自定义文件格式。</span><span class="sxs-lookup"><span data-stu-id="2805e-125">You need to work with Globanet support to set up a custom file format to convert the webpage items to.</span></span> <span data-ttu-id="2805e-126">有关详细信息，请参阅"Merge1 第三方连接器用户指南"</span><span class="sxs-lookup"><span data-stu-id="2805e-126">For more information, see the Merge1 Third-Party Connectors User Guide in</span></span> 

- <span data-ttu-id="2805e-127">在步骤 1 中创建网页捕获连接器 (步骤 3) 必须分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="2805e-127">The user who creates the Webpage Capture connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="2805e-128">在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="2805e-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2805e-129">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="2805e-129">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="2805e-130">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="2805e-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="2805e-131">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="2805e-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="2805e-132">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="2805e-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webpage-capture-connector"></a><span data-ttu-id="2805e-133">步骤 1：设置网页捕获连接器</span><span class="sxs-lookup"><span data-stu-id="2805e-133">Step 1: Set up the Webpage Capture connector</span></span>

<span data-ttu-id="2805e-134">第一步是访问数据连接器 **，** 并创建网页源数据的连接器。</span><span class="sxs-lookup"><span data-stu-id="2805e-134">The first step is to access to the **Data Connectors** and create a connector for Web Page source data.</span></span>

1. <span data-ttu-id="2805e-135">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击"**数据连接器网页**  >  **捕获"。**</span><span class="sxs-lookup"><span data-stu-id="2805e-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webpage Capture**.</span></span>

2. <span data-ttu-id="2805e-136">在"**网页捕获** 产品说明"页上，单击 **"添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="2805e-136">On the **Webpage Capture** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="2805e-137">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="2805e-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="2805e-138">输入标识连接器的唯一名称，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="2805e-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="2805e-139">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="2805e-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="2805e-140">步骤 2：在 Globanet Merge1 网站上配置网页捕获连接器</span><span class="sxs-lookup"><span data-stu-id="2805e-140">Step 2: Configure the Webpage Capture connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="2805e-141">第二步是在 Globanet Merge1 网站上配置网页捕获连接器。</span><span class="sxs-lookup"><span data-stu-id="2805e-141">The second step is to configure the Webpage Capture connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="2805e-142">若要了解如何配置网页捕获连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="2805e-142">For information about how to configure the Webpage Capture connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="2805e-143">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="2805e-143">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="2805e-144">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="2805e-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="2805e-145">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="2805e-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="2805e-146">在 **"将用户映射到 Microsoft 365 用户"页上** ，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="2805e-146">On the **Map Webpage Capture users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="2805e-147">网页捕获项目包括一个称为 *"电子邮件*"的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2805e-147">The Webpage Capture items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="2805e-148">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2805e-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="2805e-149">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="2805e-149">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webpage-capture-connector"></a><span data-ttu-id="2805e-150">步骤 4：监视网页捕获连接器</span><span class="sxs-lookup"><span data-stu-id="2805e-150">Step 4: Monitor the Webpage Capture connector</span></span>

<span data-ttu-id="2805e-151">创建网页捕获连接器后，可以在 Microsoft 365 合规中心内查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="2805e-151">After you create the Webpage Capture connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="2805e-152">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航 **中并** 单击"数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="2805e-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="2805e-153">单击 **"连接器"** 选项卡，然后选择 **网页捕获** 连接器以显示该飞出页。</span><span class="sxs-lookup"><span data-stu-id="2805e-153">Click the **Connectors** tab and then select the **Webpage Capture** connector to display the flyout page.</span></span> <span data-ttu-id="2805e-154">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="2805e-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="2805e-155">在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="2805e-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="2805e-156">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="2805e-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2805e-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="2805e-157">Known issues</span></span>

- <span data-ttu-id="2805e-158">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="2805e-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="2805e-159">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="2805e-159">Support for larger items will be available at a later date.</span></span>
