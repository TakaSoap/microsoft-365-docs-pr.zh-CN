---
title: 跨组织部署威胁防护Microsoft 365
description: 大致了解威胁防护服务和 Microsoft 365 E5。 使用安全保护用户帐户、设备、电子邮件内容Microsoft 365 E5。
keywords: Microsoft 威胁防护， defender， 设置， 高级威胁防护， 安全性， microsoft 365 E5， 保护设备
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 4008f4e0198058e2b13de62c34697e3034d499b2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583216"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>跨组织部署威胁防护Microsoft 365 E5

此解决方案介绍了威胁防护中强大的威胁Microsoft 365 E5以及威胁防护为什么很重要。 大致了解组织中的威胁Microsoft 365 E5并了解如何为组织进行设置和配置。

## <a name="why-threat-protection-is-important"></a>为什么威胁防护很重要 

[恶意软件](/windows/security/threat-protection/intelligence/understanding-malware)和复杂的网络攻击（如无文件威胁）[](/windows/security/threat-protection/intelligence/fileless-threats)是常见事件。 企业需要使用有效的 IT 安全性功能来保护自己及其客户。 网络攻击可能会给组织带来严重问题，包括失去信任、财务问题、业务损失停机时间等。 防范威胁非常重要，但确定组织的时间、工作量和资源重点在哪些方面是一项挑战。 Microsoft 365 E5可以提供帮助。 

## <a name="threat-protection-in-microsoft-365-e5"></a>威胁防护Microsoft 365 E5

Microsoft 安全解决方案内置在我们的产品和服务中。 自动化和机器学习功能可减少安全团队的负载，以确保正确的项目已解决。 Microsoft 安全解决方案的强大功能基于我们的智能安全中心中每天处理[Graph。](/graph/security-concept-overview) Microsoft 365安全解决方案包括 Microsoft 365 [Defender，](../security/defender/microsoft-365-defender.md)这是一种将电子邮件、数据、设备和标识中的信号汇集在一起，以绘制针对组织的高级威胁的图片的解决方案。

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab)使用自适应内置智能保护组织。 借助 Microsoft 365 E5 中的安全功能，你可以检测并调查本地环境中和云环境中的高级威胁、遭到入侵的标识 (恶意) 。

## <a name="better-protection-with-integration"></a>通过集成提供更好的保护

默认情况下Microsoft 365 E5集成威胁防护功能。 来自每个功能的信号为检测和响应威胁的整体能力增加强度。 与运行非 Microsoft 产品相比，组合的功能集为组织（尤其是跨国家/地区组织）提供最佳保护。 下图描述了本文中介绍的威胁防护服务和功能。

![Microsoft 365 Defender 概述](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365Defender 将信号和数据一起引入统[一Microsoft 365安全中心](/microsoft-365/security/defender/overview-security-center)。 

> [!div class="mx-imgBorder"]
> ![Defender 仪表板Microsoft 365插图](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>部署概述

下图描述了部署这些单个功能的建议路径。 

> [!div class="mx-imgBorder"]
> ![M365 威胁防护信号](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

观看此视频以简要了解部署流程。
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

下表介绍了要配置的各种解决方案/功能及其功能。

|步骤 |解决方案/功能  |说明  |
|--|---------|---------|
| 1 |[多重身份验证和条件访问](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |防止标识和设备遭到入侵。 从此保护开始，因为它具有基础性。 本指南中建议的配置包括 Azure AD Identity Protection 作为先决条件。 有关详细信息，请参阅[Azure AD Identity Protection。](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection)     |
| 2 |[Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  基于云的安全解决方案，使用本地 Active Directory 域服务 (AD DS) 信号识别、检测和调查针对组织的高级威胁、泄露的身份和恶意预览体验成员操作。 接下来重点介绍 Microsoft Defender for Identity，因为它可保护本地和云基础结构，没有依赖关系或先决条件，并且可以提供即时安全优势。 有关详细信息，请参阅[什么是标识保护？。](/azure/active-directory/identity-protection/overview-identity-protection) | 
| 3 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |将信号和安排功能组合到单个解决方案中。 使安全专业人员能够将威胁信号汇集在一起，并确定威胁的完整范围和影响。 Microsoft 365Defender 采取自动操作来阻止或停止攻击和自我修复受影响的邮箱、终结点和用户标识。 有关详细信息，请参阅[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)。 |
| 4  |[Microsoft Defender for Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | 保护组织免受电子邮件、链接和 URL (和协作) 造成的恶意威胁。 防范恶意软件、网络钓鱼、欺骗和其他攻击类型。 建议配置 Microsoft Defender for Office 365，因为更改控制、从系统迁移设置和其他注意事项可能需要更长时间才能部署。 有关详细信息，请参阅[Microsoft Defender for Office 365。](/microsoft-365/security/office-365-security/defender-for-office-365)       |
| 5  |[Microsoft Defender for Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | 有助于防止、检测、调查和响应跨设备的高级威胁 (也称为终结点) 。 Defender for Endpoint 是一款强大的威胁防护产品。 有关详细信息，请参阅 [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)。  |
| 6  |[Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | 用于发现、调查和治理的云访问安全代理。 你可以提前Microsoft Cloud App Security开始收集数据和见解。 在 SaaS 应用中实现信息和其他目标保护涉及规划并可能需要更多时间。 有关详细信息，请参阅[什么是云应用安全？](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> 具有多个安全团队的组织可以并行实现功能。 例如，一个团队可以配置 Defender for Office 365另一个团队为终结点配置 Defender。 配置不必完全遵循我们的建议顺序。 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>规划部署威胁防护解决方案

下图演示了部署威胁防护功能的高级别流程。 

![部署威胁防护功能的过程](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

若要确保贵组织尽可能提供最佳保护，请通过包含[](deploy-threat-protection-configure.md)以下步骤的过程设置和部署安全解决方案：

1. [设置多重身份验证和条件访问策略](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)。
2. [为标识配置 Microsoft Defender。](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [打开 Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)。
4. [配置 Defender for Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)。
5. [为终结点配置 Microsoft Defender。](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [配置Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)。
7. [监视状态并采取措施](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)。
8. [培训用户](deploy-threat-protection-configure.md#step-8-train-users)。

威胁防护功能可以并行配置，因此，如果你有多个网络安全团队负责不同的服务，他们可以同时配置组织的保护功能。

## <a name="next-step"></a>后续步骤

继续跨[组织配置威胁防护Microsoft 365。](deploy-threat-protection-configure.md)


