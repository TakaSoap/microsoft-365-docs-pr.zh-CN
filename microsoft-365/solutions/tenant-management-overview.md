---
title: 适用于企业的 Microsoft 365 租户管理
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
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: 规划、部署和持续操作应用程序租户的Microsoft 365概述。
ms.openlocfilehash: 7a9545800c3f5f08b8094290c4173b4368caff4d
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524209"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>适用于企业的 Microsoft 365 租户管理

通过云计算创建组织数字化转型的路径需要一个稳固的基础，员工可以依靠这些基础来提高工作效率、协作、性能、隐私、合规性和安全性。

正确配置 Microsoft 365 租户提供了基础，让工作人员专注于完成工作，IT 部门专注于提供其他业务价值的端到端解决方案。

此解决方案将按照以下步骤完成该基础的配置：

1. 确定租户
2. 优化网络
3. 同步标识并强制执行安全登录
4. 迁移Windows设备、Office客户端以及本地Office服务器和数据
5. 部署设备和应用管理

但是首先，让我们花些时间了解一下什么是租户，以及提供稳固基础的租户的外观。

## <a name="a-microsoft-365-tenant-defined"></a>定义的Microsoft 365租户

Microsoft 365租户是特定默认位置（如欧洲或北美）中存储的 Microsoft 365 服务的专用实例。 为组织创建租户时指定此位置。 每个Microsoft 365租户都是唯一的，并且独立于所有其他Microsoft 365租户。 从 Microsoft Microsoft 365一个或多个产品（如 Microsoft 365 E3 或 E5）时，创建一个租户租户，并为每个租户创建一组许可证。

你的Microsoft 365租户还包括一Azure Active Directory (Azure AD) 租户，它是用户帐户、组Azure AD对象的专用租户实例。 每个Azure AD租户都是独特、唯一的，并且独立于所有其他Azure AD租户。 虽然你的组织可以有多个 Azure AD 租户，但 Microsoft 365 租户只能使用一个 Azure AD 租户，即创建租户时创建的租户。

下面是一个示例：

![具有Microsoft 365租户的租户Azure AD示例。](../media/tenant-management-overview/tenant-management-example-tenant.png)

*租户管理* 是租户租户的规划、部署和Microsoft 365操作。

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>设计良好且运行良好的租户的属性

除了租户的正确&mdash;名称和位置之外，还需要规划、部署和管理其他元素，以确保使用云生产力应用（如 Microsoft Teams 和 Exchange Online）&mdash;的用户体验有效、安全且性能高。

以下是元素：

- 你拥有一组正确的产品 (订阅) 许可证。
  - 一组产品符合你的业务、IT 和安全需求。
  - 员工具有足够数量的许可证，并且员工预期会发生变化。
- 对于网络：
  - 已配置正确的 DNS 域名。
  - 对于企业网络，已针对现场工作人员优化了到 Microsoft 网络的网络流量。
  - 你已针对使用 VPN 客户端的远程工作人员优化了网络流量。
- 已同步 Active Directory 域服务 (AD DS) 帐户、组和其他对象。
  - 你的Azure AD租户帐户将映射到Exchange Online具有正确的电子邮件地址 DNS 域的邮箱。
  - 你的用户帐户已分配有正确购买产品的正确许可证 (如 Microsoft 365 E3 E5) 。
- 已配置强标识和访问管理。
  - 你需要使用无密码身份验证或多重身份验证和 MFA (安全) 。
  - 您具有条件访问策略，这些策略强制实施登录要求和针对较高安全级别的限制。
- 本地Office服务器及其数据已迁移到云应用或正在混合配置中使用。
- 你使用内置于设备的 Intune 或基本移动性和安全性Microsoft 365。
  - 组织拥有的设备已注册和管理。
  - 管理个人设备的应用。

下面是一个包含Microsoft 365元素的租户示例。

![租户Microsoft 365示例。](../media/tenant-management-overview/tenant-management-tenant-config.png)

在此图中，Microsoft 365租户包括：

- 适用于 Microsoft 365 E3 和 E5 的产品和许可证。
- Microsoft 365工作效率应用。
- Intune，具有已注册的设备以及设备和应用程序策略。
- 在Azure AD组和其他目录对象 (用户帐户的租户不会显示在) 、域和条件访问策略中。

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>适用于企业的 Microsoft 365 租户功能

以下各节和表列出了此解决方案中步骤的关键功能和许可。

### <a name="tenant"></a>租户

|功能或特性|说明|许可|
|---|---|---|
|多个租户|每个Microsoft 365租户都是唯一的，并且独立于所有其他Microsoft 365租户。 对于多个租户，在管理租户和为用户提供服务时，存在一些限制和其他注意事项。|Microsoft 365 E3 或 E5|
|交叉租户邮箱迁移|租户管理员可以在本地系统中以最少的基础结构依赖项在租户之间移动邮箱。 这将无需离开和载入邮箱。|Microsoft 365 E3 或 E5|
|多地理位置|租户可以在选择满足数据驻留要求的其他数据中心地理位置中存储静止数据。|Microsoft 365 E3 或 E5|
|将核心数据移动到新的数据中心地理位置|随着 Microsoft 添加新的数据中心地理位置来增加容量和计算资源，你可以请求为核心客户数据的地理位置内数据驻留进行数据中心异地移动。|Microsoft 365 E3 或 E5|
||||

### <a name="networking"></a>网络

|功能或特性|说明|许可|
|---|---|---|
|网络Insights|从租户中收集的网络Microsoft 365指标，有助于设计办公地点的网络外围。|Microsoft 365 E3 或 E5|
|自动化终结点更新|自动执行客户端 PAC 文件和网络设备Microsoft 365终结点的配置和持续更新。|Microsoft 365 E3 或 E5|
||||

### <a name="identity"></a>标识

|功能或特性|说明|许可|
|---|---|---|
|将本地 Active Directory 域服务 (AD DS) 与 Azure AD 租户同步|将本地标识提供程序用于用户帐户、组和其他对象。|Microsoft 365 E3 或 E5|
|通过安全性默认设置强制执行 MFA|通过请求第二种形式的登录身份验证，抵御遭到入侵的身份和设备的威胁。安全性默认设置要求对所有用户帐户进行 MFA。|Microsoft 365 E3 或 E5|
|通过条件访问强制执行 MFA|需要基于具有条件访问策略的登录属性的 MFA。|Microsoft 365 E3 或 E5|
|通过基于风险的条件访问强制执行 MFA|需要基于使用 Microsoft Defender for Identity 的用户登录的风险进行 MFA。|Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可）|
|自助服务密码重置 (SSPR)|允许用户重置或解锁其密码或帐户。|Microsoft 365 E3 或 E5|
||||

### <a name="migration"></a>迁移

|功能或特性|说明|许可|
|---|---|---|
|迁移到 Windows 10|将运行 Windows 7 或 Windows 8.1 的设备Windows 10 企业版。|Windows 10 企业版或 E5 Microsoft 365 E3许可证|
|迁移到Microsoft 365 企业应用版|将 Office 客户端应用（如 Word 和 PowerPoint）迁移到从云中安装且使用新功能更新的版本。|Microsoft 365 E3 或 E5|
|将本地服务器和数据迁移到Microsoft 365|将Exchange邮箱、SharePoint网站和 Skype for Business Online Microsoft 365云服务。|Microsoft 365 E3 或 E5|
||||

### <a name="device-and-app-management"></a>设备和应用管理

|功能或特性|说明|许可|
|---|---|---|
|Microsoft Intune|基于云的服务，提供移动设备管理 (MDM) 和移动应用程序管理 (MAM) ，以控制组织的应用程序和设备的使用方式，包括移动电话、平板电脑和笔记本电脑。|Microsoft 365 E3 或 E5|
|基本移动性和安全性|通过此内置服务保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 电话。|Microsoft 365 E3 或 E5|
||||

## <a name="next-steps"></a>后续步骤

使用以下步骤设置和管理你的Microsoft 365租户。

1. [确定租户](tenant-management-tenants.md)
2. [优化网络](tenant-management-networking.md)
3. [同步标识并强制执行安全登录](tenant-management-identity.md)
4. [迁移本地部署Office服务器和数据](tenant-management-migration.md)
5. [部署设备和应用管理](tenant-management-device-management.md)

[![部署和管理租户Microsoft 365步骤。](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

每个步骤描述部署选项、总结结果和正在进行的维护任务。

若要了解虚构但具有代表性的跨国家组织如何部署其 Microsoft 365 租户的元素，请参阅 [Contoso 案例研究](../enterprise/contoso-case-study.md)。
