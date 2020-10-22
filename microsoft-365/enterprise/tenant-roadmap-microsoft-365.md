---
title: 适用于 Microsoft 365 的租户路线图
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: 设置适用于 Microsoft 365 的租户的路线图。
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656003"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="95df2-103">适用于 Microsoft 365 的租户路线图</span><span class="sxs-lookup"><span data-stu-id="95df2-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="95df2-104">你的 Microsoft 365 租户是分配给你的组织的一组服务。</span><span class="sxs-lookup"><span data-stu-id="95df2-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="95df2-105">通常情况下，此租户与一个或多个 DNS 域名相关联，并充当不同订阅的中央容器以及分配给用户帐户的这些名称中的许可证。</span><span class="sxs-lookup"><span data-stu-id="95df2-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="95df2-106">有关详细信息，请参阅 [Microsoft 云产品服务的订阅、许可证、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="95df2-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="95df2-107">创建 Microsoft 365 租户时，可将其分配到特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="95df2-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="95df2-108">您还可以拥有多个地理位置的租户，并将您的租户从一个位置移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="95df2-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="95df2-109">若要让你的租户准备好进行标识，请务必仔细规划和执行你的租户配置。</span><span class="sxs-lookup"><span data-stu-id="95df2-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="95df2-110">设置你的 Microsoft 365 租户</span><span class="sxs-lookup"><span data-stu-id="95df2-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="95df2-111">在确保网络已针对本地和远程工作人员访问 Microsoft 365 的优化之后，下一个大型任务将进行规划，然后为 Microsoft 365 租户配置 DNS 域名、常见服务以及支持安全用户登录的身份基础结构。</span><span class="sxs-lookup"><span data-stu-id="95df2-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="95df2-112">计划</span><span class="sxs-lookup"><span data-stu-id="95df2-112">Plan</span></span>

<span data-ttu-id="95df2-113">若要规划你的租户实现，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95df2-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="95df2-114">了解订阅、许可证和 Azure Active Directory (Azure AD) 租户</span><span class="sxs-lookup"><span data-stu-id="95df2-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="95df2-115">了解如何使用第三方 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="95df2-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="95df2-116">了解 Microsoft 365 租户与 Azure AD 服务集成的方式</span><span class="sxs-lookup"><span data-stu-id="95df2-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="95df2-117">规划客户端应用程序支持</span><span class="sxs-lookup"><span data-stu-id="95df2-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="95df2-118">确定如何使用混合新式身份验证</span><span class="sxs-lookup"><span data-stu-id="95df2-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="95df2-119">规划 Office 2007 和 Office 2010 升级</span><span class="sxs-lookup"><span data-stu-id="95df2-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="95df2-120">了解租户隔离</span><span class="sxs-lookup"><span data-stu-id="95df2-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="95df2-121">获取有关 Microsoft 365 服务保证的详细信息</span><span class="sxs-lookup"><span data-stu-id="95df2-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="95df2-122">部署</span><span class="sxs-lookup"><span data-stu-id="95df2-122">Deploy</span></span>

<span data-ttu-id="95df2-123">若要部署租户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95df2-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="95df2-124">为您的组织添加 [DNS 域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 。</span><span class="sxs-lookup"><span data-stu-id="95df2-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="95df2-125">使用 [Microsoft 365 管理中心中的安装指南](setup-guides-for-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="95df2-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="95df2-126">构建你的 [身份基础结构](identity-roadmap-microsoft-365.md) 并 [保护你的用户登录](microsoft-365-secure-sign-in.md)。</span><span class="sxs-lookup"><span data-stu-id="95df2-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="95df2-127">移动租户的地理位置</span><span class="sxs-lookup"><span data-stu-id="95df2-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="95df2-128">Microsoft 继续为 Microsoft 365 服务 (信息) 打开新的数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="95df2-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="95df2-129">这些新数据中心信息添加容量和计算资源，以支持客户需求和使用情况增长。</span><span class="sxs-lookup"><span data-stu-id="95df2-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="95df2-130">此外，新的数据中心信息为核心客户数据提供了地理位置数据常驻。</span><span class="sxs-lookup"><span data-stu-id="95df2-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="95df2-131">有关详细信息，请参阅 [将 core Data 移动到新的 Microsoft 365 datacenter 信息](moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="95df2-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="95df2-132">部署 Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="95df2-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="95df2-133">利用 Microsoft 365 多地理位置，你的组织可将其 Microsoft 365 触及范围扩展到你的现有租户内的多个地理区域和/或国家或地区。</span><span class="sxs-lookup"><span data-stu-id="95df2-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="95df2-134">有关详细信息，请参阅 [Microsoft 365 多地理](microsoft-365-multi-geo.md)位置。</span><span class="sxs-lookup"><span data-stu-id="95df2-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="95df2-135">管理多个 Microsoft 365 租赁</span><span class="sxs-lookup"><span data-stu-id="95df2-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="95df2-136">尽管为您的组织使用一个租户是理想的，但您可以是包含多个租赁的多个组织之一。</span><span class="sxs-lookup"><span data-stu-id="95df2-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="95df2-137">多个租赁的原因可能包括合并和收购、您需要管理隔离，或者您有分散的原因。</span><span class="sxs-lookup"><span data-stu-id="95df2-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="95df2-138">如果你有多个 Microsoft 365 租赁，请参阅以下文章，了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="95df2-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="95df2-139">租户间协作</span><span class="sxs-lookup"><span data-stu-id="95df2-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="95df2-140">交叉租户邮箱迁移</span><span class="sxs-lookup"><span data-stu-id="95df2-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="95df2-141">租户到租户迁移</span><span class="sxs-lookup"><span data-stu-id="95df2-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="95df2-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="95df2-142">Next step</span></span>

<span data-ttu-id="95df2-143">使用 [订阅、许可证、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)启动租户规划。</span><span class="sxs-lookup"><span data-stu-id="95df2-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
