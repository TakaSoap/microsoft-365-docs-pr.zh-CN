---
title: 步骤 1. 适用于Microsoft 365租户的租户
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 部署和管理单个或Microsoft 365租户，并提供了多地理位置和移动位置的选项。
ms.openlocfilehash: 305d7683413d5682c0dddda418e87de0a0a682b7
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524113"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>步骤 1. 适用于Microsoft 365租户的租户

你的第一个租户决策之一是拥有多少租户。 每个Microsoft 365租户都是唯一的，并且独立于所有其他Microsoft 365租户。 其相应的Azure AD租户也不同、唯一，并且独立于所有其他Microsoft 365租户。

## <a name="single-tenant"></a>单个租户
拥有一个租户可简化组织使用租户Microsoft 365。 单个租户意味着单个 Azure AD租户具有一组帐户、组和策略。 可以通过此中央标识提供程序在组织中完成资源的权限和共享。

单个租户为用户提供功能最丰富且简化的协作和工作效率体验。

下面的示例展示了默认位置和Azure AD租户Microsoft 365租户。

![具有Microsoft 365租户的单个Azure AD租户。](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>多个租户

组织可能有多个租户有很多原因：

- 管理隔离
- 分散的 IT
- 历史决策
- 合并、收购或资产重组
- 为大型组织明确区分品牌
- 预生产、测试或沙盒租户

下面是在同一默认数据中心地理位置中具有两个租户 (租户 A 和租户 B) 的示例。 每个租户作为单独的Azure AD租户。

![具有Microsoft 365租户的多个Azure AD租户。](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

当有多个租户时，在管理租户和为用户提供服务时，存在一些限制和其他注意事项。

### <a name="inter-tenant-collaboration"></a>租户间协作

如果希望用户以安全的方式在不同 Microsoft 365 租户之间更有效地协作，租户间协作选项包括使用文件和对话的中心位置、共享日历、使用 IM、用于通信的音频/视频呼叫，以及保护对资源和应用程序的访问。

有关详细信息，请参阅Microsoft 365[租户间协作](../enterprise/microsoft-365-inter-tenant-collaboration.md)。

### <a name="cross-tenant-mailbox-migration-preview"></a>跨租户邮箱迁移 (预览) 

在预览版) 中跨租户邮箱迁移 (之前，在租户之间移动 Exchange Online 邮箱时，您必须将用户邮箱从当前租户 (源租户) 完全离开到本地，然后将它们载入到新租户 (目标租户) 。 借助新的跨租户邮箱迁移功能，源租户和目标租户中的租户管理员可以在本地系统中以最少的基础结构依赖项在租户之间移动邮箱。 这将无需离开和载入邮箱。

下面是跨租户邮箱迁移前的两个示例租户及其邮箱。

![多个Microsoft 365租户及其邮箱。](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

在此图中，两个单独的租户具有其自己的域和一组Exchange邮箱。

下面是跨租户邮箱 (租户 A) 目标租户。

![跨租户邮箱迁移后的目标租户。](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

在此图中，单个租户具有域和两组Exchange邮箱。

有关详细信息，请参阅跨 [租户邮箱迁移](../enterprise/cross-tenant-mailbox-migration.md)。

### <a name="tenant-to-tenant-migrations"></a>租户到租户迁移

对于合并、收购、资产重组和其他方案，有几种体系结构方法可能会导致你将现有 Microsoft 365 租户迁移到新租户。 

有关详细指导，请参阅[Microsoft 365租户到租户的迁移](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)。

## <a name="multi-geo-for-a-tenant"></a>租户的多地理位置

借助 Microsoft 365 多地理位置，可以在选择满足数据驻留要求的其他数据中心地理位置中预配和存储静止数据，同时向工作人员解锁新式生产力体验的全球推广。

在多地理位置环境中，Microsoft 365租户包含默认或中央位置（最初创建 Microsoft 365 订阅）以及一个或多个附属位置。 在多地理位置租户中，有关地理位置、组和用户信息的信息是在全局租户租户中Azure AD的信息。 由于租户信息是集中掌握的，并同步到每个地理位置，因此公司中涉及任何人的协作体验将跨位置共享。

下面是一个组织的示例，该组织的默认位置在欧洲，而北美是附属位置。 这两个位置共享单个Azure AD租户的全局Microsoft 365租户。

![多地理位置租户Microsoft 365示例。](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

有关详细信息，请参阅 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>将核心数据移动到新的数据中心地理位置

Microsoft 继续打开新的数据中心地理位置，Microsoft 365服务。 这些新数据中心地理位置可增加容量和计算资源，以支持我们的持续客户需求和使用增长。 此外，新的数据中心地理位置为核心客户数据提供地理位置内数据驻留。

尽管打开新的数据中心地理位置不会影响你和存储在现有数据中心地理位置中的核心数据，但 Microsoft 允许你请求将组织的核心客户数据在静止之后提前迁移到新的数据中心地理位置。

下面是一个示例，Microsoft 365 租户从欧盟 (欧盟) 数据中心地理位置移动到位于英国 (英国数据中心) 。

![在数据中心地理位置Microsoft 365租户的示例。](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

有关详细信息，请参阅将[核心数据移动到新的数据中心Microsoft 365地理位置](../enterprise/moving-data-to-new-datacenter-geos.md)。

## <a name="products-and-licenses-for-a-tenant"></a>租户的产品和许可证

在Microsoft 365第一个产品（如产品）时，将创建你的 Microsoft 365 E3。 与产品一起是许可证，按月或按年收费。 然后，管理员直接或通过组成员身份将一个产品中的可用许可证分配给用户帐户。 根据组织的业务需求，您可能有一组产品，每个产品都有自己的许可证池。 

确定产品集和每个产品的许可证数量需要进行一些规划，以：

- 确保你有足够的许可证用于需要高级功能的用户帐户。
- 根据组织员工的变化，防止许可证过多或拥有过多未分配许可证。


## <a name="results-of-step-1"></a>步骤 1 的结果

对于Microsoft 365租户，你已确定：

- 你拥有或需要多少个租户。
- 对于每个租户，必须购买哪些产品和许可证。
- 租户是否需要多地理位置，以满足数据驻留要求。
- 是否需要设置租户间协作。
- 是否需要将一个租户迁移到另一个租户。
- 是否需要将核心数据从一个数据中心地理位置移动到新数据中心地理位置。

下面是新租户的示例。

![新租户的示例。](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

在此图中，租户具有：

- 与数据中心地理位置Microsoft 365位置。
- 一组产品和许可证。
- 云生产力应用集，其中一些特定于产品。
- 包含Azure AD帐户和初始 DNS 域名的租户。

当我们完成此解决方案的其他步骤时，我们将构建此图。

## <a name="ongoing-maintenance-for-tenants"></a>租户持续维护

您可能需要持续：

- 添加新租户。
- 将新产品添加到具有初始许可证数量的租户。
- 更改租户中产品的许可证集，以针对员工需求的变化进行调整。
- 将核心数据从租户移动到新的数据中心地理位置。
- 添加多地理位置数据驻留要求。
- 设置租户间协作。

## <a name="next-step"></a>后续步骤

[![步骤 2.优化租户以访问网络。](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

继续使用[网络](tenant-management-networking.md)，为工作人员提供最佳网络，Microsoft 365云服务。
