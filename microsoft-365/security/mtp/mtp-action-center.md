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
ms.date: 09/16/2020
ms.openlocfilehash: 3ec17204903f3e83f3fbfd126d57d0b9ca5d56f7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843788"
---
# <a name="the-action-center"></a>操作中心

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

使用操作中心查看组织设备和邮箱中的当前和过去调查的结果。 根据威胁的类型和得到的结论，将自动执行 [更正操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) ，或在组织的安全操作团队批准时执行。 所有修正操作（无论是待批准还是已批准的操作）都合并在操作中心内。 

![操作中心](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>“单窗格”体验

操作中心提供任务的“单窗格”体验，例如：
- 批准挂起的修正操作；
- 查看已批准的修正操作的审核日志；以及
- 查看已完成的修正操作。

您的安全操作团队可以更有效地运营，因为操作中心提供了 Microsoft 365 Defender 在工作中的全面视图。

## <a name="go-to-the-action-center"></a>转到操作中心

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在“导航”窗格中，选择“操作中心”。 

3. 在操作中心中，您将看到两个选项卡： **挂起** 和 **历史记录** 。

    - “ **挂起** ”选项卡列出了需要由安全运营团队中的人员进行审查和批准才能继续的调查。 确保对此处看到的挂起项目进行审查并采取操作。

    - “ **历史记录** ”选项卡列出了自动执行的过去调查和修正操作。 可查看过去一天、一周、一个月或六个月的数据。

4. 若要仅显示想要查看的列，请选择“ **自定义列** ”。<br/>![Microsoft 365 Defender 中的操作中心](../../media/mtp-action-center.png)

5. 在列表中选择一个项目以查看有关调查的更多详细信息。 此时将打开调查详细信息视图。<br/>![调查详细信息](../../media/mtp-air-investdetails.png)

    - 如果调查与电子邮件内容有关 (例如，实体是邮箱) ，请在安全 & 合规性中心中打开调查详细信息 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) 。 

    - 如果调查涉及设备，则将在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 中打开调查详细信息。 

> [!TIP]
> 如果你认为在 Microsoft 365 Defender 中，自动调查和响应功能中缺少或错误地检测到了某些内容，请告诉我们！ 请参阅 [如何在自动调查和响应中报告误报/负面 (在 Microsoft 365 Defender 中的空中) 功能](mtp-autoir-report-false-positives-negatives.md)。

## <a name="available-actions"></a>可用操作

在采取补救措施时，它们将在操作中心的 "历史记录" 选项卡上列出。 此类操作包括以下内容：

- 收集调查包 
- 隔离设备 (可以撤消此操作)  
- 分离计算机 
- 释放代码执行 
- 从隔离区发布 
- 请求示例 
- 限制代码执行 (可以撤消此操作)  
- 运行防病毒扫描 
- 停止和隔离 

## <a name="required-permissions-for-action-center-tasks"></a>操作中心任务所需的权限

若要批准或拒绝操作中心中挂起的操作，必须按下表所列的方式分配权限：

|修正操作 |所需角色和权限 |
|--|----|
|Microsoft Defender for Endpoint 补救 (设备)  |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的安全管理员角色<br/>--- 或 ---<br/>在 Microsoft Defender for Endpoint 中分配的活动修正操作角色 <br/> <br/> 若要了解详细信息，请参阅以下资源： <br/>- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [为基于角色的访问控制创建和管理角色 (Microsoft Defender for Endpoint) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Microsoft Defender for Office 365 更新 (Office 内容和电子邮件)   |在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的安全管理员角色<br/>--- 和 --- <br/>搜索和清除为安全 & 合规性中心 () 分配的角色 [https://protection.office.com](https://protection.office.com) <br/><br/>**重要说明** ：如果您仅在安全 & 合规中心中分配安全管理员角色，您将无法访问操作中心或 Microsoft 365 Defender 功能。 必须在 Azure Active Directory 或 Microsoft 365 管理中心中分配安全管理员角色。 <br/><br/>若要了解详细信息，请参阅以下资源： <br/>- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [安全 & 合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> 在 Azure Active Directory 中分配了全局管理员角色的用户可以批准或拒绝操作中心中挂起的任何操作。 但是，作为最佳做法，你的组织应该限制分配全局管理员角色的人数。 对于操作中心权限，我们建议使用上面列出的安全管理员、主动修正操作以及搜索和清除角色。

## <a name="next-steps"></a>后续步骤 

- [在自动调查后批准或拒绝待处理的操作](mtp-autoir-actions.md)
- [查看自动调查的结果](mtp-autoir-results.md)

