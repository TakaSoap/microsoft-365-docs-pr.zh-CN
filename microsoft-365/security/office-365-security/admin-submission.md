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
description: 管理员可以了解如何使用安全 & 合规中心中的提交门户将可疑电子邮件、可疑钓鱼邮件、垃圾邮件和其他可能有害的邮件、URL 和文件提交给 Microsoft 进行扫描。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f1294335be5a82ef7219ef9096d84d840271c5b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499336"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)


在具有 Exchange Online 邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规中心中的提交门户将电子邮件、URL 和附件提交到 Microsoft 进行扫描。

当你提交电子邮件时，你得到：

1. **电子邮件身份验证检查**：有关电子邮件身份验证在传递时通过还是失败的详细信息。
2. **策略命中**：有关可能允许或阻止传入电子邮件进入租户的任何策略的信息，覆盖我们的服务筛选器裁定。
3. **有效负载信誉/触发**：检查邮件中任何 URL 和附件。
4. **成绩分析**：由人工评分人员完成审阅，以确认邮件是否是恶意邮件。

> [!IMPORTANT]
> 负载信誉/触发和成绩分析并非在所有租户中都完成。 当数据出于合规性目的不应离开租户边界时，将阻止信息进入组织外部。

有关向 Microsoft 提交电子邮件、URL 和附件的其他方法，请参阅向 Microsoft 报告 [邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到提交 **页面，** 请使用 <https://protection.office.com/reportsubmission> 。

- 若要向 Microsoft 提交邮件和文件，你需要是以下角色组之一的成员：

  - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。

  - **Exchange** Online 中的 [组织管理](/Exchange/permissions-exo/permissions-exo#role-groups)。

    请注意，查看自定义邮箱的用户提交需要此角色组的 [成员身份，如](#view-user-submissions-to-the-custom-mailbox) 本文稍后所述。

- 有关用户如何向 Microsoft 提交邮件和文件的信息，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="report-suspicious-content-to-microsoft"></a>向 Microsoft 报告可疑内容

1. 在安全&合规中心，转到"威胁管理提交"，验证你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**

2. 使用 **显示为** 提交邮件、URL 或附件的新提交飞出，如以下各节中所述。

### <a name="submit-a-questionable-email-to-microsoft"></a>向 Microsoft 提交有问题的电子邮件

1. 在"**对象类型"部分**，选择"**电子邮件"。** 在" **提交格式"** 部分，使用以下选项之一：

   - **网络邮件 ID：** 这是一个 GUID 值，在邮件的 **X-MS-Exchange-Organization-Network-Message-Id** 头中或在隔离邮件的 **X-MS-Office365-Filtering-Correlation-Id 头** 中可用。

   - **文件**：单击 **"选择文件"。** 在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击"打开 **"。**

   > [!NOTE]
   > 使用 Defender for Office 365 计划 1 或计划 2 的管理员可以提交 30 天的邮件。 其他管理员将只能返回 7 天。

2. 在 **"收件人"** 部分，指定要针对其运行策略检查的一个或多个收件人。 策略检查将确定电子邮件是否由于用户或组织策略而绕过扫描。

3. 在" **提交原因"** 部分，选择以下选项之一：

   - **不应被阻止**

   - **应已阻止：选择**"**垃圾邮件****"、"网络钓鱼"或**"恶意软件 **"。** 如果你不确定，请使用最佳判断。

4. 完成后，单击"提交 **"** 按钮。

   ![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>向 Microsoft 发送可疑 URL

1. 在"**对象类型"部分**，选择 **"URL"。** 在出现的框中，输入完整的 URL (例如 `https://www.fabrikam.com/marketing.html` ，) 。

2. 在" **提交原因"** 部分，选择以下选项之一：

   - **不应被阻止**

   - **应该已被阻止：选择网络钓鱼****或****恶意软件**。

3. 完成后，单击"提交 **"** 按钮。

   ![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>将可疑文件提交给 Microsoft

1. 在"**对象类型"部分**，选择"附件 **"。**

2. 单击 **"选择文件"。** 在打开的对话框中，查找并选择文件，然后单击"打开 **"。**

3. 在" **提交原因"** 部分，选择以下选项之一：

   - **不应被阻止**

   - **应已阻止**： **恶意软件** 是唯一的选择，并且会自动选中。

4. 完成后，单击"提交 **"** 按钮。

   ![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>查看提交用于分析的项目

In the Security & Compliance Center， go to **Threat management** \> **Submissions**， verify that you're on the **Submitted for analysis** tab

在页面顶部附近，你可以输入开始日期、结束日期和 (默认情况下) 你可以按提交 **ID** (通过输入框中的值并单击"刷新"按钮来筛选分配给每个提交) 的 GUID 值。 ![ ](../../media/scc-quarantine-refresh.png) Update

若要更改筛选条件，请单击" **提交 ID"按钮** 并选择下列值之一：

- **Sender**
- **主题/URL/文件名**
- **提交者**
- **提交类型**
- **状态**

![管理员提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

若要导出结果，请单击页面 **顶部附近的**"导出"，然后选择"**图表数据**"或"表 **"。** 在出现的对话框中，保存 .csv 文件。

在图形下方，有三个选项卡："电子邮件" (默认 **) 、URL** 和 **"附件"。**

### <a name="view-admin-email-submissions"></a>查看管理员电子邮件提交

单击" **电子邮件"** 选项卡。

You can click the **Column options** button near of the bottom of the page to add or remove columns from the view：

- "日期"
- **提交 ID：** 分配给每个提交的 GUID 值。
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**
- **传递原因**
- **状态**<sup>\*</sup>

  <sup>\*</sup> 如果单击此值，将在一个飞出内容中显示详细信息。

#### <a name="admin-submission-rescan-details"></a>管理员提交重新扫描详细信息

在管理员提交中提交的邮件会重新扫描，详细信息飞出中将显示结果：

- 发件人的电子邮件身份验证是否在发送时验证失败。
- 任何可能影响或覆盖邮件裁定的策略信息。
- 当前触发结果，以查看邮件中所包含的 URL 或文件是否是恶意的。
- 来自成绩者的反馈。

如果找到了覆盖，则应该会在数分钟内完成重新扫描。 如果电子邮件身份验证没有问题，或者传递不受替代的影响，则来自成绩认证人员的反馈可能需要一天的时间。

### <a name="view-admin-url-submissions"></a>查看管理员 URL 提交

单击 **"URL"** 选项卡。

You can click the **Column options** button near of the bottom of the page to add or remove columns from the view：

- "日期"
- **提交 ID**
- **提交者**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **提交类型**
- **状态**<sup>\*</sup>

  <sup>\*</sup> 如果单击此值，将在一个飞出内容中显示详细信息。

### <a name="view-admin-attachment-submissions"></a>查看管理员附件提交

单击" **附件"** 选项卡。

You can click the **Column options** button near of the bottom of the page to add or remove columns from the view：

- "日期"
- **提交 ID**
- **提交者**<sup>\*</sup>
- **文件名**<sup>\*</sup>
- **提交类型**
- **状态**<sup>\*</sup>

  <sup>\*</sup> 如果单击此值，将在一个飞出内容中显示详细信息。

## <a name="view-user-submissions-to-microsoft"></a>查看向 Microsoft 提交用户

如果已部署报告邮件外接程序、[](enable-the-report-message-add-in.md)报告网络钓鱼外接程序或用户使用 Outlook [](enable-the-report-phish-add-in.md)[网页](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中的内置报告，您可以在"用户提交"选项卡上查看报告哪些用户。 

1. 在安全与&中心中，转到"**威胁管理** \> **提交"。**

2. 选择"**用户提交"** 选项卡，然后单击"新建 **提交"。**

You can click the **Column options** button near of the bottom of the page to add or remove columns from the view：

- **提交者**
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**

<sup>\*</sup> 如果单击此值，将在一个飞出内容中显示详细信息。

在页面顶部附近，可以输入开始日期、结束日期和 (默认情况下) 可以通过在框中输入值并单击"刷新"按钮按 **发件人** 进行 ![ 筛选 ](../../media/scc-quarantine-refresh.png) 。 Update

若要更改筛选条件，请单击"发件人 **"** 按钮并选择下列值之一：

- **发件人域**
- **主题**
- **提交者**
- **提交类型**
- **发件人 IP**

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

若要导出结果，请单击页面 **顶部附近的**"导出"，然后选择"**图表数据**"或"表 **"。** 在出现的对话框中，保存 .csv 文件。

## <a name="view-user-submissions-to-the-custom-mailbox"></a>查看自定义邮箱的用户提交

**如果** 已配置 [自定义邮箱](user-submission.md) 以接收用户报告的邮件，则还可以查看并提交已传递到报告邮箱的邮件。

1. 在安全与&中心中，转到"**威胁管理** \> **提交"。**

2. 选择" **自定义邮箱"** 选项卡。

You can click the **Column options** button near of the bottom of the page to add or remove columns from the view：

- **提交者**
- **提交者**<sup>\*</sup>
- **主题**<sup>\*</sup>
- **Sender**
- **发件人 IP**<sup>\*</sup>
- **提交类型**

在页面顶部附近，可以输入开始日期、结束日期，并且可以通过在框中输入值并单击"刷新"按钮来按"提交 ![ "进行筛选 ](../../media/scc-quarantine-refresh.png) 。 Update

若要导出结果，请单击页面 **顶部附近的**"导出"，然后选择"**图表数据**"或"表 **"。** 在出现的对话框中，保存 .csv 文件。

> [!NOTE]
> 如果组织配置为仅发送到自定义邮箱，将不会发送报告的邮件进行重新扫描，并且用户报告的邮件门户中的结果将始终为空。

## <a name="undo-user-submissions"></a>撤消用户提交

用户向自定义邮箱提交可疑电子邮件后，用户和管理员将无法撤消提交。 如果用户希望恢复电子邮件，可以在"已删除邮件"或"垃圾邮件"文件夹中进行恢复。

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>从自定义邮箱向 Microsoft 提交邮件

如果已配置自定义邮箱，以截获用户报告的邮件，而不将邮件发送到 Microsoft，您可以查找特定邮件并将其发送给 Microsoft 进行分析。 这有效地将用户提交移动到管理员提交。

在"**自定义邮箱**"选项卡上，在列表中选择一封邮件，单击"操作"按钮，然后进行以下选择之一：

- **报告干净**
- **报告网络钓鱼**
- **报告恶意软件**
- **报告垃圾邮件**

!["操作"按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
