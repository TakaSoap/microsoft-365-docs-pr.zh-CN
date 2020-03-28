---
title: 手动将邮件提交给 Microsoft 进行分析
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: '你和你的用户可以将虚假的负垃圾邮件和假肯定垃圾邮件提交给 Microsoft 进行分析。 '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032800"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>手动将邮件提交给 Microsoft 进行分析

> [!NOTE]
> 如果您是使用 Exchange Online 邮箱的 Office 365 组织中的管理员，我们建议您在 Office 365 安全性 & 合规性中心中使用提交门户。 有关详细信息，请参阅[使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。

如果组织中的用户在其收件箱中收到垃圾邮件（垃圾邮件）或网络钓鱼邮件，或者如果邮件被标记为垃圾邮件，则可能会令人沮丧。 我们不断调整垃圾邮件筛选器，使其更加准确。

您和您的用户可以通过将误报（好的电子邮件标记为 "坏"）、"漏报（允许错误邮件）" 和 "网络钓鱼邮件" 提交给 Microsoft 进行分析来帮助此过程。

> [!NOTE]
> 由于我们收到的提交量很大，我们可能无法应答所有分析请求。

## <a name="submit-false-negatives-to-microsoft"></a>将漏报提交给 Microsoft

> [!TIP]
> Outlook 和 web 上的 Outlook （以前称为 Outlook Web App）中的用户可以使用 Microsoft Outlook 的报告消息外接程序，而不是使用以下过程来报告漏报。 有关如何安装和使用此工具的信息，请参阅[Enable The Report Message 外接程序](enable-the-report-message-add-in.md)。

如果您收到一封邮件，该邮件将通过应标识为垃圾邮件或网络钓鱼的垃圾邮件筛选传递，则可以根据需要将邮件提交到 Microsoft 垃圾邮件分析和 Microsoft 仿冒分析团队。 分析师将检查邮件并将其添加到服务范围的筛选器中（如果它满足分类条件）。

1. 使用以下收件人之一创建一个新的空白电子邮件：

   - **垃圾邮件**：`junk@office365.microsoft.com`

   - **网络钓鱼**：`phish@office365.microsoft.com`

2. 将垃圾邮件或仿冒邮件拖放到新邮件中。 这会将垃圾邮件或仿冒邮件保存为新邮件中的附件。 请勿复制和粘贴邮件的内容或转发邮件（我们需要原始邮件，以便我们可以检查邮件头）。

   > [!NOTE]
   > <ul><li>您可以在新邮件中附加多封邮件。 确保所有邮件都属于同一类型： "仿冒欺诈邮件" 或 "垃圾邮件"。</li><li>保留新的邮件正文空白。<li></li>对于附加的邮件，请使用 .msg （默认 Outlook 格式）或 .eml （默认 Outlook 网页格式）格式。</li></ul>

3. 完成后，请单击 "**发送**"。

> [!TIP]
> 管理员有几种不同的方法来阻止被 misidentified 为垃圾邮件的特定邮件。 有关详细信息，请参阅[在 Office 365 中创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>向 Microsoft 提交误报

> [!TIP]
> Outlook 和 Outlook 网页版中的用户可以使用 Microsoft Outlook 的报告消息外接程序，而不是使用以下过程报告误报。 有关如何安装和使用此工具的信息，请参阅[Enable The Report Message 外接程序](enable-the-report-message-add-in.md)。

如果邮件被错误地标识为垃圾邮件，您可以将邮件提交给 Microsoft 垃圾邮件分析团队。 分析师将评估邮件，并且（取决于分析结果）可以调整服务范围的筛选器以允许邮件通过。

1. 创建一个新的空白电子邮件， `not_junk@office365.microsoft.com`作为收件人：

2. 将 misidentified 邮件拖放到新邮件中。 这会将 misidentified 邮件另存为新邮件中的附件。 请勿复制和粘贴邮件的内容或转发邮件（我们需要原始邮件，以便我们可以检查邮件头）。

   > [!NOTE]
   > <ul><li>您可以在新邮件中附加多封邮件。 确保所有邮件都属于同一类型： "仿冒欺诈邮件" 或 "垃圾邮件"。</li><li>保留新的邮件正文空白。<li></li>对于附加的邮件，请使用 .msg （默认 Outlook 格式）或 .eml （默认 Outlook 网页格式）格式。</li></ul>

3. 完成后，请单击 "**发送**"。

> [!TIP]
> 管理员有几种不同的方法允许特定邮件跳过垃圾邮件筛选。 有关详细信息，请参阅[在 Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>创建邮件流规则以接收报告给 Microsoft 的邮件副本

您可以创建邮件流规则（也称为传输规则），以查找通过使用本主题中所述的方法报告给 Microsoft 的电子邮件，并且您可以配置密件抄送收件人以接收这些报告的邮件的副本。

您可以在 Exchange 管理中心（EAC）和 PowerShell （Office 365 客户的 Exchange Online PowerShell 中创建邮件流规则;适用于独立 EOP 客户的 Exchange Online Protection PowerShell）。

### <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，需要知道什么？

- 您需要先在 Exchange Online 中分配权限，然后才能执行这些过程。 具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。 有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。

- 若要在 Exchange Online 中打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要连接到独立的 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。

- 有关 Exchange Online 和独立 EOP 中的邮件流规则的详细信息，请参阅下列主题：

  - [Exchange Online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online 中的邮件流规则条件和例外（谓词）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 EAC 创建邮件流规则以接收报告的邮件的副本

1. In the EAC, go to **Mail flow** \> **Rules**.

2. 单击 "**添加** !["](../../media/ITPro-EAC-AddIcon.png) "添加" 图标，然后选择 "**创建新规则**"。

3. 在打开的" **新规则**"窗口中，配置以下设置：

   - **名称**：输入规则的唯一描述性名称。 例如，向 Microsoft 报告的密件抄送邮件。

   - 单击“其他选项”****。

   - **在以下情况下应用此规则**：选择**收件人** \> **地址包括以下任何词语**：在显示的 "**指定字词或短语**" 对话框中，输入以下值之一， **Add** ![单击 "添加](../../media/ITPro-EAC-AddIcon.png)" "添加" 图标，然后重复此步骤，直到您输入所有值为止。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     若要编辑条目，请选择该条目**Edit** ![，然后单击](../../media/ITPro-EAC-EditIcon.png)"编辑" "编辑" 图标。 若要删除条目，请将其选中**Remove** ![，然后单击](../../media/ITPro-EAC-DeleteIcon.png)"删除删除图标"。

     完成后，请单击 **"确定"**。

   - **执行下列**操作：选择 "**将收件人** \>添加**到密件抄送" 框**。 在出现的对话框中，查找并选择要添加的收件人。 完成后，请单击 **"确定"**。

4. 您可以进行其他选择来审核规则、测试规则、在特定时间段内激活规则，以及其他设置。 建议在强制执行规则之前对其进行测试。

5. 完成时，请单击“保存”****。

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>使用 PowerShell 创建邮件流规则以接收报告的邮件的副本

本示例将新建一个名为 "密件抄送给 Microsoft" 的邮件流规则，该规则将查找通过使用本主题中所述方法报告给 Microsoft 的电子邮件，并将用户 laura@contoso.com 和 julia@contoso.com 添加为密件抄送收件人。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)。

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已将邮件流规则配置为接收报告的邮件的副本，请执行以下任一步骤：

- 在 EAC 中，转到 **"邮件流** \> **规则** \> "。 \>选择该规则，](../../media/ITPro-EAC-EditIcon.png)然后单击 "**编辑** ![编辑" 图标，并验证设置。

- 在 PowerShell 中，运行以下命令来验证设置：

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- 将测试邮件发送到其中一个报告电子邮件地址，并验证结果。
