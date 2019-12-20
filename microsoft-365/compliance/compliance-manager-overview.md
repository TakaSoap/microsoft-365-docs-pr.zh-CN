---
title: Microsoft 合规性管理器概述
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: 97cbc676f9de070d1532d1e56c96db0efcce8bd0
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807331"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft 合规性管理器（预览）

> [!IMPORTANT]
> 由世纪互联运营的 Office 365、Office 365 Germany、Office 365 U.S. Government Community High (GCC High) 或 Office 365 Department of Defense 不提供合规性管理器。

[Microsoft 合规性管理器（预览版）](https://servicetrust.microsoft.com/ComplianceManager)是一个基于工作流的免费风险评估工具，可让您跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。 您的 Microsoft 365、Office 365 或 Azure Active Directory 订阅的一部分，合规性管理器可帮助您管理 Microsoft 云服务的共享职责模型中的法规遵从性。 合规性管理器提供了一个集中的仪表板，用于查看 Microsoft service 评估的标准、法规和控制实施详细信息和测试结果。 它还包括允许您管理特定于您的组织的自定义控件实现和合规性跟踪的工具。

使用合规性管理器，您的组织可以：
  
- 结合了 Microsoft 为审计员和管理机构提供的详细合规性信息，以及有关适用于您的组织的标准和规章的合规性自我评估的云服务。 其中包括国际标准化组织（ISO）、美国国家标准和技术协会（NIST）、健康保险便携性和责任法案（HIPAA）中列出的标准和法规（常规数据）保护规章（GDPR）和其他许多。
- 使您能够分配、跟踪和记录符合性和与评估相关的活动，这些活动可帮助您的组织跨团队障碍实现合规性目标。
- 提供符合性分数以帮助您跟踪进度并设置审核控件的优先级，以帮助减少组织对风险的暴露程度。
- 为您提供一个安全存储库，以便上载和管理与合规性活动相关的证据和其他项目。
- 生成详尽的 Microsoft Excel 报告，这些报告记录由 Microsoft 和您的组织为审计员、管理机构和其他合规性审阅者执行的合规性活动。

> [!NOTE]
> 合规性管理器中提供的客户操作是建议;在实现之前，你的组织可以评估这些建议在其各自的法规环境中的有效性。 在合规性管理器中找到的建议不应解释为合规性保证。

## <a name="compliance-manager-relationships"></a>合规性管理器关系

合规性管理器使用多个组件来帮助你实现合规性管理活动。 这些组件协同工作，为审计员提供完整的管理工作流和无障碍的合规性报告。

图中显示了合规性管理器的主要组件之间的关系：

![合规性管理器版本3中的关系](media/compliance-manager-relationships.png)

## <a name="groups"></a>组

[组](working-with-compliance-manager.md#groups)是允许您组织评估的容器，并在评估之间共享具有相同或相关的客户托管控件的常见信息和工作流任务。 当同一个组中的两个不同评估共享客户托管控件时，该控件的实现详细信息、测试和状态的完成将自动同步到组中任何其他评估中的相同控件。 这将统一分配给组中每个控件的已分配操作项并减少重复工作。 您还可以选择使用组进行组织。 按年、区域、合规性标准或其他分组进行评估，以帮助组织合规性工作。

## <a name="assessments"></a>评估

[评估](working-with-compliance-manager.md#assessments)是允许您根据 Microsoft 与组织之间共享的职责来组织控制，以评估云服务安全性和合规性风险的容器。 评估可帮助您实施由合规性标准和适用的数据保护标准、法规或法律指定的数据保护安全措施。 它们可帮助您针对选定 Microsoft 云服务的所选行业标准来辨别您的数据保护和合规性状况。 评估通过在与证书标准对应的评估中包含的控制实施完成。

默认情况下，合规性管理器将为您的组织创建以下评估：

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 GDPR

评估包括以下几个组件：
  
- **范围内的服务**：每个评估适用于一组特定的 Microsoft 服务。
- **Microsoft 托管控件**：对于每个云服务，microsoft 实施并管理一组适用标准和管理法规的合规性控制。
- **客户管理的控件**：这是您对每个控件执行操作时由您的组织实现的控件的集合。
- **评估分数**：评估中客户管理的控件的总可能分数的百分比。 这可帮助您跟踪分配给每个控件的操作的实现。

## <a name="controls"></a>控件

[控件](working-with-compliance-manager.md#controls-and-actions)是合规性管理器中的合规性流程容器，用于定义管理合规性活动的方式。 这些控制措施被组织为与相应证书或法规的评估结构一致的控制系列。

- **控件 ID**：所选控件在相应的证书或法规中的名称。
- **控件标题**：来自相应的证书或法规的控件 ID 的标题。
- **文章 ID**：此字段仅用于 GDPR 评估，并指定相应的 GDPR 文章编号。
- **说明**：来自相应证书或法规的控制文本。 由于版权限制，针对 ISO 标准列出了相关信息的链接。

![合规性管理器版本3中的控件](media/compliance-manager-controls.png)

合规性管理器、 **Microsoft 托管控件**、**客户托管控件**和**共享管理控件**中有三种类型的控件

### <a name="microsoft-managed-controls"></a>Microsoft 托管控件

对于每个云服务，Microsoft 实施并管理一组控件作为 Microsoft 符合各种标准和法规的一部分。 每个控件都提供了有关 Microsoft 如何实现控件的详细信息，以及 Microsoft 和/或独立第三方审计员对该实施进行测试和验证的方式和时间的详细信息。

### <a name="customer-managed-controls"></a>客户管理的控件

这是由您的组织管理的控件的集合。 您的组织负责客户托管的控制实施，作为给定标准或法规的合规性流程的一部分。 将客户管理的控件组织为相应的证书或法规的控制系列。 使用客户托管的控件来实施 Microsoft 建议的建议操作，作为合规性活动的一部分。 您的组织可以使用每个客户托管控件中的规范性指南和建议的客户操作来管理该控件的实施和评估过程。

评估中的客户管理的控件还具有内置工作流管理功能，可用于管理和跟踪评估完成的进展情况。 使用此工作流功能，可以执行以下操作：

- 为每个控件分配操作项
- 跟踪分配的交办事项
- 上载控件实现的证据
- 记录控件的测试和验证
- 将操作项标记为已实现和已测试

例如，贵组织中的合规性监察官将操作项分配给 IT 管理员，并具有执行建议操作所需的责任和必要权限。 IT 管理员上载实施任务的证据（配置或策略设置的屏幕截图），并在完成后将措施项分配回合规专员。 合规性监察官评估收集的证据，测试控件的实现，并在合规性管理器中记录实施日期和测试结果。

### <a name="shared-management-controls"></a>共享管理控件

共享控件指的是 Microsoft 和客户共同承担实施责任的任何控制。 例如，与人员屏蔽、帐户和密码管理以及加密相关的控件都需要由 Microsoft 和客户执行操作。

## <a name="action-items"></a>拟办事项

[操作项](working-with-compliance-manager.md#controls-and-actions)以内置工作流管理功能的一部分的形式包含在客户托管的控件中，可用于管理和跟踪评估完成的进展情况。

组织中的人员可以使用合规性管理器从其分配的所有评估中查看客户托管的控件。 用户登录合规性管理器并打开“**操作项目**”仪表板时，会显示分配给他们的操作项目列表。 根据分配给用户的合规性管理器角色，他们可以提供实施或测试详细信息，更新状态或分配操作项目。

证书控制通常由一个人实施，并由另一个人测试。 例如，在最初分配给一个人员以实现实施后，会将这些操作项分配给下一个测试和上载证据的人员。 对控制分配具有足够权限的任何用户都可以分配和重新分配操作项目。 这样可以集中管理控制分配以及 implementors 和测试人员之间的操作项目的分散路由。

## <a name="permissions"></a>Permissions

合规性管理器使用基于角色的访问控制权限模型。 只有分配了用户角色的用户可访问合规性管理器，并且每位用户允许的操作受到角色类型的限制。 [查看](working-with-compliance-manager.md#permissions)显示每个权限允许执行的操作的表。

门户管理员合规性管理器可以通过执行以下步骤，在合规性管理器中设置其他用户的权限：

1. 从 "最**多**" 下拉菜单中依次选择 "**管理员**" 和 "**设置**"。
2. 在此处，选择要分配的角色，然后添加要分配给该角色的员工。 然后，用户将能够执行某些操作。

此外，在[Azure Active Directory （AZURE AD）中分配了全局读者角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)的用户拥有访问合规性管理器的只读权限。 但是，他们无法在合规性管理器中编辑数据或执行任何操作。

不再存在默认**来宾访问**角色。 必须为每位用户分配一个角色，使其可访问合规性管理器并在其中工作。
  
## <a name="manage-evidence"></a>管理证据

合规性管理器可以在测试和验证客户托管的控件方面存储实施任务的证据。 证据包括文档、电子表格、屏幕截图、图像、脚本、脚本输出文件和其他文件。 合规性管理器还会自动接收遥测并为与安全得分集成的措施项创建证据记录。 作为证据上传到合规性管理器中的任何数据均存储在 Microsoft 云存储站点上的美国。 此数据在位于东南亚和西欧的 Azure 区域之间复制。

## <a name="templates"></a>模板

合规性管理器为评估提供预先配置的[模板](working-with-compliance-manager.md#templates)，并允许您为客户托管的控件创建自定义模板，以满足您的合规性需求。 新模板是通过导入 Excel 文件中的控件信息来创建的，也可以通过现有模板的副本创建模板。

合规性管理器附带的预配置模板为：

1. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
2. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
3. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
4. [NIST 800-53 修订版4](https://go.microsoft.com/fwlink/?linkid=2109075)
5. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
6. [NIST Cybersecurity Framework （CSF）](https://go.microsoft.com/fwlink/?linkid=2108868)
7. [云安全联盟（CSA）云控制矩阵（CCM）3.0。1](https://go.microsoft.com/fwlink/?linkid=2109076)
8. [联邦金融机构检查委员会（FFIEC）信息安全手册](https://go.microsoft.com/fwlink/?linkid=2109077) 
9. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / 高[科技](https://go.microsoft.com/fwlink/?linkid=2109079)
10. [FedRAMP 中等](https://go.microsoft.com/fwlink/?linkid=2108869)
11. [欧洲联合 GDPR](https://go.microsoft.com/fwlink/?linkid=2108870)
12. [加利福尼亚州消费者隐私法案（CCPA）](https://go.microsoft.com/fwlink/?linkid=2108871) （预览）
13. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [澳大利亚政府版 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) （预览）
14. [Microsoft 365 数据保护基准](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)

## <a name="compliance-score"></a>合规性分数

[Microsoft 合规性分数（预览版）](compliance-score.md)是 microsoft 365 合规性中心中的一项功能，可帮助您了解组织的合规性状况。 它将计算基于风险的分数，以衡量您在帮助降低数据保护和法规标准方面的风险的完成操作的进度。 了解您的总体合规性分数可帮助您的组织了解和管理合规性。 了解[如何计算合规性分数](compliance-score-methodology.md)。
  
> [!IMPORTANT]
> 合规性分数不表示对任何特定标准或法规的组织合规性的绝对衡量。 它表示您已采用的控制程度，可降低个人数据和个人隐私的风险。 任何服务都不能保证您符合标准或法规，并且不应以任何方式将合规性分数解释为保证。

## <a name="secure-score-integration"></a>安全分数集成

合规性管理器与[Microsoft 安全分数](../security/mtp/microsoft-secure-score.md)集成，以自动对同步交办事项的合规性分数应用安全分数积分。 这可在全局操作项或全局操作中进行配置，并提供安全分数的更新。

例如，您对在组织中激活 Azure 权限管理（也适用于与合规性相关的措施项）进行安全相关的要求。 当 Azure 权限管理激活并按安全分数处理时，合规性管理器会收到更新通知，并且该措施项的得分会自动更新为完成信用。

## <a name="ready-to-get-started"></a>准备好开始了吗？

开始[使用合规性管理器](working-with-compliance-manager.md)来管理组织的法规遵从性活动。

## <a name="resources"></a>资源

- [交互式指南：使用合规性管理器评估和增强数据保护控制](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft 安全、隐私和合规性技术社区](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)
