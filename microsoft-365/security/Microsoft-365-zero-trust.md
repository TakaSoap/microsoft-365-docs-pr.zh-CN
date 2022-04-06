---
title: Microsoft 365 零信任部署计划
f1.keywords:
- deploy zero trust
- zero trust strategy
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
description: 了解如何将Microsoft 365 零信任安全部署到环境中以防范威胁和保护敏感数据。
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
ms.openlocfilehash: 879cbe33393158ee9e24107bbe042adc2f727ac6
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667199"
---
# <a name="microsoft-365-zero-trust-deployment-plan"></a>Microsoft 365 零信任部署计划

本文提供了使用 **Microsoft 365生成零信任** 安全性的部署计划。 零信任是一种新的安全模型，假定存在漏洞并验证每个请求，就好像它源自不受控制的网络一样。 无论请求源自何处或它访问什么资源，零信任模型都告诉我们"永远不要信任，始终进行验证"。

## <a name="zero-trust-security-architecture"></a>零信任安全体系结构

零信任方法扩展到整个数字资产，并作为一种综合的安全理念和端到端策略。

此图提供了有助于零信任的主要元素的表示形式。

:::image type="content" source="../media/zero-trust/zero-trust-architecture.png" alt-text="零信任安全体系结构" lightbox="../media/zero-trust/zero-trust-architecture.png":::

在此图中：

- 安全策略实施是零信任体系结构的核心。 这包括具有条件访问的多重身份验证，这些访问考虑到了用户帐户风险、设备状态以及你设置的其他条件和策略。
- 标识、设备、数据、应用、网络和其他基础结构组件都配置了适当的安全性。 为每个组件配置的策略与整体零信任策略相协调。 例如，设备策略确定正常设备的条件，条件访问策略需要正常设备才能访问特定应用和数据。
- 威胁防护和情报监视环境，显示当前风险，并采取自动行动来修正攻击。

<!---
For more information about this architecture, including deployment objectives for your entire digital estate, see [Zero Trust Rapid Modernization Plan (RaMP)](https://review.docs.microsoft.com/security/zero-trust/zero-trust-ramp-overview?branch=zt-content-prototype).
-->

有关零信任的详细信息，请参阅 Microsoft 的 [_**零信任 指导中心**_](/security/zero-trust)。

## <a name="deploying-zero-trust-for-microsoft-365"></a>为Microsoft 365部署零信任

Microsoft 365是有意构建的，具有许多安全和信息保护功能，可帮助你在环境中构建零信任。 可以扩展许多功能，以保护对组织使用的其他 SaaS 应用以及这些应用中的数据的访问。

此图表示部署零信任功能的工作。 此工作分为可一起配置的工作单元，从底部开始，一直工作到顶部，以确保先决条件工作完成。

:::image type="content" source="../media/zero-trust/m365-zero-trust-deployment-stack.png" alt-text="Microsoft 365 零信任部署堆栈" lightbox="../media/zero-trust/m365-zero-trust-deployment-stack.png":::

在此图中：

- 零信任从标识和设备保护的基础开始。
- 威胁防护功能是建立在此基础之上的，用于提供安全威胁的实时监视和修正。
- 信息保护和治理提供针对特定数据类型的复杂控制，以保护最有价值的信息，并帮助你遵守合规性标准，包括保护个人信息。

## <a name="step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies"></a>步骤 1. 配置零信任标识和设备访问保护 - 起始点策略

第一步是通过配置标识和设备访问保护来构建零信任基础。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-1b.png" alt-text="配置零信任标识和设备访问保护的过程" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-1b.png":::

转到 [**_零信任标识和设备访问保护_**](office-365-security/microsoft-365-policies-configurations.md)以获取规范性指导来实现此目的。 本系列文章介绍一组标识和设备访问先决条件配置以及一组Azure Active Directory (Azure AD) 条件访问、Microsoft Intune和其他策略，以保护对Microsoft 365的访问 对于使用Azure AD 应用程序代理发布的企业云应用和服务、其他 SaaS 服务和本地应用程序。

|Includes|先决条件|不包括|
|---------|---------|---------|
|三层保护的建议标识和设备访问策略： <ul><li>起点</li><li>建议Enterprise () </li><li>专业</li></ul> <br> 有关以下内容的其他建议： <ul><li>外部用户 (来宾) </li><li>Microsoft Teams</li><li>SharePoint Online</li><li>Microsoft Defender for Cloud Apps</lu></ul>|Microsoft E3 或 E5 <br><br> Azure Active Directory以下任一模式： <ul><li>仅限云</li><li>使用密码哈希同步混合 (PHS) 身份验证</li><li>与直通身份验证 (PTA) 混合</li><li>联邦</li></ul>|需要托管设备的策略的设备注册。 请参阅[步骤 2。使用Intune管理终结点](#step-2-manage-endpoints-with-intune)以注册设备|

首先实现起始层。 这些策略不需要将设备注册到管理中。

:::image type="content" source="../media/zero-trust/identity-access-starting-point-tier.png" alt-text="零信任标识和设备访问策略 - 起始点层" lightbox="../media/zero-trust/identity-access-starting-point-tier.png":::

## <a name="step-2-manage-endpoints-with-intune"></a>步骤 2. 使用Intune管理终结点

接下来，将设备注册到管理中，并开始使用更复杂的控件保护这些设备。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-2.png" alt-text="使用Intune元素管理终结点" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-2.png":::

转到 [**_"使用Intune管理设备_**](../solutions/manage-devices-with-intune-overview.md)以获取规范性指导来实现此目的。

|Includes|先决条件|不包括|
|---------|---------|---------|
|使用Intune注册设备： <ul><li>公司拥有的设备</li><li>Autopilot/automated</li><li>招生</li></ul> <br> 配置策略： <ul><li>应用保护策略</li><li>合规性策略</li><li>设备配置文件策略</li></ul>|使用Azure AD注册终结点|配置信息保护功能，包括： <ul><li>敏感信息类型</li><li>标签</li><li>DLP 策略</li></ul> <br> 有关这些功能，请参阅 [步骤 5。本文稍后) 保护和管理敏感数据](#step-5-protect-and-govern-sensitive-data) (。|

## <a name="step-3-add-zero-trust-identity-and-device-access-protection--enterprise-policies"></a>步骤 3. 添加零信任标识和设备访问保护 - Enterprise策略

通过将设备注册到管理中，现在可以实现一整套建议的零信任标识和设备访问策略，这需要符合要求的设备。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png" alt-text="使用设备管理零信任标识和访问策略" lightbox="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png":::

返回到 [**_Common 标识和设备访问策略_**](office-365-security/identity-access-policies.md)，并在Enterprise层中添加策略。

:::image type="content" source="../media/zero-trust/identity-access-enterprise-tier.png" alt-text="零信任标识和访问策略 - Enterprise (建议的) 层" lightbox="../media/zero-trust/identity-access-enterprise-tier.png":::

## <a name="step-4-evaluate-pilot-and-deploy-microsoft-365-defender"></a>步骤 4. 评估、试点和部署Microsoft 365 Defender

Microsoft 365 Defender是 XDR) 解决方案 (扩展检测和响应，可自动收集、关联和分析来自Microsoft 365环境中的信号、威胁和警报数据，包括终结点、电子邮件、应用程序和标识。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-defender.png" alt-text="将Microsoft 365 Defender添加到零信任体系结构的过程" lightbox="../media/zero-trust/m365-zero-trust-architecture-defender.png":::

转到 [**_"评估"和"试点Microsoft 365 Defender_**](defender/eval-overview.md)，了解有关试点和部署Microsoft 365 Defender组件的有条不紊的指南。

|Includes|先决条件|不包括|
|---------|---------|---------|
|为所有组件设置评估和试点环境： <ul><li>Defender for Identity</li><li>Defender for Office 365</li><li>Defender for Endpoint</li><li>Microsoft Defender for Cloud Apps</li></ul> <br> 抵御威胁 <br><br> 调查并响应威胁|请参阅有关Microsoft 365 Defender的每个组件的体系结构要求的指南。| 此解决方案指南中未包含Azure AD标识保护。 它包含在[步骤 1 中。配置零信任标识和设备访问保护](#step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies)。|

## <a name="step-5-protect-and-govern-sensitive-data"></a>步骤 5. 保护和管理敏感数据

实施 Microsoft 信息保护 (MIP)，无论在何处生活或旅居在外，均可助你发现、分类和保护敏感信息。

MIP 功能包含在 Microsoft 365 合规性中，提供了了解数据、保护数据和防止数据丢失的工具。

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-info-protect.png" alt-text="通过策略强制保护数据的信息保护功能" lightbox="../media/zero-trust/m365-zero-trust-architecture-info-protect.png":::

虽然此工作在本文前面所示的部署堆栈顶部表示，但你可以随时开始此工作。

Microsoft 信息保护提供可用于实现特定业务目标的框架、流程和功能。

:::image type="content" source="../media/zero-trust/mip-solution-overview.png" alt-text="Microsoft 信息保护 (MIP) 框架" lightbox="../media/zero-trust/mip-solution-overview.png":::

有关如何规划和部署信息保护的详细信息，请 [**_参阅部署Microsoft 信息保护解决方案_**](../compliance/information-protection-solution.md)。

如果要为数据隐私法规部署信息保护，本解决方案指南为整个过程提供了一个建议的框架：[**_使用Microsoft 365为数据隐私法规部署信息保护_**](../solutions/information-protection-deploy.md)。
