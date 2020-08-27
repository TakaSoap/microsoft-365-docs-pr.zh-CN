---
title: 在&T SMS/MMS 网络数据上设置要存档的连接器
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
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以设置 TeleMessage 连接器，以在&T 移动网络中导入和存档 SMS 和 MMS 数据。 这使您可以在 Microsoft 365 中存档第三方数据源中的数据，以便您可以使用合规性功能（如法律封存、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 809d1d3fa8f043306093a2cd3802c01d054f147a
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282630"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data-preview"></a><span data-ttu-id="f7ef8-104">在&T SMS/MMS 数据 (preview 中设置要存档的连接器) </span><span class="sxs-lookup"><span data-stu-id="f7ef8-104">Set up a connector to archive AT&T SMS/MMS data (preview)</span></span>

<span data-ttu-id="f7ef8-105">使用 Microsoft 365 合规性中心中的 TeleMessage 连接器在&T 移动网络中导入和存档 SMS 和 MMS 数据。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-105">Use a TeleMessage connector in the Microsoft 365 compliance center to import and archive SMS and MMS data from AT&T Mobile Network.</span></span> <span data-ttu-id="f7ef8-106">设置和配置连接器后，它会每天连接到您的组织的&T 网络上，并将短信和 MMS 数据导入 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-106">After you set up and configure a connector, it connects to your organization's AT&T Network once every day, and imports SMS and MMS data to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="f7ef8-107">将 SMS 和 MMS 邮件存储在用户邮箱中之后，可以在&T 网络数据上应用 Microsoft 365 合规性功能，如诉讼保留、内容搜索和 Microsoft 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-107">After SMS and MMS messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to AT&T Network data.</span></span> <span data-ttu-id="f7ef8-108">例如，您可以使用内容搜索在&T 网络数据中搜索，或将包含&T 网络连接器数据的邮箱与高级电子数据展示事例中的保管人程序关联。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-108">For example, you can search AT&T Network data using Content Search or associate the mailbox that contains the AT&T Network connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="f7ef8-109">使用 AT&T 网络连接器在 Microsoft 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-109">Using a AT&T Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-att-network-data"></a><span data-ttu-id="f7ef8-110">&T 网络数据存档概述</span><span class="sxs-lookup"><span data-stu-id="f7ef8-110">Overview of archiving AT&T Network data</span></span>

<span data-ttu-id="f7ef8-111">以下概述说明在 Microsoft 365 中的&T 网络数据上使用连接器存档的过程。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-111">The following overview explains the process of using a connector to archive AT&T Network data in Microsoft 365.</span></span>

![ATT 网络存档工作流](../media/ATTNetworkConnectorWorkflow.png)

1. <span data-ttu-id="f7ef8-113">您的组织与 TeleMessage 协同工作，设置一个 AT&T 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-113">Your organization works with TeleMessage to set up an AT&T Network connector.</span></span> <span data-ttu-id="f7ef8-114">有关信息，请参阅 [&T 网络存档](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/)器。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-114">For information, see [AT&T Network Archiver](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/).</span></span>

2. <span data-ttu-id="f7ef8-115">每24小时一次，来自组织的&T 网络的 SMS 和 MMS 邮件将复制到 TeleMessage 站点。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-115">Once every 24 hours, SMS and MMS messages from your organization’s AT&T Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="f7ef8-116">您在 Microsoft 365 合规性中心中创建的 AT&T 网络连接器每天连接到 TeleMessage 网站，并将短信和 MMS 邮件从以前的24小时传输到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-116">The AT&T Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS and MMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="f7ef8-117">连接器还将短信和 MMS 邮件的内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-117">The connector also converts the content of SMS and MMS messages to an email message format.</span></span>

4. <span data-ttu-id="f7ef8-118">连接器将移动通信项目导入到特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-118">The connector imports the mobile communication items to the mailbox of specific users.</span></span> <span data-ttu-id="f7ef8-119">在用户的邮箱中创建一个名为 **&T SMS/MMS 网络存档** 器的新文件夹，然后将这些项目导入其中。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-119">A new folder named **AT&T SMS/MMS Network Archiver** is created in the user's mailbox and the items will be imported to it.</span></span> <span data-ttu-id="f7ef8-120">连接器通过使用 *用户的电子邮件地址* 属性的值执行此映射。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-120">The connector does this mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="f7ef8-121">每个短信和 MMS 邮件都包含此属性，该属性由邮件的每个参与者的电子邮件地址填充。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-121">Every SMS and MMS message contains this property, which is populated with the email address of every participant of the message.</span></span>
 
   <span data-ttu-id="f7ef8-122">除了使用 *用户电子邮件地址* 属性的值进行自动用户映射之外，还可以通过上载 CSV 映射文件来定义自定义映射。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="f7ef8-123">此映射文件包含组织中用户的移动电话号码和相应的 Microsoft 365 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="f7ef8-124">如果为每个电子邮件项目启用自动用户映射和自定义映射，则连接器将首先查看自定义映射文件。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-124">If you enable both automatic user mapping and custom mapping, for every email item the connector first looks at the custom mapping file.</span></span> <span data-ttu-id="f7ef8-125">如果找不到与移动电话号码对应的有效 Microsoft 365 用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-125">If it doesn't find a valid Microsoft 365 user that corresponds to a mobile phone number, the connector uses the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="f7ef8-126">如果连接器在自定义映射文件或电子邮件地址属性的电子邮件地址属性中找不到有效的 Microsoft 365 用户，则不会导入该项目。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the email item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f7ef8-127">准备工作</span><span class="sxs-lookup"><span data-stu-id="f7ef8-127">Before you begin</span></span>

<span data-ttu-id="f7ef8-128">存档时&T 网络数据需要执行的许多步骤都是 Microsoft 365 外部的，必须先完成，然后才能在合规性中心中创建连接器。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-128">Many of the implementation steps required to archive AT&T Network data are external to Microsoft 365 and must be completed before you can create the connector in the compliance center.</span></span>

- <span data-ttu-id="f7ef8-129">[从 TeleMessage 对移动存档服务](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)进行排序，并为您的组织获取有效的管理帐户。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-129">Order the [mobile archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="f7ef8-130">在合规中心创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="f7ef8-131">在&T 帐户和帐单联系人详细信息中获取，以便您可以填写 TeleMessage 载入表单并从&T 对邮件存档服务进行排序。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-131">Obtain your AT&T account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from AT&T.</span></span>

- <span data-ttu-id="f7ef8-132">在 TeleMessage 帐户中注册所有需要&T SMS/MMS 网络存档的用户。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-132">Register all users that require AT&T SMS/MMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="f7ef8-133">注册用户时，请确保使用的电子邮件地址与用于其 Microsoft 365 帐户的电子邮件地址相同。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="f7ef8-134">您的员工必须在&T 移动网络上有企业拥有和公司责任的移动电话。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-134">Your employees must have corporate-owned and corporate-liable mobile phones on the AT&T mobile network.</span></span> <span data-ttu-id="f7ef8-135">在 Microsoft 365 中存档邮件不适用于员工拥有或 "将自己的设备 (BYOD) 设备。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-135">Archiving messages in Microsoft 365 isn't available for employee-owned or "Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="f7ef8-136">您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-136">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="f7ef8-137">您需要在创建连接器时提供此同意。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-137">You will need to provide this consent when you create the connector.</span></span> <span data-ttu-id="f7ef8-138">若要同意此请求，请转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Office 365 全局管理员的凭据登录，然后接受该请求。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-138">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of an Office 365 global admin, and then accept the request.</span></span> <span data-ttu-id="f7ef8-139">您必须完成此步骤，然后才能成功创建&T 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-139">You have to complete this step before you can successfully create an AT&T Network connector.</span></span>

- <span data-ttu-id="f7ef8-140">在 Exchange Online 中，必须为创建位于&T 网络连接器的用户分配邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-140">The user who creates a AT&T Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="f7ef8-141">这是在 Microsoft 365 合规性中心的 " **数据连接器** " 页中添加连接器所必需的。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-141">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f7ef8-142">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-142">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="f7ef8-143">您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-143">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="f7ef8-144">或者，您可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-144">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="f7ef8-145">有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-145">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-att-network-connector"></a><span data-ttu-id="f7ef8-146">在&T 网络连接器处创建</span><span class="sxs-lookup"><span data-stu-id="f7ef8-146">Create a AT&T Network connector</span></span>

<span data-ttu-id="f7ef8-147">完成上一节中所述的先决条件后，可以在 Microsoft 365 合规性中心中创建一个 "&T" 网络连接器。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-147">After you've completed the prerequisites described in the previous section, you can create an AT&T Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f7ef8-148">连接器使用您提供的信息来连接到 TeleMessage 网站，并将短信和 MMS 邮件传输到 Microsoft 365 中对应的用户邮箱框中。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-148">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS and MMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="f7ef8-149">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击**Data connectors**  \  **&T 网络上的**数据连接器。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-149">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \ **AT&T Network**.</span></span>

2. <span data-ttu-id="f7ef8-150">在 "**位置&T 网络产品**说明" 页上，单击 "**添加连接器**"</span><span class="sxs-lookup"><span data-stu-id="f7ef8-150">On the **AT&T Network product** description page, click **Add connector**</span></span>

3. <span data-ttu-id="f7ef8-151">在 " **服务条款** " 页上，单击 " **接受**"。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-151">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="f7ef8-152">在 " **登录到 TeleMessage** " 页上的 "步骤 3" 下的以下框中，输入所需信息，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-152">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="f7ef8-153">**Username：** 您的 TeleMessage 用户名。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-153">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="f7ef8-154">**密码：** 您的 TeleMessage 密码。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-154">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="f7ef8-155">创建连接器后，可以关闭弹出窗口并转到下一页。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-155">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="f7ef8-156">在 " **用户映射** " 页上，启用自动用户映射。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-156">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="f7ef8-157">若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-157">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="f7ef8-158">提供管理员同意，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-158">Provide admin consent and then click **Next**.</span></span>

   <span data-ttu-id="f7ef8-159">若要提供管理员同意，必须使用 Office 365 全局管理员的凭据登录，然后接受同意请求。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-159">To provide admin consent, you must be signed in with the credentials of an Office 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="f7ef8-160">如果你未以全局管理员身份登录，则可以转到 [此页面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 并使用全局管理员凭据登录以接受请求。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-160">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign-in using global admin credentials to accept the request.</span></span> 

8. <span data-ttu-id="f7ef8-161">查看您的设置，然后单击 " **完成** " 以创建连接器。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-161">Review your settings, and then click **Finish** to create the connector.</span></span>

9. <span data-ttu-id="f7ef8-162">转到合规中心 "**数据连接器**" 页上的 "**连接器**" 选项卡，以查看新连接器的导入过程的进度。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-162">Go to the **Connectors** tab on the **Data connectors** page in the compliance center to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f7ef8-163">已知问题</span><span class="sxs-lookup"><span data-stu-id="f7ef8-163">Known issues</span></span>

- <span data-ttu-id="f7ef8-164">连接器未导入任何大于 10 MB 的项目。</span><span class="sxs-lookup"><span data-stu-id="f7ef8-164">The connector doesn’t import any item larger than 10 MB.</span></span>
