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
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058419"
---
# <a name="manage-office-scripts-settings"></a>管理 Office 脚本设置

Office 脚本允许用户通过录制、编辑和运行 Excel 网页中的脚本来自动执行任务。 Office 脚本与 Power Automate 一起工作，用户通过使用 Excel Online (Business) 连接器对工作簿运行脚本。 Microsoft 365 管理员可以从 Microsoft 365 管理中心管理 Office 脚本设置。

## <a name="before-you-begin"></a>准备工作

- 若要管理 Office 脚本设置，您必须是全局管理员。有关详细信息，请参阅 [关于管理员角色](../add-users/about-admin-roles.md)。

- 确保贵组织中用户具有 Microsoft 365 或 Office 365 商业版或 EDU 计划的有效许可证，该计划包括对 Office 桌面应用（如以下计划之一）的访问权限：

    - Microsoft 365 商业标准版
    - Microsoft 365 商业应用版
    - Microsoft 365 企业应用版
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>管理 Office 脚本的可用性和脚本共享

1. 在 Microsoft 365 管理中心中，转到"设置 \> **组织设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务"</a>选项卡。

2. 选择 **Office 脚本**。

3. 默认情况下，Office 脚本已打开，您的组织中的每个人都可以访问和使用该功能并共享脚本。 若要为组织关闭 Office 脚本，请清除"允许用户在 **Excel 网页** 中自动执行任务"复选框。

4. 如果之前为组织关闭 Office 脚本，并且希望将其重新启用，请选择"允许用户在 **Excel** 网页中自动执行任务"，然后指定可以访问和使用该功能的用户：

    - 若要允许您组织中所有用户访问和使用 Office 脚本，请保留"任何人 (默认) 选中。

    - 若要仅允许特定组的成员访问和使用 Office 脚本，请选择"特定组"，然后输入该组的名称或电子邮件别名以将其添加到允许列表中。 只能将一个组添加到允许列表中，并且它必须是以下类型之一：
        - Microsoft 365 组
        - 通讯组
        - 安全组
        - 启用邮件的安全组
    
        若要详细了解不同类型的组，请参阅["比较组"。](../create-groups/compare-groups.md)

5. 若要允许有权访问 Office 脚本的用户与组织中其他人共享其脚本，请选择"允许有权访问 Office 脚本的用户与组织其他人共享其 **脚本"。** 不允许在组织外部共享脚本。
 
    > [!NOTE]
    > 如果稍后为组织关闭脚本共享，用户仍可运行以前共享的脚本。
 
6. 指定有权访问 Office 脚本的用户可以共享其脚本：
    
    - 若要允许有权访问 Office 脚本的所有用户共享其脚本，请保留"任何人 (默认) 选中。

    - 若要仅允许具有 Office 脚本访问权限的特定组的成员共享其脚本，请选择"特定组"，然后输入组的名称或电子邮件别名以将其添加到允许列表中。 只能将一个组添加到允许列表中，并且它必须是以下类型之一：
        - Microsoft 365 组
        - 通讯组
        - 安全组
        - 启用邮件的安全组
    
        若要详细了解不同类型的组，请参阅["比较组"。](../create-groups/compare-groups.md)

7. 若要允许用户在 Power Automate 流中运行其 Office 脚本，请选择"允许有权访问 Office 脚本的用户使用 **Power Automate 运行其脚本"。** 这允许用户使用 Excel Online ([Business) 连接器的](/connectors/excelonlinebusiness)**"** 运行"脚本选项添加流步骤。

    - 若要允许有权访问 Office 脚本的所有用户在流中使用其脚本，请保留"任何人 (默认) 选中。

    - 若要仅允许具有 Office 脚本访问权限的特定组的成员在流中使用其脚本，请选择"特定组"，然后输入该组的名称或电子邮件别名以将其添加到允许列表中。 只能将一个组添加到允许列表中，并且必须是以下类型之一：
        - Microsoft 365 组
        - 通讯组
        - 安全组
        - 启用邮件的安全组

        若要详细了解不同类型的组，请参阅["比较组"。](../create-groups/compare-groups.md)

    - 若要了解有关将 Office 脚本与 Power Automate 一同使用（包括数据丢失防护策略可能受到影响）的更多信息，请参阅"使用 Power Automate 运行[Office 脚本"。](/office/dev/scripts/develop/power-automate-integration)

8. 选择“**保存**”。

    更改 Office 脚本设置最多可能需要 48 小时才能生效。

## <a name="next-steps"></a>后续步骤

由于 Office 脚本与 Power Automate 一起工作，因此建议您查看现有的数据丢失防护 (DLP) 策略，以确保组织的数据在用户使用 Office 脚本时保持受保护状态。 有关详细信息，请参阅 DLP 策略 [ (数据丢失) 保护](/power-automate/prevent-data-loss)。

## <a name="related-content"></a>相关内容

[Office 脚本技术文档 (](/office/dev/scripts/) 链接页) \
[Excel 中 Office 脚本](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) 简介 (文章) \
[在 Excel 中共享 Office 脚本网页](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (文章) \
[记录、编辑和创建 Excel](/office/dev/scripts/tutorials/excel-tutorial) 网页中的 Office 脚本 (文章) 
