---
title: 设置连接器以将 ServiceNow 17a-4 DataParser 数据存档到 Microsoft 365
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
description: 了解如何设置和使用 17a-4 ServiceNow DataParser 连接器在 Microsoft 365 中导入和存档 ServiceNow 数据。
ms.openlocfilehash: a01e075b6cbf400bc3b7dc38950d87443a46f81c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454417"
---
# <a name="set-up-a-connector-to-archive-data-from-servicenow"></a><span data-ttu-id="6bd0a-103">设置连接器以从 ServiceNow 存档数据</span><span class="sxs-lookup"><span data-stu-id="6bd0a-103">Set up a connector to archive data from ServiceNow</span></span>

<span data-ttu-id="6bd0a-104">使用 17a-4 LLC 中的[ServiceNow DataParser](https://www.17a-4.com/dataparser/)将数据从 ServiceNow 导入并存档到 Microsoft 365 组织的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-104">Use the [ServiceNow DataParser](https://www.17a-4.com/dataparser/) from 17a-4 LLC to import and archive data from ServiceNow to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="6bd0a-105">DataParser 包括一个 ServiceNow 连接器，该连接器配置为捕获来自第三方数据源的项目，并导入这些项Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-105">The DataParser includes a ServiceNow connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="6bd0a-106">ServiceNow DataParser 连接器将 ServiceNow 数据转换为电子邮件格式，然后将这些项目导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-106">The ServiceNow DataParser connector converts ServiceNow data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="6bd0a-107">将 ServiceNow 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-107">After ServiceNow data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="6bd0a-108">使用 ServiceNow 连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府及法规策略。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-108">Using a ServiceNow connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-servicenow-data"></a><span data-ttu-id="6bd0a-109">存档 ServiceNow 数据概述</span><span class="sxs-lookup"><span data-stu-id="6bd0a-109">Overview of archiving ServiceNow data</span></span>

<span data-ttu-id="6bd0a-110">以下概述介绍使用数据连接器在数据连接器中存档 ServiceNow Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-110">The following overview explains the process of using a data connector to archive ServiceNow data in Microsoft 365.</span></span>

![17a-4 中 ServiceNow 数据的存档工作流](../media/ServiceNowDataParserConnectorWorkflow.png)

1. <span data-ttu-id="6bd0a-112">您的组织与 17a-4 一起设置和配置 ServiceNow DataParser。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-112">Your organization works with 17a-4 to set up and configure the ServiceNow DataParser.</span></span>

2. <span data-ttu-id="6bd0a-113">DataParser 会定期收集 ServiceNow 项。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-113">On a regular basis, ServiceNow items are collected by the DataParser.</span></span> <span data-ttu-id="6bd0a-114">DataParser 还会将邮件内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="6bd0a-115">在 Microsoft 365 合规中心 创建的 ServiceNow DataParser 连接器连接到 DataParser，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-115">The ServiceNow DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="6bd0a-116">在用户邮箱中创建名为 **ServiceNow DataParser** 的收件箱文件夹中的子文件夹，并且 ServiceNow 项目将导入到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-116">A subfolder in the Inbox folder named **ServiceNow DataParser** is created in the user mailboxes, and the ServiceNow items are imported to that folder.</span></span> <span data-ttu-id="6bd0a-117">连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="6bd0a-118">每个 ServiceNow 项都包含此属性，该属性填充了每个参与者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-118">Every ServiceNow item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="6bd0a-119">设置连接器之前</span><span class="sxs-lookup"><span data-stu-id="6bd0a-119">Before you set up a connector</span></span>

- <span data-ttu-id="6bd0a-120">为 Microsoft 连接器创建 DataParser 帐户。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="6bd0a-121">为此，请联系 [17a-4 LLC](https://www.17a-4.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="6bd0a-122">在步骤 1 中创建连接器时，需要登录此帐户。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="6bd0a-123">必须在步骤 1 (中创建 ServiceNow DataParser 连接器，并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-123">The user who creates the ServiceNow DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6bd0a-124">若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6bd0a-125">默认情况下，此角色不会分配给角色组Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="6bd0a-126">可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6bd0a-127">也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6bd0a-128">有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-servicenow-dataparser-connector"></a><span data-ttu-id="6bd0a-129">步骤 1：设置 ServiceNow DataParser 连接器</span><span class="sxs-lookup"><span data-stu-id="6bd0a-129">Step 1: Set up a ServiceNow DataParser connector</span></span>

<span data-ttu-id="6bd0a-130">第一步是访问数据连接器页，Microsoft 365 合规中心 ServiceNow 数据创建 17a-4 连接器。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for ServiceNow data.</span></span>

1. <span data-ttu-id="6bd0a-131">转到 ， <https://compliance.microsoft.com> 然后单击数据连接器  >  **服务Now DataParser**。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **ServiceNow DataParser**.</span></span>

2. <span data-ttu-id="6bd0a-132">在 **"ServiceNow DataParser** 产品说明"页上，单击"**添加连接器"。**</span><span class="sxs-lookup"><span data-stu-id="6bd0a-132">On the **ServiceNow DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="6bd0a-133">在"**服务条款"页上**，单击"接受 **"。**</span><span class="sxs-lookup"><span data-stu-id="6bd0a-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="6bd0a-134">输入标识连接器的唯一名称，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="6bd0a-135">登录到 17a-4 帐户并完成 ServiceNow DataParser 连接向导中的步骤。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-135">Sign in to your 17a-4 account and complete the steps in the ServiceNow DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-servicenow-dataparser-connector"></a><span data-ttu-id="6bd0a-136">步骤 2：配置 ServiceNow DataParser 连接器</span><span class="sxs-lookup"><span data-stu-id="6bd0a-136">Step 2: Configure the ServiceNow DataParser connector</span></span>

<span data-ttu-id="6bd0a-137">与 17a-4 支持部门一起配置 ServiceNow DataParser 连接器。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-137">Work with 17a-4 Support to configure the ServiceNow DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="6bd0a-138">步骤 3：映射用户</span><span class="sxs-lookup"><span data-stu-id="6bd0a-138">Step 3: Map users</span></span>

<span data-ttu-id="6bd0a-139">ServiceNow DataParser 连接器会自动将用户映射到Microsoft 365电子邮件地址，然后再将数据导入Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-139">The ServiceNow DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-servicenow-dataparser-connector"></a><span data-ttu-id="6bd0a-140">步骤 4：监视 ServiceNow DataParser 连接器</span><span class="sxs-lookup"><span data-stu-id="6bd0a-140">Step 4: Monitor the ServiceNow DataParser connector</span></span>

<span data-ttu-id="6bd0a-141">创建 ServiceNow DataParser 连接器后，可以查看该连接器在 Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-141">After you create a ServiceNow DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="6bd0a-142">转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="6bd0a-143">单击 **"连接器"** 选项卡，然后选择您创建的 ServiceNow DataParser 连接器以显示该飞出页，其中包含有关连接器的属性和信息。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-143">Click the **Connectors** tab and then select the ServiceNow DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="6bd0a-144">在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="6bd0a-145">此日志包含已导入到 Microsoft 云的数据。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6bd0a-146">已知问题</span><span class="sxs-lookup"><span data-stu-id="6bd0a-146">Known issues</span></span>

<span data-ttu-id="6bd0a-147">目前，我们不支持导入大于 10 MB 的附件或项目。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="6bd0a-148">稍后将提供对较大项目的支持。</span><span class="sxs-lookup"><span data-stu-id="6bd0a-148">Support for larger items will be available at a later date.</span></span>
