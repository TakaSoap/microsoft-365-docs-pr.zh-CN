---
title: Microsoft 365 Defender时区设置
description: 使用此处包含的信息配置Microsoft 365 Defender时区设置并查看许可证信息。
keywords: 设置， Microsoft Defender， 网络安全威胁智能， 适用于终结点的 Microsoft Defender， 时区， utc， 本地时间， 许可证
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a3f98af5251a5666a42c1f39539d557322e71e9
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165632"
---
# <a name="microsoft-365-defender-time-zone-settings"></a>Microsoft 365 Defender时区设置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)


> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-settings-abovefoldlink)。

使用时区 **菜单时区** ![ 设置图标 1。](images/atp-time-zone.png) 配置时区并查看许可证信息。

## <a name="time-zone-settings"></a>时区设置

时间方面对于评估和分析感知的和实际的网络攻击非常重要。

网络forensic调查通常依赖时间戳来拼贴事件序列。 系统反映正确的时区设置非常重要。

Microsoft Defender for Endpoint 可以显示协调世界时 (UTC) 本地时间。

你的当前时区设置显示在 Microsoft Defender for Endpoint 菜单中。 可以在"时区"菜单中更改显示的 **时区** 。

![时区设置 icon2。](images/atp-time-zone-menu.png).

### <a name="utc-time-zone"></a>UTC 时区

默认情况下，Microsoft Defender for Endpoint 使用 UTC 时间。

将 Microsoft Defender for Endpoint 时区设置为 UTC 将显示所有用户的所有 (、事件和其他) UTC 格式的时间戳。 这可以帮助在全球不同位置工作的安全分析师在调查事件时使用相同的时间戳。

### <a name="local-time-zone"></a>本地时区

你可以选择让 Microsoft Defender for Endpoint 使用本地时区设置。 所有警报和事件都将使用本地时区显示。

本地时区取自设备的区域设置。 如果你更改你的区域设置，Microsoft Defender 终结点时区也将更改。 选择此设置意味着 Microsoft Defender for Endpoint 中显示的时间戳将针对所有 Microsoft Defender for Endpoint 用户与本地时间保持一致。 位于不同全球地点的分析师现在将看到 Microsoft Defender for Endpoint 警报，其区域设置也有所不同。

如果分析师位于单个位置，则选择使用本地时间可能会很有用。 在这种情况下，将事件与本地时间关联可能更容易，例如，当本地用户单击可疑电子邮件链接时。

### <a name="set-the-time-zone"></a>设置时区

默认情况下，Microsoft Defender for Endpoint 时区设置为 UTC。 设置时区还会更改所有 Microsoft Defender 终结点视图的时间。

设置时区：

1. 单击时区 **菜单时区** ![ 设置图标 3。 ](images/atp-time-zone.png)
2. 选择 **时区 UTC** 指示器。
3. 选择 **时区 UTC** 或本地时区，例如 -7：00。

### <a name="regional-settings"></a>区域设置

若要为 Microsoft Defender for Endpoint 应用不同的日期格式，请使用 IE Internet Explorer (区域设置) Microsoft Edge (Edge) 。 如果你使用的是其他浏览器（如 Google Chrome），请按照所需步骤更改该浏览器的时间和日期设置。 

#### <a name="internet-explorer-ie-and-microsoft-edge"></a>Internet Explorer (IE) 和 Microsoft Edge

IE 和 Microsoft Edge使用"控制面板"中"时钟、**语言** 和地区"选项中配置的"区域"设置。 

#### <a name="known-issues-with-regional-formats"></a>区域格式的已知问题

##### <a name="date-and-time-formats"></a>日期和时间格式

时间和日期格式存在一些已知问题。 如果将区域设置配置为支持的格式外的其他任何内容，门户可能无法正确反映你的设置。

支持以下日期和时间格式：

- 日期格式 MM/dd/yyyy
- 日期格式 dd/MM/yyyy
- 时间格式 hh：mm：ss (12 小时格式) 

目前不支持以下日期和时间格式：

- 日期格式 yyyy-MM-dd
- 日期格式 dd-MMM-yy
- 日期格式 dd/MM/yy
- 日期格式 MM/dd/yy
- yy 的日期格式。 将只显示 yyyy。
- 时间格式 HH：mm：ss (24 小时格式) 

##### <a name="decimal-symbol-used-in-numbers"></a>数字中使用的小数符号

使用的小数符号始终是一个点，即使在"区域设置"中的"数字 **"格式** 设置中选择了 **逗号** 。 例如，15，5K 显示为 15.5K。
