---
title: 在 Microsoft 365 中部署网络安全威胁保护
description: 了解如何在 Microsoft 365 E5 中部署威胁保护服务和 IT 网络安全功能。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 2d1316927124b1ce03910190922fa0804853ae4b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845272"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>在 Microsoft 365 中部署威胁防护功能

[恶意软件](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)和复杂的 cyberattacks （如 [fileless 威胁](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)）是常见事件。 企业需要使用有效的 IT 网络安全功能来保护自己及其客户。 此类攻击可能会导致贵组织的主要问题，包括从失去信任到财务 woes、业务威胁停机等。 防御威胁非常重要，但确定组织的时间、工作和资源的位置可能会有很大难度。 

Microsoft 安全解决方案内置在我们的产品和服务中。 自动化和机器学习功能可降低安全团队的负载，以确保解决正确的项目。 Microsoft 网络安全解决方案的优势是基于我们在 [智能安全图形](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)中每天处理的 trillions 信号。 Microsoft 365 安全解决方案包括 [microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)，这是一种解决方案，可跨您的电子邮件、数据、设备和标识一起提供各种信号，以在组织中绘制高级威胁的图片。


观看此视频以简要了解部署流程。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

使用本文作为实施威胁防护解决方案的指南。

## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5 中的威胁防护

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 使你能够使用自适应内置智能来保护你的组织。 使用 Microsoft 365 E5 中的威胁防护功能，可以在内部部署和云环境中检测和调查高级威胁、受到危害的身份和恶意操作。

在 Microsoft 365 E5 中，默认情况下会集成威胁防护功能。 来自每个功能的信号将强度增加到检测和响应威胁的总体能力。 与运行非 Microsoft 产品相比，组合的一组功能为组织提供了最佳保护，尤其是多国组织。 下图描述了 Microsoft 365 E5 中的威胁防护服务和功能，如本文中所述。

![Microsoft 365 Defender 概述](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

一旦您部署任何适用于 Office 365 的任何 Defender 功能，您就可以打开 Microsoft 365 Defender，这会将信号和数据一起引入一个位置。 

![Microsoft 365 Defender 仪表板的概念性图示](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

下图展示了用于部署这些单独功能的推荐途径。 

![M365 威胁防护信号](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|解决方案/功能  |说明  |
|---------|---------|
|多重身份验证和条件访问     |针对泄露的标识和设备进行防护。 从这种保护开始，因为它是基础。 本指南中建议的配置包括作为先决条件的 Azure AD 标识保护。     |
|Microsoft Defender for Identity     |  一种基于云的安全解决方案，利用本地 Active Directory 信号识别、检测和调查组织中的高级威胁、已泄露身份和恶意内幕行为。 关注 Microsoft Defender for Identity 下一步，因为它保护您的本地和云基础结构，没有任何依赖项或先决条件，并且可以提供直接的好处。       | 
|Microsoft Defender for Office 365     | 保护您的组织免受电子邮件、链接 (Url) 和协作工具带来的恶意威胁的侵扰。 针对恶意软件、网络钓鱼、欺骗和其他攻击类型的保护。 接下来建议配置 Microsoft Defender for Office 365，因为更改控制、从委任系统迁移设置以及其他注意事项可能需要更长时间才能部署。 <br><br>注意：请确保在 Exchange Online Protection)  (配置所有 Office 365 订阅中所包含的威胁防护功能。       |
|Microsoft Defender for Endpoint    | 一种 endpoint protection 平台，可帮助防止、检测、调查和响应高级威胁。  用于终结点的 Defender 可能需要一些时间来部署，但可以与其他功能并行进行配置。   |
|Microsoft Cloud App Security     |   用于发现、调查和治理的云访问安全代理。 你可以及早启用 Microsoft 云应用安全，以开始收集数据和见解。 在您的 SaaS 应用程序中实施信息和其他目标保护涉及规划，并可能需要更多时间。       | 

> [!TIP]
> 具有多个安全团队的组织可以并行实施这些功能。

## <a name="deploy-your-threat-protection-solution"></a>部署威胁防护解决方案

若要确保贵组织能够获得最佳保护，请设置和部署安全解决方案以包括以下步骤：

1. [设置多重身份验证和条件访问策略](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [配置 Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [启用 Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [配置适用于 Office 的 Defender 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [为终结点配置 Microsoft Defender](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [配置 Microsoft 云应用安全](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [监视状态并采取操作](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [培训用户](deploy-threat-protection-configure.md#step-8-train-users)

您的威胁防护功能可以并行配置，因此，如果您有多个负责不同服务的网络安全团队，则可以同时配置组织的保护功能。 下图说明了部署威胁防护功能的高级别过程。 

![部署威胁防护功能的过程](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


