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
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用和管理模板在 Microsoft 合规性管理器中生成评估。 使用格式化的文件创建和修改Excel模板。
ms.openlocfilehash: dd9f2b2f673164bce7f05f7e390b13012247c362
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335982"
---
# <a name="learn-about-assessment-templates-in-compliance-manager"></a>了解合规性管理器中的评估模板

**本文内容：** 了解 **模板如何工作****以及如何从评估模板** 页管理它们。 获取有关创建新 **模板**、**扩展** 和修改现有模板、使用 Excel 设置模板数据格式以及导出模板报告 **的说明**。

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

商业GCC中等帐户可以在管理中心购买 (许可证，详细了解订阅、许可证和[帐单) 。](/microsoft-365/commerce/) 选择要购买的许可证数量和付款计划。

购买链接：

- [商业](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCC中等](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

您还可以通过参与计划或批量许可[云解决方案提供商获取](https://partner.microsoft.com/membership/cloud-solution-provider)[许可证](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)。

**GCC高帐户和 DOD 帐户**

GCC高和 DOD 帐户必须通过批量许可购买[模板许可证](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)。

### <a name="try-out-premium-templates"></a>试用高级模板

若要在购买前试用高级模板，还可以获取许可证的试用版。 试用许可证适用于最多 25 个模板，最多为 90 天。 获取试用版许可证后，模板应在 48 小时内在租户中可用。

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

## <a name="create-an-assessment-template"></a>创建评估模板

若要在合规性管理器中为自定义评估创建自己的新模板，你需要使用经过特殊格式Excel电子表格来组合必要的控制数据。 完成电子表格后，将其导入合规性管理器。 若要了解更多信息，请参阅 [创建评估模板](compliance-manager-templates-create.md)。

## <a name="modify-an-assessment-template"></a>修改评估模板

在合规性管理器中处理评估时，可能需要修改已创建的评估模板。 此过程类似于模板创建过程，你将上载包含模板数据的格式化Excel文件。 若要详细了解如何进行更改以及如何保留仍要维护的数据，请参阅修改 [评估模板](compliance-manager-templates-modify.md)。

## <a name="extend-an-assessment-template"></a>扩展评估模板

合规性管理器提供向现有模板添加自己的控件和改进操作的选项。 此过程称为扩展模板。 若要扩展模板，你将使用特殊说明添加到模板数据，具体取决于你是在扩展Microsoft 365模板还是通用评估模板。 若要了解更多信息，请参阅 [扩展评估模板](compliance-manager-templates-extend.md)。

## <a name="format-assessment-template-data-in-excel"></a>格式化评估模板数据Excel

在合规性管理器中创建、修改或扩展评估模板时，将使用Excel格式和架构的电子表格。 若要正确导入文件，必须遵循这些规范。 若要了解更多信息，请参阅 Format [assessment template data in Excel](compliance-manager-templates-format-excel.md)。

## <a name="export-a-template"></a>导出模板

您可以导出Excel模板数据的所有模板文件。 你需要导出模板才能修改它，因为这将是你在修改过程中编辑Excel上传的模板[文件](compliance-manager-templates-modify.md)。 如果要在构造新的自定义模板时使用模板的数据，还可以导出模板作为参考。

若要导出模板，请转到模板详细信息页面，然后选择"**导出到** Excel按钮。

请注意，导出从合规性管理器模板扩展的模板时，导出的文件将仅包含您添加到模板的属性。 导出的文件不包括 Microsoft 提供的原始模板数据。 若要获取此类报告，请参阅导出 [评估报告的说明](compliance-manager-assessments.md#export-an-assessment-report)。