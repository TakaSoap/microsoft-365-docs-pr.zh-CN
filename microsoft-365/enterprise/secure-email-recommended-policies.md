---
title: 安全电子邮件推荐策略-适用于企业的 Microsoft 365 |Microsoft 文档
description: 介绍针对有关如何应用电子邮件策略和配置的 Microsoft 建议的策略。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: cff9413a7c580fbefd51e48acfc9610b2b07430f
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295510"
---
# <a name="policy-recommendations-for-securing-email"></a>用于保护电子邮件的策略建议

本文介绍如何实现建议的标识和设备访问策略，以保护支持新式身份验证和条件访问的组织电子邮件和电子邮件客户端。 本指南建立在 [通用标识和设备访问策略](identity-access-policies.md) 之上，还包括一些其他建议。

这些建议基于三种不同的安全性和保护层，可根据您需求的粒度进行应用： **比较基准**、 **敏感**和 **高度管控**。 You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).

这些建议要求用户使用新式电子邮件客户端，包括移动设备上的 Outlook for iOS 和 Outlook for Android。 适用于 iOS 和 Android 的 Outlook 提供了对 Office 365 最佳功能的支持。 这些移动 Outlook 应用程序还使用支持移动使用的安全功能以及与其他 Microsoft 云安全功能配合使用的安全功能。 有关详细信息，请参阅 [Outlook For iOS 和 ANDROID FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。

## <a name="updating-common-policies-to-include-email"></a>更新常见策略以包含电子邮件

为了保护电子邮件，下图说明了要从通用标识和设备访问策略中更新的策略。

[![用于保护对团队及其依赖服务的访问权限的策略更新的摘要](../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[查看此图像的更大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

请注意，为 Exchange Online 添加新策略以阻止 ActiveSync 客户端。 这将强制使用 Outlook mobile。

如果在设置 Exchange Online 和 Outlook 时将其包含在策略范围中，则只需创建新策略来阻止 ActiveSync 客户端。 查看下表中列出的策略，并执行建议的添加项，或者确认是否已包含这些策略。 每个策略链接到 [常见标识和设备访问策略](identity-access-policies.md)中的关联配置说明。

|保护级别|策略|详细信息|
|:---------------|:-------|:----------------|
|**Baseline**|[当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在云应用的分配中包括 Exchange Online|
|        |[阻止不支持新式身份验证的客户端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|在云应用的分配中包括 Exchange Online|
|        |[应用应用数据保护策略](identity-access-policies.md#apply-app-data-protection-policies)|确保 Outlook 包含在应用程序列表中。 请务必为每个平台 (iOS、Android、Windows) 更新策略|
|        |[需要经批准的应用和应用保护](identity-access-policies.md#require-approved-apps-and-app-protection)|在云应用列表中包括 Exchange Online|
|        |[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|在云应用列表中加入 Exchange Online|
|        |[阻止 ActiveSync 客户端](#block-activesync-clients)|添加此新策略| 
|**敏感**|[当登录风险为*低*、*中*或*高*时，需要进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| 在云应用的分配中包括 Exchange Online|
|         |[需要符合要求 *的 pc 和* 移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|在云应用列表中包括 Exchange Online|
|**高度管控**|[*始终* 要求进行 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在云应用的分配中包括 Exchange Online|

## <a name="block-activesync-clients"></a>阻止 ActiveSync 客户端

此策略将阻止 ActiveSync 客户端绕过其他条件访问策略。 策略配置仅适用于 ActiveSync 客户端。 通过选择 " **[需要应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**"，此策略将阻止 ActiveSync 客户端。 有关创建此策略的详细信息，请参阅 [需要使用条件访问的云应用访问的应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。

- 按照 "第2步：为 Exchange Online 配置 Azure AD 条件访问策略" 中的 "应用 ActiveSync (EAS) " 中的 [方案1： Office 365 应用程序需要批准的应用程序使用应用保护策略](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)，这会阻止 Exchange ActiveSync 客户端利用基本身份验证连接到 Exchange Online。

您还可以使用身份验证策略 [禁用基本身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)，这将强制所有客户端访问请求使用新式验证。

## <a name="set-up-message-encryption"></a>设置邮件加密

使用新的 Office 365 邮件加密 (OME) 功能，利用 Azure 信息保护中的保护功能，您的组织可以轻松地与任何设备上的任何人共享受保护的电子邮件。 用户可以使用 Outlook.com、Gmail 和其他电子邮件服务发送和接收与其他 Microsoft 365 组织以及非客户的受保护邮件。

有关详细信息，请参阅 [设置新的 Office 365 邮件加密功能](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)。

## <a name="next-steps"></a>后续步骤

![步骤4： Microsoft 365 云应用的策略](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

为以下项配置条件访问策略：

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](secure-email-recommended-policies.md)
