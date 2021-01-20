---
title: Microsoft 365 企业版租户管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 租户的规划、部署和持续操作概述。
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908481"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a><span data-ttu-id="2ad34-103">Microsoft 365 企业版租户管理</span><span class="sxs-lookup"><span data-stu-id="2ad34-103">Tenant management for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="2ad34-104">通过云计算创建组织数字化转型的路径需要一个稳固的基础，员工可以依靠此基础来提高工作效率、协作、性能、隐私、合规性和安全性。</span><span class="sxs-lookup"><span data-stu-id="2ad34-104">Creating a path to your organization's digital transformation with cloud computing requires a firm foundation upon which your workers can rely for productivity, collaboration, performance, privacy, compliance, and security.</span></span>

<span data-ttu-id="2ad34-105">正确配置 Microsoft 365 租户可提供此基础，让工作人员专注于完成工作，IT 部门专注于提供其他业务价值端到端解决方案。</span><span class="sxs-lookup"><span data-stu-id="2ad34-105">Correct configuration of your Microsoft 365 tenants provides that foundation, leaving your workers to focus on getting their work done and your IT department to focus on end-to-end solutions that provide additional business value.</span></span> 

<span data-ttu-id="2ad34-106">此解决方案将执行以下步骤中该基础的配置：</span><span class="sxs-lookup"><span data-stu-id="2ad34-106">This solution takes you through the configuration of that foundation in these steps:</span></span>

1. <span data-ttu-id="2ad34-107">确定租户</span><span class="sxs-lookup"><span data-stu-id="2ad34-107">Determine your tenants</span></span>
2. <span data-ttu-id="2ad34-108">优化网络</span><span class="sxs-lookup"><span data-stu-id="2ad34-108">Optimize your networking</span></span>
3. <span data-ttu-id="2ad34-109">同步标识并强制执行安全登录</span><span class="sxs-lookup"><span data-stu-id="2ad34-109">Synchronize your identities and enforce secure sign-ins</span></span>
4. <span data-ttu-id="2ad34-110">迁移 Windows 设备、Office 客户端和本地 Office 服务器和数据</span><span class="sxs-lookup"><span data-stu-id="2ad34-110">Migrate your Windows devices, Office clients, and on-premises Office servers and data</span></span>
5. <span data-ttu-id="2ad34-111">部署设备和应用管理</span><span class="sxs-lookup"><span data-stu-id="2ad34-111">Deploy device and app management</span></span>

<span data-ttu-id="2ad34-112">但是首先，让我们花些时间了解一下租户是什么，以及提供稳固基础的租户的外观。</span><span class="sxs-lookup"><span data-stu-id="2ad34-112">But first, let's take a moment to understand what a tenant is and what a tenant that provides a firm foundation looks like.</span></span>

## <a name="a-microsoft-365-tenant-defined"></a><span data-ttu-id="2ad34-113">定义的 Microsoft 365 租户</span><span class="sxs-lookup"><span data-stu-id="2ad34-113">A Microsoft 365 tenant defined</span></span>

<span data-ttu-id="2ad34-114">Microsoft 365 租户是 Microsoft 365 服务的专用实例，以及存储在特定默认位置（如欧洲或北美）中的组织数据。</span><span class="sxs-lookup"><span data-stu-id="2ad34-114">A Microsoft 365 tenant is a dedicated instance of the services of Microsoft 365 and your organization data stored within a specific default location, such as Europe or North America.</span></span> <span data-ttu-id="2ad34-115">为组织创建租户时指定此位置。</span><span class="sxs-lookup"><span data-stu-id="2ad34-115">This location is specified when you create the tenant for your organization.</span></span> <span data-ttu-id="2ad34-116">每个 Microsoft 365 租户各不相同、唯一，并且独立于所有其他 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="2ad34-116">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="2ad34-117">从 Microsoft 购买一个或多个产品（如 Microsoft 365 E3 或 E5）时，将创建一个 Microsoft 365 租户，并为每个租户创建一组许可证。</span><span class="sxs-lookup"><span data-stu-id="2ad34-117">You create a Microsoft 365 tenant when you purchase one or more products from Microsoft, such as Microsoft 365 E3 or E5, and a set of licenses for each.</span></span>

<span data-ttu-id="2ad34-118">Microsoft 365 租户还包括 Azure Active Directory (Azure AD) 租户，这是用于用户帐户、组和其他对象的 Azure AD 的专用实例。</span><span class="sxs-lookup"><span data-stu-id="2ad34-118">Your Microsoft 365 tenant also includes an Azure Active Directory (Azure AD) tenant, which is a dedicated instance of Azure AD for user accounts, groups, and other objects.</span></span> <span data-ttu-id="2ad34-119">每个 Azure AD 租户都是不同、唯一的，并且独立于所有其他 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="2ad34-119">Each Azure AD tenant is distinct, unique, and separate from all other Azure AD tenants.</span></span> <span data-ttu-id="2ad34-120">虽然你的组织可以有多个可以使用 Azure 订阅设置的 Azure AD 租户，但 Microsoft 365 租户只能使用单个 Azure AD 租户，即创建租户时创建的租户。</span><span class="sxs-lookup"><span data-stu-id="2ad34-120">While your organization can have multiple Azure AD tenants that you can set up with Azure subscriptions, Microsoft 365 tenants can only use a single Azure AD tenant, the one that was created when you created the tenant.</span></span> 

<span data-ttu-id="2ad34-121">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="2ad34-121">Here is an example:</span></span>

![具有 Azure AD 租户的 Microsoft 365 租户示例](../media/tenant-management-overview/tenant-management-example-tenant.png)

<span data-ttu-id="2ad34-123">*租户管理* 是 Microsoft 365 租户的规划、部署和持续操作。</span><span class="sxs-lookup"><span data-stu-id="2ad34-123">*Tenant management* is the planning, deployment, and ongoing operation of your Microsoft 365 tenants.</span></span> 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a><span data-ttu-id="2ad34-124">设计良好且操作良好的租户的属性</span><span class="sxs-lookup"><span data-stu-id="2ad34-124">Attributes of a well-designed and operating tenant</span></span>

<span data-ttu-id="2ad34-125">除了租户的正确名称和位置之外，还需要规划、部署和管理其他元素，以确保云生产力应用（如 Microsoft Teams 和 Exchange Online）的用户体验有效、安全且 &mdash; &mdash; 性能高。</span><span class="sxs-lookup"><span data-stu-id="2ad34-125">Beyond the correct name and location for your tenant, there are additional elements to plan, deploy, and manage to ensure that your user experiences with cloud productivity apps&mdash;such as Microsoft Teams and Exchange Online&mdash;are effective, secure, and performant.</span></span>

<span data-ttu-id="2ad34-126">以下是元素：</span><span class="sxs-lookup"><span data-stu-id="2ad34-126">Here are the elements:</span></span>

- <span data-ttu-id="2ad34-127">你拥有一组正确的产品 (订阅和) 许可证。</span><span class="sxs-lookup"><span data-stu-id="2ad34-127">You have the correct set of products (subscriptions) and licenses.</span></span>
  - <span data-ttu-id="2ad34-128">一组产品符合你的业务、IT 和安全需求。</span><span class="sxs-lookup"><span data-stu-id="2ad34-128">The set of products match your business, IT, and security needs.</span></span>
  - <span data-ttu-id="2ad34-129">为工作人员提供足够数量的许可证以及人员配置的预期变化。</span><span class="sxs-lookup"><span data-stu-id="2ad34-129">There is an adequate number of licenses for your workers and anticipated changes in staffing.</span></span>
- <span data-ttu-id="2ad34-130">对于网络：</span><span class="sxs-lookup"><span data-stu-id="2ad34-130">For networking:</span></span>
  - <span data-ttu-id="2ad34-131">已配置正确的 DNS 域名。</span><span class="sxs-lookup"><span data-stu-id="2ad34-131">You have configured the correct DNS domain names.</span></span>
  - <span data-ttu-id="2ad34-132">对于企业网络，已针对现场工作人员优化了到 Microsoft 网络的网络流量。</span><span class="sxs-lookup"><span data-stu-id="2ad34-132">For enterprise networks, you have optimized network traffic to the Microsoft network for onsite workers.</span></span>
  - <span data-ttu-id="2ad34-133">你已针对使用 VPN 客户端的远程工作者优化了网络流量。</span><span class="sxs-lookup"><span data-stu-id="2ad34-133">You have optimized network traffic for remote workers who are using a VPN client.</span></span>
- <span data-ttu-id="2ad34-134">已同步 Active Directory 域服务 (AD DS) 、组和其他对象。</span><span class="sxs-lookup"><span data-stu-id="2ad34-134">You have synchronized your Active Directory Domain Services (AD DS) accounts, groups, and other objects.</span></span>
  - <span data-ttu-id="2ad34-135">你的 Azure AD 租户帐户将映射到具有电子邮件地址的正确 DNS 域的 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ad34-135">Your Azure AD tenant accounts are mapped to Exchange Online mailboxes with the correct DNS domains for email addresses.</span></span>
  - <span data-ttu-id="2ad34-136">你的用户帐户已分配有来自正确购买的产品（如 Microsoft 365 E3 或 E5 (）的正确) 。</span><span class="sxs-lookup"><span data-stu-id="2ad34-136">Your user accounts have been assigned the correct licenses from the correct purchased products (such as Microsoft 365 E3 or E5).</span></span>
- <span data-ttu-id="2ad34-137">已配置强标识和访问管理。</span><span class="sxs-lookup"><span data-stu-id="2ad34-137">You have configured strong identity and access management.</span></span>
  - <span data-ttu-id="2ad34-138">您需要使用无密码身份验证或多重身份验证在 MFA (安全) 。</span><span class="sxs-lookup"><span data-stu-id="2ad34-138">You are requiring secure user sign-in with passwordless or multi-factor authentication (MFA).</span></span>
  - <span data-ttu-id="2ad34-139">您具有条件访问策略，这些策略强制实施登录要求和针对更高安全级别的限制。</span><span class="sxs-lookup"><span data-stu-id="2ad34-139">You have Conditional Access policies that enforce sign-in requirements and restrictions for higher levels of security.</span></span>
- <span data-ttu-id="2ad34-140">本地 Office 服务器及其数据已迁移到云应用或正在混合配置中使用。</span><span class="sxs-lookup"><span data-stu-id="2ad34-140">On-premises Office servers and their data have been migrated to cloud apps or are being used in a hybrid configuration.</span></span>
- <span data-ttu-id="2ad34-141">你将使用内置于 Microsoft 365 的 Intune 或基本移动性和安全性进行设备管理。</span><span class="sxs-lookup"><span data-stu-id="2ad34-141">You are doing device management with Intune or Basic Mobility and Security built into Microsoft 365.</span></span>
  - <span data-ttu-id="2ad34-142">组织拥有的设备已注册和管理。</span><span class="sxs-lookup"><span data-stu-id="2ad34-142">Your organization-owned devices are enrolled and managed.</span></span>
  - <span data-ttu-id="2ad34-143">管理个人设备的应用。</span><span class="sxs-lookup"><span data-stu-id="2ad34-143">The apps for personal devices are managed.</span></span>

<span data-ttu-id="2ad34-144">下面是具有所有这些元素的 Microsoft 365 租户的示例。</span><span class="sxs-lookup"><span data-stu-id="2ad34-144">Here is an example of a Microsoft 365 tenant with all these elements in place.</span></span>

![Microsoft 365 租户示例](../media/tenant-management-overview/tenant-management-tenant-config.png)

<span data-ttu-id="2ad34-146">在此图中，Microsoft 365 租户包括：</span><span class="sxs-lookup"><span data-stu-id="2ad34-146">In this illustration, the Microsoft 365 tenant includes:</span></span>

- <span data-ttu-id="2ad34-147">Microsoft 365 E3 和 E5 的产品和许可证。</span><span class="sxs-lookup"><span data-stu-id="2ad34-147">Products and licenses for Microsoft 365 E3 and E5.</span></span>
- <span data-ttu-id="2ad34-148">Microsoft 365 生产力应用。</span><span class="sxs-lookup"><span data-stu-id="2ad34-148">Microsoft 365 productivity apps.</span></span>
- <span data-ttu-id="2ad34-149">具有已注册的设备以及设备和应用程序策略的 Intune。</span><span class="sxs-lookup"><span data-stu-id="2ad34-149">Intune with enrolled devices and device and application policies.</span></span>
- <span data-ttu-id="2ad34-150">已同步用户帐户的 Azure AD 租户 (组和其他目录对象不会显示在) 、域和条件访问策略中。</span><span class="sxs-lookup"><span data-stu-id="2ad34-150">An Azure AD tenant that has synchronized user account (groups and other directory objects are not shown), domains, and Conditional Access policies.</span></span>

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a><span data-ttu-id="2ad34-151">Microsoft 365 企业版租户功能</span><span class="sxs-lookup"><span data-stu-id="2ad34-151">Tenant capabilities for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="2ad34-152">以下各节和表列出了此解决方案中步骤的关键功能和许可。</span><span class="sxs-lookup"><span data-stu-id="2ad34-152">The following sections and table list the key capabilities and licensing for the steps in this solution.</span></span>

### <a name="tenant"></a><span data-ttu-id="2ad34-153">租户</span><span class="sxs-lookup"><span data-stu-id="2ad34-153">Tenant</span></span>

| <span data-ttu-id="2ad34-154">功能或特性</span><span class="sxs-lookup"><span data-stu-id="2ad34-154">Capability or feature</span></span> | <span data-ttu-id="2ad34-155">说明</span><span class="sxs-lookup"><span data-stu-id="2ad34-155">Description</span></span> | <span data-ttu-id="2ad34-156">许可</span><span class="sxs-lookup"><span data-stu-id="2ad34-156">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="2ad34-157">多个租户</span><span class="sxs-lookup"><span data-stu-id="2ad34-157">Multiple tenants</span></span> | <span data-ttu-id="2ad34-158">每个 Microsoft 365 租户各不相同、唯一，并且独立于所有其他 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="2ad34-158">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="2ad34-159">对于多个租户，在管理租户和为用户提供服务时，存在一些限制和其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="2ad34-159">With multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span> | <span data-ttu-id="2ad34-160">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="2ad34-161">交叉租户邮箱迁移</span><span class="sxs-lookup"><span data-stu-id="2ad34-161">Cross-tenant mailbox migration</span></span> | <span data-ttu-id="2ad34-162">租户管理员可以在租户之间移动邮箱，这些租户在本地系统中具有最少的基础结构依赖关系。</span><span class="sxs-lookup"><span data-stu-id="2ad34-162">Tenant administrators can move mailboxes between tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="2ad34-163">这无需离开和载入邮箱。</span><span class="sxs-lookup"><span data-stu-id="2ad34-163">This removes the need to off-board and onboard mailboxes.</span></span> | <span data-ttu-id="2ad34-164">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-164">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="2ad34-165">多地理位置</span><span class="sxs-lookup"><span data-stu-id="2ad34-165">Multi-Geo</span></span> | <span data-ttu-id="2ad34-166">租户可以将静止数据存储在已选择满足数据驻留要求的其他数据中心地理位置中。</span><span class="sxs-lookup"><span data-stu-id="2ad34-166">Your tenant can store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements.</span></span> | <span data-ttu-id="2ad34-167">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-167">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="2ad34-168">将核心数据移动到新的数据中心地理位置</span><span class="sxs-lookup"><span data-stu-id="2ad34-168">Move core data to a new datacenter geo</span></span> | <span data-ttu-id="2ad34-169">随着 Microsoft 添加新的数据中心地理位置来增加容量和计算资源，你可以请求数据中心异地移动，以驻留核心客户数据。</span><span class="sxs-lookup"><span data-stu-id="2ad34-169">As Microsoft adds new datacenter geos for additional capacity and compute resources, you can request a datacenter geo move for in-geo data residency for your core customer data.</span></span> | <span data-ttu-id="2ad34-170">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-170">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="networking"></a><span data-ttu-id="2ad34-171">网络</span><span class="sxs-lookup"><span data-stu-id="2ad34-171">Networking</span></span>

| <span data-ttu-id="2ad34-172">功能或特性</span><span class="sxs-lookup"><span data-stu-id="2ad34-172">Capability or feature</span></span> | <span data-ttu-id="2ad34-173">说明</span><span class="sxs-lookup"><span data-stu-id="2ad34-173">Description</span></span> | <span data-ttu-id="2ad34-174">许可</span><span class="sxs-lookup"><span data-stu-id="2ad34-174">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="2ad34-175">Network Insights</span><span class="sxs-lookup"><span data-stu-id="2ad34-175">Network Insights</span></span> | <span data-ttu-id="2ad34-176">从 Microsoft 365 租户收集的网络性能指标，可帮助你设计办公地点的网络外围。</span><span class="sxs-lookup"><span data-stu-id="2ad34-176">Network performance metrics collected from your Microsoft 365 tenant to help you design network perimeters for your office locations.</span></span> | <span data-ttu-id="2ad34-177">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-177">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="2ad34-178">自动化终结点更新</span><span class="sxs-lookup"><span data-stu-id="2ad34-178">Automate endpoint updates</span></span> | <span data-ttu-id="2ad34-179">在客户端 PAC 文件和网络设备和服务中自动执行 Microsoft 365 终结点的配置和持续更新。</span><span class="sxs-lookup"><span data-stu-id="2ad34-179">Automate the configuration and ongoing updates for Microsoft 365 endpoints in your client PAC files and network devices and services.</span></span> | <span data-ttu-id="2ad34-180">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-180">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="identity"></a><span data-ttu-id="2ad34-181">标识</span><span class="sxs-lookup"><span data-stu-id="2ad34-181">Identity</span></span>

| <span data-ttu-id="2ad34-182">功能或特性</span><span class="sxs-lookup"><span data-stu-id="2ad34-182">Capability or feature</span></span> | <span data-ttu-id="2ad34-183">说明</span><span class="sxs-lookup"><span data-stu-id="2ad34-183">Description</span></span> | <span data-ttu-id="2ad34-184">许可</span><span class="sxs-lookup"><span data-stu-id="2ad34-184">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="2ad34-185">将本地 Active Directory 域服务 (AD DS) Azure AD 租户同步</span><span class="sxs-lookup"><span data-stu-id="2ad34-185">Synchronize on-premises Active Directory Domain Services (AD DS) with your Azure AD tenant</span></span>    | <span data-ttu-id="2ad34-186">将本地标识提供程序用于用户帐户、组和其他对象。</span><span class="sxs-lookup"><span data-stu-id="2ad34-186">Leverage your on-premises identity provider for user accounts, groups, and other objects.</span></span> | <span data-ttu-id="2ad34-187">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-187">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="2ad34-188">通过安全性默认设置强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="2ad34-188">MFA enforced with security defaults</span></span>   | <span data-ttu-id="2ad34-189">通过请求第二种形式的登录身份验证，抵御遭到入侵的身份和设备的威胁。安全性默认设置要求对所有用户帐户进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="2ad34-189">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="2ad34-190">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-190">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="2ad34-191">通过条件访问强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="2ad34-191">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="2ad34-192">需要基于具有条件访问策略的登录的属性的 MFA。</span><span class="sxs-lookup"><span data-stu-id="2ad34-192">Require MFA based on the attributes of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="2ad34-193">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-193">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="2ad34-194">通过基于风险的条件访问强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="2ad34-194">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="2ad34-195">需要基于使用 Microsoft Defender for Identity 的用户登录的风险进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="2ad34-195">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="2ad34-196">Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可）</span><span class="sxs-lookup"><span data-stu-id="2ad34-196">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="2ad34-197">自助服务密码重置 (SSPR)</span><span class="sxs-lookup"><span data-stu-id="2ad34-197">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="2ad34-198">允许用户重置或解锁其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="2ad34-198">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="2ad34-199">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-199">Microsoft 365 E3 or E5</span></span> |
||||

### <a name="migration"></a><span data-ttu-id="2ad34-200">迁移</span><span class="sxs-lookup"><span data-stu-id="2ad34-200">Migration</span></span>

| <span data-ttu-id="2ad34-201">功能或特性</span><span class="sxs-lookup"><span data-stu-id="2ad34-201">Capability or feature</span></span> | <span data-ttu-id="2ad34-202">说明</span><span class="sxs-lookup"><span data-stu-id="2ad34-202">Description</span></span> | <span data-ttu-id="2ad34-203">许可</span><span class="sxs-lookup"><span data-stu-id="2ad34-203">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="2ad34-204">迁移到 Windows 10</span><span class="sxs-lookup"><span data-stu-id="2ad34-204">Migrate to Windows 10</span></span> | <span data-ttu-id="2ad34-205">将运行 Windows 7 或 Windows 8.1 的设备迁移到 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="2ad34-205">Migrate your devices that run Windows 7 or Windows 8.1 to Windows 10 Enterprise.</span></span> | <span data-ttu-id="2ad34-206">Microsoft 365 E3 或 E5 中包含的 Windows 10 企业版许可证</span><span class="sxs-lookup"><span data-stu-id="2ad34-206">Windows 10 Enterprise licenses included with Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="2ad34-207">迁移到 Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="2ad34-207">Migrate to Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="2ad34-208">将 Office 客户端应用程序（如 Word 和 PowerPoint）迁移到从云中安装的版本，这些版本更新了新功能。</span><span class="sxs-lookup"><span data-stu-id="2ad34-208">Migrate your Office client apps such as Word and PowerPoint to the versions installed from the cloud that are updated with new features.</span></span> | <span data-ttu-id="2ad34-209">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-209">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="2ad34-210">将本地服务器和数据迁移到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ad34-210">Migrate on-premises servers and data to Microsoft 365</span></span> | <span data-ttu-id="2ad34-211">将 Exchange 邮箱、SharePoint 网站和 Skype for Business Online 迁移到 Microsoft 365 云服务。</span><span class="sxs-lookup"><span data-stu-id="2ad34-211">Migrate your Exchange mailboxes, SharePoint sites, and Skype for Business Online to Microsoft 365 cloud services.</span></span> | <span data-ttu-id="2ad34-212">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-212">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="device-and-app-management"></a><span data-ttu-id="2ad34-213">设备和应用管理</span><span class="sxs-lookup"><span data-stu-id="2ad34-213">Device and app management</span></span>

| <span data-ttu-id="2ad34-214">功能或特性</span><span class="sxs-lookup"><span data-stu-id="2ad34-214">Capability or feature</span></span> | <span data-ttu-id="2ad34-215">说明</span><span class="sxs-lookup"><span data-stu-id="2ad34-215">Description</span></span> | <span data-ttu-id="2ad34-216">许可</span><span class="sxs-lookup"><span data-stu-id="2ad34-216">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="2ad34-217">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2ad34-217">Microsoft Intune</span></span> | <span data-ttu-id="2ad34-218">提供移动设备管理 (MDM) 和移动应用程序管理 (MAM) 的基于云的服务，用于控制组织的应用程序和设备的使用方式，包括移动电话、平板电脑和笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="2ad34-218">A cloud-based service that provides mobile device management (MDM) and mobile application management (MAM) to control how your organization’s application and the devices are used, including mobile phones, tablets, and laptops.</span></span> | <span data-ttu-id="2ad34-219">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-219">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="2ad34-220">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="2ad34-220">Basic Mobility and Security</span></span> | <span data-ttu-id="2ad34-221">通过此内置服务保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 手机。</span><span class="sxs-lookup"><span data-stu-id="2ad34-221">Secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones with this built-in service.</span></span>  | <span data-ttu-id="2ad34-222">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="2ad34-222">Microsoft 365 E3 or E5</span></span> | 
||||

## <a name="next-steps"></a><span data-ttu-id="2ad34-223">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2ad34-223">Next steps</span></span>

<span data-ttu-id="2ad34-224">使用以下步骤设置和管理 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="2ad34-224">Use these steps to set up and manage your Microsoft 365 tenants.</span></span>

1. [<span data-ttu-id="2ad34-225">确定租户</span><span class="sxs-lookup"><span data-stu-id="2ad34-225">Determine your tenants</span></span>](tenant-management-tenants.md)
2. [<span data-ttu-id="2ad34-226">优化网络</span><span class="sxs-lookup"><span data-stu-id="2ad34-226">Optimize your networking</span></span>](tenant-management-networking.md)
3. [<span data-ttu-id="2ad34-227">同步标识并强制执行安全登录</span><span class="sxs-lookup"><span data-stu-id="2ad34-227">Synchronize your identities and enforce secure sign-ins</span></span>](tenant-management-identity.md)
4. [<span data-ttu-id="2ad34-228">迁移本地 Office 服务器和数据</span><span class="sxs-lookup"><span data-stu-id="2ad34-228">Migrate your on-premises Office servers and data</span></span>](tenant-management-migration.md)
5. [<span data-ttu-id="2ad34-229">部署设备和应用管理</span><span class="sxs-lookup"><span data-stu-id="2ad34-229">Deploy device and app management</span></span>](tenant-management-device-management.md)

<span data-ttu-id="2ad34-230">[![部署和管理 Microsoft 365 租户的步骤](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="2ad34-230">[![The steps to deploy and manage a Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span></span>

<span data-ttu-id="2ad34-231">每个步骤描述部署选项、总结结果和正在进行的维护任务。</span><span class="sxs-lookup"><span data-stu-id="2ad34-231">Each step describes deployment options, summarizes the results, and ongoing maintenance tasks.</span></span>

<span data-ttu-id="2ad34-232">若要了解虚构但具有代表性的多方组织如何部署其 Microsoft 365 租户的元素，请参阅 [Contoso 案例研究](../enterprise/contoso-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="2ad34-232">To understand how a fictional but representative multi-national organization deployed the elements of their Microsoft 365 tenant, see the [Contoso case study](../enterprise/contoso-case-study.md).</span></span>
