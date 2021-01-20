---
title: Microsoft 365 企业版租户管理
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
ms.custom:
- Ent_Solutions
description: Microsoft 365 租户的规划、部署和持续操作概述。
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908481"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Microsoft 365 企业版租户管理

通过云计算创建组织数字化转型的路径需要一个稳固的基础，员工可以依靠此基础来提高工作效率、协作、性能、隐私、合规性和安全性。

正确配置 Microsoft 365 租户可提供此基础，让工作人员专注于完成工作，IT 部门专注于提供其他业务价值端到端解决方案。 

此解决方案将执行以下步骤中该基础的配置：

1. 确定租户
2. 优化网络
3. 同步标识并强制执行安全登录
4. 迁移 Windows 设备、Office 客户端和本地 Office 服务器和数据
5. 部署设备和应用管理

但是首先，让我们花些时间了解一下租户是什么，以及提供稳固基础的租户的外观。

## <a name="a-microsoft-365-tenant-defined"></a>定义的 Microsoft 365 租户

Microsoft 365 租户是 Microsoft 365 服务的专用实例，以及存储在特定默认位置（如欧洲或北美）中的组织数据。 为组织创建租户时指定此位置。 每个 Microsoft 365 租户各不相同、唯一，并且独立于所有其他 Microsoft 365 租户。 从 Microsoft 购买一个或多个产品（如 Microsoft 365 E3 或 E5）时，将创建一个 Microsoft 365 租户，并为每个租户创建一组许可证。

Microsoft 365 租户还包括 Azure Active Directory (Azure AD) 租户，这是用于用户帐户、组和其他对象的 Azure AD 的专用实例。 每个 Azure AD 租户都是不同、唯一的，并且独立于所有其他 Azure AD 租户。 虽然你的组织可以有多个可以使用 Azure 订阅设置的 Azure AD 租户，但 Microsoft 365 租户只能使用单个 Azure AD 租户，即创建租户时创建的租户。 

如以下示例所示：

![具有 Azure AD 租户的 Microsoft 365 租户示例](../media/tenant-management-overview/tenant-management-example-tenant.png)

*租户管理* 是 Microsoft 365 租户的规划、部署和持续操作。 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>设计良好且操作良好的租户的属性

除了租户的正确名称和位置之外，还需要规划、部署和管理其他元素，以确保云生产力应用（如 Microsoft Teams 和 Exchange Online）的用户体验有效、安全且 &mdash; &mdash; 性能高。

以下是元素：

- 你拥有一组正确的产品 (订阅和) 许可证。
  - 一组产品符合你的业务、IT 和安全需求。
  - 为工作人员提供足够数量的许可证以及人员配置的预期变化。
- 对于网络：
  - 已配置正确的 DNS 域名。
  - 对于企业网络，已针对现场工作人员优化了到 Microsoft 网络的网络流量。
  - 你已针对使用 VPN 客户端的远程工作者优化了网络流量。
- 已同步 Active Directory 域服务 (AD DS) 、组和其他对象。
  - 你的 Azure AD 租户帐户将映射到具有电子邮件地址的正确 DNS 域的 Exchange Online 邮箱。
  - 你的用户帐户已分配有来自正确购买的产品（如 Microsoft 365 E3 或 E5 (）的正确) 。
- 已配置强标识和访问管理。
  - 您需要使用无密码身份验证或多重身份验证在 MFA (安全) 。
  - 您具有条件访问策略，这些策略强制实施登录要求和针对更高安全级别的限制。
- 本地 Office 服务器及其数据已迁移到云应用或正在混合配置中使用。
- 你将使用内置于 Microsoft 365 的 Intune 或基本移动性和安全性进行设备管理。
  - 组织拥有的设备已注册和管理。
  - 管理个人设备的应用。

下面是具有所有这些元素的 Microsoft 365 租户的示例。

![Microsoft 365 租户示例](../media/tenant-management-overview/tenant-management-tenant-config.png)

在此图中，Microsoft 365 租户包括：

- Microsoft 365 E3 和 E5 的产品和许可证。
- Microsoft 365 生产力应用。
- 具有已注册的设备以及设备和应用程序策略的 Intune。
- 已同步用户帐户的 Azure AD 租户 (组和其他目录对象不会显示在) 、域和条件访问策略中。

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Microsoft 365 企业版租户功能

以下各节和表列出了此解决方案中步骤的关键功能和许可。

### <a name="tenant"></a>租户

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| 多个租户 | 每个 Microsoft 365 租户各不相同、唯一，并且独立于所有其他 Microsoft 365 租户。 对于多个租户，在管理租户和为用户提供服务时，存在一些限制和其他注意事项。 | Microsoft 365 E3 或 E5 | 
| 交叉租户邮箱迁移 | 租户管理员可以在租户之间移动邮箱，这些租户在本地系统中具有最少的基础结构依赖关系。 这无需离开和载入邮箱。 | Microsoft 365 E3 或 E5 | 
| 多地理位置 | 租户可以将静止数据存储在已选择满足数据驻留要求的其他数据中心地理位置中。 | Microsoft 365 E3 或 E5 | 
| 将核心数据移动到新的数据中心地理位置 | 随着 Microsoft 添加新的数据中心地理位置来增加容量和计算资源，你可以请求数据中心异地移动，以驻留核心客户数据。 | Microsoft 365 E3 或 E5 | 
||||

### <a name="networking"></a>网络

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| Network Insights | 从 Microsoft 365 租户收集的网络性能指标，可帮助你设计办公地点的网络外围。 | Microsoft 365 E3 或 E5 | 
| 自动化终结点更新 | 在客户端 PAC 文件和网络设备和服务中自动执行 Microsoft 365 终结点的配置和持续更新。 | Microsoft 365 E3 或 E5 | 
||||

### <a name="identity"></a>标识

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| 将本地 Active Directory 域服务 (AD DS) Azure AD 租户同步    | 将本地标识提供程序用于用户帐户、组和其他对象。 | Microsoft 365 E3 或 E5 |
| 通过安全性默认设置强制执行 MFA   | 通过请求第二种形式的登录身份验证，抵御遭到入侵的身份和设备的威胁。安全性默认设置要求对所有用户帐户进行 MFA。   | Microsoft 365 E3 或 E5 |
| 通过条件访问强制执行 MFA| 需要基于具有条件访问策略的登录的属性的 MFA。    | Microsoft 365 E3 或 E5 | 
| 通过基于风险的条件访问强制执行 MFA   | 需要基于使用 Microsoft Defender for Identity 的用户登录的风险进行 MFA。 | Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可） | 
| 自助服务密码重置 (SSPR)    | 允许用户重置或解锁其密码或帐户。  | Microsoft 365 E3 或 E5 |
||||

### <a name="migration"></a>迁移

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| 迁移到 Windows 10 | 将运行 Windows 7 或 Windows 8.1 的设备迁移到 Windows 10 企业版。 | Microsoft 365 E3 或 E5 中包含的 Windows 10 企业版许可证 | 
| 迁移到 Microsoft 365 企业应用版 | 将 Office 客户端应用程序（如 Word 和 PowerPoint）迁移到从云中安装的版本，这些版本更新了新功能。 | Microsoft 365 E3 或 E5 | 
| 将本地服务器和数据迁移到 Microsoft 365 | 将 Exchange 邮箱、SharePoint 网站和 Skype for Business Online 迁移到 Microsoft 365 云服务。 | Microsoft 365 E3 或 E5 | 
||||

### <a name="device-and-app-management"></a>设备和应用管理

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| Microsoft Intune | 提供移动设备管理 (MDM) 和移动应用程序管理 (MAM) 的基于云的服务，用于控制组织的应用程序和设备的使用方式，包括移动电话、平板电脑和笔记本电脑。 | Microsoft 365 E3 或 E5 | 
| 基本移动性和安全性 | 通过此内置服务保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 手机。  | Microsoft 365 E3 或 E5 | 
||||

## <a name="next-steps"></a>后续步骤

使用以下步骤设置和管理 Microsoft 365 租户。

1. [确定租户](tenant-management-tenants.md)
2. [优化网络](tenant-management-networking.md)
3. [同步标识并强制执行安全登录](tenant-management-identity.md)
4. [迁移本地 Office 服务器和数据](tenant-management-migration.md)
5. [部署设备和应用管理](tenant-management-device-management.md)

[![部署和管理 Microsoft 365 租户的步骤](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

每个步骤描述部署选项、总结结果和正在进行的维护任务。

若要了解虚构但具有代表性的多方组织如何部署其 Microsoft 365 租户的元素，请参阅 [Contoso 案例研究](../enterprise/contoso-case-study.md)。
