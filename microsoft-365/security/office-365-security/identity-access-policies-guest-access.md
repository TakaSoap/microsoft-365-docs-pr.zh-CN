---
title: 用于允许来宾和外部用户 B2B 访问的标识和设备访问策略 - Microsoft 365企业|Microsoft Docs
description: 介绍用于保护来宾和外部用户访问的建议条件访问和相关策略。
ms.prod: m365-security
ms.topic: article
ms.author: dansimp
author: dansimp
audience: Admin
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 28b389292ed733318e5796a1be3ed9c11d2df462
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466600"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>允许来宾访问和 B2B 外部用户访问的策略

本文讨论调整推荐的零信任标识和设备访问策略，以允许具有 Azure Active Directory (Azure AD) 企业到企业 (B2B) 帐户的来宾和外部用户访问。 本指南基于通用 [标识和设备访问策略](identity-access-policies.md)。

这些建议旨在应用于保护 **的起点** 层。 但是，也可以根据企业的特定需要和专门的安全 **保护调整****建议**。

如果为 B2B 帐户提供一个向 Azure AD 进行身份验证的路径，这些帐户将无法访问整个环境。 B2B 用户及其帐户具有通过条件访问策略与它们共享的服务和资源（如文件）的访问权限。

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>更新常用策略以允许和保护来宾和外部用户访问

此图显示了在 B2B 来宾和外部用户访问的常见标识和设备访问策略中添加或更新的策略。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png" alt-text="用于保护来宾访问的策略更新摘要" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png":::

下表列出了创建和更新所需的策略。 常见策略链接到常见标识和设备访问策略文章中的关联 [配置说明](identity-access-policies.md) 。

|保护级别|策略|更多信息|
|---|---|---|
|**起点**|[始终要求来宾和外部用户使用 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|创建新策略并配置： <ul><li>对于 **">包括** 的用户和组>，选择"选择用户 **和** 组"，然后选择"所有 **来宾用户和外部用户"**。</li><li>对于 **">条件>登录"**，保留所有选项未选中状态，以始终对 MFA (多重) 。</li></ul>|
||[当登录风险为中或高 *时需要 MFA*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|修改此策略以排除来宾和外部用户。|

若要在条件访问策略中包括或排除来宾和外部用户，>分配""用户和>排除"，请检查 **"所有** 来宾用户和 **外部用户"**。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png" alt-text="用于排除来宾和外部用户的控件" lightbox="../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png":::

## <a name="more-information"></a>详细信息

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>来宾和外部用户访问Microsoft Teams

Microsoft Teams定义以下用户：

- **来宾访问** 使用Azure AD B2B 帐户，该帐户可添加为团队成员，并且有权访问团队的通信和资源。

- **外部** 访问适用于没有 B2B 帐户的外部用户。 外部用户访问包括邀请、通话、聊天和会议，但不包括团队成员身份和团队资源的访问权限。

有关详细信息，请参阅来宾 [和团队的外部用户访问之间的比较](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。

有关保护用户标识和设备访问策略Teams，请参阅用于保护用户Teams、组和[文件的策略建议](teams-access-policies.md)。

### <a name="require-mfa-always-for-guest-and-external-users"></a>始终对来宾用户和外部用户要求 MFA

此策略会提示来宾在租户中注册 MFA，而不考虑来宾是否在主租户中注册了 MFA。 访问租户中的资源时，来宾和外部用户需要针对每个请求使用 MFA。

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>从基于风险的 MFA 中排除来宾和外部用户

虽然组织可以使用 Azure AD Identity Protection 对 B2B 用户强制执行基于风险的策略，但由于 B2B 协作用户的身份已保留于其主目录中，因此，在资源目录中实现 Azure AD Identity Protection 存在一些限制。 由于这些限制，Microsoft 建议你将来宾从基于风险的 MFA 策略中排除，并要求这些用户始终使用 MFA。

有关详细信息，请参阅 [Identity Protection for B2B collaboration users的限制](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。

### <a name="excluding-guests-and-external-users-from-device-management"></a>从设备管理中排除来宾和外部用户

只有一个组织可以管理设备。 如果未将来宾和外部用户从要求设备符合性的策略中排除，这些策略将阻止这些用户。

## <a name="next-step"></a>后续步骤

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="云应用Microsoft 365 Microsoft Defender 云应用策略" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

为：配置条件访问策略：

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
- [Microsoft Defender for Cloud Apps](mcas-saas-access-policies.md)
 
