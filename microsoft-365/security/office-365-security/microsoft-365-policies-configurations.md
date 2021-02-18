---
title: 标识和设备访问配置 - Microsoft 365 企业版
description: 介绍 Microsoft 有关部署安全电子邮件、文档和应用策略和配置的建议和核心概念。
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
ms.openlocfilehash: e4b85091366927596a2c8f52c579c369fc9697c3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290713"
---
# <a name="identity-and-device-access-configurations"></a>标识和设备访问配置

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)

组织的新式安全外围现在扩展到网络之外，包括从任何位置使用各种设备访问基于云的应用的用户。 安全基础结构需要确定是否应授予给定访问请求以及应在哪些条件下授予。

此确定应基于登录的用户帐户、所使用的设备、用户用于访问的应用、提出访问请求的位置以及请求风险的评估。 这个功能有助于确保只有经过批准的用户和设备才能访问关键的公司资源。

本系列文章介绍了一组标识和设备访问先决条件配置以及一组 Azure Active Directory (Azure AD) 条件访问、Microsoft Intune 和其他策略，用于保护企业云应用和服务、其他 SaaS 服务以及使用 Azure AD 应用程序代理发布的本地应用程序对 Microsoft 365 的访问。

建议使用三层标识和设备访问设置和策略：基线保护、敏感保护，以及针对具有高度管控或分类数据的环境的保护。 这些层及其相应的配置会跨数据、标识和设备，提供一致级别的保护。

这些功能及其建议：

- 在 Microsoft 365 E3 和 Microsoft 365 E5 中受支持。
- 与 Microsoft [安全](../mtp/microsoft-secure-score.md) 分数以及 Azure [AD 中的标识](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)分数一致，并且将增加组织的这些分数。
- 将帮助您实施这 [五个步骤来保护标识基础结构](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)。

如果您的组织具有独特的环境要求或复杂性，请使用这些建议作为起点。 但是，大多数组织都可以按照规定实施这些建议。

观看此视频，快速概览 Microsoft 365 企业版标识和设备访问配置。
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft 还销售 Office 365 订阅的企业移动性 + (EMS) 许可证。 EMS E3 和 EMS E5 功能与 Microsoft 365 E3 和 Microsoft 365 E5 中的功能等效。 有关详细信息 [，请参阅 EMS](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) 计划。

## <a name="intended-audience"></a>目标受众

这些建议适用于熟悉 Microsoft 365 云生产力和安全服务的企业架构师和 IT 专业人员，其中包括 Azure AD (标识) 、Microsoft Intune (设备管理) 和 Azure 信息保护 (数据保护) 。

### <a name="customer-environment"></a>客户环境

建议的策略适用于在 Microsoft 云中完全运行的企业组织以及混合标识基础结构（这是与 Azure AD 租户同步的一个本地 Active Directory 域服务 (AD DS) 林）的客户。

许多提供的建议都依赖于仅 Microsoft 365 E5、具有 Identity & 威胁防护加载项、EMS E5 或 Azure Premium P2 许可证的 Microsoft 365 E3 提供的服务。

对于没有这些许可证的组织，Microsoft 建议你至少实现安全默认值，它[](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)包含在所有 Microsoft 365 计划中。

### <a name="caveats"></a>警告

你的组织可能受法规或其他合规性要求限制，包括可能需要你应用与这些建议配置不同的策略的特定建议。 这些配置推荐以前没有提供的使用情况控件。 我们建议使用这些控件，因为我们认为它们代表安全性和工作效率之间的平衡。

我们已尽力满足各种组织保护要求，但无法考虑所有可能的要求或组织的所有独特方面。

## <a name="three-tiers-of-protection"></a>三层保护

大多数组织都具有安全性和数据保护方面的特定要求。 这些要求因行业部门和组织内的工作职能而异。 例如，法律部门和管理员可能需要针对其电子邮件通信进行额外的安全和信息保护控制，而其他业务部门不需要这些控制。

每个行业也有自己独特的一组规定。 针对三个不同级别的安全和保护提供了建议，而不是提供所有可能的安全选项列表或每个行业或工作职能的建议，这些层的安全和保护可以基于你的需求粒度应用。

- **基线** 保护：建议建立用于保护数据以及访问数据的标识和设备的最低标准。 你可以遵循这些基线建议来提供强大的默认保护，以满足许多组织的需求。
- **敏感保护**：某些客户具有必须在较高级别保护的数据子集，或者可能要求在较高级别保护所有数据。 你可以对 Microsoft 365 环境中的所有或特定数据集应用增强的保护。 建议以与安全性相当的级别保护访问敏感数据的标识和设备。
- **高度管控**：某些组织可能有少量高度机密、构成商业机密或受监管数据的数据。 Microsoft 提供多种功能，帮助组织满足相关要求，包括为标识和设备添加保护。

![安全圆锥 - 所有>客户>特定客户。 向特定应用程序广泛应用](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

本指南演示如何针对每个保护层实现标识和设备保护。 使用本指南作为组织的起点，并调整策略以满足组织的特定要求。

请务必在数据、标识和设备中使用一致的保护级别。 例如，如果你实现本指南，请确保在相当的级别保护你的数据。

Microsoft **365** 体系结构模型的标识和设备保护显示哪些功能是可比较的。

[![Microsoft 365 海报的标识和设备保护缩略图](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [以 PDF 格式查看](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[下载为 PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[下载为 Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

此外，请参阅部署 [数据隐私法规解决方案](../../solutions/information-protection-deploy.md) 的信息保护，以保护 Microsoft 365 中存储的信息。

## <a name="security-and-productivity-trade-offs"></a>安全性和生产力权衡

实施任何安全策略都需要在安全性和工作效率之间进行选择。 评估每个决策对安全性、功能和易用性的平衡有何影响非常有用。

![安全三元平衡安全性、功能和易用性。](../../media/microsoft-365-policies-configurations/security-triad.png)

提供的建议基于以下原则：

- 了解用户，并灵活满足其安全性和功能要求。
- 及时应用安全策略并确保它有意义。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>标识和设备访问保护的服务和概念

Microsoft 365 企业版专为大型组织设计，使每个人都能够发挥创造力并安全地协同工作。

本部分概述了对标识和设备访问非常重要的 Microsoft 365 服务和功能。

### <a name="azure-ad"></a>Azure AD

Azure AD 提供了一整套标识管理功能。 我们建议使用这些功能保护访问。

|功能或特性|说明|许可|
|---|---|---|
|[多重身份验证 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA 要求用户提供两种形式的验证，如用户密码以及来自 Microsoft Authenticator 应用的通知或电话呼叫。 MFA 大大减少了被盗凭据可用于访问环境的风险。 Microsoft 365 对基于 MFA 的登录使用 Azure AD 多重身份验证服务。|Microsoft 365 E3 或 E5|
|[条件访问](/azure/active-directory/conditional-access/overview)|Azure AD 评估用户登录的条件，并使用条件访问策略来确定允许的访问。 例如，在本指南中，我们将向您展示如何创建条件访问策略，以要求设备合规性以访问敏感数据。 这大大减少了黑客使用自己的设备和被盗凭据访问敏感数据的风险。 它还保护设备的敏感数据，因为设备必须满足运行状况和安全性的特定要求。|Microsoft 365 E3 或 E5|
|[Azure AD 组](/azure/active-directory/fundamentals/active-directory-manage-groups)|条件访问策略、使用 Intune 的设备管理，甚至组织中文件和网站的权限都依赖于用户帐户或 Azure AD 组的分配。 我们建议你创建与要实现的保护级别对应的 Azure AD 组。 例如，你的管理人员可能是黑客的更高价值目标。 因此，有必要将这些员工的用户帐户添加到 Azure AD 组，并将该组分配给条件访问策略和其他强制执行更高级别的访问保护的策略。|Microsoft 365 E3 或 E5|
|[设备注册](/azure/active-directory/devices/overview)|你将设备注册到 Azure AD 以创建设备的标识。 此标识用于在用户登录时对设备进行身份验证，并应用要求加入域或兼容电脑的条件访问策略。 对于本指南，我们使用设备注册来自动注册加入域的 Windows 计算机。 设备注册是使用 Intune 管理设备的先决条件。|Microsoft 365 E3 或 E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|使您可以检测影响组织标识的潜在漏洞，将自动修正策略配置为低、中、高登录风险和用户风险。 本指南依赖于此风险评估来应用条件访问策略进行多重身份验证。 本指南还包括条件访问策略，如果检测到其帐户存在高风险活动，则要求用户更改其密码。|具有 Identity & 威胁防护加载项、EMS E5 或 Azure Premium P2 许可证的 Microsoft 365 E5、Microsoft 365 E3|
|[SSPR (自助服务密码) ](/azure/active-directory/authentication/concept-sspr-howitworks)|通过提供对管理员可以控制的多种身份验证方法的验证，允许用户安全地重置其密码，而无需技术支持干预。|Microsoft 365 E3 或 E5|
|[Azure AD 密码保护](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)|检测并阻止已知的弱密码及其变体以及特定于您的组织的其他弱术语。 默认全局禁止使用的密码列表将自动应用于 Azure AD 租户中的所有用户。 可在自定义禁止密码列表中定义额外条目。 用户更改或重置其密码时，将检查这些禁止的密码列表，强制使用强密码。|Microsoft 365 E3 或 E5|
|

下面是标识和设备访问的组件，包括 Intune 和 Azure AD 对象、设置和子服务。

![标识和设备访问的组件](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) 是 Microsoft 基于云的移动设备管理服务。 本指南建议使用 Intune 对 Windows 电脑进行设备管理，并推荐设备合规性策略配置。 Intune 确定设备是否合规，并将此数据发送到 Azure AD 以在应用条件访问策略时使用。

#### <a name="intune-app-protection"></a>Intune 应用保护

[Intune 应用](https://docs.microsoft.com/intune/app-protection-policy) 保护策略可用于保护移动应用中的组织数据，包括或不将设备注册到管理中。 Intune 可帮助保护信息，确保员工仍可高效工作，并防止数据丢失。 通过实施应用级别的策略，可以限制对公司资源的访问，并将数据保持在 IT 部门的控制范围内。

本指南演示如何创建建议策略以强制使用已批准的应用，并确定如何将这些应用与业务数据一同使用。

### <a name="microsoft-365"></a>Microsoft 365

本指南演示如何实施一组策略来保护对 Microsoft 365 云服务（包括 Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive for Business）的访问。 除了实施这些策略之外，我们还建议您使用这些资源提高租户的保护级别：

- [配置租户以提高安全性](tenant-wide-setup-for-increased-security.md)

  适用于租户的基准安全性的建议。

- [安全路线图：前 30 天、90 天及之后的主要优先级](security-roadmap.md)

  包括日志记录、数据管理、管理员访问和威胁防护的建议。

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 和 Microsoft 365 企业应用版

Windows 10 和 Microsoft 365 企业应用版是推荐的电脑客户端环境。 我们建议使用 Windows 10，因为 Azure 旨在为本地和 Azure AD 提供尽可能流畅的体验。 Windows 10 还包括可通过 Intune 管理的高级安全功能。 Microsoft 365 企业应用版包括最新版本的 Office 应用程序。 它们使用新式身份验证，这更加安全，也是条件访问的要求。 这些应用还包括增强的安全性和合规性工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>跨三层保护应用这些功能

下表汇总了我们对跨三层保护使用这些功能的建议。

|保护机制|基线|敏感|高度管控|
|---|---|---|---|
|强制执行 MFA|针对中级或以上登录风险|针对低级或以上登录风险|针对所有新会话|
|**强制更改密码**|对于高风险用户|对于高风险用户|对于高风险用户|
|**强制执行 Intune 应用程序保护**|是|是|是|
|**为组织拥有的设备强制执行 Intune 注册**|需要兼容或加入域的电脑，但允许自带设备 (BYOD) 手机和平板电脑|需要兼容或已加入域的设备|需要兼容或已加入域的设备|
|

## <a name="device-ownership"></a>设备所有权

上表反映了许多组织支持混合使用组织拥有的设备以及个人或 BYOD 的趋势，以在员工中实现移动工作效率。 Intune 应用保护策略可确保电子邮件在组织拥有的设备和 BYOD 上防止从 Outlook 移动应用和其他 Office 移动应用中外传输。

我们建议组织拥有的设备由 Intune 或已加入域的设备进行管理，以应用其他保护和控制。 根据数据敏感度，你的组织可能会选择不允许特定用户群体或特定应用的 BYOD。

## <a name="deployment-and-your-apps"></a>部署和应用

在配置和推出 Azure AD 集成应用的标识和设备访问配置之前，必须：

- 确定要保护的组织中使用的应用。
- 分析此应用列表，以确定提供适当保护级别的策略集。

  不应为每个应用创建单独的策略集，因为管理它们可能会变得很麻烦。 Microsoft 建议对对相同用户具有相同的保护要求的应用进行分组。

  例如，可以有一组策略，其中包括所有用户用于基线保护的所有 Microsoft 365 应用，以及针对所有敏感应用（如人力资源或财务部门使用的策略）的第二组策略，并应用于这些组。

确定要保护的应用的策略集后，以增量方式向用户推出策略，同时解决问题。

例如，配置将仅用于 Exchange Online 的所有 Microsoft 365 应用的策略以及 Exchange 的其他更改。 向用户推出这些策略并解决任何问题。 然后，添加 Teams 及其其他更改，并推出给用户。 然后，添加 SharePoint 及其其他更改。 继续添加其余应用，直到你可以放心地配置这些基线策略以包括所有 Microsoft 365 应用。

同样，对于敏感应用，创建一组策略并一次添加一个应用，并解决任何问题，直到所有问题都包含在敏感应用策略集内。

Microsoft 建议不要创建适用于所有应用的策略集，因为这可能会导致一些意外配置。 例如，阻止所有应用的策略可能会将管理员锁定在 Azure 门户之外，并且无法为重要终结点（如 Microsoft Graph）配置排除项。

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>配置标识和设备访问过程中的步骤

![配置标识和设备访问的步骤。](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. 配置必备标识功能及其设置。
2. 配置通用标识和访问条件访问策略。
3. 为来宾和外部用户配置条件访问策略。
4. 为 Microsoft 365 云应用（如 Microsoft Teams、Exchange Online 和 SharePoint）配置条件访问策略。

配置标识和设备访问后，请参阅[Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2)功能部署指南，了解要考虑的其他功能的分阶段清单，以及用于保护、监视和审核访问的[Azure AD Identity Governance。](https://docs.microsoft.com/azure/active-directory/governance/)

## <a name="next-step"></a>后续步骤

[实现标识和设备访问策略的先决条件工作](identity-access-prerequisites.md)
