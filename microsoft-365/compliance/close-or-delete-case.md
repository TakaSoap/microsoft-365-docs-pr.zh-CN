---
title: 关闭或删除事例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: ''
description: 了解在关闭或删除受调查案例支持的调查Advanced eDiscovery法律案件时会发生什么情况。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657632"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>关闭或删除Advanced eDiscovery案例

完成案例支持的法律案件或调查Advanced eDiscovery，可以关闭或删除案例。 您还可以重新打开已关闭的案例。

## <a name="close-a-case"></a>关闭案例

下面是关闭事件案例时Advanced eDiscovery情况：

- 如果案例包含任何保留内容位置，这些保留将被关闭。 关闭保留后，称为延迟保留 (30 天的宽限期) 将应用于已保留的内容位置。 这有助于防止立即删除内容，并给予管理员搜索或恢复将在延迟保留期过期后永久删除的内容的机会。 有关详细信息，请参阅从电子数据展示保留 [中删除内容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。

- 关闭案例仅关闭与该案例相关联的保留。 如果其他保留位于内容位置 (如诉讼保留、核心电子数据展示保留或其他 Advanced eDiscovery 案例的保留) 仍将保留这些保留。

- 该案例仍在安全与合规中心的"电子数据展示"Microsoft 365列出。 将保留已关闭案例的详细信息、保留、搜索和成员。

- 可以在案例关闭后对其进行编辑。 例如，您可以添加或删除成员、创建搜索、导出搜索结果以及准备搜索结果以在 Advanced eDiscovery。 活动事例和已关闭事例的主要区别在于当事例关闭时，保留已关闭。

关闭案件：

1. 在 **高级电子数据展示** 页面上，选择要关闭的案件。

2. 在" **设置** 选项卡上，**"案例信息**"下， 点击 **选择**。

3. 在"案例信息"飞出页面底部，单击 **" (...") "** 更多选项"，然后单击"**关闭案例"。**

   !["更多选项"菜单中用于关闭事件Advanced eDiscovery选项](..\Media\CloseAdvancedeDiscoveryCase.png)

   完成结束过程可能需要多达 60 分钟。

## <a name="reopen-a-closed-case&quot;></a>重新打开已关闭的案例

当重新打开Advanced eDiscovery案例时，关闭案例时已就位的任何保留不会自动恢复。 重新打开案例后，你必须转到保留选项卡并打开以前的保留。  要打开保留，请选择它以显示弹出页面，然后将 **状态** 开关设置为 **“开”**。

重新打开已关闭案例：

1. 在 **高级电子数据展示** 页面上，选择要关闭的案件。

2. 在&quot; **设置** 选项卡上，**&quot;案例信息**&quot;下， 点击 **选择**。

3. 在&quot;案例信息&quot;飞出页面底部，单击&quot; (**...") "** 更多 **选项**"，然后单击"**重新打开案例"。**

   !["更多选项"菜单中用于重新打开Advanced eDiscovery选项](..\Media\ReopenAdvancedeDiscoveryCase.png)

   可能需要 60 分钟才能完成重新打开过程。

## <a name="delete-a-case"></a>删除案例

可以删除活动用例和已关闭Advanced eDiscovery案例。 删除案例时，与该案例关联的所有组件（例如保管人列表、通信、搜索、审阅集和导出作业）都将被删除。 从合规中心内"Advanced eDiscovery"页面上Microsoft 365事例列表。 无法恢复或重新打开已删除的案例。

> [!NOTE]
> 在数据泄漏方案中，删除审阅集内项目的唯一方法就是删除Advanced eDiscovery案例。 其他"搜索和清除"方法不会从审阅集中删除项目。

在删除案例之前 (是处于活动状态还是已关闭) ，您必须先删除与该案例关联的所有保留。  这包括删除状态为"关"的 **保留**。

删除与案例相关联的保留项：

1. Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.

2. 单击要删除的保留。

3. 在飞出页面上，单击删除 **保留**。

删除案件：

1. 在 **高级电子数据展示** 页面上，选择要关闭的案件。

2. 在" **设置** 选项卡上，**"案例信息**"下， 点击 **选择**。

3. 在"案例信息"飞出页底部，单击 **" (...")****更多选项**"，然后单击"删除 **大小写"。**

   !["更多选项"菜单中用于删除Advanced eDiscovery选项](..\Media\DeleteAdvancedeDiscoveryCase.png)
