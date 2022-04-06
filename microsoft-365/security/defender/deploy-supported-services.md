---
title: 部署Microsoft 365 Defender支持的服务
description: 了解可通过Microsoft 365 Defender集成的 Microsoft 安全服务、其许可要求和部署过程
keywords: 部署、许可证、支持的服务、预配、配置Microsoft 365 Defender、M365、许可证资格、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Cloud App Security、MCAS、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.technology: m365d
ms.openlocfilehash: 4ac6186f3ec8ca7d4888a995b2352ec50529e4f1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664889"
---
# <a name="deploy-supported-services"></a>部署支持的服务

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md)集成了各种 Microsoft 安全服务，以提供针对复杂攻击的集中检测、预防和调查功能。 本文介绍支持的服务、其许可要求、与部署一个或多个服务相关的优点和限制，以及有关如何单独完全部署这些服务的链接。

## <a name="supported-services"></a>支持的服务

Microsoft 365 E5、E5 安全性、A5 或 A5 安全许可证或许可证的有效组合提供对以下受支持服务的访问权限，并使你能够使用Microsoft 365 Defender。 [查看许可要求](prerequisites.md#licensing-requirements)

| 支持的服务 | 说明 |
| ------ | ------ |
| Microsoft Defender for Endpoint | 围绕强大的行为传感器、云分析和威胁智能构建的 Endpoint Protection 套件 |
|Microsoft Defender for Office 365 | Office 365中应用和数据的高级保护，包括电子邮件和其他协作工具 |
| Microsoft Defender for Identity | 使用关联的 Active Directory 信号防御高级威胁、遭到入侵的标识和恶意预览体验成员 |
| Microsoft Defender for Cloud Apps | 识别并打击 Microsoft 和第三方云服务中的网络威胁 |

## <a name="deployed-services-and-functionality"></a>已部署的服务和功能

Microsoft 365 Defender在部署更多受支持的服务时提供更好的可见性、相关性和修正。

### <a name="benefits-of-full-deployment"></a>完全部署的好处

为了获得Microsoft 365 Defender的全部优势，建议部署所有受支持的服务。 下面是完整部署的一些主要优势：

- 事件根据来自所有可用传感器和特定于服务的分析功能的警报和事件信号进行识别和关联
- 自动调查和修正 (AIR) playbook 适用于各种实体类型，包括设备、邮箱和用户帐户
- 可以查询更全面的高级搜寻架构，以获取来自设备、邮箱和其他实体的事件和实体数据

### <a name="limited-deployment-scenarios"></a>有限的部署方案

部署的每个受支持服务都提供一组极其丰富的原始信号以及相关信息。 虽然有限的部署不会导致Microsoft 365 Defender功能关闭，但其在终结点、应用、数据和标识中提供全面可见性的能力会受到影响。 同时，任何修正功能仅适用于可由已部署的服务管理的实体。

下表列出了每个受支持的服务如何提供其他数据、通过关联数据获得更多见解的机会，以及更好的修正和响应功能。

| 服务 | 数据 (信号&相关信息)  | 响应范围&修正 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint |<ul><li>终结点状态和原始事件</li><li>终结点检测和警报，包括防病毒、EDR、攻击面减少</li><li>有关在终结点上观察到的文件和其他实体的信息</li></ul> | 终结点 |
|Microsoft Defender for Office 365 |<ul><li>邮件和邮箱状态以及原始事件</li><li>电子邮件、附件和链接检测</li></ul> | <ul><li>邮箱</li><li>Microsoft 365帐户</li></ul> |
| Microsoft Defender for Identity |<ul><li>Active Directory 信号，包括身份验证事件</li><li>与标识相关的行为检测</li></ul> | 身份 |
| Microsoft Defender for Cloud Apps |<ul><li>检测未经批准的云应用和服务 (隐藏 IT) </li><li>将数据公开到云应用</li><li>与云应用关联的威胁活动</li></ul> | 云应用 |

## <a name="deploy-the-services"></a>部署服务

部署每个服务通常需要预配到租户和一些初始配置。 请参阅下表，了解如何部署这些服务。

| 服务 | 预配说明 | 初始配置 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [Microsoft Defender for Endpoint 部署指南](../defender-endpoint/deployment-phases.md) | *请参阅预配说明* |
|Microsoft Defender for Office 365 | *无，使用 Office 365 预配* | [配置 Microsoft Defender for Office 365 策略](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [快速开始：创建 Microsoft Defender for Identity 实例](/azure-advanced-threat-protection/install-atp-step1) | *请参阅预配说明* |
| Microsoft Defender for Cloud Apps | *无* | [快速入门：Microsoft Defender for Cloud Apps 入门](/cloud-app-security/getting-started-with-cloud-app-security) |

部署支持的服务后，[打开Microsoft 365 Defender](m365d-enable.md)。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [打开 Microsoft 365 Defender](m365d-enable.md)
- [Microsoft Defender for Endpoint概述](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender for Office 365概述](../office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Cloud Apps 概述](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity概述](/azure-advanced-threat-protection/what-is-atp)
