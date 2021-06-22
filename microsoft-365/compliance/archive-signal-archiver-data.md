---
title: 设置连接器以将信号通信数据存档在 Microsoft 365
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
description: 管理员可以设置 TeleMessage 连接器，以在远程传输中导入和存档Microsoft 365。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: a779cb312e20fdf5fac0987a33734e7e81ba9c74
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054827"
---
# <a name="set-up-a-connector-to-archive-signal-communications-data-preview"></a><span data-ttu-id="bc5da-104">设置连接器以存档信号通信数据 (预览) </span><span class="sxs-lookup"><span data-stu-id="bc5da-104">Set up a connector to archive Signal communications data (preview)</span></span>

<span data-ttu-id="bc5da-105">使用邮箱中的 TeleMessage Microsoft 365 合规中心导入和存档信号聊天、附件、文件以及已删除的消息和呼叫。</span><span class="sxs-lookup"><span data-stu-id="bc5da-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive Signal chats, attachments, files, and deleted messages and calls.</span></span> <span data-ttu-id="bc5da-106">设置和配置连接器后，它将连接到组织的 TeleMessage 帐户，并且使用 TeleMessage 信号存档器将员工的移动通信导入 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="bc5da-106">After you set up and configure a connector, it connects to your organization's TeleMessage account, and imports the mobile communication of employees using the TeleMessage Signal Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="bc5da-107">在信号存档连接器数据存储在用户邮箱中之后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于信号通信数据。</span><span class="sxs-lookup"><span data-stu-id="bc5da-107">After Signal Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content search, and Microsoft 365 retention policies to Signal communications data.</span></span> <span data-ttu-id="bc5da-108">例如，可以使用内容搜索来搜索信号通信，或者将包含信号存档器连接器数据的邮箱与案例的保管人Advanced eDiscovery关联。</span><span class="sxs-lookup"><span data-stu-id="bc5da-108">For example, you can search Signal communication using Content search or associate the mailbox that contains the Signal Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="bc5da-109">使用信号存档器连接器在 Microsoft 365导入和存档数据可帮助组织遵守公司管理法规和法规策略。</span><span class="sxs-lookup"><span data-stu-id="bc5da-109">Using a Signal Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with corporate governance regulations and regulatory policies.</span></span>

## <a name="overview-of-archiving-signal-communications-data"></a><span data-ttu-id="bc5da-110">存档信号通信数据概述</span><span class="sxs-lookup"><span data-stu-id="bc5da-110">Overview of archiving Signal communications data</span></span>

<span data-ttu-id="bc5da-111">以下概述介绍使用连接器在信号传输中存档信号通信数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bc5da-111">The following overview explains the process of using a connector to archive  Signal communication data in Microsoft 365.</span></span>

![信号通信存档工作流](../media/SignalConnectorWorkflow.png)

1. <span data-ttu-id="bc5da-113">您的组织与 TeleMessage 合作，以设置信号存档器连接器。</span><span class="sxs-lookup"><span data-stu-id="bc5da-113">Your organization works with TeleMessage to set up a Signal Archiver connector.</span></span> <span data-ttu-id="bc5da-114">有关详细信息，请参阅激活[TeleMessage 信号存档器Microsoft 365。](https://www.telemessage.com/microsoft-365-activation-for-signal-archiver/)</span><span class="sxs-lookup"><span data-stu-id="bc5da-114">For more information, see [Activating the TeleMessage Signal Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-signal-archiver/).</span></span>

2. <span data-ttu-id="bc5da-115">实时将组织的信号数据复制到 TeleMessage 站点。</span><span class="sxs-lookup"><span data-stu-id="bc5da-115">In real time, your organization's Signal data is copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="bc5da-116">在 Microsoft 365 合规中心 中创建的信号存档器连接器每天连接到 TeleMessage 站点，将过去 24 小时内的电子邮件转移到 Microsoft 云中的安全 Azure 存储 区域。</span><span class="sxs-lookup"><span data-stu-id="bc5da-116">The Signal Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="bc5da-117">连接器将移动通信项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="bc5da-117">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="bc5da-118">将在特定用户的邮箱中创建名为 Signal Archiver 的新文件夹，并且项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bc5da-118">A new folder named Signal Archiver will be created in the specific user's mailbox and the items will be imported to it.</span></span> <span data-ttu-id="bc5da-119">连接器使用"用户的电子邮件地址" *属性的值执行映射* 。</span><span class="sxs-lookup"><span data-stu-id="bc5da-119">The connector does the mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="bc5da-120">每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bc5da-120">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span>

> <span data-ttu-id="bc5da-121">除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。</span><span class="sxs-lookup"><span data-stu-id="bc5da-121">In addition to automatic user mapping using the value of the *User's Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="bc5da-122">此映射文件应包含用户的移动电话号码和每个用户Microsoft 365相应的邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="bc5da-122">This mapping file should contain User's mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="bc5da-123">如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。</span><span class="sxs-lookup"><span data-stu-id="bc5da-123">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="bc5da-124">如果找不到与用户Microsoft 365用户对应的有效邮件，连接器将使用电子邮件项目的"用户的电子邮件地址"属性。</span><span class="sxs-lookup"><span data-stu-id="bc5da-124">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="bc5da-125">如果连接器在自定义映射文件或Microsoft 365项的电子邮件地址属性中找不到有效的邮件用户，则不导入该项目。 </span><span class="sxs-lookup"><span data-stu-id="bc5da-125">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user's email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="bc5da-126">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="bc5da-126">Before you set up a connector</span></span>

- <span data-ttu-id="bc5da-127">从 [TeleMessage 订购信号存档器服务，](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) 并获取组织的有效管理帐户。</span><span class="sxs-lookup"><span data-stu-id="bc5da-127">Order the [Signal Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="bc5da-128">在合规中心创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="bc5da-128">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="bc5da-129">在 TeleMessage 帐户中注册需要信号存档的所有用户。</span><span class="sxs-lookup"><span data-stu-id="bc5da-129">Register all users that require Signal archiving in the TeleMessage account.</span></span> <span data-ttu-id="bc5da-130">注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bc5da-130">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="bc5da-131">在员工的移动电话上安装信号存档器应用并激活它。</span><span class="sxs-lookup"><span data-stu-id="bc5da-131">Install the Signal Archiver app on the mobile phones of your employees and activate it.</span></span> <span data-ttu-id="bc5da-132">信号存档器应用允许他们与其他信号用户进行通信和聊天。</span><span class="sxs-lookup"><span data-stu-id="bc5da-132">The Signal Archiver app allows them to communicate and chat with other Signal users.</span></span>

- <span data-ttu-id="bc5da-133">必须在步骤 3 中为在步骤 3 中创建信号存档器连接器的用户分配邮箱导入导出Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="bc5da-133">The user who creates a Signal Archiver connector in Step 3 must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="bc5da-134">这是在"数据连接器"页的"数据连接器 **"页中添加** Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="bc5da-134">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="bc5da-135">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="bc5da-135">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="bc5da-136">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="bc5da-136">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="bc5da-137">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="bc5da-137">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="bc5da-138">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="bc5da-138">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-signal-archiver-connector"></a><span data-ttu-id="bc5da-139">创建信号存档器连接器</span><span class="sxs-lookup"><span data-stu-id="bc5da-139">Create a Signal Archiver connector</span></span>

<span data-ttu-id="bc5da-140">完成上一部分中介绍的先决条件后，可以在以下位置创建信号存档Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="bc5da-140">After you've completed the prerequisites described in the previous section, you can create the Signal Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="bc5da-141">连接器使用您提供的信息连接到 TeleMessage 站点，将信号通信数据传输至 Microsoft 365 中的相应用户邮箱框。</span><span class="sxs-lookup"><span data-stu-id="bc5da-141">The connector uses the information you provide to connect to the TeleMessage site and transfers Signal communications data to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="bc5da-142">转到 ， <https://compliance.microsoft.com> 然后单击"数据 **连接器信号**  >  **存档器"。**</span><span class="sxs-lookup"><span data-stu-id="bc5da-142">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Signal Archiver**.</span></span>

2. <span data-ttu-id="bc5da-143">在" **信号存档器** 产品说明"页上，单击" **添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="bc5da-143">On the **Signal Archiver** product description page, click **Add connector.**</span></span>

3. <span data-ttu-id="bc5da-144">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="bc5da-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="bc5da-145">在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="bc5da-145">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

    - <span data-ttu-id="bc5da-146">**用户名：** 你的 TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="bc5da-146">**Username:** Your TeleMessage username.</span></span>

    - <span data-ttu-id="bc5da-147">**密码：** 你的 TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="bc5da-147">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="bc5da-148">创建连接器后，可以关闭弹出窗口并转到下一页。</span><span class="sxs-lookup"><span data-stu-id="bc5da-148">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="bc5da-149">在" **用户映射"** 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="bc5da-149">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="bc5da-150">若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="bc5da-150">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="bc5da-151">查看设置，然后单击" **完成** "创建连接器。</span><span class="sxs-lookup"><span data-stu-id="bc5da-151">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="bc5da-152">转到"数据连接器" **页中的"** 连接器"选项卡以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="bc5da-152">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="bc5da-153">已知问题</span><span class="sxs-lookup"><span data-stu-id="bc5da-153">Known issues</span></span>

- <span data-ttu-id="bc5da-154">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="bc5da-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="bc5da-155">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="bc5da-155">Support for larger items will be available at a later date.</span></span>
