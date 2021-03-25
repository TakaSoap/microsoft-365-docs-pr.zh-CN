---
title: 查看和组织 Microsoft Defender ATP 设备列表
description: 了解可从设备列表中使用的可用功能，例如排序、筛选和导出列表以增强调查。
keywords: 排序， 筛选， 导出， csv， 设备名称， 域， 上次看到时间， 内部 IP， 运行状况状态， 活动警报， 活动恶意软件检测， 威胁类别， 查看警报， 网络， 连接， 恶意软件， 类型， 密码窃取程序， 勒索软件， 攻击， 威胁， 常规恶意软件， 不需要的软件
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9068983b5f61305b1f3da4d076e99e71974e8df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185667"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>查看和组织适用于终结点设备的 Microsoft Defender 列表

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


**"设备"** 列表显示网络中生成警报的设备列表。 默认情况下，队列显示最近 30 天内看到的设备。  

一目了然地，你将看到域、风险级别、操作系统平台和其他详细信息，以轻松识别风险最大的设备。

有几种选项可供选择以自定义设备列表视图。 在顶部导航上，你可以：

- 添加或删除列
- 导出 CSV 格式的整个列表
- 选择要显示每页的项目数
- 应用筛选器

在载入过程中， **设备列表** 将随着设备开始报告传感器数据而逐渐填充。 使用此视图在已载入终结点联机时跟踪它们，或下载完整的终结点列表作为 CSV 文件进行脱机分析。

>[!NOTE]
> 如果导出设备列表，它将包含组织的每台设备。 下载可能需要很长时间，具体取决于你的组织规模。 以 CSV 格式导出列表以未筛选的方式显示数据。 CSV 文件将包含组织的所有设备，而不考虑视图本身应用的任何筛选。

![包含设备列表的设备列表的图像](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a>排序和筛选设备列表

可以应用以下筛选器来限制警报列表，并获取更集中的视图。

### <a name="risk-level"></a>风险级别

风险级别根据各种因素（包括设备上活动警报的类型和严重性）反映了设备的总体风险评估。 解决活动警报、批准修正活动以及抑制后续警报会降低风险级别。

### <a name="exposure-level"></a>曝光级别

曝光级别根据设备挂起的安全建议累积影响反映设备的当前曝光情况。 可能的级别为低、中和高。 低曝光意味着你的设备不太容易被利用。

如果曝光级别显示"无可用数据"，可能有以下原因：

- 设备停止报告超过 30 天 - 在这种情况下，它被视为非活动状态，并且未计算曝光
- 设备操作系统不受支持 - 请参阅 [Microsoft Defender for Endpoint 的最低要求](minimum-requirements.md)
- 具有过时代理 (不太可能) 

### <a name="os-platform"></a>操作系统平台

仅选择你有兴趣调查的操作系统平台。

### <a name="health-state"></a>运行状况

按以下设备运行状况状态进行筛选：

- **活动** – 主动向服务报告传感器数据的设备。
- **非** 活动 – 已完全停止发送信号超过 7 天的设备。
- **错误配置** – 与服务通信受损或无法发送传感器数据的设备。 可以将错误配置的设备进一步分类为：
  - 无传感器数据
  - 通信受损

  若要详细了解如何解决错误配置设备上的问题，请参阅修复 [不正常的传感器](fix-unhealthy-sensors.md)。

### <a name="antivirus-status"></a>防病毒状态

按防病毒状态筛选设备。 仅适用于活动的 Windows 10 设备。

- **已禁用** - &威胁防护已关闭。
- **不报告** - 病毒&威胁防护未报告。
- **未更新** - 病毒&威胁防护不是最新的。

有关详细信息，请参阅查看威胁 [&漏洞管理仪表板](tvm-dashboard-insights.md)。

### <a name="threat-mitigation-status"></a>威胁缓解状态

若要查看受特定威胁影响的设备，请从下拉菜单中选择威胁，然后选择需要缓解的漏洞方面。

若要了解有关特定威胁的更多信息，请参阅 [威胁分析](threat-analytics.md)。 有关缓解信息，请参阅[威胁&漏洞管理。](next-gen-threat-and-vuln-mgt.md)

### <a name="windows-10-version"></a>Windows 10 版本

仅选择你有兴趣调查的 Windows 10 版本。

### <a name="tags--groups"></a>标记&组

根据已添加到个别设备的分组和标记筛选列表。 请参阅[创建和管理设备标记和](machine-tags.md)[创建和管理设备组](machine-groups.md)。

## <a name="related-topics"></a>相关主题

- [调查 Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)
