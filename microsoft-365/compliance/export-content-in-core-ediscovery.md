---
title: 从核心电子数据展示案例导出和下载内容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 介绍如何从 Microsoft 365 中的核心电子数据展示案例导出和下载Microsoft 365。
ms.openlocfilehash: 5e7d17c7ddb9060417812cccd45437c30b70e9f3
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60647362"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>从核心电子数据展示事例导出内容

成功运行与核心电子数据展示案例关联的搜索后，可以导出搜索结果。 导出搜索结果时，邮箱项目以 PST 文件或单个邮件方式下载。 当您从网站和SharePoint OneDrive for Business内容时，将导出本机文档Office文档和其他文档的副本。 一Results.csv导出的每个项目的信息的清单文件，以及包含有关每个搜索结果的信息 (XML 格式) 清单文件也导出。
  
## <a name="export-search-results"></a>导出搜索结果

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后使用已分配有相应电子数据展示权限的用户帐户的凭据登录。

2. 在左侧导航窗格中，单击 **Microsoft 365 合规中心全部显示**"，然后单击"电子数据展示>**核心"。**

3. 在 **"核心电子数据展示"** 页上，单击要创建保留的案例的名称。

4. 在案例 **的主页** 上，单击"搜索 **"** 选项卡。

5. 在弹出 **页** 底部的"操作"菜单上，单击"**导出结果"。**

   !["操作"菜单中的"导出结果"选项。](../media/ActionMenuExportResults.png)

   导出与核心电子数据展示案例关联的搜索结果的工作流与导出内容搜索页面上搜索的 **搜索结果相同** 。 有关分步说明，请参阅导出 [内容搜索结果](export-search-results.md)。

   > [!NOTE]
   > 导出搜索结果时，可以选择启用重复数据删除，以便只导出电子邮件的一个副本，即使搜索到的邮箱中可能找到同一邮件的多个实例。 有关重复数据删除以及如何标识重复项的信息，请参阅电子数据展示搜索结果中 [的重复数据删除](de-duplication-in-ediscovery-search-results.md)。

   开始导出后，搜索结果将准备下载，这意味着它们将被转移到 Microsoft 云Azure 存储 Microsoft 提供的位置。
  
6. 如果 **为导出** ，请单击"导出"选项卡以显示导出作业的列表。
  
   ![在核心电子数据展示案例的"导出"选项卡上导出作业。](../media/CoreeDiscoveryExport.png)

   您可能必须 **单击"刷新** "来更新导出作业的列表，以便它显示您创建的导出作业。 导出作业与相应的搜索具有相同的名称，_Export附加到搜索名称。

7. 单击创建的导出作业，在飞出页上显示状态信息。 此信息包括已转移到其他位置Azure 存储百分比。

8. 在转移所有项目后，单击 **"下载结果** "以将搜索结果下载到本地计算机。 有关下载搜索结果的信息，请参阅导出内容搜索结果中的步骤 2 [](export-search-results.md#step-2-download-the-search-results)

> [!NOTE]
> 导出的搜索结果必须在创建导出作业后的 14 天内下载。

### <a name="more-information-about-exporting-searches-from-a-case"></a>有关从案例导出搜索详细信息

- 有关导出搜索结果时包含的导出文件详细信息，请参阅导出 [内容搜索报告](export-a-content-search-report.md#whats-included-in-the-report)。

- 如果重新启动导出，则任何对搜索查询的更改（这些搜索是导出作业的一部分）不会影响检索到的搜索结果。 重新启动导出时，将再次运行创建导出作业时运行的相同组合搜索查询作业。

- 此外，如果重新启动导出，复制到导出位置的搜索结果Azure 存储之前的结果。 无法下载以前复制的结果。
