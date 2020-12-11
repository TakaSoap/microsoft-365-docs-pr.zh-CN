---
title: 设置连接器以存档 TeleMessage 企业号码存档程序的数据
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
description: 管理员可以设置连接器以从 TeleMessage Enterprise Number Archiver 导入和存档短信和彩信数据。 这允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 01c2807606449c576e292f8819a861b1193b4723
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620018"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a><span data-ttu-id="fed59-104">设置连接器以存档企业号码数据</span><span class="sxs-lookup"><span data-stu-id="fed59-104">Set up a connector to archive Enterprise Number data</span></span>

<span data-ttu-id="fed59-105">使用 Microsoft 365 合规中心中的 TeleMessage 连接器，从企业号码存档器导入并存档短信服务 (SMS) 和彩信服务 (MMS) 消息、聊天消息、语音呼叫录像和语音呼叫日志。</span><span class="sxs-lookup"><span data-stu-id="fed59-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) and Multimedia Messaging Service (MMS) messages, chat messages, voice call recordings, and voice call logs from the Enterprise Number Archiver.</span></span> <span data-ttu-id="fed59-106">设置和配置连接器后，它将每天连接到组织的 TeleMessage 帐户一次，并且使用 TeleMessage Enterprise Number Archiver 将员工的移动通信数据导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="fed59-106">After you set up and configure a connector, it connects to your organization's TeleMessage account once every day and imports the mobile communication data of employees using the TeleMessage Enterprise Number Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="fed59-107">在 TeleMessage Enterprise Number Archiver 连接器数据存储在用户邮箱中之后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于企业号码存档程序数据。</span><span class="sxs-lookup"><span data-stu-id="fed59-107">After the TeleMessage Enterprise Number Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to Enterprise Number Archiver data.</span></span> <span data-ttu-id="fed59-108">例如，您可以使用内容搜索搜索 TeleMessage 企业号码存档程序 SMS、MMS 和语音呼叫，或将包含企业号码存档连接器数据的邮箱与高级电子数据展示案例中的保管人关联。</span><span class="sxs-lookup"><span data-stu-id="fed59-108">For example, you can search the TeleMessage Enterprise Number Archiver SMS, MMS, and Voice Call using Content Search or associate the mailbox that contains the Enterprise Number Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="fed59-109">使用企业数字存档连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规策略。</span><span class="sxs-lookup"><span data-stu-id="fed59-109">Using an Enterprise Number Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-enterprise-number-data"></a><span data-ttu-id="fed59-110">存档企业数字数据概述</span><span class="sxs-lookup"><span data-stu-id="fed59-110">Overview of archiving Enterprise Number data</span></span>

<span data-ttu-id="fed59-111">以下概述介绍了使用连接器在 Microsoft 365 中存档企业网络数据的过程。</span><span class="sxs-lookup"><span data-stu-id="fed59-111">The following overview explains the process of using a connector to archive Enterprise Network data in Microsoft 365.</span></span>

![企业号码存档工作流](../media/EnterpriseNumberConnectorWorkflow.png)

1. <span data-ttu-id="fed59-113">您的组织与 TeleMessage 合作，以设置企业号码存档连接器。</span><span class="sxs-lookup"><span data-stu-id="fed59-113">Your organization works with TeleMessage to set up an Enterprise Number Archiver connector.</span></span> <span data-ttu-id="fed59-114">有关详细信息，请参阅 [此处](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)。</span><span class="sxs-lookup"><span data-stu-id="fed59-114">For more details refer to [here](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).</span></span>

2. <span data-ttu-id="fed59-115">在 Microsoft 365 合规中心创建的企业号码存档连接器每天连接到 TeleMessage 网站，将过去 24 小时内的电子邮件转移到 Microsoft 云中安全的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="fed59-115">The Enterprise Number Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

3. <span data-ttu-id="fed59-116">连接器将移动通信项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="fed59-116">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="fed59-117">将创建一个名为"企业数字存档程序"的新文件夹，该文件夹将导入到特定用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="fed59-117">A new folder named Enterprise Number Archiver is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="fed59-118">连接器使用用户的电子邮件地址属性的值 *进行映射* 。</span><span class="sxs-lookup"><span data-stu-id="fed59-118">The connector does mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="fed59-119">每个电子邮件都包含此属性，此属性填充了电子邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fed59-119">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="fed59-120">除了使用用户的电子邮件地址属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。</span><span class="sxs-lookup"><span data-stu-id="fed59-120">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="fed59-121">此映射文件应包含每个用户的移动号码和相应的 Microsoft 365 邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="fed59-121">This mapping file should contain User’s mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="fed59-122">如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，</span><span class="sxs-lookup"><span data-stu-id="fed59-122">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="fed59-123">如果找不到与用户移动电话号码对应的有效 Microsoft 365 用户，连接器将使用电子邮件项目的用户电子邮件地址属性。</span><span class="sxs-lookup"><span data-stu-id="fed59-123">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="fed59-124">如果连接器在自定义映射文件或电子邮件项目的用户电子邮件地址属性中找不到有效的 Microsoft 365 用户，将不会导入该项目。</span><span class="sxs-lookup"><span data-stu-id="fed59-124">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user’s email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fed59-125">开始之前</span><span class="sxs-lookup"><span data-stu-id="fed59-125">Before you begin</span></span>

<span data-ttu-id="fed59-126">存档企业号码存档程序数据所需的一些实施步骤在 Microsoft 365 外部，必须先完成这些步骤，然后才能在合规中心创建连接器。</span><span class="sxs-lookup"><span data-stu-id="fed59-126">Some of the implementation steps required to archive Enterprise Number Archiver data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="fed59-127">从 [TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 中订购企业号码存档程序服务，并获取组织的有效管理帐户。</span><span class="sxs-lookup"><span data-stu-id="fed59-127">Order the [Enterprise Number Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="fed59-128">在合规中心创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="fed59-128">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="fed59-129">在 TeleMessage 帐户中注册需要企业号码 SMS/MMS 网络存档的所有用户。</span><span class="sxs-lookup"><span data-stu-id="fed59-129">Register all users that require Enterprise Number SMS/MMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="fed59-130">注册用户时，请务必使用用于其 Microsoft 365 帐户的相同电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fed59-130">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="fed59-131">在员工的移动电话上安装和激活 TeleMessage Enterprise Number Archiver 应用。</span><span class="sxs-lookup"><span data-stu-id="fed59-131">Install and activate the TeleMessage Enterprise Number Archiver app on the mobile phones of your employees.</span></span>

- <span data-ttu-id="fed59-132">必须在 Exchange Online 中为创建企业号码存档连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="fed59-132">The user who creates a Enterprise Number Archiver connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fed59-133">这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。</span><span class="sxs-lookup"><span data-stu-id="fed59-133">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fed59-134">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="fed59-134">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fed59-135">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="fed59-135">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fed59-136">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="fed59-136">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fed59-137">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="fed59-137">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-an-enterprise-number-archiver-connector"></a><span data-ttu-id="fed59-138">创建企业号码存档程序连接器</span><span class="sxs-lookup"><span data-stu-id="fed59-138">Create an Enterprise Number Archiver connector</span></span>

<span data-ttu-id="fed59-139">完成上一部分中介绍的先决条件后，可以在 Microsoft 365 合规中心创建企业数字存档程序连接器。</span><span class="sxs-lookup"><span data-stu-id="fed59-139">After you've completed the prerequisites described in the previous section, you can create an Enterprise Number Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fed59-140">连接器使用你提供的信息连接到 TeleMessage 网站，将短信、彩信和语音呼叫消息转移到 Microsoft 365 中的相应用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="fed59-140">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS, MMS, and voice call messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="fed59-141">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击"**数据连接器** \> **企业数字存档程序"。**</span><span class="sxs-lookup"><span data-stu-id="fed59-141">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **Enterprise Number Archiver**.</span></span>

2. <span data-ttu-id="fed59-142">在" **企业数字存档程序** 产品说明"页上，单击 **"添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="fed59-142">On the **Enterprise Number Archiver** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="fed59-143">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="fed59-143">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fed59-144">在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="fed59-144">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="fed59-145">**用户名：** TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="fed59-145">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="fed59-146">**密码：** TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="fed59-146">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="fed59-147">创建连接器后，可以关闭弹出窗口并转到下一页。</span><span class="sxs-lookup"><span data-stu-id="fed59-147">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="fed59-148">在" **用户映射"** 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="fed59-148">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="fed59-149">若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="fed59-149">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="fed59-150">查看设置，然后单击" **完成** "创建连接器。</span><span class="sxs-lookup"><span data-stu-id="fed59-150">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="fed59-151">转到"数据连接器 **"页中的** "连接器"选项卡以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="fed59-151">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fed59-152">已知问题</span><span class="sxs-lookup"><span data-stu-id="fed59-152">Known issues</span></span>

- <span data-ttu-id="fed59-153">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="fed59-153">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fed59-154">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="fed59-154">Support for larger items will be available at a later date.</span></span>
