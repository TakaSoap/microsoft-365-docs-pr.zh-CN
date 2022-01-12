---
title: 在 Advanced eDiscovery 中设置历史版本
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
description: 使用文档中的历史Advanced eDiscovery从存储在 SharePoint 和 OneDrive 的所有版本的文档中收集内容。
ms.openlocfilehash: 5ecbb9c9216482223ce756aed5742e25a3b851a1
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61936650"
---
# <a name="set-up-historical-versions-in-advanced-ediscovery-preview"></a>在预览版中Advanced eDiscovery (历史) 

通过 Advanced eDiscovery 中的历史版本功能，您组织中的电子数据展示管理员可以搜索并收集存储在 SharePoint Online 和 OneDrive for Business 中所有版本OneDrive for Business。 然后，您可以将该内容添加到审阅集进行分析和审阅。 这可以帮助您从文档的特定版本查找和查看与案例或调查相关的内容，即使同一文档的最新版本不包含相关信息。

若要在组织中支持历史版本Advanced eDiscovery，SharePoint必须启用其组织中网站的版本控制。 然后，当用户修改 SharePoint 或 OneDrive 中的文档时，在将文档保存或自动保存 (创建隐式常规) 。 SharePoint版本控制允许跟踪对项目上SharePoint的活动 (包括文档、事件和任务) 。 此版本控制功能留下可在法律调查中提供证据的审核线索。 组织可以使用这些较旧版本的文档，组织可能需要在法律事务中发现期间共享包含敏感或相关内容的此类版本。

电子数据展示管理员打开组织的历史版本，然后为特定 SharePoint 网站激活它后，SharePoint 内容推送服务将爬网激活网站上文档的所有主要版本和次要版本，然后发送这些版本进行索引。 完成爬网和索引过程后，文档及其版本可用于电子数据展示搜索。 只要特定版本可以按版本历史记录 (，) ，该版本就可以在 Advanced eDiscovery 搜索中发现。

## <a name="set-up-historical-versions"></a>设置历史版本

若要在 Advanced eDiscovery 中启用历史版本，组织必须将其打开，然后激活特定网站，以便为存储在这些网站上的所有文档版本编制索引以便进行搜索。 在设置Advanced eDiscovery版本版本之前，必须启用版本控制SharePoint。

### <a name="step-1-turn-on-versioning-in-sharepoint"></a>步骤 1：在 SharePoint

第一步是在 SharePoint Online 中启用版本控制，以便保留文档的所有版本。 有关说明，请参阅 SharePoint 中的[版本控制](/microsoft-365/community/versioning-basics-best-practices)。

### <a name="step-2-turn-on-historical-versions"></a>步骤 2：打开历史版本

下一步是在 Advanced eDiscovery 中启用历史版本。 若要为组织启用历史版本，人员必须是全局管理员或电子数据展示管理员 (电子数据展示管理员组) 中的电子数据展示管理员子组的成员。 启用历史版本后，它将应用于整个组织。

> [!IMPORTANT]
> 打开历史版本后，将无法在公共预览期间关闭它。 在正式发布历史版本后，你将能够关闭它。

1. In the Microsoft 365 合规中心， go to [Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764)， and then click **Advanced eDiscovery settings**.

   ![选择Advanced eDiscovery设置](..\media\HistoricalVersions1.png)

2. 在 **"设置"** 页上，选择"历史版本" (**预览**) "选项卡，然后将"历史 **版本**"租户控件切换开关切换为"打开"。

   ![打开切换以启用历史版本](..\media\HistoricalVersions2.png)

   将显示一条警告，提示你无法关闭历史版本。 如前所述，在公开发布此功能之前，你将无法关闭历史版本。

3. 单击 **"** 是"打开历史版本。

### <a name="step-3-activate-sharepoint-sites"></a>步骤 3：激活SharePoint网站

为组织启用历史版本后，最后一步是激活SharePoint网站以支持历史版本。 当您通过将网站 (添加到"历史版本"选项卡) 上的网站列表中来激活网站集时，将重新对网站进行重新绘制，并且会为存储在该网站上的所有文档版本编制索引以用于搜索。

> [!NOTE]
> 在历史版本的公共预览期间，每个组织限制为 100 个网站激活。 每次为历史版本启用或禁用网站时，激活都会计入此限制。 如果启用多个网站，则每个网站都计为一次激活。 激活总数显示在"历史版本 **"** 选项卡上。

1. 在"**历史记录版本**"选项卡上的"Advanced eDiscovery设置"页上，单击"启用"以激活历史版本的网站。

   ![单击"启用"以激活历史版本的网站](..\media\HistoricalVersions3.png)  

   将显示一个飞出页面，其中包含组织中SharePoint网站的列表。

2. 选择要激活的网站，然后单击" **启用** "以针对历史版本激活它。 您可以使用搜索框搜索特定网站。

   将显示一条警告，指出将索引网站上的文档版本，并且此索引过程需要一段时间才能准备好搜索这些版本。 该警告还表明，在 30 天内，你将无法禁用所选网站的历史版本。

3. 单击 **"** 是"以激活历史版本的网站。

   ![将显示激活的网站和网站激活数](..\media\HistoricalVersions4.png)  

   该网站将添加到已激活网站列表中。 显示网站激活数的计数器也会更新。

4. 对要针对历史版本激活的每个网站重复上述步骤。

## <a name="frequently-asked-questions"></a>常见问题解答

**历史版本与将草稿集合提交到审阅集时"收集所有版本"选项之间如何不同？**

目前，仅对最新版本的文档编制索引以用于搜索。 这意味着在运行草稿集合时，只会搜索最新版本的文档。 如果文档与集合的关键字查询匹配，则它将在集合结果中返回。 但是，如果文档的最新版本与搜索查询不匹配，则如果较旧版本的文档包含关键字，则不返回文档事件。 为了帮助缓解这种情况，Advanced eDiscovery将集合提交到审阅集时，可以收集文档[的所有版本](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)。 这意味着任何可能包含关键字的旧版本都将添加到审阅集。

历史版本不同于"收集所有版本"，因为当您激活网站时，文档的所有版本 (并不只是对上一版本) 编制索引以用于搜索。 结果是，如果较旧版本的文档包含与搜索查询匹配的关键字，则集合将返回该关键字。

**当为网站启用历史版本时，是否会影响网站的性能？**

否。 为网站启用历史版本后，网站的性能将和启用网站之前的性能相同。 启用网站后对网站执行的爬网和索引编制过程的速度将较慢，并且将在非高峰时段执行。 为网站启用历史版本将启动回填过程，此过程将查找网站上的所有文档版本，然后将这些版本发送到索引。 此回填过程可能会影响服务运行状况，具体取决于网站的文档版本数。 我们通过以下方式缓解了这种潜在影响：

- 我们会尽力在非高峰时段处理这些版本。

- 我们处理最低优先级队列中的文档版本，这允许将大多数服务资源委派给用户更改。

**激活网站后必须等待多久，直到该网站上的所有文档历史版本都编制索引并可用于电子数据展示搜索？**

根据网站的文档数和每个文档的平均版本数，我们尝试估计每个网站的总文件数。 基于此，估计编制索引可能需要多久，如下所示：

`Number of versions / (Processing rate of 100,000 files per day ) + .5 days = Total number of days to process a site`

由于对网站上版本的索引进行了优化，以在非高峰时段运行，因此将添加半天作为缓冲区。

例如，如果文档总数和网站的所有版本为 150，000，则处理网站的历史版本至少需要两天：

`150,000 files/100,000 files per day + .5 days = 2 days`

**为什么不建议为历史版本频繁激活或停用网站？**

停用之前激活的网站时，将触发清理过程。 此过程需要一些时间才能完成。 如果再次激活同一网站，则重新索引网站的回填过程必须重新运行。 清理和回填过程会消耗大量时间和资源。 因此，我们建议您仔细考虑并规划要针对历史版本激活哪些网站，以避免重复激活和停用网站的历史版本。
