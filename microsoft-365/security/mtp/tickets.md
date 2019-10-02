---
title: 通过 ServiceNow 创建和跟踪票证
description: Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。 这允许安全管理员将安全得分建议直接发送到 ServiceNow 并创建票证。
keywords: security、Microsoft 365、M365、安全分数、安全中心、ServiceNow、票证、任务
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350324"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="85908-105">通过 ServiceNow 管理票证</span><span class="sxs-lookup"><span data-stu-id="85908-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="85908-106">Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。</span><span class="sxs-lookup"><span data-stu-id="85908-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="85908-107">这使安全管理员能够直接向 ServiceNow 发送[Microsoft Secure 得分](microsoft-secure-score.md)改进操作，并创建一个票证。</span><span class="sxs-lookup"><span data-stu-id="85908-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="85908-108">可以创建事件管理和变更管理票证。</span><span class="sxs-lookup"><span data-stu-id="85908-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85908-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="85908-109">Prerequisites</span></span>

<span data-ttu-id="85908-110">有权访问 Microsoft 365 安全中心和 ServiceNow 实例，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="85908-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="85908-111">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="85908-111">Kingston or higher version</span></span>
* <span data-ttu-id="85908-112">拥有管理员的高凭据</span><span class="sxs-lookup"><span data-stu-id="85908-112">Have admin HI credentials</span></span>
* <span data-ttu-id="85908-113">拥有对目标供应商实例的管理员权限</span><span class="sxs-lookup"><span data-stu-id="85908-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="85908-114">ServiceNow 建议用户在你的 ServiceNow 实例中保留现成设置（默认）。</span><span class="sxs-lookup"><span data-stu-id="85908-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="85908-115">进行自定义可能会导致完成安装清单中的错误并与 Microsoft 365 安全中心集成。</span><span class="sxs-lookup"><span data-stu-id="85908-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="85908-116">数据交换</span><span class="sxs-lookup"><span data-stu-id="85908-116">Data exchange</span></span>

<span data-ttu-id="85908-117">当你将 Microsoft 365 安全中心连接到 ServiceNow 时，Microsoft 将收到以下其他数据：</span><span class="sxs-lookup"><span data-stu-id="85908-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="85908-118">ServiceNow 实例名称</span><span class="sxs-lookup"><span data-stu-id="85908-118">ServiceNow instance name</span></span>
* <span data-ttu-id="85908-119">ServiceNow 客户端 ID</span><span class="sxs-lookup"><span data-stu-id="85908-119">ServiceNow client ID</span></span>
* <span data-ttu-id="85908-120">ServiceNow 客户端密码</span><span class="sxs-lookup"><span data-stu-id="85908-120">ServiceNow client secret</span></span>
* <span data-ttu-id="85908-121">ServiceNow 访问 & 刷新令牌</span><span class="sxs-lookup"><span data-stu-id="85908-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="85908-122">从 Microsoft 365 安全中心创建 ServiceNow 票证时，会将以下数据发送到 ServiceNow：</span><span class="sxs-lookup"><span data-stu-id="85908-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="85908-123">启动创建票证的用户 ID</span><span class="sxs-lookup"><span data-stu-id="85908-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="85908-124">任务名称</span><span class="sxs-lookup"><span data-stu-id="85908-124">Task name</span></span>
* <span data-ttu-id="85908-125">任务说明</span><span class="sxs-lookup"><span data-stu-id="85908-125">Task description</span></span>
* <span data-ttu-id="85908-126">优先级</span><span class="sxs-lookup"><span data-stu-id="85908-126">Priority</span></span>
* <span data-ttu-id="85908-127">截止日期</span><span class="sxs-lookup"><span data-stu-id="85908-127">Due date</span></span>
* <span data-ttu-id="85908-128">建议源（用户建议或 Microsoft 推荐）</span><span class="sxs-lookup"><span data-stu-id="85908-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="85908-129">建议类别（设备、数据、应用、标识、基础结构）</span><span class="sxs-lookup"><span data-stu-id="85908-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="85908-130">将 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="85908-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="85908-131">导航到 Microsoft 365 安全中心主页，你将看到一个卡片，询问你是否使用 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="85908-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![您是否使用 ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="85908-133">在这里，将会发送到 ServiceNow 设置页面，在此页面中，你将按照说明授权 Microsoft 365 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="85908-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="85908-134">在授权 Microsoft 365 安全中心与 ServiceNow 之间的连接时，请确保使用在安装步骤中创建的集成用户登录名和密码，而不是您的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="85908-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="85908-135">按照说明操作并授权连接后，你可以在 Microsoft 365 安全中心连接页和 ServiceNow Microsoft 365 票证发放连接器应用体验中查看连接状态。</span><span class="sxs-lookup"><span data-stu-id="85908-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="85908-136">现在，你已设置为开始创建任务！</span><span class="sxs-lookup"><span data-stu-id="85908-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="85908-137">创建一个任务并将其共享到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="85908-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="85908-138">建立集成后，可以基于特定 Microsoft 安全得分改进操作创建 ServiceNow 任务。</span><span class="sxs-lookup"><span data-stu-id="85908-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="85908-139">转到 Microsoft 365 安全中心门户中安全得分的任何改进措施，并选择 "共享" 图标。</span><span class="sxs-lookup"><span data-stu-id="85908-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="85908-140">其中一个下拉选项是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="85908-140">One of the dropdown options is ServiceNow.</span></span>

![安全分数中的 ServiceNow 共享](../images/servicenow-share.png)

<span data-ttu-id="85908-142">然后，将生成一个任务，您可以在其中设置优先级并编辑名称、说明或截止日期。</span><span class="sxs-lookup"><span data-stu-id="85908-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="85908-143">填写所有必填字段后，即可将该任务发送到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="85908-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="85908-144">该任务将在 ServiceNow 中显示为 Microsoft 365 安全和配置更改请求。</span><span class="sxs-lookup"><span data-stu-id="85908-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="85908-145">跟踪票证</span><span class="sxs-lookup"><span data-stu-id="85908-145">Track tickets</span></span>

<span data-ttu-id="85908-146">一旦创建了 ServiceNow 更改管理和事件管理票证，它们将显示在 Microsoft 365 安全中心主页上的卡片上。</span><span class="sxs-lookup"><span data-stu-id="85908-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="85908-147">通过这些卡，您可以创建一个票证、查看所有票证或管理 ServiceNow 配置。</span><span class="sxs-lookup"><span data-stu-id="85908-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 更改管理票证](../images/change-management-375.png)  ![ServiceNow 事件管理票证](../images/incident-management-375.png)

<span data-ttu-id="85908-150">若要在 Microsoft 365 安全中心中重新设置或管理你的 ServiceNow 集成，请选择任一卡片上的 "**管理 servicenow 配置**"。</span><span class="sxs-lookup"><span data-stu-id="85908-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="85908-151">您可以从中删除当前 ServiceNow 连接并自定义票证状态名称。</span><span class="sxs-lookup"><span data-stu-id="85908-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="85908-152">使用 Microsoft 365 安全中心中显示的 ServiceNow 票证，您的任务将处于活动状态，可在其中跟踪和操作其他安全仪表板项目的位置。</span><span class="sxs-lookup"><span data-stu-id="85908-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="85908-153">常见问题</span><span class="sxs-lookup"><span data-stu-id="85908-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="85908-154">在安装清单的第一步中收到错误（OAuth 创建）</span><span class="sxs-lookup"><span data-stu-id="85908-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="85908-155">**错误消息**：由于表的跨范围访问策略，对作用域 "x_mioms_m365ticket" 中的 "oauth_entity" 执行的读取操作已被拒绝</span><span class="sxs-lookup"><span data-stu-id="85908-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="85908-156">我们的应用程序假定 ServiceNow 实例上的任何管理员都可以创建和读取 OAuth 实体。</span><span class="sxs-lookup"><span data-stu-id="85908-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="85908-157">此错误可能是由于对 ServiceNow 实例的自定义设置造成的，这会限制可创建/读取 OAuth 实体的用户。</span><span class="sxs-lookup"><span data-stu-id="85908-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="85908-158">ServiceNow 建议用户保持 "开箱即用" 功能（默认）。</span><span class="sxs-lookup"><span data-stu-id="85908-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="85908-159">将 "应用程序注册表" 表配置设置为默认值：</span><span class="sxs-lookup"><span data-stu-id="85908-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="85908-160">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="85908-160">Label = Application Registeries</span></span>
* <span data-ttu-id="85908-161">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="85908-161">Name = oauth_entity</span></span>
* <span data-ttu-id="85908-162">可从 = 所有应用程序范围访问</span><span class="sxs-lookup"><span data-stu-id="85908-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="85908-163">可以读取 = 复选框处于选中状态</span><span class="sxs-lookup"><span data-stu-id="85908-163">Can read = check box selected</span></span>

<span data-ttu-id="85908-164">**ServiceNow 建议用户保持 "开箱即用" 功能（默认）。**</span><span class="sxs-lookup"><span data-stu-id="85908-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="85908-165">如何验证为 Microsoft 365 Security & 合规性连接器创建的 OAuth 实体？</span><span class="sxs-lookup"><span data-stu-id="85908-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="85908-166">转到 ServiceNow 中的 "应用程序注册表" 表（菜单 > 系统 OAuth > 应用程序注册表），并查找您创建的 OAuth 实体（您为其分配的名称）。</span><span class="sxs-lookup"><span data-stu-id="85908-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="85908-167">如何验证在 Microsoft 365 Security & 合规性连接器的第2步安装清单中创建的集成用户？</span><span class="sxs-lookup"><span data-stu-id="85908-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="85908-168">转到 ServiceNow 中的 "用户" 表（菜单 > 用户管理 > 用户），并查找您创建的集成用户（您为其分配的名称）。</span><span class="sxs-lookup"><span data-stu-id="85908-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="85908-169">在授权 Microsoft 365 安全中心与 ServiceNow 之间的连接时，请确保使用在安装步骤中创建的集成用户登录名和密码，而不是您的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="85908-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="85908-170">我已完成安装并设置了步骤，但我无法在主页上看到 ServiceNow 卡，也无法在 Microsoft 安全分数中看到共享图标</span><span class="sxs-lookup"><span data-stu-id="85908-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="85908-171">通过转到来https://security.microsoft.com/ticketProvisioning检查设置页面的状态。</span><span class="sxs-lookup"><span data-stu-id="85908-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="85908-172">选择 "**保存**" 并返回到主页。</span><span class="sxs-lookup"><span data-stu-id="85908-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="85908-173">应显示卡片。</span><span class="sxs-lookup"><span data-stu-id="85908-173">The cards should appear.</span></span>
