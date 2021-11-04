---
title: 内部风险管理通知模板
description: 了解管理中心中的内部风险管理通知Microsoft 365
keywords: Microsoft 365- 预览体验计划风险管理、风险管理、合规性
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 47b53814ce3df8c2a8215705521169f27065b5a3
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753893"
---
# <a name="insider-risk-management-notice-templates"></a>内部风险管理通知模板

通过内部风险管理通知模板，您可以在为已生成策略匹配和已确认警报的活动创建案例时自动向用户发送电子邮件。 对于大多数生成案例的警报，用户操作是错误或无意活动的结果，没有恶意目的。 通知可让用户更加小心、提供刷新培训信息或公司策略资源的链接， 通知可以是内部合规性培训计划的重要部分，并且有助于为具有定期风险活动的用户创建记录审核线索。

如果要在案例解决过程中向用户发送策略匹配项的电子邮件提醒通知，请创建通知模板。 通知只能发送到与所审阅的特定案例关联的用户电子邮件地址。 选择要应用于策略匹配的通知模板时，可以选择接受模板中定义的字段值或根据需要覆盖字段

## <a name="notice-templates-dashboard"></a>通知模板仪表板

**通知模板仪表板** 显示已配置通知模板的列表，并允许你创建新的通知模板。 通知模板以相反的日期顺序列出，最新的通知模板列出在最前面。

![内部风险管理通知模板仪表板。](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>通知的 HTML

如果要为通知创建多个基于文本的简单电子邮件，可以在通知模板的邮件正文字段中使用 HTML 来创建更详细的邮件。 以下示例提供基于 HTML 的基本电子邮件通知模板的邮件正文格式：

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
> 内部风险管理通知模板中的 HTML href 属性实现目前仅支持单引号，而不支持 URL 引用的双引号。

## <a name="create-a-new-notice-template"></a>创建新的通知模板

若要创建新的内部风险管理通知模板，你将使用预览体验成员风险管理解决方案中的通知创建Microsoft 365 合规中心。 

完成以下步骤以创建新的内部风险管理通知模板：

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心，</a>go to **Insider risk management** and select the Notice **templates** tab.
2. 选择 **"创建通知模板** "以打开通知创建工具。
3. 在" **新建通知模板"页上** ，填写下列字段：
    - **模板名称**：为通知输入友好名称。 从案例发送通知时，此名称将显示在通知仪表板上的通知列表和通知选择列表中。
    - **发件人**：输入通知的发件人电子邮件地址。 此地址将出现在发送给用户的所有通知的 **From：** 字段中，除非在从案例发送通知时发生更改。
    - **"抄** 送"和"密件抄送"字段：从订阅的 Active Directory 选择的策略匹配通知的可选用户或组。
    - **主题**：邮件主题行中显示的信息支持文本字符。
    - **邮件正文**：邮件正文中显示的信息支持文本或 HTML 值。
4. 选择 **"创建** "以创建并保存通知模板， **或选择"** 取消"以关闭而不保存通知模板。

## <a name="update-a-notice-template"></a>更新通知模板

若要更新现有的内部风险管理通知模板，请完成以下步骤：

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心，</a>go to **Insider risk management** and select the Notice **templates** tab.
2. 在通知仪表板上，选择要管理的通知模板。
3. 在通知详细信息页面上，选择"编辑 **"**
4. 在 **"编辑** "页上，可以编辑以下字段：
    - **模板名称**：为通知输入新的友好名称。 从案例发送通知时，此名称将显示在通知仪表板上的通知列表和通知选择列表中。
    - **发件人**：更新通知的发件人电子邮件地址。 此地址将出现在发送给用户的所有通知的 **From：** 字段中，除非在从案例发送通知时发生更改。
    - **"抄** 送"和"密件抄送"字段：更新要收到策略匹配通知的可选用户或组（从订阅的 Active Directory 选择）。
    - **主题**：更新邮件主题行中显示的信息，支持文本字符。
    - **邮件正文**：更新邮件正文中显示的信息，支持文本或 HTML 值。
5. 选择 **"保存** "更新并保存通知，或 **选择"** 取消"关闭而不保存通知模板。

## <a name="delete-a-notice-template"></a>删除通知模板

若要删除现有的内部风险管理通知模板，请完成以下步骤：

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心，</a>go to **Insider risk management** and select the Notice **templates** tab.
2. 在通知仪表板上，选择要删除的通知模板。
3. 选择工具栏 **上的"** 删除"图标。
4. 若要删除通知模板，请在删除 **对话框中选择** "是"。 若要取消删除，请选择"取消 **"。**
