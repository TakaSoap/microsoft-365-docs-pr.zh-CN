---
title: 大Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 在管理中Advanced eDiscovery大的情况，以便可以添加更多项目来审阅集，并充分利用其他增加的限制。
ms.openlocfilehash: d4737b6c715ac96fc9e16c40e2f4fa784a66e5d1
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "53542414"
---
# <a name="use-large-cases-in-advanced-ediscovery-preview"></a>在预览版Advanced eDiscovery (大) 

越来越多的组织将 Advanced eDiscovery 解决方案用于Microsoft 365电子数据展示流程。 这包括响应法规请求、调查和诉讼。 随着Advanced eDiscovery增加，常见的客户要求是增加可在单个网站集中管理的内容Advanced eDiscovery量。 为了帮助适应数据总量和总项目数的大小写大小显著增加的情况，现在可以在创建大案例时选择大Advanced eDiscovery格式。  

## <a name="create-a-large-case"></a>创建大案例

若要创建大案例：

1. 转到 <https://compliance.microsoft.com> 并登录。

2. 在导航窗格的左侧导航窗格中，Microsoft 365 合规中心"**电子数据展示>高级"。**

3. 在 **"Advanced eDiscovery"** 页上，单击"事例 **"** 选项卡，然后单击"**创建事例"。**

   将显示 **"新建电子数据展示案例** "飞出页。 " **大小写格式** "部分提供用于创建大案例的选项。 如果需要在短时间内收集大量内容，请选择此案例类型。

   !["新建电子数据展示案例"页面上的"大案例"选项](..\media\AeDLargeCases1.png)

4. 命名案例后，选择"大案例" **选项** ，然后单击 **"保存"** 创建大案例。

## <a name="benefits-of-large-cases"></a>大案例的好处

新的大案例格式允许你管理包含 4000 万多个项目的情况。 此功能可帮助您通过整个电子数据展示工作流有效地管理大量案例数据。

下面是在工作流中大案例的其他Advanced eDiscovery列表。

- **集合**：在大型情况下，一个集合最多可以收集 1 TB 的数据。 

   对于每个大的情况，集合设置将默认收集云附件和上下文Teams和Yammer内容。 这些设置有助于在调查中收集数字通信的完整图片。 对于 Teams 和 Yammer 上下文对话，大写格式会将基于时间 1：1、1：N 和 Channel 对话的快照转换为 html 脚本，以帮助提供对话上下文并减少基于聊天的内容产生的项目总数。  

- **审阅**：每个审阅集最多支持 1 TB 的预扩展内容。 其他元数据可用于筛选器和查询，包括团队名称、频道名称和内容Teams名称。 每个脚本将包括响应项目之前和之后基于时间的内容。 对于频道对话，将为响应式内容收集根帖子及所有回复。  

- **导出**：可以在单个导出作业中导出大型内容集。 大案例格式允许您导出 500 万个文档或 500 GB，以导出作业中较小的为准。

此外，新的大案例格式还包括一个更新的用户界面，该用户界面显示本例中每个审阅集的总大小。 Review set sizes are displayed in a column on the **Review sets** tab and in a flyout pane that persists of every tab in the case.

![用户界面中的大Advanced eDiscovery统计信息](..\media\LargeCaseUI.png)

## <a name="frequently-asked-questions"></a>常见问题解答

**如果我尝试在单个集合中收集超过 1 TB，它是否正常工作？**

性能将受到负面影响，在某些情况下可能会导致不稳定。

**如果默认情况下以大案例格式包含云附件;如何从评价体验中删除该内容？**  

使用审阅集筛选器按邮件类型进行筛选或使用 HasAttachment 筛选器排除云附件。 有关详细信息，请参阅查询 [和筛选审阅集的内容](review-set-search.md)。

**导出聊天对话脚本时，加载文件是否包含所有扩展的元数据和每个脚本的单个项目？**

对话的所有元数据都嵌入 HTML 脚本文件中。  许多常见字段在加载文件中可用。 有关导出元数据的信息，请参阅文档[元数据字段Advanced eDiscovery。](document-metadata-fields-in-Advanced-eDiscovery.md)
