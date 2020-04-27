---
title: 信息保护基础结构退出条件
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 检查基于信息保护的服务和基础结构的条件，确保你的配置满足 Microsoft 365 企业版的要求。
ms.openlocfilehash: c0b4ff6a0d289b8a8c63255d817ea455df00bf13
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631629"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>信息保护基础结构退出条件

![第 6 阶段：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

确保你的信息保护基础结构符合以下必需条件，以及你认为可选的那些条件。

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>必需：为你的组织定义安全和信息保护级别。

已计划并确定组织需要的安全级别。这些级别定义了最低安全级别，以及对敏感信息及其所需数据安全性提升保护的额外安全级别。

至少，当前需要使用三种安全级别：

- 基线
- 敏感
- 高度管控

如果需要，可在[步骤 1](infoprotect-define-sec-infoprotect-levels.md) 中进行设置以满足此要求。 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>必需：已配置增强的 Microsoft 365 安全性

你已配置以下用于[增强 Microsoft 365 安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)的设置：

- Microsoft 365 安全中心中的威胁管理策略
- 其他 Exchange Online 租户范围内设置
- SharePoint Online 管理中心中的租户范围内共享策略
- Azure Active Directory 中的设置 (Azure AD)

你还已[启用 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。

如果需要，请执行[第 3 步](infoprotect-configure-increased-security-office-365.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>可选：已在整个环境中配置分类

你已与法律和合规性团队合作，共同为组织的数据治理和安全策略制定了适当的分类和标签方案。 

这些策略对应于以下项的配置和部署：

- 敏感数据类型
- 保留标签
- 敏感度标签
- Azure 信息保护标签

如果需要，请执行[第 2 步](infoprotect-configure-classification.md)，这样做有助于满足此要求。 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>可选：在整个环境中部署 Windows 信息保护

你已注册 Windows 10 企业版设备，它们部署且应用了定义下列内容的 Intune 策略：

- 要保护的应用。
- 保护级别。
- 保护涵盖的范围。

必要时请执行[第 4 步](infoprotect-deploy-windows-information-protection.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-data-loss-prevention-dlp-is-deployed"></a>可选：部署数据丢失防护 (DLP)

你分析、测试并随后推广了 DLP 策略集；该集中注明了位置和条件及操作规则，而且你的组织需要它来保护客户和其他类型的专用数据，并借此满足行业和区域性的法规和要求。

你的数据合规与安全员工正在使用安全与合规仪表板来监视 DLP 事件。

必要时请执行[步骤 5](infoprotect-data-loss-prevention.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a>必需：为你的组织定义安全和信息保护级别

已根据组织的需要配置以下电子邮件加密：

|||
|:-------|:-----|
| **加密方法** | **对于已发送的电子邮件** |
| [Office 365 邮件加密 (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | 在组织外部加密 |
| [信息权限管理 (IRM)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | 具有加密和权限 |
| [安全/多用途 Internet 邮件扩展 (S/MIME)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | 具有加密和数字签名（使用公钥加密） |
|||

必要时请执行[步骤 6](infoprotect-email-encryption.md)，这样做有助于满足此要求。

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>可选：配置 Office 365 Privileged Access Management

你已使用[在 Office 365 中配置特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题中的信息来启用特权访问并在组织中创建一个或多个特权访问策略。 你已配置这些策略，且实时访问已启用，可访问敏感数据或关键配置设置。

如果需要，请执行[步骤 7](infoprotect-configure-privileged-access-management.md)，这样做有助于满足此要求。 

## <a name="results-and-next-steps"></a>结果和后续步骤

Microsoft 365 企业版的信息保护基础结构使用定义的安全级别、Office 365 增强安全性、使用敏感数据和标签的分类、Windows 信息保护、数据丢失防护、电子邮件加密以及特权访问权限管理。

如果你正在执行 Microsoft 365 企业版端到端部署，那么你现在已准备好让你的[工作负载和应用场景](deploy-workloads.md)充分利用底层基础结构的所有功能和配置。
