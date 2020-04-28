---
title: 通过 ServiceNow 创建和跟踪票证
description: Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。 安全管理员可以将安全得分建议直接发送到 ServiceNow 并创建票证。
keywords: security、Microsoft 365、M365、安全分数、安全中心、ServiceNow、票证、任务
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
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
ms.openlocfilehash: eb6af6b11d2d932f3bd2165aa3f597c14feb5ae8
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901018"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="9dd03-105">通过 ServiceNow 管理票证</span><span class="sxs-lookup"><span data-stu-id="9dd03-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="9dd03-106">ServiceNow 是一款受欢迎的云计算平台，可帮助公司管理企业运营的数字工作流。</span><span class="sxs-lookup"><span data-stu-id="9dd03-106">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="9dd03-107">他们的 Now 平台具有 IT 工作流、员工工作流和客户工作流。</span><span class="sxs-lookup"><span data-stu-id="9dd03-107">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="9dd03-108">Microsoft 已与 ServiceNow 合作，使 IT 管理员可以更轻松地管理两个平台中的票证和任务。</span><span class="sxs-lookup"><span data-stu-id="9dd03-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="9dd03-109">了解有关 ServiceNow 的详细信息</span><span class="sxs-lookup"><span data-stu-id="9dd03-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="9dd03-110">Microsoft 365 安全中心现已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。</span><span class="sxs-lookup"><span data-stu-id="9dd03-110">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="9dd03-111">安全管理员可以直接向 ServiceNow 发送[Microsoft Secure 得分](microsoft-secure-score.md)改进操作，并创建一个票证。</span><span class="sxs-lookup"><span data-stu-id="9dd03-111">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="9dd03-112">可以创建事件管理和变更管理票证。</span><span class="sxs-lookup"><span data-stu-id="9dd03-112">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="9dd03-113">然后，可以在 Microsoft 安全中心主页和 ServiceNow 中跟踪它们。</span><span class="sxs-lookup"><span data-stu-id="9dd03-113">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9dd03-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="9dd03-114">Prerequisites</span></span>

<span data-ttu-id="9dd03-115">有权访问 Microsoft 365 安全中心和 ServiceNow 实例，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9dd03-115">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="9dd03-116">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9dd03-116">Kingston or higher version</span></span>
* <span data-ttu-id="9dd03-117">拥有管理员的高凭据</span><span class="sxs-lookup"><span data-stu-id="9dd03-117">Have admin HI credentials</span></span>
* <span data-ttu-id="9dd03-118">拥有对目标供应商实例的管理员权限</span><span class="sxs-lookup"><span data-stu-id="9dd03-118">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="9dd03-119">ServiceNow 建议用户在你的 ServiceNow 实例中保留默认设置。</span><span class="sxs-lookup"><span data-stu-id="9dd03-119">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="9dd03-120">在完成安装清单并与 Microsoft 365 安全中心集成时，具有自定义可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="9dd03-120">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="9dd03-121">数据交换</span><span class="sxs-lookup"><span data-stu-id="9dd03-121">Data exchange</span></span>

<span data-ttu-id="9dd03-122">当您将 Microsoft 365 安全中心连接到 ServiceNow 时，Microsoft 会收到以下附加数据：</span><span class="sxs-lookup"><span data-stu-id="9dd03-122">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="9dd03-123">ServiceNow 实例名称</span><span class="sxs-lookup"><span data-stu-id="9dd03-123">ServiceNow instance name</span></span>
* <span data-ttu-id="9dd03-124">ServiceNow 客户端 ID</span><span class="sxs-lookup"><span data-stu-id="9dd03-124">ServiceNow client ID</span></span>
* <span data-ttu-id="9dd03-125">ServiceNow 客户端密码</span><span class="sxs-lookup"><span data-stu-id="9dd03-125">ServiceNow client secret</span></span>
* <span data-ttu-id="9dd03-126">ServiceNow 访问 & 刷新令牌</span><span class="sxs-lookup"><span data-stu-id="9dd03-126">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="9dd03-127">当您从 Microsoft 365 安全中心创建 ServiceNow 票证时，会将以下数据发送到 ServiceNow：</span><span class="sxs-lookup"><span data-stu-id="9dd03-127">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="9dd03-128">启动创建票证的用户 ID</span><span class="sxs-lookup"><span data-stu-id="9dd03-128">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="9dd03-129">任务名称</span><span class="sxs-lookup"><span data-stu-id="9dd03-129">Task name</span></span>
* <span data-ttu-id="9dd03-130">任务说明</span><span class="sxs-lookup"><span data-stu-id="9dd03-130">Task description</span></span>
* <span data-ttu-id="9dd03-131">优先级</span><span class="sxs-lookup"><span data-stu-id="9dd03-131">Priority</span></span>
* <span data-ttu-id="9dd03-132">截止日期</span><span class="sxs-lookup"><span data-stu-id="9dd03-132">Due date</span></span>
* <span data-ttu-id="9dd03-133">建议源（用户建议或 Microsoft 推荐）</span><span class="sxs-lookup"><span data-stu-id="9dd03-133">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="9dd03-134">建议类别（设备、数据、应用、标识、基础结构）</span><span class="sxs-lookup"><span data-stu-id="9dd03-134">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="9dd03-135">将 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9dd03-135">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="9dd03-136">导航到 Microsoft 365 安全中心主页以查看 ServiceNow 连接卡。</span><span class="sxs-lookup"><span data-stu-id="9dd03-136">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![您是否使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="9dd03-138">选择 "连接到 ServiceNow" 以转到 "ServiceNow 设置" 页。</span><span class="sxs-lookup"><span data-stu-id="9dd03-138">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="9dd03-139">按照说明授权 Microsoft 365 连接器应用。</span><span class="sxs-lookup"><span data-stu-id="9dd03-139">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="9dd03-140">在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="9dd03-140">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="9dd03-141">请勿使用你的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="9dd03-141">Do not use your personal credentials.</span></span>

<span data-ttu-id="9dd03-142">按照说明进行操作并授权连接后，请查看 Microsoft 365 安全中心连接页和 ServiceNow Microsoft 365 票证发放连接器应用程序体验中的连接状态。</span><span class="sxs-lookup"><span data-stu-id="9dd03-142">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="9dd03-143">现在，你已设置为开始创建任务！</span><span class="sxs-lookup"><span data-stu-id="9dd03-143">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="9dd03-144">创建一个任务并将其共享到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9dd03-144">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="9dd03-145">建立集成后，基于特定 Microsoft 安全得分改进操作创建 ServiceNow 任务。</span><span class="sxs-lookup"><span data-stu-id="9dd03-145">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="9dd03-146">转到 Microsoft 365 安全中心门户中安全得分的任何改进措施，并选择 "共享" 图标。</span><span class="sxs-lookup"><span data-stu-id="9dd03-146">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="9dd03-147">其中一个下拉选项是 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9dd03-147">One of the dropdown options is ServiceNow.</span></span>

![安全分数中的 ServiceNow 共享](../../media/servicenow-share.png)

<span data-ttu-id="9dd03-149">将生成一个任务，您可以在其中设置优先级并编辑名称、说明或截止日期。</span><span class="sxs-lookup"><span data-stu-id="9dd03-149">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="9dd03-150">填写所有必填字段后，将该任务发送到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9dd03-150">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="9dd03-151">在 ServiceNow 中，此任务显示为 Microsoft 365 安全性和配置更改请求。</span><span class="sxs-lookup"><span data-stu-id="9dd03-151">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="9dd03-152">跟踪票证</span><span class="sxs-lookup"><span data-stu-id="9dd03-152">Track tickets</span></span>

<span data-ttu-id="9dd03-153">一旦创建了 ServiceNow 更改管理和事件管理票证，它们就会显示在 Microsoft 365 安全中心主页上的卡片上。</span><span class="sxs-lookup"><span data-stu-id="9dd03-153">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="9dd03-154">通过这些卡，您可以创建一个票证、查看所有票证或管理 ServiceNow 配置。</span><span class="sxs-lookup"><span data-stu-id="9dd03-154">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 更改管理票证](../../media/change-management-375.png)  ![ServiceNow 事件管理票证](../../media/incident-management-375.png)

<span data-ttu-id="9dd03-157">若要在 Microsoft 365 安全中心中重新设置或管理你的 ServiceNow 集成，请选择任一卡片上的 "**管理 servicenow 配置**"。</span><span class="sxs-lookup"><span data-stu-id="9dd03-157">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="9dd03-158">在此处，删除当前的 ServiceNow 连接并自定义票证状态名称。</span><span class="sxs-lookup"><span data-stu-id="9dd03-158">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="9dd03-159">借助 Microsoft 365 security center 中显示的 ServiceNow 票证，你的任务可以在某个位置进行跟踪，并在你的其他安全仪表板项目旁边进行操作。</span><span class="sxs-lookup"><span data-stu-id="9dd03-159">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9dd03-160">故障排除</span><span class="sxs-lookup"><span data-stu-id="9dd03-160">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="9dd03-161">您在安装清单（OAuth 创建）的第一步中收到错误</span><span class="sxs-lookup"><span data-stu-id="9dd03-161">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="9dd03-162">**错误消息**：由于表的跨范围访问策略，对作用域 "x_mioms_m365ticket" 中的 "oauth_entity" 执行的读取操作已被拒绝</span><span class="sxs-lookup"><span data-stu-id="9dd03-162">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="9dd03-163">应用程序假定 ServiceNow 实例上的任何管理员都可以创建和读取 OAuth 实体。</span><span class="sxs-lookup"><span data-stu-id="9dd03-163">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="9dd03-164">此错误可能是由于对 ServiceNow 实例的自定义设置造成的，这会限制可创建/读取 OAuth 实体的用户。</span><span class="sxs-lookup"><span data-stu-id="9dd03-164">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="9dd03-165">**ServiceNow 建议用户保留默认功能。**</span><span class="sxs-lookup"><span data-stu-id="9dd03-165">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="9dd03-166">将 "应用程序注册表" 表配置设置为默认值：</span><span class="sxs-lookup"><span data-stu-id="9dd03-166">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="9dd03-167">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="9dd03-167">Label = Application Registeries</span></span>
* <span data-ttu-id="9dd03-168">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="9dd03-168">Name = oauth_entity</span></span>
* <span data-ttu-id="9dd03-169">可从 = 所有应用程序范围访问</span><span class="sxs-lookup"><span data-stu-id="9dd03-169">Accessible from = All application scopes</span></span>
* <span data-ttu-id="9dd03-170">可以读取 = 复选框处于选中状态</span><span class="sxs-lookup"><span data-stu-id="9dd03-170">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="9dd03-171">如何验证为 Microsoft 365 安全 & 合规性连接器创建的 OAuth 实体</span><span class="sxs-lookup"><span data-stu-id="9dd03-171">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="9dd03-172">转到 ServiceNow 中的 "应用程序注册表" 表（**菜单 > 系统 OAuth > 应用程序注册表**），并使用您为其分配的名称查找您创建的 OAuth 实体。</span><span class="sxs-lookup"><span data-stu-id="9dd03-172">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="9dd03-173">作为集成用户登录</span><span class="sxs-lookup"><span data-stu-id="9dd03-173">Logging in as the integration user</span></span>

<span data-ttu-id="9dd03-174">在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="9dd03-174">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="9dd03-175">请勿使用你的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="9dd03-175">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="9dd03-176">转到 ServiceNow 中的 "授权" 页面。</span><span class="sxs-lookup"><span data-stu-id="9dd03-176">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="9dd03-177">如果使用个人凭据登录，请选择右上角的 "**不**链接"。</span><span class="sxs-lookup"><span data-stu-id="9dd03-177">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="9dd03-178">以您以前从安装清单创建的集成用户的形式登录到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9dd03-178">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="9dd03-179">在 ServiceNow 页面中选择 "**允许**"，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。</span><span class="sxs-lookup"><span data-stu-id="9dd03-179">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="9dd03-180">继续执行设置步骤。</span><span class="sxs-lookup"><span data-stu-id="9dd03-180">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="9dd03-181">如何验证在安装清单中创建的集成用户是否符合 Microsoft 365 安全 & 合规性连接器</span><span class="sxs-lookup"><span data-stu-id="9dd03-181">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="9dd03-182">转到 ServiceNow 中的 "用户" 表 **（菜单 > 用户管理 > 用户**），并使用您为其分配的名称查找您创建的集成用户。</span><span class="sxs-lookup"><span data-stu-id="9dd03-182">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="9dd03-183">你的公司启用了单一登录，这将阻止你通过 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9dd03-183">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="9dd03-184">如果贵公司已启用单一登录，但您收到错误或登录失败，请按照这两个解决方案之一。</span><span class="sxs-lookup"><span data-stu-id="9dd03-184">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="9dd03-185">以集成用户的形式登录到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9dd03-185">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="9dd03-186">导航回 ServiceNow 中的 "授权" 页面。</span><span class="sxs-lookup"><span data-stu-id="9dd03-186">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="9dd03-187">选择右上角的 "**不向您**链接"。</span><span class="sxs-lookup"><span data-stu-id="9dd03-187">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="9dd03-188">以您以前从安装清单创建的集成用户的形式登录到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9dd03-188">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="9dd03-189">在 ServiceNow 页面中选择 "**允许**"，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。</span><span class="sxs-lookup"><span data-stu-id="9dd03-189">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="9dd03-190">继续执行设置步骤。</span><span class="sxs-lookup"><span data-stu-id="9dd03-190">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="9dd03-191">创建安全管理员用户</span><span class="sxs-lookup"><span data-stu-id="9dd03-191">Create a security admin user</span></span>

1. <span data-ttu-id="9dd03-192">在 Azure Active Directory 中创建具有安全管理员权限的用户。</span><span class="sxs-lookup"><span data-stu-id="9dd03-192">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="9dd03-193">用户需要与您在安装清单中创建的集成用户具有相同的名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9dd03-193">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="9dd03-194">登录和连接完成后，可以删除安全管理员角色。</span><span class="sxs-lookup"><span data-stu-id="9dd03-194">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="9dd03-195">作为此用户登录到 Microsoft 365 安全中心，并按照安装步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="9dd03-195">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="9dd03-196">IP 筛选</span><span class="sxs-lookup"><span data-stu-id="9dd03-196">IP filtering</span></span>

<span data-ttu-id="9dd03-197">如果已启用 IP 筛选，则可能需要显式允许 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9dd03-197">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="9dd03-198">有关如何允许 ServiceNow 中的 IP 范围的信息，请参阅[IP 地址访问控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html)。</span><span class="sxs-lookup"><span data-stu-id="9dd03-198">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="9dd03-199">有关允许的 IP 地址列表，请参阅[AZURE IP 范围和服务标记-公共云](https://www.microsoft.com/en-us/download/details.aspx?id=56519)。</span><span class="sxs-lookup"><span data-stu-id="9dd03-199">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="9dd03-200">安装已完成，但看不到票证且无法共享</span><span class="sxs-lookup"><span data-stu-id="9dd03-200">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="9dd03-201">如果已完成安装和设置步骤，但您在主页上看不到 ServiceNow 卡，并且无法从 Microsoft 安全分数中共享到 ServiceNow，请在处https://security.microsoft.com/ticketProvisioning检查设置页面的状态。</span><span class="sxs-lookup"><span data-stu-id="9dd03-201">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="9dd03-202">选择 "**授权**" 并返回到主页。</span><span class="sxs-lookup"><span data-stu-id="9dd03-202">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="9dd03-203">应显示卡片。</span><span class="sxs-lookup"><span data-stu-id="9dd03-203">The cards should appear.</span></span>

