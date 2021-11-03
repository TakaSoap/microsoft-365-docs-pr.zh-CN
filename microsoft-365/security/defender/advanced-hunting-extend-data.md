---
title: 使用正确的设置扩展高级搜寻范围
description: 检查设备Windows的审核设置和其他设置，以确保在高级搜寻中获得最全面的数据
keywords: 高级搜寻， 事件， 透视， 实体， 审核设置， 用户帐户管理， 安全组管理， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 365， Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dd61fa434eaf2130f0fcb0f28df9a20d696e04ec
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60665353"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>使用正确的设置扩展高级搜寻范围

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

[高级](advanced-hunting-overview.md)搜寻依赖于来自各种源的数据，包括你的设备、Office 365工作区、Azure AD和 Microsoft Defender for Identity。 若要尽可能获取最全面的数据，请确保在相应的数据源中具有正确的设置。

## <a name="advanced-security-auditing-on-windows-devices"></a>Windows高级安全审核
打开这些高级审核设置，以确保获取有关设备上活动的数据，包括本地帐户管理、本地安全组管理和服务创建。

| 数据 | 说明 | 架构表 | 如何配置 |
| --- | --- | --- | --- |
| 帐户管理 | 作为指示本地帐户创建、删除和其他与帐户相关的活动的各种值 `ActionType` 捕获的事件 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署高级安全审核策略 [：审核用户帐户管理](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [了解高级安全审核策略](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 安全组管理 | 捕获为指示本地安全组创建和其他本地组管理活动 `ActionType` 的各种值的事件 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署高级安全审核策略： [审核安全组管理](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [了解高级安全审核策略](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| 服务安装 | 使用 值 捕获的事件 `ActionType` `ServiceInstalled` ，指示已创建服务 | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - 部署高级安全审核策略： [审核安全系统扩展](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [了解高级安全审核策略](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>域控制器上的 Microsoft Defender for Identity 传感器
如果你正在本地运行 Active Directory，则需要在域控制器上安装 Microsoft Defender for Identity 传感器，才能获取 Microsoft Defender for Identity 的数据。 安装并正确配置后，此数据还将通过 Microsoft Defender for Identity 馈送到高级搜寻中，并提供标识信息和网络中事件的更全面的图片。 此数据还增强了 Microsoft Defender for Identity 生成高级搜寻也涵盖的相关警报的能力。 

| 数据 | 说明 | 架构表 | 如何配置 |
| --- | --- | --- | --- |
| 域控制器  | 从本地 Active Directory 发送到 Microsoft Defender for Identity 的数据，丰富了与标识有关的信息，例如帐户详细信息、登录活动和 Active Directory 查询 | 多个表，包括[IdentityInfo、IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)和[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) [](advanced-hunting-identityinfo-table.md)  | - [安装 Microsoft Defender for Identity 传感器](/azure-advanced-threat-protection/install-atp-step4)<br>- [打开相关Windows事件](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>本文中的某些表在 Microsoft Defender for Endpoint 中可能不可用。 [打开"Microsoft 365 Defender"](m365d-enable.md)以使用更多数据源搜寻威胁。 你可以按照从 Microsoft Defender for Endpoint 迁移高级搜寻查询中的步骤将高级搜寻工作流从 Microsoft Defender for Endpoint 移动到[Microsoft 365 Defender。](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)