---
title: 管理员提交
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
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心的"提交"门户将可疑的电子邮件、疑头发邮件、垃圾邮件和其他可能有害的邮件、URL 和文件提交给 Microsoft 进行扫描。
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845962"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规中心中的提交门户将电子邮件、URL 和附件提交给 Microsoft 进行扫描。

提交电子邮件时，你将获得有关可能允许传入电子邮件进入租户的所有策略的信息，并查看邮件中的任何 URL 和附件。 可能允许邮件的策略包括单个用户的安全发件人列表和租户级策略（如 Exchange 邮件流规则 (也称为传输规则) 。

有关提交电子邮件、URL 和附件给 Microsoft 的其他方法，请参阅"[报告邮件和文件到 Microsoft"。](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到"提交 **"** 页面，请使用 <https://protection.office.com/reportsubmission> 。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 要向 Microsoft 提交邮件和文件，您必须是以下角色组之一的成员：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 若要获取对提交门户的只读访问权限，你需要是以下角色组的成员之一：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

- 有关用户如何向 Microsoft 提交邮件和文件的详细信息，请参阅"[报告邮件和文件"发送给 Microsoft。](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>向 Microsoft 报告可疑内容

1. 在安全与 &合规中心内，转到 **"威**胁 \> **管理提交**"，验证你是否在"**管理员提交"** 选项卡上，然后单击"新建**提交"。**

2. 使用 **似** 下来提交邮件、URL 或附件的新提交浮出控件，如下面各节中所述。

### <a name="submit-a-questionable-email-to-microsoft"></a>向 Microsoft 提交可疑电子邮件

1. 在"对象**类型"部分**，选择"**电子邮件"。** 在" **提交格式** "部分，使用下列选项之一：

   - **网络消息 ID：** 这是在邮件的 **X-MS-Exchange-Organization-Network-Message-Id 标头中可用的** GUID 值。

   - **文件**：单击 **"选择文件"。** 在打开的对话框中，找到并选择 .eml 或 .msg 文件，然后单击"打开 **"。**

2. 在 **"收件人** "部分，指定要对其运行策略检查的一个或多个收件人。 策略检查将确定是否由于用户或组织策略绕过扫描。

3. 在" **提交的原因** "部分，选择以下选项之一：

   - **不应已经阻止**

   - **应已阻止：****选择垃圾邮件****、网络钓鱼**或**恶意软件**。 如果你不确定，请使用最佳问题。

4. 如果在提交后策略导致筛选器被绕过，则你将看到有关该策略的信息。

   如果由于一个或多个策略而导致未绕过筛选器，则扫描将在几分钟内完成。 你将通过单击状态链接来查看有关提交的其他信息。 这包括策略检查结果和重新扫描的版本。 请注意，这不会再次通过 Office 365 ATP 完整筛选堆栈运行电子邮件，而是基于邮件、URL 或文件的特定属性运行部分重新扫描。

5. 完成后，单击"提交 **"** 按钮。

![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>将可自定义 URL 发送到 Microsoft

1. 在"对象**类型"部分**，选择 **"URL"。** 在出现的框中，输入完整的 URL (例如 <https://www.fabrikam.com/marketing.html>) 。

2. 在" **提交的原因** "部分，选择以下选项之一：

   - **不应已经阻止**

   - **应该已阻止：** 选择 **网络钓鱼** 或 **恶意软件**。

3. 完成后，单击"提交 **"** 按钮。

![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>将可检查的文件提交至 Microsoft

1. 在"对象**类型"部分**，选择"附件 **"。**

2. 单击 **"选择文件"。** 在打开的对话框中，找到并选择文件，然后单击"打开 **"。**

3. 在" **提交的原因** "部分，选择以下选项之一：

   - **不应已经阻止**

   - **应已阻止："****只"** 恶意软件"是唯一选择，并自动选择。

4. 完成后，单击"提交 **"** 按钮。

![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>查看管理员提交

在安全与 &合规中心内，转到 **"威**胁 \> **管理提交**"，验证你是否在"**管理员提交"** 选项卡上，然后单击"新建**提交"。**

在页面顶部区域的开头，可以输入开始日期、结束日期和 (默认情况下) 你可以通过在框中输入值并单击"刷新"按钮，按提交 **ID** (进行筛选，即分配给每个提交) 的 GUID ![ 值 ](../../media/scc-quarantine-refresh.png) 。 Update

若要更改筛选条件，请单击提交 **ID 按钮** ，然后选择以下值之一：

- **Sender**
- **使用者/URL/文件名**
- **提交者**
- **提交类型**
- **状态**

![筛选管理提交选项](../../media/admin-submission-email-filter-options.png)

要导出结果，请单击页面**顶部的"** 导出"，然后选择"图表数据 **"或**"**表"。** 在出现的对话框中，保存 .csv 文件。

在图下方有三个**选项卡：电子邮件** (个) **URL，和****附件**。

### <a name="view-admin-email-submissions"></a>查看管理员电子邮件提交

单击" **电子邮件"** 选项卡。

可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：

- **Date**
- **提交 ID：** 分配给每个提交的 GUID 值。
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**
- **传递原因**
- **状态**<sup>\*</sup>
- **控件类型**
- **控件源**

  <sup>\*</sup> 如果你单击此值，则在浮出控件中显示详细信息。

### <a name="view-admin-url-submissions"></a>查看管理 URL 提交

单击 **"URL"** 选项卡。

可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：

- **Date**
- **提交 ID**
- **提交者**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **提交类型**
- **状态**<sup>\*</sup>

  <sup>\*</sup> 如果你单击此值，则在浮出控件中显示详细信息。

### <a name="view-admin-attachment-submissions"></a>查看管理员附件提交

单击" **附件"** 选项卡。

可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：

- **Date**
- **提交 ID**
- **提交者**<sup>\*</sup>
- **文件名**<sup>\*</sup>
- **提交类型**
- **状态**<sup>\*</sup>

  <sup>\*</sup> 如果你单击此值，则在浮出控件中显示详细信息。

## <a name="view-user-submissions-to-microsoft"></a>查看用户提交至 Microsoft

如果已部署报告 [邮件加载项或](enable-the-report-message-add-in.md)用户使用 Outlook 网页 [版中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)，可以在"用户提交"选项卡上 **查看有哪些用户报告** 。

1. 在安全与&合规中心内，转到 **威胁** \> **管理提交**。

2. 选择"**用户提交"** 选项卡，然后单击"新建**提交"。**

可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：

- **Submitted on - 提交时间**
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**

<sup>\*</sup> 如果你单击此值，则在浮出控件中显示详细信息。

在页面顶部区域的开头，可以输入开始日期、结束日期和 (默认情况下) 您可以按 **发件人进行筛选** ，方法是在框中输入值，然后单击"刷新 ![ "按钮 ](../../media/scc-quarantine-refresh.png) 。 Update

若要更改筛选条件，请单击"发件人 **"** 按钮，并选择以下值之一：

- **发件人域**
- **主题**
- **提交者**
- **提交类型**
- **发件人 IP**

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

要导出结果，请单击页面**顶部的"** 导出"，然后选择"图表数据 **"或**"**表"。** 在出现的对话框中，保存 .csv 文件。

## <a name="view-user-submissions-to-the-custom-mailbox"></a>查看用户提交到自定义邮箱

如果您配置了 [自定义邮箱以](user-submission.md) 接收用户报告的邮件，则您可以查看和提交已传递到报告邮箱的邮件。

1. 在安全与&合规中心内，转到 **威胁** \> **管理提交**。

2. 选择" **自定义邮箱"** 选项卡。

可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：

- **Submitted on - 提交时间**
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**

在页面顶部区域的开头，可以输入开始日期和结束日期，并可通过在 **框中** 输入值并单击"刷新"按钮来进行 ![ 筛选 ](../../media/scc-quarantine-refresh.png) 。 Update

要导出结果，请单击页面**顶部的"** 导出"，然后选择"图表数据 **"或**"**表"。** 在出现的对话框中，保存 .csv 文件。

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>从自定义邮箱将邮件提交至 Microsoft

如果你已将自定义邮箱配置为截获用户报告的邮件，而不向 Microsoft 发送邮件，则您可以找到特定邮件并将其发送给 Microsoft 进行分析。 这可有效地将用户提交移至管理员提交。

在" **自定义邮箱** "选项卡上，在列表中选择邮件，再 **单击"操作** "按钮，然后做出以下选择之一：

- **报告干净报告**
- **报告网络钓鱼**
- **报告恶意软件**
- **报告垃圾邮件**

![操作按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
