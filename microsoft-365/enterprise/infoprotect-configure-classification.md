---
title: 第 2 步：配置环境分类
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
description: 了解并配置对组织中的数据进行分类的各种方法。
ms.openlocfilehash: e8c40ca4c419edc2d59a060dfd4fe8918cf4e784
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544181"
---
# <a name="step-2-configure-classification-for-your-environment"></a>第 2 步：配置环境分类

*此步骤可选，它适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![第 6 阶段：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

在步骤此中，配合法律和合规性团队来定义组织数据的分类方案。

## <a name="microsoft-365-classification-types"></a>Microsoft 365 分类类型

Microsoft 365 包括四种类型的分类：

- 敏感信息类型
- 保留标签
- 敏感度标签
- Azure 信息保护标签和保护

### <a name="sensitive-information-types"></a>敏感信息类型

Microsoft 365 中的敏感信息类型定义了自动化流程（例如搜索）如何识别特定信息类型。 这些信息包括员工或客户的敏感数据，例如医疗服务号码和信用卡号。 你可以使用敏感信息类型查找敏感数据并应用数据丢失保护 (DLP) 规则策略，以保护这些数据。 有关详细信息，请参阅 [DLP 策略包含的内容](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains)。 

敏感信息类型对于满足合规性和法规要求（例如通用数据保护条例 (GDPR)）尤其有用。

### <a name="retention-labels"></a>保留标签

定义数据管理策略的一部分就是确定特定类型的文档或含有特定内容的文档应保留多长时间，以符合组织政策和区域法规要求。 例如，某些类型的文档应在保留一段时间之后删除，有些文档则必须永久保留。

对于 Microsoft 365 中存储的文档，你可以对 Exchange 电子邮件、SharePoint Online、OneDrive for Business 和 Teams 聊天和渠道消息中存储的文档和数据定义并应用保留标签。 

如果使用保留标签，则应为需要应用保留标签的每个类别的文件创建标签。 在保留标签中，你可以指定：

- 一组文件描述符（例如，按业务部门、文件类别或法规）。
- 已附加保留标签的文件的保留设置，例如保留时间以及达到保留时间之后的行为。

也可以通过配置 SharePoint Online 网站将默认保留标签应用到网站中的所有新文档，以此为文件自动应用保留标签。 

有关详细信息，请参阅[保留标签概述](https://docs.microsoft.com/office365/securitycompliance/labels)。

### <a name="sensitivity-labels"></a>敏感度标签

为特定类型的文档或含有特定内容的文档提供保护和实施安全措施的一部分就是将其贴上标签，以便应用其他安全性。 借助 Microsoft 365 中的敏感度标签，你可以：

- 执行保护设置，例如加密、权限或添加水印。
- 使用 Windows 信息保护 (WIP) 终结点保护阻止此类内容被复制到第三方应用（如 Twitter 或 Gmail），或者被复制到可移除存储设备（如 U 盘）。
- 使用 Microsoft Cloud App Security (CAS) 保护第三方应用和服务中的内容。 
- 对内容进行分类，无需使用任何保护设置。

如果使用敏感度标签，则应为每个安全和信息保护级别配置标签。 例如，为以下对象创建三个敏感度标签：

- 基线
- 敏感
- 高度管控

如果你在 SharePoint Online 网站中存储包含高度管控数据的文件，并且希望在文件离开网站时，这些文件具有与网站相同的权限，则需要创建一个额外的敏感标签，其权限与该网站相同。

有关详细信息，请参阅此[敏感度标签概述](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels)。

### <a name="azure-information-protection-labels-and-protection"></a>Azure 信息保护标签和保护

可以使用 Azure 信息保护标签来分类并选择性地保护组织的文档和电子邮件。 这些标签可以应用于存储在 Microsoft 365 之外的文档。 这些标签可以由定义规则和条件的管理员自动应用、由用户手动应用或是组合应用（在这种情况下会向用户提供建议）。

若要规划和部署 Azure 信息保护标签和保护，请执行下列操作：

1. 审阅 [Azure 信息保护要求](https://docs.microsoft.com/information-protection/get-started/requirements)。
2. 请按照[分类、标签和保护的部署路线图](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)。

有关详细信息，请参阅 [Azure 信息保护文档库](https://docs.microsoft.com/information-protection/)。

现有 Azure 信息保护标签与敏感度标签无缝工作。 例如，你可以保留现有 Azure 信息保护标签以及应用于文档和电子邮件的标签。

如果使用了敏感度和 Azure 信息保护标签，则应[将 Azure 信息保护标签迁移到敏感度标签](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels)。

## <a name="example-classification-for-gdpr"></a>示例：GDPR 分类

有关包括个人数据的 GDPR 分类方案示例，请参阅[为个人数据构建分类方案](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)。

## <a name="take-it-for-a-test-drive"></a>体验一下

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：数据分类](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step2)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 3 步](../media/stepnumbers/Step3.png)|[为 Office 365 配置提高的安全性](infoprotect-configure-increased-security-office-365.md)|

