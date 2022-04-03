---
title: Microsoft 365 零信任部署计划
f1.keywords:
- deploy zero trust
- zero trust strategy
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
description: 了解如何将零Microsoft 365安全部署到环境中，以抵御威胁和保护敏感数据。
ms.topic: tutorial
ms.prod: m365-security
ms.technology: m365d
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- m365solution-zerotrust
- m365solution-overview
- M365-security-compliance
ms.openlocfilehash: 59ebfb9ffb925cc5937802a31902e7c2342fc740
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755650"
---
# <a name="microsoft-365-zero-trust-deployment-plan"></a>Microsoft 365 零信任部署计划

本文提供了一个部署计划，用于构建零 **信任** Microsoft 365。 零信任是一种新的安全模型，它假定泄露并验证每个请求，就好像它源自不受控制的网络一样。 无论请求源自何处或它访问哪个资源，零信任模型都指导我们"从不信任，始终验证"。


## <a name="zero-trust-security-architecture"></a>零信任安全体系结构

零信任方法在整个数字资产中延伸，并充当集成的安全理念和端到端策略。 

此图提供了参与零信任的主要元素的表示形式。

:::image type="content" source="../media/zero-trust/zero-trust-architecture.png" alt-text="零信任安全体系结构" lightbox="../media/zero-trust/zero-trust-architecture.png":::

在此图中：
- 安全策略实施是零信任体系结构的中心。 这包括具有条件访问的多重身份验证，该访问会考虑用户帐户风险、设备状态以及您设置的其他条件和策略。
- 标识、设备、数据、应用、网络和其他基础结构组件均配置了适当的安全性。 为其中每个组件配置的策略与总体零信任策略协调一致。 例如，设备策略确定正常运行设备的条件，条件访问策略要求正常运行的设备访问特定应用和数据。
- 威胁防护和智能监视环境、显示当前风险，并采取自动操作来修正攻击。

<!---
For more information about this architecture, including deployment objectives for your entire digital estate, see [Zero Trust Rapid Modernization Plan (RaMP)](https://review.docs.microsoft.com/security/zero-trust/zero-trust-ramp-overview?branch=zt-content-prototype). 
-->

有关零信任详细信息，请参阅 Microsoft 的 [_**零信任指南中心**_](/security/zero-trust)。

## <a name="deploying-zero-trust-for-microsoft-365"></a>为部署零信任Microsoft 365

Microsoft 365是特意构建的，它具有许多安全和信息保护功能，可帮助你在环境中构建零信任。 可以扩展许多功能，以保护对组织使用的其他 SaaS 应用以及这些应用内的数据的访问。

此图表示部署零信任功能的工作。 此工作分为多个工作单元，可以一起配置工作，从底部开始并工作到顶部以确保先决条件工作已完成。


:::image type="content" source="../media/zero-trust/m365-zero-trust-deployment-stack.png" alt-text="Microsoft 365 零信任部署堆叠" lightbox="../media/zero-trust/m365-zero-trust-deployment-stack.png":::

在此图中：
- 零信任从标识和设备保护的基础开始。 
- 威胁防护功能基于此基础构建，可提供实时监视和修复安全威胁。 
- 信息保护和治理提供了针对特定类型的数据进行复杂控制，以保护最有价值的信息，并帮助您遵守合规性标准，包括保护个人信息。

## <a name="step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies"></a>步骤 1. 配置零信任标识和设备访问保护 — 起始点策略

第一步是通过配置标识和设备访问保护来构建零信任基础。 


:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-1b.png" alt-text="配置零信任标识和设备访问保护" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-1b.png":::



转到 [**_"零信任标识和设备访问保护_**](office-365-security/microsoft-365-policies-configurations.md) "，获取完成此操作的指导说明。 本系列文章介绍了一组标识和设备访问先决条件配置以及一组 Azure Active Directory (Azure AD) 条件访问、Microsoft Intune 和其他策略，用于保护对 Microsoft 365 用于企业云应用和服务、其他 SaaS 服务以及使用应用程序代理发布的Azure AD应用程序。



|Includes  |先决条件  |不包括  |
|---------|---------|---------|
|用于三层保护的建议标识和设备访问策略：<br>- 起始点<br>- Enterprise (推荐) <br>- 专用<br><br>针对以下项的其他建议：<br>- 外部用户 (来宾<br>- Microsoft Teams<br>- SharePoint Online<br>- 适用于云应用的 Microsoft Defender| Microsoft E3 或 E5<br><br>Azure Active Directory以下任一模式下运行：<br>- 仅云<br>- 使用密码哈希同步与 PHS (身份验证) 混合<br>- 通过 PTA 身份验证与传递 (混合) <br>- 联合     |需要托管设备的策略的设备注册。 请参阅"使用 Intune 管理终结点"以注册设备 |
| | | |

首先实现起始点层。 这些策略不需要将设备注册到管理中。 


:::image type="content" source="../media/zero-trust/identity-access-starting-point-tier.png" alt-text="零信任标识和设备访问策略 — 起始点层" lightbox="../media/zero-trust/identity-access-starting-point-tier.png":::


## <a name="step-2-manage-endpoints-with-intune"></a>步骤 2. 使用 Intune 管理终结点

接下来，将设备注册到管理中，并开始使用更复杂的控件来保护这些设备。 

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-2.png" alt-text="使用 Intune 管理终结点" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-2.png":::


转到 [**_使用 Intune 管理_**](../solutions/manage-devices-with-intune-overview.md) 设备，获得完成此操作的指导性指导。 


|Includes  |先决条件  |不包括  |
|---------|---------|---------|
|使用 Intune 注册设备<br>- 企业拥有的设备<br>- Autopilot/automated<br>- 注册<br><br>配置策略<br>- 应用保护策略<br>- 合规性策略<br>- 设备配置文件策略 | 向用户注册Azure AD     | 配置信息保护功能，包括：<br>- 敏感信息类型<br>- 标签<br>- DLP 策略<br>有关这些功能，请参阅步骤 5。 保护并控制 (本文稍后将介绍) 。       |
|    |         |         |

## <a name="step-3-add-zero-trust-identity-and-device-access-protection--enterprise-policies"></a>第 3 步。 添加零信任标识和设备访问保护 — Enterprise策略

在设备注册到管理中后，你现在可以实施一整套推荐的零信任标识和设备访问策略，要求使用合规设备。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png" alt-text="零信任标识和访问策略与设备管理" lightbox="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png":::

返回到 [**_通用标识和设备访问策略_**](office-365-security/identity-access-policies.md)，并添加新Enterprise策略。  

:::image type="content" source="../media/zero-trust/identity-access-enterprise-tier.png" alt-text="零信任标识和访问策略 — Enterprise (推荐) 层" lightbox="../media/zero-trust/identity-access-enterprise-tier.png":::

## <a name="step-4-evaluate-pilot-and-deploy-microsoft-365-defender"></a>步骤 4. 评估、试验和部署Microsoft 365 Defender

Microsoft 365 Defender是一种扩展检测和响应 (XDR) 解决方案，可自动收集、关联和分析来自 Microsoft 365 环境的信号、威胁和警报数据，包括终结点、电子邮件、应用程序和标识。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-defender.png" alt-text="将Microsoft 365 Defender添加到零信任体系结构" lightbox="../media/zero-trust/m365-zero-trust-architecture-defender.png":::

转到 [**_评估和试用Microsoft 365 Defender_**](defender/eval-overview.md)，获得有关试点和部署组件Microsoft 365 Defender指南。 

|Includes  |先决条件  |不包括  |
|---------|---------|---------|
| 设置所有组件的评估和试验环境：<br>- Defender for Identity<br>- Defender for Office 365<br>- 适用于终结点的 Defender<br>- 适用于云应用的 Microsoft Defender<br><br>抵御威胁<br><br> 调查并响应威胁   | 请参阅指南以阅读有关每个应用程序组件的体系结构Microsoft 365 Defender。        | Azure AD本解决方案指南中不包含 Identity Protection。 它包含在步骤 1：配置零信任标识和设备访问保护中。        |
|    |         |         |

## <a name="step-5-protect-and-govern-sensitive-data"></a>步骤 5. 保护并管理敏感数据

实施 Microsoft 信息保护 (MIP)，无论在何处生活或旅居在外，均可助你发现、分类和保护敏感信息。

MIP 功能包含在 Microsoft 365 合规性中，提供了了解数据、保护数据和防止数据丢失的工具。


:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-info-protect.png" alt-text="信息保护功能通过策略实施来保护数据" lightbox="../media/zero-trust/m365-zero-trust-architecture-info-protect.png":::

尽管此工作在本文前面说明的部署堆栈的顶部表示，但可以随时开始此工作。 

Microsoft 信息保护提供了可用于实现特定业务目标的框架、过程和功能。

:::image type="content" source="../media/zero-trust/mip-solution-overview.png" alt-text="Microsoft 信息保护框架" lightbox="../media/zero-trust/mip-solution-overview.png":::


若要详细了解如何计划和部署信息保护，请参阅部署Microsoft 信息保护 [**_解决方案_**](../compliance/information-protection-solution.md)。 

如果你要针对数据隐私法规部署信息保护，此解决方案指南为整个过程提供了一个建议框架：使用 Microsoft 365 部署数据 [**_隐私法规的信息保护_**](../solutions/information-protection-deploy.md)。