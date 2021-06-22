---
title: 设置连接器以将 Cisco Jabber 存档在 Oracle Microsoft 365
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
description: 了解如何在 Microsoft 365 合规中心 中设置和使用连接器，以从 Oracle 上的 Cisco Jabber 导入数据并Microsoft 365。
ms.openlocfilehash: 8c8e95a9a96767aa227c463c96b04a30d8aac7dc
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054642"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data"></a><span data-ttu-id="dc8ed-103">设置连接器以在 Oracle 数据上存档 Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="dc8ed-103">Set up a connector to archive Cisco Jabber on Oracle data</span></span>

<span data-ttu-id="dc8ed-104">使用 Microsoft 365 合规中心 连接器将数据从 Oracle 平台上的 Cisco Jabber 导入并存档到组织Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber on Oracle platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="dc8ed-105">为 Oracle 连接器提供[Cisco Jabber，](https://www.veritas.com/insights/merge1/jabber)该连接器配置为定期捕获第三方数据源 (中的项目) 将这些项目导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-105">Veritas provides a [Cisco Jabber on Oracle](https://www.veritas.com/insights/merge1/jabber) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="dc8ed-106">连接器将 Oracle 上的 Cisco Jabber 中的内容（如文件和文件操作、注释和共享内容）转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-106">The connector converts the content such as files and file operations, comments, and shared content from Cisco Jabber on Oracle to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="dc8ed-107">在 Oracle 上的 Cisco Jabber 数据存储在用户邮箱中后，Microsoft 365合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-107">After Cisco Jabber on Oracle data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="dc8ed-108">使用 Oracle 连接器上的 Cisco Jabber 在 Microsoft 365 导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-108">Using a Cisco Jabber on Oracle connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a><span data-ttu-id="dc8ed-109">对 Oracle 数据存档 Cisco Jabber 概述</span><span class="sxs-lookup"><span data-stu-id="dc8ed-109">Overview of archiving Cisco Jabber on Oracle data</span></span>

<span data-ttu-id="dc8ed-110">以下概述介绍使用连接器在 Oracle 中存档 Cisco Jabber Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-110">The following overview explains the process of using a connector to archive the Cisco Jabber on Oracle data in Microsoft 365.</span></span>

![Cisco Jabber 对 Oracle 数据的存档工作流](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. <span data-ttu-id="dc8ed-112">贵组织与 Oracle 上的 Cisco Jabber 合作，在 Oracle 网站上设置和配置 Cisco Jabber。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-112">Your organization works with Cisco Jabber on Oracle to set up and configure a Cisco Jabber on Oracle site.</span></span>

2. <span data-ttu-id="dc8ed-113">每 24 小时一次，将 Oracle 项上的 Cisco Jabber 复制到该"改进 24 小时"网站。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-113">Once every 24 hours, Cisco Jabber on Oracle items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="dc8ed-114">连接器还将 Oracle 项上的 Cisco Jabber 转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-114">The connector also converts Cisco Jabber on Oracle items to an email message format.</span></span>

3. <span data-ttu-id="dc8ed-115">你在 Microsoft 365 合规中心 创建的 Oracle 连接器上的 Cisco Jabber 每天连接到一个 Microsoft 云中的一个安全 Azure 存储 位置，并每天连接到一个 Microsoft Merge1 网站。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-115">The Cisco Jabber on Oracle connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the Jabber content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="dc8ed-116">连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="dc8ed-117">在用户邮箱中创建名为 **Cisco Jabber on Oracle** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-117">A subfolder in the Inbox folder named **Cisco Jabber on Oracle** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="dc8ed-118">连接器使用 *Email* 属性的值实现此操作。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="dc8ed-119">每个 Jabber 项目都包含此属性，该属性用项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-119">Every Jabber item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dc8ed-120">准备工作</span><span class="sxs-lookup"><span data-stu-id="dc8ed-120">Before you begin</span></span>

- <span data-ttu-id="dc8ed-121">为 Microsoft 连接器创建 Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="dc8ed-122">若要进行此操作，请联系["用户支持人员"。](https://www.veritas.com/content/support/en_US)</span><span class="sxs-lookup"><span data-stu-id="dc8ed-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/content/support/en_US).</span></span> <span data-ttu-id="dc8ed-123">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="dc8ed-124">必须在步骤 1 步骤 1 中在 Oracle 连接器上创建 Cisco Jabber (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-124">The user who creates the Cisco Jabber on Oracle connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="dc8ed-125">若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dc8ed-126">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="dc8ed-127">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="dc8ed-128">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="dc8ed-129">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a><span data-ttu-id="dc8ed-130">步骤 1：在 Oracle 连接器上设置 Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="dc8ed-130">Step 1: Set up the Cisco Jabber on Oracle connector</span></span>

<span data-ttu-id="dc8ed-131">第一步是访问数据连接器页 **，Microsoft 365 合规中心为** Jabber 数据创建连接器。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jabber data.</span></span>

1. <span data-ttu-id="dc8ed-132">转到 ， <https://compliance.microsoft.com> 然后单击 Oracle **上的"数据连接器**  >  **""Cisco Jabber"。**</span><span class="sxs-lookup"><span data-stu-id="dc8ed-132">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Cisco Jabber on Oracle**.</span></span>

2. <span data-ttu-id="dc8ed-133">在 **Oracle 产品说明页上的 Cisco Jabber** 上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="dc8ed-133">On the **Cisco Jabber on Oracle** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="dc8ed-134">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="dc8ed-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="dc8ed-135">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="dc8ed-136">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a><span data-ttu-id="dc8ed-137">第 2 步：在 Oracle 上配置 Cisco Jabber，位于"完成"合并 1 网站上</span><span class="sxs-lookup"><span data-stu-id="dc8ed-137">Step 2: Configure the Cisco Jabber on Oracle on the Veritas Merge1 site</span></span>

<span data-ttu-id="dc8ed-138">第二步是在"Cisco Merge1"站点上的 Oracle 连接器上配置 Cisco Jabber。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-138">The second step is to configure the Cisco Jabber on Oracle connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="dc8ed-139">若要了解如何在 Oracle 连接器上配置 Cisco Jabber，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-139">For information about how to configure the Cisco Jabber on Oracle connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf).</span></span>

<span data-ttu-id="dc8ed-140">单击"保存 **&完成\*\*\*\*"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="dc8ed-141">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="dc8ed-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="dc8ed-142">若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="dc8ed-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="dc8ed-143">在"**将 Oracle 用户映射到用户Microsoft 365上的"映射 Cisco Jabber"** 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-143">On the **Map Cisco Jabber on Oracle users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="dc8ed-144">Oracle 项上的 Cisco Jabber 包含名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-144">The Cisco Jabber on Oracle items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="dc8ed-145">如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="dc8ed-146">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a><span data-ttu-id="dc8ed-147">步骤 4：监视 Oracle 连接器上的 Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="dc8ed-147">Step 4: Monitor the Cisco Jabber on Oracle connector</span></span>

<span data-ttu-id="dc8ed-148">在 Oracle 连接器上创建 Cisco Jabber 后，可以查看连接器在 Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-148">After you create the Cisco Jabber on Oracle connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="dc8ed-149">转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="dc8ed-150">单击 **"连接器"** 选项卡，然后选择 Oracle 连接器上的 **Cisco Jabber** 以显示包含连接器的属性和信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-150">Click the **Connectors** tab and then select the **Cisco Jabber on Oracle** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="dc8ed-151">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="dc8ed-152">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="dc8ed-153">已知问题</span><span class="sxs-lookup"><span data-stu-id="dc8ed-153">Known issues</span></span>

- <span data-ttu-id="dc8ed-154">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="dc8ed-155">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="dc8ed-155">Support for larger items will be available at a later date.</span></span>
