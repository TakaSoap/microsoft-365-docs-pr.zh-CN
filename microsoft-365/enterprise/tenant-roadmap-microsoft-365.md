---
title: 租户的租户Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: 设置租户租户的Microsoft 365。
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909450"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="ccf14-103">租户的租户Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ccf14-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="ccf14-104">你的Microsoft 365租户是分配给你的组织的一组服务。</span><span class="sxs-lookup"><span data-stu-id="ccf14-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="ccf14-105">通常，此租户与一个或多个公共 DNS 域名相关联，并充当不同订阅以及分配给用户帐户的许可证的中心和独立容器。</span><span class="sxs-lookup"><span data-stu-id="ccf14-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="ccf14-106">有关详细信息，请参阅 Microsoft 云产品/服务订阅、许可证 [、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf14-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="ccf14-107">创建租户时Microsoft 365租户，将其分配给特定地理位置。</span><span class="sxs-lookup"><span data-stu-id="ccf14-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="ccf14-108">还可以拥有具有多个地理位置的租户，将租户从一个位置移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="ccf14-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="ccf14-109">若要使租户为用户、组、许可证和云应用做好准备，必须仔细规划和执行租户配置。</span><span class="sxs-lookup"><span data-stu-id="ccf14-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="ccf14-110">设置 Microsoft 365 租户</span><span class="sxs-lookup"><span data-stu-id="ccf14-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="ccf14-111">在确保优化网络以同时针对本地和远程工作人员访问 Microsoft 365 后，下一项重大任务是为 DNS 域名、公共服务以及支持安全用户登录的标识基础结构规划并配置 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="ccf14-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="ccf14-112">计划</span><span class="sxs-lookup"><span data-stu-id="ccf14-112">Plan</span></span>

<span data-ttu-id="ccf14-113">若要规划租户实施，请执行：</span><span class="sxs-lookup"><span data-stu-id="ccf14-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="ccf14-114">了解 Azure AD 租户Azure Active Directory (订阅、) 许可证</span><span class="sxs-lookup"><span data-stu-id="ccf14-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="ccf14-115">了解如何使用第三方 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="ccf14-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="ccf14-116">了解租户租户Microsoft 365 Azure AD 服务集成的方式</span><span class="sxs-lookup"><span data-stu-id="ccf14-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="ccf14-117">规划客户端应用支持</span><span class="sxs-lookup"><span data-stu-id="ccf14-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="ccf14-118">确定如何使用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="ccf14-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="ccf14-119">规划 Office 2007 和 Office 2010 升级</span><span class="sxs-lookup"><span data-stu-id="ccf14-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="ccf14-120">了解租户隔离</span><span class="sxs-lookup"><span data-stu-id="ccf14-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="ccf14-121">部署</span><span class="sxs-lookup"><span data-stu-id="ccf14-121">Deploy</span></span>

<span data-ttu-id="ccf14-122">部署租户：</span><span class="sxs-lookup"><span data-stu-id="ccf14-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="ccf14-123">为 [组织添加 DNS](../admin/setup/add-domain.md) 域。</span><span class="sxs-lookup"><span data-stu-id="ccf14-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="ccf14-124">使用[管理中心 中的Microsoft 365指南](setup-guides-for-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf14-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="ccf14-125">构建标识[基础结构](identity-roadmap-microsoft-365.md)[，并保护用户登录](microsoft-365-secure-sign-in.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf14-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="ccf14-126">移动租户的地理位置</span><span class="sxs-lookup"><span data-stu-id="ccf14-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="ccf14-127">Microsoft 继续打开新的数据中心地理位置， (地理位置) 服务Microsoft 365地理位置。</span><span class="sxs-lookup"><span data-stu-id="ccf14-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="ccf14-128">这些新数据中心地理位置增加了容量和计算资源，以支持客户需求和使用情况增长。</span><span class="sxs-lookup"><span data-stu-id="ccf14-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="ccf14-129">此外，新的数据中心地理位置为核心客户数据提供地理位置内数据驻留。</span><span class="sxs-lookup"><span data-stu-id="ccf14-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="ccf14-130">有关详细信息，请参阅将[核心数据移动到Microsoft 365地理位置](moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf14-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="ccf14-131">部署Microsoft 365多地理位置</span><span class="sxs-lookup"><span data-stu-id="ccf14-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="ccf14-132">利用 Microsoft 365 多地理位置，你的组织可将其 Microsoft 365 触及范围扩展到你的现有租户内的多个地理区域和/或国家或地区。</span><span class="sxs-lookup"><span data-stu-id="ccf14-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="ccf14-133">有关详细信息，请参阅 [Microsoft 365 多地理位置](microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf14-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="ccf14-134">管理多个 Microsoft 365 租户</span><span class="sxs-lookup"><span data-stu-id="ccf14-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="ccf14-135">尽管对于组织组织来说，拥有一个租户是理想选择，但你可能是拥有多个租户的许多组织之一。</span><span class="sxs-lookup"><span data-stu-id="ccf14-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="ccf14-136">原因可能包括合并和收购、您希望管理隔离，或者您具有分散的 IT。</span><span class="sxs-lookup"><span data-stu-id="ccf14-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="ccf14-137">如果你有多个Microsoft 365，请参阅以下文章，详细了解：</span><span class="sxs-lookup"><span data-stu-id="ccf14-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="ccf14-138">租户间协作</span><span class="sxs-lookup"><span data-stu-id="ccf14-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="ccf14-139">交叉租户邮箱迁移</span><span class="sxs-lookup"><span data-stu-id="ccf14-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="ccf14-140">租户到租户迁移</span><span class="sxs-lookup"><span data-stu-id="ccf14-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="ccf14-141">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ccf14-141">Next step</span></span>

<span data-ttu-id="ccf14-142">使用订阅、许可证、 [帐户和租户开始租户规划](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf14-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>