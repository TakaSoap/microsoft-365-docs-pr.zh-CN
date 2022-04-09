---
title: Microsoft Defender for Office 365中的用户标记
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/17/2021
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理员可以了解如何在计划 2 Microsoft Defender for Office 365中识别具有用户标记的特定用户组。 标记筛选可在Microsoft Defender for Office 365中跨警报、报表和调查进行，以便快速识别标记的用户。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da17b2dfb20746bb48b1ba737968873d4151595
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731605"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365中的用户标记

用户标记是[Microsoft Defender for Office 365](defender-for-office-365.md)中特定用户组的标识符。 有两种类型的用户标记：

- **系统标记**：目前， [Priority 帐户](../../admin/setup/priority-accounts.md) 是唯一的系统标记类型。
- **自定义标记**：你自己创建这些用户标记。

如果你的组织已在订阅中包含Defender for Office 365计划 2 (或作为加载项) ，则除了使用优先级帐户标记外，还可以创建自定义用户标记。

> [!NOTE]
> 目前，只能向邮箱用户应用用户标记。

向用户应用系统标记或自定义标记后，可以在警报、报表和调查中使用这些标记作为筛选器：

- [警告](alerts.md)
- [自定义警报策略](../../compliance/alert-policies.md#viewing-alerts)
- [威胁资源管理器和实时检测](threat-explorer.md)
- [电子邮件实体页面](mdo-email-entity-page.md#other-innovations)
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
- [攻击模拟](attack-simulation-training.md#target-users)
- [市场活动视图](campaigns.md)
- [管理员和用户提交](admin-submission.md)
- [隔离](quarantine.md)
- 对于优先级帐户，可以在 Exchange 管理中心 (EAC) 中[使用优先级帐户报告的电子邮件问题](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。

本文介绍如何在Microsoft 365 Defender门户中配置用户标记。 Microsoft 365 Defender门户中没有用于管理用户标记的 cmdlet。

若要查看用户标记如何成为帮助保护高影响用户帐户的策略的一部分，请参阅[Microsoft 365中优先级帐户的安全建议](security-recommendations-for-priority-accounts.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到 **"用户标记"** 页，请使用 <https://security.microsoft.com/securitysettings/userTags>。

- 需要在Microsoft 365 Defender门户中分配权限，然后才能执行本文中的过程：
  - 若要创建、修改和删除自定义用户标记，需要是 **组织管理** 或 **安全管理员** 角色组的成员。
  - 若要从"优先级帐户"系统标记中添加和删除成员，需要是 **安全管理员** 和 **Exchange管理员** 角色组的成员。
  - 若要从现有自定义用户标记中添加和删除成员，需要是 **组织管理** 或 **安全管理员** 角色组的成员。
  - 若要对用户标记进行只读访问，需要是 **全局读取者**、 **安全操作员** 或 **安全读取者** 角色组的成员。

  有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

  > [!NOTE]
  >
  > - 将用户添加到Microsoft 365 管理中心中相应的Azure Active Directory角色可为用户提供Microsoft 365 Defender门户中所需的权限 _以及_ Microsoft 365中其他功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - 用户标记管理由 **标记读取器** 和 **标记管理器** 角色控制。

- 还可以管理和监视Microsoft 365 管理中心中的优先级帐户。 有关说明，请参阅 [管理和监视优先级帐户](../../admin/setup/priority-accounts.md)。

- 有关保护 (管理员 _帐户) 的特权帐户_ 的信息，请参阅 [本主题](/azure/architecture/framework/security/critical-impact-accounts)。

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>使用Microsoft 365 Defender门户创建用户标记

1. 在Microsoft 365 Defender门户中<https://security.microsoft.com>，转到 **设置** \> **电子邮件&协作** \> **用户标记**。 若要直接转到 **"用户标记"** 页，请使用 <https://security.microsoft.com/securitysettings/userTags>。

2. 在 **"用户标记"页上** ，单击 !["创建标记"图标。](../../media/m365-cc-sc-create-icon.png) **创建标记**。

3. **"创建标记**"向导将在新的浮出控件中打开。 在 **"定义标记** "页上，配置以下设置：
   - **名称**：输入标记的唯一描述性名称。 这是你将看到和使用的值。 请注意，创建标记后无法重命名标记。
   - **说明**：输入标记的可选说明。

   完成后，请单击“**下一步**”。

4. 在 **"分配成员** "页上，执行以下任一步骤：
   - 单击 !["添加成员"图标。](../../media/m365-cc-sc-create-icon.png) **添加成员**。 在显示的浮出控件中，执行以下任一步骤来添加单个用户或组：
     - 在框中单击并滚动浏览列表以选择用户或组。
     - 单击框中，开始键入以筛选列表并选择用户或组。
     - 若要添加其他值，请单击框中的空区域。
     - 若要删除单个条目，请单击 ![删除条目图标。](../../media/m365-cc-sc-remove-selection-icon.png) 在框中的条目旁边。
     - 若要删除所有条目，请单击 !["删除条目"图标。](../../media/m365-cc-sc-remove-selection-icon.png) 在框下方 **的所选 nn 用户和 nn 组** 项上。

     完成后，单击“**添加**”。

     在 **"分配成员** "页上，还可以通过单击 !["删除"图标删除条目。](../../media/m365-cc-sc-delete-icon.png) 在条目旁边。

   - 单击 **"导** 入"以选择包含用户或组的电子邮件地址的文本文件。 请确保文本文件每行包含一个条目。

   完成后，请单击“**下一步**”。

5. 在显示的 **"审阅"标记** 页上，查看设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，单击" **提交**"，然后单击 **"完成**"。

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>使用Microsoft 365 Defender门户查看用户标记

1. 在Microsoft 365 Defender门户中<https://security.microsoft.com>，转到 **设置** \> **电子邮件&协作** \> **用户标记**。 若要直接转到 **"用户标记"** 页，请使用 <https://security.microsoft.com/securitysettings/userTags>。

2. 在 **"用户标记"** 页上，以下属性显示在用户标记列表中：

   - **标记**：用户标记的名称。 请注意，这包括内置的 **优先级帐户** 系统标记。
   - **应用于**：成员数
   - **上次修改时间**
   - **创建日期**

3. 单击名称选择用户标记时，详细信息会显示在浮出控件中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>使用Microsoft 365 Defender门户修改用户标记

1. 在Microsoft 365 Defender门户中<https://security.microsoft.com>，转到 **设置** \> **电子邮件&协作** \> **用户标记**。 若要直接转到 **"用户标记"** 页，请使用 <https://security.microsoft.com/securitysettings/userTags>。

2. 在 **"用户标记"页上** ，从列表中选择用户标记，然后单击 !["编辑标记"图标。](../../media/m365-cc-sc-edit-icon.png) **编辑标记**。

3. 在显示的详细信息浮出控件中，与本文前面的"[使用Microsoft 365 Defender门户创建用户标记"](#use-the-microsoft-365-defender-portal-to-create-user-tags)部分中所述的向导和设置相同。

   **注意**:

   - " **定义标记** "页不适用于内置的 **"优先级"帐户** 系统标记，因此不能重命名此标记或更改说明。
   - 无法重命名自定义标记，但可以更改说明。

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>使用Microsoft 365 Defender门户删除用户标记

> [!NOTE]
> 无法删除内置的 **优先级帐户** 系统标记。

1. 在Microsoft 365 Defender门户中<https://security.microsoft.com>，转到 **设置** \> **电子邮件&协作** \> **用户标记**。 若要直接转到 **"用户标记"** 页，请使用 <https://security.microsoft.com/securitysettings/userTags>。

2. 在 **"用户标记"页上** ，从列表中选择用户标记，然后单击 !["删除标记"图标。](../../media/m365-cc-sc-delete-icon.png) **删除标记**。

3. 读取显示的确认对话框中的警告，然后单击 **"是"，删除**。

## <a name="more-information"></a>更多信息

- [在Microsoft Defender for Office 365中配置和查看优先级帐户](configure-review-priority-account.md)