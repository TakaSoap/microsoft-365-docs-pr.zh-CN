---
title: 转到操作中心以查看并批准自动调查和修正任务
description: 使用操作中心查看有关自动调查的详细信息并批准挂起的操作
keywords: 操作中心， 威胁防护， 调查， 警报， 挂起， 自动， 检测
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: b64cbc55a975ee02bd1bd5d41d30330e8729d4be
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329567"
---
# <a name="the-action-center"></a>操作中心

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

操作中心为事件和警报任务提供了"单窗格"体验，例如：

- 批准挂起的修正操作。
- 查看审核日志修正操作的内容。
- 查看已完成的修正操作。

由于操作中心提供了有关工作Microsoft 365 Defender视图，因此安全运营团队可以更高效地操作。

## <a name="the-unified-action-center"></a>统一操作中心

统一操作中心 () [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 一个位置列出设备、电子邮件&协作内容和标识的挂起和已完成的修正操作。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="统一操作中心Microsoft 365 Defender门户。" lightbox="../../media/m3d-action-center-unified.png":::

例如： 

- 如果之前使用的是安全Office 365合规[https://protection.office.com](https://protection.office.com)&中心 () ，请尝试在 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中统一操作中心</a>。
- 如果使用的是 Microsoft Defender 安全中心 () [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) 中的操作中心，请尝试在 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中。</a>
- 如果你已在使用 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>，你将[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)在操作中心 () 。

统一操作中心将跨 Defender for Endpoint 和 Defender for Office 365。 它定义所有修正操作的共同语言，并提供统一的调查体验。 安全运营团队具有"单窗格"体验，可查看和管理修正操作。  

如果您具有适当的权限以及以下一个或多个订阅，可以使用统一操作中心：

- [Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> 若要了解更多信息，请参阅 [要求](./prerequisites.md)。

## <a name="using-the-action-center"></a>使用操作中心

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender并</a>登录。 
2. 在“导航”窗格中，选择“操作中心”。 

访问操作中心时，会看到两个选项卡：" **挂起的操作"和** " **历史记录"**。 下表总结了您将在每个选项卡上看到的内容：

|Tab  |说明  |
|---------|---------|
|**Pending**     | 显示需要关注的操作的列表。 可以一次批准或拒绝一个操作，也可以选择多个操作（如果他们的操作类型与隔离文件 (隔离文件) 。 <p>**提示**：确保尽快审阅 (批准或拒绝) 挂起的操作，以便可以及时完成自动调查。       |
|**历史记录**     | 充当审核日志的操作的一个组，例如： <br/>- 由于自动调查而采取的修正操作 <br/>- 对可疑或恶意电子邮件、文件或 URL 采取的修正操作<br/>- 安全运营团队批准的修正操作 <br/>- 运行的命令和在实时响应会话期间应用的修正操作<br/>- 防病毒保护采取的修正操作 <p>提供了一种撤消某些操作 (请参阅 [Undo completed actions) ](m365d-autoir-actions.md#undo-completed-actions) 。        |

可以在操作中心中自定义、排序、筛选和导出数据。

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="操作中心的排序、筛选和自定义功能。" lightbox="../../media/m3d-action-center-columnsfilters.png":::

- 选择列标题以按升序或降序对项目进行排序。
- 使用时间段筛选器查看过去一天、一周、30 天或 6 个月的数据。
- 选择要查看的列。
- 指定要包含在每个数据页上的项目数。
- 使用筛选器仅查看要查看的项目。
- 选择 **"** 导出"将结果导出到.csv文件。

## <a name="actions-tracked-in-the-action-center"></a>操作中心中跟踪的操作

所有修正操作（无论是待批准还是已批准的操作）都可在操作中心跟踪。 可用操作包括：

- 收集调查程序包 
- 隔离设备 (可以撤消此操作)  
- 卸载计算机 
- 释放代码执行 
- 从隔离区中释放 
- 请求示例 
- 限制代码 (可以撤消此操作)  
- 运行防病毒扫描 
- 停止和隔离 

除了自动调查后自动采取的修正操作之外，操作中心还[](m365d-autoir.md)跟踪安全团队为应对检测到的威胁而采取的操作，以及由于 Microsoft 365 Defender 中的威胁防护功能而采取的操作。 有关自动和手动修正操作详细信息，请参阅 [修正操作](m365d-remediation-actions.md)。

## <a name="viewing-action-source-details"></a>查看操作源详细信息

 (**新建！**) 改进的操作中心现在包括一个 **操作** 源列，告知你每个操作的来源。 下表介绍了可能 **的操作源** 值：

| 操作源值 | 说明 |
|:-----|:---|
| **手动设备操作** | 对设备采取的手动操作。 示例包括 [设备隔离](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) 或 [文件隔离](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files)。 |
| **手动电子邮件操作** | 对电子邮件执行手动操作。 示例包括软删除电子邮件 [或修正电子邮件](../office-365-security/remediate-malicious-email-delivered-office-365.md)。 |
| **自动设备操作** | 对实体（如文件或进程）采取的自动操作。 自动操作的示例包括将文件发送到隔离区、停止进程和删除注册表项。  (请参阅 [Microsoft Defender for Endpoint.) ](../defender-endpoint/manage-auto-investigation.md#remediation-actions) |
| **自动电子邮件操作** | 对电子邮件内容（如电子邮件、附件或 URL）采取的自动操作。 自动操作的示例包括软删除电子邮件、阻止 URL 和关闭外部邮件转发。  (请参阅 [Microsoft Defender for Office 365.) ](../office-365-security/air-remediation-actions.md) 中的修正操作 |
| **高级搜寻操作** | 使用高级搜寻对设备或电子邮件 [采取的操作](./advanced-hunting-overview.md)。 |
| **资源管理器操作** | 使用资源管理器对电子邮件内容 [采取的操作](../office-365-security/threat-explorer.md)。 |
| **手动实时响应操作** | 使用实时响应对设备 [采取的操作](../defender-endpoint/live-response.md)。 示例包括删除文件、停止进程和删除计划任务。 |
| **实时响应操作** | 使用 [Microsoft Defender for Endpoint API 对设备采取的操作](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)。 操作示例包括隔离设备、运行防病毒扫描和获取文件信息。 |

## <a name="required-permissions-for-action-center-tasks"></a>操作中心任务所需的权限

若要执行任务，如在操作中心批准或拒绝挂起的操作，必须分配如下表所列权限：

|修正操作 |所需角色和权限 |
|--|----|
|Microsoft Defender for Endpoint 修正 (设备)  |**安全管理员** 角色分配在 Azure Active Directory (Azure AD)  () [https://portal.azure.com](https://portal.azure.com) 或 [https://admin.microsoft.com](https://admin.microsoft.com) Microsoft 365 管理中心 () <br/>--- 或 ---<br/>**在 Microsoft** Defender for Endpoint 中分配的活动修正操作角色 <br/> <br/> 若要了解详细信息，请参阅以下资源： <br/>- [Azure AD内置角色](/azure/active-directory/roles/permissions-reference)<br/>- [使用 Microsoft Defender for Endpoint (创建和管理基于角色的访问控制) ](../defender-endpoint/user-roles.md)  |
|Microsoft Defender for Office 365修正 (Office内容和电子邮件)   |**安全管理员** 角色分配在 Azure AD () [https://portal.azure.com](https://portal.azure.com) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>--- 和 --- <br/>**在安全与** 合规中心&分配搜索和清除 () [https://protection.office.com](https://protection.office.com) <br/><br/>**重要** 提示：如果仅在 Office 365  安全与合规中心 & [https://protection.office.com](https://protection.office.com) () 中分配了安全管理员角色，则无法访问操作中心或 Microsoft 365 Defender 功能。 您必须 **在安全管理** 角色或Azure AD分配安全Microsoft 365 管理中心。 <br/><br/>若要了解详细信息，请参阅以下资源： <br/>- [Azure AD内置角色](/azure/active-directory/roles/permissions-reference)<br/>- [安全与合规&中的权限](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> 在操作中心 **中** 分配了全局管理员角色Azure AD可以批准或拒绝操作中心中任何挂起的操作。 但是，最佳做法是，贵组织应限制分配了全局管理员 **角色的人的数量** 。 对于 **操作中心权限**，我们建议使用上表中列出的安全管理员、活动修正操作和搜索和清除角色。

## <a name="next-step"></a>后续步骤 

- [查看和管理修正操作](m365d-autoir-actions.md)
