---
title: 了解通过 Microsoft SharePoint Syntex 中的示例模型了解SharePoint Syntex
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
ms.openlocfilehash: 6fffb4bf9ab30059696dc158ac9e6d91690fb83a
ms.sourcegitcommit: b51bfed24a9e3b7adf82d4918b76462cd40dffaf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61153720"
---
# <a name="learn-about-document-understanding-models-through-the-sample-model-in-microsoft-sharepoint-syntex"></a>了解通过 Microsoft SharePoint Syntex 中的示例模型了解SharePoint Syntex

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

可以访问[文档SharePoint Syntex示例](https://github.com/pnp/syntex-samples)存储库，其中包含演示文档理解模型的不同使用模式的社区示例。 此存储库中的示例包含文档了解模型文件和用于训练模型的文件。 导入后，可以使用这些模型处理文件以及查看和编辑分类器与提取器。

## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[文档理解概述](document-understanding-overview.md)

[创建表单处理模型](create-a-form-processing-model.md)  
