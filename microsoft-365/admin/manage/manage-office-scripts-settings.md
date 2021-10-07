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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: 了解如何为Office用户管理脚本设置。
ms.openlocfilehash: f03ee34e0ff41c3eb082beca79127cd609496564
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168034"
---
# <a name="manage-office-scripts-settings"></a>管理 Office 脚本设置

[Office脚本](/office/dev/scripts)允许用户通过录制、编辑和运行脚本来自动执行任务Excel web 版。 Office脚本适用于Power Automate，用户通过使用 Excel Online (Business) 连接器对工作簿运行脚本。 Microsoft 365管理员可以从Office管理脚本Microsoft 365 管理中心。

## <a name="before-you-begin"></a>准备工作

- 若要管理Office脚本设置，你必须是全局管理员。有关详细信息，请参阅关于[管理员角色](../add-users/about-admin-roles.md)。

- 确保贵组织的用户拥有对 Microsoft 365 或 Office 365 商业或 EDU 计划的有效许可证，该计划包括对 Office 桌面应用的访问权限，如以下计划之一：

- Microsoft 365 商业标准版
- Microsoft 365 商业应用版
- Microsoft 365 企业应用版
- Office 365 E3
- Office 365 E5
- Office 365 A3
- Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>管理脚本Office和脚本共享的可用性

1. In the Microsoft 365 管理中心， go to the **设置** \> **Org settings** \> **[Services](https://go.microsoft.com/fwlink/p/?linkid=2053743)** tab.

2. 选择 **Office脚本"。**

3. Office默认情况下，脚本已打开，并且您组织中的每个人都可以访问和使用该功能并共享脚本。 若要关闭Office脚本，请清除"允许用户在脚本中自动Excel web 版 **任务"** 复选框。

4. 如果之前为组织关闭 Office 脚本，并且希望将其重新启用，请选择"允许用户在 Excel web 版 中自动执行任务 **"，** 然后指定可以访问和使用该功能的用户：

    - 若要允许组织中所有用户访问和使用脚本，Office"默认 ("") "。 

    - 若要仅允许特定组的成员访问和使用 Office Scripts，请选择"特定组"，然后输入组的名称或电子邮件别名以将其添加到允许列表。 只能将一个组添加到允许列表，并且必须是以下类型之一：
        - Microsoft 365组
        - 通讯组
        - 安全组
        - 启用邮件的安全组

        若要详细了解不同类型的组，请参阅比较 [组](../create-groups/compare-groups.md)。

5. 若要允许有权访问 Office 脚本的用户与组织中的其他人共享其脚本，请选择"允许有权访问 Office 脚本的用户与组织中的其他人共享其 **脚本"。** 不允许在组织外部共享脚本。

    > [!NOTE]
    > 如果稍后为组织关闭脚本共享，用户仍可运行以前共享的脚本。

6. 指定有权访问脚本Office哪些用户可以共享其脚本：

    - 若要允许有权访问脚本的Office共享其脚本，请保留"任何人 (默认设置) 选中。

    - 若要仅允许有权访问 Office Scripts 的特定组的成员共享其脚本，请选择"特定组"，然后输入组的名称或电子邮件别名以将其添加到允许列表中。 只能将一个组添加到允许列表，并且必须是以下类型之一：
        - Microsoft 365组
        - 通讯组
        - 安全组
        - 启用邮件的安全组

        若要详细了解不同类型的组，请参阅比较 [组](../create-groups/compare-groups.md)。

7. 若要允许用户在脚本流Office脚本Power Automate，请选择"允许有权访问 Office 脚本的用户使用 Power Automate **运行** Power Automate" 。 这允许用户使用 Excel [Online (Business) Connector 的](/connectors/excelonlinebusiness)**运行** 脚本选项添加流步骤。

    - 若要允许有权访问脚本的Office在流中使用其脚本，请保留"任何人 ("默认) 选中。

    - 若要仅允许具有 Office 脚本访问权限的特定组的成员在流中使用其脚本，请选择"特定组"，然后输入组的名称或电子邮件别名以将其添加到允许列表中。 只能将一个组添加到允许列表，并且必须是以下类型之一：
        - Microsoft 365组
        - 通讯组
        - 安全组
        - 启用邮件的安全组

        若要详细了解不同类型的组，请参阅比较 [组](../create-groups/compare-groups.md)。

    - 若要了解有关将脚本与 Office 一Power Automate，请参阅 Run Office [Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration)。

8. 选择“**保存**”。

    对 Office 脚本设置的更改最多可能需要 48 小时才能生效。

## <a name="next-steps"></a>后续步骤

由于Office脚本适用于 Power Automate，因此建议您查看现有的数据丢失防护 (DLP) 策略，以确保在用户使用 Office Scripts 时，组织的数据仍然受到保护。 有关详细信息，请参阅[数据丢失防护 (DLP) 策略](/power-automate/prevent-data-loss)。

## <a name="related-content"></a>相关内容

[Office脚本技术文档 (](/office/dev/scripts/)链接页) \
[Office中Excel (](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a)脚本) \
[在 Office Web Excel 中共享 (](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)脚本) \
[记录、编辑和创建Office脚本Excel web 版 (](/office/dev/scripts/tutorials/excel-tutorial)文章) 
