---
title: 管理高级 eDiscovery 中的作业
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
description: 高级 eDiscovery 作业帮助跟踪与执行各种高级 eDiscovery 任务相关的长期运行进程状态。
ms.openlocfilehash: 6f246202ac371500b7fe16204b34bc00ba8ee9a7
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61871461"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>管理高级 eDiscovery 中的作业

以下是高级 eDiscovery 中某个案例的 **作业** 选项卡上跟踪的作业（通常是长期运行进程）列表。 使用和管理案例的用户操作会触发这些作业。

| 作业类型            | 说明     |
| :----------------- | :----------     |
|正在添加数据到审阅集。 | 用户向审阅集添加集合。 此作业包括 2 个子作业： </br>• **Export** - 生成集合中的项列表。 </br>• **Ingestion & Indexing** - 在名为) 的进程中，与搜索查询匹配的集合中的项复制到 Azure 存储 位置 *(，* 然后对 Azure 存储 位置中的那些项重新编制索引。 新索引将用于在数据集中查询和分析项目。 </br></br>有关详细信息，请参阅 [添加搜索结果到审阅集](add-data-to-review-set.md)。 |
|正在将数据添加到另一审阅集 | 用户将一个审阅集中的文档添加到同一案例中的另一个不同的审阅集。 有关详细信息，请参阅 [将其它审阅集中数据添加到审阅集](add-data-to-review-set-from-another-review-set.md)。|
|正在将非 Microsoft 365 数据添加到审阅集。 | 用户将非 Microsoft 365 数据上传到审阅集。 在此进程中还会编制数据的索引。 例如，将本地文件服务器或客户端计算机的文件上传到审阅集。 有关详细信息，请参阅 [加载非 Microsoft 365 数据到审阅集](load-non-office-365-data-into-a-review-set.md)。| 
|正在将已修正数据添加到审阅集 | 已修正出现处理错误的数据，并且已将其加载回审阅集。 有关详细信息，请参阅：</br>• [处理数据时修正错误](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [单个项目错误修正](single-item-error-remediation.md)| 
|正在比较加载集 | 用户观察审阅集中不同加载集的差别。 加载集是像审阅集添加数据的一个实例。 例如，如果将 2 次不同搜索的结果添加到同一审阅集，每一个都代表一个加载集。 |
|对话重建|用户将搜索结果添加到对话审阅集时，服务（如 Microsoft Teams）中的即时消息对话（也称为 *线程对话*）将重建为 PDF 文件。 如果用户在审阅集中单击 **“操作”>“创建对话 PDF”** 也可触发此作业。 有关详细信息，请参阅 [审阅高级 eDiscovery 中的对话](conversation-review-sets.md)。
|正在将编修文档转换为 PDF|用户为审阅集中的文档添加批注并编修部分内容后，可选择将已编修文档转换为 PDF 文件。 此操作可确保如果导出文档进行演示，已编修部分将不可见。 有关详细信息，请参阅 [查看审阅集中的文档](annotating-and-redacting-documents.md)。 |
|预估搜索结果 | 用户创建并运行或重新运行草稿集合后，搜索工具会搜索索引中与搜索查询匹配的项目，并准备一个估计值，其中包括搜索时所有项目的数量和总大小以及搜索的数据源的数量。  有关详细信息，请参阅 [收集案例数据](collecting-data-for-ediscovery.md)。 | 
|准备导出数据 | 用户从审阅集导出文档。 导出过程完成时，可将导出数据下载到本地计算机。 有关详细信息，请参阅 [导出案例数据](exporting-data-ediscover20.md)。 | 
|准备错误解决方案 |用户在案例的 **正在处理** 选项卡上“错误”视图中选择文件并创建新的错误修正方法时，此过程第一步需要将含有处理错误的文件上传到 Microsoft 云中的 Azure Storage 位置。 此作业跟踪上传进程的进度。 有关错误修正流程的详细信息，请参阅 [处理数据时错误修正](error-remediation-when-processing-data-in-advanced-ediscovery.md)。 | 
|准备搜索预览 | 在用户创建并运行新的草稿集合 (或重新运行现有草稿集合) 后，搜索工具将准备与可预览的搜索查询) 匹配的项目 (的示例子集。 预览搜索结果有助于确定搜索是否有效。  有关详细信息，请参阅 [收集案例数据](collecting-data-for-ediscovery.md#view-search-results-and-statistics)。 | 
|重新编制保管人数据索引 | 向案例添加保管人时，保管人选择数据源中的所有部分索引项都将由名为 *高级索引* 的进程重新编制索引。 在案例的 **正在处理** 选项卡上单击 **更新索引**，以及在保管人属性浮出控件页面上更新特定保管人索引时，也会触发此作业。 有关详细信息，请参阅 [保管人数据高级索引](indexing-custodian-data.md).
|运行分析 | 用户通过运行高级 eDiscovery 分析工具（如近似重复检测、电子邮件线程分析和主题分析）分析审阅集中的数据。 有关详细信息，请参阅 [分析审阅集数据](analyzing-data-in-review-set.md)。 | 
|标记文档 | 对审阅集中的文档进行审阅时，如果用户单击 **标记面板** 中的 **开始标记作业**，就会触发此作业。 标记审阅集中的文档，并随后在查看文档面板中批量选择这些文档后，用户可以开始此作业。 有关详细信息，请参阅 [标记审阅集中的文档](tagging-documents.md)。 | 
|||

## <a name="job-status"></a>作业状态

下表介绍了作业的不同状态。

| 状态           | 说明     |
| :----------------- | :----------     |
| 已提交 | 已创建新作业。  **作业** 选项卡上的 **已创建** 列将显示作业提交的日期和时间。 |
| 提交失败。 | 作业提交失败。  应当尝试重新运行触发此作业的操作。 |
| 正在进行 | 作业正在进行，可在 **作业** 选项卡中监控作业的进度。 |
| 成功 | 作业已成功完成。 **作业** 选项卡上的 **已完成** 列将显示作业完成的日期和时间。 |
| 部分成功 | 作业成功。 如果作业在某些保管人数据源中未找到任何部分索引数据（也称为 *未索引数据*），一般将返回此状态。  |
| 已失败 | 作业失败。  应当尝试重新运行触发此作业的操作。 如果作业再次失败，建议联系 Microsoft 支持部门，并提供作业的支持信息。 |
|||
