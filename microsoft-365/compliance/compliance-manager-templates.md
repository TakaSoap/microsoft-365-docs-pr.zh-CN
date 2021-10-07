---
title: 使用 Microsoft 合规性管理器中的评估模板
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用和管理模板在 Microsoft 合规性管理器中生成评估。 使用格式化的文件创建和修改Excel模板。
ms.openlocfilehash: 56bbe69b6baaa996a1b63e20ca657641b9da9038
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173555"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>在合规性管理器中使用评估模板

**本文内容：** 了解 **模板如何工作****以及如何从评估模板** 页管理它们。 获取有关创建新 **模板**、扩展和修改现有模板、使用 Excel 设置模板数据格式以及导出模板报告 **的说明**。 

> [!IMPORTANT]
> 组织可用的评估模板取决于您的许可协议。 [查看详细信息](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="templates-overview"></a>模板概述

模板是在合规性管理器中用于创建评估的控制措施框架。 我们全面的模板集可帮助你的组织遵守管理数据的收集和使用的国家、区域和行业特定要求。

我们按与基础认证或法规相同的名称来引用模板，例如欧盟 GDPR 模板和 ISO/IEC 27701：2019 模板。 由于合规性经理可用于评估不同类型的产品，因此每个模板有两个版本：一个版本适用于 Microsoft 365，另一个版本可定制为适合你选择的产品。

请注意，美国政府 Community (GCC) 、GCC 高和国防部 (DoD) 客户当前可以使用 Microsoft 365 模板版本，但并非通用。

## <a name="template-availability-and-licensing"></a>模板可用性和许可

合规性管理器中包含两类模板：包含模板和高级模板。

1. **包含的** 模板由合规性管理器许可证授予，涵盖了关键法规和要求。 若要了解有关根据许可协议提供哪些模板的详细信息，请参阅 [许可详细信息](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。
2. **高级版模板** 来涵盖其他需求和方案，可以通过购买模板许可证获得。

开始创建评估时，合规性管理器将跟踪处于活动状态的模板数，以便你可以监视使用情况。 若要了解更多信息，请参阅 [活动模板和非活动模板](compliance-manager-templates.md#active-and-inactive-templates)。

查看 [合规性管理器中可用的](compliance-manager-templates-list.md) 模板的完整列表。

### <a name="purchase-premium-template-licenses"></a>购买高级模板许可证

模板许可证可通过这些方法中的一种或多种方法获取，具体取决于合规性管理器许可协议。 完成购买后，模板应在 48 小时内在租户中可用。

**商业和GCC中等**

商业和GCC中等帐户可以在管理中心购买模板许可证 ([了解有关](/microsoft-365/commerce/)订阅、许可证和帐单) 。 选择要购买的许可证数量和付款计划。

购买链接：

- [商业](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCC中等](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

您还可以通过参与许可计划或批量许可[云解决方案提供商获取](https://partner.microsoft.com/membership/cloud-solution-provider)[许可证](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)。

**GCC高帐户和 DOD 帐户**

GCC高和 DOD 帐户必须通过批量许可购买[模板许可证](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)。

### <a name="try-out-premium-templates"></a>试用高级模板

若要在购买前试用高级模板，还可以获取许可证的试用版。 试用版许可证适用于最多 25 个模板，最多为 90 天。 获取试用版许可证后，模板应在 48 小时内在租户中可用。

若要启动试用版，请选择适合贵组织的链接：

- [商业](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/e320704d-b7c9-4012-b6a6-0a2679790360)
- [GCC中等](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/87ed2908-0a8d-430a-9635-558ed42b581f)
- [GCC 高级](https://portal.office365.us/SubscriptionDetails?OfferId=e14362d7-2c11-4a43-9c92-59f1b499b96a)
- [DOD](https://portal.apps.mil/Commerce/Trial.aspx?OfferId=17e28290-7de6-41a9-af30-f6497396ab2e)

#### <a name="active-and-inactive-templates"></a>活动模板和无效模板

模板将显示激活状态为活动状态或非活动状态：

- 从该模板 **创建** 评估后，该模板将被视为活动模板。
- 如果您的 **组织未将** 模板用于评估，则认为该模板处于非活动状态。

如果将任何评估链接到已购买的高级模板，该模板将处于活动状态一年。 除非你取消购买，否则你的购买将自动续订。

还可以试用高级模板。 试用版许可证适用于最多 25 个模板，试用期为 30 天。 试用版开始后，模板应在 48 小时内在租户中可用。 试用可以通过 Microsoft 365 管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">激活。</a>

#### <a name="activated-templates-counter"></a>激活的模板计数器

你的评估页面和评估模板页面顶部附近有一 **个** 已激活的模板计数器。 计数器显示根据许可协议，你有资格使用的模板数。 模板使用在认证级别计数。

例如，如果计数器显示 2/5，则意味着你的组织已激活 5 个模板中的 2 个模板可供使用。

如果计数器显示 5/2，则表明你的组织超出其限制，需要购买 3 个使用中的高级模板。

Microsoft 365和通用版本的模板具有联合许可，因此可以在多个产品之间使用相同的基础认证。 使用同一模板的任一或两个版本将仅计为一个激活的模板。

有关更多详细信息，请参阅合规性 [管理器许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。

## <a name="view-and-manage-templates"></a>查看和管理模板

合规性管理器中的"评估模板"页显示模板列表及其关键详细信息。 该列表包括合规性管理器提供的模板，以及组织已修改或创建的任何模板。 你可以应用筛选器，以根据认证、产品范围、国家/地区、行业、创建模板的人以及模板是否已启用评估创建来查找模板。

Select a template from its row to bring up its details page. 此页面包含模板的说明，以及有关认证、范围和控制详细信息的进一步信息。 在此页中，可以选择相应的按钮来创建评估、将模板数据导出到Excel，或修改模板。

## <a name="format-template-data-with-excel"></a>将模板数据格式化为Excel

The Excel spreadsheet (download [an example](https://go.microsoft.com/fwlink/?linkid=2124865)) used to create or modify templates has a specific format and schema that must be used in order to import correctly into Compliance Manager. 它包含四个选项卡，其中三个选项卡是必需的：

1. [模板](#template-tab) (模板) 
2. [ControlFamily](#controlfamily-tab) (必需) 
3. [需要](#actions-tab) (操作) 
4. [维度 (](#dimensions-tab) 可选) 

使用模板数据填写电子表格时，电子表格必须按上面列出的顺序包含选项卡，否则数据无法成功导入模板。

##### <a name="template-tab"></a>"模板"选项卡

" **模板** "选项卡是必需的。 此选项卡中的信息提供有关模板的元数据。 有四个必需列。 列必须保留工作表上Excel，如下所示。 您可以在这四列 **后** 添加您自己的列以提供您自己的维度。 如果这样做，请务必将它们添加到" **维度"** 选项卡。

- **title**：这是模板的标题，必须是唯一的。 它不能与合规性管理器中拥有的另一个模板共享名称，包括你自己的模板或合规性管理器模板。

- **product：** 这是一个必需维度。 列出与模板关联的产品。

- **certification：** This is the regulation you're using for the template.

- **inScopeServices：** 这些是此评估处理的服务 (例如，如果将 Office 365 列为产品，Microsoft Teams可能是范围内服务) 。 可以列出用两个分号分隔的多个服务。

> [!NOTE]
> 导入电子表格以创建或自定义模板后，无法编辑在产品和认证单元格中插入的数据。 此外，组不能包含具有相同产品/认证组合的 **两** 个评估。 你可以有多个模板，它们具有相同的产品/认证组合。

##### <a name="controlfamily-tab"></a>ControlFamily 选项卡

**"ControlFamily"** 选项卡是必需的。  此选项卡中必须遵循示例电子表格中提供的顺序的必需列包括：

- **controlName：** 这是认证、标准或法规中的控制名称，通常为某种 ID 类型。 控件名称在模板中必须是唯一的。 电子表格中不能有多个同名的控件。

- **controlFamily：** 为 controlFamily 提供一个字词或短语，用于标识控件的广泛分组。 controlFamily 不必是唯一的;它可以在电子表格中多次列出。 同一 controlFamily 也可以列在多个模板中，尽管它们相互之间没有任何关系。 每个 controlFamily 都必须映射到至少一个控件。

- **controlTitle：** 为控件提供标题。 controlName 是参考代码，而标题是一种格式文本格式，通常在法规中可见。

- **controlDescription：** 提供控件的说明。

- **controlActionTitle：** 这是要与此控件相关的操作的标题。 可以通过用两个分号分隔来添加多个操作，两者之间没有空格。 您列出每个控件都必须包含至少一个操作，并且该操作必须存在 (这意味着您可以列出您在同一电子表格的"操作"选项卡上列出的操作、存在于其他模板中的操作或由 Microsoft) 创建的操作。 不同的控件可以引用相同的操作。

##### <a name="actions-tab"></a>"操作"选项卡

" **操作** "选项卡是必需的。  它指定了由组织管理的改进操作，而不是 Microsoft 的改进操作，这些改进操作已存在于合规性管理器中。 此选项卡的必需列必须遵循示例电子表格中提供的顺序：

- **actionTitle：** 这是操作的标题，是必填字段。 你提供的标题必须是唯一的。 **重要** 提示：如果你引用了自己已有的操作， (如在另一个模板) 并修改后续列中的任何元素，这些更改将传播到其他模板中的同一操作。

- **implementationType：** 在此必填字段中，列出以下三种实现类型之一：
    - **操作** - 人员和流程实施的用于保护组织系统、资产、数据和人员的机密性、完整性和可用性 (例如：安全意识和培训) 
    - **技术** - 使用信息系统的硬件、软件或固件组件中包含的技术和机制完成的操作，以保护组织系统和数据的机密性、完整性和可用性 (例如：多重身份验证) 
    - **文档** - 通过已记录的策略和过程实施的操作，这些策略和过程建立和定义保护组织系统、资产、数据和人员的机密性、完整性和可用性所需的控件 (例如：信息安全策略) 

- **actionScore：** 在此必填字段中，为操作提供一个数值分数值。 该值必须是从 1 到 99 的整个数字;不能为 0、null 或空白。 数字越大，其改进合规性状态的价值就越高。 下图演示合规性管理器如何对控件进行评分：

  ![合规性管理器控制点值。](../media/compliance-score-action-scoring.png "合规性管理器控制点值")

- **actionDescriptionTitle：** 这是说明的标题，是必需的。 此说明标题允许您在多个模板中执行相同的操作，并在每个模板中显示不同的说明。  此字段可帮助您阐明说明引用的模板。 在大多数情况下，可以在此字段中输入要创建的模板的名称。

- **actionDescription：** 提供操作的说明。 可以应用加粗文本和超链接等格式。 这是必填字段。

- **dimension-Action Purpose**：这是一个可选字段。 如果包含，则标头必须包含"dimension-"前缀。 你在此处包括的任何维度都将用作合规性管理器中的筛选器，并出现在合规性管理器中的改进操作详细信息页面上。

##### <a name="dimensions-tab"></a>"维度"选项卡

" **维度"** 选项卡是可选的。 但是，如果在其他地方引用维度，如果已创建的模板或 Microsoft 模板中不存在维度，则需要在此处指定该维度。 下面列出了此选项卡的列：

- **dimensionKey：list** as "product"、"certifications"、"action purpose"
- **dimensionValue**：示例：Office 365、HIPPA、预防、检测

导出现有模板时，导出的电子表格将具有"维度"选项卡，其中列出了模板中使用的所有维度。

## <a name="create-an-assessment-template"></a>创建评估模板

若要为自定义评估创建自己的新模板，你将使用经过特殊格式Excel电子表格来组合必要的控制数据。 完成电子表格后，将其导入合规性管理器。

#### <a name="required-roles"></a>所需角色

只有具有全局管理员或合规性管理器管理角色的用户才能创建和修改模板。 详细了解角色 [和权限](compliance-manager-setup.md#set-user-permissions-and-assign-roles)。

### <a name="create-new-template-in-compliance-manager"></a>在合规性管理器中创建新模板

1. 转到合规性 **管理器中的** 评估模板页面。
2. 选择 **"创建新模板"。** 将打开模板创建向导。
3. 选择要创建的模板类型。 在这种情况下，请选择"**创建自定义模板"，** 然后选择"下一 **步"。**
4. 在 **"Upload文件**"屏幕上，选择"浏览"查找并上载包含所有所需Excel模板数据的格式化文件。
5. 如果文件没有问题，将显示上载的文件的名称。 选择“**下一步**”以继续。  (如果需要更改文件，请选择"更改Upload **文件") 。**
    - 如果文件出错，顶部的错误消息将说明错误。 你将需要修复文件并再次上传它。 如果电子表格的格式不正确，或者某些字段中的信息无效，则会导致错误。
6. " **审阅和完成"** 屏幕显示改进操作和控件的数量以及模板的最大分数。 准备好批准后，选择" **创建模板"。**  (如果需要进行更改，请选择"上 **一** 步") 
7. 最后一个屏幕确认已创建一个新模板。 选择 **"完成** "退出向导。
8. 你将到达新模板的详细信息页面，可在其中 [创建评估](compliance-manager-assessments.md#create-assessments)。

## <a name="extend-microsoft-365-assessment-templates"></a>扩展Microsoft 365评估模板

合规性管理器提供将你自己的控制措施和改进操作添加到 Microsoft 提供的现有模板的选项。 此过程称为扩展 Microsoft 模板。 扩展模板时，它仍然可以接收 Microsoft 发布的更新，当相关法规或产品策略发生更改时，可能会 (接受评估更新) 。 [](compliance-manager-assessments.md#accept-updates-to-assessments)

请注意，如果您要为除产品外的其他产品设置Microsoft 365，您的流程将有所不同。 若要了解更多信息，请参阅 [扩展通用评估模板](#extend-universal-assessment-templates)。

### <a name="prepare-template-data-and-create-extension"></a>准备模板数据和创建扩展

若要准备，您需要组合一个特殊格式的电子表格Excel导入必要的模板数据。 这些Excel文件遵循上面所述的相同常规格式，但扩展有特殊要求。 请参阅以下其他要点以帮助防止错误：

- 电子表格应仅包含要添加到评估的操作和控制。
- 电子表格不能包含要修改的评估中已存在的任何控件或操作。
- 请考虑在模板标题中包括"扩展名"，例如，"GDPR – [你的公司名称]扩展名"。 这样，与 Microsoft 提供的标准模板或名称相似的自定义模板不同，更易于在评估模板页面上的列表中进行标识。

设置电子表格格式后，请按照以下步骤操作。

1. 转到评估 **模板页面，** 然后选择 **创建新模板**。 将打开模板创建向导。

2. 选择要创建的模板类型。 在这种情况下，请选择"**扩展 Microsoft 模板"，** 然后选择"**选择 Microsoft 模板"。**

3. 模板选择飞出窗格显示在屏幕的右侧，其中显示所有模板的列表及其活动状态或非活动状态。 激活 **的模板** 计数器显示当前使用的模板数，该数量与可供使用的模板总数之比。 如果超过限制，消息栏将发出通知。

4. 模板选择飞出窗格显示在屏幕的右侧。 使用 **搜索** 应用筛选器以查找您想要的模板

5. 找到模板后，选择其名称左侧的单选按钮，然后选择"保存 **"。**

6. 下一个屏幕将显示所选的模板。 如果正确，请选择"下一 **步"。**  (如果不正确，请选择" **选择其他模板** "以再次选择。) 

7. 在 **"Upload文件**"屏幕上，选择"浏览"查找并上载包含所有所需Excel模板数据的格式化文件。

8. 如果文件没有问题，下一个屏幕将显示已上传文件的名称。 如果需要 **更改** (，请选择"下一步"以继续Upload **文件) 。**

    - 如果文件有问题，顶部会显示一条错误消息，说明错误所在。 你需要修复并重新上传文件。 如果电子表格的格式不正确，或者某些字段中的信息无效，则会导致错误。

9. " **审阅和完成"** 屏幕显示改进操作和控件的数量以及模板的最大分数。 准备好批准后，选择"下一 **步"。**  (如果需要进行更改，请选择Upload **文件 .)**

10. 最后一个屏幕确认已创建一个新模板。 选择 **"完成** "退出向导。

11. 你将到达新模板的详细信息页面。 从此处，可以通过选择创建评估 **来创建评估**。 有关指导，请参阅 [生成和管理评估](compliance-manager-assessments.md#create-assessments)。

## <a name="extend-universal-assessment-templates"></a>扩展通用评估模板

还可以扩展模板的通用版本以自定义特定于产品的评估。 在使用通用模板创建评估且评估具有独特的产品和认证组合时，你将收到一个特殊的扩展模板。 可对其进行修改以满足你的需求。 有关如何编辑模板的指南，请参阅以下有关修改模板的说明。

编辑通用模板时，可更改模板中所有的内容，但这样做会中断与父模板的继承关系。 这意味着，如果刷新父模板，它将不再自动接收来自 Microsoft 的更新。

## <a name="modify-a-template"></a>修改模板

您可能需要修改已创建的模板，例如添加控件，或者添加或删除改进操作。 此过程类似于模板创建过程，你将使用模板数据Excel格式化文件。

但是，当您使用对现有模板数据的更改设置文件格式时，请注意一些详细信息。 **我们建议您仔细阅读这些说明，以确保不会覆盖要保留的任何现有数据。**

### <a name="format-your-excel-file-to-modify-an-existing-template"></a>设置Excel文件的格式以修改现有模板

从 **评估模板页面中**   ，选择要修改的模板，这将显示其详细信息页面。 然后选择导出 **到Excel。** 将Excel模板数据的文件。 将文件保存到本地计算机。

若要使用此文件，请跳转到下面的部分，以快速找到所需的说明：

- [编辑主模板属性](#edit-the-main-template-attributes)
- [添加改进操作](#add-an-improvement-action)
- [编辑改进操作的信息](#edit-an-improvement-actions-information)
- [更改改进操作的名称](#change-an-improvement-actions-name)
- [删除改进操作](#remove-an-improvement-action)
- [删除控件](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>编辑主模板属性

在 **"模板"** 选项卡上，可以编辑标题列 **、inScopeServices** 列以及您可能已添加的其他任何列中的任何内容。 但是，你无法编辑产品或 **认证** 列中 **的任何** 内容。

#### <a name="add-an-improvement-action"></a>添加改进操作

1. 转到" **操作"** 选项卡。将信息添加到现有操作下第一个空行的必填字段中。
2. 转到 **"ControlFamily"** 选项卡。查找包含改进操作映射到的控件的行。 将新操作添加到该行的 **controlActionTitle** 列 (请记住，用两个分号分隔此字段中的多个操作，两者之间没有空格) 。
3. 保存电子表格。

#### <a name="edit-an-improvement-actions-information"></a>编辑改进操作的信息

您可以更改除标题 之外的任何 *改进操作的信息*。 您可以编辑 B 列前向的任何单元格，当您将文件导入回模板时，该模板中的改进操作现在将包含更新的数据。

您无法编辑 A **列** (操作) 因为如果您这样做，合规性管理器会认为这是一个新的改进操作。 如果要更改改进操作的名称，请参阅下面的说明。

#### <a name="change-an-improvement-actions-name"></a>更改改进操作的名称

如果要更改改进操作的名称，您必须在电子表格中明确指定将现有名称替换为新名称。 请按以下步骤操作：

1. 在电子表格 **的"** 操作"选项卡中，在 A 列之后向电子表格添加新列。
2. 在此新列（现在为 B 列）中，放在第 1 行中作为标题 **：oldActionTitle**。
3. 复制 A 列的内容并将其粘贴到 B 列。这会将现有改进操作标题（即要更改的标题）放入 B 列。
4. 在列 A **和 actionTitle** 中，删除旧名称，并将其替换为改进操作的新名称。

请注意，对于改进操作和 Microsoft 操作，操作标题都必须以英语编写，才能在控件中引用时被识别。

#### <a name="remove-an-improvement-action"></a>删除改进操作

若要从模板中删除改进操作，需要将其从引用它的每个控件中删除。 请按照以下步骤修改电子表格：

1. 在 **ControlFamily** 选项卡上，搜索要删除的改进操作的标题。
2. 在显示改进操作的单元格中删除它的标题。 如果改进操作是该行上的唯一操作，请删除该行 (删除控件) 。
3. 在 **"操作** "选项卡上，删除包含要删除的改进操作的行。
4. 保存电子表格。

当您将电子表格导入回模板时，您的改进操作将从模板中删除。

从模板中删除改进操作不会从合规性管理器中完全删除改进操作。 该操作仍可由另一个模板引用。

#### <a name="remove-a-control"></a>删除控件

若要删除控件，请执行以下步骤修改电子表格，然后重新导入电子表格：

1. 在 **ControlFamily** 选项卡上，在 controlName 列中查找要 **删除的** 控件。
2. 删除该控件的行。
    - 如果此已删除控件包含任何其他控件未引用的改进操作，则需要从"操作"选项卡中删除 **这些改进** 操作。否则，您将收到验证错误。

3. 保存电子表格。

将电子表格导入回模板时，控件将从模板中删除。

### <a name="modify-template-info-in-compliance-manager"></a>在合规性管理器中修改模板信息

完成并Excel文件后，请按照以下步骤操作。

1. 再次打开评估模板页面并选择你的模板。 在模板的详细信息页上，选择 **"修改模板** "以启动修改向导。
2. 在 **"Upload文件**"屏幕上，选择"浏览"查找并上载Excel文件。
3. 如果文件没有问题，下一个屏幕将显示已上传文件的名称。 如果需要 **更改** (，请选择"下一步"以继续Upload **文件) 。**
    - 如果文件有问题，顶部会显示一条错误消息，说明错误所在。 你将需要修复文件并再次上传它。 如果电子表格的格式不正确，或者某些字段中的信息无效，则会导致错误。

4. " **审阅和完成"** 屏幕显示改进操作和控件的数量以及模板的最大分数。 准备好批准后，选择"下一 **步"。**
5. 最后一个屏幕确认模板已修改。 选择 **"完成** "退出向导。

您的模板现在将包含您所做的更改。 使用此修改后模板的任何评估现在将显示挂起的更新，你将需要接受对评估的更新以反映在模板中所做的更改。 详细了解评估 [更新](compliance-manager-assessments.md#accept-updates-to-assessments)。

> [!NOTE]
> 如果使用英语版本外的其他语言使用合规性管理器，则你会注意到，导出模板进行自定义时，某些文本以英语Excel。 操作标题 (改进操作，如果适用，Microsoft) 必须英语，控件必须识别这些操作。 如果对操作标题进行更改，请确保以英语编写它，以便正确导入文件。

## <a name="export-a-template"></a>导出模板

您可以导出Excel模板数据的所有模板文件。 你需要导出模板才能修改它，因为这将是你在修改过程中编辑Excel上传的模板[文件](#modify-a-template)。 如果要在构造新的自定义模板时使用模板的数据，还可以导出模板作为参考。

若要导出模板，请转到模板详细信息页面并选择"**导出** 到Excel按钮。

请注意，导出从合规性管理器模板扩展的模板时，导出的文件将仅包含您添加到模板的属性。 导出的文件不包括 Microsoft 提供的原始模板数据。 若要获取此类报告，请参阅导出 [评估报告的说明](compliance-manager-assessments.md#export-an-assessment-report)。
