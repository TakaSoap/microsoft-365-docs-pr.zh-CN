---
title: 信息保护基础结构退出条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 检查基于信息保护的服务和基础结构的条件，确保你的配置满足 Microsoft 365 企业版的要求。
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865927"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>信息保护基础结构退出条件

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

完成底层基础结构之前，请确保信息保护基础结构满足以下条件。 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>必需：为你的组织定义安全和信息保护级别。

已计划并确定组织需要的安全级别。这些级别定义了最低安全级别，以及对敏感信息及其所需数据安全性提升保护的额外安全级别。

至少，当前需要使用三种安全级别：

- 基线
- 敏感
- 高度管控

如果需要，[步骤 1](infoprotect-define-sec-infoprotect-levels.md) 可以帮助你满足此要求。 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a>必需：已配置增强的 Office 365 安全性

为了提升安全性，已根据[配置 Office 365 租户以提高安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)中的信息配置以下设置：

- Office 365 安全与合规中心的威胁管理策略
- 其他 Exchange Online 租户范围内设置
- SharePoint 管理中心中的租户范围内共享策略
- Azure Active Directory 中的设置

此外，已[启用 Office 365 高级威胁防护 (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)。

如果需要，请执行[第 3 步](infoprotect-configure-increased-security-office-365.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>可选：已在整个环境中配置分类

你已与法律和合规性团队合作，为组织数据制定了适当的分类和标签方案，包括以下内容：

- 敏感数据类型
- Office 365 标签
- Azure 信息保护标签

如果需要，请执行[第 2 步](infoprotect-configure-classification.md)，这样做有助于满足此要求。 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>可选：配置 Office 365 Privileged Access Management

已根据[配置 Office 365 Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 主题中的信息启用特权访问，并在 Office 365 组织中创建一个或多个特权访问策略。已配置这些策略，并已启用实时访问权限，可访问敏感数据或关键配置设置。

如果需要，请执行[第 4 步](infoprotect-configure-privileged-access-management.md)，这样做有助于满足此要求。 

## <a name="next-step"></a>后续步骤

现已准备好部署[工作负载和方案](deploy-workloads.md)，如在 Microsoft 365 企业版底层基础结构之上运行的 Microsoft Teams 和 Exchange Online。
