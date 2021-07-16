---
title: Microsoft 365 隔离控制
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
description: 了解隔离控件在Microsoft 365中如何工作，从而允许服务根据需要进行互操作或保持自治。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464062"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="a3de7-103">Microsoft 365 隔离控制</span><span class="sxs-lookup"><span data-stu-id="a3de7-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="a3de7-104">Microsoft 持续致力于确保网站的多租户Microsoft 365支持企业级安全性、机密性、隐私、完整性、本地、国际和可用性[标准](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)。</span><span class="sxs-lookup"><span data-stu-id="a3de7-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="a3de7-105">Microsoft 提供的服务规模和范围使得管理具有大量人工交互Microsoft 365非常困难且非经济。</span><span class="sxs-lookup"><span data-stu-id="a3de7-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="a3de7-106">Microsoft 365服务通过多个全球分布的数据中心提供，每个数据中心都通过几个需要人员触摸或客户内容访问的操作实现高度自动化。</span><span class="sxs-lookup"><span data-stu-id="a3de7-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="a3de7-107">我们的员工使用自动化工具和高度安全的远程访问支持这些服务和数据中心。</span><span class="sxs-lookup"><span data-stu-id="a3de7-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="a3de7-108">Microsoft 365由多个服务组成，这些服务提供重要的业务功能并有助于实现整个Microsoft 365体验。</span><span class="sxs-lookup"><span data-stu-id="a3de7-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="a3de7-109">其中每个服务都是独立的，旨在相互集成。</span><span class="sxs-lookup"><span data-stu-id="a3de7-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="a3de7-110">Microsoft 365设计有以下原则：</span><span class="sxs-lookup"><span data-stu-id="a3de7-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="a3de7-111">**[面向服务的体系结构](/previous-versions/aa480021(v=msdn.10))：** 以提供明确定义的业务功能的可互操作服务的形式设计和开发软件。</span><span class="sxs-lookup"><span data-stu-id="a3de7-111">**[Service-Oriented Architecture](/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="a3de7-112">**[操作](https://www.microsoft.com/download/details.aspx?id=40872)** 安全保证 ：一个框架，包含通过 [Microsoft](https://www.microsoft.com/sdl/default.aspx)特有的各种功能获得的知识，包括 Microsoft 安全开发生命周期 [、Microsoft 安全](https://technet.microsoft.com/library/dn440717.aspx)响应中心，以及网络安全威胁形势的深入感知。</span><span class="sxs-lookup"><span data-stu-id="a3de7-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="a3de7-113">Microsoft 365服务相互交互，但设计和实现，以便它们可以作为自治服务进行部署和运行，相互独立。</span><span class="sxs-lookup"><span data-stu-id="a3de7-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="a3de7-114">Microsoft 隔离组织的职责Microsoft 365，以减少未经授权或无意修改或滥用组织资产的机会。</span><span class="sxs-lookup"><span data-stu-id="a3de7-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="a3de7-115">Microsoft 365团队将角色定义为全面的基于角色的访问控制机制的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3de7-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="a3de7-116">客户内容隔离</span><span class="sxs-lookup"><span data-stu-id="a3de7-116">Customer content isolation</span></span>

<span data-ttu-id="a3de7-117">租户中所有客户内容都与其他租户以及管理租户中使用的操作和系统数据Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a3de7-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="a3de7-118">在整个过程中实施多种形式的保护Microsoft 365最大程度地降低任何服务或应用程序Microsoft 365的风险。</span><span class="sxs-lookup"><span data-stu-id="a3de7-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="a3de7-119">多形式的保护还可以防止未经授权访问租户或Microsoft 365信息。</span><span class="sxs-lookup"><span data-stu-id="a3de7-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="a3de7-120">有关 Microsoft 如何在租户内实现租户数据的逻辑隔离Microsoft 365，请参阅租户隔离[Microsoft 365。](microsoft-365-tenant-isolation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a3de7-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>