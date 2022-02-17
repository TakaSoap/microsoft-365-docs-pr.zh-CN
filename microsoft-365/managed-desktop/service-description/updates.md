---
title: 如何处理更新Microsoft 托管桌面
description: 保持Microsoft 托管桌面是速度和稳定性的平衡。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e696f1b89cf03bbd4123252ea967e2aca10ef49
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879248"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>如何处理更新Microsoft 托管桌面

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft 托管桌面设备连接到基于云的现代基础结构。

保持Windows、Office、驱动程序、固件适用于企业的 Microsoft Store应用程序是速度和稳定性的平衡。 我们使用更新组来确保以安全方式推出操作系统更新和策略。 有关详细信息，请参阅更改和Microsoft 托管桌面[过程的视频](https://www.microsoft.com/videoplayer/embed/RE4mWqP)。

Microsoft 发布的更新是累积更新，并归类为质量更新或功能更新。 有关详细信息，请参阅 Windows [更新企业：更新类型](/windows/deployment/update/waas-manage-updates-wufb#update-types)。

## <a name="update-groups"></a>更新组

Microsoft 托管桌面四个Azure AD组来管理更新：

| Group | 说明 |
| ------ | ------ |
| 测试 | 用于验证Microsoft 托管桌面策略更改、操作系统更新、功能更新以及推送到 Azure AD 组织的其他更改 ("租户") 。 测试组为： <ul><li>最适合测试或可以提供早期反馈的用户。</li><li>从任何已建立的服务级别协议和用户支持中排除。</li><li>可用于验证应用程序与新策略或操作系统更改的兼容性。</li></ul> |
| First | 包含早期软件采用者以及可能受预发布更新限制的设备。 <br><br> 如果测试圈中的测试期间未涵盖的方案，则此组的设备可能会遇到中断。 |
| 快速 | 将速度优先于稳定性。 Fast 组为： <ul><li>用于检测质量问题，然后再提供给广泛组。</li> <li>下一层验证，通常比 Test 和 First 组更加稳定。</li></ul> |
| 宽泛 | 此组是最后一个提供功能和质量更新的组。 <br><br> Broad 组包含组织中大多数Azure AD，因此支持部署速度的稳定性。 应对此组执行应用测试，因为环境是最稳定的。 |

### <a name="moving-devices-between-update-groups"></a>在更新组之间移动设备

你可能希望某些设备最后接收更新，而其他设备希望先接收更新。 若要将这些设备移动到相应的更新组，请参阅将 [设备分配到部署组](../working-with-managed-desktop/assign-deployment-group.md)。

有关这些部署组内的角色和职责详细信息，请参阅Microsoft 托管桌面[角色和职责](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>使用Microsoft 托管桌面更新组

你可以管理一些服务部分，如应用部署，其中可能需要面向所有托管设备。

## <a name="update-deployment"></a>更新部署

下面介绍了更新部署的工作原理。

| 步骤 | 说明 |
| ------ | ------ |
| 第 1 步 | Microsoft 托管桌面根据下表中指定的计划部署新功能或质量更新。|
| 第 2 步 | 部署期间，Microsoft 托管桌面诊断数据和用户支持系统监视故障或中断的迹象。 如果检测到任何组，我们会立即将部署暂停到所有当前组和未来组。<br><br> 例如，如果在将质量更新部署到第一组时发现问题，则更新到 First、Fast 和 Broad 组的部署将暂停，直到问题得到缓解。 <br><br> 可以通过在管理门户中提交票证来Microsoft 托管桌面兼容性问题。 <br><br> 功能和质量更新独立暂停。 默认情况下，暂停生效 35 天。 但是，可以减小或扩展它，具体取决于问题是否得到缓解。 |
| 第 3 步 | 取消对组暂停后，将按照表中的计划恢复部署。 |
| 第 4 步| 用户可以在设置的时段内响应重启通知。 此期限称为截止时间，它从向设备提供更新的时间开始计算。 <br><br> 在此期间，设备将仅在使用时段外自动重启。 此期限到期后，将到达截止时间，设备将在下一次可用机会时重启，而不考虑使用时段。 <br><br> 质量更新的截止时间为三天;对于功能更新，需要 5 天。 |

> [!NOTE]
> 虽然每个更新的时间线各不相同，但此部署过程适用于功能和质量更新。

## <a name="deployment-settings"></a>部署设置

更新下面列出的部署设置：

| 更新类型 | 测试 | First | 快速 | 宽泛 |
| ------ | ------ | ------ | ------ | ------ |
| 操作系统的质量更新 | 零天 | 零天 | 零天 | 七天 |
| 操作系统的功能更新 | 零天 | 30 天 | 60 天 | 90 天 |
| 驱动程序/固件 | 遵循质量更新计划。 | 遵循质量更新计划。 | 遵循质量更新计划。 | 遵循质量更新计划。 |
| 防病毒定义 | 通过每次扫描进行更新。 | 通过每次扫描进行更新。 | 通过每次扫描进行更新。 | 通过每次扫描进行更新。 |
| Microsoft 365 企业应用版 | [了解更多](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [了解详细信息](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [了解详细信息](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [了解详细信息](../get-started/m365-apps.md#updates-to-microsoft-365-apps) |
| Microsoft Edge | [了解详细信息](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [了解详细信息](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [了解详细信息](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [了解详细信息](../get-started/edge-browser-app.md#updates-to-microsoft-edge) |
| Microsoft Teams | [了解详细信息](../get-started/teams.md#updates) | [了解详细信息](../get-started/teams.md#updates) | [了解详细信息](../get-started/teams.md#updates) | [了解详细信息](../get-started/teams.md#updates) |

>[!NOTE]
>这些延迟期是特意设计的，以确保所有用户都符合高安全性和性能标准。<br><br> 根据在所有 Microsoft 托管桌面 设备上收集的数据以及更新的不同范围和影响，Microsoft 托管桌面 保留灵活性，可以临时修改任何和所有部署组的上述延迟期的长度。
>
>Microsoft 托管桌面针对每个托管租户Windows独立评估功能版本，以评估其的必要性和实用性。 因此，Microsoft 托管桌面部署所有功能更新Windows部署。

## <a name="windows-insider-program"></a>Windows 预览体验计划

Microsoft 托管桌面不支持属于预览体验成员计划Windows的设备。

预览Windows计划用于验证预发布Windows软件。 它适用于不是任务关键型的设备。 虽然这是一个重要的 Microsoft 计划，但它不适合在生产环境中广泛部署。

使用预览体验成员Windows发现的任何设备都可能会放入"测试"组中。 这些设备将免于更新服务级别协议和用户支持，Microsoft 托管桌面。

## <a name="bandwidth-management"></a>带宽管理

我们将传递 [优化用于](/windows/deployment/update/waas-delivery-optimization) 所有操作系统和驱动程序更新。 传递优化通过从企业网络内的对等Windows更新服务最小化下载大小。
