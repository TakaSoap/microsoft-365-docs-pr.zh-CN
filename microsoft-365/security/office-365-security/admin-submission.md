---
title: 管理员提交
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的提交门户将可疑电子邮件、可疑网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、URL 和文件提交给 Microsoft 进行扫描。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed417db93bc2f3efa6b85b0ef97c10b5941cd8eb
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029510"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在 Exchange Online 中具有邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规中心中的提交门户将电子邮件、URL 和附件提交给 Microsoft 进行扫描。

当你提交电子邮件时，你将获得：

1. **电子邮件身份验证检查**：有关电子邮件身份验证在传递时通过还是失败的详细信息。
2. **策略命中**：有关可能允许或阻止传入电子邮件进入租户的任何策略的信息，覆盖我们的服务筛选器裁定。
3. **有效负载信誉/触发**：检查邮件中任何 URL 和附件。
4. **成绩分析**：由人工评分人员进行审阅，以确认邮件是否是恶意邮件。

> [!IMPORTANT]
> 负载信誉/触发和成绩分析并非在所有租户中完成。 当数据出于合规性目的不应离开租户边界时，将阻止信息进入组织外部。

有关向 Microsoft 提交电子邮件、URL 和附件的其他方法，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到提交 **页面，** 请使用 <https://protection.office.com/reportsubmission> 。

- 若要向 Microsoft 提交邮件和文件，你需要是以下角色组之一的成员：

  - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。

  - **Exchange** [Online 中的组织管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。

    请注意，查看自定义邮箱的用户提交需要此角色[](#view-user-submissions-to-the-custom-mailbox)组成员身份，如本文稍后所述。

- 若要详细了解用户如何向 Microsoft 提交邮件和文件，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="report-suspicious-content-to-microsoft"></a>向 Microsoft 报告可疑内容

1. 在安全&合规中心，转到"**威胁** 管理提交"，确认你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**

2. 使用 **显示为** 提交邮件、URL 或附件的新提交飞出，如以下部分所述。

### <a name="submit-a-questionable-email-to-microsoft"></a>向 Microsoft 提交一封有问题的电子邮件

1. 在"**对象类型"** 部分，选择"**电子邮件"。** 在 **"提交格式** "部分中，使用以下选项之一：

   - **网络邮件 ID：** 这是一个 GUID 值，在邮件的 **X-MS-Exchange-Organization-Network-Message-Id** 标头中或在隔离邮件的 **X-MS-Office365-Filtering-Correlation-Id 标头** 中可用。

   - **文件**：单击 **"选择文件"。** 在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击"**打开"。**

   > [!NOTE]
   > 具有 Defender for Office 365 计划 1 或计划 2 的管理员可以提交 30 天的邮件。 其他管理员将只能返回 7 天。

2. 在 **"收件人"** 部分中，指定要针对这些收件人运行策略检查的一个或多个收件人。 策略检查将确定电子邮件是否由于用户或组织策略而绕过扫描。

3. 在 **"提交原因"部分** ，选择下列选项之一：

   - **不应被阻止**

   - **应该已被阻止**：选择 **垃圾邮件**、 **网络钓鱼** 或 **恶意软件**。 如果你不确定，请使用最佳判断。

4. 完成后，单击"提交 **"** 按钮。

   ![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>向 Microsoft 发送可疑 URL

1. 在"**对象类型"** 部分，选择 **URL。** 在出现的框中，输入完整的 URL (例如 `https://www.fabrikam.com/marketing.html` ，) 。

2. 在 **"提交原因"部分** ，选择下列选项之一：

   - **不应被阻止**

   - **应该已被阻止：** 选择 **网络钓鱼或****恶意软件**。

3. 完成后，单击"提交 **"** 按钮。

   ![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>将可疑文件提交给 Microsoft

1. 在"**对象类型"** 部分，选择"**附件"。**

2. 单击 **"选择文件"。** 在打开的对话框中，查找并选择文件，然后单击"打开 **"。**

3. 在 **"提交原因"部分** ，选择下列选项之一：

   - **不应被阻止**

   - **应该已被阻止**： **恶意软件** 是唯一的选择，并且会自动选中。

4. 完成后，单击"提交 **"** 按钮。

   ![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>查看管理员提交

在安全&合规中心，转到"**威胁** 管理提交"，确认你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**

在页面顶部附近，你可以输入开始日期、结束日期和 (默认情况下) 可以通过在框中输入值并单击"刷新"按钮，按提交 **ID** (筛选分配给每个提交) 的 GUID 值 ![ ](../../media/scc-quarantine-refresh.png) 。 Update

若要更改筛选条件，请单击 **"提交 ID"** 按钮并选择下列值之一：

- **Sender**
- **主题/URL/文件名**
- **提交者**
- **提交类型**
- "状态"

![管理员提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或****"表"。** 在出现的对话框中，保存 .csv 文件。

在图形下方，有三个选项卡：电子邮件 (默认 **) 、URL** 和 **附件**。

### <a name="view-admin-email-submissions"></a>查看管理员电子邮件提交

单击 **"电子邮件"** 选项卡。

可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：

- "日期"
- **提交 ID：** 分配给每个提交的 GUID 值。
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**
- **传递原因**
- **状态**<sup>\*</sup>

  <sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。

#### <a name="admin-submission-rescan-details"></a>管理员提交重新扫描详细信息

在管理员提交中提交的邮件将重新扫描，详细信息飞出中显示的结果如下：

- 如果在发送时发件人的电子邮件身份验证失败。
- 有关可能影响或替代邮件裁定的任何策略命中的信息。
- 当前触发结果，以查看邮件中包含的 URL 或文件是否恶意。
- 来自成绩人员的反馈。

如果发现覆盖，则重新扫描应在几分钟后完成。 如果电子邮件身份验证没有问题，或者传递不受替代影响，则来自成绩人员的反馈可能需要一天的时间。

### <a name="view-admin-url-submissions"></a>查看管理员 URL 提交

单击 **"URL"** 选项卡。

可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：

- "日期"
- **提交 ID**
- **提交者**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **提交类型**
- **状态**<sup>\*</sup>

  <sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。

### <a name="view-admin-attachment-submissions"></a>查看管理员附件提交

单击 **"附件"** 选项卡。

可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：

- "日期"
- **提交 ID**
- **提交者**<sup>\*</sup>
- **文件名**<sup>\*</sup>
- **提交类型**
- **状态**<sup>\*</sup>

  <sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。

## <a name="view-user-submissions-to-microsoft"></a>查看用户向 Microsoft 提交内容

如果已部署报告邮件外接程序、[](enable-the-report-message-add-in.md)报告网络钓鱼外接程序或用户使用 Outlook [](enable-the-report-phish-add-in.md)[网页](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中的内置报告，可以在"用户提交"选项卡上查看用户报告的内容。 

1. 在安全&中心，转到 **"威胁管理** \> **提交"。**

2. 选择 **"用户提交"** 选项卡，然后单击"**新建提交"。**

可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：

- **提交于**
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**

<sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。

在页面顶部附近，可以输入开始日期、结束日期和 (默认情况下) 可以通过在框中输入值并单击"刷新"按钮按发件人进行 ![ 筛选 ](../../media/scc-quarantine-refresh.png) 。 Update

若要更改筛选条件，请单击 **"发件人"** 按钮并选择下列值之一：

- **发件人域**
- **主题**
- **提交者**
- **提交类型**
- **发件人 IP**

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或****"表"。** 在出现的对话框中，保存 .csv 文件。

## <a name="view-user-submissions-to-the-custom-mailbox"></a>查看用户提交到自定义邮箱

**如果** 已配置自定义 [邮箱](user-submission.md) 以接收用户报告的邮件，则还可以查看并提交已传递到报告邮箱的邮件。

1. 在安全&中心，转到 **"威胁管理** \> **提交"。**

2. 选择 **"自定义邮箱"** 选项卡。

可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：

- **提交于**
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**

在页面顶部附近，可以输入开始日期、结束日期，并且可以通过在框中输入值并单击"刷新"按钮按"提交 ![ "进行筛选 ](../../media/scc-quarantine-refresh.png) 。 Update

若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或****"表"。** 在出现的对话框中，保存 .csv 文件。

## <a name="undo-user-submissions"></a>撤消用户提交

用户向自定义邮箱提交可疑电子邮件后，用户和管理员将无法选择撤消提交。 如果用户希望恢复电子邮件，它将可用于"已删除邮件"或"垃圾邮件"文件夹中的恢复。

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>从自定义邮箱向 Microsoft 提交邮件

如果已配置自定义邮箱以截获用户报告的邮件，而不将邮件发送到 Microsoft，您可以查找特定邮件并将其发送给 Microsoft 进行分析。 这有效地将用户提交移动到管理员提交。

在 **"自定义邮箱**"选项卡上，在列表中选择一封邮件，单击"操作"按钮，然后进行以下选择之一：

- **报告干净**
- **报告网络钓鱼**
- **报告恶意软件**
- **报告垃圾邮件**

!["操作"按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
