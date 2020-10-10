---
title: 使用适当的设置扩展高级的求职覆盖范围
description: 检查 Windows 设备和其他设置上的审核设置，以帮助确保你在高级搜寻中获取最全面的数据
keywords: 高级搜索、事件、数据透视、实体、审核设置、用户帐户管理、安全组管理、威胁搜索、网络威胁搜寻、搜索、查询、遥测、Microsoft 365、Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 39beff1ea5e983af53cdb954783c11f13569a022
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413946"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>使用适当的设置扩展高级的求职覆盖范围

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

[高级搜寻](advanced-hunting-overview.md) 依赖于来自各种源的数据，其中包括设备、Office 365 工作区、azure AD 和 azure ATP。 若要尽可能获取最全面的数据，请确保相应的数据源中的设置正确。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 设备上的高级安全审核
启用这些高级审核设置，以确保获取有关设备上的活动的数据，包括本地帐户管理、本地安全组管理和服务创建。

| Data | 说明 | 架构表 | 如何配置 |
| --- | --- | --- | --- |
| 帐户管理 | 以各种 `ActionType` 指示本地帐户创建、删除和其他与帐户相关活动的值捕获的事件 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高级安全审核策略： [审核用户帐户管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 安全组管理 | 以各种 `ActionType` 指示本地安全组创建和其他本地组管理活动的值的形式捕获事件 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高级安全审核策略： [审核安全组管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 服务安装 | 以值捕获的 `ActionType` 事件 `ServiceInstalled` ，指示已创建的服务 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -部署高级安全审核策略： [审核安全系统扩展](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>域控制器上的 Azure ATP 传感器
如果您在本地运行 Active Directory，则需要在域控制器上安装 Azure ATP 传感器，以获取 Azure ATP 的数据。 在安装并正确配置后，此数据还会通过 Azure ATP 进入高级搜索，并提供网络中的标识信息和事件的更全面的说明。 此数据还增强了 Azure ATP 生成相关警报的能力，这些警报也是高级搜寻所涵盖的。 

| Data | 说明 | 架构表 | 如何配置 |
| --- | --- | --- | --- |
| 域控制器 | 将本地 Active Directory 中的数据发送到 Azure ATP，浓缩与标识相关的信息，例如帐户详细信息、登录活动和 Active Directory 查询 | 多个表，包括 [IdentityInfo](advanced-hunting-identityinfo-table.md)、 [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)和 [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [安装 Azure ATP 传感器](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [启用相关的 Windows 事件](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)
