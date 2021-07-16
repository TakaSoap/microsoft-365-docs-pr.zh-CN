---
title: 设置连接器以在聊天连接 ICE 聊天Microsoft 365
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
description: 了解如何设置和使用 17a-4 ICE 连接 Chat DataParser 连接器，以在聊天连接中导入和存档 ICE Microsoft 365。
ms.openlocfilehash: 0aac5c701f122eaf99497635281ebc07d835fc2e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454477"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data"></a><span data-ttu-id="57f1c-103">设置连接器以存档 ICE 连接聊天数据</span><span class="sxs-lookup"><span data-stu-id="57f1c-103">Set up a connector to archive ICE Connect Chat data</span></span>

<span data-ttu-id="57f1c-104">使用 17a-4 LLC 中的[ICE DataParser](https://www.17a-4.com/ice-dataparser/)将 ICE 连接 Chat 数据导入并存档到组织用户Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="57f1c-104">Use the [ICE DataParser](https://www.17a-4.com/ice-dataparser/) from 17a-4 LLC to import and archive data from ICE Connect Chat to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="57f1c-105">DataParser 包括一个 ICE 聊天连接器，该连接器配置为捕获来自第三方数据源的项目，并导入这些项Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="57f1c-105">The DataParser includes an ICE Chat connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="57f1c-106">ICE DataParser 连接器将 ICE 连接 聊天数据转换为电子邮件格式，然后将这些项目导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="57f1c-106">The ICE DataParser connector converts ICE Connect Chat data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="57f1c-107">ICE 连接聊天数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="57f1c-107">After ICE Connect Chat data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="57f1c-108">使用 ICE DataParser 连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="57f1c-108">Using an ICE DataParser connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ice-chat-data"></a><span data-ttu-id="57f1c-109">存档 ICE 聊天数据概述</span><span class="sxs-lookup"><span data-stu-id="57f1c-109">Overview of archiving ICE Chat data</span></span>

<span data-ttu-id="57f1c-110">以下概述介绍使用数据连接器在聊天中存档 ICE 连接 Chat 数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="57f1c-110">The following overview explains the process of using a data connector to archive ICE Connect Chat data in Microsoft 365.</span></span>

![ICE 的存档工作流连接 17a-4 聊天数据](../media/ICEChatDataParserConnectorWorkflow.png)

1. <span data-ttu-id="57f1c-112">你的组织与 17a-4 一起设置和配置 ICE DataParser。</span><span class="sxs-lookup"><span data-stu-id="57f1c-112">Your organization works with 17a-4 to set up and configure the ICE DataParser.</span></span>

2. <span data-ttu-id="57f1c-113">DataParser 会连接 ICE 聊天聊天项目。</span><span class="sxs-lookup"><span data-stu-id="57f1c-113">On a regular basis, ICE Connect Chat items are collected by the DataParser.</span></span> <span data-ttu-id="57f1c-114">DataParser 还会将邮件内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="57f1c-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="57f1c-115">在 microsoft 云中创建的 ICE DataParser 连接器Microsoft 365 合规中心 DataParser，将邮件传输至 Microsoft 云中的Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="57f1c-115">The ICE DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="57f1c-116">"收件箱"文件夹中名为 **ICE DataParser** 的子文件夹是在用户邮箱中创建的，ICE 连接 Chat 项目将导入到该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="57f1c-116">A subfolder in the Inbox folder named **ICE DataParser** is created in the user mailboxes, and the ICE Connect Chat items are imported to that folder.</span></span> <span data-ttu-id="57f1c-117">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="57f1c-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="57f1c-118">每个 ICE 连接 聊天项目都包含此属性，该属性填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="57f1c-118">Every ICE Connect Chat item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="57f1c-119">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="57f1c-119">Before you set up a connector</span></span>

- <span data-ttu-id="57f1c-120">为 Microsoft 连接器创建 DataParser 帐户。</span><span class="sxs-lookup"><span data-stu-id="57f1c-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="57f1c-121">为此，请联系 [17a-4 LLC](https://www.17a-4.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="57f1c-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="57f1c-122">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="57f1c-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="57f1c-123">必须在步骤 1 (步骤 1 中创建 ICE DataParser 连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="57f1c-123">The user who creates the ICE DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="57f1c-124">若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="57f1c-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="57f1c-125">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="57f1c-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="57f1c-126">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="57f1c-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="57f1c-127">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="57f1c-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="57f1c-128">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="57f1c-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-ice-dataparser-connector"></a><span data-ttu-id="57f1c-129">步骤 1：设置 ICE DataParser 连接器</span><span class="sxs-lookup"><span data-stu-id="57f1c-129">Step 1: Set up an ICE DataParser connector</span></span>

<span data-ttu-id="57f1c-130">第一步是访问 Microsoft 365 合规中心 中的"数据连接器"页，并创建 ICE 连接 17a-4 连接器。</span><span class="sxs-lookup"><span data-stu-id="57f1c-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for ICE Connect Chat data.</span></span>

1. <span data-ttu-id="57f1c-131">转到 ， <https://compliance.microsoft.com> 然后单击数据 **连接器**  >  **ICE DataParser**。</span><span class="sxs-lookup"><span data-stu-id="57f1c-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **ICE DataParser**.</span></span>

2. <span data-ttu-id="57f1c-132">在 **ICE DataParser** 产品说明页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="57f1c-132">On the **ICE DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="57f1c-133">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="57f1c-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="57f1c-134">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="57f1c-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="57f1c-135">登录到你的 17a-4 帐户并完成 ICE DataParser 连接向导中的步骤。</span><span class="sxs-lookup"><span data-stu-id="57f1c-135">Sign in to your 17a-4 account and complete the steps in the ICE DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-ice-dataparser-connector"></a><span data-ttu-id="57f1c-136">步骤 2：配置 ICE DataParser 连接器</span><span class="sxs-lookup"><span data-stu-id="57f1c-136">Step 2: Configure the ICE DataParser connector</span></span>

<span data-ttu-id="57f1c-137">与 17a-4 支持人员一起配置 ICE DataParser 连接器。</span><span class="sxs-lookup"><span data-stu-id="57f1c-137">Work with 17a-4 Support to configure the ICE DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="57f1c-138">步骤 3：映射用户</span><span class="sxs-lookup"><span data-stu-id="57f1c-138">Step 3: Map users</span></span>

<span data-ttu-id="57f1c-139">ICE DataParser 连接器会自动将用户映射到其Microsoft 365电子邮件地址，然后再将数据导入Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="57f1c-139">The ICE DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-ice-dataparser-connector"></a><span data-ttu-id="57f1c-140">步骤 4：监视 ICE DataParser 连接器</span><span class="sxs-lookup"><span data-stu-id="57f1c-140">Step 4: Monitor the ICE DataParser connector</span></span>

<span data-ttu-id="57f1c-141">创建 ICE DataParser 连接器后，可以查看连接器在连接器Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="57f1c-141">After you create an ICE DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="57f1c-142">转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="57f1c-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="57f1c-143">单击 **"连接器"** 选项卡，然后选择您创建的 ICE DataParser 连接器以显示浮出控件页，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="57f1c-143">Click the **Connectors** tab and then select the ICE DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="57f1c-144">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="57f1c-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="57f1c-145">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="57f1c-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="57f1c-146">已知问题</span><span class="sxs-lookup"><span data-stu-id="57f1c-146">Known issues</span></span>

<span data-ttu-id="57f1c-147">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="57f1c-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="57f1c-148">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="57f1c-148">Support for larger items will be available at a later date.</span></span>
