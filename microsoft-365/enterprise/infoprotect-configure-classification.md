---
title: 第 2 步：配置环境分类
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置对组织中的数据进行分类的各种方法。
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865597"
---
# <a name="step-2-configure-classification-for-your-environment"></a>第 2 步：配置环境分类

** 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

在步骤此中，配合法律和合规性团队来定义组织数据的分类方案。

## <a name="microsoft-classifications"></a>Microsoft 分类

Microsoft 365 包括三种类型的分类：

- Office 365 敏感信息类型
- Office 365 标签
- Azure 信息保护标签和保护

### <a name="sensitive-information-types-for-office-365"></a>Office 365 敏感信息类型

Office 365 敏感信息类型定义了自动化过程（如搜索）如何识别运行状况服务号和信用卡号等的特定信息类型。使用敏感信息类型可以查找敏感数据，并应用数据丢失防护规则和策略来保护此数据。有关详细信息，请参阅[数据丢失防护策略概述](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。例如，敏感信息类型对于满足合规性和法规要求（如一般数据保护条例 (GDPR)）特别有帮助。

### <a name="office-365-labels"></a>Office 365 标签
可将 Office 365 标签用于存储在 SharePoint Online 和 OneDrive for Business 中的个人数据和高度管控文件以及商业机密文件。有关详细信息（包括如何创建它们），请参阅[标签概述](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)。

如果决定使用 Office 365 标签，应为每个级别的保护配置至少一个标签。例如，为以下安全级别创建三个标签：

- 基线
- 敏感
- 高度管控

### <a name="azure-information-protection-labels-and-protection"></a>Azure 信息保护标签和保护

可使用 Azure 信息保护标签进行分类，并选择性地保护组织文档和电子邮件。这些标签可应用到存储在 Office 365 外部的文档。这些标签即可以由定义规则和条件的管理员自动应用，也可以由用户手动应用，或者可以在建议的情况下用户通过组合这两种方式来应用标签。

若要规划和部署 Azure 信息保护标签和保护，请执行下列操作：

1. 审阅 [Azure 信息保护要求](https://docs.microsoft.com/information-protection/get-started/requirements)。
2. 请按照[分类、标签和保护的部署路线图](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)。

有关详细信息，请参阅 [Azure 信息保护文档库](https://docs.microsoft.com/information-protection/)。

## <a name="classification-for-gdpr"></a>GDPR 分类

有关包括个人数据的 GDPR 分类方案示例，请参阅[为个人数据构建分类方案](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：数据分类](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step3)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[为 Office 365 配置提高的安全性](infoprotect-configure-increased-security-office-365.md)|

