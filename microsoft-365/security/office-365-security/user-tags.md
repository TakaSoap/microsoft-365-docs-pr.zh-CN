---
title: Microsoft Defender for Office 365 中的用户标记
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 计划 2 中标识具有用户标记的特定用户组。 标签筛选可用于 Microsoft Defender for Office 365 中的警报、报告和调查，以快速标识标记的用户。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed91492e652773b3a48373df49b20d97887df6ee
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931430"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的用户标记

> [!NOTE]
> 用户标记功能在预览版中，并非对所有人都可用，并且可能会更改。 有关发布计划的信息，请查看 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。

用户标记是 [Microsoft Defender for Office 365](office-365-atp.md)中特定用户组的标识符。 有两种类型的用户标记：

- **系统标记**：目前 [，优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 是唯一类型的系统标记。
- **自定义标记**：您自己创建这些用户标记。

如果你的组织将 Defender for Office 365 计划 2 (包含在订阅中或作为加载项) ，则除了使用优先级帐户标记外，还可以创建自定义用户标记。

向用户应用系统标记或自定义标记后，可以在警报、报告和调查中使用这些标记作为筛选器：

- [安全与合规中心&警报](alerts.md)
- [威胁资源管理器和实时检测](threat-explorer.md)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [市场活动视图](campaigns.md)
- 对于优先级帐户，可以使用 Exchange[](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)管理中心中的"优先级帐户的电子邮件问题"报告 (EAC) 。

本文介绍如何在安全与合规中心&标记。 安全与合规中心& cmdlet 管理用户标记。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到" **用户标记"** 页，请打开 <https://protection.office.com/userTags> 。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要创建、修改和删除用户标记，您必须是组织 **管理或****安全** 管理员角色组的成员。
  - 若要从现有用户标记中添加和删除成员，你需要是组织管理、**安全** 管理员或 **安全** 操作员角色组的成员
  - 若要对用户标记进行只读访问，你需要是全局读者或安全 **读者角色组** 的成员。 

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - 用户标记管理由 Tag **Reader、Tag** **Contributor** 和 **Tag Manager 角色** 控制。

- 还可以在 Microsoft 365 管理中心管理和监视优先级帐户。 有关说明，请参阅 [管理和监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。

## <a name="use-the-security-center-to-create-user-tags"></a>使用安全中心创建用户标记

1. 在安全中心，转到 **威胁管理** \> **用户标记**。

2. 在打开 **的用户标记** 页上，单击"**创建标记"。**

3. " **创建标记"** 向导将在新的飞出中打开。在" **定义标记"** 页上，配置以下设置：
   - **名称**：为标记输入唯一的描述性名称。 这是你将看到和使用的值。
   - **说明**：输入标记的可选说明。

   完成后，单击“下一步”。

4. 在 **"分配用户"** 页上，执行下列任一步骤：

   - 单击 **"添加用户"。** 在出现的"飞出"中，执行下列任一步骤以添加单个用户或组：
     - 在框中单击并滚动浏览列表以选择用户或组。
     - 在框中单击并开始键入以筛选列表并选择用户或组。
     - 若要添加其他值，请单击框中的空白区域。
     - 若要从框中删除单个条目，请单击框中用户或 ![ 组上的"删除 ](../../media/scc-remove-icon.png) "图标。
     - 若要从框下方的列表中删除现有条目，请单击 **"删除** ![ "图标 ](../../media/scc-remove-icon.png) 删除该条目。

     完成后，单击"添加 **"。**

   - 单击 **"** 导入"选择包含用户或组的电子邮件地址的文本文件。 确保文本文件每行包含一个条目。

   完成后，单击“下一步”。

5. 在" **审阅标记"** 页上，查看设置。 可以单击 **特定** 节中的"编辑"进行更改。

   完成后，单击"提交 **"。**

## <a name="use-the-security-center-to-view-user-tags"></a>使用安全中心查看用户标记

1. 在安全中心，转到 **威胁管理** \> **用户标记**。

2. 在打开 **的用户标记** 页上，选择要查看的用户标记 (不要单击复选框) 。

3. 在出现的只读详细信息飞出中，查看设置。

   完成后，单击“关闭”。

## <a name="use-the-security-center-to-modify-user-tags"></a>使用安全中心修改用户标记

1. 在安全中心，转到 **威胁管理** \> **用户标记**。

2. 在打开 **的用户标记** 页上，选择要查看的用户标记，然后单击"编辑 **"标记**。

3. 策略向导将在"编辑" **标记飞出时** 打开。单击 **"** 下一步"查看和修改设置。

   完成后，单击"提交 **"。**

## <a name="use-the-security-center-to-remove-user-tags"></a>使用安全中心删除用户标记

**注意**：不能删除内置优先级 **帐户** 标记。

1. 在安全中心，转到 **威胁管理** \> **用户标记**。

2. 在打开 **的用户标记** 页上，选择要删除的用户标记，单击"删除标记"，然后在出现的警告中选择"是，删除"。
