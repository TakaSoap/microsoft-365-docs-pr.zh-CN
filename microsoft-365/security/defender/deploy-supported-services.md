---
title: 部署受支持Microsoft 365 Defender
description: 了解 Microsoft 安全服务，这些服务可通过 Microsoft 365 Defender集成、许可要求和部署过程
keywords: 部署， 许可证， 受支持的服务， 预配， 配置 Microsoft 365 Defender， M365， 许可证资格， Microsoft Defender for Endpoint， Microsoft Defender for Office 365， Microsoft Defender for Identity， Microsoft Cloud App Security， MCAS， E5， A5， EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
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
ms.openlocfilehash: 4a3aac06f19c7ed86af67f3b72bac8bf367628a8
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58258206"
---
# <a name="deploy-supported-services"></a>部署支持的服务

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md)各种 Microsoft 安全服务，以提供针对复杂攻击的集中检测、防护和调查功能。 本文介绍受支持的服务、其许可要求、与部署一个或多个服务相关的优点和限制，以及指向如何单独完全部署它们的链接。

## <a name="supported-services"></a>支持的服务
A Microsoft 365 E5， E5 Security， A5， or A5 Security license or a5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft 365 Defender. [请参阅许可要求](prerequisites.md#licensing-requirements)

| 支持的服务 | 描述 |
| ------ | ------ |
| Microsoft Defender for Endpoint | 围绕强大的行为传感器、云分析和威胁智能构建的终结点保护套件 |
|Microsoft Defender for Office 365 | 对应用中的应用和数据的高级保护Office 365包括电子邮件和其他协作工具 |
| Microsoft Defender for Identity | 使用关联的 Active Directory 信号防御高级威胁、泄露的标识和恶意预览体验成员 |
| Microsoft Cloud App Security | 识别并防御 Microsoft 和第三方云服务中的网络威胁 |

## <a name="deployed-services-and-functionality"></a>已部署的服务和功能
Microsoft 365 Defender部署更多受支持服务时，可提供更好的可见性、相关性和修正。

### <a name="benefits-of-full-deployment"></a>完整部署的好处
若要获得部署服务的完整Microsoft 365 Defender，我们建议部署所有受支持的服务。 以下是完整部署的一些关键优势：
- 根据来自所有可用传感器和特定于服务的分析功能发出的警报和事件信号来标识并关联事件
- AIR (自动调查和) 手册适用于各种实体类型，包括设备、邮箱和用户帐户
- 可以针对设备、邮箱和其他实体的事件和实体数据查询更全面的高级搜寻架构

### <a name="limited-deployment-scenarios"></a>有限的部署方案
您部署的每个受支持的服务都提供一组极其丰富的原始信号和相关信息。 虽然有限的部署不会导致Microsoft 365 Defender功能关闭，但它提供跨终结点、应用、数据和标识的全面可见性的能力会受到影响。 同时，任何修正功能仅适用于可通过已部署的服务管理的实体。

下表列出了每个受支持的服务如何提供其他数据、通过关联数据获取其他见解的机会，以及更好的修正和响应功能。

| 服务 | 数据 (信号&信息关联)  | 修正&响应范围 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | - 终结点状态和原始事件<br />- 终结点检测和警报，包括防病毒、EDR、攻击面减少<br />- 有关在终结点上观测到的文件和其他实体的信息 | 终结点 |
|Microsoft Defender for Office 365 | - 邮件和邮箱状态以及原始事件<br />- 电子邮件、附件和链接检测 | - 邮箱<br />- Microsoft 365帐户 |
| Microsoft Defender for Identity | - Active Directory 信号，包括身份验证事件<br />- 与标识相关的行为检测 | 身份 |
| Microsoft Cloud App Security | - 检测未批准的云应用和服务 (卷影 IT) <br />- 向云应用公开数据<br />- 与云应用关联的威胁活动 | 云应用 |

## <a name="deploy-the-services"></a>部署服务
部署每个服务通常需要预配到租户和一些初始配置。 请参阅下表，了解如何部署其中每个服务。

| 服务 | 设置说明 | 初始配置 |
| ------ | ------ | ------ |
| Microsoft Defender for Endpoint | [Microsoft Defender for Endpoint 部署指南](../defender-endpoint/deployment-phases.md) | *请参阅预配说明* |
|Microsoft Defender for Office 365 | *无，已预配Office 365* | [配置 Microsoft Defender for Office 365 策略](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [快速入门：创建 Microsoft Defender for Identity 实例](/azure-advanced-threat-protection/install-atp-step1) | *请参阅预配说明* |
| Microsoft Cloud App Security | *无* | [快速入门：快速入门Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

部署支持的服务后，打开["Microsoft 365 Defender"。](m365d-enable.md)

## <a name="related-topics"></a>相关主题

- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [打开 Microsoft 365 Defender](m365d-enable.md)
- [Microsoft Defender for Endpoint 概述](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender for Office 365 概述](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security 概述](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity 概述](/azure-advanced-threat-protection/what-is-atp)
