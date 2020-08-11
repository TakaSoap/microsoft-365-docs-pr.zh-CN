---
title: '表单处理概述 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Project Cortex 中的表单处理。
ms.openlocfilehash: dbea06cdf2dbb232a7ea48c78d7ea968dd18b9c0
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612722"
---
# <a name="form-processing-overview-preview"></a>表单处理概述 (预览) 
> [!Note]
> 本文中的内容适用于 Project Cortex 私人预览。 了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。

Project Cortex 使用 Microsoft PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)表单处理在 SharePoint 文档库中创建模型。
您可以使用 AI 生成器表单处理创建 AI 模型，这些模型使用机器学习技术来识别和提取结构化或半结构化文档（如窗体和发票）中的键值对和表数据。

通常情况下，公司会收到大量的发票以及来自各种来源（如邮件、传真、电子邮件或亲自）的发票。 处理这些文档并手动将其输入数据库可能需要花费大量时间。 通过使用 AI 提取文档中的文本、键/值对和表，表单处理将自动执行此过程。 

例如，您可以创建一个表单处理模型，该模型将标识上载到文档库的所有采购订单文档。 从每个采购订单中，您可以提取并显示对您很重要的特定数据，如*PO 号*、*日期*或*总成本*。

您可以使用示例文件来培训模型，并定义要从表单中提取的信息。 您的文档的布局通过培训您的模型来了解。 您只需五个表单文档即可开始。 AI 建筑物将分析有关键值对的示例文件，还可以手动识别可能未检测到的文件。  通过 AI 生成器，您可以在示例文件上测试模型的准确性。

在训练和发布模型之后，使用它创建一个在将文件上传到 SharePoint 文档库时运行的[电源自动化流](https://docs.microsoft.com/power-automate/getting-started)，并提取模型中已标识的数据。 提取的数据将显示在模型的文档库视图中的列中。

Office 365 管理员需要为 SharePoint 文档库[启用表单处理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding)，以便用户能够在其中[创建表单处理模型](create-a-form-processing-model.md)。



## <a name="see-also"></a>另请参阅
  
[电源自动化文档](https://docs.microsoft.com/power-automate/)</br>
[创建表单处理模型](create-a-form-processing-model.md)</br>
[文档理解概述](document-understanding-overview.md)</br>
[培训：使用 AI 生成器改进业务绩效](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




