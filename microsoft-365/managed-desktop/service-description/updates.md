---
title: Microsoft 托管桌面如何处理更新
description: 及时更新 Microsoft 托管桌面是速度和稳定性的平衡。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865505"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft 托管桌面如何处理更新


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 托管桌面连接到基于云的现代基础结构的所有设备。确保业务应用程序更新的 Windows、 Office、 驱动程序、 固件和 Microsoft 存储最新是速度和稳定性的平衡。部署在拨打将用于确保 OS 和策略的推出以安全方式。 

## <a name="update-groups"></a>更新组

Microsoft 托管桌面使用四个 Azure AD 组来管理更新：

- 测试： 非生产设备用于验证跨租户的其余部分部署所做的更改之前的更改。在此拨打的设备超出记录的最终用户支持的范围。 
- 首先： 包含前期软件应用，并且设备可能受到预发布更新。
- Fast： 优先稳定性速度。用于检测质量问题之前它们拨打给广泛的组。 
- 广泛： 最后一组具有可用的功能和质量更新。此组包含大多数租户中的用户，因此倾向稳定性于优先于部署中的速度。

累积和可能归类为质量或功能更新 Microsoft 发布的更新。有关详细信息，请参阅[Windows Update： 常见问题](https://support.microsoft.com/help/12373/windows-update-faq)。 

如何更新部署的工作方式：
- Microsoft 托管桌面部署新的功能或质量更新，将根据下面指定的计划。
- 在部署期间，Microsoft 托管桌面监视故障或中断 （基于遥测信号和最终用户支持系统） 的迹象。如果检测到任何已立即暂停部署到当前和将来的所有组。
    - 示例： 如果发现问题时质量的更新部署到的第一个组，然后更新到第一个、 Fast、 和广泛的部署将所有暂停解决该问题之前。
    - 兼容性问题可能会报告归档 Microsoft 托管桌面 IT 管理门户中的票证。
- 功能和质量更新独立暂停。暂停实际上是 35 天，默认情况下，但可减少或扩展具体取决于是否修正问题。
- 未暂停组后，部署恢复根据以下计划。
- 此部署过程适用于功能和质量更新，但日程表会有所不同，每个。

<table>
<tr><th colspan="5">更新部署设置</th></tr>
<tr><th>更新类型</th><th>测试</th><th>第一个</th><th>快速</th><th>广泛</th></tr>
<tr><td>高质量的操作系统的更新</td><td>0 天</td><td>0 天</td><td>0 天</td><td>3 天</td></tr>
<tr><td>操作系统的功能更新</td><td>0 天</td><td>30 天</td><td>60 天</td><td>90 天</td></tr>
<tr><td>驱动程序/固件</td><td colspan="4">遵循高质量的更新的计划</td></tr>
<tr><td>防病毒定义</td><td colspan="4">更新了每个扫描</td></tr>
</table>

这些延期段有意旨在确保高安全性和性能标准的所有用户。Microsoft 托管桌面基于跨所有 Microsoft 托管桌面设备和不同的范围和更新的影响整个收集的数据，此外，保留灵活地修改 ad 上的所有部署组上述延期期的时长临时基础。

## <a name="windows-insider-program"></a>Windows 内幕计划

Microsoft 托管桌面不支持 Windows 内幕计划的一部分的设备。Windows 内幕计划用于验证预发行 Windows 软件和适用于非任务关键设备。尽管这是一项重要 Microsoft 举措，它不是在生产环境中的广泛部署。 

与 Windows 内幕生成找到任何设备将置于测试组，且不可包含更新服务级别协议 (Sla。

## <a name="bandwidth-management"></a>带宽管理

传递优化用于所有操作的系统和驱动程序更新。它旨在从企业网络内部的对等方的更新，降至最低从 Windows 更新 (WU) 服务下载的大小。


