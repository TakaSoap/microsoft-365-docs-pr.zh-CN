---
title: Microsoft 托管桌面如何处理更新
description: 及时更新 Microsoft 托管桌面是速度和稳定性的平衡。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865505"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft 托管桌面如何处理更新


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 托管桌面连接到基于云的现代基础结构的所有设备。确保业务应用程序更新的 Windows、 Office、 驱动程序、 固件和 Microsoft 存储最新是速度和稳定性的平衡。部署在拨打将用于确保 OS 和策略的推出以安全方式。 

## <a name="update-rings"></a>更新响铃

Microsoft 托管桌面使用四个 Azure AD 组来管理更新：

- 测试： 测试拨打仅用于测试和验证的客户租户中所做的更改。  
- 第一个： 首先被用于与愿意早期安装软件和采用某些预发布更新的有限的技术知识用户早期测试振铃。
- 快速： fast 环是我们期望用户一大组。 此拨打的目标是以保持设备更新和安全与软件传递快速速度。  
- 广泛： 慢环是平衡保守滚超出质量和功能的更新。 高质量的更新仍传送较快的速度，但不是立即。 

拨打系统中的更新被分类为质量，或更新的功能：
- 高质量的更新包括安全，critical、 和驱动程序更新。 这些是通常每月更新。 
- 功能更新包含不仅安全和质量修订，但也显著功能新增功能和更改;每年分号发布它们。 

拨打升级的工作原理：
- Microsoft 托管桌面部署新的功能或质量更新，将根据下面指定的计划。
- 在部署期间，Microsoft 托管桌面监视的故障或其他中断 （通过遥测信号和我们最终用户支持系统）; 迹象如果检测到任何已立即暂停部署到所有当前和将来响铃。
    - 示例： 如果质量的更新部署到首次响铃时发现问题时，然后首先，Fast 和广泛将所有暂停解决该问题之前。
    - 兼容性问题可能会报告归档 Microsoft 托管桌面 IT 管理门户中的票证。
- 功能和质量更新独立暂停。 暂停实际上是默认情况下 35 天，但可减少或扩展具体取决于是否修正问题。
- 未暂停响铃后，部署恢复根据以下计划。
- 此升级过程适用于功能和质量更新，但日程表会有所不同，每个。

<table>
<tr><th colspan="5">拨打和延迟设置</th></tr>
<tr><th>更新类型</th><th>测试拨打</th><th>第一个</th><th>快速</th><th>广泛</th></tr>
<tr><td>高质量的操作系统的更新</td><td>0 天</td><td>0 天</td><td>1 天</td><td>5 天</td></tr>
<tr><td>操作系统的功能更新</td><td>半年通道 （目标） + 0 天</td><td>半年通道 （目标） + 30 天</td><td>半年通道 （目标） + 60 天</td><td>半年通道 + 30 天</td></tr>
<tr><td>驱动程序/固件</td><td colspan="4">遵循高质量的更新的计划</td></tr>
<tr><td>防病毒定义</td><td colspan="4">更新了每个扫描</td></tr>
<tr><td>Office 支持加号单击可运行</td><td colspan="4">与半年通道对齐</td></tr>
</table>


## <a name="windows-insider-program"></a>Windows 内幕计划

Microsoft 托管桌面不支持 Windows 内幕计划的一部分的设备。此程序用于验证预发行 Windows 软件和适用于非任务关键设备。尽管这是一项重要 Microsoft 举措，它不是在生产环境中的广泛部署。 

与 Windows 内幕生成找到任何设备将放入测试振铃，并不会包含更新 Sla。

## <a name="bandwidth-management"></a>带宽管理

传递优化用于所有操作的系统和驱动程序更新。它旨在从企业网络内部的对等方的更新，降至最低从 Windows 更新 (WU) 服务下载的大小。


