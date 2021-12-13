---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- admindeeplinkDEFENDER
- admindeeplinkEXCHANGE
description: 管理员可以了解如何在 Microsoft Defender for Office 365 计划 2 中标识具有用户标记的特定用户组。 可在 Microsoft Defender for Office 365警报、报告和调查之间使用标签筛选，以快速标识已标记的用户。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a3472a7625082e21d88e01db12cd5d8d14f86c27
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61422743"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

> [!NOTE]
> 用户标记功能在预览版中，不可供所有人使用，并且可能会更改。 有关发布计划的信息，请查看Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)。

用户标记是 Microsoft Defender for Office 365[中的特定用户组的标识符](defender-for-office-365.md)。 有两种类型的用户标记：

- **系统标记**：目前 [，优先级帐户](../../admin/setup/priority-accounts.md) 是唯一类型的系统标记。
- **自定义标记**：你可自己创建这些用户标记。

如果你的组织拥有适用于 Office 365 计划 2 (的 Defender 或作为加载项) ，则除了使用优先级帐户标记外，还可以创建自定义用户标记。

> [!NOTE]
> 目前，只能将用户标记应用于邮箱用户。

向用户应用系统标记或自定义标记后，可以在警报、报告和调查中使用这些标记作为筛选器：

- [警告](alerts.md)
- [自定义警报策略](../../compliance/alert-policies.md#viewing-alerts)
- [威胁资源管理器和实时检测](threat-explorer.md)
- [电子邮件实体页面](mdo-email-entity-page.md#other-innovations)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [市场活动视图](campaigns.md)
- [管理员和用户提交](admin-submission.md)
- 对于优先级帐户，可以使用管理中心中的[](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)"优先级帐户的电子邮件Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">报告</a>。

本文介绍如何在应用程序门户中配置用户<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender标记</a>。 管理门户中没有任何 cmdlet Microsoft 365 Defender管理用户标记。

若要了解用户标记如何作为策略的一部分来帮助保护高影响的用户帐户，请参阅安全建议[中](security-recommendations-for-priority-accounts.md)优先级帐户Microsoft 365。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com/</a> 以打开 Microsoft 365 Defender 门户。 若要直接转到" **用户标记"** 页，请打开 <https://security.microsoft.com/securitysettings/userTags> 。

- 您需在 Microsoft 365 Defender 门户中分配权限，然后才能执行本文中的过程：
  - 若要创建、修改和删除用户标记，您必须是组织管理或安全 **管理员****角色组** 的成员。
  - 若要从现有用户标记中添加和删除成员，你需要是组织管理、**安全** 管理员或 **安全** 操作员角色组的成员
  - 对于用户标记的只读访问，你需要是全局读取 **者** 或安全 **读者角色组** 的成员。

  有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

  > [!NOTE]
  >
  > - 将用户添加到 Azure Active Directory 中的相应 Microsoft 365 管理中心 可为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - 用户标记管理由 Tag **Reader** 和 **Tag Manager 角色** 控制。

- 还可以在安全管理中管理和监视Microsoft 365 管理中心。 有关说明，请参阅 [管理和监视优先级帐户](../../admin/setup/priority-accounts.md)。

- 有关保护管理员帐户的 _特权 (_ 的信息) ，请参阅 [本主题](/azure/architecture/framework/security/critical-impact-accounts)。

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>使用Microsoft 365 Defender门户创建用户标记

1. 在 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中</a>，转到设置 \> **电子邮件&协作** \> **用户标记。**

2. 在" **用户标记"** 页上，单击" ![ 创建标记图标"。](../../media/m365-cc-sc-create-icon.png) **创建标记**。

3. " **创建标记** "向导将在新的飞出控件中打开。 在" **定义标记"** 页上，配置以下设置：
   - **名称**：输入标记的唯一描述性名称。 这是你将看到并使用的值。 请注意，创建标记后无法重命名它。
   - **说明**：输入标记的可选说明。

   完成后，单击“**下一步**”。

4. 在 **"分配成员"** 页上，执行以下步骤之一：
   - 单击 ![ "添加成员"图标。](../../media/m365-cc-sc-create-icon.png) **添加成员**。 在出现的"飞出"中，执行以下任一步骤以添加单个用户或组：
     - 在框中单击并滚动浏览列表以选择用户或组。
     - 在框中单击并开始键入以筛选列表并选择用户或组。
     - 若要添加其他值，请单击框中的空白区域。
     - 若要删除单个条目，请单击 ![删除条目图标。](../../media/m365-cc-sc-remove-selection-icon.png) 框中的条目旁边。
     - 若要删除所有条目，请单击" ![ 删除条目图标"。](../../media/m365-cc-sc-remove-selection-icon.png) 位于 **框下方的"所选 nn 用户和 nn 组** "项上。

     完成后，单击“**添加**”。

     返回到" **分配成员** "页，您还可以通过单击"删除"图标 ![ 来删除条目。](../../media/m365-cc-sc-delete-icon.png) 项旁边。

   - 单击 **"** 导入"选择一个包含用户或组的电子邮件地址的文本文件。 确保文本文件每行包含一个条目。

   完成后，单击“**下一步**”。

5. 在出现的 **"审阅标记** "页上，查看设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，单击"提交 **"，** 然后单击"完成 **"。**

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>使用Microsoft 365 Defender查看用户标记

1. 在 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中</a>，转到设置 \> **电子邮件&协作** \> **用户标记。**

2. 在 **"用户标记** "页上，用户标记列表中将显示以下属性：

   - **Tag**：用户标记的名称。 请注意，这包括内置的 **优先级帐户** 系统标记。
   - **应用于**：成员数
   - **上次修改时间**
   - **创建日期**

3. 当您通过单击该名称选择用户标记时，详细信息将显示在一个 flyout 中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>使用 Microsoft 365 Defender门户修改用户标记

1. 在 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中</a>，转到设置 \> **电子邮件&协作** \> **用户标记。**

2. 在" **用户标记** "页上，从列表中选择用户标记，然后单击"编辑 ![ 标记图标"。](../../media/m365-cc-sc-edit-icon.png) **编辑标记**。

3. 在出现的详细信息飞出控件中，提供相同的向导和设置，如本文前面使用 Microsoft 365 Defender[门户](#use-the-microsoft-365-defender-portal-to-create-user-tags)创建用户标记部分所述。

   **注意**：

   - " **定义标记** "页对内置 **Priority** 帐户系统标记不可用，因此无法重命名此标记或更改说明。
   - 不能重命名自定义标记，但可以更改说明。

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>使用Microsoft 365 Defender删除用户标记

> [!NOTE]
> 无法删除内置的 **优先级帐户系统** 标记。

1. 在 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中</a>，转到设置 \> **电子邮件&协作** \> **用户标记。**

2. 在" **用户标记** "页上，从列表中选择用户标记，然后单击" ![ 删除标记图标"。](../../media/m365-cc-sc-delete-icon.png) **删除标记**。

3. 阅读出现的确认对话框中的警告，然后单击"是 **，删除"。**
