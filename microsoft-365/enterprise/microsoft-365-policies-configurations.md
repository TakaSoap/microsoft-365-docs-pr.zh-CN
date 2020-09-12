---
title: 标识和设备访问配置-适用于企业的 Microsoft 365
description: 介绍了用于部署安全电子邮件、文档和应用策略和配置的 Microsoft 建议和核心概念。
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/31/2020
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
ms.openlocfilehash: 375e58214e19960d3e3100a0c1051fe7c4924aae
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546638"
---
# <a name="identity-and-device-access-configurations"></a>标识和设备访问配置

本系列文章介绍了如何通过实施建议的环境和配置（包括一组规定的条件访问策略和相关功能）来配置对云服务的安全访问（通过 Microsoft 365 企业版产品）。 您可以使用本指南来保护对与 azure ad 应用程序代理发布的 Microsoft 365 服务、其他 SaaS 服务和本地应用程序集成的所有服务的访问，这些服务与 azure Active Directory (Azure AD) （包括 Microsoft 服务、其他 SaaS 服务和本地应用程序）。

这些建议：

- 与 [Microsoft 安全分数](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) 和 [Azure AD 中的标识分数](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)一致，并将增加贵组织的这些分数
- 将帮助您实施以下 [五个步骤来保护您的身份基础结构](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)。 

如果您的组织具有独特的环境要求或复杂性，请使用这些建议作为起点。 但是，大多数组织都可以按规定实现这些建议。

>[!Note]
>Microsoft 还为 Office 365 订阅销售企业移动性 + 安全性 (EMS) 许可证。 EMS E3 和 EMS E5 功能大致等同于 Microsoft 365 E3 和 Microsoft 365 E5 中的那些功能。 有关详细信息，请参阅 [EMS 计划](https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) 。
>

## <a name="intended-audience"></a>目标受众

这些建议适用于熟悉 Microsoft 365 云生产力和安全服务的企业架构师和 IT 专业人员，其中包括 Azure AD (标识) 、Microsoft Intune (设备管理) 和 Azure 信息保护 (数据保护) 。

### <a name="customer-environment"></a>客户环境

建议的策略适用于完全在 Microsoft 云中运行的企业组织，并适用于具有混合标识基础结构的客户，后者是本地 Active Directory 域服务 (AD DS) 林，与 Azure AD 租户同步。

提供的许多建议依赖于 Microsoft 365 E5、Microsoft 365 E3 和 Identity & 威胁防护附加、EMS E5 或 Azure Premium P2 许可证中提供的服务。

对于没有这些许可证的那些组织，Microsoft 建议您至少实施 [安全默认设置，这些默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)包括在所有 Microsoft 365 计划中。 

### <a name="caveats"></a>几点

您的组织可能需要遵守管理法规或其他合规性要求，包括可能要求您应用从这些建议配置中分离的策略的特定建议。 这些配置推荐以前没有提供的使用情况控件。 我们建议使用这些控制措施，因为我们认为它们代表安全性和生产率之间的平衡。  

我们已尽最大努力满足各种组织保护要求，但我们无法满足所有可能的要求，也无法考虑组织的所有独特方面。

## <a name="three-tiers-of-protection"></a>三层保护

大多数组织都具有安全性和数据保护方面的特定要求。 这些要求因行业部门和组织内的工作职能而异。 例如，法律部门和管理员可能需要其他业务部门不需要的电子邮件通信周围的其他安全和信息保护控制。 

每个行业也有自己独特的一组规定。 建议针对三种不同的安全性和保护层提供了建议，这些建议可根据您的需求的粒度来应用，而不是提供所有可能的安全选项列表或建议的每个行业部分或作业功能。

- **基准保护**：我们建议您建立用于保护数据的最低标准，以及访问您的数据的标识和设备。 您可以遵循这些基准建议，以提供满足许多组织需求的强默认保护。
- **敏感保护**：某些客户具有必须在更高级别进行保护的数据子集，或者可能需要在更高级别保护所有数据。 您可以对 Microsoft 365 环境中的所有或特定的数据集应用增强的保护。 建议以与安全性相当的级别保护访问敏感数据的标识和设备。  
- **高度管控**：某些组织可能拥有高度分类的少量数据，构成商业机密或受管制数据。 Microsoft 提供多种功能，帮助组织满足相关要求，包括为标识和设备添加保护。

![安全圆锥-> 一些客户 > 特定客户的所有客户。 适用于特定应用程序的广泛应用程序](../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

本指南向您介绍如何针对每种级别的保护对标识和设备实施保护。 使用此指南作为组织的起点，并调整策略以满足组织的特定要求。

请务必在数据、标识和设备中使用一致的保护级别。 例如，如果您实施了本指南，请务必保护您的数据处于可比较的级别。 

Microsoft 365 体系结构模型的 **标识和设备保护** 显示可比较的功能。

[![用于 Microsoft 365 海报的标识和设备保护的缩略图](../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br/>  [以 PDF](../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| 形式查看[下载为 PDF 格式](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \|[下载为 Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

此外，请参阅为 [数据隐私法规部署信息保护](../solutions/information-protection-deploy.md) 解决方案，以保护存储在 Microsoft 365 中的信息。

## <a name="security-and-productivity-trade-offs"></a>安全性和生产力权衡

实现任何安全策略都需要权衡安全性和生产率。 评估每个决策对安全性、功能和易用性的影响情况进行评估是有帮助的。

![安全 triad 平衡安全性、功能和易用性。](../media/microsoft-365-policies-configurations/security-triad.png)

提供的建议基于以下原则：

- 了解你的用户并灵活地满足其安全性和功能要求。
- 及时应用安全策略并确保它有意义。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>标识和设备访问保护的服务和概念

适用于企业的 Microsoft 365 专为大型组织设计，使每个人都能具有创造性且安全地协同工作。

本节概述了对标识和设备访问非常重要的 Microsoft 365 服务和功能。

### <a name="azure-ad"></a>Azure AD

Azure AD 提供一套完整的标识管理功能。 我们建议使用这些功能来保护访问。

| 功能或特性 | 说明 | 许可 |
|:-------|:-----|:-------|
| [多重身份验证 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) | MFA 要求用户提供两种形式的验证，如用户密码以及来自 Microsoft 验证器应用或电话呼叫的通知。 MFA 极大地降低了失窃凭据可用于访问环境的风险。 Microsoft 365 对基于 MFA 的登录使用 Azure 多因素身份验证服务。 | Microsoft 365 E3 或 E5 |
| [条件访问](/azure/active-directory/conditional-access/overview) | Azure AD 评估用户登录的条件，并使用条件访问策略确定允许的访问权限。 例如，在本指南中，我们将向您介绍如何创建条件访问策略，以要求访问敏感数据的设备合规性。 这极大地降低了具有自己的设备和被盗凭据的黑客可以访问您的敏感数据的风险。 它还保护了设备上的敏感数据，因为这些设备必须满足运行状况和安全性的特定要求。 | Microsoft 365 E3 或 E5 |
| [Azure AD 组](/azure/active-directory/fundamentals/active-directory-manage-groups) | 条件访问策略、具有 Intune 的设备管理，甚至对组织中的文件和网站的权限依赖于用户帐户或 Azure AD 组的分配。 我们建议您创建与您实施的保护级别相对应的 Azure AD 组。 例如，您的执行人员可能更高的黑客的价值目标。 因此，将这些员工的用户帐户添加到 Azure AD 组并将该组分配给条件访问策略和其他强制实施更高级别的保护的策略是有意义的。 | Microsoft 365 E3 或 E5 |
| [设备注册](/azure/active-directory/devices/overview) | 将设备注册到 Azure AD 以创建设备的标识。 当用户登录并应用需要加入域或合规的 Pc 的条件访问策略时，此标识用于对设备进行身份验证。 在本指南中，我们使用设备注册自动注册加入域的 Windows 计算机。 设备注册是使用 Intune 管理设备的先决条件。 | Microsoft 365 E3 或 E5 |
| [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview) | 使您能够检测到影响组织标识的潜在漏洞，并将自动修正策略配置为低、中和高的登录风险和用户风险。 本指南依赖此风险评估来应用多因素身份验证的条件访问策略。 本指南还包括一个条件访问策略，该策略要求用户在为其帐户检测到高风险活动时更改其密码。 | Microsoft 365 E5，Microsoft 365 E3 with Identity & 威胁防护加载项、EMS E5 或 Azure 高级 P2 许可证 |
| [自助服务密码重置 (SSPR) ](/azure/active-directory/authentication/concept-sspr-howitworks) | 通过提供管理员可以控制的多种身份验证方法的验证，允许用户安全地重置其密码，而无需技术人员干预。 | Microsoft 365 E3 或 E5 |
| [AZURE AD 密码保护](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)。 检测并阻止已知的弱密码及其变体以及特定于您的组织的其他弱术语。 默认全局禁止密码列表将自动应用于 Azure AD 租户中的所有用户。 您可以在 "自定义禁止密码" 列表中定义其他条目。 当用户更改或重置其密码时，将检查这些禁止的密码列表，以强制使用强密码。 |  Microsoft 365 E3 或 E5 |
||||

![标识和设备访问的组件。](../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) 是 Microsoft 基于云的移动设备管理服务。 本指南推荐使用 Intune 的 Windows 电脑的设备管理，并建议设备合规性策略配置。 Intune 确定设备是否合规，并将此数据发送到 Azure AD，以便在应用条件访问策略时使用。

#### <a name="intune-app-protection"></a>Intune 应用保护

[Intune 应用保护](https://docs.microsoft.com/intune/app-protection-policy) 策略可用于保护你的组织在移动应用中的数据，包括或不将设备注册到管理中。 Intune 可帮助保护信息，确保员工仍能高效工作，并防止数据丢失。 通过实施应用程序级别的策略，可以限制对公司资源的访问并将数据保留在 IT 部门的控制范围内。

本指南向您介绍如何创建建议的策略来强制使用已批准的应用程序，并确定这些应用程序如何与您的业务数据结合使用。

### <a name="microsoft-365"></a>Microsoft 365

本指南介绍如何实现一组用于保护对 Microsoft 365 云服务（包括 Microsoft 团队、Exchange Online、SharePoint Online 和 OneDrive for Business）的访问权限的策略。 除了实施这些策略之外，我们还建议您使用以下资源提高租户的保护级别：

- [配置租户以提高安全性](../security/office-365-security/tenant-wide-setup-for-increased-security.md)

  适用于租户的基准安全性的建议。

- [安全路线图：前30天、90天及以上的主要优先级](../security/office-365-security/security-roadmap.md)

  包括日志记录、数据管理、管理员访问和威胁防护的建议。

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 和 Microsoft 365 企业应用版

适用于企业的 Microsoft 365 应用程序的 Windows 10 是电脑的推荐客户端环境。 建议 Windows 10，因为 Azure 旨在提供内部部署和 Azure AD 的最平滑体验。 Windows 10 还包含可通过 Intune 管理的高级安全功能。 适用于企业的 Microsoft 365 应用程序包括 Office 应用程序的最新版本。 这些身份验证使用新式验证，这是更安全和有条件访问的要求。 这些应用程序还包括增强的安全性和合规性工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>在三层保护中应用这些功能

下表总结了在三层保护中使用这些功能的建议。

|保护机制|基线|敏感|高度管控|
|:-------------------|:-------|:--------|:---------------|
|强制执行 MFA|针对中级或以上登录风险|针对低级或以上登录风险|针对所有新会话|
|**强制更改密码**|对于高风险用户|对于高风险用户|对于高风险用户|
|**强制实施 Intune 应用程序保护**|是|是|是|
|**为组织拥有的设备强制执行 Intune 注册**|需要兼容或加入域的电脑，但允许在 (BYOD) 电话和平板电脑上引入自己的设备|需要兼容或加入域的设备|需要兼容或加入域的设备|

## <a name="device-ownership"></a>设备所有权

上表反映了许多组织支持组织拥有的设备的组合以及个人或 BYODs 的趋势，以实现整个工作的工作效率。 Intune 应用保护策略可确保电子邮件在组织拥有的设备和 BYODs 上的 exfiltrating 从 Outlook 移动应用和其他 Office 移动应用程序中受到保护。  

我们建议由 Intune 或加入域来管理组织拥有的设备，以应用更多的保护和控制。 根据数据敏感度的不同，您的组织可能会选择不允许对特定用户群体或特定应用的 BYODs。

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>配置标识和设备访问的过程中的步骤

![配置标识和设备访问的步骤。](../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. 配置必备组件标识功能及其设置。
2. 配置通用标识和访问条件访问策略。
3. 为来宾和外部用户配置条件访问策略。
4. 为 microsoft 团队、Exchange Online 和 SharePoint 等 Microsoft 365 云应用配置条件访问策略。

## <a name="next-step"></a>后续步骤

[实现标识和设备访问策略的先决条件工作](identity-access-prerequisites.md)
