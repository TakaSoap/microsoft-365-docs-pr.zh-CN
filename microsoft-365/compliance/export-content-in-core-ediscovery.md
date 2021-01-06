---
title: 从核心电子数据展示案例中导出和下载内容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍如何从核心电子数据展示案例导出和下载内容。
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760296"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>从核心电子数据展示案例中导出内容

成功运行搜索后，可以导出搜索结果。 导出搜索结果时，邮箱项目将下载到 PST 文件或单个邮件中。 从 SharePoint 和 OneDrive for Business 网站导出内容时，将导出本机 Office 文档和其他文档的副本。 一Results.csv导出的每个项目的信息的一个文档文件，以及一个包含每个搜索结果信息的 (清单文件) 包含每个搜索结果的信息。
  
可以导出与案例关联的 [单个](#export-the-results-of-a-single-search) 搜索的结果，也可以导出与案例关联的多个 [搜索的结果](#export-the-results-of-multiple-searches)。
  
## <a name="export-the-results-of-a-single-search"></a>导出单个搜索的结果

1. Go [https://compliance.microsoft.com](https://compliance.microsoft.com) to and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**核心。**

3. 在 **"核心电子数据** 展示"页上，选择要导出搜索结果的大小写，然后单击"**打开案例"。**

4. 在 **案例** 的主页上，单击"搜索 **"** 选项卡。

5. 在案例的搜索列表中，单击要导出搜索结果的搜索，然后在飞出上单击 **"导出结果** "。

    将显示 **"导出结果** "页。 

    ![导出结果页](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    导出与核心电子数据展示案例关联的搜索结果的工作流与导出内容搜索页面上搜索的 **搜索结果相同** 。 有关分步说明，请参阅"[导出内容搜索结果"。](export-search-results.md)

    > [!NOTE]
    > 导出搜索结果时，可以选择启用重复数据删除，以便只导出电子邮件的一个副本，即使搜索到的邮箱中可能找到了同一邮件的多个实例。 有关重复数据删除以及如何标识重复项的信息，请参阅电子数据展示搜索结果中的重复 [数据删除](de-duplication-in-ediscovery-search-results.md)。

    开始导出后，搜索结果准备下载，这意味着它们上传到 Microsoft 提供的 Microsoft 云中的 Azure 存储位置。
  
6. 单击 **"导出** "选项卡以显示案例的导出作业列表。
  
    您可能必须单击 **"刷新"** 来更新导出作业的列表，以便它显示您创建的导出作业。 导出作业与相应的搜索具有相同的名称，_Export附加到搜索名称。

7. 单击创建的导出作业，在飞出页上显示状态信息。 此信息包括已转移到 Azure 存储位置的项目百分比。

8. 在转移所有项目后，单击"下载 **结果** "将搜索结果下载到本地计算机。 有关下载搜索结果的信息，请参阅"导出内容搜索结果的步骤 [2"](export-search-results.md#step-2-download-the-search-results)

## <a name="export-the-results-of-multiple-searches"></a>导出多个搜索的结果

作为导出与案例关联的单个搜索的结果的替代方法，您可以在单个导出作业中从同一案例导出多个搜索的结果。 导出多个搜索的结果比一次导出一个搜索的结果更快、更容易。
  
> [!NOTE]
> 如果其中一个搜索已配置为保留搜索位置，你无法导出多个搜索的结果。

1. Go [https://compliance.microsoft.com](https://compliance.microsoft.com) to and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**核心。**

3. 在 **"核心电子数据** 展示"页上，选择要导出搜索结果的大小写，然后单击"**打开案例"。**

4. 在 **案例** 的主页上，单击"搜索 **"** 选项卡。
    
5. 在案例的搜索列表中，选中要导出搜索结果的两个或多个搜索旁边的复选框。 

   将显示 **"批量操作** "飞出页。 

    ![在"批量操作"页上，单击"导出结果"](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. 单击 **"导出结果"。**

   将显示 **"导出结果** "页。 

    ![导出结果页](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    此时，导出与核心电子数据展示案例关联的多个搜索的结果的工作流与导出单个搜索的搜索结果相同。 请参阅上一节中的步骤 5。

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>有关导出多个搜索的结果详细信息

- 导出多个搜索的结果时，使用 **OR** 运算符组合来自所有搜索的搜索查询，然后启动组合搜索。 组合搜索的估计结果显示在所选导出作业的飞出页中。 搜索结果随后会复制到 Microsoft 云中的 Azure 存储位置。 复制作业的状态也显示在飞出页上。 如前所述，复制所有搜索结果后，您可以将它们下载到本地计算机。

- 对于要导出的所有搜索，查询中的最大关键字数为 500。 这是单个搜索的相同限制。 这是因为导出作业使用 **OR** 运算符将所有搜索查询组合在一起。 如果超过此限制，将返回错误。 在这种情况下，您必须从较少的搜索中导出结果，或简化要导出的原始搜索的搜索查询。

- 导出的搜索结果按找到项目的内容位置进行组织。 这意味着导出结果中的内容位置可能包含由不同搜索返回的项目。 例如，如果您选择在每个邮箱的一个 PST 文件中导出电子邮件，则 PST 文件可能包含来自多个搜索的结果。

- 如果同一内容位置中的同一电子邮件项目或文档由您导出的多个搜索返回，则只导出该项目的一个副本。

- 创建多个搜索后，无法编辑导出。 例如，无法从导出作业中添加或删除搜索。 您必须创建导出作业以更改导出的搜索结果。 创建导出作业后，只能将结果下载到计算机、重新启动导出或删除导出作业。

- 如果重新启动导出，则对包括导出作业的搜索查询的任何更改都不会影响检索到的搜索结果。 重新启动导出时，将再次运行创建导出作业时运行的同一个组合搜索查询作业。

- 此外，如果重新启动导出，复制到 Azure 存储位置的搜索结果将覆盖以前的结果。 无法下载之前复制的结果。
