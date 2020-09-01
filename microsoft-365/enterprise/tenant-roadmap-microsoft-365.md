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
ms.openlocfilehash: 540d1bc53ac06b85d22a8a60a62e51761e10339c
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315749"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="2abac-103">适用于 Microsoft 365 的租户路线图</span><span class="sxs-lookup"><span data-stu-id="2abac-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="2abac-104">你的 Microsoft 365 租户是分配给你的组织的一组服务。</span><span class="sxs-lookup"><span data-stu-id="2abac-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="2abac-105">此租户通常与一个或多个 DNS 域名相关联，并充当不同订阅的中央容器以及分配给用户帐户的这些名称中的许可证。</span><span class="sxs-lookup"><span data-stu-id="2abac-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="2abac-106">创建 Microsoft 365 租户时，可将其分配到特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="2abac-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="2abac-107">您还可以拥有多个地理位置的租户，并将您的租户从一个位置移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="2abac-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="2abac-108">良好规划和执行的租户配置对于为网络和标识的基础服务做好准备是至关重要的。</span><span class="sxs-lookup"><span data-stu-id="2abac-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="2abac-109">套餐</span><span class="sxs-lookup"><span data-stu-id="2abac-109">Plan</span></span>

<span data-ttu-id="2abac-110">若要规划你的租户实现，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2abac-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="2abac-111">了解订阅、许可证和 Azure Active Directory (Azure AD) 租户</span><span class="sxs-lookup"><span data-stu-id="2abac-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="2abac-112">了解如何使用第三方 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="2abac-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="2abac-113">Microsoft 365 管理中心中的访问安装指南</span><span class="sxs-lookup"><span data-stu-id="2abac-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="2abac-114">了解 Microsoft 365 租户与 Azure AD 服务集成的方式</span><span class="sxs-lookup"><span data-stu-id="2abac-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="2abac-115">规划客户端应用程序支持</span><span class="sxs-lookup"><span data-stu-id="2abac-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="2abac-116">确定如何使用混合新式身份验证</span><span class="sxs-lookup"><span data-stu-id="2abac-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="2abac-117">规划 Office 2007 和 Office 2010 升级</span><span class="sxs-lookup"><span data-stu-id="2abac-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="2abac-118">了解租户隔离</span><span class="sxs-lookup"><span data-stu-id="2abac-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="2abac-119">获取有关 Microsoft 365 服务保证的详细信息</span><span class="sxs-lookup"><span data-stu-id="2abac-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="2abac-120">部署</span><span class="sxs-lookup"><span data-stu-id="2abac-120">Deploy</span></span>

<span data-ttu-id="2abac-121">若要部署你的租户，请为你的组织 [添加 DNS 域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 。</span><span class="sxs-lookup"><span data-stu-id="2abac-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="2abac-122">具有多个地理位置的租户</span><span class="sxs-lookup"><span data-stu-id="2abac-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="2abac-123">利用 Microsoft 365 多地理位置，你的组织可将其 Microsoft 365 触及范围扩展到你的现有租户内的多个地理区域和/或国家或地区。</span><span class="sxs-lookup"><span data-stu-id="2abac-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="2abac-124">[开始](microsoft-365-multi-geo.md) 了解、规划、配置和管理 Microsoft 365 多地理位置。</span><span class="sxs-lookup"><span data-stu-id="2abac-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="2abac-125">移动租户的地理位置</span><span class="sxs-lookup"><span data-stu-id="2abac-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="2abac-126">Microsoft 继续为 Microsoft 365 服务 (信息) 打开新的数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="2abac-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="2abac-127">这些新数据中心信息添加容量和计算资源，以支持客户需求和使用情况增长。</span><span class="sxs-lookup"><span data-stu-id="2abac-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="2abac-128">此外，新的数据中心信息为核心客户数据提供了地理位置数据常驻。</span><span class="sxs-lookup"><span data-stu-id="2abac-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="2abac-129">通过将 [核心数据移动到新的 Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md)，了解并请求地区数据移动的入门知识。</span><span class="sxs-lookup"><span data-stu-id="2abac-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="2abac-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2abac-130">Next step</span></span>

<span data-ttu-id="2abac-131">使用 [订阅、许可证、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)启动租户规划。</span><span class="sxs-lookup"><span data-stu-id="2abac-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

