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
ms.openlocfilehash: b9e900baf02e9fc866fe6fe520ad1e40ccd565de
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950696"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="afc91-104">将 ServiceNow 票证集成到 Microsoft 365 安全中心和合规性中心</span><span class="sxs-lookup"><span data-stu-id="afc91-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="afc91-105">ServiceNow 是一款受欢迎的云计算平台，可帮助公司管理企业运营的数字工作流。</span><span class="sxs-lookup"><span data-stu-id="afc91-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="afc91-106">他们的 Now 平台具有 IT 工作流、员工工作流和客户工作流。</span><span class="sxs-lookup"><span data-stu-id="afc91-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="afc91-107">了解有关 ServiceNow 的详细信息</span><span class="sxs-lookup"><span data-stu-id="afc91-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="afc91-108">Microsoft 已与 ServiceNow 合作，使 IT 管理员可以更轻松地管理两个平台中的票证和任务。</span><span class="sxs-lookup"><span data-stu-id="afc91-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="afc91-109">[Microsoft 365 安全中心](overview-security-center.md) 和 [microsoft 365 合规性中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。</span><span class="sxs-lookup"><span data-stu-id="afc91-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="afc91-110">**在安全中心中管理 ServiceNow 票证**</span><span class="sxs-lookup"><span data-stu-id="afc91-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="afc91-111">**在合规中心中管理 ServiceNow 票证** (即将推出) </span><span class="sxs-lookup"><span data-stu-id="afc91-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="afc91-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="afc91-112">Prerequisites</span></span>

<span data-ttu-id="afc91-113">有权访问 Microsoft 365 安全中心或合规性中心和包含以下内容的 ServiceNow 实例：</span><span class="sxs-lookup"><span data-stu-id="afc91-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="afc91-114">Kingston 或更高版本</span><span class="sxs-lookup"><span data-stu-id="afc91-114">Kingston or higher version</span></span>
* <span data-ttu-id="afc91-115">拥有管理员的高凭据</span><span class="sxs-lookup"><span data-stu-id="afc91-115">Have admin HI credentials</span></span>
* <span data-ttu-id="afc91-116">拥有对目标供应商实例的管理员权限</span><span class="sxs-lookup"><span data-stu-id="afc91-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="afc91-117">ServiceNow 建议用户在你的 ServiceNow 实例中保留默认设置。</span><span class="sxs-lookup"><span data-stu-id="afc91-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="afc91-118">在完成安装清单并与 Microsoft 365 安全中心集成时，具有自定义可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="afc91-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="afc91-119">数据交换</span><span class="sxs-lookup"><span data-stu-id="afc91-119">Data exchange</span></span>

<span data-ttu-id="afc91-120">当您将 Microsoft 365 安全中心或合规中心连接到 ServiceNow 时，Microsoft 会收到以下附加数据：</span><span class="sxs-lookup"><span data-stu-id="afc91-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="afc91-121">ServiceNow 实例名称</span><span class="sxs-lookup"><span data-stu-id="afc91-121">ServiceNow instance name</span></span>
* <span data-ttu-id="afc91-122">ServiceNow 客户端 ID</span><span class="sxs-lookup"><span data-stu-id="afc91-122">ServiceNow client ID</span></span>
* <span data-ttu-id="afc91-123">ServiceNow 客户端密码</span><span class="sxs-lookup"><span data-stu-id="afc91-123">ServiceNow client secret</span></span>
* <span data-ttu-id="afc91-124">ServiceNow 访问 & 刷新令牌</span><span class="sxs-lookup"><span data-stu-id="afc91-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="afc91-125">当您从 Microsoft 365 安全中心或合规中心创建 ServiceNow 票证时，会将以下数据发送到 ServiceNow：</span><span class="sxs-lookup"><span data-stu-id="afc91-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="afc91-126">启动创建票证的用户 ID</span><span class="sxs-lookup"><span data-stu-id="afc91-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="afc91-127">任务名称</span><span class="sxs-lookup"><span data-stu-id="afc91-127">Task name</span></span>
* <span data-ttu-id="afc91-128">任务说明</span><span class="sxs-lookup"><span data-stu-id="afc91-128">Task description</span></span>
* <span data-ttu-id="afc91-129">Priority</span><span class="sxs-lookup"><span data-stu-id="afc91-129">Priority</span></span>
* <span data-ttu-id="afc91-130">截止日期</span><span class="sxs-lookup"><span data-stu-id="afc91-130">Due date</span></span>
* <span data-ttu-id="afc91-131">建议源 (用户建议或 Microsoft 建议) </span><span class="sxs-lookup"><span data-stu-id="afc91-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="afc91-132"> (设备、数据、应用程序、标识、基础结构) 的建议类别</span><span class="sxs-lookup"><span data-stu-id="afc91-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="afc91-133">连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="afc91-133">Connect to ServiceNow</span></span>

<span data-ttu-id="afc91-134">请转到 [Microsoft 365 安全中心中的创建和跟踪 ServiceNow 票证](tickets-security-center.md) ，了解如何连接到 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="afc91-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="afc91-135">即将推出从 Microsoft 365 合规中心进行连接。</span><span class="sxs-lookup"><span data-stu-id="afc91-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="afc91-136">故障排除</span><span class="sxs-lookup"><span data-stu-id="afc91-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="afc91-137">您将在安装清单 (OAuth 创建的第一步中收到错误) </span><span class="sxs-lookup"><span data-stu-id="afc91-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="afc91-138">**错误消息**：由于表的跨范围访问策略，对作用域 "x_mioms_m365ticket" 中的 "oauth_entity" 执行的读取操作已被拒绝</span><span class="sxs-lookup"><span data-stu-id="afc91-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="afc91-139">应用程序假定 ServiceNow 实例上的任何管理员都可以创建和读取 OAuth 实体。</span><span class="sxs-lookup"><span data-stu-id="afc91-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="afc91-140">此错误可能是由您的 ServiceNow 实例中的自定义项导致的，用于限制可创建或读取 OAuth 实体的用户。</span><span class="sxs-lookup"><span data-stu-id="afc91-140">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="afc91-141">**ServiceNow 建议用户保留默认功能。**</span><span class="sxs-lookup"><span data-stu-id="afc91-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="afc91-142">将 "应用程序注册表" 表配置设置为默认值：</span><span class="sxs-lookup"><span data-stu-id="afc91-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="afc91-143">Label = Application Registeries</span><span class="sxs-lookup"><span data-stu-id="afc91-143">Label = Application Registeries</span></span>
* <span data-ttu-id="afc91-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="afc91-144">Name = oauth_entity</span></span>
* <span data-ttu-id="afc91-145">可从 = 所有应用程序范围访问</span><span class="sxs-lookup"><span data-stu-id="afc91-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="afc91-146">可以读取 = 复选框处于选中状态</span><span class="sxs-lookup"><span data-stu-id="afc91-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="afc91-147">如何验证为 Microsoft 365 安全 & 合规性连接器创建的 OAuth 实体</span><span class="sxs-lookup"><span data-stu-id="afc91-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="afc91-148">转到 "应用程序注册表" 表 (**Menu > 系统 OAuth > 应用程序注册表**) 在 ServiceNow 中。</span><span class="sxs-lookup"><span data-stu-id="afc91-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow.</span></span> <span data-ttu-id="afc91-149">使用您为其分配的名称查找您创建的 OAuth 实体。</span><span class="sxs-lookup"><span data-stu-id="afc91-149">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="afc91-150">以集成用户的登录</span><span class="sxs-lookup"><span data-stu-id="afc91-150">Signing in as the integration user</span></span>

<span data-ttu-id="afc91-151">在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用在安装步骤中创建的集成用户登录和密码。</span><span class="sxs-lookup"><span data-stu-id="afc91-151">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="afc91-152">请勿使用你的个人凭据。</span><span class="sxs-lookup"><span data-stu-id="afc91-152">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="afc91-153">转到 ServiceNow 中的 "授权" 页面。</span><span class="sxs-lookup"><span data-stu-id="afc91-153">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="afc91-154">如果你使用个人凭据登录，请选择右上角的 " **不** 链接"。</span><span class="sxs-lookup"><span data-stu-id="afc91-154">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="afc91-155">登录到 ServiceNow，将其作为您以前从安装清单创建的集成用户。</span><span class="sxs-lookup"><span data-stu-id="afc91-155">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="afc91-156">在 ServiceNow 页面中选择 " **允许** "，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。</span><span class="sxs-lookup"><span data-stu-id="afc91-156">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="afc91-157">继续执行安装步骤。</span><span class="sxs-lookup"><span data-stu-id="afc91-157">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="afc91-158">如何验证在安装清单中创建的集成用户是否符合 Microsoft 365 安全 & 合规性连接器</span><span class="sxs-lookup"><span data-stu-id="afc91-158">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="afc91-159">转到 "用户" 表 \*\* (菜单中 > 用户管理 > 用户\*\*) 在 ServiceNow 中，并使用您为其分配的名称查找您创建的集成用户。</span><span class="sxs-lookup"><span data-stu-id="afc91-159">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="afc91-160">你的公司启用了单一登录，这将阻止你通过 Microsoft 365 安全中心连接到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="afc91-160">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="afc91-161">如果您的公司启用了单一登录，但您收到错误或登录失败，请按照以下两个解决方案之一进行操作。</span><span class="sxs-lookup"><span data-stu-id="afc91-161">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="afc91-162">以集成用户的形式登录到 ServiceNow</span><span class="sxs-lookup"><span data-stu-id="afc91-162">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="afc91-163">导航回 ServiceNow 中的 "授权" 页面。</span><span class="sxs-lookup"><span data-stu-id="afc91-163">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="afc91-164">选择右上角的 " **不向您** 链接"。</span><span class="sxs-lookup"><span data-stu-id="afc91-164">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="afc91-165">登录到 ServiceNow，将其作为您以前从安装清单创建的集成用户。</span><span class="sxs-lookup"><span data-stu-id="afc91-165">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="afc91-166">在 ServiceNow 页面中选择 " **允许** "，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。</span><span class="sxs-lookup"><span data-stu-id="afc91-166">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="afc91-167">继续执行安装步骤。</span><span class="sxs-lookup"><span data-stu-id="afc91-167">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="afc91-168">创建安全管理员用户</span><span class="sxs-lookup"><span data-stu-id="afc91-168">Create a security admin user</span></span>

1. <span data-ttu-id="afc91-169">在 Azure Active Directory 中创建具有安全管理员权限的用户。</span><span class="sxs-lookup"><span data-stu-id="afc91-169">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="afc91-170">用户需要与您在安装清单中创建的集成用户具有相同的名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="afc91-170">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="afc91-171">登录和连接完成后，可以删除安全管理员角色。</span><span class="sxs-lookup"><span data-stu-id="afc91-171">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="afc91-172">作为此用户登录到 Microsoft 365 安全中心，并按照安装步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="afc91-172">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="afc91-173">IP 筛选</span><span class="sxs-lookup"><span data-stu-id="afc91-173">IP filtering</span></span>

<span data-ttu-id="afc91-174">如果已启用 IP 筛选，则可能需要显式允许 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="afc91-174">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="afc91-175">有关如何允许 ServiceNow 中的 IP 范围的信息，请参阅 [IP 地址访问控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 。</span><span class="sxs-lookup"><span data-stu-id="afc91-175">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="afc91-176">有关允许的 IP 地址列表，请参阅 [AZURE IP 范围和服务标记-公共云](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 。</span><span class="sxs-lookup"><span data-stu-id="afc91-176">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="afc91-177">安装已完成，但看不到票证且无法共享</span><span class="sxs-lookup"><span data-stu-id="afc91-177">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="afc91-178">如果已完成安装和设置步骤，但您在主页上看不到 ServiceNow 卡，并且无法从 Microsoft 安全分数中共享到 ServiceNow，请在处检查设置页面的状态 https://security.microsoft.com/ticketProvisioning 。</span><span class="sxs-lookup"><span data-stu-id="afc91-178">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="afc91-179">选择 " **授权** " 并返回到主页。</span><span class="sxs-lookup"><span data-stu-id="afc91-179">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="afc91-180">应显示卡片。</span><span class="sxs-lookup"><span data-stu-id="afc91-180">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="afc91-181">资源</span><span class="sxs-lookup"><span data-stu-id="afc91-181">Resources</span></span>

- [<span data-ttu-id="afc91-182">在安全中心中管理 ServiceNow 票证</span><span class="sxs-lookup"><span data-stu-id="afc91-182">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)