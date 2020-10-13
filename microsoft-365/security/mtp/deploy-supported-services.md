---
title: 部署 Microsoft 威胁防护支持的服务
description: 了解可以通过 Microsoft 威胁防护、其许可要求和部署过程集成的 Microsoft 安全服务
keywords: 部署、许可证、受支持的服务、设置、配置 Microsoft 威胁防护、M365、许可证资格、Microsoft Defender ATP、MDATP、Office 365 ATP、Azure ATP、Microsoft 云应用安全性、MCAS、高级威胁防护、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
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
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4e4036e1a1ee0ccf807dc5299b9842911f140478
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430807"
---
# <a name="deploy-supported-services"></a>部署支持的服务

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 威胁防护](microsoft-threat-protection.md) 集成了各种 Microsoft 安全服务，以提供针对复杂攻击的集中式检测、预防和调查功能。 本文介绍了受支持的服务、其许可要求、与部署一个或多个服务相关的优势和限制，以及如何单独完全部署它们的链接。

## <a name="supported-services"></a>支持的服务
Microsoft 365 E5、E5 Security、A5 或 A5 安全许可证或有效的许可证组合提供对以下受支持服务的访问权限，并允许您在 Microsoft 365 安全中心中使用 Microsoft 威胁防护。 [请参阅许可要求](prerequisites.md#licensing-requirements)

| 支持的服务 | 说明 |
| ------ | ------ |
| 每个租户 | 围绕功能强大的行为传感器、云分析和威胁智能构建的 Endpoint protection 套件 |
| Office 365 ATP | Office 365 中的应用和数据的高级保护，包括电子邮件和其他协作工具 |
| Azure ATP | 使用关联的 Active Directory 信号防御高级威胁、已泄露身份和恶意预览体验 |
| Microsoft Cloud App Security | 跨你的 Microsoft 和第三方云服务识别和打击威胁 |

## <a name="deployed-services-and-functionality"></a>部署的服务和功能
当您部署更受支持的服务时，Microsoft 威胁防护可提供更好的可见性、关联和修正。

### <a name="benefits-of-full-deployment"></a>完整部署的好处
若要获得 Microsoft 威胁防护的全部优点，建议部署所有受支持的服务。 以下是完整部署的一些主要优点：
- 根据来自所有可用传感器和特定于服务的分析功能的警报和事件信号确定和关联事件
- 自动调查和修正 (空气) 行动手册适用于各种实体类型，包括设备、邮箱和用户帐户
- 可以查询更全面的高级搜寻架构，以获取来自设备、邮箱和其他实体的事件和实体数据

### <a name="limited-deployment-scenarios"></a>有限的部署方案
您部署的每个受支持的服务都提供了一组极其丰富的原始信号以及关联信息。 虽然有限的部署不会导致禁用 Microsoft 威胁防护功能，但其在终结点、应用、数据和标识之间提供全面可见性的能力将受到影响。 同时，任何修正功能仅适用于可由您部署的服务管理的实体。

下表列出了每个受支持的服务如何提供其他数据、通过关联数据获取更多洞察力的机会以及更好的补救措施和响应功能。

| 服务 | 数据 (信号 & 相关信息)  | 修正 & 响应作用域 |
| ------ | ------ | ------ |
| 每个租户 | -终结点状态和原始事件<br />-终结点检测和警报，包括防病毒、EDR、攻击面减少<br />-有关在终结点上观测到的文件和其他实体的信息 | 终结点 |
| Office 365 ATP | -邮件和邮箱状态以及原始事件<br />-电子邮件、附件和链接检测 | -邮箱<br />-Microsoft 365 帐户 |
| Azure ATP | -Active Directory 信号，包括身份验证事件<br />-与标识相关的行为检测 | 身份 |
| Microsoft Cloud App Security | -Unsanctioned 云应用和服务的检测 (隐藏它) <br />-将数据暴露给云应用<br />-与云应用程序关联的威胁活动 | 云应用 |

## <a name="deploy-the-services"></a>部署服务
部署每个服务通常需要预配到租户和一些初始配置。 请参阅下表了解每个服务的部署方式。

| 服务 | 预配说明 | 初始配置 |
| ------ | ------ | ------ |
| 每个租户 | [Microsoft Defender ATP 部署指南](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *请参阅预配说明* |
| Office 365 ATP | *无，使用 Office 365 预配* | [配置 ATP 策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [快速入门：创建 Azure ATP 实例](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *请参阅预配说明* |
| Microsoft Cloud App Security | *无* | [快速入门： Microsoft 云应用安全入门](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

部署受支持的服务后， [打开 Microsoft 威胁防护](mtp-enable.md)。

## <a name="related-topics"></a>相关主题

- [Microsoft 威胁防护概述](microsoft-threat-protection.md)
- [打开 Microsoft 威胁防护](mtp-enable.md)
- [Microsoft Defender ATP 概述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 概述](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概述](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 概述](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
