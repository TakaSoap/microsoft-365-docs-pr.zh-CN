---
title: 跨 Microsoft 365 部署威胁防护功能
description: 了解如何在 Microsoft 365 E5 中部署威胁防护服务和安全性功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 2da2ace96b731baedea9142e211e9301db69000d
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976564"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>跨 Microsoft 365 部署威胁防护功能

[恶意软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)和复杂的网络攻击（如无文件威胁）[](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)是常见事件。 企业需要使用有效的 IT 安全性功能来保护自己及其客户。 网络攻击可能会给组织带来严重问题，包括失去信任、财务问题、业务损失停机时间等。 防范威胁很重要，但确定组织的时间、精力和资源重点在哪些方面可能非常困难。 

Microsoft 安全解决方案内置在我们的产品和服务中。 自动化和机器学习功能可减少安全团队的负载，以确保解决正确的项目。 Microsoft 安全解决方案的强大功能基于我们的 Intelligent [Security Graph](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)中每天处理数十万个信号。 Microsoft 365 安全解决方案包括 [Microsoft 365 Defender，](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)这是一种将电子邮件、数据、设备和标识中的信号汇集在一起的解决方案，可绘制针对组织的高级威胁的图片。


观看此视频以简要了解部署流程。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

使用本文作为实现威胁防护解决方案的指南。

## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5 中的威胁防护

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 使你能够使用自适应内置智能保护组织。 借助 Microsoft 365 E5 中的威胁防护功能，可以检测和调查内部部署和云环境中的高级威胁、遭到入侵的标识和恶意操作。

在 Microsoft 365 E5 中，默认情况下集成了威胁防护功能。 来自每个功能的信号为检测和响应威胁的整体能力增加强度。 与运行非 Microsoft 产品相比，组合的功能集为组织（尤其是跨国家/地区组织）提供最佳保护。 下图描述了本文中介绍的 Microsoft 365 E5 中的威胁防护服务和功能。

![Microsoft 365 Defender 概述](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

一旦部署任何 Defender for Office 365 功能，就可以打开 Microsoft 365 Defender，从而将信号和数据汇集在一起。 

![Microsoft 365 Defender 仪表板的概念图示](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

下图描述了部署这些单个功能的建议路径。 

![M365 威胁防护信号](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|解决方案/功能  |说明  |
|---------|---------|
|多重身份验证和条件访问     |防止标识和设备遭到入侵。 从此保护开始，因为它具有基础性。 本指南中建议的配置包括 Azure AD Identity Protection 作为先决条件。     |
|Microsoft Defender for Identity     |  基于云的安全解决方案，利用本地 Active Directory 信号识别、检测和调查针对组织的高级威胁、泄露的身份和恶意内部操作。 接下来关注 Microsoft Defender for Identity，因为它可保护你的企业部署和云基础结构，没有任何依赖关系或先决条件，并且可以提供直接的好处。       | 
|Microsoft Defender for Office 365     | 保护组织免受电子邮件、链接和 (URL) 和协作工具造成的恶意威胁。 恶意软件、网络钓鱼、欺骗和其他攻击类型的保护。 下一步建议配置 Microsoft Defender for Office 365，因为更改控制、从系统迁移设置和其他注意事项可能需要更长时间才能部署。 <br><br>注意：确保配置 Exchange Online Protection (中所有 Office 365 订阅) 。       |
|Microsoft Defender for Endpoint    | 有助于预防、检测、调查和响应高级威胁的终结点保护平台。  Defender for Endpoint 可能需要一些时间才能部署，但配置可以与其他功能并行完成。   |
|Microsoft Cloud App Security     |   用于发现、调查和治理的云访问安全代理。 你可以提前启用 Microsoft Cloud App Security，以便开始收集数据和见解。 在 SaaS 应用中实现信息和其他目标保护涉及规划，并且可能需要更多时间。       | 

> [!TIP]
> 具有多个安全团队的组织可以并行实现这些功能。

## <a name="deploy-your-threat-protection-solution"></a>部署威胁防护解决方案

若要确保组织具有尽可能最佳的保护，请设置和部署安全解决方案以包括以下步骤：

1. [设置多重身份验证和条件访问策略](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [为标识配置 Microsoft Defender](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [打开 Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [为 Office 365 配置 Defender](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [配置适用于终结点的 Microsoft Defender](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [配置 Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [监视状态并采取措施](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [培训用户](deploy-threat-protection-configure.md#step-8-train-users)

威胁防护功能可以并行配置，因此，如果有多个网络安全团队负责不同的服务，他们可以同时配置组织的保护功能。 下图演示了部署威胁防护功能的高级别流程。 

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
