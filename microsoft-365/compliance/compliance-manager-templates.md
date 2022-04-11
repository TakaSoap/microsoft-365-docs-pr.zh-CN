---
title: 在 Microsoft 合规性管理器中使用评估模板
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用和管理模板在 Microsoft 合规性管理器中生成评估。 使用格式化Excel文件创建和修改模板。
ms.openlocfilehash: 0dc28eb3058e3b929da47d947b29c7ba7be41111
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64758984"
---
# <a name="learn-about-assessment-templates-in-compliance-manager"></a>了解合规性管理器中的评估模板

**本文：** 了解 **模板的工作原理** 以及如何从评估模板页 **管理它们** 。 获取有关 **创建** 新模板、**扩展** 和 **修改** 现有模板、**使用Excel设置模板数据格式** 以及导出模板 **报表** 的说明。

> [!IMPORTANT]
> 组织可用的评估模板取决于许可协议。 [查看详细信息](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="templates-overview"></a>模板概述

模板是用于在合规性管理器中创建评估的控件框架。 我们全面的模板集可以帮助你的组织遵守管理数据收集和使用的国家、区域和行业特定的要求。

## <a name="template-versions-microsoft-and-universal"></a>模板版本：Microsoft 和通用

我们使用与其基础认证或法规相同的名称来引用模板，例如欧盟 GDPR 模板和 ISO/IEC 27701：2019 模板。

合规性管理器可用于评估不同类型的产品。 除基线之外，所有模板都至少包含一个适用于预定义产品（如Microsoft 365）的版本，以及一个可根据其他产品定制的通用版本。 通用模板的评估更为通用，但提供了扩展的多功能性，因为它们可以帮助你轻松跟踪组织在多个产品中的符合性。

请注意，美国政府Community (GCC) 中度、GCC高和国防部 (DoD) 客户目前无法使用通用模板。

## <a name="template-availability-and-licensing"></a>模板可用性和许可

合规性管理器中有两类模板：包括和高级。

1. **包含的模板** 由合规性管理器许可证授予，并涵盖关键法规和要求。 若要详细了解许可协议下可用的模板，请参阅 [许可详细信息](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。
2. **高级版模板**，以涵盖其他需求和方案，可以通过购买模板许可证来获取。

开始创建评估时，合规性管理器将跟踪活动模板数量，以便监视使用情况。 若要了解详细信息，请参阅 [活动模板和非活动模板](compliance-manager-templates.md#active-and-inactive-templates)。

查看合规性管理器中可用 [的模板的完整列表](compliance-manager-templates-list.md) 。

### <a name="purchase-premium-template-licenses"></a>购买高级模板许可证

模板许可证可由其中一种或多种方法获取，具体取决于合规性管理器许可协议。 完成购买后，模板应在 48 小时内在租户中可用。

**商业和GCC中**

商业和GCC中等帐户可以在管理中心购买模板许可证， ([详细了解订阅、许可证和计费](/microsoft-365/commerce/)) 。 选择要购买的许可证数量和付款计划。

购买链接：

- [商业](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCC中度](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

还可以通过参与[云解决方案提供商计划](https://partner.microsoft.com/membership/cloud-solution-provider)或[批量许可](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)来获取许可证。

**GCC高和 DOD 帐户**

GCC高和 DOD 帐户必须通过[批量许可](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)购买模板许可证。

### <a name="try-out-premium-templates"></a>试用高级模板

若要在购买之前试用高级模板，还可以获取许可证的试用版本。 试用许可证最多适用于 25 个模板，为期 90 天。 获取试用许可证后，模板应在 48 小时内在租户中可用。

如果你的组织具有合规性管理器的商业许可证，你可以了解如何在 [关于 Microsoft 合规性管理器高级评估的免费试用](compliance-easy-trials-compliance-manager-assessments.md)版中开始试用。

如果你的组织处于GCC或 DOD 许可证之下，请为组织选择适当的试用链接：

- [GCC中度](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/87ed2908-0a8d-430a-9635-558ed42b581f)
- [GCC 高级](https://portal.office365.us/SubscriptionDetails?OfferId=e14362d7-2c11-4a43-9c92-59f1b499b96a)
- [国防部](https://portal.apps.mil/Commerce/Trial.aspx?OfferId=17e28290-7de6-41a9-af30-f6497396ab2e)

#### <a name="active-and-inactive-templates"></a>活动模板和非活动模板

模板会将激活状态显示为活动或非活动状态：

- 从该模板创建评估后，模板被视为 **活动** 模板。
- 如果组织未将其用于评估，则模板被视为 **非活动** 。

如果将任何评估链接到购买的高级模板，则该模板将处于活动状态一年。 除非取消，否则购买将自动续订。

#### <a name="activated-templates-counter"></a>已激活的模板计数器

评估页和评估模板页顶部附近有一个 **已激活的模板** 计数器。 该计数器根据许可协议显示你有资格使用的模板数。 模板使用在认证级别进行计数。

例如，如果计数器显示 2/5，则表示组织已激活 5 个可用模板中的 2 个模板。

如果计数器显示 5/2，则表示你的组织超出了其限制，需要购买 3 个正在使用的高级模板。

预定义产品的模板（如Microsoft 365）与同一模板的通用版本具有联合许可。 这样，便可以在多个产品中使用相同的基础认证。 使用同一模板的任一或两个版本将仅算作一个已激活的模板。

有关更多详细信息，请参阅 [合规性管理器许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。

## <a name="view-and-manage-templates"></a>查看和管理模板

合规性管理器中的评估模板页显示模板列表及其关键详细信息。 该列表包括合规性管理器提供的模板以及组织修改或创建的任何模板。 可以应用筛选器来查找基于认证、产品范围、国家/地区、行业、创建模板的人员以及是否为创建评估启用模板的模板。

从其行中选择模板以显示其详细信息页。 此页包含模板的说明以及有关认证、范围和控件详细信息的详细信息。 在此页中，可以选择相应的按钮来创建评估、将模板数据导出到Excel或修改模板。

## <a name="create-an-assessment-template"></a>创建评估模板

若要在合规性管理器中为自定义评估创建自己的新模板，你将使用特殊格式的Excel电子表格来组装必要的控制数据。 完成电子表格后，会将其导入合规性管理器。 若要了解详细信息，请参阅 [“创建评估模板](compliance-manager-templates-create.md)”。

## <a name="modify-an-assessment-template"></a>修改评估模板

在合规性管理器中使用评估时，可能需要修改已创建的评估模板。 此过程类似于模板创建过程，因为将上传包含模板数据的格式化Excel文件。 若要详细了解如何进行更改以及如何保留仍要维护的数据，请参阅 [“修改评估模板](compliance-manager-templates-modify.md)”。

## <a name="extend-an-assessment-template"></a>扩展评估模板

合规性管理器提供了将自己的控件和改进操作添加到现有模板的选项。 此过程称为扩展模板。 若要扩展模板，将使用特殊说明添加到模板数据，具体取决于是扩展 Microsoft 评估模板还是通用评估模板。 若要了解详细信息，请参阅 [“扩展评估模板](compliance-manager-templates-extend.md)”。

## <a name="format-assessment-template-data-in-excel"></a>在Excel中设置评估模板数据的格式

在 Compliance Manager 中创建、修改或扩展评估模板时，你将使用使用特定格式和架构的Excel电子表格。 必须遵循这些规范才能正确导入文件。 若要了解详细信息，请参阅[Excel中的格式评估模板数据](compliance-manager-templates-format-excel.md)。

## <a name="export-a-template"></a>导出模板

可以导出包含模板所有数据的Excel文件。 需要导出模板才能对其进行修改，因为这将是在[修改过程中](compliance-manager-templates-modify.md)编辑和上传的Excel文件。 如果要在构造新的自定义模板时使用该模板中的数据，也可以导出模板供参考。

若要导出模板，请转到模板详细信息页，然后选择“**导出到Excel**”按钮。

请注意，导出从合规性管理器模板扩展的模板时，导出的文件将仅包含添加到模板的属性。 导出的文件不包括 Microsoft 提供的原始模板数据。 若要获取此类报告，请参阅有关 [导出评估报告的](compliance-manager-assessments.md#export-an-assessment-report)说明。