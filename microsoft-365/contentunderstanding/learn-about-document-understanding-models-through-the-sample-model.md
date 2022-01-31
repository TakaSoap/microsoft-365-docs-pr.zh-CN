---
title: 导入 Microsoft 文档理解模型示例SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.custom: intro-get-started
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: 通过示例模型了解文档理解模型。
ms.openlocfilehash: 6e7c680bcb136b52e0b3c9821471d922d43b614b
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281166"
---
# <a name="import-a-sample-document-understanding-model-for-microsoft-sharepoint-syntex"></a>导入 Microsoft 文档理解模型示例SharePoint Syntex

SharePoint Syntex提供了可用于检查的示例模型，从而更好地了解如何创建自己的模型。 示例模型还使你能够检查模型组件，如其分类器、提取程序和说明。 还可以使用示例文件来训练模型。

## <a name="import-the-sample-model"></a>导入示例模型

若要访问示例模型，需要先将模型导入到内容中心。

1. 从内容中心中，选择“**模型**”来查看你的模型列表。</br>
2. 在“**模型**”页面上，选择“**导入示例模型**”。</br>

    ![导入示例模型。](../media/content-understanding/import-sample-model.png) </br>

3. 导入完成后，将打开 **BenefitsChangeNotice** 模型主页。 如果以后需要打开示例模型，可从内容中心的模型列表中打开它。 </br>

     ![示例主页。](../media/content-understanding/sample-home-page.png)</br>

你不仅可以浏览分析示例模型，从而更好地理解模型的构建方式，你还可以随着工作模型的发展，进一步执行以下操作：

- 添加其他提取程序。 例如，添加一个提取 *折扣费用* 的提取程序。
- 将该模型应用于文档库，并上传某些培训文件，以了解该模型如何分类文件并从中提取数据。

## <a name="get-sample-models"></a>获取示例模型

可以访问文档SharePoint Syntex[示例](https://github.com/pnp/syntex-samples)存储库，其中包含演示文档理解模型的不同使用模式的社区示例。 此存储库中的示例包含文档了解模型文件和用于训练模型的文件。 导入后，可以使用这些模型处理文件以及查看和编辑分类器与提取器。

## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[文档理解概述](document-understanding-overview.md)

[创建表单处理模型](create-a-form-processing-model.md)  
