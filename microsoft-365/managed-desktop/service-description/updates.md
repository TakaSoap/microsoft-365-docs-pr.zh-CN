---
title: 如何在 Microsoft 托管桌面中处理更新
description: 将 Microsoft 托管桌面保持最新状态是速度和稳定性的平衡。
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0dad909ce9e17f993de64ba39b08f388c71abb89
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278641"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>如何在 Microsoft 托管桌面中处理更新


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 托管桌面将所有设备连接到基于云的新式基础结构。 保持 Windows、Office、驱动程序、固件和 Microsoft Store for Business 应用程序更新最新是速度和稳定性的平衡。 部署组将用于确保以安全的方式推出 OS 和策略。 

由 Microsoft 发布的更新是累积的, 可能会被分类为质量或功能更新。
有关详细信息, 请参阅[Windows update for Business: 更新类型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。 

## <a name="update-groups"></a>更新组

Microsoft 托管桌面使用四个 Azure AD 组管理更新:

- **测试**: 用于验证 Microsoft 托管桌面策略更改、OS 更新、功能更新和其他已推送到租户的更改。 测试组中不应放置任何最终用户。 测试组不受任何已建立的 sla 和最终用户支持的支持。 此组可用于验证应用程序与新策略或操作系统更改的兼容性。  
- **First**: 包含早期的软件采用者和设备, 可能受预发布更新的制约。 如果存在测试环中测试期间未涵盖的方案, 则此组中的设备可能会遇到中断。
- **Fast**: 按稳定性对速度进行优先级划分。 用于在向广泛组提供质量问题之前检测质量问题。 此组可用作验证的下一层, 但通常比测试和第一组更稳定。 
- **广泛**: 最后一个组具有可用的功能和质量更新。 此组包含租户中的大多数用户, 因此在部署过程中比速度更有利于稳定性。 应在此完成应用程序的测试, 因为环境最稳定。 

有关这些部署组的详细信息角色和职责, 请参阅[Microsoft 托管桌面角色和职责](../intro/roles-and-responsibilities.md)

更新部署的工作原理:
- Microsoft 托管桌面根据下面指定的计划, 部署新的功能或质量更新。
- 在部署过程中, Microsoft 托管的桌面监视器会针对故障或中断 (基于诊断数据信号和最终用户支持系统) 的迹象进行标记。 如果检测到任何其他组, 则会立即暂停部署到当前和将来的所有组。
    - 示例: 如果在将质量更新部署到第一个组时发现了问题, 则在解决问题之前, 先将部署更新到第一个、快速和广泛的过程将会暂停。
    - 可以通过在 Microsoft 托管桌面 IT 管理门户中存档票证来报告兼容性问题。
- 功能和质量更新是独立暂停的。 默认情况下, Pause 将对35天生效, 但可以根据问题是否修正来进行缩减或扩展。
- 一旦组未暂停, 部署将根据下面的计划恢复。
- 此部署过程适用于功能和质量更新, 尽管每个的时间线各不相同。

<table>
<tr><th colspan="5">更新部署设置</th></tr>
<tr><th>更新类型</th><th>测试</th><th>First</th><th>快速</th><th>宽泛</th></tr>
<tr><td>操作系统的质量更新</td><td>0天</td><td>0天</td><td>0天</td><td>3 天</td></tr>
<tr><td>操作系统的功能更新</td><td>0天</td><td>30 天</td><td>60 天</td><td>90 天</td></tr>
<tr><td>驱动程序/固件</td><td colspan="4">遵循质量更新计划</td></tr>
<tr><td>反病毒定义</td><td colspan="4">更新每个扫描</td></tr>
</table>

这些延期时段特意旨在确保所有用户的高安全性和性能标准。 此外, 根据在所有 Microsoft 托管桌面设备上收集的数据以及更新的不同范围和影响, Microsoft 托管桌面保留了灵活性, 以便在 ad 上修改任意和所有部署组的上述延期时段的长度hoc。

## <a name="windows-insider-program"></a>Windows 预览体验计划

Microsoft 托管桌面不支持属于 Windows 预览体验计划的设备。 windows 预览体验计划用于验证预发布的 Windows 软件, 适用于非关键设备。 虽然这是一个重要的 Microsoft 计划, 但不适合在生产环境中进行广泛的部署。 

使用 Windows 有问必答版本找到的任何设备都将放入测试组中, 并且不会包含在更新服务级别协议 (sla) 中。

## <a name="bandwidth-management"></a>带宽管理

传递优化用于所有操作系统和驱动程序更新。 它通过在企业网络中查找对等方的更新, 最小化 Windows Update (WU) 服务的下载大小。


