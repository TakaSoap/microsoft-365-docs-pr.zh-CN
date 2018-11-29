---
title: 标识和设备访问配置-Microsoft 365 企业版
description: 介绍 Microsoft 建议和部署安全电子邮件、 文档、 和应用程序策略和配置的核心概念。
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
ms.openlocfilehash: 74378da4206c3735cd949358c6cb34b314c82b97
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865420"
---
# <a name="identity-and-device-access-configurations"></a>身份识别与设备访问配置

本系列文章介绍如何通过实施建议的环境和配置，包括一规定的条件的访问策略配置安全地访问通过企业移动 + 安全产品的云服务和相关的功能。本指南可用于保护访问集成在一起 Azure Active Directory，包括 Office 365 服务，其他 SaaS 服务和内部部署应用程序与 Azure AD 应用程序代理发布的所有服务。 

这些建议与 Microsoft 安全分数以及[标识得分 Azure AD 中](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score)对齐，并将提高您的组织这些分数。这些建议还将帮助您实现这些[保护标识基础结构的五个步骤](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps)。 

Microsoft 知道一些组织具有唯一的环境的要求的复杂性。如果您是这些组织之一，使用这些建议作为起点。但是，大多数组织可以实现这些建议的规定。 

## <a name="intended-audience"></a>目标受众

这些建议适用于企业架构师和熟悉[Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx)和[Microsoft 企业移动 + 安全](http://microsoft.com/ems)包括，以及其他，Azure Active Directory （标识） Microsoft 的 IT 专业人员Intune （设备管理）、 和 Azure 信息保护 （数据保护）。

### <a name="customer-environment"></a>客户环境

建议的策略所适用于企业操作系统完全在 Microsoft 云的组织和混合客户与基础结构部署在本地和 Microsoft 云。

提供建议的许多依赖于服务可仅通过企业移动多个安全 (EMS) E5 许可证。建议假定完整 EMS E5 许可证功能。

对于这些组织没有企业移动多个安全 E5 许可证，Microsoft 建议您至少实现附带的所有计划的 Azure AD 基线保护功能。可以在文章中，[什么是比较基准保护](/azure/active-directory/active-directory-conditional-access-baseline-protection)Azure AD 库中找到的详细信息。

### <a name="caveats"></a>注意事项

您的组织可能受法规或其他合规性要求，包括可能需要应用偏离以下建议的配置的策略的特定建议。这些配置建议过去尚未提供的使用率控件。我们建议这些控件，因为我们认为它们表示安全性和工作效率之间的平衡。  

我们已完成我们最佳以体现多种组织保护需求，我们也不能向所有可能要求或组织的所有唯一方面的帐户。

## <a name="three-tiers-of-protection"></a>三层保护

大多数组织都具有安全性和数据保护方面的特定要求。 这些要求因行业部门和组织内的工作职能而异。 例如，法律部门和 Office 365 管理员可能要求对其电子邮件通信进行额外的安全和信息保护控制，而其他业务部门用户不要求这样做。

每个行业还具有自己的专用法规集。而不是提供所有可能的安全选项或建议的列表每个行业段或作业函数已提供三个不同级别的安全性的建议以及可以应用的保护根据您的需求的粒度.

- **比较基准保护**— 建议建立用于保护数据，以及标识和访问您的数据的设备的最小标准。您可以按照这些基线建议，以便为强默认保护符合许多组织的需求。
- **敏感保护**— 某些客户具有较高的级别必须保护或需要更高级别保护的所有数据的数据子集。您可以将增加的保护应用于所有或特定的数据设置 Office 365 环境中。我们建议保护标识和访问具有相当级别的安全性的敏感数据的设备。  
- **高度管控**— 某些组织可能具有少量的高度分类的数据、 商业秘密或监管的数据。Microsoft 提供的功能，帮助组织满足这些要求，包括用于标识和设备的新增了的保护。

![安全圆锥图-所有客户 > 某些客户 > 特定客户。对特定应用程序广泛的应用程序](../images/M365-idquality-threetiers.png)

本指南演示如何实现保护标识和设备的每一层的保护。使用本指南作为起点为您的组织，然后调整以满足您的特定组织需求的策略。

请务必在您的数据、 身份和设备使用一致的保护级别。例如，如果实现了本指南，请务必保护您的数据在相当级别中的一种。这些体系结构模型显示哪些功能是相当。

**Office 365 标识和设备保护**<br/>
![海报"标识和设备 protection for Office 365"的缩略图](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)

**Office 365 中的文件保护解决方案**<br/>
!["Office 365 中的文件保护解决方案"海报的缩略图](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>安全性和生产力权衡

实现任何安全策略需要权衡之间安全性和工作效率。非常有用评估每个决定将如何影响的安全、 功能和易于使用的平衡。

![安全三平衡安全、 功能和易用性。](media/policies-configurations/security-triad.png)

提供的建议基于以下原则：

- 了解您在其安全性和功能要求灵活的访问群体。
- 只需在时间内应用安全策略，并确保它才有意义。

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>服务和标识和设备访问保护的概念

Microsoft 365 企业版专为大型组织，并将 Office 365 企业版，Windows 10 Enterprise 和企业移动 + 安全 (EMS) 来授权所有人都是创作和单位电话的集成在一起，安全地。

本节提供 Microsoft 365 服务和标识和设备访问的重要的功能的概述。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD 提供了一整套标识管理功能。有关保护访问我们建议使用以下功能：

- **[自助服务密码重置 (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks.md)** — 允许用户通过提供验证管理员可以控制的多个身份验证方法的安全地重置而无需帮助台干预其密码。
- **[多重身份验证 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks.md)** — MFA 要求用户提供两种形式的验证，例如用户密码以及来自 Microsoft Authenticator 应用程序或电话呼叫的通知。MFA 大大降低风险窃取的标识可用于访问 Office 365 环境。
- **[条件访问](/azure/active-directory/conditional-access/overview.md)**— Azure AD 用户登录的条件的计算结果，并使用创建允许访问的条件的访问策略。例如，在本指南介绍您如何创建一个条件访问策略来设备合规性要求对敏感数据的访问。这大大降低风险与已被盗标识黑客可以访问您的敏感数据。它还可以保护敏感数据在设备上的，因为设备满足特定的运行状况和安全要求。
- **[Azure AD 组](/azure/active-directory/fundamentals/active-directory-manage-groups.md)**— 条件访问规则，使用 Intune，设备管理和依赖于对文件和您的组织中的网站的偶数权限分配给用户和/或 Azure AD 组。我们建议您创建 Azure AD 组对应的要实现的保护级别。例如，您的主管人员是黑客更高的可能值目标。因此，它有意义这些员工分配给 Azure AD 的组并将此组分配给条件访问策略和强制实施更高级别的保护用于访问其他策略。
- **[设备注册](/azure/active-directory/devices/overview.md)**— 到 Azure AD 以提供与设备的标识注册设备。此标识用于一个用户登录时，设备进行身份验证以及应用需要加入域的或法规要求 Pc 的条件访问规则。对于本指南中，我们可以使用设备注册自动注册加入域的 Windows 计算机。设备注册是用于管理设备 Intune 的先决条件。 
- **[Azure AD 身份保护](/azure/active-directory/identity-protection/overview)**— Azure AD 身份保护可用于检测潜在安全漏洞影响组织的标识和配置自动的修正策略低、 中型和高登录助手风险和用户风险。本指南依赖于此风险评估应用的多因素身份验证的条件的访问策略。本指南还包括一个条件访问策略要求用户在其帐户检测到高风险活动更改其密码。

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune)是 Microsoft 的基于云的移动设备管理服务。本指南建议的 Windows Intune Pc 设备管理和建议设备合规性策略配置。Intune 确定设备是否符合并将该数据发送到 Azure AD 应用条件访问策略时使用。

#### <a name="intune-app-protection"></a>Intune 应用程序保护

[Intune 应用程序保护](https://docs.microsoft.com/intune/app-protection-policy)策略可用于管理到保护使用或不注册设备的移动应用程序中的公司的数据。Intune 有助于保护 Office 365 的信息，并确保您的员工仍可提高生产效率，并防止数据丢失。通过实施应用程序级别的策略，您可以限制访问公司资源，并保持您的 IT 部门的控件内的数据。

本指南演示如何创建以强制使用已批准应用程序并确定如何这些应用程序可用于您的业务数据的建议的策略。

### <a name="office-365"></a>Office 365

本指南演示如何实现一组策略来保护到 Office 365，包括 Exchange Online、 SharePoint Online 和 OneDrive for Business 的访问。除了实施这些策略，我们建议您也会引发的 Office 365 租户使用这些资源的保护级别：

- [配置 Office 365 租户为了提高安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)— 这些建议适用于基准安全，而其 for Office 365 租户。
- [Office 365 安全路线图： Top 优先级的前 30 天，90 天及其他认证实战](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)— 这些建议包括日志记录、 数据管理、 管理员访问权限和威胁保护。
- [保护 SharePoint Online 网站和文件](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)— 这组文章介绍如何保护文件和比较基准，敏感和高度机密 protection 适当级别的网站。

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 和 Office 365 专业增强版

Windows 10 和 Office 365 ProPlus 是 Pc 的推荐客户端环境。我们建议 Windows 10，如 Azure 旨在为内部部署和 Azure AD 提供可能使体验。Windows 10 还包括可以通过 Intune 的高级的安全功能。Office 365 ProPlus 包含的最新版本的 Office 应用程序。这些条件访问使用都更安全的现代身份验证和要求。这些应用程序还包括增强的安全性和遵从性工具。

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>跨三个层的保护应用这些功能

下表总结了我们的保护三个层之间使用这些功能的建议。

|保护机制|Baseline|敏感|高度管控|
|:-------------------|:-------|:--------|:---------------|
|强制执行 MFA|针对中级或以上登录风险|针对低级或以上登录风险|针对所有新会话|
|强制更改密码|针对高风险用户|针对高风险用户|针对高风险用户|
|强制执行 Intune 应用程序保护|是|是|是|
|强制执行 Intune 注册 (COD)|需要符合或域加入 PC，但允许 BYOD 电话平板电脑|需要一个兼容或已加入域的设备|需要一个兼容或已加入域的设备|

## <a name="device-ownership"></a>设备所有权

上表反映许多组织支持的企业拥有设备以及个人或使-您拥有设备 (BYOD)，以实现移动生产力跨人力资源混合的趋势。Intune 应用程序保护策略确保电子邮件抵御 Outlook 移动应用程序和移动其他 Office 的应用程序中使用，企业拥有设备和 BYOD 超出 exfiltrating。  

我们建议企业拥有设备由 Intune 或加入域的应用其他保护和控制。 数据敏感度，根据您的组织可以选择不允许 BYOD 特定用户或特定应用程序。

## <a name="next-steps"></a>后续步骤

[必备工时实现标识和设备访问策略](identity-access-prerequisites.md)