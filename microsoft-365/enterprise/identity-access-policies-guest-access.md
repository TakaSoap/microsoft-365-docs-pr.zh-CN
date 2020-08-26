---
title: 允许来宾和外部 B2B 访问的标识和设备访问策略-Microsoft 365 for enterprise |Microsoft 文档
description: 描述建议的条件访问和用于保护来宾和外部用户访问的相关策略。
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: ad1203543db1c2bd0ea9e9bdd3433aad58db320b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898100"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>允许来宾和外部 B2B 访问的策略
本文介绍如何调整建议的公共标识和设备访问策略，以允许 (来宾和外部用户的 B2B 帐户访问) 。 本指南建立在 [通用标识和设备访问策略](identity-access-policies.md)之上。

这些建议旨在适用于保护的 **基准** 层。 但是，您可以根据您对 **敏感** 和 **高度管控** 保护的需求的粒度来调整建议。 

为 B2B 用户提供用于对你的 Azure AD 租户进行身份验证的路径不会为这些用户授予对你的整个环境的访问权限。 B2B 用户只能访问与他们共享的资源 (例如，在条件访问策略中授予的服务中) 文件。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>更新常见策略以允许和保护来宾和外部访问 

下图说明了常见标识和设备访问策略，并指示 (带有铅笔图标) 要添加或更新以保护来宾和外部访问权限的策略。 

![保护来宾访问的策略更新摘要](../media/identity-access-ruleset-guest.png)

下表列出了您需要更新或创建新的策略。 常见策略链接到 [常见标识和设备访问策略](identity-access-policies.md) 文章中相关的配置说明。

|保护级别|策略|更多信息|
|:---------------|:-------|:----------------|
|**Baseline**|[要求为来宾和外部用户始终进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|创建此新规则并仅将其应用于来宾和外部用户。 在 "登录风险" 下，将所有选项保留为未选中状态，以始终强制执行 MFA。|
|        |[当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|修改此规则以排除来宾和外部用户。|
|        |[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|修改此规则以排除来宾和外部用户。|

若要在条件访问规则中包括或排除来宾和外部用户，请单击 "包含" 或 "排除" 选项卡，并检查 **所有来宾和外部用户**。

![用于排除来宾的控件的屏幕捕获](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>更多信息

### <a name="guests-vs-external-users"></a>来宾和外部用户
在 Azure AD 中，来宾和外部用户是相同的。 这两个用户的用户类型为 "来宾"。 来宾用户是 B2B 用户。

Microsoft 团队在应用程序中区分来宾用户和外部用户，但在进行身份验证时，这两个用户都是 B2B 用户。 有关团队来宾和外部用户的详细信息，请参阅 [为团队启用来宾和外部访问](teams-access-policies.md#enabling-guest-and-external-access-for-teams)。

### <a name="require-mfa-always-for-guest-and-external-users"></a>要求为来宾和外部用户始终进行 MFA
此规则将提示来宾在你的租户中注册 MFA，而不考虑是否在其家乡租户中为 MFA 注册了这些规则。 在访问租户中的资源时，来宾和外部用户需要对每个请求使用 MFA。 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>从基于风险的 MFA 中排除来宾和外部用户
虽然组织可以使用身份保护为 B2B 用户强制实施基于风险的策略，但由于在其主目录中存在其标识，因此在资源目录中对 B2B 协作用户实施身份保护有一些限制。 由于这些限制，Microsoft 建议您将来宾用户从基于风险的 MFA 策略中排除，并要求这些用户始终使用 MFA。 

有关详细信息，请参阅 [针对 B2B 协作用户的标识保护的限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。 

### <a name="excluding-guest-and-external-users-from-device-management"></a>从设备管理中排除来宾和外部用户 
只有一个组织可以管理一个设备。 如果不从需要设备符合性的策略中排除来宾和外部用户，则这些策略将阻止这些用户。 

## <a name="next-steps"></a>后续步骤

[了解如何启用团队条件访问](teams-access-policies.md)

