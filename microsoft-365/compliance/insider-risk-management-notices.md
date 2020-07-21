---
title: 内幕风险管理通知模板
description: 了解 Microsoft 365 中的内部人员风险管理通知模板
keywords: Microsoft 365，内幕风险管理，风险管理，合规性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0211eefe3c4a946bbaa4ad4c8c66e5df7b37091e
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199483"
---
# <a name="insider-risk-management-notice-templates"></a>内幕风险管理通知模板

内幕风险管理通知模板允许你向用户发送电子邮件，当他们的活动生成策略匹配和警报时。 在大多数情况下，生成警报的用户操作是不正确意图的错误或无意活动的结果。 通知为用户提供了更小心的简单提醒，提供了有关复习培训的信息或公司策略资源的链接。 通知可能是内部合规性培训计划的重要组成部分，可帮助为具有定期风险活动的用户创建记录的审核跟踪。

如果要向用户发送有关策略匹配的电子邮件提醒通知（作为问题解决过程的一部分），请创建通知模板。 通知只能发送到与所审阅的特定警报关联的用户电子邮件地址。 选择要应用于策略匹配项的通知模板时，可以选择接受模板中定义的字段值，也可以根据需要覆盖这些字段。

## <a name="notice-templates-dashboard"></a>通知模板仪表板

"**通知模板" 仪表板**显示已配置的通知模板的列表，并允许您创建新的通知模板。 通知模板按相反的日期顺序列出，最新的声明模板最先列出。

![内幕风险管理通知模板仪表板](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>用于通知的 HTML

如果要创建多个简单的基于文本的电子邮件通知，可以通过使用通知模板的邮件正文字段中的 HTML 来创建更详细的消息。 下面的示例提供基于 HTML 的基本电子邮件通知模板的邮件正文格式：

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> 内幕风险管理通知模板中的 HTML href 属性实现目前仅支持为单引号（而不是双引号）提供 URL 引用。

## <a name="create-a-new-notice-template"></a>创建新的通知模板

若要创建新的内幕风险管理通知模板，请使用 Microsoft 365 合规性中心内的**内幕风险管理**解决方案中的 "通知向导"。

完成以下步骤以创建新的内幕风险管理通知模板：

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**通知模板**" 选项卡。
2. 选择 "**创建通知模板**" 以打开 "通知向导"。
3. 在 "**创建新的通知模板**" 页上，填写下列字段：
    - **模板名称**：输入通知的友好名称。 此名称显示在通知仪表板上的通知列表中，以及从案例发送通知时的通知选择列表中。
    - **发件人：输入**通知的发件人电子邮件地址。 此地址将显示在发送给用户的所有通知的 "**发件人：** " 字段中，除非在从案例发送通知时进行了更改。
    - **"抄送" 和 "密件抄送"** 字段：要向其通知策略匹配的可选用户或组，从 Active Directory 为你的订阅进行了选择。
    - **Subject**：邮件的主题行中显示的信息支持文本字符。
    - **邮件正文**：显示在邮件正文中的信息支持文本或 HTML 值。
4. 选择 "**创建**" 以创建并保存通知模板，或选择 "**取消**" 关闭而不保存通知模板。

## <a name="update-a-notice-template"></a>更新通知模板

若要更新现有的内幕风险管理通知模板，请完成以下步骤：

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**通知模板**" 选项卡。
2. 在 "通知" 仪表板上，选择要管理的通知模板。
3. 在 "通知详细信息" 页上，选择 "**编辑**"
4. 在 "**编辑**" 页上，您可以编辑以下字段：
    - **模板名称**：为通知输入新的友好名称。 此名称显示在通知仪表板上的通知列表中，以及从案例发送通知时的通知选择列表中。
    - **发**件人：更新通知的发件人电子邮件地址。 此地址将显示在发送给用户的所有通知的 "**发件人：** " 字段中，除非在从案例发送通知时进行了更改。
    - **"抄送" 和 "密件抄送**" 字段：更新要向订阅的 Active Directory 中选择的策略匹配项通知的可选用户或组。
    - **主题**：在邮件的主题行中显示的更新信息支持文本字符。
    - **邮件正文**：更新邮件正文中显示的信息，支持文本或 HTML 值。
5. 选择 "**保存**" 以更新并保存通知，或选择 "**取消**" 关闭而不保存通知模板。

## <a name="delete-a-notice-template"></a>删除通知模板

若要删除现有的内幕风险管理通知模板，请完成以下步骤：

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**通知模板**" 选项卡。
2. 在 "通知" 仪表板上，选择要删除的通知模板。
3. 在工具栏上选择 "**删除**" 图标。
4. 若要删除通知模板，请在 "删除" 对话框中选择 **"是"** 。 若要取消删除，请选择 "**取消**"。
