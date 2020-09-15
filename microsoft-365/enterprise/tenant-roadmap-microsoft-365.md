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
ms.collection: M365-subscription-management
ms.custom: it-pro
description: 设置适用于 Microsoft 365 的租户的路线图。
ms.openlocfilehash: 7834e8b7f9ff8a1b33f2f2a7ccc4a499e4da7c69
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775143"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="e049b-103">适用于 Microsoft 365 的租户路线图</span><span class="sxs-lookup"><span data-stu-id="e049b-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="e049b-104">你的 Microsoft 365 租户是分配给你的组织的一组服务。</span><span class="sxs-lookup"><span data-stu-id="e049b-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="e049b-105">通常情况下，此租户与一个或多个 DNS 域名相关联，并充当不同订阅的中央容器以及分配给用户帐户的这些名称中的许可证。</span><span class="sxs-lookup"><span data-stu-id="e049b-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="e049b-106">创建 Microsoft 365 租户时，可将其分配到特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="e049b-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="e049b-107">您还可以拥有多个地理位置的租户，并将您的租户从一个位置移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="e049b-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="e049b-108">若要让你的租户为网络和标识的基础服务做好准备，请务必仔细规划和执行你的租户配置。</span><span class="sxs-lookup"><span data-stu-id="e049b-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="e049b-109">套餐</span><span class="sxs-lookup"><span data-stu-id="e049b-109">Plan</span></span>

<span data-ttu-id="e049b-110">若要规划你的租户实现，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e049b-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="e049b-111">了解订阅、许可证和 Azure Active Directory (Azure AD) 租户</span><span class="sxs-lookup"><span data-stu-id="e049b-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="e049b-112">了解如何使用第三方 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="e049b-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="e049b-113">Microsoft 365 管理中心中的访问安装指南</span><span class="sxs-lookup"><span data-stu-id="e049b-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="e049b-114">了解 Microsoft 365 租户与 Azure AD 服务集成的方式</span><span class="sxs-lookup"><span data-stu-id="e049b-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="e049b-115">规划客户端应用程序支持</span><span class="sxs-lookup"><span data-stu-id="e049b-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="e049b-116">确定如何使用混合新式身份验证</span><span class="sxs-lookup"><span data-stu-id="e049b-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="e049b-117">规划 Office 2007 和 Office 2010 升级</span><span class="sxs-lookup"><span data-stu-id="e049b-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="e049b-118">了解租户隔离</span><span class="sxs-lookup"><span data-stu-id="e049b-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="e049b-119">获取有关 Microsoft 365 服务保证的详细信息</span><span class="sxs-lookup"><span data-stu-id="e049b-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="e049b-120">部署</span><span class="sxs-lookup"><span data-stu-id="e049b-120">Deploy</span></span>

<span data-ttu-id="e049b-121">若要部署你的租户，请为你的组织 [添加 DNS 域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 。</span><span class="sxs-lookup"><span data-stu-id="e049b-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="e049b-122">具有多个地理位置的租户</span><span class="sxs-lookup"><span data-stu-id="e049b-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="e049b-123">利用 Microsoft 365 多地理位置，你的组织可将其 Microsoft 365 触及范围扩展到你的现有租户内的多个地理区域和/或国家或地区。</span><span class="sxs-lookup"><span data-stu-id="e049b-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="e049b-124">若要了解有关 Microsoft 365 多地理位置的信息，包括如何规划、配置和管理，请 [从这里开始](microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="e049b-124">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="e049b-125">移动租户的地理位置</span><span class="sxs-lookup"><span data-stu-id="e049b-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="e049b-126">Microsoft 继续为 Microsoft 365 服务 (信息) 打开新的数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="e049b-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="e049b-127">这些新数据中心信息添加容量和计算资源，以支持客户需求和使用情况增长。</span><span class="sxs-lookup"><span data-stu-id="e049b-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="e049b-128">此外，新的数据中心信息为核心客户数据提供了地理位置数据常驻。</span><span class="sxs-lookup"><span data-stu-id="e049b-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="e049b-129">有关 Microsoft 365 datacenter geo 的信息，包括如何请求地区数据移动，请 [从这里开始](moving-data-to-new-datacenter-geos.md)。</span><span class="sxs-lookup"><span data-stu-id="e049b-129">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="e049b-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e049b-130">Next step</span></span>

<span data-ttu-id="e049b-131">使用 [订阅、许可证、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)启动租户规划。</span><span class="sxs-lookup"><span data-stu-id="e049b-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

