---
title: 标识和设备访问配置 - Microsoft 365配置
description: 介绍用于部署安全电子邮件、文档和应用策略和配置的 Microsoft 建议和核心概念。
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: e3d807337cfa2e7fa6a27f63e58bd441d95716d5
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110063"
---
# <a name="identity-and-device-access-configurations"></a>标识和设备访问配置

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

组织的新式安全外围现在扩展到网络之外，包括从任何位置使用各种设备访问基于云的应用的用户。 安全基础结构需要确定是否应授予给定访问请求以及应在哪些条件下授予。

此确定应基于登录的用户帐户、所使用的设备、用户用于访问的应用、提出访问请求的位置以及请求风险的评估。 这个功能有助于确保只有经过批准的用户和设备才能访问关键的公司资源。

本系列文章介绍了一组标识和设备访问先决条件配置以及一组 Azure Active Directory (Azure AD) 条件访问、Microsoft Intune 和其他策略，用于保护对 Microsoft 365 用于企业云应用和服务、其他 SaaS 服务以及使用应用程序代理发布的Azure AD应用程序。

在三个层中推荐标识和设备访问设置和策略：基线保护、敏感保护，以及针对具有高度管控或分类数据的环境的保护。 这些层及其相应的配置会跨数据、标识和设备，提供一致级别的保护。

这些功能及其建议：

- 在 Microsoft 365 E3 和 Microsoft 365 E5 中Microsoft 365 E5。
- 与 Microsoft[安全分数以及](../defender/microsoft-secure-score.md)Azure AD[中的标识](/azure/active-directory/fundamentals/identity-secure-score)分数一致，将增加组织的这些分数。
- 将帮助您实施这 [五个步骤来保护标识基础结构](/azure/security/azure-ad-secure-steps)。

如果您的组织具有独特的环境要求或复杂性，请使用这些建议作为起点。 但是，大多数组织都可以按照规定实现这些建议。

观看此视频，快速概览适用于企业的 Microsoft 365 和设备访问配置。

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft 还企业移动性 + 安全性 (EMS) 订阅Office 365许可证。 EMS E3 和 EMS E5 功能等效于 Microsoft 365 E3 和 Microsoft 365 E5。 有关详细信息 [，请参阅 EMS](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) 计划。

## <a name="intended-audience"></a>目标受众

这些建议适用于熟悉 Microsoft 365 云生产力和安全服务的企业架构师和 IT 专业人员，其中包括 Azure AD (标识) 、Microsoft Intune (设备管理) 和 Microsoft 信息保护 (数据保护) 。

### <a name="customer-environment"></a>客户环境

建议的策略适用于完全在 Microsoft 云内运营的企业组织以及混合标识基础结构（这是与 Azure AD 租户同步的一个本地 Active Directory 域服务 (AD DS) 林）的客户。

提供的很多建议都依赖于仅适用于 Microsoft 365 E5、Microsoft 365 E3 E5 安全加载项、EMS E5 或 Azure AD Premium P2 许可证的服务。

对于没有这些许可证的组织，Microsoft 建议你至少实现安全默认值，它[](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)包含在所有Microsoft 365计划中。

### <a name="caveats"></a>注意事项

你的组织可能受法规或其他合规性要求限制，包括可能需要你应用与这些建议配置不同的策略的特定建议。 这些配置推荐以前没有提供的使用情况控件。 我们建议使用这些控件，因为我们认为它们代表安全性和生产力之间的平衡。

我们已尽力满足各种组织保护要求，但无法考虑所有可能的要求或组织的所有独特方面。

## <a name="three-tiers-of-protection"></a>三层保护

大多数组织都具有安全性和数据保护方面的特定要求。 这些要求因行业部门和组织内的工作职能而异。 例如，法律部门及管理员可能需要针对其电子邮件通信进行额外的安全和信息保护控制，而其他业务部门不需要这些控制。

每个行业也有自己独特的一组规定。 针对三种不同安全和保护层提供了建议，可以基于你的需求粒度应用这三种不同安全和保护层，而不是提供所有可能的安全选项列表或每个行业部门或工作职能的建议。

- **基线** 保护：建议建立用于保护数据以及访问数据的标识和设备的最低标准。 你可以遵循这些基线建议来提供强大的默认保护，以满足许多组织的需求。
- **敏感保护**：某些客户具有必须在较高级别进行保护的数据子集，或者他们可能要求在较高级别保护所有数据。 你可以对环境中的所有或特定数据集应用增强Microsoft 365保护。 建议以与安全性相当的级别保护访问敏感数据的标识和设备。
- **高度管控**：某些组织可能有少量高度机密、构成商业秘密或受监管数据的数据。 Microsoft 提供多种功能，帮助组织满足相关要求，包括为标识和设备添加保护。

![安全圆锥 - 所有>特定>的客户。 广泛的应用程序到特定应用程序。](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

本指南显示了如何针对这些保护层中的每个标识和设备实施保护。 使用本指南作为组织的起点，并调整策略以满足组织的特定要求。

请务必在数据、标识和设备中使用一致的保护级别。 例如，如果你实现本指南，请确保在相当的级别保护你的数据。

Identity **and device protection for Microsoft 365** model shows you which capabilities are comparable.

[![用于海报标识和设备保护的缩略图Microsoft 365图像。](../../media/microsoft-365-policies-configurations/o365-identity-device-protection-thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [以 PDF 格式查看](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[以 PDF 格式下载](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[下载为Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

此外，请参阅[部署数据隐私法规信息](../../solutions/information-protection-deploy.md)保护解决方案来保护存储在Microsoft 365。

## <a name="security-and-productivity-trade-offs"></a>安全性和生产力权衡

实施任何安全策略需要在安全性和工作效率之间进行选择。 评估每个决策对安全性、功能和易用性的平衡有何影响很有用。

![安全性三重平衡安全性、功能和易用性。](../../media/microsoft-365-policies-configurations/security-triad.png)

提供的建议基于以下原则：

- 了解用户，并灵活满足其安全性和功能要求。
- 及时应用安全策略并确保其有意义。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>标识和设备访问保护的服务和概念

Microsoft 365企业版专为大型组织设计，使每个人都能够发挥创造力并安全地协同工作。

本节概述了对标识Microsoft 365访问非常重要的服务和功能。

### <a name="azure-ad"></a>Azure AD

Azure AD提供了一整套标识管理功能。 我们建议使用这些功能来保证访问安全。

|功能或特性|说明|许可|
|---|---|---|
|[多重身份验证 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA 要求用户提供两种形式的验证，如用户密码以及来自应用或Microsoft Authenticator的通知。 MFA 大大减少了凭据被盗可用于访问环境的风险。 Microsoft 365使用 Azure AD 多重身份验证服务进行基于 MFA 的登录。|Microsoft 365 E3 或 E5|
|[条件访问](/azure/active-directory/conditional-access/overview)|Azure AD评估用户登录的条件，并使用条件访问策略来确定允许的访问。 例如，在本指南中，我们将向您展示如何创建条件访问策略，以要求设备合规性以访问敏感数据。 这大大降低了具有自己的设备和凭据被盗的黑客访问敏感数据的风险。 它还保护设备的敏感数据，因为设备必须满足运行状况和安全性的特定要求。|Microsoft 365 E3 或 E5|
|[Azure AD组](/azure/active-directory/fundamentals/active-directory-manage-groups)|条件访问策略、使用 Intune 的设备管理，甚至组织中文件和网站的权限都依赖于对用户帐户或组Azure AD分配。 建议创建Azure AD保护级别对应的组。 例如，你的管理人员可能是黑客的更高价值目标。 因此，有必要将这些员工的用户帐户添加到 Azure AD 组，并将该组分配给条件访问策略和其他强制实施更高级别的访问保护的策略。|Microsoft 365 E3 或 E5|
|[设备注册](/azure/active-directory/devices/overview)|将设备注册到Azure AD为设备创建标识。 此标识用于在用户登录时对设备进行身份验证，并应用要求加入域或兼容电脑的条件访问策略。 对于本指南，我们使用设备注册在计算机中自动注册Windows域。 设备注册是使用 Intune 管理设备的先决条件。|Microsoft 365 E3 或 E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|使您可以检测影响组织标识的潜在漏洞，将自动修正策略配置为低、中、高登录风险和用户风险。 本指南依赖于此风险评估，对多重身份验证应用条件访问策略。 本指南还包括条件访问策略，要求用户在检测到其帐户的高风险活动时更改其密码。|Microsoft 365 E5，Microsoft 365 E3 E5 安全加载项、EMS E5 或 Azure AD Premium P2 许可证|
|[SSPR (自助服务密码) ](/azure/active-directory/authentication/concept-sspr-howitworks)|通过提供对管理员可以控制的多种身份验证方法的验证，允许用户安全地重置其密码，而无需支持人员干预。|Microsoft 365 E3 或 E5|
|[Azure AD密码保护](/azure/active-directory/authentication/concept-password-ban-bad)|检测并阻止已知的弱密码及其变体以及特定于您的组织的其他弱术语。 默认全局禁止使用的密码列表将自动应用于 Azure AD 租户中的所有用户。 可在自定义禁止密码列表中定义额外条目。 用户更改或重置其密码时，将检查这些禁止的密码列表，强制使用强密码。|Microsoft 365 E3 或 E5|
|

下面是标识和设备访问的组件，包括 Intune 和 Azure AD 对象、设置和子服务。

![标识和设备访问的组件。](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune) 是 Microsoft 基于云的移动设备管理服务。 本指南建议使用 Intune 对Windows电脑进行设备管理，并推荐设备合规性策略配置。 Intune 确定设备是否合规，并将此数据Azure AD条件访问策略时使用的设备。

#### <a name="intune-app-protection"></a>Intune 应用保护

[Intune 应用](/intune/app-protection-policy) 保护策略可用于保护移动应用中的组织数据，支持或不将设备注册到管理中。 Intune 可帮助保护信息，确保员工仍可高效工作，并防止数据丢失。 通过实现应用级别的策略，可以限制对公司资源的访问，并控制 IT 部门的数据。

本指南演示如何创建建议策略以强制使用已批准的应用，并确定如何将这些应用与业务数据一同使用。

### <a name="microsoft-365"></a>Microsoft 365

本指南演示如何实施一组策略来保护对 Microsoft 365 云服务的访问，包括 Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive for Business。 除了实施这些策略外，我们还建议你使用这些资源提高租户的保护级别：

- [配置租户以提高安全性](tenant-wide-setup-for-increased-security.md)

  推荐适用于租户的基准安全性。

- [安全路线图：前 30 天、前 90 天及以后的首要任务](security-roadmap.md)

  推荐，包括日志记录、数据管理、管理员访问和威胁防护。

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 和 Microsoft 365 企业应用版

Windows 10是Microsoft 365 企业应用版推荐用于电脑的客户端环境。 我们建议Windows 10，因为 Azure 旨在为本地和本地部署环境提供尽可能Azure AD。 Windows 10还包括可通过 Intune 管理的高级安全性功能。 Microsoft 365 企业应用版包括最新版本的 Office 应用程序。 这些身份验证使用新式验证，这是更安全且条件访问的要求。 这些应用还包括增强的合规性和安全工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>跨三层保护应用这些功能

下表总结了我们对跨三层保护使用这些功能的建议。

|保护机制|基线|敏感|高度管控|
|---|---|---|---|
|强制执行 MFA|针对中级或以上登录风险|针对低级或以上登录风险|针对所有新会话|
|**强制更改密码**|对于高风险用户|对于高风险用户|对于高风险用户|
|**强制执行 Intune 应用程序保护**|是|是|是|
|**强制对组织拥有的设备进行 Intune 注册**|需要兼容或已加入域的电脑，但允许自带设备 (BYOD) 手机和平板电脑|需要兼容或已加入域的设备|需要兼容或已加入域的设备|
|

## <a name="device-ownership"></a>设备所有权

上表反映了许多组织支持混合使用组织拥有的设备以及个人或 BYOD 的趋势，从而在整个员工中实现移动生产力。 Intune 应用保护策略可确保电子邮件在组织拥有的设备和 BYOD 上免遭 Outlook 移动应用和其他 Office 移动应用的外传输。

我们建议由 Intune 或已加入域的设备管理，以应用其他保护和控制。 根据数据敏感度，你的组织可能会选择不允许特定用户群体或特定应用的 BYOD。

## <a name="deployment-and-your-apps"></a>部署和应用

在配置和推出集成了应用的标识和设备Azure AD配置之前，你必须：

- 确定要保护的组织中使用的应用。
- 分析此应用列表，以确定提供适当保护级别的策略集。

  不应为每个应用创建单独的策略集，因为管理它们可能会变得很麻烦。 Microsoft 建议对对相同用户具有相同的保护要求的应用进行分组。

  例如，你可以拥有一组策略，其中包括适用于所有用户的所有 Microsoft 365 应用进行基线保护，第二组策略适用于所有敏感应用（如人力资源或财务部门使用的策略）并应用于这些组。

确定要保护的应用的策略集后，以增量方式向用户推出策略，同时解决问题。

例如，配置将用于所有 Microsoft 365 应用的策略，Exchange Online其他更改Exchange。 向用户推出这些策略，并解决任何问题。 然后，添加Teams及其其他更改，并推出给用户。 然后，添加SharePoint其其他更改。 继续添加其余的应用，直到你可以放心地配置这些基线策略以包含所有Microsoft 365应用。

同样，对于敏感应用，创建一组策略，一次添加一个应用，并解决所有问题，直到所有问题都包含在敏感应用策略集内。

Microsoft 建议不要创建适用于所有应用的策略集，因为这可能会导致一些意外配置。 例如，阻止所有应用的策略可能会将管理员锁定在 Azure 门户之外，并且无法为重要终结点（如 Microsoft Graph）配置排除项。

## <a name="steps-to-configure-identity-and-device-access"></a>配置标识和设备访问的步骤

![配置标识和设备访问的步骤。](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. 配置先决条件标识功能及其设置。
2. 配置通用标识和访问条件访问策略。
3. 为来宾用户和外部用户配置条件访问策略。
4. 为云应用配置Microsoft 365访问策略（如 Microsoft Teams、Exchange Online 和 SharePoint）和 Microsoft Defender for Cloud Apps 策略。

配置标识和设备访问后，请参阅[Azure AD 功能](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2)部署指南，了解要考虑的其他功能的分阶段清单，Azure AD Identity Governance 来保护、监视[和](/azure/active-directory/governance/)审核访问。

## <a name="next-step"></a>后续步骤

[实现标识和设备访问策略的先决条件工作](identity-access-prerequisites.md)
