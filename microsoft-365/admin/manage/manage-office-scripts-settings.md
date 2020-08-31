---
title: 管理 Office 脚本设置
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 了解如何管理组织中用户的 Office 脚本设置。
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300825"
---
# <a name="manage-office-scripts-settings"></a>管理 Office 脚本设置

通过 Office 脚本，用户可以通过在 web 上的 Excel 中录制、编辑和运行脚本来自动执行任务。 Office 脚本使用 Power 自动功能，并且用户通过使用 Excel Online (Business) 连接器在工作簿上运行脚本。 Microsoft 365 管理员可以从 Microsoft 365 管理中心管理 Office 脚本设置。

## <a name="before-you-begin"></a>准备工作

- 若要管理 Office 脚本设置，您必须是全局管理员。有关详细信息，请参阅 [关于管理员角色](../add-users/about-admin-roles.md)。

- 确保组织中的用户具有有效的 Microsoft 365 或 Office 365 商业版或 EDU 计划的许可证，包括对 Office 桌面应用程序的访问权限，例如以下计划之一：

    - Microsoft 365 商业标准版
    - Microsoft 365 商业应用版
    - Microsoft 365 企业应用版
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>管理 Office 脚本的可用性和脚本的共享

1. 在 Microsoft 365 管理中心，转到 " **设置** \> **组织设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务</a> " 选项卡。

2. 选择 " **Office 脚本**"。

3. 默认情况下，Office 脚本处于打开状态，组织中的所有人都可以访问和使用功能并共享脚本。 若要关闭组织的 Office 脚本，请清除 " **让用户在 Excel 中自动处理其任务"** 复选框。

4. 如果您以前关闭了组织的 Office 脚本，并且想要将其重新打开，请选择 **"让用户在 Excel 中自动执行其任务**"，然后指定可以访问和使用该功能的用户：

    - 若要允许组织中的所有用户访问和使用 Office 脚本，请让 **每个人** (选中默认) 。 

    - 若要仅允许特定组的成员访问和使用 Office 脚本，请选择 " **特定组**"，然后输入要将其添加到允许列表中的组的名称或电子邮件别名。 您只能将一个组添加到允许列表中，并且必须是以下类型之一：
        - Microsoft 365 组
        - 通讯组
        - 安全组
        - 启用邮件的安全组
    
        若要了解有关不同类型的组的详细信息，请参阅 [比较组](../create-groups/compare-groups.md)。

5. 若要允许有权访问 Office 脚本的用户与组织中的其他人共享其脚本，请选择 " **允许访问 Office 脚本的用户与组织中的其他人共享其脚本**。 不允许在组织外部共享脚本。
 
    > [!NOTE]
    > 如果稍后关闭组织的脚本共享，用户将仍能运行以前共享的脚本。
 
6. 指定有权访问 Office 脚本的用户可以共享其脚本：
    
    - 若要允许具有 Office 脚本访问权限的所有用户共享其脚本，请将 **每个人** (保留) 选择的默认值。

    - 若要仅允许具有 Office 脚本访问权限的特定组的成员共享其脚本，请选择 " **特定组**"，然后输入要将其添加到允许列表中的组的名称或电子邮件别名。 您只能将一个组添加到允许列表中，并且必须是以下类型之一：
        - Microsoft 365 组
        - 通讯组
        - 安全组
        - 启用邮件的安全组
    
        若要了解有关不同类型的组的详细信息，请参阅 [比较组](../create-groups/compare-groups.md)。

7. 选择“保存”****。

    最长可能需要48小时才能使 Office 脚本设置的更改生效。

## <a name="next-steps"></a>后续步骤

由于 Office 脚本与电源自动配合使用，因此我们建议您查看现有的数据丢失防护 (DLP) 策略，以确保组织的数据在用户使用 Office 脚本时保持受保护状态。 有关详细信息，请参阅 [数据丢失防护 (DLP) 策略](/power-automate/prevent-data-loss)。

## <a name="related-content"></a>相关内容

[Office 脚本技术文档](/office/dev/scripts/) (链接页面) \
Excel (文章) [中的 Office 脚本简介](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a)\
[在 Excel For Web 中共享 Office 脚本](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (文章) \
[在 Excel 的 web (文章) 中记录、编辑和创建 Office 脚本](/office/dev/scripts/tutorials/excel-tutorial)