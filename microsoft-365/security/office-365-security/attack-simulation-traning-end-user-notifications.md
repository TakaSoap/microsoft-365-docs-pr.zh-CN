---
title: 攻击模拟训练的最终用户通知
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何在 Microsoft Defender for Office 365 计划 2 中为攻击模拟培训创建最终用户通知电子邮件。
ms.technology: mdo
ms.openlocfilehash: 3aa46724ef3414c83a5ece0c5fa17b4f9342c81c
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526658"
---
# <a name="end-user-notifications-for-attack-simulation-training"></a>攻击模拟训练的最终用户通知

在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 的攻击模拟培训中，最终用户通知是发送给用户的电子邮件 有两种基本类型的通知：

- **模拟通知**：这些消息在用户注册培训时发送，并作为所需培训的提醒发送。
- **正面的钓鱼** 通知：这些邮件在用户报告模拟网络钓鱼邮件时发送。

To see the available end-user notification， open the Microsoft 365 Defender portal at <https://security.microsoft.com>， and then go to **Email & collaboration** \> **Attack simulation training** \> **End-user notifications** tab.若要直接转到最终用户 **通知选项卡，** 请使用 <https://security.microsoft.com/attacksimulator?viewid=endUserNotification>。

" **最终用户通知"选项卡** 有两个选项卡：

- **全局通知**：包含内置和不可修改的通知。
- **租户通知**：包含已创建的自定义通知。

将显示每个通知的以下信息：

- **通知**：通知的名称。
- **语言**：如果通知包含多个翻译，则直接显示前两种语言。 To see the remaining languages， hover over the numeric icon (for example， **+10**) .
- **类型**：值为"模拟 **通知"或** " **正误报通知"**。
- **源**：对于内置通知，值为 **Global**。 对于自定义通知，值为 **Tenant**。
- **状态**
- **链接模拟**
- **创建方**：对于内置通知，值为 **Microsoft**。 对于自定义通知，该值是创建通知的用户的 UPN。
- **创建时间**
- **修改者**
- **上次修改时间**

若要在列表中查找通知，请使用搜索 ![图标。](../../media/m365-cc-sc-search-icon.png) **用于** 查找通知名称的搜索框。

若要按类型对通知进行分组，请单击"组 ![图标"。](../../media/m365-cc-sc-group-icon.png) **分组** ，然后选择" **通知类型"**。 若要取消通知组合，请选择"无 **"**。

仅" **租户通知"** 选项卡上，单击"筛选器 ![图标"。](../../media/m365-cc-sc-filter-icon.png) 按一种或多种语言筛选通知。

若要删除显示的一个或多个列，请单击"自定义 ![列图标"。](../../media/m365-cc-sc-customize-icon.png) **自定义列**。

从列表中选择通知时，将显示详细信息飞出，并包含以下信息：

- **预览** 选项卡：查看通知邮件。 若要查看不同语言的邮件，请使用" **选择语言"** 框。
- **详细信息** 选项卡：查看有关通知的详细信息：
  - **通知说明**
  - **源**：对于内置通知，值为 **Global**。 对于自定义通知，值为 **Tenant**。
  - **通知类型**
  - **修改者**
  - **上次修改时间**

## <a name="create-end-user-notifications"></a>创建最终用户通知

在" **租户通知"** 选项卡上，可以单击" ![创建新图标"。](../../media/m365-cc-sc-create-icon.png) **创建新的** 以启动新的最终用户通知向导。

1. 在" **定义详细信息** "页上，配置以下设置：
   - **选择通知类型**：**有正面的误报通知****或模拟** 通知。
   - **名称**：输入唯一的名称。
   - **说明**：输入可选说明。

   完成后，单击“**下一步**”。

2. 在 **"定义内容** "页上，唯一可用的设置是"使用业务 **语言添加内容"** 按钮。 单击它时，将显示" **使用默认语言添加** 内容"飞出，其中包含以下设置：
   - **From 显示名称**
   - **从电子邮件地址**
   - **选择电子邮件的语言：** 从列表中选择语言。
   - **将其标记为默认语言**：因为这是通知的第一种且唯一的语言，因此将选择此值，并且你无法更改它。
   - **主题**：默认值为 **"感谢报告钓鱼** 邮件，但你可以更改它"。
   - **导入电子邮件**：可以选择单击此按钮，然后单击" **选择** 文件"以导入现有的纯文本消息文件。
   - 电子邮件内容区域：有两个选项卡可用：
     - **"** 文本"选项卡：可以使用格式文本编辑器创建通知电子邮件。 除了典型的字体和格式设置之外，以下设置也可用：
       - **动态标记**：从以下标记中选择：
         - **插入名字**
         - **插入姓氏**
         - **插入 UPN**
         - **插入电子邮件地址**
         - **插入有效负载**
     - **代码** 选项卡：可以直接查看和修改 HTML 代码。

   可以通过单击页面顶部的" **预览电子邮件** "按钮预览结果。

   完成后，单击“**保存**”。

   你将返回到"定义内容"页，其中，你刚刚创建的通知汇总了以下信息：

   - **Language**
   - **主题**
   - **类别**
   - **操作**：以下图标可用：
     - ![编辑图标。](../../media/m365-cc-sc-edit-icon.png) **Edit**
     - ![视图图标。](../../media/m365-cc-sc-view-icon.png) **View**
     - ![删除图标。](../../media/m365-cc-sc-delete-icon.png) **删除**：如果通知只有语言版本，则不能将其删除。

   若要添加不同语言版本的通知，请单击"添加翻译 ![图标"](../../media/m365-cc-sc-create-icon.png)。 在出现的 **"添加翻译**"飞出中，可用的设置与前面所述的"使用默认语言添加内容"飞出内容相同。 唯一的区别是，可以在其他翻译中选择"将其 **标记为** 默认语言"。

   完成后，单击"保存 **"**

   你可以根据需要多次重复这些步骤，以使用 12 种支持的语言创建通知的翻译版本。

   完成后，单击"下一 **步"**

3. 在 **"查看通知** "页上，你可以查看通知的详细信息。

   可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，请单击“**提交**”。

   在" **新建模拟通知创建** "页上，可以使用链接创建新通知、启动模拟或查看所有通知。

   完成后，单击“**完成**”。

返回到" **租户通知"** 选项卡，你创建的通知现已列出。

选择通知时，可以使用以下附加选项：

你将返回到"积极积极者通知"页面，其中刚刚创建的通知现在显示在"选择正面的误报通知 **"** 列表中。

- 若要修改通知或添加其他翻译，请选择该通知，然后单击"编辑 ![图标"。](../../media/m365-cc-sc-edit-icon.png) **编辑通知** 以启动通知向导，如 (已填充大多数值) 。 如果通知已有 12 种支持语言的翻译，则不能添加更多翻译。

- 若要创建通知副本，请选择它，然后单击 ![创建副本图标。](../../media/m365-cc-sc-copy-icon.png).

- 若要删除通知，请选择它，然后单击 ![删除图标。](../../media/m365-cc-sc-delete-icon.png).

## <a name="related-links"></a>相关链接

[开始使用攻击模拟培训](attack-simulation-training-get-started.md)

[创建网络钓鱼攻击模拟](attack-simulation-training.md)

[攻击模拟培训的模拟自动化](attack-simulation-training-simulation-automations.md)
