---
title: 建议的安全文档策略 - Microsoft 365 企业版|Microsoft Docs
description: 介绍 Microsoft 建议中有关如何保护 SharePoint 文件访问的策略。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: a3485896cae5e41808cfd16a77d484a35c768a6d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931766"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>保护 SharePoint 网站和文件的策略建议

本文介绍如何实施推荐的标识和设备访问策略来保护 SharePoint 和 OneDrive for Business。 本指南基于通用 [标识和设备访问策略](identity-access-policies.md)。

这些建议基于 SharePoint 文件的三个不同安全和保护层，这些层可以基于你的需求粒度应用：**基线**、敏感和 **高度管控**。  你可以了解有关这些安全层以及推荐的客户端操作系统（概述中这些建议所引用） [的更多信息](microsoft-365-policies-configurations.md)。

除了实施本指南之外，请确保使用适当保护量配置 SharePoint 网站，包括为敏感和高度管控内容设置适当的权限。

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>更新常见策略以包括 SharePoint 和 OneDrive for Business

若要保护 SharePoint 和 OneDrive 中的文件，下图说明了从通用标识和设备访问策略更新的策略。

[![用于保护对 Teams 及其从属服务的访问权限的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[查看此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

如果在创建常见策略时包含 SharePoint，则只需创建新策略。 对于条件访问策略，SharePoint 包括 OneDrive。

新策略通过向指定的 SharePoint 网站应用特定的访问要求，为敏感和高度管控内容实现设备保护。

下表列出了查看和更新 SharePoint 或创建新策略所需的策略。 常见策略链接到通用标识和设备访问策略文章中的 [关联配置](identity-access-policies.md) 说明。

|保护级别|策略|更多信息|
|---|---|---|
|**Baseline**|[当登录风险为中或高 *时需要* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在云应用分配中包括 SharePoint。|
||[阻止不支持新式身份验证的客户端](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|在云应用分配中包括 SharePoint。|
||[应用 APP 数据保护策略](identity-access-policies.md#apply-app-data-protection-policies)|请确保所有推荐的应用都包含在应用列表中。 请务必为 iOS、Android、Windows) 的每个平台更新 (策略。|
||[需要兼容电脑](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|将 SharePoint 包括在云应用列表中。|
||[在 SharePoint 中使用应用强制限制](#use-app-enforced-restrictions-in-sharepoint)|添加新策略。 这将告知 Azure Active Directory (Azure AD) 使用 SharePoint 中指定的设置。 此策略适用于所有用户，但仅影响对 SharePoint 访问策略中包含的网站的访问。|
|**敏感**|[当登录风险较低、中等或高时需要MFA ](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在云应用分配中包括 SharePoint。|
||[要求 *兼容电脑和* 移动设备](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|将 SharePoint 包括在云应用列表中。|
||[SharePoint 访问控制策略](#sharepoint-access-control-policies)：允许仅浏览器访问非托管设备中的特定 SharePoint 网站。|这将阻止编辑和下载文件。 使用 PowerShell 指定网站。|
|**高度管控**|[*始终* 需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|在云应用分配中包括 SharePoint。|
||[SharePoint 访问控制策略](#use-app-enforced-restrictions-in-sharepoint)：阻止从非托管设备访问特定 SharePoint 网站。|使用 PowerShell 指定网站。|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>在 SharePoint 中使用应用强制限制

如果在 SharePoint 中实现访问控制，则必须在 Azure AD 中创建此条件访问策略，以告诉 Azure AD 强制实施在 SharePoint 中配置的策略。 此策略适用于所有用户，但仅在 SharePoint 中创建访问控制时影响对使用 PowerShell 指定的网站的访问。

若要配置此策略，请参阅"阻止或限制对非托管设备的控制访问"中的"阻止或限制对特定 SharePoint 网站集或 OneDrive[帐户的访问"。](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>SharePoint 访问控制策略

Microsoft 建议使用设备访问控制保护具有敏感和高度管控内容的 SharePoint 网站中的内容。 为此，请创建一个策略，指定保护级别和要应用保护的网站。

- 敏感网站：允许仅浏览器访问。 这将阻止用户编辑和下载文件。
- 高度管控网站：阻止来自非托管设备的访问。

请参阅"阻止或限制对特定 SharePoint 网站集或 OneDrive 帐户的访问"中的"控制非[托管设备的访问"。](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

## <a name="how-these-policies-work-together"></a>这些策略如何协同工作

了解 SharePoint 网站权限通常基于访问网站的业务需求，了解这一点很重要。 这些权限由网站所有者管理，并且可以是高度动态的。 使用 SharePoint 设备访问策略可确保保护这些网站，无论用户被分配到与基线、敏感或高度管控保护相关联的 Azure AD 组。

下图提供了 SharePoint 设备访问策略如何保护用户访问网站的示例。

[![SharePoint 设备访问策略如何保护网站的示例](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[查看此图像的较大版本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

尽管为他分配了基准条件访问策略，但可以使用敏感或高度管控保护来访问 SharePoint 网站。

- 如果他访问的敏感或高度管控网站是使用电脑的成员，则只要其电脑合规，就授予其访问权限。
- 如果他访问的敏感网站是使用其非托管电话的成员（允许基线用户使用）的，则由于为此站点配置了设备访问策略，他将收到对敏感网站的仅浏览器访问权限。
- 如果 James 访问高度管控的网站，而他也是使用非托管电话的成员，则他将被阻止，因为此站点配置了访问策略。 他只能使用自己托管且合规的电脑访问此网站。

## <a name="next-step"></a>后续步骤

![步骤 4：Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

为：

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
