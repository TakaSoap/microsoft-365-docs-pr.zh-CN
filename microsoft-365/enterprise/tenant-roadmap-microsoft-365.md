---
title: 租户的租户Microsoft 365
f1.keywords:
  - NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
  - M365-subscription-management
  - m365initiative-coredeploy
ms.custom: it-pro
description: 设置租户的Microsoft 365。
---

# <a name="tenant-roadmap-for-microsoft-365"></a>租户的租户Microsoft 365

你的Microsoft 365租户是分配给你的组织的一组服务。 通常，此租户与一个或多个公共 DNS 域名相关联，并充当不同订阅以及分配给用户帐户的许可证的中心和独立容器。 有关详细信息，请参阅 Microsoft 云产品/服务订阅、许可证 [、帐户和租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。

创建租户时Microsoft 365租户，将其分配给特定地理位置。 还可以拥有具有多个地理位置的租户，将租户从一个位置移动到另一个位置。

若要使租户为用户、组、许可证和云应用做好准备，必须仔细规划和执行租户配置。

## <a name="set-up-your-microsoft-365-tenant"></a>设置 Microsoft 365 租户

在确保针对内部部署和远程工作人员对 Microsoft 365 的访问进行了优化后，下一项重大任务是为 DNS 域名、公共服务以及支持安全用户登录的标识基础结构规划并配置 Microsoft 365 租户。

### <a name="plan"></a>计划

若要规划租户实施，请执行：

- [了解订阅、许可证和Azure Active Directory (Azure AD) 租户](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [了解如何使用第三方 SSL 证书](plan-for-third-party-ssl-certificates.md)
- [了解租户租户Microsoft 365集成的方式Azure AD服务](integrated-apps-and-azure-ads.md)
- [规划客户端应用支持](microsoft-365-client-support-certificate-based-authentication.md)
- [确定如何使用混合新式验证](hybrid-modern-auth-overview.md)
- [规划 Office 2007 和 Office 2010 升级](plan-upgrade-previous-versions-office.md)
- [了解租户隔离](/compliance/assurance/microsoft-365-isolation-controls)

### <a name="deploy"></a>部署

部署租户： 

- 为 [组织添加 DNS](../admin/setup/add-domain.md) 域。
- 使用[设置指南中的Microsoft 365 管理中心](setup-guides-for-microsoft-365.md)。
- 构建标识 [基础结构](deploy-identity-solution-overview.md)。

### <a name="move-a-tenants-geographic-locations"></a>移动租户的地理位置

Microsoft 继续打开新的数据中心地理位置 (地理位置) 服务Microsoft 365地理位置。 这些新数据中心地理位置增加了容量和计算资源，以支持客户需求和使用情况增长。 此外，新的数据中心地理位置为核心客户数据提供地理位置内数据驻留。

有关详细信息，请参阅将[核心数据移动到新的数据中心Microsoft 365地理位置](moving-data-to-new-datacenter-geos.md)。


## <a name="deploy-microsoft-365-multi-geo"></a>部署Microsoft 365多地理位置

利用 Microsoft 365 多地理位置，你的组织可将其 Microsoft 365 触及范围扩展到你的现有租户内的多个地理区域和/或国家或地区。

有关详细信息，请参阅 [Microsoft 365 多地理位置](microsoft-365-multi-geo.md)。

## <a name="manage-multiple-microsoft-365-tenants"></a>管理多个Microsoft 365租户 

尽管拥有单个租户进行组织组织是理想选择，但你可能是拥有多个租户的许多组织之一。 原因可能包括合并和收购、您希望管理隔离，或者您具有分散的 IT。

如果你有多个租户Microsoft 365，请参阅以下文章，详细了解：

- [租户间协作](microsoft-365-inter-tenant-collaboration.md)
- [交叉租户邮箱迁移](cross-tenant-mailbox-migration.md)
- [租户到租户迁移](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>后续步骤

使用订阅、许可证、帐户和租户 [开始租户规划](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)。