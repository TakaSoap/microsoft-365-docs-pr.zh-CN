---
title: 设置连接器以在 Microsoft 365 中存档 WhatsApp 数据
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
description: 管理员可以设置 TeleMessage 连接器以在 Microsoft 365 中导入和存档 WhatsApp 数据。 这使你可以存档 Microsoft 365 中第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 446845b95df7cf460eeb554d72c076b6221f7edc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923390"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a><span data-ttu-id="6c79e-104">设置连接器以存档 WhatsApp 数据</span><span class="sxs-lookup"><span data-stu-id="6c79e-104">Set up a connector to archive WhatsApp data</span></span>

<span data-ttu-id="6c79e-105">使用 Microsoft 365 合规中心中的 TeleMessage 连接器导入和存档 WhatsApp 呼叫、聊天、附件、文件和已删除的消息。</span><span class="sxs-lookup"><span data-stu-id="6c79e-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive WhatsApp calls, chats, attachments, files, and deleted messages.</span></span> <span data-ttu-id="6c79e-106">设置和配置连接器后，它每天连接到组织的 TeleMessage 帐户一次，并且使用 TeleMessage Whatssage WhatsApp Phone Archiver 或 TeleMessage Whatsapp 云存档器将员工的移动通信导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c79e-106">After you set up and configure a connector, it connects to your organization's TeleMessage account once every day, and imports the mobile communication of employees using the TeleMessage WhatsApp Phone Archiver or TeleMessage WhatsApp Cloud Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="6c79e-107">将 WhatsApp 数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 WhatsApp 数据。</span><span class="sxs-lookup"><span data-stu-id="6c79e-107">After WhatsApp data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to WhatsApp data.</span></span> <span data-ttu-id="6c79e-108">例如，您可以使用内容搜索搜索 WhatsApp 邮件，或将包含 WhatsApp 邮件的邮箱与高级电子数据展示案例中的保管人关联。</span><span class="sxs-lookup"><span data-stu-id="6c79e-108">For example, you can search WhatsApp messages using Content Search or associate the mailbox that contains WhatsApp messages with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="6c79e-109">使用 WhatsApp 连接器在 Microsoft 365 中导入和存档数据可帮助你的组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="6c79e-109">Using a WhatsApp connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-whatsapp-data"></a><span data-ttu-id="6c79e-110">存档 WhatsApp 数据概述</span><span class="sxs-lookup"><span data-stu-id="6c79e-110">Overview of archiving WhatsApp data</span></span>

<span data-ttu-id="6c79e-111">以下概述介绍使用连接器在 Microsoft 365 中存档 WhatsApp 数据的过程。</span><span class="sxs-lookup"><span data-stu-id="6c79e-111">The following overview explains the process of using a connector to archive WhatsApp data in Microsoft 365.</span></span>

![WhatsApp 存档工作流](../media/WhatsAppConnectorWorkflow.png)

1. <span data-ttu-id="6c79e-113">您的组织与 TeleMessage 合作，以设置 WhatsApp 存档器连接器。</span><span class="sxs-lookup"><span data-stu-id="6c79e-113">Your organization works with TeleMessage to set up a WhatsApp Archiver connector.</span></span> <span data-ttu-id="6c79e-114">有关详细信息，请参阅 [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver)。</span><span class="sxs-lookup"><span data-stu-id="6c79e-114">For more information, see [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).</span></span>

2. <span data-ttu-id="6c79e-115">每 24 小时一次，组织的 WhatsApp 数据将复制到 TeleMessage 站点。</span><span class="sxs-lookup"><span data-stu-id="6c79e-115">Once every 24 hours, your organization’s WhatsApp data is copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="6c79e-116">在 Microsoft 365 合规中心创建的 WhatsApp 连接器每天连接到 TeleMessage 网站，将过去 24 小时内的 WhatsApp 数据转移到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="6c79e-116">The WhatsApp connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers WhatsApp data from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="6c79e-117">连接器还会将内容 WhatsApp 数据转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="6c79e-117">The connector also converts the content WhatsApp data to an email message format.</span></span>

4. <span data-ttu-id="6c79e-118">连接器将 WhatsApp 数据导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6c79e-118">The connector imports WhatsApp data to the mailbox of a specific user.</span></span> <span data-ttu-id="6c79e-119">将创建一个名为 **WhatsApp Archiver** 的新文件夹，该文件夹将导入到特定用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="6c79e-119">A new folder named **WhatsApp Archiver** is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="6c79e-120">连接器使用"用户的电子邮件地址"属性的值 *执行此映射* 。</span><span class="sxs-lookup"><span data-stu-id="6c79e-120">The connector does this mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="6c79e-121">每个 WhatsApp 邮件都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6c79e-121">Every WhatsApp message contains this property, which is populated with the email address of every participant of the message.</span></span>

   <span data-ttu-id="6c79e-122">除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来实现自定义映射。</span><span class="sxs-lookup"><span data-stu-id="6c79e-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also implement custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="6c79e-123">此映射文件包含组织中用户的移动电话号码和相应的 Microsoft 365 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6c79e-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="6c79e-124">如果同时启用自动用户映射和自定义映射，连接器将首先查看自定义映射文件，每个 WhatsApp 项。</span><span class="sxs-lookup"><span data-stu-id="6c79e-124">If you enable both automatic user mapping and custom mapping, for every WhatsApp item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="6c79e-125">如果找不到与用户的移动电话号码对应的有效 Microsoft 365 用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。</span><span class="sxs-lookup"><span data-stu-id="6c79e-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="6c79e-126">如果连接器在自定义映射文件或 WhatsApp 项目的电子邮件地址属性中找不到有效的 Microsoft 365 用户，该项目将不会导入。</span><span class="sxs-lookup"><span data-stu-id="6c79e-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the WhatsApp item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6c79e-127">开始之前</span><span class="sxs-lookup"><span data-stu-id="6c79e-127">Before you begin</span></span>

<span data-ttu-id="6c79e-128">存档 WhatsApp 通信数据所需的一些实现步骤位于 Microsoft 365 外部，必须先完成这些步骤，然后才能在合规中心创建连接器。</span><span class="sxs-lookup"><span data-stu-id="6c79e-128">Some of the implementation steps required to archive WhatsApp communication data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="6c79e-129">从 [TeleMessage 订购 WhatsApp Archiver](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 服务，并获取组织的有效管理帐户。</span><span class="sxs-lookup"><span data-stu-id="6c79e-129">Order the [WhatsApp Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="6c79e-130">在合规中心创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="6c79e-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="6c79e-131">在 TeleMessage 帐户中注册需要 WhatsApp 存档的所有用户。</span><span class="sxs-lookup"><span data-stu-id="6c79e-131">Register all users that require WhatsApp archiving in the TeleMessage account.</span></span> <span data-ttu-id="6c79e-132">注册用户时，请务必使用用于其 Microsoft 365 帐户的相同电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6c79e-132">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="6c79e-133">在员工的移动电话上安装 TeleMessage [WhatsApp Phone Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) 应用并激活该应用。</span><span class="sxs-lookup"><span data-stu-id="6c79e-133">Install the TeleMessage [WhatsApp Phone Archiver app](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) on the mobile phones of your employees and activate it.</span></span> <span data-ttu-id="6c79e-134">或者，可以在员工的移动电话上安装常规 WhatsApp 或 WhatsApp Business 应用，并扫描 TeleMessage 网站上 QR 代码，以激活 WhatsApp 云存档器服务。</span><span class="sxs-lookup"><span data-stu-id="6c79e-134">Alternatively, you can install the regular WhatsApp or WhatsApp Business apps on the mobile phones of your employees and activate the WhatsApp Cloud Archiver service by scanning a QR code on the TeleMessage website.</span></span> <span data-ttu-id="6c79e-135">有关详细信息，请参阅[WhatsApp Cloud Archiver。](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)</span><span class="sxs-lookup"><span data-stu-id="6c79e-135">For more information, see [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).</span></span>

- <span data-ttu-id="6c79e-136">必须在 Exchange Online 中为创建 Verizon 网络连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="6c79e-136">The user who creates a Verizon Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6c79e-137">这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。</span><span class="sxs-lookup"><span data-stu-id="6c79e-137">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6c79e-138">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="6c79e-138">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="6c79e-139">可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="6c79e-139">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6c79e-140">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="6c79e-140">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6c79e-141">有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。</span><span class="sxs-lookup"><span data-stu-id="6c79e-141">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-whatsapp-archiver-connector"></a><span data-ttu-id="6c79e-142">创建 WhatsApp 存档器连接器</span><span class="sxs-lookup"><span data-stu-id="6c79e-142">Create a WhatsApp Archiver connector</span></span>

<span data-ttu-id="6c79e-143">完成上一部分中所述的先决条件后，可以在 Microsoft 365 合规中心创建 WhatsApp 连接器。</span><span class="sxs-lookup"><span data-stu-id="6c79e-143">After you've completed the prerequisites described in the previous section, you can create the WhatsApp connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6c79e-144">连接器使用您提供的信息连接到 TeleMessage 站点，将 WhatsApp 数据传输至 Microsoft 365 中的相应用户邮箱框。</span><span class="sxs-lookup"><span data-stu-id="6c79e-144">The connector uses the information you provide to connect to the TeleMessage site and transfer the WhatsApp data to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="6c79e-145">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **WhatsApp Archiver**。</span><span class="sxs-lookup"><span data-stu-id="6c79e-145">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **WhatsApp Archiver**.</span></span>

2. <span data-ttu-id="6c79e-146">在 **"WhatsApp 存档程序产品** 说明"页上，单击" **添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="6c79e-146">On the **WhatsApp Archiver** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="6c79e-147">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="6c79e-147">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="6c79e-148">在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="6c79e-148">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="6c79e-149">**用户名：** 你的 TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="6c79e-149">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="6c79e-150">**密码：** 你的 TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="6c79e-150">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="6c79e-151">创建连接器后，可以关闭弹出窗口并转到下一页。</span><span class="sxs-lookup"><span data-stu-id="6c79e-151">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="6c79e-152">在"**用户映射"页上**，启用自动用户映射，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="6c79e-152">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="6c79e-153">如果你需要自定义映射上传 CSV 文件，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="6c79e-153">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="6c79e-154">查看设置，然后单击" **完成** "创建连接器。</span><span class="sxs-lookup"><span data-stu-id="6c79e-154">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="6c79e-155">转到"数据连接器" **页中的"** 连接器"选项卡以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="6c79e-155">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6c79e-156">已知问题</span><span class="sxs-lookup"><span data-stu-id="6c79e-156">Known issues</span></span>

- <span data-ttu-id="6c79e-157">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="6c79e-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="6c79e-158">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="6c79e-158">Support for larger items will be available at a later date.</span></span>