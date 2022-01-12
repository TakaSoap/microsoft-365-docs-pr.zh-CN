---
title: 在服务中设置律师-客户Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在审查案例内容时，使用律师-客户特权检测模型使用基于机器学习的特权Advanced eDiscovery检测。
ms.openlocfilehash: 5e8a9e1ef0cf8cd8375cd6ce9a0b4d210840e838
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61933655"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>在服务中设置律师-客户Advanced eDiscovery

任何电子数据展示过程的审阅阶段的主要且成本高昂的方面是查看文档的特权内容。 Advanced eDiscovery提供基于机器学习的特权内容的检测，提高此过程的效率。 此功能称为 *律师-客户特权检测*。

## <a name="how-does-it-work"></a>它的工作原理是什么？

启用律师-客户特权检测后，当您分析审阅集内的数据时，律师-客户特权检测模型将处理审阅集内的所有[](analyzing-data-in-review-set.md)文档。 模型查找两项内容：

- 特权内容 – 模型使用机器学习来确定文档包含本质上合法内容的可能性。

- 参与者 – 作为设置律师-客户特权检测的一部分，您必须为组织提交律师列表。 模型随后将文档参与者与代理列表进行比较，以确定文档是否具有至少一个代理参与者。

模型将生成每个文档的以下三个属性：

- **AttorneyClientPrivilegeScore：** 文档在本质上是合法的可能性;分数的值介于 **0** 和 **1 之间**。

- **HasAttorney：** 如果律师列表中列出了其中一个文档参与者，则此属性设置为 **true;** 否则值为 **false**。 如果你的组织未上传代理列表，则此值设置为 **false**。

- **IsPrivilege：** 如果 **"AttorneyClientPrivilegeScore"** 的值超过阈值或文档具有律师参与者，则此属性设置为 **true;** 否则，该值设置为 **false**。

这些属性 (其相应的值) 添加到审阅集内文档的文件元数据中，如以下屏幕截图所示：

![文件元数据中显示的律师-客户特权属性。](../media/AeDAttorneyClientPrivilegeMetadata.png)

这三个属性也可在审阅集内搜索。 有关详细信息，请参阅查询 [审阅集内的数据](review-set-search.md)。

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>设置律师-客户特权检测模型

若要启用律师-客户特权检测模型，你的组织必须将其打开，然后上载律师列表。

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>步骤 1：启用律师-客户特权检测

作为您组织中电子数据展示管理员 (电子数据展示管理员角色组) 中的电子数据展示管理员子组的成员必须在 Advanced eDiscovery 事例中提供该模型。

1. In the Microsoft 365 合规中心， go to [Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764)， and then click **Advanced eDiscovery settings**.

   ![选择Advanced eDiscovery设置](..\media\HistoricalVersions1.png)

2. 在 **"设置"** 页上，选择"**分析**"选项卡，然后将"**律师-客户特权检测"** 开关切换为"打开"。

   ![单击切换以打开律师-客户特权检测](..\media\TurnOnAttorneyClientPrivilegeDetection.png)

3. 单击“保存”以保存所做的更改。

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>步骤 2：Upload可选律师 (列表) 

若要充分利用律师-客户特权检测模型，并使用之前所述的"律师或潜在特权"检测的结果，我们建议您为在组织工作的律师和律师上载电子邮件地址列表。

要上载律师-客户特权检测模型使用律师列表，请执行以下操作：

1. 创建 .csv 文件（不带标题行），在单独的行上为每个合适的人员添加电子邮件地址。将此文件保存到本地计算机。

2. 在 **"Advanced eDiscovery设置"** 页上，选择 **"分析"** 选项卡。

   将显示 **"律师-客户特权** "页，并且" **律师-客户特权检测** "切换处于打开状态。

   ![律师-客户特权飞出页](..\media\AeDUploadAttorneyList1.png)

3. 选择 **"选择** 文件"，然后查找并选择.csv 1 中创建的配置文件。

4. 选择 **"保存** "上载律师列表。

## <a name="use-the-attorney-client-privilege-detection-model"></a>使用律师-客户特权检测模型

按照本节中的步骤对审阅集内的文档使用律师-客户特权检测。

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>步骤 1：使用律师-客户特权检测模型创建智能标记组

在审核过程中查看律师-客户特权检测结果的主要方法之一是使用智能标记组。 智能标记组指示律师-客户特权检测的结果，并在智能标记组中的标记旁边在线显示结果。 这样，您可以在文档审阅期间快速识别潜在的特权文档。 此外，您还可以使用智能标记组的标记来标记具有特权或非特权的文档。 有关智能标记详细信息，请参阅在智能标记[Advanced eDiscovery。](smart-tags.md)

1. 在包含步骤 1 中分析的文档的审阅集内，选择"管理 **审阅** 集"，然后选择"**管理标记"。**

2. 在 **"标记**"下，选择"添加组"旁边的下拉 **组件**，然后选择"**添加智能标记组"。**

   ![选择"添加智能标记组"。](../media/AeDCreateSmartTag.png)

3. 在"**为智能标记选择模型"页上**，选择"**律师****-客户特权"旁边的"选择"。**

   将显示名为 **"律师-客户特权"的** 标记组。 它包含名为 **Positive** 和 **Negative** 的两个子标记，它们对应于模型生成的可能结果。

   ![律师-客户特权智能标记组。](../media/AeDAttorneyClientSmartTagGroup.png)

3. 根据审阅情况重命名标记组和标记。 例如，可以将"正"**重命名** 为 **"特权**"，将 **"负**"重命名为"**非特权"。**

### <a name="step-2-analyze-a-review-set"></a>步骤 2：分析审阅集

在分析审阅集内的文档时，律师-客户特权检测模型也将运行，并且还会将 (如何工作 [？](#how-does-it-work) 中介绍的相应属性) 将添加到审阅集内的所有文档。 有关分析审阅集内的数据详细信息，请参阅分析审阅集内[Advanced eDiscovery。](analyzing-data-in-review-set.md)

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>步骤 3：使用智能标记组查看特权内容

分析审阅集并设置智能标记后，下一步是查看文档。 如果模型已确定文档可能具有特权，则标记面板中的相应智能标记将指示律师-客户特权检测生成的以下结果：

- 如果文档的内容在本质上可能是合法内容，则标签"法律内容"显示在相应的智能标记 (在这种情况下，该智能标记是默认的 **"正值**") 。

- 如果文档中有一个在组织律师列表中找到的参与者，则标签"律师"显示在相应的智能标记旁边 (该智能标记在此例中也是默认的 **"** 正") 。

- 如果文档的内容在本质上可能是合法的，并且律师列表中有参与者，则同时显示法律内容和律师标签。   

如果模型确定文档不包含本质上是合法的内容或不包含律师列表中的参与者，则标记面板中不会显示任何标签。

例如，以下屏幕截图显示了两个文档。 第一个包含本质上是合法的内容，并且有一个参与者在律师列表中找到。 第二个不包含任何标签，因此不显示任何标签。

![包含律师和法律内容标签的文档。](../media/AeDTaggingPanelLegalContentAttorney.png)

![不带任何标签的文档。](../media/AeDTaggingPanelNegative.png)

在查看文档以查看文档是否包含特权内容后，可以使用相应的标记标记该文档。
