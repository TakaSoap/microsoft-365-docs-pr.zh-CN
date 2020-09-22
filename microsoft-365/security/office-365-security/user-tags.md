---
title: 用户标记
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Oiffce 365 ATP 计划2中识别具有用户标记的特定用户组。 标记筛选在 Office 365 ATP 中的通知、报告和调查中可用，以快速识别已标记的用户。
ms.openlocfilehash: d47c5c00e3cf0362c44aebc18d11db4bba68a149
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48210020"
---
# <a name="user-tags-in-the-microsoft-security-center"></a>Microsoft 安全中心中的用户标记

用户标记是 [Office 365 高级威胁防护 (ATP) ](office-365-atp.md)中的特定用户组的标识符。 [优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) 是一类用户标记。 如果您的组织具有 Office 365 ATP 计划 2 (包含在订阅中或作为加载项) ，除了使用优先级帐户标记之外，还可以创建自定义用户标记。

对特定用户应用标记后，可以将这些标记用作警报、报告和调查中的筛选器：

- [安全 & 合规中心中的警报](alerts.md)
- [威胁资源管理器和实时检测](threat-explorer.md)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [市场活动视图](campaigns.md)

本文介绍如何在安全中心中配置用户标记。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 你可以在上打开 "安全中心" <https://security.microsoft.com/> 。 若要直接转到 " **用户标记** " 页，请打开 <https://security.microsoft.com/securitysettings/userTags> 。

- 若要创建、修改或删除用户标记，您需要是安全 & 合规性中心中的 " **组织管理** " 或 " **安全管理员** " 角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

- 您还可以在 Microsoft 365 管理中心中管理和监视优先级帐户。 有关说明，请参阅 [管理和监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。

## <a name="use-the-security-center-to-create-user-tags"></a>使用安全中心创建用户标记

1. 在 "安全中心" 中，转到 " **设置** \> **电子邮件 & 协作** \> **用户标记**"。

2. 在打开的 " **用户标记** " 页上，单击 " **创建标记**"。

3. " **创建标记** " 向导将在新的飞出中打开。在 " **定义标记** " 页上，配置以下设置：

   - **名称**：为标记输入唯一的描述性名称。 这是你将看到和使用的值。

   - **说明**：输入标记的可选说明。

   完成后，单击“下一步”****。

4. 在 " **分配邮箱** " 页上，执行下列步骤之一：

   - 单击 " **添加邮箱**"。 在出现的 "飞出" 中，执行以下任一步骤添加单个用户或组：

     - 在框中单击，并在列表中滚动以选择用户或组。
     - 在框中单击，然后开始键入以筛选列表并选择用户或组。
     - 若要添加其他值，请单击框中的空白区域。
     - 若要从框中删除单个条目， **Remove**请 ![ ](../../media/scc-remove-icon.png) 在框中的用户或组上单击 "删除删除图标"。
     - 若要从框下方的列表中删除现有条目，请单击 " **删除** ![ 删除图标 ](../../media/scc-remove-icon.png) " 条目。

     完成后，请单击 " **添加**"。

   - 单击 " **导入** " 以选择包含用户或组的电子邮件地址的文本文件。 确保文本文件中每行包含一个条目。

   完成后，单击“下一步”****。

5. 在 " **查看标记** " 页上，查看您的设置。 您可以单击 "特定" 部分中的 " **编辑** " 来进行更改。

   完成后，请单击 " **提交**"。

## <a name="use-the-security-center-to-view-user-tags"></a>使用安全中心查看用户标记

1. 在 "安全中心" 中，转到 " **设置** \> **电子邮件 & 协作** \> **用户标记**"。

2. 在打开的 " **用户标记** " 页上，选择要查看的用户标记 (不要单击复选框) 。

3. 在出现的只读详细信息飞出中，查看设置。

   完成后，单击“关闭”****。

## <a name="use-the-security-center-to-modify-user-tags"></a>使用安全中心修改用户标记

1. 在 "安全中心" 中，转到 " **设置** \> **电子邮件 & 协作** \> **用户标记**"。

2. 在打开的 " **用户标记** " 页上，选择要查看的用户标记，然后单击 " **编辑标记**"。

3. "策略向导" 将在 " **编辑" 标记** 飞出时打开。单击 " **下一步** " 查看并修改设置。

   完成后，请单击 " **提交**"。

## <a name="use-the-security-center-to-remove-user-tags"></a>使用安全中心删除用户标记

**注意**：不能删除内置的 " **优先级" 帐户** 标记。

1. 在 "安全中心" 中，转到 " **设置** \> **电子邮件 & 协作** \> **用户标记**"。

2. 在打开的 " **用户标记** " 页上，选择要删除的用户标记，单击 " **删除标记**"，然后选择 **"是，** 在出现的警告中删除"。
