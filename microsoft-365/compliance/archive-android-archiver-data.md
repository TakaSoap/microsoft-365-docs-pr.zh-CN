---
title: 设置连接器以存档 Android 移动数据
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
description: 管理员可以设置 TeleMessage 连接器，以从 Android 移动电话导入和存档短信、彩信和语音呼叫。 这允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如法定保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 5837d5247ca7ac82389d2781110883058ca98bb7
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620527"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a><span data-ttu-id="1443d-104">设置连接器以存档 Android 移动数据</span><span class="sxs-lookup"><span data-stu-id="1443d-104">Set up a connector to archive Android mobile data</span></span>

<span data-ttu-id="1443d-105">使用 Microsoft 365 合规中心中的 TeleMessage 连接器从 Android 移动电话导入和存档短信、彩信、语音呼叫和呼叫日志。</span><span class="sxs-lookup"><span data-stu-id="1443d-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive SMS, MMS, voice calls, and call logs from Android mobile phones.</span></span> <span data-ttu-id="1443d-106">设置和配置连接器后，它将每天连接到组织的 TeleMessage 帐户一次，并且使用 TeleMessage Android 存档器将员工的移动通信导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="1443d-106">After you set up and configure a connector, it connects to your organization's TeleMessage account once every day, and imports the mobile communication of employees using the TeleMessage Android Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="1443d-107">Android 移动电话数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 Android 存档程序数据。</span><span class="sxs-lookup"><span data-stu-id="1443d-107">After data from Android mobile phones is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to Android Archiver data.</span></span> <span data-ttu-id="1443d-108">例如，您可以使用内容搜索搜索 Android 存档程序移动应用，或将包含 Android 存档连接器数据的邮箱与高级电子数据展示案例中的保管人关联。</span><span class="sxs-lookup"><span data-stu-id="1443d-108">For example, you can search Android Archiver mobile communication using Content Search or associate the mailbox that contains the Android Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="1443d-109">使用 Android 存档连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。</span><span class="sxs-lookup"><span data-stu-id="1443d-109">Using an Android Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-android-mobile-data"></a><span data-ttu-id="1443d-110">存档 Android 移动数据概述</span><span class="sxs-lookup"><span data-stu-id="1443d-110">Overview of archiving Android mobile data</span></span>

<span data-ttu-id="1443d-111">以下概述介绍了使用连接器在 Microsoft 365 中存档 Android 移动数据的过程。</span><span class="sxs-lookup"><span data-stu-id="1443d-111">The following overview explains the process of using a connector to archive Android mobile data in Microsoft 365.</span></span>

![Android 存档连接器工作流](../media/AndroidArchiverConnectorWorkflow.png)

1. <span data-ttu-id="1443d-113">你的组织与 TeleMessage 合作，以设置 Android 存档连接器。</span><span class="sxs-lookup"><span data-stu-id="1443d-113">Your organization works with TeleMessage to set up an Android Archiver connector.</span></span> <span data-ttu-id="1443d-114">有关详细信息，请参阅 [Android 存档程序](https://www.telemessage.com/office365-activation-for-android-archiver/)。</span><span class="sxs-lookup"><span data-stu-id="1443d-114">For more information, see [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).</span></span>

2. <span data-ttu-id="1443d-115">每 24 小时一次，从组织的 Android 移动电话发送的短信、彩信、语音呼叫和呼叫日志将复制到 TeleMessage 网站。</span><span class="sxs-lookup"><span data-stu-id="1443d-115">Once every 24 hours, SMS, MMS, voice calls, and call logs from your organization's Android mobile phones are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="1443d-116">在 Microsoft 365 合规中心创建的 Android 存档连接器每天连接到 TeleMessage 网站，将过去 24 小时内的 Android 数据转移到 Microsoft 云中安全的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="1443d-116">The Android Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the Android data from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="1443d-117">连接器还会将 Android 数据转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="1443d-117">The connector also converts the Android data to an email message format.</span></span>

4. <span data-ttu-id="1443d-118">连接器将移动通信项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="1443d-118">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="1443d-119">将创建一个名为 Android Archiver 的新文件夹，该文件夹将导入到特定用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="1443d-119">A new folder named Android Archiver is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="1443d-120">连接器使用用户的电子邮件地址属性的值 *进行映射* 。</span><span class="sxs-lookup"><span data-stu-id="1443d-120">The connector does mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="1443d-121">每个电子邮件都包含此属性，此属性填充了电子邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1443d-121">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="1443d-122">除了使用用户的电子邮件地址属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。</span><span class="sxs-lookup"><span data-stu-id="1443d-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="1443d-123">此映射文件应包含每个用户的移动号码和相应的 Microsoft 365 邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="1443d-123">This mapping file should contain User’s mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="1443d-124">如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，</span><span class="sxs-lookup"><span data-stu-id="1443d-124">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="1443d-125">如果找不到与用户移动电话号码对应的有效 Microsoft 365 用户，连接器将使用电子邮件项目的用户电子邮件地址属性。</span><span class="sxs-lookup"><span data-stu-id="1443d-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="1443d-126">如果连接器在自定义映射文件或电子邮件项目的用户电子邮件地址属性中找不到有效的 Microsoft 365 用户，将不会导入该项目。</span><span class="sxs-lookup"><span data-stu-id="1443d-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user’s email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1443d-127">开始之前</span><span class="sxs-lookup"><span data-stu-id="1443d-127">Before you begin</span></span>

<span data-ttu-id="1443d-128">存档 Android 通信数据所需的一些实施步骤在 Microsoft 365 外部，必须先完成，然后才能在合规中心创建连接器。</span><span class="sxs-lookup"><span data-stu-id="1443d-128">Some of the implementation steps required to archive Android communication data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="1443d-129">从 [TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 订购 Android 存档器服务，并获取组织的有效管理帐户。</span><span class="sxs-lookup"><span data-stu-id="1443d-129">Order the [Android Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="1443d-130">创建连接器时，需要登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="1443d-130">You'll need to sign into this account when you create the connector.</span></span>

- <span data-ttu-id="1443d-131">在 TeleMessage 帐户中注册需要 Android 存档服务的所有用户。</span><span class="sxs-lookup"><span data-stu-id="1443d-131">Register all users that require the Android Archiver service in the TeleMessage account.</span></span> <span data-ttu-id="1443d-132">注册用户时，请务必使用用于其 Microsoft 365 帐户的相同电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1443d-132">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="1443d-133">在员工的移动电话上安装和激活 TeleMessage Android Archiver 应用。</span><span class="sxs-lookup"><span data-stu-id="1443d-133">Install and activate the TeleMessage Android Archiver app on the mobile phones of your employees.</span></span>

- <span data-ttu-id="1443d-134">必须在 Exchange Online 中为创建 Android 存档程序连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="1443d-134">The user who creates a Android Archiver connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="1443d-135">这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。</span><span class="sxs-lookup"><span data-stu-id="1443d-135">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1443d-136">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="1443d-136">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="1443d-137">可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="1443d-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="1443d-138">也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="1443d-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="1443d-139">有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="1443d-139">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-an-android-archiver-connector"></a><span data-ttu-id="1443d-140">创建 Android 存档程序连接器</span><span class="sxs-lookup"><span data-stu-id="1443d-140">Create an Android Archiver connector</span></span>

<span data-ttu-id="1443d-141">最后一步是在 Microsoft 365 合规中心创建 Android 存档连接器。</span><span class="sxs-lookup"><span data-stu-id="1443d-141">The last step is to create an Android Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1443d-142">连接器使用你提供的信息连接到 TeleMessage 网站，将 Android 通信转移到 Microsoft 365 中的相应用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="1443d-142">The connector uses the information you provide to connect to the TeleMessage site and transfer Android communication to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="1443d-143">转到并 [https://compliance.microsoft.com](https://compliance.microsoft.com) 单击 **数据连接器**  >  **Android 存档程序**。</span><span class="sxs-lookup"><span data-stu-id="1443d-143">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** > **Android Archiver**.</span></span>

2. <span data-ttu-id="1443d-144">在 **Android 存档器** 产品说明页上，单击 **"添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="1443d-144">On the **Android Archiver** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="1443d-145">在"**服务条款"页上**，单击"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="1443d-145">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="1443d-146">在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="1443d-146">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="1443d-147">**用户名：** TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="1443d-147">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="1443d-148">**密码：** TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="1443d-148">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="1443d-149">创建连接器后，关闭弹出窗口并单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="1443d-149">After the connector is created, close the pop-up window and click **Next**.</span></span>

6. <span data-ttu-id="1443d-150">在"**用户映射"** 页上，启用自动用户映射并单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="1443d-150">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="1443d-151">如果你需要自定义映射上传 CSV 文件，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="1443d-151">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="1443d-152">查看设置，然后单击" **完成** "创建连接器。</span><span class="sxs-lookup"><span data-stu-id="1443d-152">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="1443d-153">转到"数据连接器 **"页中的** "连接器"选项卡以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="1443d-153">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="1443d-154">已知问题</span><span class="sxs-lookup"><span data-stu-id="1443d-154">Known issues</span></span>

- <span data-ttu-id="1443d-155">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="1443d-155">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="1443d-156">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="1443d-156">Support for larger items will be available at a later date.</span></span>
