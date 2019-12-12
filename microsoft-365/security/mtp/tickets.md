---
title: 通过 ServiceNow 创建和跟踪票证
description: Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。 安全管理员可以将安全得分建议直接发送到 ServiceNow 并创建票证。
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
ms.openlocfilehash: e67ff2b28a6dec741b2ad7af5179dca226fb86ad
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962569"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="cc2c5-105">通过 ServiceNow 管理票证</span><span class="sxs-lookup"><span data-stu-id="cc2c5-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="cc2c5-106">Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="cc2c5-107">安全管理员可以直接向 ServiceNow 发送[Microsoft Secure 得分](microsoft-secure-score.md)改进操作，并创建一个票证。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="cc2c5-108">可以创建事件管理和变更管理票证。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc2c5-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="cc2c5-109">Prerequisites</span></span>

<span data-ttu-id="cc2c5-110">有权访问 Microsoft 365 安全中心和 ServiceNow 实例，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc2c5-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="cc2c5-111">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cc2c5-111">Kingston or higher version</span></span>
* <span data-ttu-id="cc2c5-112">拥有管理员的高凭据</span><span class="sxs-lookup"><span data-stu-id="cc2c5-112">Have admin HI credentials</span></span>
* <span data-ttu-id="cc2c5-113">拥有对目标供应商实例的管理员权限</span><span class="sxs-lookup"><span data-stu-id="cc2c5-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="cc2c5-114">ServiceNow 建议用户在你的 ServiceNow 实例中保留默认设置。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="cc2c5-115">在完成安装清单并与 Microsoft 365 安全中心集成时，具有自定义可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="cc2c5-116">数据交换</span><span class="sxs-lookup"><span data-stu-id="cc2c5-116">Data exchange</span></span>

<span data-ttu-id="cc2c5-117">当您将 Microsoft 365 安全中心连接到 ServiceNow 时，Microsoft 会收到以下附加数据：</span><span class="sxs-lookup"><span data-stu-id="cc2c5-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="cc2c5-118">ServiceNow 实例名称</span><span class="sxs-lookup"><span data-stu-id="cc2c5-118">ServiceNow instance name</span></span>
* <span data-ttu-id="cc2c5-119">ServiceNow 客户端 ID</span><span class="sxs-lookup"><span data-stu-id="cc2c5-119">ServiceNow client ID</span></span>
* <span data-ttu-id="cc2c5-120">ServiceNow 客户端密码</span><span class="sxs-lookup"><span data-stu-id="cc2c5-120">ServiceNow client secret</span></span>
* <span data-ttu-id="cc2c5-121">ServiceNow 访问 & 刷新令牌</span><span class="sxs-lookup"><span data-stu-id="cc2c5-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="cc2c5-122">当您从 Microsoft 365 安全中心创建 ServiceNow 票证时，会将以下数据发送到 ServiceNow：</span><span class="sxs-lookup"><span data-stu-id="cc2c5-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="cc2c5-123">启动创建票证的用户 ID</span><span class="sxs-lookup"><span data-stu-id="cc2c5-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="cc2c5-124">任务名称</span><span class="sxs-lookup"><span data-stu-id="cc2c5-124">Task name</span></span>
* <span data-ttu-id="cc2c5-125">任务说明</span><span class="sxs-lookup"><span data-stu-id="cc2c5-125">Task description</span></span>
* <span data-ttu-id="cc2c5-126">优先级</span><span class="sxs-lookup"><span data-stu-id="cc2c5-126">Priority</span></span>
* <span data-ttu-id="cc2c5-127">截止日期</span><span class="sxs-lookup"><span data-stu-id="cc2c5-127">Due date</span></span>
* <span data-ttu-id="cc2c5-128">建议源（用户建议或 Microsoft 推荐）</span><span class="sxs-lookup"><span data-stu-id="cc2c5-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="cc2c5-129">建议类别（设备、数据、应用、标识、基础结构）</span><span class="sxs-lookup"><span data-stu-id="cc2c5-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="cc2c5-130">将 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="cc2c5-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="cc2c5-131">导航到 Microsoft 365 安全中心主页以查看 ServiceNow 连接卡。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![您是否使用 ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="cc2c5-133">选择 "连接到 ServiceNow" 以转到 "ServiceNow 设置" 页。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="cc2c5-134">按照说明授权 Microsoft 365 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="cc2c5-135">在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="cc2c5-136">请勿使用你的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="cc2c5-137">按照说明进行操作并授权连接后，请查看 Microsoft 365 安全中心连接页和 ServiceNow Microsoft 365 票证发放连接器应用程序体验中的连接状态。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="cc2c5-138">现在，你已设置为开始创建任务！</span><span class="sxs-lookup"><span data-stu-id="cc2c5-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="cc2c5-139">创建一个任务并将其共享到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="cc2c5-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="cc2c5-140">建立集成后，基于特定 Microsoft 安全得分改进操作创建 ServiceNow 任务。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="cc2c5-141">转到 Microsoft 365 安全中心门户中安全得分的任何改进措施，并选择 "共享" 图标。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="cc2c5-142">其中一个下拉选项是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-142">One of the dropdown options is ServiceNow.</span></span>

![安全分数中的 ServiceNow 共享](../images/servicenow-share.png)

<span data-ttu-id="cc2c5-144">将生成一个任务，您可以在其中设置优先级并编辑名称、说明或截止日期。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="cc2c5-145">填写所有必填字段后，将该任务发送到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="cc2c5-146">在 ServiceNow 中，此任务显示为 Microsoft 365 安全性和配置更改请求。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="cc2c5-147">跟踪票证</span><span class="sxs-lookup"><span data-stu-id="cc2c5-147">Track tickets</span></span>

<span data-ttu-id="cc2c5-148">一旦创建了 ServiceNow 更改管理和事件管理票证，它们就会显示在 Microsoft 365 安全中心主页上的卡片上。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="cc2c5-149">通过这些卡，您可以创建一个票证、查看所有票证或管理 ServiceNow 配置。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 更改管理票证](../images/change-management-375.png)  ![ServiceNow 事件管理票证](../images/incident-management-375.png)

<span data-ttu-id="cc2c5-152">若要在 Microsoft 365 安全中心中重新设置或管理你的 ServiceNow 集成，请选择任一卡片上的 "**管理 servicenow 配置**"。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="cc2c5-153">在此处，删除当前的 ServiceNow 连接并自定义票证状态名称。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="cc2c5-154">借助 Microsoft 365 security center 中显示的 ServiceNow 票证，你的任务可以在某个位置进行跟踪，并在你的其他安全仪表板项目旁边进行操作。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="cc2c5-155">故障排除</span><span class="sxs-lookup"><span data-stu-id="cc2c5-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="cc2c5-156">您在安装清单（OAuth 创建）的第一步中收到错误</span><span class="sxs-lookup"><span data-stu-id="cc2c5-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="cc2c5-157">**错误消息**：由于表的跨范围访问策略，对作用域 "x_mioms_m365ticket" 中的 "oauth_entity" 执行的读取操作已被拒绝</span><span class="sxs-lookup"><span data-stu-id="cc2c5-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="cc2c5-158">应用程序假定 ServiceNow 实例上的任何管理员都可以创建和读取 OAuth 实体。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="cc2c5-159">此错误可能是由于对 ServiceNow 实例的自定义设置造成的，这会限制可创建/读取 OAuth 实体的用户。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="cc2c5-160">**ServiceNow 建议用户保留默认功能。**</span><span class="sxs-lookup"><span data-stu-id="cc2c5-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="cc2c5-161">将 "应用程序注册表" 表配置设置为默认值：</span><span class="sxs-lookup"><span data-stu-id="cc2c5-161">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="cc2c5-162">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="cc2c5-162">Label = Application Registeries</span></span>
* <span data-ttu-id="cc2c5-163">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="cc2c5-163">Name = oauth_entity</span></span>
* <span data-ttu-id="cc2c5-164">可从 = 所有应用程序范围访问</span><span class="sxs-lookup"><span data-stu-id="cc2c5-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="cc2c5-165">可以读取 = 复选框处于选中状态</span><span class="sxs-lookup"><span data-stu-id="cc2c5-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="cc2c5-166">如何验证为 Microsoft 365 安全 & 合规性连接器创建的 OAuth 实体</span><span class="sxs-lookup"><span data-stu-id="cc2c5-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="cc2c5-167">转到 ServiceNow 中的 "应用程序注册表" 表（菜单 > 系统 OAuth > 应用程序注册表），并查找您创建的 OAuth 实体（您为其分配的名称）。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-167">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="cc2c5-168">如何验证在安装清单中创建的集成用户是否符合 Microsoft 365 安全 & 合规性连接器</span><span class="sxs-lookup"><span data-stu-id="cc2c5-168">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="cc2c5-169">转到 ServiceNow 中的 "用户" 表（菜单 > 用户管理 > 用户），并查找您创建的集成用户（您为其分配的名称）。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-169">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="cc2c5-170">在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-170">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="cc2c5-171">请勿使用你的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-171">Do not use your personal credentials.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="cc2c5-172">安装已完成，但看不到票证且无法共享</span><span class="sxs-lookup"><span data-stu-id="cc2c5-172">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="cc2c5-173">如果已完成安装和设置步骤，但您在主页上看不到 ServiceNow 卡，并且无法从 Microsoft 安全分数中共享到 ServiceNow，请在处https://security.microsoft.com/ticketProvisioning检查设置页面的状态。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-173">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="cc2c5-174">选择 "**保存**" 并返回到主页。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-174">Select **Save** and return to the home page.</span></span> <span data-ttu-id="cc2c5-175">应显示卡片。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-175">The cards should appear.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="cc2c5-176">你的公司启用了单一登录，这将阻止你通过 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="cc2c5-176">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="cc2c5-177">如果贵公司已启用单一登录，但您收到错误或登录失败，请按照这两个解决方案之一。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-177">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="logging-into-servicenow-as-the-integration-user"></a><span data-ttu-id="cc2c5-178">以集成用户的形式登录到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="cc2c5-178">Logging into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="cc2c5-179">导航回 ServiceNow 中的 "授权" 页面。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-179">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="cc2c5-180">选择右上角的 "**不向您**链接"。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-180">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="cc2c5-181">以您以前从安装清单创建的集成用户的形式登录到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-181">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="cc2c5-182">在 ServiceNow 页面中选择 "**允许**"，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-182">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="cc2c5-183">继续执行设置步骤。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-183">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="cc2c5-184">创建安全管理员用户</span><span class="sxs-lookup"><span data-stu-id="cc2c5-184">Create a security admin user</span></span>

1. <span data-ttu-id="cc2c5-185">在 Azure Active Directory 中创建具有安全管理员权限的用户。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-185">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="cc2c5-186">用户需要与您在安装清单中创建的集成用户具有相同的名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-186">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="cc2c5-187">登录和连接完成后，可以删除安全管理员角色。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-187">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="cc2c5-188">作为此用户登录到 Microsoft 365 安全中心，并按照安装步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="cc2c5-188">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>
