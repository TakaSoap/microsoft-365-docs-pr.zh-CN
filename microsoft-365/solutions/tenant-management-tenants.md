---
title: 步骤 1. Microsoft 365 企业版租户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 部署和管理单个或多个 Microsoft 365 租户，具有多地理位置和移动位置的选项。
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406380"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>步骤 1. Microsoft 365 企业版租户

你的第一个租户决策之一是拥有多少租户。 每个 Microsoft 365 租户都是不同、唯一的，并且独立于所有其他 Microsoft 365 租户。 它对应的 Azure AD 租户也不同、唯一，并且独立于所有其他 Microsoft 365 租户。

## <a name="single-tenant"></a>单个租户
拥有一个租户可简化组织对 Microsoft 365 的使用的许多方面。 单个租户意味着单个 Azure AD 租户具有一组帐户、组和策略。 可以通过此中央标识提供程序在整个组织中完成资源的权限和共享。

单个租户为用户提供功能最丰富且简化的协作和工作效率体验。

下面是显示 Microsoft 365 租户的默认位置和 Azure AD 租户的示例。

![具有 Azure AD 租户的单个 Microsoft 365 租户](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>多个租户

组织可能有多个租户的原因有很多：

- 管理隔离
- 分散式 IT
- 历史决策
- 合并、收购或资产重组
- 为大型组织明确区分品牌
- 预生产、测试或沙盒租户

下面是在同一默认数据中心地理位置中具有两个租户 (租户 A 和租户 B) 的示例。 每个租户作为单独的 Azure AD 租户。

![具有自己的 Azure AD 租户的多个 Microsoft 365 租户](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

当有多个租户时，在管理租户和为用户提供服务时，存在一些限制和其他注意事项。

### <a name="inter-tenant-collaboration"></a>租户间协作

如果希望用户以安全的方式在不同 Microsoft 365 租户之间更有效地协作，租户间协作选项包括使用文件和对话的中心位置、共享日历、使用 IM、音频/视频呼叫进行通信，以及保护对资源和应用程序的访问。

有关详细信息，请参阅 [Microsoft 365 租户间协作](../enterprise/microsoft-365-inter-tenant-collaboration.md)。

### <a name="cross-tenant-mailbox-migration-preview"></a>跨租户邮箱迁移 (预览) 

在预览版) 中跨租户邮箱迁移 (之前，在租户之间移动 Exchange Online 邮箱时，您必须将用户邮箱从当前租户 (源租户) 完全注销到本地，然后将它们载入到新租户 (目标租户) 。 借助新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在租户之间移动邮箱，且在本地系统中基础结构依赖关系最小。 这无需注销和载入邮箱。

下面是跨租户邮箱迁移前的两个示例租户及其邮箱。

![多个 Microsoft 365 租户及其邮箱](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

在此图中，两个单独的租户具有其自己的域和一组 Exchange 邮箱。

下面是跨租户邮箱 (租户 A) 的目标租户。

![跨租户邮箱迁移后的目标租户](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

在此图中，单个租户具有域和 Exchange 邮箱集。

有关详细信息，请参阅跨 [租户邮箱迁移](../enterprise/cross-tenant-mailbox-migration.md)。

### <a name="tenant-to-tenant-migrations"></a>租户到租户迁移

对于合并、收购、资产重组和其他方案，有几种体系结构方法可能会导致你将现有 Microsoft 365 租户迁移到新租户。 

有关详细指导，请参阅 [Microsoft 365 租户到租户迁移](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)。

## <a name="multi-geo-for-a-tenant"></a>租户的多地理位置

使用 Microsoft 365 多地理位置，可以在选择满足数据驻留要求的其他数据中心地理位置中设置和存储静止数据，同时为工作人员解锁新式生产力体验的全球推出。

在多地理位置环境中，Microsoft 365 租户由最初创建 Microsoft 365 订阅的默认或中心位置以及一个或多个附属位置组成。 在多地理位置租户中，有关地理位置、组和用户信息的信息在全局 Azure AD 租户中掌握。 由于租户信息是集中掌握并同步到每个地理位置的，因此公司中涉及任何人的协作体验将跨位置共享。

下面是一个组织示例，该组织的默认位置位于欧洲，而附属位置位于北美。 这两个位置共享单个 Microsoft 365 租户的同一个全局 Azure AD 租户。

![多地理位置 Microsoft 365 租户示例](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

有关详细信息，请参阅 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>将核心数据移动到新的数据中心地理位置

Microsoft 继续为 Microsoft 365 服务打开新的数据中心地理位置。 这些新数据中心地理位置增加了容量和计算资源，以支持我们的持续客户需求和使用增长。 此外，新的数据中心地理位置为核心客户数据提供地理位置内数据驻留。

尽管打开新的数据中心地理位置不会影响你和存储在现有数据中心地理位置中的核心数据，但 Microsoft 允许你请求将组织的核心客户数据在静止时提前迁移到新的数据中心地理位置。

下面是一个示例，其中 Microsoft 365 租户从欧盟 (EU) 数据中心地理位置移动到位于英国 (数据中心) 。

![在数据中心地理位置之间移动 Microsoft 365 租户的示例](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

有关详细信息，请参阅将 [核心数据移动到新的 Microsoft 365 数据中心地理位置](../enterprise/moving-data-to-new-datacenter-geos.md)。

## <a name="products-and-licenses-for-a-tenant"></a>租户的产品和许可证

购买第一个产品（如 Microsoft 365 E3）时，将创建 Microsoft 365 租户。 除了产品外，还有许可证，按月或按年收费。 然后，管理员直接或通过组成员身份将一个产品中的可用许可证分配给用户帐户。 根据组织的业务需求，您可能有一组产品，每个产品都有自己的许可证池。 

确定产品集和每个产品的许可证数量需要进行一些规划，以：

- 确保您具有足够的许可证用于需要高级功能的用户帐户。
- 根据组织人员配置的变化，阻止你使用过多的许可证或拥有过多的未分配许可证。


## <a name="results-of-step-1"></a>步骤 1 的结果

对于 Microsoft 365 企业版租户，已确定：

- 你拥有或需要多少个租户。
- 对于每个租户，必须购买哪些产品和许可证。
- 租户是否需要为多地理位置，以满足数据驻留要求。
- 是否需要设置租户间协作。
- 是否需要将一个租户迁移到另一个租户。
- 是否需要将核心数据从一个数据中心地理位置移动到新数据中心地理位置。

下面是新租户的示例。

![新租户示例](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

在此图中，租户具有：

- 与 Microsoft 365 数据中心地理位置对应的默认位置。
- 一组产品和许可证。
- 云生产力应用集，其中一些特定于产品。
- 包含全局管理员帐户和初始 DNS 域名的 Azure AD 租户。

在浏览此解决方案的其他步骤时，我们将生成此图。

## <a name="ongoing-maintenance-for-tenants"></a>租户持续维护

你可能需要持续：

- 添加新租户。
- 将新产品添加到具有初始许可证数量的租户。
- 更改租户中产品的许可证集，以根据员工需求的变化进行调整。
- 将核心数据从租户移动到新的数据中心地理位置。
- 添加多地理位置数据驻留要求。
- 设置租户间协作。

## <a name="next-step"></a>后续步骤

[![步骤 2.优化租户以用于访问网络](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

继续使用 [网络](tenant-management-networking.md) ，从工作人员到 Microsoft 365 云服务提供最佳网络。
