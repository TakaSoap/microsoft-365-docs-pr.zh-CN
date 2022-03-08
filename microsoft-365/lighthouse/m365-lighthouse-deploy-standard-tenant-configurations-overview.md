---
title: 使用基线部署标准租户配置的概述
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，了解如何使用基线部署标准租户配置。
ms.openlocfilehash: f59ca686892e0b20ce5e9ffb6d62859ce8079896
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323145"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>使用基线部署标准租户配置的概述 

Microsoft 365 Lighthouse基线提供了一种可重复且可扩展的方法，可让你跨多个客户Microsoft 365管理安全设置。 基线还有助于使用保护用户、设备和数据的配置监视核心安全策略和租户合规性标准。

为帮助托管服务提供商 (MSP) 客户采用安全性，Lighthouse 提供了一组标准的基线参数和预定义的配置，Microsoft 365服务。 这些安全配置可帮助衡量租户Microsoft 365安全性和合规性进度。

可以从 Lighthouse 内查看默认基线及其部署步骤。 若要将基线应用于租户 **，请选择左侧** 导航窗格中的"租户"，然后选择租户。 接下来，转到"部署 **计划"** 选项卡，然后实现基线。

## <a name="default-baseline-security-templates"></a>默认基线安全模板

安全工作负载的浅色默认基线配置旨在确保所有托管租户都安全合规。

下表中的基线配置与 Lighthouse 默认基线一起采用标准配置。<br><br>

| 基线配置 | 说明 |
|--|--|
| 要求管理员使用 MFA | 要求所有管理员进行多重身份验证的条件访问策略。 所有云应用程序都需要它。 有关此基线详细信息，请参阅条件 [访问：需要所有管理员的 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)。|
| 要求最终用户使用 MFA | 要求所有用户进行多重身份验证的条件访问策略。  所有云应用程序都需要它。 有关此基线详细信息，请参阅条件 [访问：要求所有用户使用 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。 |
| 阻止传统身份验证 | 用于阻止旧版客户端身份验证的条件访问策略。 有关此基线详细信息，请参阅使用条件访问[阻止Azure AD身份验证](/azure/active-directory/conditional-access/block-legacy-authentication)。|
| 设置设备注册 | 设备注册，允许租户设备注册Microsoft Endpoint Manager。 这是通过设置自动注册在 Azure Active Directory 和 Microsoft Endpoint Manager。 有关此基线详细信息，请参阅为设备Windows[注册](/mem/intune/enrollment/windows-enroll)。 |
| 配置Microsoft Defender 防病毒及Windows 10的自定义设置 | 具有预配置Windows配置的设备的设备Microsoft Defender 防病毒配置文件。 有关此基线详细信息，请参阅 [在 Intune 中配置 Microsoft Defender for Endpoint](/mem/intune/protect/advanced-threat-protection-configure)。|
| 配置 Microsoft Defender 防火墙Windows 10及更高版本 | 防火墙策略，通过阻止不需要和未授权的网络流量来帮助保护设备。 有关此基线详细信息，请参阅 [Best practices for configuring Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/best-practices-configuring)。  |
| 为设备配置设备合规性策略Windows 10及更高版本 | 一Windows预配置设置的设备策略，以满足基本合规性要求。 有关此基线详细信息，请参阅条件[访问：要求兼容或混合Azure AD设备](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。 |


## <a name="related-content"></a>相关内容

[Deploy Microsoft 365 Lighthouse baselines (](m365-lighthouse-deploy-baselines.md) article) \
[常见条件访问策略](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) (文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
