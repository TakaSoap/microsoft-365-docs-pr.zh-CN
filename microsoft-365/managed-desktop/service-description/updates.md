---
title: 如何在 Microsoft 托管桌面中处理更新
description: 使 Microsoft 托管桌面保持最新是速度和稳定性的平衡。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4d8de363cc9111fade719fdf5384519d1236f431
ms.sourcegitcommit: 05657b39eaafc0503b01c6adcc5d8a5e615dc02c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50031335"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>如何在 Microsoft 托管桌面中处理更新


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 托管桌面将所有设备连接到基于云的现代基础结构。 使 Windows、Office、驱动程序、固件和适用于 Business 的 Microsoft Store 应用程序保持最新是速度和稳定性的平衡。 部署组将用于确保以安全方式推出操作系统更新和策略。 有关详细信息，请参阅视频 Microsoft [托管桌面更改和发布过程](https://www.microsoft.com/videoplayer/embed/RE4mWqP)。

Microsoft 发布的更新是累积更新，并归类为质量更新或功能更新。
有关详细信息，请参阅适用于 Business [的 Windows 更新：更新类型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)。 

## <a name="update-groups"></a>更新组

Microsoft 托管桌面使用四个 Azure AD 组来管理更新：

- **测试**：用于验证 Microsoft 托管桌面策略更改、操作系统更新、功能更新以及推送到租户的其他更改。 测试组中不应放置任何用户。 测试组无需任何已建立的服务级别协议和用户支持。 此组可用于验证应用程序与新策略或操作系统更改的兼容性。  
- **第** 一：包含早期软件采用者以及可能受预发布更新限制的设备。 如果测试圈中测试期间未涵盖的方案，则此组中的设备可能会遇到中断。
- **快速**：将速度优先级设置在稳定性上。 可用于在向 Broad 组提供质量问题之前检测这些问题。 此组充当下一个验证层，但通常比 Test 和 First 组更加稳定。 
- **广泛**：最后一个提供功能和质量更新的组。 此组包含租户中的大多数用户，因此支持部署速度的稳定性。 应在此处测试应用，因为环境最稳定。 

### <a name="moving-devices-between-update-groups"></a>在更新组之间移动设备
你可能希望某些设备最后接收更新，而希望先接收其他更新。 若要将这些设备移动到相应的更新组，请提交管理员 [支持请求](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/admin-support?view=o365-worldwide) ，我们将为用户移动设备。 

> [!NOTE]
> 如果需要将用户移动到其他更新组，请提交支持请求。 不要自己在更新组之间移动设备。 如果设备移动不正确，则会产生严重的后果。 设备可能会意外更新，并且策略可能会发生冲突，更改设备配置。

有关这些部署组内的角色和职责详细信息，请参阅 Microsoft [托管桌面角色和职责](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>使用 Microsoft 托管桌面更新组 
你管理的部分服务（如应用部署）可能有必要面向所有托管设备。 在这些实例中，使用更新组联系这些用户，了解无法添加、删除或更改这些组的成员身份是有意义的。 

## <a name="how-update-deployment-works"></a>更新部署的工作原理：
1. Microsoft 托管桌面根据下表中指定的计划部署新功能或质量更新。
2. 在部署过程中，Microsoft 托管桌面基于诊断数据和用户支持系统监视故障或中断的迹象。 如果检测到任何一个，我们会立即将部署暂停到所有当前和将来的组。
    - 示例：如果在将质量更新部署到第一个组时发现问题，则更新为"第一个"、"快速"和"广泛"的部署将全部暂停，直到问题得到解决。
    - 可以通过在 Microsoft 托管桌面管理门户中填写票证来报告兼容性问题。
    - 功能和质量更新独立暂停。 默认情况下暂停生效 35 天，但可以减小或延长，具体取决于是否已修复问题。
3. 取消暂停组后，根据表中的计划恢复部署。

虽然每个更新的时间线各不相同，但此部署过程适用于功能更新和质量更新。




<table>
    <tr><th colspan="5">更新部署设置</th></tr>
    <tr><th>更新类型</th><th>测试</th><th>First</th><th>快速</th><th>宽泛</th></tr>
    <tr><td>操作系统的质量更新</td><td>0 天</td><td>0 天</td><td>0 天</td><td>3 天</td></tr>
    <tr><td>操作系统的功能更新</td><td>0 天</td><td>30 天</td><td>60 天</td><td>90 天</td></tr>
    <tr><td>驱动程序/固件</td><td colspan="4">遵循质量更新计划</td></tr>
    <tr><td>防病毒定义</td><td colspan="4">使用每次扫描更新</td></tr>
    <tr><td>Microsoft 365 企业应用版</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">了解更多</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">了解更多</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/teams#updates">了解更多</a></td></tr>
</table>

>[!NOTE]
>这些延迟期是特意设计的，以确保所有用户都符合高安全性和性能标准。 此外，基于在所有 Microsoft 托管桌面设备上收集的数据以及更新的不同范围和影响，Microsoft 托管桌面保留临时修改任何和所有部署组的上述延迟期长度的灵活性。
>
>Microsoft 托管桌面会针对每个 Windows 功能版本进行独立评估，以评估其对托管租户的必要性和有用性。 因此，Microsoft 托管桌面可能会或可能不会部署所有 Windows 功能更新。 

## <a name="windows-insider-program"></a>Windows 预览体验计划

Microsoft 托管桌面不支持属于 Windows 预览体验计划的设备。 Windows 预览体验计划用于验证预发行 Windows 软件，并且适用于非任务关键型设备。 虽然这是一个重要的 Microsoft 计划，但它不适合在生产环境中广泛部署。 

使用 Windows 预览体验成员版本发现的任何设备都可能会放入"测试"组中，并且不会从 Microsoft 托管桌面更新服务级别协议和用户支持。

## <a name="bandwidth-management"></a>带宽管理

我们将传递 [优化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) 用于所有操作系统和驱动程序更新。 这将通过从企业网络内的对等方处寻找更新来最大程度地减小 Windows 更新服务的下载大小。

