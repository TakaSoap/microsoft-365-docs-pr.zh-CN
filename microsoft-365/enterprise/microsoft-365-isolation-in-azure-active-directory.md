---
title: Microsoft 365隔离和访问控制Azure Active Directory
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
description: 本文介绍隔离和访问控制如何工作，使多个租户的数据相互隔离Azure Active Directory。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332408"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a><span data-ttu-id="d5dc5-103">Microsoft 365隔离和访问控制Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d5dc5-103">Microsoft 365 Isolation and Access Control in Azure Active Directory</span></span>

<span data-ttu-id="d5dc5-104">Azure Active Directory (Azure AD) 旨在通过逻辑数据隔离以高度安全的方式托管多个租户。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-104">Azure Active Directory (Azure AD) was designed to host multiple tenants in a highly secure way through logical data isolation.</span></span> <span data-ttu-id="d5dc5-105">对 Azure AD 的访问受授权层限制。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-105">Access to Azure AD is gated by an authorization layer.</span></span> <span data-ttu-id="d5dc5-106">Azure AD 隔离使用租户容器作为安全边界的客户，以保护客户的内容，以便共同租户无法访问或泄露内容。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-106">Azure AD isolates customers using tenant containers as security boundaries to safeguard a customer's content so that the content cannot be accessed or compromised by co-tenants.</span></span> <span data-ttu-id="d5dc5-107">Azure AD 的授权层执行三项检查：</span><span class="sxs-lookup"><span data-stu-id="d5dc5-107">Three checks are performed by Azure AD's authorization layer:</span></span>

- <span data-ttu-id="d5dc5-108">主体是否已启用以访问 Azure AD 租户？</span><span class="sxs-lookup"><span data-stu-id="d5dc5-108">Is the principal enabled for access to Azure AD tenant?</span></span>
- <span data-ttu-id="d5dc5-109">是否已启用主体以访问此租户中的数据？</span><span class="sxs-lookup"><span data-stu-id="d5dc5-109">Is the principal enabled for access to data in this tenant?</span></span>
- <span data-ttu-id="d5dc5-110">此租户中主体的角色是否经过授权，可以请求数据访问类型？</span><span class="sxs-lookup"><span data-stu-id="d5dc5-110">Is the principal's role in this tenant authorized for the type of data access requested?</span></span>

<span data-ttu-id="d5dc5-111">没有适当的身份验证和令牌或证书，任何应用程序、用户、服务器或服务都无法访问 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-111">No application, user, server, or service can access Azure AD without the proper authentication and token or certificate.</span></span> <span data-ttu-id="d5dc5-112">如果请求未附带正确的凭据，则拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-112">Requests are rejected if they are not accompanied by proper credentials.</span></span>

<span data-ttu-id="d5dc5-113">实际上，Azure AD 将每个租户托管在其自己的受保护容器中，并且具有租户单独拥有和管理的容器内的策略和权限。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-113">Effectively, Azure AD hosts each tenant in its own protected container, with policies and permissions to and within the container solely owned and managed by the tenant.</span></span>
 
![Azure 容器](../media/office-365-isolation-azure-container.png)

<span data-ttu-id="d5dc5-115">租户容器的概念在所有层（从门户到永久性存储）的目录服务中都根深有理。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-115">The concept of tenant containers is deeply ingrained in the directory service at all layers, from portals all the way to persistent storage.</span></span> <span data-ttu-id="d5dc5-116">即使多个 Azure AD 租户元数据存储在同一物理磁盘上，容器之间也没有任何关系，目录服务定义的其他内容又由租户管理员指示。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-116">Even when multiple Azure AD tenant metadata is stored on the same physical disk, there is no relationship between the containers other than what is defined by the directory service, which in turn is dictated by the tenant administrator.</span></span> <span data-ttu-id="d5dc5-117">在未通过授权层之前，无法从任何请求的应用程序或服务直接连接到 Azure AD 存储。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-117">There can be no direct connections to Azure AD storage from any requesting application or service without first going through the authorization layer.</span></span>

<span data-ttu-id="d5dc5-118">在下面的示例中，Contoso 和 Fabrikam 都有单独的专用容器，即使这些容器可能共享某些相同的基础结构（如服务器和存储），它们仍然彼此独立，并受到授权和访问控制层限制。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-118">In the example below, Contoso and Fabrikam both have separate, dedicated containers, and even though those containers may share some of the same underlying infrastructure, such as servers and storage, they remain separate and isolated from each other, and gated by layers of authorization and access control.</span></span>
 
![Azure 专用容器](../media/office-365-isolation-azure-dedicated-containers.png)

<span data-ttu-id="d5dc5-120">此外，Azure AD 中无法执行任何应用程序组件，并且一个租户无法强制破坏另一个租户的完整性、访问另一个租户的加密密钥或从服务器读取原始数据。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-120">In addition, there are no application components that can execute from within Azure AD, and it is not possible for one tenant to forcibly breach the integrity of another tenant, access encryption keys of another tenant, or read raw data from the server.</span></span>

<span data-ttu-id="d5dc5-121">默认情况下，Azure AD 禁止由其他租户中的标识发出的所有操作。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-121">By default, Azure AD disallows all operations issued by identities in other tenants.</span></span> <span data-ttu-id="d5dc5-122">通过基于声明的访问控制，每个租户在逻辑上隔离在 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-122">Each tenant is logically isolated within Azure AD through claims-based access controls.</span></span> <span data-ttu-id="d5dc5-123">目录数据的读取和写入范围为租户容器，由内部抽象层和基于角色的访问控制 (RBAC) 层进行限制，这两个层共同强制租户作为安全边界。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-123">Reads and writes of directory data are scoped to tenant containers, and gated by an internal abstraction layer and a role-based access control (RBAC) layer, which together enforce the tenant as the security boundary.</span></span> <span data-ttu-id="d5dc5-124">每个目录数据访问请求都由这些层进行处理，并且每个访问请求Microsoft 365上述逻辑进行控制。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-124">Every directory data access request is processed by these layers and every access request in Microsoft 365 is policed by the logic above.</span></span>

<span data-ttu-id="d5dc5-125">Azure AD 具有北美、美国政府、欧盟、德国和万维网分区。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-125">Azure AD has North America, U.S. Government, European Union, Germany, and World Wide partitions.</span></span> <span data-ttu-id="d5dc5-126">租户存在于单个分区中，而分区可以包含多个租户。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-126">A tenant exists in a single partition, and partitions can contain multiple tenants.</span></span> <span data-ttu-id="d5dc5-127">分区信息从用户抽象化。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-127">Partition information is abstracted away from users.</span></span> <span data-ttu-id="d5dc5-128">给定分区 (包括其中所有租户) 复制到多个数据中心。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-128">A given partition (including all the tenants within it) is replicated to multiple datacenters.</span></span> <span data-ttu-id="d5dc5-129">租户的分区基于租户属性 (例如，国家/地区代码) 。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-129">The partition for a tenant is chosen based on properties of the tenant (e.g., the country code).</span></span> <span data-ttu-id="d5dc5-130">每个分区中的密钥和其他敏感信息都使用专用密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-130">Secrets and other sensitive information in each partition is encrypted with a dedicated key.</span></span> <span data-ttu-id="d5dc5-131">密钥会在新建分区时自动生成。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-131">The keys are generated automatically when a new partition is created.</span></span>

<span data-ttu-id="d5dc5-132">Azure AD 系统功能是每个用户会话的唯一实例。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-132">Azure AD system functionalities are a unique instance to each user session.</span></span> <span data-ttu-id="d5dc5-133">此外，Azure AD 使用加密技术在网络级别隔离共享系统资源，以防止未经授权的和意外的信息传输。</span><span class="sxs-lookup"><span data-stu-id="d5dc5-133">In addition, Azure AD uses encryption technologies to provide isolation of shared system resources at the network level to prevent unauthorized and unintended transfer of information.</span></span>
