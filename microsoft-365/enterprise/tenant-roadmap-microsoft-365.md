---
title: Microsoft 365 租户路线图
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
description: 设置 Microsoft 365 租户的路线图。
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909450"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Microsoft 365 租户路线图

Microsoft 365 租户是分配给你的组织的一组服务。 通常，此租户与一个或多个公共 DNS 域名相关联，并充当不同订阅以及分配给用户帐户的许可证的中心和独立容器。 有关详细信息，请参阅 Microsoft 云产品/服务订阅、许可证 [、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。

创建 Microsoft 365 租户时，将其分配给特定地理位置。 还可以拥有具有多个地理位置的租户，将租户从一个位置移动到另一个位置。

若要使租户为用户、组、许可证和云应用做好准备，必须仔细规划和执行租户配置。

## <a name="set-up-your-microsoft-365-tenant"></a>设置 Microsoft 365 租户

在确保网络针对内部部署和远程工作人员访问 Microsoft 365 进行了优化后，下一项重大任务是为 DNS 域名、公共服务以及支持安全用户登录的标识基础结构规划并配置 Microsoft 365 租户。

### <a name="plan"></a>计划

若要规划租户实施，请执行：

- [了解 Azure AD 租户中的订阅 (、许可证) Azure Active Directory](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [了解如何使用第三方 SSL 证书](plan-for-third-party-ssl-certificates.md)
- [了解 Microsoft 365 租户与 Azure AD 服务集成的方式](integrated-apps-and-azure-ads.md)
- [规划客户端应用支持](microsoft-365-client-support-certificate-based-authentication.md)
- [确定如何使用混合新式验证](hybrid-modern-auth-overview.md)
- [规划 Office 2007 和 Office 2010 升级](plan-upgrade-previous-versions-office.md)
- [了解租户隔离](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>部署

部署租户： 

- 为 [组织添加 DNS](../admin/setup/add-domain.md) 域。
- 使用 [Microsoft 365 管理中心中的设置指南](setup-guides-for-microsoft-365.md)。
- 构建标识[基础结构](identity-roadmap-microsoft-365.md)[，并保护用户登录](microsoft-365-secure-sign-in.md)。

### <a name="move-a-tenants-geographic-locations"></a>移动租户的地理位置

Microsoft 继续打开新的数据中心地理位置， (Microsoft 365) 地理位置。 这些新数据中心地理位置增加了容量和计算资源，以支持客户需求和使用情况增长。 此外，新的数据中心地理位置为核心客户数据提供地理位置内数据驻留。

有关详细信息，请参阅将 [核心数据移动到新的 Microsoft 365 数据中心地理位置](moving-data-to-new-datacenter-geos.md)。


## <a name="deploy-microsoft-365-multi-geo"></a>部署 Microsoft 365 多地理位置

利用 Microsoft 365 多地理位置，你的组织可将其 Microsoft 365 触及范围扩展到你的现有租户内的多个地理区域和/或国家或地区。

有关详细信息，请参阅 [Microsoft 365 多地理位置](microsoft-365-multi-geo.md)。

## <a name="manage-multiple-microsoft-365-tenants"></a>管理多个 Microsoft 365 租户 

尽管对于组织组织来说，拥有一个租户是理想选择，但你可能是拥有多个租户的许多组织之一。 原因可能包括合并和收购、您希望管理隔离，或者您具有分散的 IT。

如果你有多个 Microsoft 365 租户，请参阅以下文章，详细了解：

- [租户间协作](microsoft-365-inter-tenant-collaboration.md)
- [交叉租户邮箱迁移](cross-tenant-mailbox-migration.md)
- [租户到租户迁移](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>后续步骤

使用订阅、许可证、 [帐户和租户开始租户规划](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。