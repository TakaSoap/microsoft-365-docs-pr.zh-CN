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
ms.openlocfilehash: 643bb962277d30caf8ea067b9276a5986af8914f
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504511"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>使用基线部署标准租户配置的概述 

Microsoft 365 Lighthouse基线提供了一种可重复且可扩展的方法，可让你跨多个客户Microsoft 365管理安全设置。 基线提供了标准租户配置，用于部署核心安全策略和合规性标准，以确保租户的用户、设备和数据安全。

可以从 Lighthouse 内查看默认基线及其部署步骤。 若要将基线应用于租户 **，请选择左侧** 导航窗格中的"租户"，然后选择租户。 接下来，转到" **部署计划"** 选项卡以开始部署。

## <a name="lighthouse-baseline"></a>浅色基线

Lighthouse 基线配置旨在确保所有托管租户都安全且合规。 从 **左侧** 导航窗格中选择"比较基准"以查看适用于所有租户的默认基线。  若要查看默认基线中包含的部署步骤，请选择" **查看比较** 基准"以打开默认基线页。 选择任意部署步骤以查看部署详细信息和用户影响。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="&quot;默认基线&quot;页的屏幕截图。":::

### <a name="default-lighthouse-configurations"></a>默认"浅色"配置

| 基线配置 | 说明 |
|--|--|
| 要求管理员使用 MFA | 要求所有管理员进行多重身份验证的条件访问策略。 所有云应用程序都需要它。 有关此基线详细信息，请参阅条件 [访问：需要所有管理员的 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)。|
| 要求最终用户使用 MFA | 要求所有用户进行多重身份验证的条件访问策略。  所有云应用程序都需要它。 有关此基线详细信息，请参阅条件 [访问：要求所有用户使用 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。 |
| 阻止传统身份验证 | 用于阻止旧版客户端身份验证的条件访问策略。 有关此基线详细信息，请参阅使用条件访问[阻止Azure AD身份验证](/azure/active-directory/conditional-access/block-legacy-authentication)。|
| 设置设备注册 | 设备注册，允许租户设备注册Microsoft Endpoint Manager。 这是通过设置自动注册在 Azure Active Directory 和 Microsoft Endpoint Manager。 有关此基线详细信息，请参阅为设备Windows[注册](/mem/intune/enrollment/windows-enroll)。 |
| 配置Microsoft Defender 防病毒及Windows 10的自定义设置 | 具有预配置Windows配置的设备的设备Microsoft Defender 防病毒配置文件。 有关此基线详细信息，请参阅 [在 Intune 中配置 Microsoft Defender for Endpoint](/mem/intune/protect/advanced-threat-protection-configure)。|
| 配置 Microsoft Defender 防火墙Windows 10及更高版本 | 防火墙策略，通过阻止不需要和未授权的网络流量来帮助保护设备。 有关此基线详细信息，请参阅 [Best practices for configuring Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/best-practices-configuring)。  |
| 为设备配置设备合规性策略Windows 10及更高版本 | 一Windows预配置设置的设备策略，以满足基本合规性要求。 有关此基线详细信息，请参阅条件[访问：要求兼容或混合Azure AD设备](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。 |

## <a name="deployment-plans"></a>部署计划

每个活动租户都有一个部署计划，其中包括部署基线中的Microsoft 365 Lighthouse步骤。 若要访问租户的部署计划，请从"租户"页上的列表中选择活动租户，然后选择"部署 **计划"** 选项卡。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/deployment-plan-tab.png" alt-text="&quot;部署计划&quot;选项卡的屏幕截图。":::

"部署计划"选项卡包含以下信息：


|列  |说明  |
|---------|---------|
|部署步骤     |  部署步骤的说明。       |
|状态     |部署步骤的状态。         |
|基线     |从中派生部署步骤的基线。         |
|类别     | 部署步骤是否与管理设备、标识或数据相关联。        |
|上次更新    | 上次更新部署步骤的日期。        |


"部署计划"选项卡还包括以下选项：

- **导出：** 选择将部署步骤数据导出到Excel逗号分隔值 (.csv) 文件中。
- **刷新：** 选择以检索最新的部署步骤数据。
- **搜索：** 输入关键字以快速找到列表中的特定部署步骤。

## <a name="deployment-steps-and-processes"></a>部署步骤和过程

每个租户的部署计划包括部署基线中的Microsoft 365 Lighthouse步骤。 每个部署步骤由一个或多个流程组成，需要完成这些流程以满足部署步骤的要求。 当新租户变为活动租户时，必须完成与部署步骤和流程关联的部署活动。

对于每个部署步骤，可以执行以下操作：

|操作  |说明  |
|---------|---------|
| 共享    |  允许通过链接或通过电子邮件共享部署步骤的内容。    |
| 查看和部署    |  使用户能够： <ul><li>如果受支持，请将部署步骤中的配置设置与任何现有策略中的设置进行比较，而无需将设置部署到租户。<br>以下部署步骤支持比较：</br><ul><li>为设备配置设备合规性策略Windows 10及更高版本</li><li>要求最终用户使用 MFA</li><li>要求管理员使用 MFA</li><li>阻止传统身份验证</li></ul></li> <li>将配置设置部署到租户。</li></ul>**注意：** 不支持在不将设置部署到租户的情况下进行比较的步骤将使您能够查看配置设置并部署这些设置。|
| 更新行动计划状态    |  使用户能够报告其部署步骤的行动计划的状态。      |

## <a name="related-content"></a>相关内容

[Deploy Microsoft 365 Lighthouse baselines (](m365-lighthouse-deploy-baselines.md) article) \
[常见条件访问策略](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) (文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
