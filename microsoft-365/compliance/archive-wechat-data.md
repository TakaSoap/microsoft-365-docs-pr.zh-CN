---
title: 设置连接器以将 WeChat 数据存档在 Microsoft 365
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
description: 在邮箱中设置并使用连接器Microsoft 365 合规中心在 Microsoft 365 中导入和存档 WeChat 数据。
ms.openlocfilehash: e610b58421c2d84402010c9a5d5ad33ec6da5b04
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054617"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a><span data-ttu-id="55c18-103">设置连接器以存档 WeChat 数据</span><span class="sxs-lookup"><span data-stu-id="55c18-103">Set up a connector to archive WeChat data</span></span>

<span data-ttu-id="55c18-104">使用电子邮件中的 TeleMessage 连接器Microsoft 365 合规中心和存档 WeChat 和 WeCom 呼叫、聊天、附件、文件和已撤回的消息。</span><span class="sxs-lookup"><span data-stu-id="55c18-104">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive WeChat and WeCom calls, chats, attachments, files, and recalled messages.</span></span> <span data-ttu-id="55c18-105">设置和配置连接器后，它将连接到您组织的 TeleMessage 帐户，并且使用 TeleMessage WeChat 存档器将员工的移动通信导入 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="55c18-105">After you set up and configure a connector, it connects to your organization's TeleMessage account, and imports the mobile communication of employees using the TeleMessage WeChat Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="55c18-106">将 WeChat 存档连接器数据存储在用户邮箱中后，您可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、In-Place 存档、审核、通信合规性和 Microsoft 365 保留策略）应用于 WeChat 通信数据。</span><span class="sxs-lookup"><span data-stu-id="55c18-106">After WeChat Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and Microsoft 365 retention policies to WeChat communication data.</span></span> <span data-ttu-id="55c18-107">例如，您可以使用内容搜索搜索 WeChat 通信，或将包含 WeChat 存档连接器数据的邮箱与案例的保管人Advanced eDiscovery关联。</span><span class="sxs-lookup"><span data-stu-id="55c18-107">For example, you can search WeChat communication using Content Search or associate the mailbox that contains the WeChat Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="55c18-108">使用 WeChat 存档器连接器在 Microsoft 365 导入和存档数据可帮助组织遵守公司管理法规和法规策略。</span><span class="sxs-lookup"><span data-stu-id="55c18-108">Using a WeChat Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with corporate governance regulations and regulatory policies.</span></span>

## <a name="overview-of-archiving-wechat-communication-data"></a><span data-ttu-id="55c18-109">存档 WeChat 通信数据概述</span><span class="sxs-lookup"><span data-stu-id="55c18-109">Overview of archiving WeChat communication data</span></span>

<span data-ttu-id="55c18-110">以下概述介绍使用连接器在 Microsoft 365 中存档 WeChat 通信数据的过程。</span><span class="sxs-lookup"><span data-stu-id="55c18-110">The following overview explains the process of using a connector to archive WeChat communications data in Microsoft 365.</span></span>

![WeChat 存档程序数据的存档工作流](../media/WeChatConnectorWorkflow.png)

1. <span data-ttu-id="55c18-112">您的组织与 TeleMessage 合作，以设置 WeChat 存档连接器。</span><span class="sxs-lookup"><span data-stu-id="55c18-112">Your organization works with TeleMessage to set up a WeChat Archiver connector.</span></span>

2. <span data-ttu-id="55c18-113">实时将组织的 WeChat 数据复制到 TeleMessage 网站。</span><span class="sxs-lookup"><span data-stu-id="55c18-113">In real time, your organization's WeChat data is copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="55c18-114">在 Microsoft 365 合规中心 创建的 WeChat 存档连接器每天连接到 TeleMessage 站点，将过去 24 小时内的电子邮件转移到 Microsoft 云中的安全 Azure 存储 区域。</span><span class="sxs-lookup"><span data-stu-id="55c18-114">The WeChat Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="55c18-115">连接器将移动通信项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="55c18-115">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="55c18-116">将在特定用户的邮箱中创建名为 WeChat Archiver 的新文件夹，并且项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55c18-116">A new folder named WeChat Archiver will be created in the specific user's mailbox and the items will be imported to it.</span></span> <span data-ttu-id="55c18-117">连接器使用"用户的电子邮件地址" *属性的值进行映射* 。</span><span class="sxs-lookup"><span data-stu-id="55c18-117">The connector does mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="55c18-118">每个电子邮件都包含此属性，该属性填充了电子邮件每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="55c18-118">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span> <span data-ttu-id="55c18-119">除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。</span><span class="sxs-lookup"><span data-stu-id="55c18-119">In addition to automatic user mapping using the value of the *User's Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="55c18-120">此映射文件应包含用户的移动电话号码和每个用户Microsoft 365相应的邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="55c18-120">This mapping file should contain User's mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="55c18-121">如果启用自动用户映射并提供自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。</span><span class="sxs-lookup"><span data-stu-id="55c18-121">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="55c18-122">如果找不到与用户Microsoft 365用户对应的有效邮件，连接器将使用电子邮件项目的"用户的电子邮件地址"属性。</span><span class="sxs-lookup"><span data-stu-id="55c18-122">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="55c18-123">如果连接器在自定义映射文件或Microsoft 365项的电子邮件地址属性中找不到有效的邮件用户，则不导入该项目。 </span><span class="sxs-lookup"><span data-stu-id="55c18-123">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user's email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="55c18-124">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="55c18-124">Before you set up a connector</span></span>

- <span data-ttu-id="55c18-125">使用 TeleMessage 设置 WeChat 存档连接器。</span><span class="sxs-lookup"><span data-stu-id="55c18-125">Work with TeleMessage to set up a WeChat archive connector.</span></span> <span data-ttu-id="55c18-126">有关详细信息，请参阅激活[TeleMessage WeChat Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)。</span><span class="sxs-lookup"><span data-stu-id="55c18-126">For more information, see [Activating the TeleMessage WeChat Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/).</span></span>

- <span data-ttu-id="55c18-127">为用户设置 TeleMessage 连接器Microsoft 365并获取有效的公司管理帐户。</span><span class="sxs-lookup"><span data-stu-id="55c18-127">Set up a TeleMessage connector for Microsoft 365 and get a valid company administration account.</span></span> <span data-ttu-id="55c18-128">有关详细信息，请参阅 Order [Microsoft 365 Mobile Archiving](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)。</span><span class="sxs-lookup"><span data-stu-id="55c18-128">For more information, see [Order Microsoft 365 Mobile Archiving](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/).</span></span>

- <span data-ttu-id="55c18-129">在 TeleMessage 帐户中注册需要 WeChat 存档的所有用户，其电子邮件地址与用户的 Microsoft 365相同。</span><span class="sxs-lookup"><span data-stu-id="55c18-129">Register all users that require WeChat archiving in the TeleMessage account with the same email address that is used for the user's Microsoft 365 account.</span></span>

- <span data-ttu-id="55c18-130">你需要在组织中用户的移动电话上安装并激活该应用。</span><span class="sxs-lookup"><span data-stu-id="55c18-130">You'll need to install the Tencent WeCom app on the mobile phones of users in your organization and activate it.</span></span> <span data-ttu-id="55c18-131">WeCom 应用允许用户与其他 WeChat 和 WeCom 用户进行通信和聊天。</span><span class="sxs-lookup"><span data-stu-id="55c18-131">The WeCom app lets users communicate and chat with other WeChat and WeCom users.</span></span>

- <span data-ttu-id="55c18-132">必须为在服务器中创建 WeChat 存档Microsoft 365 合规中心分配邮箱导入导出角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="55c18-132">The user who creates a WeChat Archiver connector in the Microsoft 365 compliance center must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="55c18-133">这是在合规中心的"数据连接器 **"页中添加** 连接器所必需。</span><span class="sxs-lookup"><span data-stu-id="55c18-133">This is required to add connectors in the **Data connectors** page in the compliance center.</span></span> <span data-ttu-id="55c18-134">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="55c18-134">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="55c18-135">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="55c18-135">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="55c18-136">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="55c18-136">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="55c18-137">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="55c18-137">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="55c18-138">此数据连接器可用于美国政府GCC云Microsoft 365环境中。</span><span class="sxs-lookup"><span data-stu-id="55c18-138">This data connector is available in GCC environments in the Microsoft 365 US Government cloud.</span></span> <span data-ttu-id="55c18-139">第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。</span><span class="sxs-lookup"><span data-stu-id="55c18-139">Third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Microsoft 365 infrastructure and therefore are not covered by the Microsoft 365 compliance and data protection commitments.</span></span> <span data-ttu-id="55c18-140">Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。</span><span class="sxs-lookup"><span data-stu-id="55c18-140">Microsoft makes no representation that use of this product to connect to third-party applications implies that those third-party applications are FEDRAMP compliant.</span></span>

## <a name="create-a-wechat-archiver-connector"></a><span data-ttu-id="55c18-141">创建 WeChat 存档器连接器</span><span class="sxs-lookup"><span data-stu-id="55c18-141">Create a WeChat Archiver connector</span></span>

<span data-ttu-id="55c18-142">按照本节中的步骤操作，在 Microsoft 365 合规中心 中创建 WeChat 存档Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="55c18-142">Follow the steps in this section to create a WeChat Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="55c18-143">连接器使用您提供的信息连接到 TeleMessage 站点，将 WeChat 通信数据传输至 Microsoft 365 中的相应用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="55c18-143">The connector uses the information you provide to connect to the TeleMessage site and transfer WeChat communications data to the corresponding user mailboxes in Microsoft 365.</span></span>

1. <span data-ttu-id="55c18-144">转到 ， <https://compliance.microsoft.com> 然后单击"**数据连接器**  >  **WeChat Archiver"。**</span><span class="sxs-lookup"><span data-stu-id="55c18-144">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **WeChat Archiver**.</span></span>

2. <span data-ttu-id="55c18-145">在 **"WeChat 存档器** 产品说明"页上，单击" **添加连接器"**</span><span class="sxs-lookup"><span data-stu-id="55c18-145">On the **WeChat Archiver** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="55c18-146">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="55c18-146">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="55c18-147">在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="55c18-147">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

    - <span data-ttu-id="55c18-148">**用户名**：你的 TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="55c18-148">**Username**: Your TeleMessage user name.</span></span>

    - <span data-ttu-id="55c18-149">**密码**：你的 TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="55c18-149">**Password**: Your TeleMessage password.</span></span>

5. <span data-ttu-id="55c18-150">创建连接器后，可以关闭弹出窗口转到下一页。</span><span class="sxs-lookup"><span data-stu-id="55c18-150">After the connector is created, you can close the pop-up window go to the next page.</span></span>

6. <span data-ttu-id="55c18-151">在" **用户映射"** 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="55c18-151">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="55c18-152">您还可以上载自定义用户映射 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="55c18-152">You can also upload a custom user mapping CSV file.</span></span>

7. <span data-ttu-id="55c18-153">单击 **"下** 一步"，查看设置，然后单击" **完成** "以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="55c18-153">Click **Next**, review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="55c18-154">转到"**数据连接器"** 页上的"连接器"选项卡以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="55c18-154">Go to the **Connectors** tab on **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="55c18-155">已知问题</span><span class="sxs-lookup"><span data-stu-id="55c18-155">Known issues</span></span>

- <span data-ttu-id="55c18-156">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="55c18-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="55c18-157">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="55c18-157">Support for larger items will be available at a later date.</span></span>
