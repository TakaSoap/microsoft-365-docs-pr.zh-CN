---
title: 转到操作中心以查看并批准自动调查和修正任务
description: 使用操作中心查看有关自动调查的详细信息并批准挂起的操作
keywords: 操作中心, 威胁防护, 调查, 警报, 挂起, 自动, 检测
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: aa9f433bc60949aa625d9346421b025121347a2c
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683315"
---
# <a name="the-action-center"></a>操作中心

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

使用操作中心 () 查看组织中设备和邮箱中当前和过去的 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 调查的结果。 根据威胁的类型和结果裁定，可自动执行[](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)修正操作，也可在组织的安全运营团队批准后执行修正操作。 所有修正操作（无论是待批准还是已批准的操作）都合并在操作中心内。 

![操作中心](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>“单窗格”体验

操作中心提供任务的“单窗格”体验，例如：
- 批准挂起的修正操作；
- 查看已批准的修正操作的审核日志；以及
- 查看已完成的修正操作。

你的安全运营团队可以更高效地操作，因为操作中心提供了 Microsoft 365 Defender 工作的全面视图。

## <a name="go-to-the-action-center"></a>转到操作中心

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在“导航”窗格中，选择“操作中心”。 

3. 在操作中心，你将看到两个选项卡：**挂起和****历史记录**。

    - “**挂起**”选项卡列出了需要由安全运营团队中的人员进行审查和批准才能继续的调查。 确保对此处看到的挂起项目进行审查并采取操作。

    - “**历史记录**”选项卡列出了自动执行的过去调查和修正操作。 可查看过去一天、一周、一个月或六个月的数据。

4. 若要仅显示想要查看的列，请选择“**自定义列**”。<br/>![Microsoft 365 Defender 中的操作中心](../../media/mtp-action-center.png)

5. 在列表中选择一个项目以查看有关调查的更多详细信息。 此时将打开调查详细信息视图。<br/>![调查详细信息](../../media/mtp-air-investdetails.png)

    - 如果调查与电子邮件内容 (，例如，实体是邮箱) ，调查详细信息在安全与合规&中心 [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) () 。 

    - 如果调查涉及设备，则将在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 中打开调查详细信息。 

> [!TIP]
> 如果认为 Microsoft 365 Defender 中的自动调查和响应功能遗漏或检测错误，请告诉我们！ 请参阅 [如何在 Microsoft 365](mtp-autoir-report-false-positives-negatives.md)Defender 中的 AIR (功能中的自动调查和响应) 误报/负数。

## <a name="available-actions"></a>可用操作

在采取修正操作时，它们列在操作中心的"历史记录"选项卡上。 此类操作包括：

- 收集调查包 
- 隔离设备 (此操作可以撤消)  
- 载出计算机 
- 发布代码执行 
- 解除隔离 
- 请求示例 
- 限制代码 (此操作可以撤消)  
- 运行防病毒扫描 
- 停止和隔离 

> [!NOTE]
> 除了自动采取的修正操作外，安全运营团队还可以执行手动操作来解决检测到的威胁。 有关自动和手动修正操作详细信息，请参阅 [修正操作](mtp-remediation-actions.md)。

## <a name="action-source"></a>操作源

 (**新增功能！) ，** 正如你所知，Microsoft 365 Defender 将跨多个服务（如 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 和 Microsoft Defender [for Office 365）](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)的自动调查和响应功能汇集在一起。 新的和改进的操作中心现在包括一 **个操作源** 列，可告知您每个修正操作的来源。 

下表描述了可能 **的操作源** 值：

| 操作源值 | 说明 |
|:-----|:---|
| **手动设备操作** | 对设备执行手动操作。 示例包括 [设备隔离](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) 或 [文件隔离](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files)。 |
| **手动电子邮件操作** | 对电子邮件执行手动操作。 示例包括软删除电子邮件 [或修正电子邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365)。 |
| **自动设备操作** | 对实体（如文件或进程）采取的自动操作。 自动操作的示例包括将文件发送到隔离区、停止进程和删除注册表项。  (Microsoft [Defender for Endpoint .) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions) |
| **自动电子邮件操作** | 对电子邮件内容（如电子邮件、附件或 URL）执行自动操作。 自动操作的示例包括软删除电子邮件、阻止 URL 和关闭外部邮件转发。  (Microsoft [Defender for Office 365 .) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions) |
| **高级搜寻操作** | 使用高级搜寻对设备或电子邮件 [采取的操作](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)。 |
| **资源管理器操作** | 使用资源管理器对电子邮件内容 [采取的操作](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)。 |
| **手动实时响应操作** | 使用实时响应对设备 [采取的操作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。 示例包括删除文件、停止进程和删除计划任务。 |
| **实时响应操作** | 使用 Microsoft Defender [for Endpoint API 对设备采取的操作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)。 操作示例包括隔离设备、运行防病毒扫描和获取有关文件的信息。 |

## <a name="required-permissions-for-action-center-tasks"></a>操作中心任务所需的权限

若要批准或拒绝操作中心中挂起的操作，必须按下表所列的方式分配权限：

|修正操作 |所需角色和权限 |
|--|----|
|适用于终结点的 Microsoft Defender (设备)  |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的安全管理员角色<br/>--- 或 ---<br/>在 Microsoft Defender for Endpoint 中分配的活动修正操作角色 <br/> <br/> 若要了解详细信息，请参阅以下资源： <br/>- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [使用 Microsoft Defender for Endpoint (创建和管理基于角色的访问控制) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Microsoft Defender for Office 365 修正 (Office 内容和电子邮件)   |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的安全管理员角色<br/>--- 和 --- <br/>为安全与合规中心&搜索和清除 [https://protection.office.com](https://protection.office.com) ()  <br/><br/>**重要** 提示：如果你仅在安全与合规中心分配了安全管理员角色&，你将无法访问操作中心或 Microsoft 365 Defender 功能。 必须在 Azure Active Directory 或 Microsoft 365 管理中心中分配安全管理员角色。 <br/><br/>若要了解详细信息，请参阅以下资源： <br/>- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [安全与合规&中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> 在 Azure Active Directory 中分配了全局管理员角色的用户可以批准或拒绝操作中心中挂起的任何操作。 但是，作为最佳做法，你的组织应该限制分配全局管理员角色的人数。 对于操作中心权限，我们建议使用上面列出的安全管理员、主动修正操作以及搜索和清除角色。

## <a name="next-steps"></a>后续步骤 

- [批准或拒绝自动调查后挂起的操作](mtp-autoir-actions.md)
- [查看自动调查的结果](mtp-autoir-results.md)

