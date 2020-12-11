---
title: 设置连接器以在 Microsoft 365 中存档 Verizon 网络数据
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
description: 管理员可以设置 TeleMessage 连接器，以从 Microsoft 365 中的 Verizon 网络导入和存档短信和彩信数据。 这允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如法定保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 2628a373a0232d5cadbb54db7253e56e35596b04
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619768"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a><span data-ttu-id="38abd-104">设置连接器以存档 Verizon 网络数据</span><span class="sxs-lookup"><span data-stu-id="38abd-104">Set up a connector to archive Verizon Network data</span></span>

<span data-ttu-id="38abd-105">使用 Microsoft 365 合规中心中的 TeleMessage 连接器从 Verizon 网络导入和存档短信服务 (SMS) 和彩信服务 (MMS) 数据。</span><span class="sxs-lookup"><span data-stu-id="38abd-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) and Multimedia Messaging Service (MMS) data from Verizon Network.</span></span> <span data-ttu-id="38abd-106">设置和配置连接器后，它每天连接到组织的 Verizon 网络一次，将短信和彩信数据导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="38abd-106">After you set up and configure a connector, it connects to your organization's Verizon Network once every day and imports SMS and MMS data to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="38abd-107">将 Verizon 网络连接器数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 Verizon 数据。</span><span class="sxs-lookup"><span data-stu-id="38abd-107">After Verizon Network connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to Verizon data.</span></span> <span data-ttu-id="38abd-108">例如，您可以使用内容搜索搜索 Verizon SMS 和 MMS 消息，或将包含 Verizon 网络数据的邮箱与高级电子数据展示案例中的保管人关联。</span><span class="sxs-lookup"><span data-stu-id="38abd-108">For example, you can search Verizon SMS and MMS messages using Content Search or associate the mailbox that contains Verizon Network data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="38abd-109">使用 Verizon 网络连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="38abd-109">Using a Verizon Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-verizon-network-data"></a><span data-ttu-id="38abd-110">存档 Verizon 网络数据概述</span><span class="sxs-lookup"><span data-stu-id="38abd-110">Overview of archiving Verizon Network data</span></span>

<span data-ttu-id="38abd-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 Verizon 网络数据的过程。</span><span class="sxs-lookup"><span data-stu-id="38abd-111">The following overview explains the process of using a connector to archive Verizon Network data in Microsoft 365.</span></span>

![Verizon 网络存档工作流](../media/VerizonNetworkConnectorWorkflow.png)

1. <span data-ttu-id="38abd-113">您的组织与 TeleMessage 和 Verizon 合作，以设置 Verizon 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="38abd-113">Your organization works with TeleMessage and Verizon to set up a Verizon Network connector.</span></span> <span data-ttu-id="38abd-114">有关详细信息，请参阅[Verizon Network Archiver。](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/)</span><span class="sxs-lookup"><span data-stu-id="38abd-114">For more information, see [Verizon Network Archiver](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/).</span></span>

2. <span data-ttu-id="38abd-115">每 24 小时一次，来自组织的 Verizon 网络的短信和彩信将复制到 TeleMessage 站点。</span><span class="sxs-lookup"><span data-stu-id="38abd-115">Once every 24 hours, SMS and MMS messages from your organization’s Verizon Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="38abd-116">在 Microsoft 365 合规中心创建的 Verizon 网络连接器每天连接到 TeleMessage 站点，将过去 24 小时内的短信和彩信转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="38abd-116">The Verizon Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS and MMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="38abd-117">连接器还会将短信和彩信的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="38abd-117">The connector also converts the content of SMS and MMS messages to an email message format.</span></span>

4. <span data-ttu-id="38abd-118">连接器将移动通信项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="38abd-118">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="38abd-119">在特定用户的邮箱中创建名为 **Verizon SMS/MMS 网络** 存档程序的新文件夹，项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="38abd-119">A new folder named **Verizon SMS/MMS Network Archiver** is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="38abd-120">连接器使用用户的电子邮件地址属性的值执行 *此映射* 。</span><span class="sxs-lookup"><span data-stu-id="38abd-120">The connector does this mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="38abd-121">每个短信和彩信都包含此属性，此属性填充了邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="38abd-121">Every SMS and MMS message contains this property, which is populated with the email address of every participant of the message.</span></span>

   <span data-ttu-id="38abd-122">除了使用用户的电子邮件地址属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来实现自定义映射。</span><span class="sxs-lookup"><span data-stu-id="38abd-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also implement custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="38abd-123">此映射文件包含组织中用户的移动电话号码和相应的 Microsoft 365 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="38abd-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="38abd-124">如果同时启用自动用户映射和自定义映射，连接器将首先查看自定义映射文件，针对每个 Verizon 项。</span><span class="sxs-lookup"><span data-stu-id="38abd-124">If you enable both automatic user mapping and custom mapping, for every Verizon item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="38abd-125">如果找不到与用户移动电话号码对应的有效 Microsoft 365 用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。</span><span class="sxs-lookup"><span data-stu-id="38abd-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="38abd-126">如果连接器在自定义映射文件或 Verizon 项目的电子邮件地址属性中找不到有效的 Microsoft 365 用户，将不会导入该项目。</span><span class="sxs-lookup"><span data-stu-id="38abd-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the Verizon item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="38abd-127">开始之前</span><span class="sxs-lookup"><span data-stu-id="38abd-127">Before you begin</span></span>

<span data-ttu-id="38abd-128">存档 Verizon 网络数据所需的一些实施步骤在 Microsoft 365 外部，必须先完成，然后才能在合规中心创建连接器。</span><span class="sxs-lookup"><span data-stu-id="38abd-128">Some of the implementation steps required to archive Verizon Network data are external to Microsoft 365 and must be completed before you can create a connector in the compliance center.</span></span>

- <span data-ttu-id="38abd-129">从 [TeleMessage 订购 Verizon 网络](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 存档器服务，并获取组织的有效管理帐户。</span><span class="sxs-lookup"><span data-stu-id="38abd-129">Order the [Verizon Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="38abd-130">在合规中心创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="38abd-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="38abd-131">获取 Verizon 网络帐户和帐单联系人详细信息，以便可以填写 TeleMessage 载入表单，然后从 Verizon 订购邮件存档服务。</span><span class="sxs-lookup"><span data-stu-id="38abd-131">Obtain your Verizon Network account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from Verizon.</span></span>

- <span data-ttu-id="38abd-132">在 TeleMessage 帐户中注册需要 Verizon SMS 和 MMS 存档的所有用户。</span><span class="sxs-lookup"><span data-stu-id="38abd-132">Register all users that require Verizon SMS and MMS archiving in the TeleMessage account.</span></span> <span data-ttu-id="38abd-133">注册用户时，请务必使用用于其 Microsoft 365 帐户的相同电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="38abd-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="38abd-134">员工必须在 Verizon 移动网络上拥有公司拥有和负责企业的移动电话。</span><span class="sxs-lookup"><span data-stu-id="38abd-134">Your employees must have corporate-owned and corporate-liable mobile phones on the Verizon mobile network.</span></span> <span data-ttu-id="38abd-135">Microsoft 365 中的存档邮件不适用于员工拥有或自带设备 (BYOD) 设备。</span><span class="sxs-lookup"><span data-stu-id="38abd-135">Archiving messages in Microsoft 365 isn't available for employee-owned or Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="38abd-136">必须在 Exchange Online 中为创建 Verizon 网络连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="38abd-136">The user who creates a Verizon Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="38abd-137">这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。</span><span class="sxs-lookup"><span data-stu-id="38abd-137">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="38abd-138">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="38abd-138">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="38abd-139">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="38abd-139">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="38abd-140">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="38abd-140">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="38abd-141">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="38abd-141">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-verizon-network-connector"></a><span data-ttu-id="38abd-142">创建 Verizon 网络连接器</span><span class="sxs-lookup"><span data-stu-id="38abd-142">Create a Verizon Network connector</span></span>

<span data-ttu-id="38abd-143">完成上一部分中所述的先决条件后，可以在 Microsoft 365 合规中心创建 Verizon 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="38abd-143">After you've completed the prerequisites described in the previous section, you can create Verizon Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="38abd-144">连接器使用你提供的信息连接到 TeleMessage 网站，将短信和彩信转移到 Microsoft 365 中的相应用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="38abd-144">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS and MMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="38abd-145">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后单击 **"数据连接器**  >  **Verizon 网络"。**</span><span class="sxs-lookup"><span data-stu-id="38abd-145">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** > **Verizon Network**.</span></span>

2. <span data-ttu-id="38abd-146">在 **"Verizon 网络** 产品说明"页上，单击 **"添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="38abd-146">On the **Verizon Network** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="38abd-147">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="38abd-147">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="38abd-148">在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="38abd-148">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>
  
   - <span data-ttu-id="38abd-149">**用户名：** TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="38abd-149">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="38abd-150">**密码：** TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="38abd-150">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="38abd-151">创建连接器后，可以关闭弹出窗口并转到下一页。</span><span class="sxs-lookup"><span data-stu-id="38abd-151">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="38abd-152">在"**用户映射"** 页上，启用自动用户映射并单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="38abd-152">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="38abd-153">如果你需要自定义映射上传 CSV 文件，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="38abd-153">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="38abd-154">查看设置，然后单击" **完成** "创建连接器。</span><span class="sxs-lookup"><span data-stu-id="38abd-154">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="38abd-155">转到"数据连接器 **"页中的** "连接器"选项卡以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="38abd-155">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="38abd-156">已知问题</span><span class="sxs-lookup"><span data-stu-id="38abd-156">Known issues</span></span>

- <span data-ttu-id="38abd-157">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="38abd-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="38abd-158">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="38abd-158">Support for larger items will be available at a later date.</span></span>
