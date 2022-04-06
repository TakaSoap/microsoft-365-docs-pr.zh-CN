---
title: 管理提交
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: seo-marvel-apr2020
description: 管理员可以了解如何使用 Microsoft 365 Defender 门户中的提交门户向 Microsoft 提交可疑电子邮件、可疑钓鱼邮件、垃圾邮件以及其他可能有害的邮件、URL 和电子邮件附件，以重新扫描。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0d699c3344cc16f3e15996139f1d2d8b608ba50
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477140"
---
# <a name="use-the-submissions-portal-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>使用提交门户将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)


在Microsoft 365邮箱Exchange Online，管理员可以使用 Microsoft 365 Defender 门户中的提交门户将电子邮件、URL 和附件提交到 Microsoft 进行扫描。

当你提交电子邮件进行分析时，你将获得：

- **电子邮件身份验证检查**：有关电子邮件身份验证在传递时通过还是失败的详细信息。
- **策略** 命中：有关可能允许或阻止传入电子邮件进入租户的任何策略的信息，覆盖我们的服务筛选器裁定。
- **有效负载信誉/触发**：邮件中任何 URL 和附件最新检查。
- **成绩分析**：由人工评分人员进行审阅，以确认邮件是否是恶意邮件。

> [!IMPORTANT]
> 负载信誉/触发和成绩分析并非在所有租户中都完成。 如果出于合规性目的数据不应离开租户边界，则阻止信息进入组织外部。

有关向 Microsoft 提交电子邮件、URL 和附件的其他方法，请参阅向 [Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com/> 打开 Microsoft 365 Defender 门户。 若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission>。

- 若要将邮件和文件提交到 Microsoft，你需要具有以下角色之一：
  - **安全管理员****或安全** 读者Microsoft 365 Defender [门户](permissions-microsoft-365-security-center.md)。
  
    请注意，查看自定义邮箱的用户提交需要这些角色之 [一，如](#view-user-submissions-to-microsoft) 本文稍后所述。

- 如果邮件在邮箱中仍然可用，并且用户或其他管理员未清除，则管理员可以提交 30 天的邮件。

- 将按照以下速率限制管理员提交：
  - 任意 15 分钟内的最大提交数：150 个提交
  - 24 小时内相同的提交：3 个提交
  - 15 分钟内相同的提交：1 个提交
  
- 有关用户如何向 Microsoft 提交邮件和文件的信息，请参阅向 [Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="report-suspicious-content-to-microsoft"></a>向 Microsoft 报告可疑内容

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to the **Submissions** page at **Actions & submissions**\>. 若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission>。

2. 在 **"提交"**![页上，验证"电子邮件"或"电子邮件附件或  URL"选项卡是否根据要报告的内容类型选中，然后单击"提交到 Microsoft 进行分析"图标。](../../media/m365-cc-sc-create-icon.png) **提交给 Microsoft 进行分析**。

3. 使用 **"提交给 Microsoft 进行分析** "飞出页面，它显示为提交内容类型 (电子邮件、URL 或电子邮件附件) 如以下部分所述。

   > [!NOTE]
   > 不允许数据离开环境的云中不可用文件和 URL 提交。 选择文件或 URL 的能力将灰出来。

### <a name="notify-users-from-within-the-portal"></a>从门户中通知用户

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to the **Submissions** page at **Email & collaboration** \> **Submissions**. 若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission>。

2. 在" **提交"** 页上，选择" **用户报告的邮件** "选项卡，然后选择要标记并通知的邮件。

3. 选择"**标记为并通知**"下拉列表，然后选择"**未找到网络钓鱼**\>或垃圾邮件的威胁 **"**。

   :::image type="content" source="../../media/unified-submission-user-reported-message.png" alt-text="&quot;提交&quot;页" lightbox="../../media/unified-submission-user-reported-message.png":::

报告的邮件将被标记为误报或漏报。 系统会自动从门户向报告邮件的用户发送电子邮件通知。

### <a name="submit-a-questionable-email-to-microsoft"></a>向 Microsoft 提交有问题的电子邮件

1. 在 **"选择提交类型** "框中，确认 **"电子邮件** "在下拉列表中选中。

2. 在 **"添加网络邮件 ID 或上载电子邮件文件** "部分，使用以下选项之一：
   - 添加电子邮件网络邮件 **ID**：这是一个 GUID 值，可用于邮件中的 **X-MS-Exchange-Organization-Network-Message-Id** 标头或隔离邮件中的 **X-MS-Office365-Filtering-Correlation-Id** 头。
   - **Upload电子邮件文件 (.msg 或 .eml) ：单击"浏览****文件"**。 在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击"打开 **"**。

3. 在 **"选择具有问题的** 收件人"框中，指定要针对其运行策略检查的收件人。 策略检查将确定电子邮件是否由于用户或组织策略而绕过扫描。

4. 在 **"选择提交到 Microsoft** 的原因"部分中，选择以下选项之一：
   - **不应阻止误报 (误报)**
   - **应已被** 阻止 (假负) ：在"电子邮件应已分类为出现的部分"中，选择下列值之一 (如果你不确定，请使用最佳判断) ：
     - **网络钓鱼**
     - **恶意软件**
     - **垃圾邮件**

5. 完成后，请单击“**提交**”。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-flyout-email.png" alt-text="新 URL 提交过程" lightbox="../../media/submission-flyout-email.png":::

### <a name="send-a-suspect-url-to-microsoft"></a>向 Microsoft 发送可疑 URL

1. 在 **"选择提交类型"框中** ，从下拉列表中选择" **URL** "。

2. 在出现的 **"URL** "框中，输入完整的 URL (例如，) `https://www.fabrikam.com/marketing.html` 。

3. 在 **"选择提交到 Microsoft** 的原因"部分中，选择以下选项之一：
   - **不应阻止误报 (误报)**
   - **应已被阻止 (假负)**：在"此 **URL** 应已分类为出现的部分"中，选择下列值之一 (如果你不确定，请使用最佳判断) ：
     - **网络钓鱼**
     - **恶意软件**

4. 完成后，请单击“**提交**”。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-url-flyout.png" alt-text="&quot;新建电子邮件&quot;提交过程" lightbox="../../media/submission-url-flyout.png":::

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>将可疑的电子邮件附件提交给 Microsoft

1. 在" **选择提交类型"框中** ，从下拉列表 **中选择** "电子邮件附件"。

2. 在出现的 **"文件** "部分，单击" **浏览文件"**。 在打开的对话框中，查找并选择该文件，然后单击"打开 **"**。

3. 在 **"选择提交到 Microsoft** 的原因"部分中，选择以下选项之一：
   - **不应阻止误报 (误报)**
   - 应已被阻止 **(假负)**：在"此文件应已分类为出现的部分"中，选择下列值之一 (如果你不确定，请使用最佳判断) ：
     - **网络钓鱼**
     - **恶意软件**

4. 完成后，请单击“**提交**”。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/submission-file-flyout.png" alt-text="&quot;新建附件&quot;提交过程" lightbox="../../media/submission-file-flyout.png":::

> [!NOTE]
> 如果恶意软件筛选将邮件附件替换为"恶意软件警报Text.txt文件，则需要从隔离区提交包含原始附件的原始邮件。 有关隔离以及如何释放包含恶意软件误报的邮件详细信息，请参阅以管理员角色管理隔离的邮件 [和文件](manage-quarantined-messages-and-files.md)。

## <a name="view-admin-submissions-to-microsoft"></a>查看向 Microsoft 提交的管理员

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to the **Submissions** page at **Actions & submissions**\>. 若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission>。

2. 在 **"提交"** 页上，验证" **电子邮件**、 **URL** 或电子邮件附件 **"** 选项卡是否被选中。

   - 可以通过单击可用列标题来对条目进行排序。 单击 **"自定义列** "最多可显示七列。 默认值标有星号（<sup>\*</sup>）：
     - **提交名称**<sup>\*</sup>
     - **发件人**<sup>\*</sup>
     - **收件人**
     - **提交日期**<sup>\*</sup>
     - **提交原因**<sup>\*</sup>
     - **状态**<sup>\*</sup>
     - **结果**<sup>\*</sup>
     - **筛选裁定**
     - **传递/阻止原因**
     - **提交 ID**
     - **网络消息 ID/对象 ID**
     - **方向**
     - **发件人 IP**
     - **BCL (批量兼容)**
     - **目标**
     - **策略操作**
     - **提交者**
     - **网络钓鱼模拟**
     - **标记**<sup>\*</sup>
     - **允许**

     完成后，单击“**应用**”。

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-customize-columns.png" alt-text="管理员提交的&quot;新自定义&quot;列选项" lightbox="../../media/admin-submission-customize-columns.png":::

   - 若要筛选条目，请单击"筛选器 **"**。 以下筛选器可用：
     - **提交日期**：**开始日期和****结束日期**。
     - **提交 ID**：分配给每个提交的 GUID 值。
     - **网络消息 ID**
     - **Sender**
     - **收件人**
     - **名称**
     - **提交者**
     - **提交原因**
     - **状态**
     - **Tags**

     完成后，单击“**应用**”。

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-filters.png" alt-text="管理员提交的&quot;新建筛选器&quot;选项" lightbox="../../media/admin-submission-filters.png":::

   - 若要对条目进行分组 **，请单击"** 分组"，然后从下拉列表中选择下列值之一：
     - **无**
     - **类型**
     - **原因**
     - **状态**
     - **结果**
     - **Tags**

   - 若要导出条目，请单击"导出 **"**。 在出现的对话框中，保存.csv文件。

### <a name="admin-submission-result-details"></a>管理员提交结果详细信息

在管理员提交中提交的邮件会进行审阅，并且结果会显示在提交详细信息飞出中：

- 发件人的电子邮件身份验证是否在发送时验证失败。
- 任何可能影响或覆盖邮件裁定的策略信息。
- 当前触发结果，以查看邮件中所包含的 URL 或文件是否是恶意的。
- 来自成绩者的反馈。

如果找到替代，则结果应在几分钟后可用。 如果电子邮件身份验证没有问题，或者传递不受替代的影响，则来自成绩认证人员的反馈可能需要一天的时间。

## <a name="view-user-submissions-to-microsoft"></a>查看向 Microsoft 提交用户

如果已部署报告邮件外接程序、[](enable-the-report-message-add-in.md)报告网络钓鱼外接程序或用户使用 [Outlook 网页版](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 中的[](enable-the-report-phish-add-in.md)内置报告，您可以在"用户报告的邮件"选项卡上查看报告的用户。

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to the **Submissions** page at **Actions & submissions**\>. 若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission>。

2. 在" **提交"** 页上，选择" **用户报告的邮件"** 选项卡。

   - 可以通过单击可用列标题来对条目进行排序。 单击 **"自定义列** "以显示选项。 默认值标有星号（<sup>\*</sup>）：

     - **电子邮件主题**<sup>\*</sup>
     - **报告者**<sup>\*</sup>
     - **报告的日期**<sup>\*</sup>
     - **发件人**<sup>\*</sup>
     - **报告的原因**<sup>\*</sup>
     - **结果**<sup>\*</sup>
     - **邮件报告 ID**
     - **网络消息 ID**
     - **发件人 IP**
     - **报告自**
     - **网络钓鱼模拟**
     - **转换为管理员提交**
     - **标记**<sup>\*</sup>
     - **标记为**<sup>\*</sup>
     - **标记者**
     - **标记的日期**

     完成后，单击“**应用**”。

   - 若要筛选条目，请单击"筛选器 **"**。 以下筛选器可用：
     - **报告的日期****：开始日期** 和 **结束日期**。
     - **报告者**
     - **电子邮件主题**
     - **邮件报告 ID**
     - **网络消息 ID**
     - **Sender**
     - **报告的原因****：非垃圾邮件**、**网络钓鱼** 或 **垃圾邮件**
     - **报告来源**： **Microsoft 外接程序** 或 **第三方外接程序**
     - **网络钓鱼模拟**： **是** 或 **否**
     - **转换为管理员提交**： **是** 或 **否**
     - **Tags**

     完成后，单击“**应用**”。

     > [!div class="mx-imgBorder"]
     > :::image type="content" source="../../media/admin-submission-reported-messages.png" alt-text="用户提交的&quot;新建筛选器&quot;选项" lightbox="../../media/admin-submission-reported-messages.png":::

   - 若要对条目进行分组 **，请单击"** 分组"，然后从下拉列表中选择下列值之一：
     - **无**
     - **原因**
     - **Sender**
     - **报告者**
     - **结果**
     - **报告自**
     - **网络钓鱼模拟**
     - **转换为管理员提交**
     - **Tags**
   
   - 若要导出条目，请单击"导出 **"**。 在出现的对话框中，保存.csv文件。

> [!NOTE]
> 如果组织配置为仅将用户报告的邮件发送到自定义邮箱，将不会发送报告的邮件进行重新扫描，并且 **"用户** 报告的邮件"中的结果将始终为空。

### <a name="undo-user-submissions"></a>撤消用户提交

用户向自定义邮箱提交可疑电子邮件后，用户和管理员将无法撤消提交。 如果用户希望恢复电子邮件，可以在"已删除邮件"或"垃圾邮件"文件夹中进行恢复。

### <a name="converting-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission"></a>将用户报告的邮件从自定义邮箱转换为管理员提交 

如果已配置自定义邮箱，以截获用户报告的邮件，而不将邮件发送到 Microsoft，您可以查找特定邮件并将其发送给 Microsoft 进行分析。

在" **用户报告的邮件** "选项卡上，在列表中选择一封邮件，单击"提交给 **Microsoft** 进行分析"，然后从下拉列表中选择下列值之一：

- **报告干净**
- **报告网络钓鱼**
- **报告恶意软件**
- **报告垃圾邮件**
- **触发调查**

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/admin-submission-main-action-button.png" alt-text="&quot;操作&quot;按钮上的&quot;新建&quot;选项" lightbox="../../media/admin-submission-main-action-button.png":::
