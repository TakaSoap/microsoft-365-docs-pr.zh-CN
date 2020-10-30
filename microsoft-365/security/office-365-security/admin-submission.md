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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规性中心中的提交门户将可疑的电子邮件、可疑的网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、Url 和文件提交到 Microsoft 进行扫描。
ms.openlocfilehash: 5d4123acaf3c9891f9aeb8028173f3071c260935
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806756"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在 Exchange Online 中有邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规性中心中的提交门户将电子邮件、Url 和附件提交给 Microsoft 进行扫描。

当您提交电子邮件时，您将获得可能允许传入的电子邮件进入租户的任何策略的信息，以及对邮件中的任何 Url 和附件的检查。 可能允许邮件的策略包括单个用户的安全发件人列表以及租户级别策略（如 Exchange 邮件流规则） (也称为传输规则) 。

有关向 Microsoft 提交电子邮件、Url 和附件的其他方法，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **提交** 页面，请使用 <https://protection.office.com/reportsubmission> 。

- 若要向 Microsoft 提交邮件和文件，您必须是下列角色组之一的成员：

  - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“ **组织管理** ”或“ **安全管理员** ”。

  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 **组织管理** 。

    请注意，此角色组中的成员身份是 [查看用户提交到自定义邮箱的](#view-user-submissions-to-the-custom-mailbox) 必要条件，如本主题后面所述。

- 有关用户如何向 Microsoft 提交邮件和文件的详细信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="report-suspicious-content-to-microsoft"></a>向 Microsoft 报告可疑内容

1. 在 "安全性 & 合规性中心" 中，转到 " **威胁管理** \> **提交** "，确认您在 " **管理员提交** " 选项卡上，然后单击 " **新建提交** "。

2. 使用在提交邮件、URL 或附件时出现的 **新提交** 浮出控件，如以下各节中所述。

### <a name="submit-a-questionable-email-to-microsoft"></a>将可疑电子邮件提交给 Microsoft

1. 在 " **对象类型** " 部分，选择 " **电子邮件** "。 在 " **提交格式** " 部分，使用以下选项之一：

   - **网络邮件 ID** ：这是邮件中 **X--组织网络-邮件 ID** 标头中可用的 GUID 值。

   - **文件** ：单击 " **选择文件** "。 在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击 " **打开** "。

2. 在 " **收件人** " 部分，指定要对其运行策略检查的一个或多个收件人。 策略检查将确定电子邮件是否因用户或组织策略而绕过扫描。

3. 在 " **提交原因** " 部分，选择下列选项之一：

   - **不应被阻止**

   - **应已阻止** ：选择 " **垃圾邮件** "、" **网络钓鱼** " 或 " **恶意软件** "。 如果你不确定，请使用你的最佳判断力。

4. 如果由于提交策略而绕过筛选器，你将看到有关该策略的信息。

   如果筛选器由于一个或多个策略而被绕过，扫描将在几分钟内完成。 您将通过单击状态链接来查看有关提交的其他信息。 这包括策略检查结果和重新扫描判定结果。 注意这不会再次通过 Office 365 ATP 完全筛选堆栈运行电子邮件，但会根据邮件、URL 或文件的某些属性运行部分重新扫描。

5. 完成后，单击 " **提交** " 按钮。

![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>向 Microsoft 发送可疑 URL

1. 在 " **对象类型** " 部分，选择 " **URL** "。 在出现的框中，输入完整的 URL (例如， `https://www.fabrikam.com/marketing.html`) 。

2. 在 " **提交原因** " 部分，选择下列选项之一：

   - **不应被阻止**

   - **应已阻止** ：选择 " **网络钓鱼** " 或 " **恶意软件** "。

3. 完成后，单击 " **提交** " 按钮。

![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>将可疑文件提交给 Microsoft

1. 在 " **对象类型** " 部分，选择 " **附件** "。

2. 单击 " **选择文件** "。 在打开的对话框中，查找并选择文件，然后单击 " **打开** "。

3. 在 " **提交原因** " 部分，选择下列选项之一：

   - **不应被阻止**

   - **应已被阻止** ： **恶意软件** 是唯一的选择，并且会自动选中。

4. 完成后，单击 " **提交** " 按钮。

![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>查看管理提交

在 "安全性 & 合规性中心" 中，转到 " **威胁管理** \> **提交** "，确认您在 " **管理员提交** " 选项卡上，然后单击 " **新建提交** "。

在页面顶部附近，您可以输入开始日期、结束日期和 (默认情况下) 您可以按 **提交 ID** (筛选器分配给每个提交) 的 GUID 值，方法是在框中输入一个值，然后单击 " ![ 刷新" ](../../media/scc-quarantine-refresh.png) 按钮。 Update

若要更改筛选条件，请单击 " **提交 ID** " 按钮，然后选择下列值之一：

- **Sender**
- **主题/URL/文件名**
- **提交者**
- **提交类型**
- **Status**

![用于管理提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

若要导出结果，请单击页面顶部附近的 " **导出** "，然后选择 " **图表数据** " 或 " **表格** "。 在出现的对话框中，保存 .csv 文件。

在图形下方有三个选项卡： **电子邮件** (默认) 、 **URL** 和 **附件** 。

### <a name="view-admin-email-submissions"></a>查看管理员电子邮件提交

单击 " **电子邮件** " 选项卡。

您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：

- **Date**
- **提交 ID** ：分配给每个提交的 GUID 值。
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**
- **传递原因**
- **状态值**<sup>\*</sup>
- **控件类型**
- **控制源**

  <sup>\*</sup> 如果单击此值，则会在浮出控件中显示详细信息。

### <a name="view-admin-url-submissions"></a>查看管理 URL 提交

单击 " **URL** " 选项卡。

您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：

- **Date**
- **提交 ID**
- **提交者**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **提交类型**
- **状态值**<sup>\*</sup>

  <sup>\*</sup> 如果单击此值，则会在浮出控件中显示详细信息。

### <a name="view-admin-attachment-submissions"></a>查看管理员附件提交

单击 " **附件** " 选项卡。

您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：

- **Date**
- **提交 ID**
- **提交者**<sup>\*</sup>
- **文件名**<sup>\*</sup>
- **提交类型**
- **状态值**<sup>\*</sup>

  <sup>\*</sup> 如果单击此值，则会在浮出控件中显示详细信息。

## <a name="view-user-submissions-to-microsoft"></a>查看向 Microsoft 提交的用户

如果已部署 [报告邮件加载项](enable-the-report-message-add-in.md)，或者用户在 [Web 上使用 Outlook 中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)功能，则可以在 " **用户提交** " 选项卡上查看要报告的用户。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **提交** "。

2. 选择 " **用户提交** " 选项卡，然后单击 " **新建提交** "。

您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：

- **提交于**
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**

<sup>\*</sup> 如果单击此值，则会在浮出控件中显示详细信息。

在页面顶部附近，您可以输入开始日期、结束日期和 (默认情况下) 您可以通过在框中输入值并单击 "刷新" 按钮来按 **发件人** 进行筛选 ![ ](../../media/scc-quarantine-refresh.png) 。 Update

若要更改筛选条件，请单击 " **发件人** " 按钮，然后选择下列值之一：

- **发件人域**
- **主题**
- **提交者**
- **提交类型**
- **发件人 IP**

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

若要导出结果，请单击页面顶部附近的 " **导出** "，然后选择 " **图表数据** " 或 " **表格** "。 在出现的对话框中，保存 .csv 文件。

## <a name="view-user-submissions-to-the-custom-mailbox"></a>查看到自定义邮箱的用户提交

**如果** 您已 [将自定义邮箱配置](user-submission.md) 为接收用户报告的邮件，则可以查看并提交传递到报告邮箱的邮件。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **提交** "。

2. 选择 " **自定义邮箱** " 选项卡。

您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：

- **提交于**
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**

在页面顶部附近，可以输入开始日期和结束日期，您可以通过在框中输入值并单击 "刷新" 按钮来按 **提交的** 方式进行筛选 ![ ](../../media/scc-quarantine-refresh.png) 。 Update

若要导出结果，请单击页面顶部附近的 " **导出** "，然后选择 " **图表数据** " 或 " **表格** "。 在出现的对话框中，保存 .csv 文件。

## <a name="undo-user-submissions"></a>撤消用户提交

用户将可疑电子邮件提交到自定义邮箱后，用户和管理员不能选择撤消提交。 如果用户想要恢复该电子邮件，则可在 "已删除邮件" 或 "垃圾邮件" 文件夹中进行恢复。 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>从自定义邮箱向 Microsoft 提交邮件

如果已将自定义邮箱配置为在不向 Microsoft 发送邮件的情况下截获用户报告的邮件，则可以查找特定邮件并将其发送给 Microsoft 进行分析。 这将有效地将用户提交移动到管理员提交。

在 " **自定义邮箱** " 选项卡上，选择列表中的一封邮件，单击 " **操作** " 按钮，然后进行下列选择之一：

- **报告清理**
- **报告网络钓鱼**
- **报告恶意软件**
- **报告垃圾邮件**

!["操作" 按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
