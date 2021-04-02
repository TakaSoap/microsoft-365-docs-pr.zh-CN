---
title: 使用高级搜寻的共享查询
description: 使用预定义的以及共享的查询快速启动威胁搜寻。 与公众或组织共享查询。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 自定义检测， 架构， kusto， github 存储库， 我的查询， 共享查询
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 78a532167e4256e3453803f1a0b4a9e4875771cf
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499428"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>使用高级搜寻的共享查询

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

可以与同一个组织内的用户共享[高级搜寻](advanced-hunting-overview.md)查询。 还可以查找在 GitHub 上公开共享的查询。 借助这些查询，你可以快速追寻特定威胁搜寻方案，而无需从头开始编写查询。

![共享查询的图像](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>保存、修改和共享查询
可以保存新的或已有的查询，以便只有你可以访问它，或将它与组织内的其他用户共享。

1. 在"共享查询"或"我的查询"下键入新查询或 **加载现有查询**。

2. 从 **保存** 选项 **中选择** 保存或另存为。 若要避免覆盖现有查询，请选择"**另存为"。**

3. 输入查询的名称。

   ![保存查询的图像](images/advanced-hunting-save-query.png)

4. 选择要将查询保存到的文件夹。
    - **共享查询** - 与组织中所有用户共享
    - **我的查询** — 只有你可以访问
    
5. 选择“保存”。

## <a name="delete-or-rename-a-query"></a>删除或重命名查询
1. 右键单击要重命名或删除的查询。

    ![删除查询的图像](images/atp_advanced_hunting_delete_rename.png)

2. 选择“删除”，并确认删除。 或者选择“重命名”，并为查询提供新名称。

## <a name="create-a-direct-link-to-a-query"></a>创建指向查询的直接链接
若要生成直接在高级搜寻查询编辑器中打开查询的链接，请完成查询并选择"**共享链接"。**

## <a name="access-queries-in-the-github-repository"></a>访问 GitHub 存储库中的查询  
Microsoft 安全研究人员定期在[指定的 GitHub 公共存储库](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)中共享高级搜寻查询。 此存储库可自行参与。 [免费加入 GitHub](https://github.com/)，即可参与。 

>[!TIP]
>此外，Microsoft 研究人员还提供了高级搜寻查询，你可以使用它们查找与存在的威胁关联的活动和指示器。 将这些查询作为 Microsoft Defender 安全中心[威胁分析](threat-analytics.md)报告的一部分提供。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [了解架构](advanced-hunting-schema-reference.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](overview-custom-detections.md)
