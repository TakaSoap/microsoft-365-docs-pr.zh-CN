---
title: 设备清单
description: 了解可从"设备"列表中使用的可用功能，例如排序、筛选和导出列表以增强调查。
keywords: 排序， 筛选， 导出， csv， 设备名称， 域， 上次看到， 内部 IP， 运行状况状态， 活动警报， 活动恶意软件检测， 威胁类别， 查看警报， 网络， 连接， 恶意软件， 类型， 密码窃取器， 勒索软件， 攻击， 威胁， 一般恶意软件， 不需要的软件
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
ms.openlocfilehash: 631a141ca6c898c6394bfd34839fd65d351fe8fc
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665527"
---
# <a name="device-inventory"></a>设备清单

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-machinesview-abovefoldlink)。

" **设备"列表** 显示网络中生成警报的设备列表。 默认情况下，队列显示过去 30 天内看到的设备。

一目了然，你将看到诸如域、风险级别、OS 平台和其他详细信息，以便轻松识别风险最大的设备。

可以选择多个选项来自定义设备列表视图。 在顶部导航上，可以：

- 添加或删除列
- 以 CSV 格式导出整个列表
- 选择每个页面要显示的项数
- 应用筛选器

在载入过程中， **设备列表** 在设备开始报告传感器数据时会逐渐填充。 使用此视图可在载入终结点联机时跟踪这些终结点，或下载完整的终结点列表作为 CSV 文件进行脱机分析。

> [!NOTE]
> 如果导出设备列表，它将包含组织中的每个设备。 下载可能需要大量时间，具体取决于你的组织有多大。 以 CSV 格式导出列表以未经筛选的方式显示数据。 CSV 文件将包含组织中的所有设备，而不管在视图本身中应用了任何筛选。

:::image type="content" source="images/device-inventory.png" alt-text="设备列表" lightbox="images/device-inventory.png":::

## <a name="sort-and-filter-the-device-list"></a>对设备列表进行排序和筛选

可以应用以下筛选器来限制警报列表并获取更集中的视图。

### <a name="device-name"></a>设备名称

在Microsoft Defender for Endpoint载入过程中，载入到 MDE 的设备在开始报告传感器数据时会逐渐填充到设备清单中。 在此之后，设备清单由通过设备发现过程在网络中发现的设备填充。 设备清单有三个选项卡，按以下方式列出设备：

- **计算机和移动**：Enterprise终结点 (工作站、服务器和移动设备) 
- **网络设备**：路由器和交换机等设备
- **IoT 设备**：打印机和照相机等设备

## <a name="navigate-to-the-device-inventory-page"></a>导航到"设备清单"页

通过从 [Microsoft 365 Defender门户](/defender/microsoft-365-security-center-mde)的 **"终结点**"导航菜单中选择 **"设备清单**"，访问设备清单页。

## <a name="device-inventory-overview"></a>设备清单概述

设备清单将在 **"计算机和移动"** 选项卡上打开。一目了然，你将看到设备名称、域、风险级别、暴露级别、OS 平台、载入状态、传感器运行状况等信息，以便轻松识别风险最大的设备。

使用 **"载入状态"** 列按发现的设备以及已载入到Microsoft Defender for Endpoint的设备进行排序和筛选。

![包含设备列表的设备列表的图像。](images/device-inventory.png)

在 **"网络设备** "和 **"IoT 设备"** 选项卡中，你还将看到供应商、模型和设备类型等信息：

![网络设备列表的图像。](images/device-inventory-networkdevices.png)

在每个设备清单选项卡的顶部，可以看到设备总数、尚未加入的设备数，以及已确定为组织风险较高的设备数。 可以使用此信息来帮助你确定设备的安全状况改进的优先级。

**新发现的** 网络设备和 IoT 设备的设备计数选项卡显示在当前视图中列出的最近 7 天内发现的新设备数。

![新发现的设备计数的图像。](images/new-discovered-devices.png)

## <a name="explore-the-device-inventory"></a>浏览设备清单

可以选择多个选项来自定义设备清单视图。 在每个选项卡的顶部导航上，可以：

- 按名称搜索设备
- 按最近使用的 IP 地址或 IP 地址前缀搜索设备
- 添加或删除列
- 以 CSV 格式导出整个列表以进行脱机分析
- 选择要显示的日期范围
- 应用筛选器

> [!NOTE]
> 如果导出设备列表，它将包含组织中的每个设备。 下载可能需要大量时间，具体取决于你的组织有多大。 以 CSV 格式导出列表以未经筛选的方式显示数据。 CSV 文件将包含组织中的所有设备，而不管在视图本身中应用了任何筛选。

可以使用每个设备清单选项卡上可用的排序和筛选功能来获取更集中的视图，并帮助你评估和管理组织中的设备。

每个选项卡顶部的计数将基于当前视图进行更新。

## <a name="use-filters-to-customize-the-device-inventory-views"></a>使用筛选器自定义设备清单视图

筛选器 | 说明
:---|:---
**风险级别** </br> | 风险级别反映设备的总体风险评估，具体取决于多种因素，包括设备上活动警报的类型和严重性。 解决活动警报、批准修正活动和禁止后续警报可以降低风险级别。
**曝光级别** </br> | 公开级别根据设备挂起的安全建议的累积影响，反映了设备的当前曝光情况。 可能的级别为低、中和高。 低曝光率意味着你的设备更容易受到剥削。 </br> </br> 如果曝光级别显示"没有可用数据"，则存在以下几种原因：</br>- 设备停止报告超过 30 天。 在这种情况下，它被视为非活动状态，并且不会计算曝光率。</br>- 不支持设备 OS - 请参阅[Microsoft Defender for Endpoint的最低要求](/microsoft-365/security/defender-endpoint/minimum-requirements)。</br>- 代理过时的设备 (不太可能) 。
**Tags** </br> | 根据已添加到单个设备的分组和标记筛选列表。 请参阅 ["创建和管理设备标记](machine-tags.md)"。
**设备值**</br> | 根据设备是否已标记为高值或低值来筛选列表。
**排除状态** </br> | 根据设备是否已排除来筛选列表。 有关详细信息，请参阅 [排除设备](exclude-devices.md)。
**OS 平台** </br>| 按你感兴趣的 OS 平台进行筛选 </br></br> (_计算机以及移动设备和 IoT 设备仅_) 
**首次看到** </br> | 根据首次在网络中看到设备的时间或Microsoft Defender for Endpoint传感器首次报告设备的时间来筛选视图。</br></br> (_计算机以及移动设备和 IoT 设备仅_) 
**Windows 版本** </br> | 按你感兴趣的Windows版本进行筛选。</br></br> _仅 (计算机和移动_ 设备) 
**传感器运行状况** </br> | 按以下传感器运行状况状态进行筛选，以便载入设备Microsoft Defender for Endpoint：</br> - **活动**：主动向服务报告传感器数据的设备。</br> - **非活动**：已停止发送信号超过 7 天的设备。 </br> - **配置错误**：设备无法与服务通信或无法发送传感器数据。 </br> 配置错误的设备可进一步分类为： </br>  - 无传感器数据 </br>  - 通信受损 </br>  有关如何解决配置错误设备的问题的详细信息，请参阅： [修复不正常的传感器](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors)。</br></br> _仅 (计算机和移动_ 设备) 
**载入状态** </br> | 载入状态指示设备当前是否已载入Microsoft Defender for Endpoint。 可以按以下状态进行筛选： </br> - **载入**：终结点载入到Microsoft Defender for Endpoint。  </br> - **可以载入**：终结点已作为受支持的设备在网络中发现，但目前尚未载入。 Microsoft 强烈建议载入这些设备。 </br> - **不支持**：终结点是在网络中发现的，但Microsoft Defender for Endpoint不支持。 </br> - **信息不足**：系统无法确定设备的可支持性。</br></br> _仅 (计算机和移动_ 设备) 
**防病毒状态** </br> | 根据防病毒状态是否已禁用、未更新或未知来筛选视图。</br></br> _仅 (计算机和移动_ 设备) 
**Group** </br> | 根据你感兴趣的组筛选列表。 </br></br> _仅 (计算机和移动_ 设备) 
**由** </br> | 通过指示如何管理设备进行管理来进行管理。 You can filter by:</br>- Microsoft Defender for Endpoint </br> - 移动设备管理 (MDM)  </br>- 未知：这可能是由于运行过时的Windows版本、SCCM 就位或其他第三方 MDM。</br></br> _仅 (计算机和移动_ 设备) 
**设备类型** </br> | 按你感兴趣的设备类型进行筛选。</br></br>  (_IoT 设备仅_) 

## <a name="use-columns-to-customize-the-device-inventory-views"></a>使用列自定义设备清单视图

可以从视图中添加或删除列，并通过单击可用列标题对条目进行排序。

在 **"计算机和移动"** 选项卡上，选择 **"自定义"列** 以查看可用的列。 在下图中检查默认值：

![计算机和移动设备的图像](images/computerandmobilescolumns.png)

在" **网络设备** "选项卡上，选择 **"自定义列** "以查看可用的列。 在下图中检查默认值：

![网络设备列的图像](images/networkdevicescolumns.png)

在 **"IoT 设备"** 选项卡上，选择 **"自定义列** "以查看可用的列。 在下图中检查默认值：

![IoT 设备列的图像](images/iotdevicescolumns.png)

## <a name="related-articles"></a>相关文章

[调查Microsoft Defender for Endpoint设备列表中的设备](investigate-machines.md)
