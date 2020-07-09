---
title: 将 ServiceNow 票证集成到 Microsoft 365 安全中心和合规性中心
description: 了解如何从 Microsoft 365 安全中心和合规中心在 ServiceNow 中创建和跟踪票证。
keywords: security、Microsoft 365、M365、合规性、合规性中心、安全中心、ServiceNow、票证、任务、雪、connection
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086663"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="9bbe8-104">将 ServiceNow 票证集成到 Microsoft 365 安全中心和合规性中心</span><span class="sxs-lookup"><span data-stu-id="9bbe8-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="9bbe8-105">ServiceNow 是一款受欢迎的云计算平台，可帮助公司管理企业运营的数字工作流。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="9bbe8-106">他们的 Now 平台具有 IT 工作流、员工工作流和客户工作流。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="9bbe8-107">了解有关 ServiceNow 的详细信息</span><span class="sxs-lookup"><span data-stu-id="9bbe8-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="9bbe8-108">Microsoft 已与 ServiceNow 合作，使 IT 管理员可以更轻松地管理两个平台中的票证和任务。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="9bbe8-109">[Microsoft 365 安全中心](overview-security-center.md)和[microsoft 365 合规性中心](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center)已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="9bbe8-110">**在安全中心中管理 ServiceNow 票证**</span><span class="sxs-lookup"><span data-stu-id="9bbe8-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="9bbe8-111">**在合规中心中管理 ServiceNow 票证**（即将推出）</span><span class="sxs-lookup"><span data-stu-id="9bbe8-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bbe8-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="9bbe8-112">Prerequisites</span></span>

<span data-ttu-id="9bbe8-113">有权访问 Microsoft 365 安全中心或合规性中心和包含以下内容的 ServiceNow 实例：</span><span class="sxs-lookup"><span data-stu-id="9bbe8-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="9bbe8-114">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9bbe8-114">Kingston or higher version</span></span>
* <span data-ttu-id="9bbe8-115">拥有管理员的高凭据</span><span class="sxs-lookup"><span data-stu-id="9bbe8-115">Have admin HI credentials</span></span>
* <span data-ttu-id="9bbe8-116">拥有对目标供应商实例的管理员权限</span><span class="sxs-lookup"><span data-stu-id="9bbe8-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="9bbe8-117">ServiceNow 建议用户在你的 ServiceNow 实例中保留默认设置。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="9bbe8-118">在完成安装清单并与 Microsoft 365 安全中心集成时，具有自定义可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="9bbe8-119">数据交换</span><span class="sxs-lookup"><span data-stu-id="9bbe8-119">Data exchange</span></span>

<span data-ttu-id="9bbe8-120">当您将 Microsoft 365 安全中心或合规中心连接到 ServiceNow 时，Microsoft 会收到以下附加数据：</span><span class="sxs-lookup"><span data-stu-id="9bbe8-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="9bbe8-121">ServiceNow 实例名称</span><span class="sxs-lookup"><span data-stu-id="9bbe8-121">ServiceNow instance name</span></span>
* <span data-ttu-id="9bbe8-122">ServiceNow 客户端 ID</span><span class="sxs-lookup"><span data-stu-id="9bbe8-122">ServiceNow client ID</span></span>
* <span data-ttu-id="9bbe8-123">ServiceNow 客户端密码</span><span class="sxs-lookup"><span data-stu-id="9bbe8-123">ServiceNow client secret</span></span>
* <span data-ttu-id="9bbe8-124">ServiceNow 访问 & 刷新令牌</span><span class="sxs-lookup"><span data-stu-id="9bbe8-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="9bbe8-125">当您从 Microsoft 365 安全中心或合规中心创建 ServiceNow 票证时，会将以下数据发送到 ServiceNow：</span><span class="sxs-lookup"><span data-stu-id="9bbe8-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="9bbe8-126">启动创建票证的用户 ID</span><span class="sxs-lookup"><span data-stu-id="9bbe8-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="9bbe8-127">任务名称</span><span class="sxs-lookup"><span data-stu-id="9bbe8-127">Task name</span></span>
* <span data-ttu-id="9bbe8-128">任务说明</span><span class="sxs-lookup"><span data-stu-id="9bbe8-128">Task description</span></span>
* <span data-ttu-id="9bbe8-129">Priority</span><span class="sxs-lookup"><span data-stu-id="9bbe8-129">Priority</span></span>
* <span data-ttu-id="9bbe8-130">截止日期</span><span class="sxs-lookup"><span data-stu-id="9bbe8-130">Due date</span></span>
* <span data-ttu-id="9bbe8-131">建议源（用户建议或 Microsoft 推荐）</span><span class="sxs-lookup"><span data-stu-id="9bbe8-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="9bbe8-132">建议类别（设备、数据、应用、标识、基础结构）</span><span class="sxs-lookup"><span data-stu-id="9bbe8-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="9bbe8-133">连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9bbe8-133">Connect to ServiceNow</span></span>

<span data-ttu-id="9bbe8-134">请转到[Microsoft 365 安全中心中的创建和跟踪 ServiceNow 票证](tickets-security-center.md)，了解如何连接到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="9bbe8-135">即将推出从 Microsoft 365 合规中心进行连接。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9bbe8-136">疑难解答</span><span class="sxs-lookup"><span data-stu-id="9bbe8-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="9bbe8-137">您在安装清单（OAuth 创建）的第一步中收到错误</span><span class="sxs-lookup"><span data-stu-id="9bbe8-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="9bbe8-138">**错误消息**：由于表的跨范围访问策略，对作用域 "x_mioms_m365ticket" 中的 "oauth_entity" 执行的读取操作已被拒绝</span><span class="sxs-lookup"><span data-stu-id="9bbe8-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="9bbe8-139">应用程序假定 ServiceNow 实例上的任何管理员都可以创建和读取 OAuth 实体。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="9bbe8-140">此错误可能是由于对 ServiceNow 实例的自定义设置造成的，这会限制可创建/读取 OAuth 实体的用户。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="9bbe8-141">**ServiceNow 建议用户保留默认功能。**</span><span class="sxs-lookup"><span data-stu-id="9bbe8-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="9bbe8-142">将 "应用程序注册表" 表配置设置为默认值：</span><span class="sxs-lookup"><span data-stu-id="9bbe8-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="9bbe8-143">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="9bbe8-143">Label = Application Registeries</span></span>
* <span data-ttu-id="9bbe8-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="9bbe8-144">Name = oauth_entity</span></span>
* <span data-ttu-id="9bbe8-145">可从 = 所有应用程序范围访问</span><span class="sxs-lookup"><span data-stu-id="9bbe8-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="9bbe8-146">可以读取 = 复选框处于选中状态</span><span class="sxs-lookup"><span data-stu-id="9bbe8-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="9bbe8-147">如何验证为 Microsoft 365 安全 & 合规性连接器创建的 OAuth 实体</span><span class="sxs-lookup"><span data-stu-id="9bbe8-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="9bbe8-148">转到 ServiceNow 中的 "应用程序注册表" 表（**菜单 > 系统 OAuth > 应用程序注册表**），并使用您为其分配的名称查找您创建的 OAuth 实体。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="9bbe8-149">作为集成用户登录</span><span class="sxs-lookup"><span data-stu-id="9bbe8-149">Logging in as the integration user</span></span>

<span data-ttu-id="9bbe8-150">在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="9bbe8-151">请勿使用你的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="9bbe8-152">转到 ServiceNow 中的 "授权" 页面。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="9bbe8-153">如果使用个人凭据登录，请选择右上角的 "**不**链接"。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="9bbe8-154">以您以前从安装清单创建的集成用户的形式登录到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="9bbe8-155">在 ServiceNow 页面中选择 "**允许**"，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="9bbe8-156">继续执行设置步骤。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="9bbe8-157">如何验证在安装清单中创建的集成用户是否符合 Microsoft 365 安全 & 合规性连接器</span><span class="sxs-lookup"><span data-stu-id="9bbe8-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="9bbe8-158">转到 ServiceNow 中的 "用户" 表 **（菜单 > 用户管理 > 用户**），并使用您为其分配的名称查找您创建的集成用户。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="9bbe8-159">你的公司启用了单一登录，这将阻止你通过 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9bbe8-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="9bbe8-160">如果贵公司已启用单一登录，但您收到错误或登录失败，请按照这两个解决方案之一。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="9bbe8-161">以集成用户的形式登录到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="9bbe8-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="9bbe8-162">导航回 ServiceNow 中的 "授权" 页面。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="9bbe8-163">选择右上角的 "**不向您**链接"。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="9bbe8-164">以您以前从安装清单创建的集成用户的形式登录到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="9bbe8-165">在 ServiceNow 页面中选择 "**允许**"，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="9bbe8-166">继续执行设置步骤。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="9bbe8-167">创建安全管理员用户</span><span class="sxs-lookup"><span data-stu-id="9bbe8-167">Create a security admin user</span></span>

1. <span data-ttu-id="9bbe8-168">在 Azure Active Directory 中创建具有安全管理员权限的用户。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="9bbe8-169">用户需要与您在安装清单中创建的集成用户具有相同的名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="9bbe8-170">登录和连接完成后，可以删除安全管理员角色。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="9bbe8-171">作为此用户登录到 Microsoft 365 安全中心，并按照安装步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="9bbe8-172">IP 筛选</span><span class="sxs-lookup"><span data-stu-id="9bbe8-172">IP filtering</span></span>

<span data-ttu-id="9bbe8-173">如果已启用 IP 筛选，则可能需要显式允许 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="9bbe8-174">有关如何允许 ServiceNow 中的 IP 范围的信息，请参阅[IP 地址访问控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html)。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="9bbe8-175">有关允许的 IP 地址列表，请参阅[AZURE IP 范围和服务标记-公共云](https://www.microsoft.com/en-us/download/details.aspx?id=56519)。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="9bbe8-176">安装已完成，但看不到票证且无法共享</span><span class="sxs-lookup"><span data-stu-id="9bbe8-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="9bbe8-177">如果已完成安装和设置步骤，但您在主页上看不到 ServiceNow 卡，并且无法从 Microsoft 安全分数中共享到 ServiceNow，请在处检查设置页面的状态 https://security.microsoft.com/ticketProvisioning 。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="9bbe8-178">选择 "**授权**" 并返回到主页。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="9bbe8-179">应显示卡片。</span><span class="sxs-lookup"><span data-stu-id="9bbe8-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="9bbe8-180">资源</span><span class="sxs-lookup"><span data-stu-id="9bbe8-180">Resources</span></span>

- [<span data-ttu-id="9bbe8-181">在安全中心中管理 ServiceNow 票证</span><span class="sxs-lookup"><span data-stu-id="9bbe8-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)