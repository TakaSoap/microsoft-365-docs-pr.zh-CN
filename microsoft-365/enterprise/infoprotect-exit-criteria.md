---
title: 信息保护基础结构退出条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 检查基于信息保护的服务和基础结构的条件，确保你的配置满足 Microsoft 365 企业版的要求。
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283690"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>信息保护基础结构退出条件

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

确保你的信息保护基础结构符合以下必需条件，以及你认为可选的那些条件。

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>必需：为你的组织定义安全和信息保护级别。

已计划并确定组织需要的安全级别。这些级别定义了最低安全级别，以及对敏感信息及其所需数据安全性提升保护的额外安全级别。

至少，当前需要使用三种安全级别：

- 基线
- 敏感
- 高度管控

如果需要，可在[步骤 1](infoprotect-define-sec-infoprotect-levels.md) 中进行设置以满足此要求。 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>必需：已配置增强的 Microsoft 365 安全性

你已配置 [Office 365 增强安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)的以下设置：

- Microsoft 365 安全中心中的威胁管理策略
- 其他 Exchange Online 租户范围内设置
- SharePoint 管理中心中的租户范围内共享策略
- Azure Active Directory 中的设置 (Azure AD)

你还已[启用 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/zh-CN/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。

如果需要，请执行[第 3 步](infoprotect-configure-increased-security-office-365.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>可选：已在整个环境中配置分类

你已与法律和合规性团队合作，为组织数据管理和安全策略制定了适当的分类和标签方案。 

这些策略对应于以下项的配置和部署：

- 敏感数据类型
- 保留标签
- 敏感度标签
- Azure 信息保护标签

如果需要，请执行[第 2 步](infoprotect-configure-classification.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>可选：配置 Office 365 Privileged Access Management

你已使用[在 Office 365 中配置特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题中的信息来启用特权访问并在组织中创建一个或多个特权访问策略。 你已配置这些策略，且实时访问已启用，可访问敏感数据或关键配置设置。

如果需要，请执行[第 4 步](infoprotect-configure-privileged-access-management.md)，这样做有助于满足此要求。 

## <a name="results-and-next-steps"></a>结果和后续步骤

Microsoft 365 企业版的信息保护基础结构使用定义的安全级别、Office 365 增强安全性、使用敏感数据和标签的分类以及特权访问权限管理。

如果你正在执行 Microsoft 365 企业版端到端部署，那么你现在已准备好让你的[工作负载和应用场景](deploy-workloads.md)充分利用底层基础结构的所有功能和配置。
