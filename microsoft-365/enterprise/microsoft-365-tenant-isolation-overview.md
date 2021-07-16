---
title: 租户隔离Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文汇总了 Microsoft 如何在云服务（如 Microsoft 365）中强制执行租户Microsoft 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b52d936bb00ac0adef0baf428cbc5f9a8f8aba49
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464061"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="2a219-103">租户隔离Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2a219-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="2a219-104">云计算的主要好处之一是同时跨多个客户共享、通用的基础结构的概念，这导致规模下降。</span><span class="sxs-lookup"><span data-stu-id="2a219-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="2a219-105">此概念称为 *"多租户"。*</span><span class="sxs-lookup"><span data-stu-id="2a219-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="2a219-106">Microsoft 持续致力于确保云服务的多租户体系结构支持企业级安全性、机密性、隐私性、完整性和可用性标准。</span><span class="sxs-lookup"><span data-stu-id="2a219-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="2a219-107">根据从可信赖计算和安全开发生命周期中[](https://www.microsoft.com/trust-center)收集的重要投资与[](https://www.microsoft.com/securityengineering/sdl/)经验，Microsoft 云服务的设计假定所有租户都可能对所有其他租户具有危害，并且我们实施了安全措施，以防止一个租户的操作影响另一个租户的安全或服务，或访问另一个租户的内容。</span><span class="sxs-lookup"><span data-stu-id="2a219-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="2a219-108">在多租户环境中维护租户隔离的两个主要目标是：</span><span class="sxs-lookup"><span data-stu-id="2a219-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="2a219-109">防止跨租户泄露客户内容或未经授权访问客户内容;和</span><span class="sxs-lookup"><span data-stu-id="2a219-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="2a219-110">防止一个租户的操作对另一个租户的服务造成负面影响</span><span class="sxs-lookup"><span data-stu-id="2a219-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="2a219-111">在整个 Microsoft 365 中实施了多种形式的保护，以防止客户危害 Microsoft 365 服务或应用程序，或获取对其他租户或 Microsoft 365 系统本身信息的未经授权的访问，包括：</span><span class="sxs-lookup"><span data-stu-id="2a219-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="2a219-112">通过基于授权和基于角色的访问控制Microsoft 365租户中的客户内容Azure Active Directory逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="2a219-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="2a219-113">SharePointOnline 在存储级别提供数据隔离机制。</span><span class="sxs-lookup"><span data-stu-id="2a219-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="2a219-114">Microsoft 使用严格的物理安全、背景屏蔽和多层加密策略来保护客户内容的机密性和完整性。</span><span class="sxs-lookup"><span data-stu-id="2a219-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="2a219-115">数据中心Microsoft 365均具有生物识别访问控制，大多数要求使用打印的指纹才能获得物理访问权限。</span><span class="sxs-lookup"><span data-stu-id="2a219-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="2a219-116">此外，作为招聘过程的一部分，所有美国 Microsoft 员工都需要成功完成标准背景检查。</span><span class="sxs-lookup"><span data-stu-id="2a219-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="2a219-117">有关在管理中用于管理访问的控件Microsoft 365，请参阅Microsoft 365[访问控制"。](/compliance/assurance/assurance-administrative-access-controls-overview)</span><span class="sxs-lookup"><span data-stu-id="2a219-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).</span></span>
- <span data-ttu-id="2a219-118">Microsoft 365使用对静态和传输中的客户内容进行加密的服务器端技术，包括 BitLocker、每个文件加密、传输层安全性 (TLS) 和 Internet 协议安全性 (IPsec) 。</span><span class="sxs-lookup"><span data-stu-id="2a219-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="2a219-119">有关加密中加密的特定Microsoft 365，请参阅数据[加密技术Microsoft 365。](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2a219-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="2a219-120">同时，上面列出的保护提供了强大的逻辑隔离控件，提供与单独由物理隔离提供的威胁保护和缓解等效。</span><span class="sxs-lookup"><span data-stu-id="2a219-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="2a219-121">相关链接</span><span class="sxs-lookup"><span data-stu-id="2a219-121">Related Links</span></span>

- [<span data-ttu-id="2a219-122">Azure Active Directory 中的隔离和访问控制</span><span class="sxs-lookup"><span data-stu-id="2a219-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="2a219-123">Office Graph 和 Delve 中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="2a219-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="2a219-124">Microsoft 365 搜索中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="2a219-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="2a219-125">资源限制</span><span class="sxs-lookup"><span data-stu-id="2a219-125">Resource Limits</span></span>](/compliance/assurance/assurance-resource-limits)
- [<span data-ttu-id="2a219-126">监视和测试租户边界</span><span class="sxs-lookup"><span data-stu-id="2a219-126">Monitoring and Testing Tenant Boundaries</span></span>](/compliance/assurance/assurance-monitoring-and-testing)
- [<span data-ttu-id="2a219-127">Microsoft 365 中的隔离和访问控制</span><span class="sxs-lookup"><span data-stu-id="2a219-127">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)