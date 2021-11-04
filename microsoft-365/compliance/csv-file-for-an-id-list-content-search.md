---
title: 准备用于 ID 列表内容搜索的 CSV 文件
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: 使用现有内容搜索中的 CSV 文件创建返回特定电子邮件项目的 ID 列表搜索。
ms.openlocfilehash: 6e06a5ba45b7c9b90875ed099e11263c28146998
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755707"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>准备用于 ID 列表内容搜索的 CSV 文件

您可以使用特定邮箱电子邮件和其他邮箱项的列表来搜索Exchange条目。 若要创建 ID 列表搜索，你可以提交一个用于标识要搜索的特定邮箱项的逗号分隔符值 (CSV) 文件。 对于此 CSV 文件，使用 **Results.csv** 文件或在您导出内容搜索结果或从现有内容搜索导出内容搜索报告时包含的 **Unindexed Items.csv** 文件。 然后，编辑其中一个文件以指示要搜索的特定项目、创建新的 ID 列表搜索并提交 CSV 文件。

**为什么要创建 ID 列表搜索？** 如果无法确定项目是否根据 **Results.csv** 或 **Unindexed Items.csv** 文件中元数据对电子数据展示请求做出响应，可以使用 ID 列表搜索来查找、预览该项目，然后导出该项目以确定该项目是否响应正在调查的案例。 ID 列表搜索通常用于搜索和返回一组特定的未索引项目。

以下是创建 ID 列表搜索的过程的快速概述。

1. 在搜索中新建并运行Microsoft 365 合规中心。

2. 导出内容搜索结果或内容搜索报告。 有关更多信息，请参阅：

    - [导出内容搜索结果](export-search-results.md)

    - [导出内容搜索报告](export-a-content-search-report.md)

3. 编辑 **Results.csv** 未索引 **Items.csv文件，** 并确定要包括在 ID 列表搜索中的特定邮箱项目。 请参阅 [为](#prepare-the-csv-file-for-an-id-list-search) ID 列表搜索准备 CSV 文件的说明。

4. 创建新的 ID 列表搜索 (查看 [) ](#create-an-id-list-search) 并提交您准备的 CSV 文件的说明。 创建的搜索查询将仅搜索 CSV 文件中所选的项目。

> [!NOTE]
> 仅邮箱项目支持 ID 列表搜索。 在 ID 列表搜索中SharePoint OneDrive搜索文档和文档。

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>准备用于 ID 列表搜索的 CSV 文件

导出搜索结果或搜索报告后，执行以下步骤以准备用于 ID 列表搜索的 CSV 文件。 此 CSV 文件标识 ID 列表搜索中的每个项目。

可以从搜索（包括网站和帐户SharePoint CSV 文件OneDrive，但只能选择用于 ID 列表搜索的邮箱项目。 如果在文档或SharePoint中选择OneDrive，则创建 ID 列表搜索时 CSV 文件验证失败。

1. 在Results.csv **中****打开"** 未Items.csv索引Excel。

2. 在 **"所选****"列中，** 在对应于要搜索的项目的单元格中键入"是"。 对要搜索的每个项目重复此步骤。

    > [!IMPORTANT]
    > 当您在"文档 ID"Excel中打开 CSV 文件时，"文档 **ID"** 列的数据格式可能已更改为 **"常规"。** 这导致以科学表示法显示项目的文档 ID。 例如，"481037338205"的文档 ID 显示为"4.81037E+11"。 如果发生这种情况，您必须执行以下步骤以将"文档 **ID"** 列的数据格式更改为 **"** 数字"，以还原文档 ID 的正确格式。 如果不这样做，则使用 CSV 文件的 ID 列表搜索将失败。

3. 右键单击整个"**文档 ID"** 列，然后选择"**设置单元格格式"。**

4. 在"**类别"** 框中，单击"**数字"。**

5. 将小数位数更改为 **0，** 然后单击 **"确定"** 保存更改。 请注意，"文档 ID"列中的值将更改为数字。

    下面是准备提交用于 ID 列表内容搜索的 CSV 文件的示例。

    ![目标内容搜索的 CSV 文件示例。](../media/SearchIDListCSVFile.png)

6. 保存 CSV 文件或使用 **另存为** 保存文件，文件名不同。 在这两种情况下，请务必使用 CSV 格式保存文件。

## <a name="create-an-id-list-search"></a>创建 ID 列表搜索

下一步是创建新的 ID 列表搜索并提交你在上一步中准备的 CSV 文件。

> [!IMPORTANT]
> 应在导出搜索结果或报告后的 2 天内创建 ID 列表搜索。 如果搜索结果或报告导出时间超过 2 天，应重新导出搜索结果或报告以生成更新的 CSV 文件。 然后，你可以准备其中一个更新的 CSV 文件，并使用它创建 ID 列表搜索。

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">"Microsoft 365 合规中心</a>并登录。

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击“**显示所有**”，然后单击“**内容搜索**”。

3. 在"**内容搜索"页上**，单击"**按 ID 列表搜索"。**

4. 在"**按 ID 搜索列表**"飞出菜单上，将搜索 (并视需要将其描述为) 然后单击"浏览"，然后选择在上一步中准备的 CSV 文件。

    Microsoft 365尝试验证 CSV 文件。 如果验证失败，则会显示一条错误消息，可帮助您解决验证错误。 CSV 文件必须成功验证，以创建 ID 列表搜索。

5. 成功验证 CSV 文件后，单击" **搜索** "创建 ID 列表搜索。

    下面是 ID 列表搜索中的飞出页示例，其中显示生成的查询和搜索结果的估计数量。

    ![ID 列表搜索的搜索查询。](../media/SearchIDListFlyout.png)

    在 ID 搜索的统计信息中显示的估计项目数应该与 CSV 文件中所选的项目数相匹配。

6. 预览或导出 ID 列表搜索返回的项目。

## <a name="more-information"></a>详细信息

如果在创建 ID 列表搜索后移动邮箱，则搜索查询不会返回指定的项目。 这是因为移动邮箱时更改了邮箱项目的 **DocumentId** 属性。 在极少数情况下，当您创建 ID 列表搜索后移动邮箱时，您应创建新的内容搜索 (或更新现有搜索) 然后导出搜索结果或报告以生成可用于创建新的 ID 列表搜索的更新 CSV 文件。
