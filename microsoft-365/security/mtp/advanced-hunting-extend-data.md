---
title: 使用正确的设置扩展高级搜寻范围
description: 检查 Windows 设备的审核设置和其他设置，以帮助确保你在高级搜寻中获得最全面的数据
keywords: 高级搜寻， 事件， 透视， 实体， 审核设置， 用户帐户管理， 安全组管理， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 365， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929582"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>使用正确的设置扩展高级搜寻范围

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[高级搜寻](advanced-hunting-overview.md) 依赖于来自各种源的数据，包括你的设备、Office 365 工作区、Azure AD 和 Microsoft Defender for Identity。 若要尽可能获取最全面的数据，请确保在相应的数据源中具有正确的设置。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows 设备上的高级安全审核
打开这些高级审核设置，以确保获取有关设备上活动的数据，包括本地帐户管理、本地安全组管理和服务创建。

| Data | 说明 | 架构表 | 如何配置 |
| --- | --- | --- | --- |
| 帐户管理 | 作为指示本地帐户创建、删除和其他与帐户相关的活动的各种值 `ActionType` 捕获的事件 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署高级安全审核策略 [：审核用户帐户管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 安全组管理 | 作为指示本地安全组创建和其他本地组管理活动的各种值 `ActionType` 捕获的事件 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署高级安全审核策略： [审核安全组管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 服务安装 | 使用值捕获 `ActionType` 的事件 `ServiceInstalled` ，指示已创建服务 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署高级安全审核策略： [审核安全系统扩展](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>域控制器上的 Microsoft Defender for Identity 传感器
如果在本地运行 Active Directory，则需要在域控制器上安装 Microsoft Defender for Identity 传感器，才能获取 Microsoft Defender for Identity 的数据。 安装并正确配置后，此数据还将通过 Microsoft Defender for Identity 馈送到高级搜寻中，并更全面地了解网络中的身份信息和事件。 此数据还增强了 Microsoft Defender for Identity 生成高级搜寻也涵盖的相关警报的能力。 

| Data | 说明 | 架构表 | 如何配置 |
| --- | --- | --- | --- |
| 域控制器 | 从本地 Active Directory 发送到 Microsoft Defender 的标识数据，用于丰富与标识有关的信息，例如帐户详细信息、登录活动和 Active Directory 查询 | 多个表，包括[IdentityInfo、IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)和[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) [](advanced-hunting-identityinfo-table.md)  | - [安装 Microsoft Defender for Identity 传感器](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [打开相关的 Windows 事件](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)
