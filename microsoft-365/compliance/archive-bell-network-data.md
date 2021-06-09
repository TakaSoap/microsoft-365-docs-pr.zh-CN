---
title: 设置连接器以存档 Bell 短信/MMS 网络数据
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
description: 管理员可以设置 TeleMessage 连接器，以从 Bell 短信和 MMS 数据进行导入和存档。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 7cfdb4556c19261b7e377df72ebe96b9cf20c992
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822210"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a><span data-ttu-id="75890-104">设置连接器以存档 Bell Network 数据</span><span class="sxs-lookup"><span data-stu-id="75890-104">Set up a connector to archive Bell Network data</span></span>

<span data-ttu-id="75890-105">使用 Microsoft 365 合规中心中的 TeleMessage 连接器从 Bell 网络导入和存档短信服务 (短信) 和彩信服务 () 彩信。</span><span class="sxs-lookup"><span data-stu-id="75890-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) and Multimedia Messaging Service (MMS) messages from the Bell Network.</span></span> <span data-ttu-id="75890-106">设置和配置连接器后，它每天连接到组织的 Bell 网络一次，将 短信 和 MMS 邮件导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="75890-106">After you set up and configure a connector, it connects to your organization's Bell Network once every day, and imports SMS and MMS messages to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="75890-107">在 短信 邮件和彩信存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 Bell Network 数据。</span><span class="sxs-lookup"><span data-stu-id="75890-107">After the SMS and MMS messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to Bell Network data.</span></span> <span data-ttu-id="75890-108">例如，您可以使用内容搜索短信 Bell Network 短信/MMS，或者将包含 Bell Network 连接器数据的邮箱与案例的保管人Advanced eDiscovery关联。</span><span class="sxs-lookup"><span data-stu-id="75890-108">For example, you can search Bell Network SMS/MMS using Content Search or associate the mailbox that contains the Bell Network connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="75890-109">使用 Bell 网络连接器导入数据并存档Microsoft 365可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="75890-109">Using a Bell Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-bell-network-data"></a><span data-ttu-id="75890-110">存档 Bell Network 数据概述</span><span class="sxs-lookup"><span data-stu-id="75890-110">Overview of archiving Bell Network data</span></span>

<span data-ttu-id="75890-111">以下概述介绍使用连接器在服务器中存档 Bell Network 数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="75890-111">The following overview explains the process of using a connector to archive Bell Network data in Microsoft 365.</span></span>

![Bell 网络存档工作流](../media/BellNetworkConnectorWorkflow.png)

1. <span data-ttu-id="75890-113">您的组织与 TeleMessage 和 Bell 合作，以设置 Bell 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="75890-113">Your organization works with TeleMessage and Bell to set up a Bell Network connector.</span></span> <span data-ttu-id="75890-114">有关详细信息，请参阅 [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver)。</span><span class="sxs-lookup"><span data-stu-id="75890-114">For more information, see [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).</span></span>

2. <span data-ttu-id="75890-115">实时地短信来自组织的 Bell Network 的彩信和彩信复制到 TeleMessage 站点。</span><span class="sxs-lookup"><span data-stu-id="75890-115">In real time, SMS and MMS messages from your organization's Bell Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="75890-116">在 Microsoft 365 合规中心创建的 Bell 网络连接器每天连接到 TeleMessage 站点，将 短信 和彩信从过去 24 小时转移到 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="75890-116">The Bell Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS and MMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="75890-117">连接器还会将彩信短信彩信的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="75890-117">The connector also converts the content of SMS and MMS messages to an email message format.</span></span>

4. <span data-ttu-id="75890-118">连接器将移动通信项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="75890-118">The connector imports the mobile communication items to the mailbox of specific users.</span></span> <span data-ttu-id="75890-119">将创建一个名为 **Bell 短信/MMS 网络** 存档器的新文件夹，该文件夹将导入到特定用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="75890-119">A new folder named **Bell SMS/MMS Network Archiver** is created in a specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="75890-120">连接器使用"用户的电子邮件地址"属性的值 *执行此映射* 。</span><span class="sxs-lookup"><span data-stu-id="75890-120">The connector does this mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="75890-121">每个短信和彩信都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="75890-121">Every SMS and MMS message contains this property, which is populated with the email address of every participant of the message.</span></span>

   <span data-ttu-id="75890-122">除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。</span><span class="sxs-lookup"><span data-stu-id="75890-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="75890-123">此映射文件包含您Microsoft 365的移动电话号码和相应的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="75890-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="75890-124">如果同时启用自动用户映射和自定义映射，连接器将首先针对每个 Bell Network 项查看自定义映射文件。</span><span class="sxs-lookup"><span data-stu-id="75890-124">If you enable both automatic user mapping and custom mapping, for every Bell Network item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="75890-125">如果找不到与Microsoft 365移动电话号码对应的有效用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。</span><span class="sxs-lookup"><span data-stu-id="75890-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="75890-126">如果连接器在自定义映射文件或 Bell Network 项目的电子邮件地址Microsoft 365找不到有效的用户，该项目将不会导入。</span><span class="sxs-lookup"><span data-stu-id="75890-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the Bell Network item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="75890-127">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="75890-127">Before you set up a connector</span></span>

<span data-ttu-id="75890-128">存档 Bell Network 数据所需的一些实现步骤Microsoft 365且必须先完成，然后才能在合规中心创建连接器。</span><span class="sxs-lookup"><span data-stu-id="75890-128">Some of the implementation steps required to archive Bell Network data are external to Microsoft 365 and must be completed before you can create a connector in the compliance center.</span></span>

- <span data-ttu-id="75890-129">从 [TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) 订购 Bell Network Archiver 服务，并获取组织的有效管理帐户。</span><span class="sxs-lookup"><span data-stu-id="75890-129">Order the [Bell Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="75890-130">在合规中心创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="75890-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="75890-131">获取 Bell Network 帐户和帐单联系人详细信息，以便填写 TeleMessage 载入表单，然后从 Bell 订购邮件存档服务。</span><span class="sxs-lookup"><span data-stu-id="75890-131">Obtain your Bell Network account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from Bell.</span></span>

- <span data-ttu-id="75890-132">在 TeleMessage 帐户中注册需要 Bell 短信/MMS 网络存档的所有用户。</span><span class="sxs-lookup"><span data-stu-id="75890-132">Register all users that require Bell SMS/MMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="75890-133">注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="75890-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="75890-134">员工必须在 Bell 移动网络上拥有公司拥有和负责企业的移动电话。</span><span class="sxs-lookup"><span data-stu-id="75890-134">Your employees must have corporate-owned and corporate-liable mobile phones on the Bell mobile network.</span></span> <span data-ttu-id="75890-135">存档设备Microsoft 365中的消息不适用于员工拥有或"自带设备办公 (BYOD) 设备。</span><span class="sxs-lookup"><span data-stu-id="75890-135">Archiving messages in Microsoft 365 isn't available for employee-owned or "Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="75890-136">必须为创建 Bell 网络连接器的用户分配邮箱导入导出Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="75890-136">The user who creates a Bell Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="75890-137">在安全与合规中心的"数据连接器"页中添加Microsoft 365是必需的。</span><span class="sxs-lookup"><span data-stu-id="75890-137">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="75890-138">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="75890-138">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="75890-139">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="75890-139">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="75890-140">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="75890-140">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="75890-141">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="75890-141">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="75890-142">此数据连接器可用于美国政府GCC云Microsoft 365环境中。</span><span class="sxs-lookup"><span data-stu-id="75890-142">This data connector is available in GCC environments in the Microsoft 365 US Government cloud.</span></span> <span data-ttu-id="75890-143">第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。</span><span class="sxs-lookup"><span data-stu-id="75890-143">Third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Microsoft 365 infrastructure and therefore are not covered by the Microsoft 365 compliance and data protection commitments.</span></span> <span data-ttu-id="75890-144">Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。</span><span class="sxs-lookup"><span data-stu-id="75890-144">Microsoft makes no representation that use of this product to connect to third-party applications implies that those third-party applications are FEDRAMP compliant.</span></span>

## <a name="create-a-bell-network-connector"></a><span data-ttu-id="75890-145">创建 Bell 网络连接器</span><span class="sxs-lookup"><span data-stu-id="75890-145">Create a Bell Network connector</span></span>

<span data-ttu-id="75890-146">最后一步是在合规性中心内Microsoft 365 Bell 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="75890-146">The last step is to create a Bell Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="75890-147">连接器使用您提供的信息连接到 TeleMessage 站点，将 短信/MMS 邮件转移到 Microsoft 365 中的相应用户邮箱框。</span><span class="sxs-lookup"><span data-stu-id="75890-147">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS/ MMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="75890-148">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击数据连接器  >  **Bell 短信/MMS 网络存档器**。</span><span class="sxs-lookup"><span data-stu-id="75890-148">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** > **Bell SMS/MMS Network Archiver**.</span></span>

2. <span data-ttu-id="75890-149">在 **"Bell Network** 产品说明"页上，单击" **添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="75890-149">On the **Bell Network** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="75890-150">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="75890-150">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="75890-151">在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="75890-151">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="75890-152">**用户名：** 你的 TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="75890-152">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="75890-153">**密码：** 你的 TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="75890-153">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="75890-154">创建连接器后，可以关闭弹出窗口并转到下一页。</span><span class="sxs-lookup"><span data-stu-id="75890-154">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="75890-155">在" **用户映射"** 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="75890-155">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="75890-156">若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="75890-156">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="75890-157">查看设置，然后单击" **完成** "创建连接器。</span><span class="sxs-lookup"><span data-stu-id="75890-157">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="75890-158">转到合规 **中心** 内"数据连接器"页上的"连接器"选项卡，查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="75890-158">Go to the **Connectors** tab on the **Data connectors** page in the compliance center to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="75890-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="75890-159">Known issues</span></span>

- <span data-ttu-id="75890-160">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="75890-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="75890-161">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="75890-161">Support for larger items will be available at a later date.</span></span>
