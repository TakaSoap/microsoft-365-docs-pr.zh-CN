---
title: 设备时间线中的技术
description: 了解 Microsoft Defender for Endpoint 中的设备时间线
keywords: 设备时间线， 终结点， MITRE， MITRE ATT&CK， 技术， 策略
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d724b7663bd4484c630e97362eb5766490e1fa8e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465896"
---
# <a name="techniques-in-the-device-timeline"></a>设备时间线中的技术

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

通过分析特定设备上发生的事件，你可以获取调查的更多见解。 首先，从"设备"列表中选择 [感兴趣的设备](machines-view-overview.md)。 在设备页面上，可以选择"时间线"选项卡以查看设备上发生的所有事件。

## <a name="understand-techniques-in-the-timeline"></a>了解时间线中的技术

> [!IMPORTANT]
> 某些信息与公共预览版中预发布的产品功能相关，在商业发行之前可能会对其进行重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

在 Microsoft Defender for Endpoint 中 **，** 技术是数据类型时间线中的附加功能。 技术提供有关与 [MITRE ATT 和 CK](https://attack.mitre.org/) 技术&子技术相关的活动的更多见解。

此功能通过帮助分析员了解在设备上观察到的活动来简化调查体验。 然后，分析员可以决定进行进一步调查。

对于公共预览，技术默认可用，在查看设备的时间线时与事件一起显示。

:::image type="content" source="images/device-timeline-2.png" alt-text="设备时间线中的技术" lightbox="images/device-timeline-2.png":::

技术以粗体文本突出显示，左侧显示蓝色图标。 相应的 MITRE ATT&CK ID 和技术名称也显示为其他信息下的标记。

搜索和导出选项还可用于技术。

## <a name="investigate-using-the-side-pane"></a>使用侧窗格进行调查

选择一种技术以打开其对应的侧窗格。 你可以在此处查看其他信息和见解，如相关 ATT&CK 技术、策略和说明。

选择特定 *攻击技术* 以打开相关 ATT&CK 技术页面，可在其中找到有关它的信息。

在右侧看到蓝色图标时，可以复制实体的详细信息。 例如，若要复制相关文件的 SHA1，请选择蓝色页面图标。

:::image type="content" source="images/techniques-side-pane-clickable.png" alt-text="要复制实体详细信息的" lightbox="images/techniques-side-pane-clickable.png":::

您可以对命令行执行相同的操作。

:::image type="content" source="images/techniques-side-pane-command.png" alt-text="复制命令行的选项" lightbox="images/techniques-side-pane-command.png":::

## <a name="investigate-related-events"></a>调查相关事件

若要使用 [高级搜寻](advanced-hunting-overview.md) 查找与所选技术相关的事件，请选择 **"搜寻"查找相关事件**。 这将导致高级搜寻页面，该页面具有用于查找与技术相关的事件的查询。

:::image type="content" source="images/techniques-hunt-for-related-events.png" alt-text="&quot;搜寻相关事件&quot;选项" lightbox="images/techniques-hunt-for-related-events.png":::

> [!NOTE]
> 使用"技术"侧窗格中的 **"搜寻** 相关事件"按钮进行查询将显示与标识的技术相关的所有事件，但不包括技术本身在查询结果中。

## <a name="customize-your-device-timeline"></a>自定义设备时间线

在设备时间线的右上角，你可以选择一个日期范围来限制时间线中的事件和技术数量。

您可以自定义要公开哪些列。 您还可以按事件组或事件组数据类型标记的事件。

### <a name="choose-columns-to-expose"></a>选择要公开列

可以通过选择"选择列"按钮选择要在日程表 **中公开哪些** 列。

:::image type="content" source="images/filter-customize-columns.png" alt-text="可在其中自定义列的窗格" lightbox="images/filter-customize-columns.png":::


可以从中选择要包含的信息集。

### <a name="filter-to-view-techniques-or-events-only"></a>筛选以仅查看技术或事件

若要仅查看事件或技术， **请从设备** 时间线选择筛选器，然后选择要查看的首选数据类型。

:::image type="content" source="images/device-timeline-filters.png" alt-text="&quot;筛选器&quot;窗格" lightbox="images/device-timeline-filters.png":::

## <a name="see-also"></a>另请参阅

- [查看和组织设备列表](machines-view-overview.md)
- [Microsoft Defender for Endpoint 设备时间线事件标志](device-timeline-event-flag.md)
