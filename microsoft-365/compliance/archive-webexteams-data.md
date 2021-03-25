---
title: 在 Microsoft 365 中设置用于 Webex Teams 数据的连接器
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
description: 管理员可以设置连接器，以在 Microsoft 365 中从 Microsoft 365 的 Webex Teams 连接器导入和存档数据。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163893"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a><span data-ttu-id="b5bf8-104">设置连接器以存档 WebEx Teams 数据</span><span class="sxs-lookup"><span data-stu-id="b5bf8-104">Set up a connector to archive Webex Teams data</span></span>

<span data-ttu-id="b5bf8-105">使用 Microsoft 365 合规中心中的 Microsoft 365 连接器将数据从 Webex Teams 导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from Webex Teams to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b5bf8-106">Microsoft 提供了一个 [Webex Teams](https://globanet.com/webex-teams/) 连接器，该连接器配置为捕获 Webex Teams 通信项目，并导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-106">Veritas provides a [Webex Teams](https://globanet.com/webex-teams/) connector that is configured to capture Webex Teams communication items and import them to Microsoft 365.</span></span> <span data-ttu-id="b5bf8-107">连接器将 Webex Teams 中的内容（如一对一聊天、群组对话、频道对话和来自组织的 Webex Teams 帐户的附件）转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-107">The connector converts content from Webex Teams, such as 1:1 chats, group conversations, channel conversations, and attachments from your organization's Webex Teams account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="b5bf8-108">在 Webex Teams 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-108">After Webex Teams data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="b5bf8-109">使用 Webex Teams 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-109">Using a Webex Teams connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webex-teams-data"></a><span data-ttu-id="b5bf8-110">存档 Webex Teams 数据概述</span><span class="sxs-lookup"><span data-stu-id="b5bf8-110">Overview of archiving Webex Teams data</span></span>

<span data-ttu-id="b5bf8-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 Webex Teams 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-111">The following overview explains the process of using a connector to archive Webex Teams data in Microsoft 365.</span></span>

![Webex Teams 数据的存档工作流](../media/WebexTeamsConnectorWorkflow.png)

1. <span data-ttu-id="b5bf8-113">你的组织与 Webex Teams 一起设置和配置 Webex Teams 网站。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-113">Your organization works with Webex Teams to set up and configure a Webex Teams site.</span></span>

2. <span data-ttu-id="b5bf8-114">每 24 小时复制一次 Webex Teams 项，然后复制到"完成"合并 1 网站。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-114">Once every 24 hours, Webex Teams items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="b5bf8-115">连接器还会将 Webex Teams 项目转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-115">The connector also converts the Webex Teams items to an email message format.</span></span>

3. <span data-ttu-id="b5bf8-116">在 Microsoft 365 合规中心创建的 Webex Teams 连接器，每天连接到 Microsoft Merge1，将 Webex Teams 项转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-116">The Webex Teams connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 every day, and transfers the Webex Teams items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b5bf8-117">连接器使用自动用户映射的 *Email* 属性值将项目导入特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="b5bf8-118">在用户邮箱中创建名为 **Webex Teams** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-118">A subfolder in the Inbox folder named **Webex Teams** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="b5bf8-119">连接器使用 *Email* 属性的值实现此操作。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="b5bf8-120">每个 Webex Teams 项都包含此属性，该属性用该项目每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-120">Every Webex Teams item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b5bf8-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="b5bf8-121">Before you begin</span></span>

- <span data-ttu-id="b5bf8-122">为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="b5bf8-123">若要创建此帐户，请联系["用户支持人员"。](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="b5bf8-123">To create this account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="b5bf8-124">在步骤 1 中创建连接器时，将登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b5bf8-125">在 上创建 [https://developer.webex.com/](https://developer.webex.com) 一个应用程序，以从 Webex Teams 帐户提取数据。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-125">Create an application at [https://developer.webex.com/](https://developer.webex.com) to fetch data from your Webex Teams account.</span></span> <span data-ttu-id="b5bf8-126">有关创建应用程序的分步说明，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="b5bf8-126">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span></span>

   <span data-ttu-id="b5bf8-127">创建此应用程序时，Webex 平台将生成一组唯一凭据。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-127">When you create this application, the Webex platform generates a set of unique credentials.</span></span> <span data-ttu-id="b5bf8-128">在全局合并 1 网站上配置 Webex Teams 连接器时，步骤 2 中会使用这些凭据。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-128">These credentials are used in Step 2 when you configure the Webex Teams connector on the Global Merge1 site.</span></span>

- <span data-ttu-id="b5bf8-129">必须在步骤 1 中创建 Webex Teams 连接器 (在步骤 3) 中完成此连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-129">The user who creates the Webex Teams connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b5bf8-130">在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b5bf8-131">默认情况下，此角色不会分配给 Exchange Online 中的角色组。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="b5bf8-132">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b5bf8-133">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b5bf8-134">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-134">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webex-teams-connector"></a><span data-ttu-id="b5bf8-135">步骤 1：设置 Webex Teams 连接器</span><span class="sxs-lookup"><span data-stu-id="b5bf8-135">Step 1: Set up the Webex Teams connector</span></span>

<span data-ttu-id="b5bf8-136">第一步是获取对数据连接器的访问权限并设置[Webex Teams](https://globanet.com/webex-teams/)连接器。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-136">The first step is to gain access to the **Data Connectors** and set up the [Webex Teams](https://globanet.com/webex-teams/) connector.</span></span>

1. <span data-ttu-id="b5bf8-137">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **Webex Teams**。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webex Teams**.</span></span>

2. <span data-ttu-id="b5bf8-138">在 **"Webex Teams** 产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="b5bf8-138">On the **Webex Teams** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b5bf8-139">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="b5bf8-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b5bf8-140">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="b5bf8-141">登录到 Merge1 帐户以配置连接器。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="b5bf8-142">步骤 2：在"完成"合并 1 网站中配置 Webex Teams 连接器</span><span class="sxs-lookup"><span data-stu-id="b5bf8-142">Step 2: Configure the Webex Teams connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="b5bf8-143">第二步是在 Merge1 网站上配置 Webex Teams 连接器。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-143">The second step is to configure the Webex Teams connector on the Merge1 site.</span></span> <span data-ttu-id="b5bf8-144">若要了解如何配置 Webex Teams 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-144">For information about how to configure the Webex Teams connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="b5bf8-145">单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="b5bf8-146">步骤 3：映射用户并完成连接器设置</span><span class="sxs-lookup"><span data-stu-id="b5bf8-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="b5bf8-147">若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b5bf8-147">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="b5bf8-148">在" **将 Webex Teams 用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-148">On the **Map Webex Teams users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="b5bf8-149">Webex Teams 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-149">The Webex Teams items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="b5bf8-150">如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="b5bf8-151">单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-151">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webex-teams-connector"></a><span data-ttu-id="b5bf8-152">步骤 4：监视 Webex Teams 连接器</span><span class="sxs-lookup"><span data-stu-id="b5bf8-152">Step 4: Monitor the Webex Teams connector</span></span>

<span data-ttu-id="b5bf8-153">创建 Webex Teams 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-153">After you create the Webex Teams connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b5bf8-154">转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b5bf8-155">单击" **连接器"** 选项卡，然后选择 **Webex Teams** 连接器以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-155">Click the **Connectors** tab and then select the **Webex Teams** connector to display the flyout page.</span></span> <span data-ttu-id="b5bf8-156">此页面包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b5bf8-157">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b5bf8-158">此日志包含有关已导入到 Microsoft 云的数据的信息。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-158">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b5bf8-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="b5bf8-159">Known issues</span></span>

- <span data-ttu-id="b5bf8-160">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b5bf8-161">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="b5bf8-161">Support for larger items will be available at a later date.</span></span>