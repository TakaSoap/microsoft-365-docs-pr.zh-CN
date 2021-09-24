---
title: 报告 Microsoft Defender for Endpoint ASR 规则并排除故障
description: 本主题介绍如何报告 Microsoft Defender for Endpoint ASR 规则并排除故障
keywords: 攻击面减少规则， asr， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， microsoft defender 终结点
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: ecd38f39ddbc50876c6dbc6f5edf227d0f17a495
ms.sourcegitcommit: 584445b62cb82218597b62495fb76fcb5b12af9d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2021
ms.locfileid: "59498336"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>针对 ATP ASR 规则报告 Microsoft Defender 并排除故障

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

安全Microsoft 365中心是跨 Microsoft 标识、数据、设备、应用和基础结构监视和管理安全性的新界面。 可在此处轻松查看组织的安全运行状况、配置设备、用户和应用，并获取可疑活动的警报。 Microsoft 365 安全中心旨在帮助安全管理员和安全操作团队更好地管理和保护其组织。 请访问 上Microsoft 365安全中心 <https://security.microsoft.com> 。

在Microsoft 365安全中心中，我们将提供你当前 ASR 规则配置和您资产中的事件的完整外观。 请注意，你的设备必须载入到 Microsoft Defender for Endpoint 服务中，以填充这些报告。
下面是报告设备攻击面减少Microsoft 365下 (安全 \>  \> **中心中的** 屏幕截图) 。 在设备级别 **，从攻击** 面减少规则 **窗格中选择配置** 。 将显示以下屏幕，可在其中选择特定设备并检查其单独的 ASR 规则配置。

:::image type="content" source="images/asrrulesnew.png" lightbox="images/asrrulesnew.png" alt-text="ASR 规则屏幕。":::

## <a name="microsoft-defender-for-endpoint---advanced-hunting"></a>Microsoft Defender for Endpoint - 高级搜寻

Microsoft Defender for Endpoint 的最强大功能之一是高级搜寻。 如果你不熟悉高级搜寻，请参阅使用高级搜寻主动 [搜寻威胁](advanced-hunting-overview.md)。

高级搜寻是基于查询的 (Kusto 查询语言) 威胁搜寻工具，允许你浏览从你的设备收集的最多 30 天的捕获 (原始) 数据。 通过高级搜寻，你可以主动检查事件以查找有趣的指示器和实体。 灵活访问数据有助于不受约束地搜寻已知威胁和潜在威胁。

通过高级搜寻，可以提取 ASR 规则信息、创建报告，并获取有关给定 ASR 规则审核或阻止事件的上下文的深入信息。

ASR 规则事件可从应用高级搜寻部分中的 DeviceEvents 表中Microsoft 365 Defender。 例如，如下所示的简单查询可以报告过去 30 天内将 ASR 规则作为数据源的所有事件，并按 ActionType 计数汇总这些事件，在这种情况下，它将是 ASR 规则的实际代码名。

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="高级搜寻查询。":::

:::image type="content" source="images/adv-hunt-sc-2new.png" lightbox="images/adv-hunt-sc-2new.png" alt-text="高级搜寻屏幕。":::

借助高级搜寻，你可以使查询符合自己的喜好，以便你可以查看发生的情况，无论你是想要在单台计算机中定位某些内容，还是想要从整个环境中提取见解。

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Microsoft Defender for Endpoint 计算机时间线

Microsoft Defender for Endpoint 计算机时间线是高级搜寻的替代方法，但范围较窄。 你可以查看过去六个月内设备的所有收集的事件，在 Microsoft 365 Defender 中，通过进入计算机列表，选择给定计算机，然后单击时间线选项卡。

下图是给定终结点上这些事件的时间线视图的屏幕截图。 从此视图中，可以基于右侧窗格中的任何事件组筛选事件列表。 还可以在查看警报和滚动历史时间线时启用或禁用已标记和详细事件。

:::image type="content" source="images/mic-sec-def-timelinenew.png" lightbox="images/mic-sec-def-timelinenew.png" alt-text="Microsoft 365 Defender时间线。":::

## <a name="how-to-troubleshoot-asr-rules"></a>如何解决 ASR 规则问题？

第一种也是最直接的方法就是在本地检查 Windows 设备上启用的 ASR 规则 (其配置) 是使用 PowerShell cmdlet。

下面是一些其他一些信息源，Windows ASR 规则的影响和操作疑难解答。

### <a name="querying-which-rules-are-active"></a>查询哪些规则处于活动状态

确定 ASR 规则是否已启用的最简单方法是通过 PowerShell cmdlet Get-MpPreference。

下面是一个示例：

:::image type="content" source="images/getmpreferencescriptnew.png" lightbox="images/getmpreferencescriptnew.png" alt-text="get mppreference 脚本。":::

有多个 ASR 规则处于活动状态，具有不同的配置操作。

若要展开有关 ASR 规则的上述信息，可以使用属性 **AttackSurfaceReductionRules_Ids** 和/或 **AttackSurfaceReductionRules_Actions**。

示例：

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids
```

:::image type="content" source="images/getmpref-examplenew.png" alt-text="获取 mpreference 示例。":::

上面显示了设置不同于 0 的 ASR 规则的所有 (未配置) 。

下一步是列出每个规则 (配置) 或审核策略的实际操作。

```powershell
Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions
```

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2.":::

### <a name="querying-blocking-and-auditing-events"></a>查询阻止和审核事件

可以在活动日志中查看 ASR 规则Windows Defender事件。

若要访问它，请Windows事件查看器，并浏览到应用程序和服务日志 \> **Microsoft** Windows Windows Defender \>  \>  \> **操作**。

:::image type="content" source="images/eventviewerscrnew.png" lightbox="images/eventviewerscrnew.png" alt-text="事件查看器 scr。":::

## <a name="microsoft-defender-malware-protection-logs"></a>Microsoft Defender 恶意软件保护日志

您还可以通过专用的命令行工具（称为 Microsoft Defender 防病毒）查看规则事件，该工具可用于管理和配置任务，并 `*mpcmdrun.exe*` 根据需要自动执行任务。

您可以在 *%ProgramFiles%\Windows Defender\MpCmdRun.exe找到此实用工具*。 必须从提升的命令提示符下运行 (，即以管理员角色) 。

若要生成支持信息，请键入 *MpCmdRun.exe -getfiles*。 一段时间之后，多个日志将打包到存档 (MpSupportFiles.cab) *C：\ProgramData\Microsoft\Windows Defender\Support 中提供*。

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="恶意软件保护日志。":::

提取该存档，你将具有许多可用于故障排除的文件。

最相关的文件如下所示：

- **MPOperationalEvents.txt：** 此文件包含事件查看器中有关Windows Defender日志的相同级别的信息。
- **MPRegistry.txt：** 在此文件中，你可以分析所有当前Windows Defender配置，从捕获支持日志开始。
- **MPLog.txt：** 此日志包含有关项目的所有操作Windows Defender。
