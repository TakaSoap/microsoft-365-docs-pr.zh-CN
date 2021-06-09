---
title: 设置连接器以在服务中存档 TELUS 网络Microsoft 365
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
description: 管理员可以设置 TeleMessage 连接器，以在 短信 中导入和存档 TELUS 网络Microsoft 365。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: d5a0875b34c8dca06ac2a81dc33ce1ba44a62671
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822173"
---
# <a name="set-up-a-connector-to-archive-telus-network-data"></a><span data-ttu-id="dd38b-104">设置连接器以存档 TELUS 网络数据</span><span class="sxs-lookup"><span data-stu-id="dd38b-104">Set up a connector to archive TELUS Network data</span></span>

<span data-ttu-id="dd38b-105">使用 Microsoft 365 合规中心中的 TeleMessage 连接器导入并存档 (短信) TELUS 网络的数据。</span><span class="sxs-lookup"><span data-stu-id="dd38b-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) data from your organization's TELUS Network.</span></span> <span data-ttu-id="dd38b-106">设置和配置连接器后，它每天连接到您组织的 TELUS 网络一次，短信数据导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="dd38b-106">After you set up and configure a connector, it connects to your organization's TELUS Network once every day, and imports SMS data to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="dd38b-107">在短信邮件存储在用户邮箱中之后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和Microsoft 365保留策略）应用于 TELUS 数据。</span><span class="sxs-lookup"><span data-stu-id="dd38b-107">After SMS messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to TELUS data.</span></span> <span data-ttu-id="dd38b-108">例如，您可以使用内容搜索搜索 TELUS 短信邮件，或将包含 TELUS 数据的邮箱与案例的保管人Advanced eDiscovery关联。</span><span class="sxs-lookup"><span data-stu-id="dd38b-108">For example, you can search TELUS SMS messages using Content Search or associate the mailbox that contains the TELUS data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="dd38b-109">使用 TELUS 网络连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="dd38b-109">Using a TELUS Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-telus-network-data"></a><span data-ttu-id="dd38b-110">存档 TELUS 网络数据概述</span><span class="sxs-lookup"><span data-stu-id="dd38b-110">Overview of archiving TELUS Network data</span></span>

<span data-ttu-id="dd38b-111">以下概述介绍使用连接器在服务中存档 TELUS 网络数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dd38b-111">The following overview explains the process of using a connector to archive TELUS Network data in Microsoft 365.</span></span>

![TELUS 网络存档工作流](../media/TelusNetworkConnectorWorkflow.png)

1. <span data-ttu-id="dd38b-113">您的组织与 TeleMessage 和 TELUS 一起设置 TELUS 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="dd38b-113">Your organization works with TeleMessage and TELUS to set up a TELUS Network connector.</span></span> <span data-ttu-id="dd38b-114">有关详细信息，请参阅 [TELUS Network Archiver](https://www.telemessage.com/office365-activation-for-telus-network-archiver/)。</span><span class="sxs-lookup"><span data-stu-id="dd38b-114">For more information, see [TELUS Network Archiver](https://www.telemessage.com/office365-activation-for-telus-network-archiver/).</span></span>

2. <span data-ttu-id="dd38b-115">实时短信您组织的 TELUS 网络发送的邮件将复制到 TeleMessage 站点。</span><span class="sxs-lookup"><span data-stu-id="dd38b-115">In real time, SMS messages from your organization's TELUS Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="dd38b-116">在 Microsoft 365 合规中心创建的 TELUS 网络连接器每天连接到 TeleMessage 站点，将 短信 邮件从过去 24 小时转移到 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="dd38b-116">The TELUS Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="dd38b-117">连接器还会将邮件短信转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="dd38b-117">The connector also converts the content of SMS messages to an email message format.</span></span>

4. <span data-ttu-id="dd38b-118">连接器将移动通信项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="dd38b-118">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="dd38b-119">将创建一个名为 **TELUS 短信** Network Archiver 的新文件夹，该文件夹将导入到特定用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dd38b-119">A new folder named **TELUS SMS Network Archiver** is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="dd38b-120">连接器使用"用户的电子邮件地址" *属性的值进行映射* 。</span><span class="sxs-lookup"><span data-stu-id="dd38b-120">The connector does mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="dd38b-121">每短信一封邮件都包含此属性，该属性用邮件中每个参与者的电子邮件地址短信填充。</span><span class="sxs-lookup"><span data-stu-id="dd38b-121">Every SMS message contains this property, which is populated with the email address of every participant of the SMS message.</span></span>

   <span data-ttu-id="dd38b-122">除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来实现自定义映射。</span><span class="sxs-lookup"><span data-stu-id="dd38b-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also implement custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="dd38b-123">此映射文件包含您Microsoft 365的移动电话号码和相应的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dd38b-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="dd38b-124">如果同时启用自动用户映射和自定义映射，连接器首先将针对每个 TELUS 项查看自定义映射文件。</span><span class="sxs-lookup"><span data-stu-id="dd38b-124">If you enable both automatic user mapping and custom mapping, for every TELUS item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="dd38b-125">如果找不到与Microsoft 365移动电话号码对应的有效用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。</span><span class="sxs-lookup"><span data-stu-id="dd38b-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="dd38b-126">如果连接器在自定义映射文件或 TELUS Microsoft 365电子邮件地址属性中找不到有效的邮件用户，则不导入该项目。</span><span class="sxs-lookup"><span data-stu-id="dd38b-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the TELUS item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="dd38b-127">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="dd38b-127">Before you set up a connector</span></span>

<span data-ttu-id="dd38b-128">存档 TELUS 网络数据所需的一些实现步骤位于 Microsoft 365且必须先完成，然后才能在合规中心创建连接器。</span><span class="sxs-lookup"><span data-stu-id="dd38b-128">Some of the implementation steps required to archive TELUS Network data are external to Microsoft 365 and must be completed before you can create a connector in the compliance center.</span></span>

- <span data-ttu-id="dd38b-129">从 [TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 订购 TELUS 网络存档器服务，并获取组织的有效管理帐户。</span><span class="sxs-lookup"><span data-stu-id="dd38b-129">Order the [TELUS Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="dd38b-130">在合规中心创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="dd38b-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="dd38b-131">获取 TELUS 网络帐户和帐单联系人详细信息，以便可以填写 TeleMessage 载入表单，然后从 TELUS 订购邮件存档服务。</span><span class="sxs-lookup"><span data-stu-id="dd38b-131">Obtain your TELUS Network account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from TELUS.</span></span>

- <span data-ttu-id="dd38b-132">在 TeleMessage 帐户中注册短信 TELUS 网络存档的所有用户。</span><span class="sxs-lookup"><span data-stu-id="dd38b-132">Register all users that require TELUS SMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="dd38b-133">注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dd38b-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="dd38b-134">你的员工必须在TELUS 移动网络上拥有公司拥有和负责企业的移动电话。</span><span class="sxs-lookup"><span data-stu-id="dd38b-134">Your employees must have corporate-owned and corporate-liable mobile phones on theTELUS mobile network.</span></span> <span data-ttu-id="dd38b-135">在 BYOD Microsoft 365中存档消息不适用于员工拥有的设备或自带设备 (BYOD) 设备。</span><span class="sxs-lookup"><span data-stu-id="dd38b-135">Archiving messages in Microsoft 365 isn't available for employee-owned or Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="dd38b-136">必须为创建 TELUS 网络连接器的用户分配邮箱导入导出Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="dd38b-136">The user who creates a TELUS Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="dd38b-137">在安全与合规中心的"数据连接器"页中添加Microsoft 365是必需的。</span><span class="sxs-lookup"><span data-stu-id="dd38b-137">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dd38b-138">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="dd38b-138">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="dd38b-139">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="dd38b-139">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="dd38b-140">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="dd38b-140">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="dd38b-141">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="dd38b-141">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="dd38b-142">此数据连接器可用于美国政府GCC云Microsoft 365环境中。</span><span class="sxs-lookup"><span data-stu-id="dd38b-142">This data connector is available in GCC environments in the Microsoft 365 US Government cloud.</span></span> <span data-ttu-id="dd38b-143">第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。</span><span class="sxs-lookup"><span data-stu-id="dd38b-143">Third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Microsoft 365 infrastructure and therefore are not covered by the Microsoft 365 compliance and data protection commitments.</span></span> <span data-ttu-id="dd38b-144">Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。</span><span class="sxs-lookup"><span data-stu-id="dd38b-144">Microsoft makes no representation that use of this product to connect to third-party applications implies that those third-party applications are FEDRAMP compliant.</span></span>

## <a name="create-a-telus-network-connector"></a><span data-ttu-id="dd38b-145">创建 TELUS 网络连接器</span><span class="sxs-lookup"><span data-stu-id="dd38b-145">Create a TELUS Network connector</span></span>

<span data-ttu-id="dd38b-146">完成上一部分中所述的先决条件后，可以在合规性中心内Microsoft 365 TELUS 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="dd38b-146">After you've completed the prerequisites described in the previous section, you can create TELUS Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dd38b-147">连接器使用您提供的信息连接到 TeleMessage 站点，短信邮件传输至 Microsoft 365 中的相应用户邮箱Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dd38b-147">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="dd38b-148">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器**  >  **TELUS 网络"。**</span><span class="sxs-lookup"><span data-stu-id="dd38b-148">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **TELUS Network**.</span></span>

2. <span data-ttu-id="dd38b-149">在 **TELUS 网络** 产品说明页上，单击" **添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="dd38b-149">On the **TELUS Network** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="dd38b-150">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="dd38b-150">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="dd38b-151">在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="dd38b-151">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="dd38b-152">**用户名：** 你的 TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="dd38b-152">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="dd38b-153">**密码：** 你的 TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="dd38b-153">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="dd38b-154">创建连接器后，可以关闭弹出窗口并转到下一页。</span><span class="sxs-lookup"><span data-stu-id="dd38b-154">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="dd38b-155">在"**用户映射"页上**，启用自动用户映射，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="dd38b-155">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="dd38b-156">如果你需要自定义映射上传 CSV 文件，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="dd38b-156">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="dd38b-157">查看设置，然后单击" **完成** "创建连接器。</span><span class="sxs-lookup"><span data-stu-id="dd38b-157">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="dd38b-158">转到"数据连接器" **页中的"** 连接器"选项卡以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="dd38b-158">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="dd38b-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="dd38b-159">Known issues</span></span>

- <span data-ttu-id="dd38b-160">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="dd38b-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="dd38b-161">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="dd38b-161">Support for larger items will be available at a later date.</span></span>
