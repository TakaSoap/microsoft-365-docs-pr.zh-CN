---
title: 适用于 Microsoft 365 的租户路线图
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
description: 设置适用于 Microsoft 365 的租户的路线图。
ms.openlocfilehash: 038d9b0d94b84d184f0d9d9b250d0ee4d2c19de9
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753962"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>适用于 Microsoft 365 的租户路线图

你的 Microsoft 365 租户是分配给你的组织的一组服务。 通常情况下，此租户与一个或多个公共 DNS 域名相关联，并充当不同订阅的中央和独立容器，并可作为分配给用户帐户的这些容器中的许可证。 有关详细信息，请参阅 [Microsoft 云产品服务的订阅、许可证、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。

创建 Microsoft 365 租户时，可将其分配到特定的地理位置。 您还可以拥有多个地理位置的租户，并将您的租户从一个位置移动到另一个位置。

若要让你的租户为用户、组、许可证和云应用准备就绪，请务必仔细规划和执行你的租户配置。

## <a name="set-up-your-microsoft-365-tenant"></a>设置你的 Microsoft 365 租户

在确保网络已针对本地和远程工作人员访问 Microsoft 365 的优化之后，下一个大型任务将进行规划，然后为 Microsoft 365 租户配置 DNS 域名、常见服务以及支持安全用户登录的身份基础结构。

### <a name="plan"></a>套餐

若要规划你的租户实现，请执行以下操作：

- [了解订阅、许可证和 Azure Active Directory (Azure AD) 租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [了解如何使用第三方 SSL 证书](plan-for-third-party-ssl-certificates.md)
- [了解 Microsoft 365 租户与 Azure AD 服务集成的方式](integrated-apps-and-azure-ads.md)
- [规划客户端应用程序支持](microsoft-365-client-support-certificate-based-authentication.md)
- [确定如何使用混合新式身份验证](hybrid-modern-auth-overview.md)
- [规划 Office 2007 和 Office 2010 升级](plan-upgrade-previous-versions-office.md)
- [了解租户隔离](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>部署

若要部署租户，请执行以下操作： 

- 为您的组织添加 [DNS 域](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) 。
- 使用 [Microsoft 365 管理中心中的安装指南](setup-guides-for-microsoft-365.md)。
- 构建你的 [身份基础结构](identity-roadmap-microsoft-365.md) 并 [保护你的用户登录](microsoft-365-secure-sign-in.md)。

### <a name="move-a-tenants-geographic-locations"></a>移动租户的地理位置

Microsoft 继续为 Microsoft 365 服务 (信息) 打开新的数据中心地理位置。 这些新数据中心信息添加容量和计算资源，以支持客户需求和使用情况增长。 此外，新的数据中心信息为核心客户数据提供了地理位置数据常驻。

有关详细信息，请参阅 [将 core Data 移动到新的 Microsoft 365 datacenter 信息](moving-data-to-new-datacenter-geos.md)。


## <a name="deploy-microsoft-365-multi-geo"></a>部署 Microsoft 365 多地理位置

利用 Microsoft 365 多地理位置，你的组织可将其 Microsoft 365 触及范围扩展到你的现有租户内的多个地理区域和/或国家或地区。

有关详细信息，请参阅 [Microsoft 365 多地理](microsoft-365-multi-geo.md)位置。

## <a name="manage-multiple-microsoft-365-tenant"></a>管理多个 Microsoft 365 租户 

尽管为您的组织使用一个租户是理想的，但您可以是具有多个租户的多个组织之一。 原因可能包括合并和收购、需要管理隔离或分散 IT。

如果你有多个 Microsoft 365 租户，请参阅以下文章，了解详细信息：

- [租户间协作](microsoft-365-inter-tenant-collaboration.md)
- [交叉租户邮箱迁移](cross-tenant-mailbox-migration.md)
- [租户到租户迁移](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>后续步骤

使用 [订阅、许可证、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)启动租户规划。
