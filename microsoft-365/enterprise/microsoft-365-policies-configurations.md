---
title: 标识和设备访问配置-Microsoft 365 企业版
description: 介绍了用于部署安全电子邮件、文档和应用策略和配置的 Microsoft 建议和核心概念。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 9751d1e224d2fb4b879a5dbc37cb368af2152987
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291346"
---
# <a name="identity-and-device-access-configurations"></a>身份识别与设备访问配置

本系列文章介绍了如何配置通过企业移动性 + 安全产品对云服务的安全访问, 具体方法是实施建议的环境和配置, 包括一组规定的条件访问策略和相关功能。 您可以使用本指南来保护与 azure Active Directory 集成的所有服务 (包括 Office 365 服务、其他 SaaS 服务以及使用 Azure AD 应用程序代理发布的本地应用程序) 的访问权限。 

这些建议与 Microsoft 安全分数以及[Azure AD 中的标识分数](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score)相一致, 并将增加组织的这些分数。 这些建议还将帮助您实施以下[五个步骤来保护您的身份基础结构](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps)。 

Microsoft 知道, 某些组织有独特的环境要求或复杂性。 如果你是这些组织之一, 请使用这些建议作为起点。 但是, 大多数组织都可以按规定实现这些建议。 

## <a name="intended-audience"></a>目标受众

这些建议适用于熟悉[Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx)和[microsoft 企业移动性 + 安全性](http://microsoft.com/ems)的企业架构师和 IT 专业人员, 其中包括其他、Azure Active Directory (identity)、microsoftIntune (设备管理) 和 Azure 信息保护 (数据保护)。

### <a name="customer-environment"></a>客户环境

建议的策略适用于完全在 Microsoft 云中运行的企业组织, 以及适用于具有混合基础结构的客户 (部署在本地和 Microsoft 云上)。

提供的许多建议依赖于仅适用于企业移动性 + 安全性 (EMS) E5 许可证的服务。 提供的建议采用完整 EMS E5 许可证功能。

对于没有企业移动性 + 安全 E5 许可证的组织, Microsoft 建议您至少实现所有计划附带的 Azure AD 基准保护功能。 有关详细信息, 请参阅 Azure AD 库中的 "[比较基准保护](/azure/active-directory/active-directory-conditional-access-baseline-protection)" 一文。

### <a name="caveats"></a>几点

您的组织可能需要遵守管理法规或其他合规性要求, 包括可能要求您应用从这些建议配置中分离的策略的特定建议。 这些配置推荐以前没有提供的使用情况控件。 推荐这些控件的原因是我们认为这些控件可实现安全性与生产力之间的平衡。  

我们已尽最大努力满足各种组织保护要求, 但我们无法满足所有可能的要求, 也无法考虑组织的所有独特方面。

## <a name="three-tiers-of-protection"></a>三层保护

大多数组织都具有安全性和数据保护方面的特定要求。 这些要求因行业部门和组织内的工作职能而异。 例如，法律部门和 Office 365 管理员可能要求对其电子邮件通信进行额外的安全和信息保护控制，而其他业务部门用户不要求这样做。 

每个行业也有自己独特的一组规定。 我们提供了三种不同的安全性和保护层的建议, 而不是提供所有可能的安全选项的列表, 也可以根据您需求的粒度来应用这些功能。.

- **基准保护**: 我们建议您建立用于保护数据的最低标准, 以及访问您的数据的标识和设备。 您可以遵循这些基准建议, 以提供满足许多组织需求的强默认保护。
- **敏感保护**: 某些客户具有必须在更高级别进行保护的数据子集, 或者可能需要在更高级别保护所有数据。 可对 Office 365 环境中的所有或特定数据集应用增强的保护。 建议以与安全性相当的级别保护访问敏感数据的标识和设备。  
- **高度管控**: 某些组织可能具有少量的数据, 这些数据高度保密、consititutes 商业秘密或受管制数据。 Microsoft 提供多种功能，帮助组织满足相关要求，包括为标识和设备添加保护。

![安全圆锥-所有客户 > 一些客户 > 特定客户。 适用于特定应用程序的广泛应用程序](../images/M365-idquality-threetiers.png)

本指南向您介绍如何针对每种级别的保护对标识和设备实施保护。 使用此指南作为组织的起点, 并调整策略以满足组织的特定要求。

请务必在数据、标识和设备间使用一致的保护级别。 例如, 如果您实施了本指南, 请务必保护您的数据处于可比较的级别。 这些体系结构模型显示了可比较的功能。

**Office 365 的标识和设备保护**<br/>
![海报 "适用于 Office 365 的标识和设备保护" 的缩略图](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)

**Office 365 中的文件保护解决方案**<br/>
![海报 "Office 365 中的文件保护解决方案" 的缩略图](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>安全性和生产力权衡

实现任何安全策略都需要权衡安全性和生产率。 评估每个决策对安全性、功能和易用性的影响情况进行评估是有帮助的。

![安全 triad 平衡安全性、功能和易用性。](media/policies-configurations/security-triad.png)

提供的建议基于以下原则:

- 了解你的受众并灵活满足其安全性和功能要求。
- 及时应用安全策略并确保它有意义。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>标识和设备访问保护的服务和概念

Microsoft 365 企业版专为大型组织而设计, 并集成了 Office 365 企业版、Windows 10 企业版和企业移动性 + 安全性 (EMS), 使每个人都能进行创造性和安全地协同工作。

本节概述了对标识和设备访问非常重要的 Microsoft 365 服务和功能。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD 提供一套完整的标识管理功能。 为了确保访问安全, 我们建议使用以下功能:

- **[自助密码重置 (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)**: 允许您的用户通过验证管理员可以控制的多种身份验证方法, 安全地重置其密码, 而不需要提供帮助程序干预。

- **[多重身份验证 (mfa)](/azure/active-directory/authentication/concept-mfa-howitworks)**: mfa 要求用户提供两种形式的验证, 如用户密码以及来自 Microsoft 验证器应用或电话呼叫的通知。 MFA 极大地降低了可用于访问 Office 365 环境的被盗标识的风险。

- **[条件访问](/azure/active-directory/conditional-access/overview)**: Azure AD 评估用户登录的条件, 并使用您创建的条件访问策略来允许访问。 例如, 在本指南中, 我们将向您介绍如何创建条件访问策略, 以要求访问敏感数据的设备合规性。 这极大地降低了具有盗窃标识的黑客可以访问您的敏感数据的风险。 它还保护了设备上的敏感数据, 因为这些设备会满足运行状况和安全性的特定要求。

- **[Azure ad 组](/azure/active-directory/fundamentals/active-directory-manage-groups)**: 条件访问规则、具有 Intune 的设备管理, 甚至对组织中的文件和网站的权限, 依赖于用户和/或 Azure AD 组的分配。 我们建议您创建与您实施的保护级别相对应的 Azure AD 组。 例如, 您的执行人员可能更高的黑客的价值目标。 因此, 将这些员工分配到 Azure AD 组并将该组分配给条件访问策略和其他强制实施更高级别的保护的策略是有意义的。

- **[设备注册](/azure/active-directory/devices/overview)**: 将设备注册到 Azure AD 以向设备提供标识。 此标识用于在用户登录时对设备进行身份验证, 并应用需要加入域或合规的电脑的条件访问规则。 在本指南中, 我们使用设备注册自动注册加入域的 Windows 计算机。 设备注册是使用 Intune 管理设备的先决条件。 

- **[azure ad identity protection](/azure/active-directory/identity-protection/overview)**: azure ad 标识保护使您能够检测到影响组织的身份的潜在漏洞, 并将自动修正策略配置为低、中和高的登录风险和用户风险。 本指南依赖此风险评估来应用多因素身份验证的条件访问策略。 本指南还包括一个条件访问策略, 该策略要求用户在为其帐户检测到高风险活动时更改其密码。

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune)是 Microsoft 基于云的移动设备管理服务。 本指南推荐使用 Intune 的 Windows 电脑的设备管理, 并建议设备合规性策略配置。 Intune 确定设备是否合规, 并将此数据发送到 Azure AD, 以便在应用条件访问策略时使用。

#### <a name="intune-app-protection"></a>Intune 应用保护

[Intune 应用保护](https://docs.microsoft.com/intune/app-protection-policy)策略可用于保护你的组织在移动应用中的数据, 包括或不将设备注册到管理中。 Intune 可帮助保护 Office 365 信息, 确保您的员工仍能提高工作效率, 并防止数据丢失。 通过实施应用程序级别的策略, 可以限制对公司资源的访问并将数据保留在 IT 部门的控制范围内。

本指南向您介绍如何创建建议的策略来强制使用已批准的应用程序, 并确定这些应用程序如何与您的业务数据结合使用。

### <a name="office-365"></a>Office 365

本指南介绍如何实现一组用于保护对 Office 365 (包括 Exchange online、SharePoint online 和 OneDrive for business) 的访问权限的策略。 除了实施这些策略之外, 我们还建议您使用以下资源提高 Office 365 租户的保护级别:

- [配置 office 365 租户以提高安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355): 这些建议适用于 Office 365 租户的基准安全性。
- [Office 365 安全路线图: 前30天、90天及以上的主要优先级](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352): 这些建议包括日志记录、数据管理、管理员访问和威胁防护。
- [保护 SharePoint Online 网站和文件](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files): 此系列文章介绍了如何在适当的级别保护文件和网站, 以实现基准、敏感和高度机密保护。

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 和 Office 365 专业增强版

Windows 10 和 Office 365 专业增强版是电脑的推荐客户端环境。 建议 Windows 10, 因为 Azure 旨在提供内部部署和 Azure AD 的最平滑体验。 Windows 10 还包含可通过 Intune 管理的高级安全功能。 office 365 专业增强版包括 office 应用程序的最新版本。 这些身份验证使用新式验证, 这是更安全和有条件访问的要求。 这些应用程序还包括增强的安全性和合规性工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>在三层保护中应用这些功能

下表总结了在三层保护中使用这些功能的建议。

|保护机制|Baseline|敏感|高度管控|
|:-------------------|:-------|:--------|:---------------|
|强制执行 MFA|针对中级或以上登录风险|针对低级或以上登录风险|针对所有新会话|
|**强制更改密码**|对于高风险用户|对于高风险用户|对于高风险用户|
|**强制实施 Intune 应用程序保护**|是|是|是|
|**强制 Intune 注册 (货至付款)**|需要兼容或加入域的电脑, 但允许 BYOD 电话/平板电脑|需要兼容或加入域的设备|需要兼容或加入域的设备|

## <a name="device-ownership"></a>设备所有权

上面的表反映了许多组织支持公司拥有的设备的混合以及个人或附带的设备 (BYODs), 以便在整个工作中实现移动工作效率的趋势。 Intune 应用保护策略可确保电子邮件在企业拥有的设备和 BYODs 上的 exfiltrating 不会受到 Outlook 移动应用和其他 Office 移动应用的保护。  

我们建议由 Intune 或加入域来管理企业拥有的设备, 以应用更多的保护和控制。 根据数据敏感度的不同, 您的组织可能会选择不允许对特定用户群体或特定应用的 BYODs。

## <a name="next-steps"></a>后续步骤

[实现标识和设备访问策略的先决条件工作](identity-access-prerequisites.md)
