---
title: 如何在更新中处理Microsoft 托管桌面
description: 保持Microsoft 托管桌面是速度和稳定性的平衡。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 992ad102e07dbbca5aa0e1e4243ebade268906b1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211365"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>如何在更新中处理Microsoft 托管桌面


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 托管桌面设备连接到基于云的现代基础结构。 保持Windows、Office、驱动程序、固件适用于企业的 Microsoft Store应用程序是速度和稳定性的平衡。 我们使用更新组来确保以安全方式推出操作系统更新和策略。 有关详细信息，请参阅更改和Microsoft 托管桌面[过程的视频](https://www.microsoft.com/videoplayer/embed/RE4mWqP)。 

Microsoft 发布的更新是累积更新，并归类为质量更新或功能更新。
有关详细信息，请参阅适用于Windows[更新：更新类型](/windows/deployment/update/waas-manage-updates-wufb#update-types)。 

## <a name="update-groups"></a>更新组


Microsoft 托管桌面四个 Azure AD 组来管理更新：

- **测试**：用于验证Microsoft 托管桌面更改、操作系统更新、功能更新以及推送到 Azure AD 组织的其他更改 ("租户") 。 最适合测试或可以提供早期反馈的用户。 测试组不受任何已建立的服务级别协议和用户支持。 此组可用于验证应用程序与新策略或操作系统更改的兼容性。  
- **First**： Contains early software adopters and devices that could be subject to pre-release updates. 如果测试圈中的测试期间未涵盖的方案，则此组的设备可能会遇到中断。
- **快速**：将速度优先考虑稳定性。 用于检测质量问题，然后再提供给广泛组。 该组充当下一个验证层，但通常比 Test 和 First 组更加稳定。 
- **广泛**：最后一个提供功能和质量更新的组。 此组包含 Azure AD 组织中大多数用户，因此支持部署速度的稳定性。 应在此处测试应用，因为环境最稳定。

### <a name="moving-devices-between-update-groups"></a>在更新组之间移动设备
你可能希望某些设备最后接收更新，而其他设备希望先接收更新。 若要将这些设备移动到相应的更新组，请参阅将 [设备分配到部署组](../working-with-managed-desktop/assign-deployment-group.md)。

有关这些部署组内的角色和职责详细信息，请参阅Microsoft 托管桌面[角色和职责](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>使用Microsoft 托管桌面更新组 
你可以管理一些服务部分，如应用部署，其中可能需要面向所有托管设备。

## <a name="how-update-deployment-works"></a>更新部署的工作原理：
1. Microsoft 托管桌面根据下表中指定的计划部署新功能或质量更新。
2. 部署期间，Microsoft 托管桌面诊断数据和用户支持系统监视故障或中断的迹象。 如果检测到任何组，我们会立即将部署暂停到所有当前组和未来组。
    - 示例：如果在将质量更新部署到第一个组时发现问题，则更新到 First、Fast 和 Broad 的部署将全部暂停，直到问题得到缓解。
    - 可以通过在管理门户中提交票证来Microsoft 托管桌面兼容性问题。
    - 功能和质量更新独立暂停。 默认情况下，暂停生效 35 天，但可以减小或延长，具体取决于问题是否得到缓解。
3. 取消对组暂停后，将按照表中的计划恢复部署。
4. 用户可以响应设置时段的重启通知 (称为截止时间，从向设备) 提供更新的时间开始计算，在此期间设备仅在使用时段外自动重启。 此期限到期后，将到达截止时间，设备将在下一次可用机会时重启，而不考虑使用时段。 质量更新的截止时间为三天;对于功能更新，需要 5 天。

虽然每个更新的时间线各不相同，但此部署过程适用于功能和质量更新。


<table>
    <tr><th colspan="5">更新部署设置</th></tr>
    <tr><th>更新类型</th><th>测试</th><th>First</th><th>快速</th><th>宽泛</th></tr>
    <tr><td>操作系统的质量更新</td><td>0 天</td><td>0 天</td><td>0 天</td><td>7 天</td></tr>
    <tr><td>操作系统的功能更新</td><td>0 天</td><td>30 天</td><td>60 天</td><td>90 天</td></tr>
    <tr><td>驱动程序/固件</td><td colspan="4">遵循质量更新计划</td></tr>
    <tr><td>防病毒定义</td><td colspan="4">通过每次扫描更新</td></tr>
    <tr><td>Microsoft 365 企业应用版</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">了解详细信息</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">了解详细信息</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">了解详细信息</a></td></tr>
</table>

>[!NOTE]
>这些延迟期是特意设计的，以确保所有用户都符合高安全性和性能标准。 此外，根据在所有 Microsoft 托管桌面 设备上收集的数据以及更新的不同范围和影响，Microsoft 托管桌面 保留临时修改任何和所有部署组的上述延迟期长度的灵活性。
>
>Microsoft 托管桌面针对每个功能版本Windows独立评估，以评估其管理租户的必要性和实用性。 因此，Microsoft 托管桌面部署所有功能更新Windows部署。 

## <a name="windows-insider-program"></a>Windows 预览体验计划

Microsoft 托管桌面不支持属于预览体验计划Windows的设备。 预览Windows计划用于验证预发布Windows软件，适用于非关键任务的设备。 虽然这是一个重要的 Microsoft 计划，但它不适合在生产环境中广泛部署。 

使用预览体验成员Windows发现的任何设备都可能会放入测试组，并且不会从更新服务级别协议和用户支持Microsoft 托管桌面。

## <a name="bandwidth-management"></a>带宽管理

我们将传递 [优化用于](/windows/deployment/update/waas-delivery-optimization) 所有操作系统和驱动程序更新。 传递优化通过从企业网络内的对等Windows更新服务最小化下载大小。
