---
title: 建议的安全文档策略 - Microsoft 365策略|Microsoft Docs
description: 介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。
ms.author: dansimp
author: dansimp
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 3057e66352b9bd658ddd4958986cbefd61e4e187
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682936"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>用于保护网站和SharePoint的策略建议

本文介绍如何实施推荐的零信任标识和设备访问策略来保护SharePoint OneDrive for Business。 本指南基于通用 [标识和设备访问策略](identity-access-policies.md)。

这些建议基于三种不同的安全层和保护 SharePoint 文件，这些文件可以基于你的需求粒度应用：起始点、企业和 **专用安全**。  你可以了解有关这些安全层以及建议的客户端操作系统（概述中这些建议所引用） [的更多信息](microsoft-365-policies-configurations.md)。

除了实施本指南之外，请确保为SharePoint网站配置适当的保护，包括为企业和专用安全内容设置适当的权限。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>更新常见策略以包括SharePoint和OneDrive for Business

若要保护 SharePoint 和 OneDrive 中的文件，下图说明了从通用标识和设备访问策略更新的策略。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png" alt-text="用于保护对应用程序的访问权限的策略更新SharePoint。" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png":::

如果在创建SharePoint策略时包括了策略，则只需创建新策略。 对于条件访问策略，SharePoint包括OneDrive。

新策略通过向指定的网站应用特定访问要求，为企业和专用安全内容SharePoint设备保护。

下表列出了需要查看和更新的策略，或创建新的SharePoint。 常见策略链接到常见标识和设备访问策略文章中的关联 [配置说明](identity-access-policies.md) 。

|保护级别|策略|更多信息|
|---|---|---|
|**起点**|[当登录风险为中或高 *时需要 MFA*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|将SharePoint包括在云应用的分配中。|
||[阻止不支持新式身份验证的客户端](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|将SharePoint包括在云应用的分配中。|
||[应用 APP 数据保护策略](identity-access-policies.md#apply-app-data-protection-policies)|请确保所有推荐的应用都包含在应用列表中。 请务必为 iOS、Android、 (的每个平台更新Windows) 。|
||[在应用中使用应用强制SharePoint](#use-app-enforced-restrictions-in-sharepoint)|添加新策略。 这将Azure Active Directory (Azure AD) 使用 SharePoint 中指定的设置。 此策略适用于所有用户，但仅影响对访问策略中包含的SharePoint的访问。|
|企业|[登录风险低、中或高 *时需要 MFA*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|将SharePoint包括在云应用的分配中。|
||[要求兼容电脑 *和* 移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|将SharePoint包括在云应用列表中。|
||[SharePoint访问控制策略](#sharepoint-access-control-policies)：允许仅浏览器访问SharePoint非托管设备中的特定网站。|这将阻止编辑和下载文件。 使用 PowerShell 指定网站。|
|**专用安全**|[*始终* 需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|将SharePoint包括在云应用的分配中。|
||[SharePoint访问控制策略](#use-app-enforced-restrictions-in-sharepoint)：阻止从非SharePoint访问特定网站。|使用 PowerShell 指定网站。|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>在应用中使用应用强制SharePoint

如果在 SharePoint 中实现访问控制，则必须在 Azure AD 创建此条件访问策略Azure AD以强制实施在 SharePoint 中配置的策略。 此策略适用于所有用户，但仅影响在使用 PowerShell 创建访问控件时对使用 PowerShell 指定的SharePoint。

若要配置此策略，请参阅控制从非托管设备SharePoint或OneDrive访问"中的"阻止或限制对特定网站集或帐户[的访问权限"](/sharepoint/control-access-from-unmanaged-devices)。

## <a name="sharepoint-access-control-policies"></a>SharePoint访问控制策略

Microsoft 建议通过设备访问控制SharePoint企业专用安全内容来保护网站中的内容。 为此，可创建一个策略，指定保护级别以及要应用保护的网站。

- Enterprise网站：允许仅浏览器访问。 这将阻止用户编辑和下载文件。
- 专用安全网站：阻止来自非托管设备的访问。

请参阅控制从非托管设备SharePoint访问中的"阻止或OneDrive访问特定网站集或帐户["](/sharepoint/control-access-from-unmanaged-devices)。

## <a name="how-these-policies-work-together"></a>这些策略如何协同工作

必须了解的是，SharePoint权限通常基于访问网站的业务需求。 这些权限由网站所有者管理，可以是高度动态的。 使用 SharePoint访问策略可确保保护这些站点，无论用户被分配到的 Azure AD 组与起始点、企业还是专门的安全保护相关联。

下图提供了一个示例，SharePoint访问策略如何保护用户对网站的访问。

:::image type="content" source="../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png" alt-text="设备访问SharePoint如何保护网站的示例。" lightbox="../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png":::

为一位用户分配了起点条件访问策略，但可以SharePoint企业或专门的安全保护访问这些网站。

- 如果为用户是使用电脑进行企业或专门安全保护的网站的一员，则授予他的访问权。
- 如果为一个企业保护网站访问，则他将成为使用非托管电话（允许起始点用户使用）的成员，由于为此网站配置了设备访问策略，他将收到仅浏览器访问企业网站的访问权限。
- 如果作为使用非托管电话的会员的一员，则他将被阻止，因为为此网站配置了访问策略。 他只能使用自己的托管电脑访问此网站。

## <a name="next-step"></a>后续步骤

![步骤 4：云Microsoft 365策略。](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

为：配置条件访问策略：

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)