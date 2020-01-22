---
title: 转到操作中心以查看并批准自动调查和修正任务
description: 使用操作中心查看有关自动调查的详细信息并批准挂起的操作
keywords: 操作中心, 威胁防护, 调查, 警报, 挂起, 自动, 检测
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 91f2ae9a9fef96a3fdfedf86481aa5f5f33cb724
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260210"
---
# <a name="go-to-the-action-center-to-view-remediation-actions"></a>转到操作中心以查看修正操作

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="a-single-pane-of-glass-experience"></a>“单窗格”体验

![操作中心](../images/air-actioncenter.png)

使用操作中心查看组织设备和邮箱中的当前和过去调查的结果。 根据威胁的类型和[最终结论](mtp-autoir-results.md#remediation-actions-following-automated-investigation)，自动执行修正操作，或者在组织的安全运营团队批准后执行修正操作。 所有修正操作（无论是待批准还是已批准的操作）都合并在操作中心内。 

操作中心提供任务的“单窗格”体验，例如：
- 批准挂起的修正操作；
- 查看已批准的修正操作的审核日志；以及
- 查看已完成的修正操作。

你的安全运营团队可以更有效地进行运营，因为操作中心提供了工作中的 Microsoft 威胁防护的全面视图。

## <a name="remediation-actions"></a>修正操作

下表列出了操作中心当前支持的修正操作： 

|终结点修正操作  |电子邮件修正操作  |
|---------|---------|
|隔离<br/>删除注册表项<br/>终止进程 <br/>停止服务 <br/>删除注册表项 <br/>禁用驱动程序 <br/>删除计划任务      |软删除电子邮件或群集<br/>阻止 URL（单击时）<br/>关闭外部邮件转发          |

## <a name="go-to-the-action-center"></a>转到操作中心

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在导航窗格中，选择“**操作中心**”。 

3. 在操作中心，你将看到两个选项卡：“**挂起**”和 **“历史记录**”。

    - “**挂起**”选项卡列出了需要由安全运营团队中的人员进行审查和批准才能继续的调查。 确保对此处看到的挂起项目进行审查并采取操作。

    - “**历史记录**”选项卡列出了自动执行的过去调查和修正操作。 可查看过去一天、一周、一个月或六个月的数据。

4. 若要仅显示想要查看的列，请选择“**自定义列**”。<br/>![Microsoft 威胁防护中的操作中心](../images/mtp-action-center.png)

5. 在列表中选择一个项目以查看有关调查的更多详细信息。 此时将打开调查详细信息视图。<br/>![调查详细信息](../images/mtp-air-investdetails.png)

    - 如果调查与电子邮件内容有关（例如，实体是邮箱），则将在 Office 365 安全与合规中心 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) 中打开调查详细信息。 

    - 如果调查涉及设备，则将在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 中打开调查详细信息。 


> [!TIP]
> 如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！ 请参阅[如何在 Microsoft 威胁防护中报告误报/负面的自动调查和响应（空中）功能](mtp-autoir-report-false-positives-negatives.md)。

## <a name="required-permissions-for-action-center-tasks"></a>操作中心任务所需的权限

若要批准或拒绝操作中心中挂起的操作，必须按下表所列的方式分配权限：

|修正操作 |所需角色和权限 |
|--|----|
|Microsoft Defender ATP 修正（设备） |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的**安全管理员**角色<br/>--- 或 ---<br/>在 Microsoft Defender ATP 中分配的**主动修正操作**角色 <br/> <br/> 若要了解详细信息，请参阅以下资源： <br/>- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [为基于角色的访问控制创建和管理角色 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP 修正（Office 内容和电子邮件）  |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的**安全管理员**角色<br/>--- 和 --- <br/>在 Office 365 安全与合规中心 ([https://protection.office.com](https://protection.office.com)) 中分配的**搜索和清除**角色 <br/><br/>**重要提示**：如果仅在 Office 365 安全与合规中心中分配了安全管理员角色，则将无法访问操作中心或 Microsoft 威胁防护功能。 必须在 Azure Active Directory 或 Microsoft 365 管理中心中分配安全管理员角色。 <br/><br/>若要了解详细信息，请参阅以下资源： <br/>- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Office 365 安全与合规中心的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> 在 Azure Active Directory 中分配了**全局管理员**角色的用户可以批准或拒绝操作中心中挂起的任何操作。 但是，作为最佳做法，你的组织应该限制分配全局管理员角色的人数。 对于操作中心权限，我们建议使用上面列出的**安全管理员**、**主动修正操作**以及**搜索和清除**角色。

## <a name="next-steps"></a>后续步骤 

- [深入了解 Microsoft 威胁防护中的事件](incidents-overview.md)
- [查看自动调查的结果](mtp-autoir-results.md)
- [了解 Microsoft 威胁防护中的搜寻](advanced-hunting-overview.md)

