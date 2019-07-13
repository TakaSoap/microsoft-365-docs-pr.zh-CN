---
title: Azure Active Directory 租户详细信息
description: 本主题介绍在注册 Microsoft 托管桌面时对 AAD 帐户所做的更改。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643943"
---
# <a name="azure-active-directory-tenant-details"></a>Azure Active Directory 租户详细信息
{gory 帐户、API 调用、权限等的详细信息, 等等。


## <a name="data-transmitted-to-and-from-your-aad-account"></a>向 AAD 帐户传输数据的数据


向你的帐户发送的来自 Microsoft 的数据:

- 组名称
- 安全策略配置
- 设备订单
- 用户帐户 (msadmin、mstest、mwaas_soc_ro、mwaas_wdgsoc)
- 将 E5 许可证分配给用户帐户
- 更新响铃的 Windows 更新策略

从你的帐户发送到 Microsoft 的数据:

- 设备更新、使用率和可靠性数据
- 应用程序部署和可靠性数据
- 更新和安全策略部署数据
- 分配到设备的用户  

从你的帐户传输的数据存储在 Microsoft 租户 (美国托管的 Microsoft 租户) 中的 Azure SQL 数据库中。 根据 {Microsoft Azure security} 中所述的策略存储和处理数据。 

## <a name="api-permissions-and-calls"></a>API 权限和调用

**注册期间:**

API 权限:
- DeviceManagementServiceConfig.ReadWrite.All
- Directory.AccessAsUser.All
- User.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- DeviceManagementManagedDevices.ReadWrite.All
- Group.ReadWrite.All

API 调用:
- POST/organization/{organizationId}/setMobileDeviceManagementAuthority
- GET/POST/directoryRoles/{id}/members
- GET/POST/users
- GET/POST/groups
- 修补程序/groups/{id}
- GET/POST/deviceManagement/deviceConfigurations
- 获取/deviceManagement/detectedApps

**注册后, 在常规管理过程中:**

API 权限:
- DeviceManagementManagedDevices.ReadWrite.All
- DeviceManagementApps.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- Reports.Read.All
- User.ReadWrite.All
- Group.ReadWrite.All
- Directory.AccessAsUser.All

API 调用:
- GET/POST/directoryRoles/{id}/members
- GET/PATCH/POST/users
- GET/POST/groups
- 修补程序/groups/{id}
- GET/POST/deviceManagement/deviceConfigurations
- GET/POST/deviceAppManagement/mobileApps
- 获取/deviceManagement/detectedApps
- 获取/devices
- POST/users/{id | userPrincipalName}/assignLicense
- 获取/subscribedSkus

## <a name="accounts-used-by-microsoft-managed-desktop"></a>Microsoft 托管桌面使用的帐户





| 帐户 | 说明  | 条件访问  | 多重身份验证  | 为什么这一点很正常 |
|---------|---------|---------|---------|--------------|
| msadmin @ * onmmicrosoft | 具有管理员权限的有限服务帐户, 用作 Microsoft Intune 和用户管理员 {这是什么？ 为 Microsoft 新式桌面设备定义和配置租户。没有交互式登录权限;仅通过服务执行操作。  | 排除, 因为它不是源自您的网络        | 由于没有交互式登录而被排除        | 存储在 Azure Key Vault 中的密码 |
| mstest @ * onmmicrosoft     |         |         |         |
| mssupport @ * onmmicrosoft     |         |         |         |
| msadminint @ * onmmicrosoft     |         |         |         |
