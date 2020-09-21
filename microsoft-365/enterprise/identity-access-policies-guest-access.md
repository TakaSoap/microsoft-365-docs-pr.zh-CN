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
ms.openlocfilehash: 6d6562f528b36acdfbc28da9647d3356a0f585af
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132154"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>允许来宾和外部 B2B 访问的策略

本文介绍如何调整建议的公共标识和设备访问策略，以允许来宾和具有 Azure Active Directory (Azure AD) 企业到企业 (B2B) 帐户的外部用户访问。 本指南建立在 [通用标识和设备访问策略](identity-access-policies.md)之上。

这些建议旨在适用于保护的 **基准** 层。 不过，您还可以根据您对 **敏感** 和 **高度管控** 保护的需求的粒度来调整建议。 

为 B2B 帐户提供用于对 Azure AD 租户进行身份验证的路径不会为这些帐户授予对你的整个环境的访问权限。 B2B 用户及其帐户只能访问与他们共享的资源 (如在条件访问策略中授予的服务中) 的文件。

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>更新常见策略以允许和保护来宾和外部访问 

若要使用 Azure AD B2B 帐户保护来宾和外部访问，下图说明了要从通用标识和设备访问策略中添加或更新的策略。 

[![保护来宾访问的策略更新摘要](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[查看此图像的更大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

下表列出了您需要创建和更新的策略。 常见策略链接到 [常见标识和设备访问策略](identity-access-policies.md) 文章中相关的配置说明。

|保护级别|策略|更多信息|
|:---------------|:-------|:----------------|
|**Baseline**|[要求为来宾和外部用户始终进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|创建此新策略并配置： <ul><li> 对于 **> 包括的用户和组 > 的工作分配**，请选择 " **选择用户和组**"，然后选择 " **所有来宾和外部用户**"。 </li><li> 对于 **工作分配 > 条件 > 登录**，请将所有选项保留为选中状态，以始终强制实施多重身份验证 (MFA) 。</li>|
|        |[当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|修改此策略以排除来宾和外部用户。|
|        |[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|修改此策略以排除来宾和外部用户。|

若要在条件访问策略中包括或排除来宾和外部用户，对于 > 包含或**排除**的**用户和组 > 的工作分配**，请检查**所有来宾和外部用户**。

![用于排除来宾和外部用户的控件的屏幕捕获](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>更多信息

### <a name="guest-and-external-access-with-microsoft-teams"></a>Microsoft 团队的来宾和外部访问

Microsoft 团队定义了以下内容：

- **来宾访问** 使用可添加为团队成员的 AZURE AD B2B 帐户，并拥有对团队的通信和资源的所有具有独特权限访问权限。

- **外部访问** 适用于没有 B2B 帐户的外部用户。 外部访问可以包括邀请和参与呼叫、聊天和会议，但不包括团队成员资格和对团队资源的访问权限。

有关详细信息，请参阅对 [团队的来宾和外部访问之间的比较](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。

条件访问策略仅适用于团队中的来宾访问，因为存在相应的 Azure AD B2B 帐户。

有关保护团队的标识和设备访问策略的详细信息，请参阅 [保护团队聊天、组和文件的策略建议](teams-access-policies.md) 。

<!--
ount treats guest and external users that have an Azure AD B2B account differently than external access  .


to a meeting, call, or chat with


differentiates between guest users and external users within the app. Guest users have Azure AD B2B accounts and can be added to teams. External users can only participate in calls, chats, and meetings. 
--> 

### <a name="require-mfa-always-for-guest-and-external-users"></a>要求为来宾和外部用户始终进行 MFA
此策略将提示来宾在你的租户中注册 MFA，而不考虑是否在其家乡租户中向 MFA 注册了这些。 在访问租户中的资源时，来宾和外部用户需要对每个请求使用 MFA。 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>从基于风险的 MFA 中排除来宾和外部用户
虽然组织可以使用 Azure AD 标识保护为 B2B 用户强制实施基于风险的策略，但由于在其主目录中存在其标识，对资源目录中的 B2B 协作用户实施 Azure AD 标识保护有一些限制。 由于这些限制，Microsoft 建议您将来宾用户从基于风险的 MFA 策略中排除，并要求这些用户始终使用 MFA。 

有关详细信息，请参阅 [针对 B2B 协作用户的标识保护的限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。 

### <a name="excluding-guest-and-external-users-from-device-management"></a>从设备管理中排除来宾和外部用户 
只有一个组织可以管理一个设备。 如果不从需要设备符合性的策略中排除来宾和外部用户，则这些策略将阻止这些用户。 

## <a name="next-step"></a>后续步骤

![步骤4： Microsoft 365 云应用的策略](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

为以下项配置条件访问策略：

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

