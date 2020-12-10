---
title: 配置垃圾邮件筛选策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中查看、创建、修改和删除反垃圾邮件策略。
ms.openlocfilehash: 2601e4b7b360ce45fbece3e66b5aa09cd512f68c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572809"
---
# <a name="configure-anti-spam-policies-in-eop"></a>在 EOP 中配置反垃圾邮件策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在有 Exchange Online 的 Microsoft 365 组织，或没有 Exchange Online 邮箱的 Exchange Online Protection (EOP) 组织中，EOP 都会自动保护入站电子邮件免受垃圾邮件威胁。 EOP 使用反垃圾邮件策略（亦称为“垃圾邮件筛选策略”或“内容筛选策略”），作为组织全面抵御垃圾邮件的措施的一部分。 有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。

管理员可以查看、编辑和配置（但不能删除）默认反垃圾邮件策略。 还可以创建应用于组织中特定用户、组或域的自定义反垃圾邮件策略，以实现更细致的控制。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

若要配置反垃圾邮件策略，可以使用安全与合规中心，也可以使用 PowerShell（适用于有 Exchange Online 的 Microsoft 365 组织的 Exchange Online PowerShell，或适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell）。

反垃圾邮件策略的基本要素如下：

- **垃圾邮件筛选策略**：指定根据垃圾邮件筛选裁定执行的操作和通知选项。
- **垃圾邮件筛选规则**：指定垃圾邮件筛选策略的优先级和收件人筛选器（即对谁应用策略）。

在安全与合规中心内管理反垃圾邮件策略时，这两个要素之间的区别并不明显：

- 在创建反垃圾邮件策略时，实际上是同时创建了垃圾邮件筛选规则和关联的垃圾邮件筛选策略，并对二者使用相同的名称。
- 如果你修改反垃圾邮件策略，与名称、优先级、启用/禁用以及收件人筛选器有关的设置会修改垃圾邮件筛选规则。 其他所有设置会修改关联的垃圾邮件筛选策略。
- 如果你删除反垃圾邮件策略，垃圾邮件筛选规则和关联的垃圾邮件筛选策略也会随之删除。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本主题后面的[使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置反垃圾邮件策略](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies)部分。

每个组织都有名为“默认”的内置反垃圾邮件策略，它具有以下属性：

- 该策略会应用于组织中的所有收件人，即使没有与此策略关联的垃圾邮件筛选规则（亦称为“收件人筛选器”），也不例外。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略始终具有更高的优先级。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

为了提高垃圾邮件筛选的有效性，可以创建自定义反垃圾邮件策略，它包含应用于特定用户或用户组的更严格设置。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须分配有安全与合规中心内的权限，才能执行本文中的步骤：
  - 必须是 **“组织管理”** 或 **“安全管理员”** 角色组的成员，才能添加、修改和删除反垃圾邮件策略。
  - 若要获得对受限用户门户的只读访问权限，必须成为 **全球读者** 或 **安全读者** 角色组的成员。

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关建议的反垃圾软件策略设置，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>使用安全与合规中心创建反垃圾邮件策略

在安全与合规中心内创建自定义反垃圾邮件策略，会同时创建垃圾邮件筛选规则和关联的垃圾邮件筛选策略，并对二者使用相同的名称。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **“反垃圾邮件设置”** 页上，单击 **“创建策略”**。

3. 在随即打开的 **“新建垃圾邮件筛选策略”** 浮出控件中，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。 请勿使用以下字符：`\ % & * + / = ? { } | < > ( ) ; : , [ ] "`。

      如果以前在 Exchange 管理中心 (EAC) 内创建了包含这些字符的反垃圾邮件策略，应在 PowerShell 中重命名反垃圾邮件策略。 有关说明，请参阅本主题稍后将介绍的[使用 PowerShell 修改垃圾邮件筛选规则](#use-powershell-to-modify-spam-filter-rules)部分。

   - **说明**：输入策略的可选说明。

4. （可选）展开 **“垃圾邮件和批量操作”** 部分，然后验证或配置以下设置：

   - **选择要对传入的垃圾邮件和群发电子邮件执行的操作**：选择或审阅根据以下垃圾邮件筛选裁定而对邮件执行的操作：

     - **垃圾邮件**
     - **高可信度垃圾邮件**
     - **钓鱼电子邮件**
     - **高可信度钓鱼电子邮件**
     - **群发电子邮件**

     下表介绍了可以根据垃圾邮件筛选裁定而执行的操作。

     - 复选标记 ( ![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) 表示操作可以执行（并不是所有操作都适用于所有垃圾邮件筛选裁定）。
     - 复选标记后面的星号 (<sup>\*</sup>) 表示垃圾邮件筛选裁定对应的默认操作。

     ****

     |操作|垃圾邮件|高<br/>置信<br/>垃圾邮件 (spam)|网络钓鱼<br/>电子邮件|高<br/>置信<br/>仿冒<br/>电子邮件|批量邮件<br/>电子邮件|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**将邮件移动到“垃圾邮件”文件夹**：邮件递送到邮箱，并移动到“垃圾邮件”文件夹。<sup>1</sup>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**添加 X 标头**：向邮件头添加 X 标头，并将邮件递送到邮箱。 <p> 稍后将在 **“添加此 X 标头文本”** 框中，输入 X 标头字段名称（而不是值）。 <p> 对于 **“垃圾邮件”** 和 **“高可信度垃圾邮件”** 裁定，邮件移动到“垃圾邮件”文件夹。<sup>1、2</sup>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**在主题行前面追加文本**：向邮件的主题行开头添加文本。 邮件递送到邮箱，并移动到“垃圾邮件”文件夹。<sup>1、2</sup> <p> 稍后将在 **“在主题行前面添加此文本作为前缀”** 框中输入文本。|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**将邮件重定向到电子邮件地址**：将邮件发送给其他收件人，而不是目标收件人。 <p> 稍后将在 **“重定向到此电子邮件地址”** 框中指定收件人。|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**删除邮件**：无提示删除整个邮件，包括所有附件。|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**隔离邮件**：将邮件发送到隔离，而不是目标收件人。 <p> 稍后将在 **“隔离”** 框中指定所需的邮件隔离时长。|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**无操作**|||||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     > <sup>1</sup>在 Exchange Online 中，如果邮箱启用了垃圾邮件规则（默认处于启用状态），邮件会移动到“垃圾邮件”文件夹。 有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。
     >
     > 在 EOP 保护本地 Exchange 邮箱的独立 EOP 环境中，需要在本地 Exchange 中配置邮件流规则（亦称为“传输规则”），以转换 EOP 垃圾邮件筛选裁定，这样垃圾邮件规则才能将邮件移动到“垃圾邮件”文件夹。 有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。
     >
     > <sup>2</sup>可以将此使用值用作邮件流规则（亦称为“传输规则”）中的条件来筛选或路由邮件。

   - **选择阈值**：指定触发 **“群发电子邮件”** 垃圾邮件筛选裁定的指定操作的邮件批量投诉级别 (BCL)（大于指定值，而不是小于或等于指定值）。 值越高，邮件就越不理想（是垃圾邮件的可能性就越大）。 默认值为 7。 有关详细信息，请参阅 [EOP 中的批量投诉级别 (BCL)](bulk-complaint-level-values.md)，以及[垃圾邮件与群发电子邮件有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

     默认情况下，在反垃圾邮件策略中，仅在 PowerShell 中可配置的设置 _MarkAsSpamBulkMail_ 的值为 `On`。 此设置极大地影响 **“群发电子邮件”** 筛选裁定结果：

     - **_MarkAsSpamBulkMail_ 的值为“On”**：大于阈值的 BCL 转换为对应于 **“垃圾邮件”** 筛选裁定的 SCL 6，并会对邮件执行 **“群发电子邮件”** 筛选裁定对应的操作。

     - **_MarkAsSpamBulkMail_ 的值为“Off”**：虽然邮件已有 BCL 标记，但 _不会_ 根据 **“群发电子邮件”** 筛选裁定执行任何操作。 实际上，BCL 阈值和 **“群发电子邮件”** 筛选裁定对应的操作不相关。

   - **隔离**：指定在选择 **“隔离邮件”** 作为垃圾邮件筛选裁定对应的操作时的邮件隔离时长。 在此时间段到期后，邮件就会被删除。 默认值为 30 天。 有效值介于 1 和 30 天之间。 若要了解隔离，请参阅以下主题：

     - [EOP 中隔离的邮件](quarantine-email-messages.md)
     - [在 EOP 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)
     - [在 EOP 中以用户身份查找和释放已隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

   - **添加此 X 标头文本**：只有当你选择 **“添加 X 标头”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。 指定的值是添加到邮件头的标头字段 *名称*。 标头字段 *值* 始终为 `This message appears to be spam`。

     长度上限为 255 个字符，且值不得包含空格或冒号 (:)。

     例如，如果你输入值 `X-This-is-my-custom-header`，则添加到邮件的 X 标头为 `X-This-is-my-custom-header: This message appears to be spam.`

     如果你输入的值包含空格或冒号 (:)，输入值会遭忽略，且添加到邮件中的是默认 X 标头 (`X-This-Is-Spam: This message appears to be spam.`)。

   - **在主题行前面添加此文本作为前缀**：只有当你选择 **“在主题行前面追加文本”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。 输入要添加到邮件主题行开头的文本。

   - **重定向到此电子邮件地址**：只有当你选择 **“将邮件重定向到电子邮件地址”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。 输入要将邮件递送到的电子邮件地址。 可以输入多个值，用分号 (;) 分隔。

   - **安全提示**：“安全提示”默认处于启用状态，但你可以通过取消选中 **“开”** 复选框来禁用它。 若要详细了解安全提示，请参阅 [电子邮件安全提示](safety-tips-in-office-365.md)。

   **零时差自动清除** 设置：ZAP 检测已递送到 Exchange Online 邮箱的邮件，并对邮件执行操作。 若要详细了解 ZAP，请参阅[零时差自动清除 - 抵御垃圾邮件和恶意软件](zero-hour-auto-purge.md)。

   - **垃圾邮件 ZAP**：默认启用 ZAP 进行垃圾邮件检测，但你可以通过取消选中“**开**”复选框来禁用它。

   - **钓鱼邮件 ZAP**：默认启用 ZAP 进行钓鱼邮件检测，但你可以通过取消选中“**开**”复选框来禁用它。

5. （可选）展开“**允许列表**”部分，通过电子邮件地址或电子邮件域配置允许跳过垃圾邮件筛选的邮件发件人：

   > [!CAUTION]
   >
   > - 在此处添加域之前，请慎重考虑。 有关详细信息，请参阅[在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)
   >
   > - 切勿将接受的域（你拥有的域）或公共域（例如，microsoft.com 或 office.com）添加到允许的域列表中。 这会允许攻击者将不使用垃圾邮件筛选的电子邮件发送到你的组织。

   - **允许发件人**：单击 **“编辑”**。 在随即显示的 **“允许的发件人列表”** 浮出控件中，执行以下步骤：

      a. 输入发件人的电子邮件地址。 可以指定多个电子邮件地址，用分号 (;) 分隔。

      b. 单击 ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 添加发件人。

      根据需要重复执行这些步骤（次数不限）。

      你添加的发件人显示在浮出控件上的 **“允许的发件人”** 部分中。 若要删除发件人，请单击 ![“删除”图标](../../media/scc-remove-icon.png)。

      完成后，单击 **“保存”**。

   - **允许域**：单击 **“编辑”**。 在随即显示的 **“允许的域列表”** 浮出控件中，执行以下步骤：

      a. 输入域。 可以指定多个域，用分号 (;) 分隔。

      b. 单击 ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 添加域。

      根据需要重复执行这些步骤（次数不限）。

      你添加的域显示在浮出控件上的 **“允许的域”** 部分中。 若要删除域，请单击 ![“删除”图标](../../media/scc-remove-icon.png)。

      完成后，单击 **“保存”**。

6. （可选）展开 **“阻止列表”** 部分，通过电子邮件地址或电子邮件域配置始终被标记为“高可信度垃圾邮件”的邮件发件人：

   > [!NOTE]
   > 手动阻止域并不危险，但可能会增加管理工作量。 有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。

   - **阻止发件人**：单击 **“编辑”**。 在随即显示的 **“阻止的发件人列表”** 浮出控件中，执行以下步骤：

      a. 输入发件人的电子邮件地址。 可以指定多个电子邮件地址，用分号 (;) 分隔。 不允许使用通配符 (*)。

      b. 单击 ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 添加发件人。

      根据需要重复执行这些步骤（次数不限）。

      你添加的发件人显示在浮出控件上的 **“阻止的发件人”** 部分中。 若要删除发件人，请单击 ![“删除”按钮](../../media/scc-remove-icon.png)。

      完成后，单击 **“保存”**。

   - **阻止域**：单击 **“编辑”**。 在随即显示的 **“阻止的域列表”** 浮出控件中，执行以下步骤：

      a. 输入域。 可以指定多个域，用分号 (;) 分隔。 不允许使用通配符 (*)。

      b. 单击 ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 添加域。

      根据需要重复执行这些步骤（次数不限）。

      你添加的域显示在浮出控件上的 **“阻止的域”** 列表中。 若要删除域，请单击 ![“删除”按钮](../../media/scc-remove-icon.png)。

      完成后，单击 **“保存”**。

7. （可选）展开 **“国际垃圾邮件”** 部分，配置被垃圾邮件筛选阻止的电子邮件语言或源国家/地区：

   - **筛选用以下语言编写的电子邮件**：此设置默认处于禁用状态（**“状态”：“关”**）。 单击 **“编辑”**。 在随即显示的 **“国际垃圾邮件设置”** 浮出控件中，配置以下设置：

     - **筛选用以下语言编写的电子邮件**：选中此复选框，以启用这项设置。 取消选中此复选框可禁用这项设置。

     - 单击此框，然后开始键入语言 *名称*。 此时会显示受支持语言的筛选列表，以及相应的 ISO 639-2 语言代码。 选中找到的所需语言。 根据需要重复执行此步骤（次数不限）。

       你选择的语言列表显示在浮出控件上。 若要删除语言，请单击 ![“删除”按钮](../../media/scc-remove-icon.png)。

     完成后，单击 **“保存”**。

   - **筛选以下国家或地区发送来的电子邮件**：此设置默认处于禁用状态（**“状态”：“关”**）。 若要启用此设置，请单击 **“编辑”**。 在随即显示的 **“国际垃圾邮件设置”** 浮出控件中，配置以下设置：

     - **筛选以下国家或地区发送来的电子邮件**：选中此复选框，以启用这项设置。 取消选中此复选框可禁用这项设置。

     - 单击此框，然后开始键入国家或地区 *名称*。 此时会显示受支持国家/地区的筛选列表，以及相应的 ISO 3166-1 国家/地区代码（由两个字母组成）。 选中找到的所需国家或地区。 根据需要重复执行此步骤（次数不限）。

       你选择的国家/地区列表显示在浮出控件上。 若要删除国家或地区，请单击 ![“删除”按钮](../../media/scc-remove-icon.png)。

     完成后，单击 **“保存”**。

8. 可选 **“垃圾邮件属性”** 部分包含默认禁用的高级垃圾邮件筛选 (ASF) 设置。 ASF 设置即将弃用，其功能正在合并到筛选堆栈的其他部分中。 建议在反垃圾邮件策略中保持所有这些 ASF 设置的禁用状态不变。

   若要详细了解这些设置，请参阅 [EOP 中的高级垃圾邮件筛选设置](advanced-spam-filtering-asf-options.md)。

9. （必需）展开 **“应用于”** 部分，以确定向哪些内部收件人应用策略。

    只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

    若要查看所有可配置的条件，最简单的方法是单击 **“添加条件”** 三次。 若要删除不需要配置的条件，可以单击 ![“删除”按钮](../../media/scc-remove-icon.png)。

    - **收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。 单击 **“添加标记”** 框，以查看并选择域。 如果有多个域，请再次单击 **“添加标记”** 框来选择其他域。

    - **收件人是**：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。 单击 **“添加标记”**，然后开始键入内容来筛选列表。 若要选择其他收件人，请再次单击 **“添加标记”** 框。

    - **收件人是以下组的成员**：指定组织中的一个或多个组。 单击 **“添加标记”**，然后开始键入内容来筛选列表。 若要选择其他收件人，请再次单击 **“添加标记”** 框。

    - **下列情况除外**：若要添加规则的例外情况，请单击 **“添加条件”** 三次，以查看所有可配置的例外。 设置和行为与条件完全相同。

10. 完成后，单击 **“保存”**。

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>使用安全与合规中心查看反垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开反垃圾邮件策略：

   - 名为 **“默认垃圾邮件筛选策略”** 的默认策略。

   - 你创建的自定义策略，其中 **“类型”** 列中的值为 **“自定义反垃圾邮件策略”**。

3. 随即出现的展开策略详细信息中显示了重要的策略设置。 若要查看更多详情，请单击 **“编辑策略”**。

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>使用安全与合规中心修改反垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开反垃圾邮件策略：

   - 名为 **“默认垃圾邮件筛选策略”** 的默认策略。

   - 你创建的自定义策略，其中 **“类型”** 列中的值为 **“自定义反垃圾邮件策略”**。

3. 单击 **“编辑策略”**。

对于自定义反垃圾邮件策略，随即显示的浮出控件中的可配置设置与[使用安全与合规中心创建反垃圾邮件策略](#use-the-security--compliance-center-to-create-anti-spam-policies)部分中介绍的设置完全相同。

对于名为 **“默认垃圾邮件筛选策略”** 的默认反垃圾邮件策略，没有 **“应用于”** 部分（此策略应用于所有人），且无法重命名此策略。

若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。

### <a name="enable-or-disable-anti-spam-policies"></a>启用或禁用反垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开已创建的自定义策略（**“类型”** 列中的值为 **“自定义反垃圾邮件策略”**）。

3. 在随即显示的展开策略详细信息中，注意 **“开”** 列中的值。

   将切换开关移动到左侧可禁用策略： ![切换开关关闭](../../media/scc-toggle-off.png)

   将切换开关移动到右侧可启用策略： ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

无法禁用默认反垃圾邮件策略。

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>设置自定义反垃圾邮件策略的优先级

默认情况下，反垃圾邮件策略根据创建顺序来获得优先级（新策略的优先级低于旧策略）。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

自定义反垃圾邮件策略按处理顺序显示（第一个策略的 **“优先级”** 值为“0”）。 名为 **“默认垃圾邮件筛选策略”** 的默认反垃圾邮件策略的优先级值为 **“最低”**，你无法更改此值。

 **注意**：在安全与合规中心内，只能更改已创建的反垃圾邮件策略的优先级。 在 PowerShell 中，可以在创建垃圾邮件筛选规则时替代默认优先级（这可能会影响现有规则的优先级）。

若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **“反垃圾邮件设置”** 页上，查找 **“类型”** 列中的值为 **“自定义反垃圾邮件策略”** 的策略。 注意 **“优先级”** 列中的值：

   - 优先级最高的自定义反垃圾邮件策略的值为 ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) **0**。

   - 优先级最低的自定义反垃圾邮件策略的值为 ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) **n**（例如，![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) **3**）。

   - 如果有三个或更多个自定义反垃圾邮件策略，介于最高和最低优先级之间的策略的值为 ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png)![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) **n**（例如，![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png)![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) **2**）。

3. 单击 ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) 或 ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) 在优先级列表中上移或下移自定义反垃圾邮件策略。

### <a name="configure-end-user-spam-notifications"></a>配置最终用户垃圾邮件通知

如果垃圾邮件筛选裁定隔离了邮件，你可以配置最终用户垃圾邮件通知，让收件人知道向他们发送的邮件发生了什么。 若要详细了解这些通知，请参阅 [ EOP 中的最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开反垃圾邮件策略：

   - 名为 **“默认垃圾邮件筛选策略”** 的默认策略。

   - 你创建的自定义策略，其中 **“类型”** 列中的值为 **“自定义反垃圾邮件策略”**。

3. 在随即显示的展开策略详细信息中，单击 **“配置最终用户垃圾邮件通知”**。

4. 在随即打开的 **\<Policy Name\>** 对话框中，配置以下设置：

   - **启用最终用户垃圾邮件通知**：选中此复选框，以启用通知。 取消选中此复选框可禁用通知。

   - **发送最终用户垃圾邮件通知的间隔天数**：选择通知发送频率。 默认值为 3 天。 可输入介于 1 和 15 天之间的值。

     在 24 小时内，有 3 个从以下时间开始计时的最终用户垃圾邮件通知周期：01:00 UTC、08:00 UTC 和 16:00 UTC。

     > [!NOTE]
     > 如果我们在上一个周期中错过了通知，则后续周期会推送通知。 这可能会在同一天内显示多个通知。

   - **通知语言**：单击下拉列表，并从列表中选择可用语言。 默认值是“默认”（即英语）。

   完成时，请单击“保存”。

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>使用安全与合规中心删除反垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **“反垃圾邮件设置”** 页上，单击 ![“展开”图标](../../media/scc-expand-icon.png) 展开要删除的自定义策略（**“类型”** 列中的值为 **“自定义反垃圾邮件策略”**）。

3. 在随即显示的展开策略详细信息中，单击 **“删除策略”**。

4. 在随即显示的警告对话框中，单击 **“是”**。

无法删除默认策略。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置反垃圾邮件策略

如前文所述，反垃圾邮件策略由垃圾邮件筛选策略和垃圾邮件筛选规则组成。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，垃圾邮件筛选策略与垃圾邮件筛选规则之间的区别很明显。 可以使用 **\*-HostedContentFilterPolicy** cmdlet 管理垃圾邮件筛选策略，并使用 **\*-HostedContentFilterRule** cmdlet 管理垃圾邮件筛选规则。

- 在 PowerShell 中，先创建垃圾邮件筛选策略，再创建确定向哪个策略应用规则的垃圾邮件筛选规则。
- 在 PowerShell 中，分别修改垃圾邮件筛选策略和垃圾邮件筛选规则中的设置。
- 如果你通过 PowerShell 删除垃圾邮件筛选策略，相应的垃圾邮件筛选规则不会自动随之删除，反之亦然。

以下反垃圾邮件策略设置仅在 PowerShell 中可配置：

- 默认情况下，_MarkAsSpamBulkMail_ 参数的值为 `On`。 本主题前面的[使用安全与合规中心创建反垃圾邮件策略](#use-the-security--compliance-center-to-create-anti-spam-policies)部分中介绍了此设置的效果。

- 以下设置用于最终用户垃圾邮件隔离通知：

  - _DownloadLink_ 参数：显示或隐藏 Outlook 垃圾邮件报告工具的链接。

  - _EndUserSpamNotificationCustomSubject_ 参数：可用于自定义通知的主题行。

### <a name="use-powershell-to-create-anti-spam-policies"></a>使用 PowerShell 创建反垃圾邮件策略

在 PowerShell 中创建反垃圾邮件策略的过程分为两步：

1. 创建垃圾邮件筛选策略。
2. 创建垃圾邮件筛选规则，它指定了向哪个垃圾邮件筛选策略应用规则。

 **注意**：

- 可以新建垃圾邮件筛选规则，并向它分配未关联的现有垃圾邮件筛选策略。 垃圾邮件筛选规则不能与多个垃圾邮件筛选策略关联。

- 可以在 PowerShell 中对新垃圾邮件筛选策略配置以下设置（在安全与合规中心内，只有在创建策略后，才能配置这些设置）：

  - 新建禁用的策略（在 **New-HostedContentFilterRule** cmdlet 上 _Enabled_ 为 `$false`）。
  - 在创建过程中，在 **New-HostedContentFilterRule** cmdlet 上设置策略优先级（_优先级_ _\<Number\>_）。

- 在 PowerShell 中新建的垃圾邮件筛选策略在安全与合规中心内不可见，除非你将策略分配到垃圾邮件筛选规则。

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>第 1 步：使用 PowerShell 创建垃圾邮件筛选策略

若要创建垃圾邮件筛选策略，请使用以下语法：

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

下面的示例使用以下设置创建名为“Contoso Executives”的垃圾邮件筛选策略：

- 当垃圾邮件筛选裁定为“垃圾邮件”或“高可信度垃圾邮件”时隔离邮件。

- BCL 6 触发“群发电子邮件”垃圾邮件筛选裁定对应的操作。

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-HostedContentFilterPolicy** 和 **Set-HostedContentFilterPolicy** 包含旧的 _ZapEnabled_ 参数，以及新的 _PhishZapEnabled_ 和 _SpamZapEnabled_ 参数。 _ZapEnabled_ 参数已在 2020 年 2 月遭弃用。 _PhishZapEnabled_ 和 _SpamZapEnabled_ 参数用于继承 _ZapEnabled_ 参数的值。 不过，如果你在命令中使用 _PhishZapEnabled_ 和 _SpamZapEnabled_ 参数，或在安全与合规中心内的反垃圾邮件策略中使用 **“垃圾邮件 ZAP”** 或 **“钓鱼邮件 ZAP”** 设置，_ZapEnabled_ 参数的值会遭忽略。 也就是说，请勿使用 _ZapEnabled_ 参数；而是改用 _PhishZapEnabled_ 和 _SpamZapEnabled_ 参数。

若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>第 2 步：使用 PowerShell 创建垃圾邮件筛选规则

若要创建垃圾邮件筛选规则，请使用以下语法：

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

下面的示例使用以下设置新建名为“Contoso Executives”的垃圾邮件筛选规则：

- 名为“Contoso Executives”的垃圾邮件筛选策略与此规则关联。

- 此规则应用于“Contoso Executives Group”组中的成员。

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

若要详细了解语法和参数，请参阅 [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule)。

### <a name="use-powershell-to-view-spam-filter-policies"></a>使用 PowerShell 查看垃圾邮件筛选策略

若要返回所有垃圾邮件筛选策略的摘要列表，请运行以下命令：

```PowerShell
Get-HostedContentFilterPolicy
```

若要返回特定垃圾邮件筛选策略的详细信息，请使用以下语法：

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

下面的示例返回名为“Executives”的垃圾邮件筛选策略的所有属性值。

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)。

### <a name="use-powershell-to-view-spam-filter-rules"></a>使用 PowerShell 查看垃圾邮件筛选规则

若要查看现有垃圾邮件筛选规则，请使用以下语法：

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

若要返回所有垃圾邮件筛选规则的摘要列表，请运行以下命令：

```PowerShell
Get-HostedContentFilterRule
```

若要按已启用或已禁用规则筛选列表，请运行以下命令：

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

若要返回特定垃圾邮件筛选规则的详细信息，请使用以下语法：

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

下面的示例返回名为“Contoso Executives”的垃圾邮件筛选规则的所有属性值。

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

若要详细了解语法和参数，请参阅 [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule)。

### <a name="use-powershell-to-modify-spam-filter-policies"></a>使用 PowerShell 修改垃圾邮件筛选策略

除了以下几项之外，在 PowerShell 中修改垃圾邮件筛选策略时可用的设置，与本主题前面的[第 1 步：使用 PowerShell 创建垃圾邮件筛选策略](#step-1-use-powershell-to-create-a-spam-filter-policy)部分中介绍的可用于创建策略的设置相同。

- 只有在 PowerShell 中修改垃圾邮件筛选策略时，才能使用 _MakeDefault_ 开关，它可将指定策略转换为默认策略（应用于所有人，优先级值始终为 **“最低”**，且无法删除）。

- 无法重命名垃圾邮件筛选策略（**Set-HostedContentFilterPolicy** cmdlet 没有 _Name_ 参数）。 在安全与合规中心内重命名反垃圾邮件策略时，只是在重命名垃圾邮件筛选 _规则_。

若要修改垃圾邮件筛选策略，请使用以下语法：

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)。

### <a name="use-powershell-to-modify-spam-filter-rules"></a>使用 PowerShell 修改垃圾邮件筛选规则

在 PowerShell 中修改垃圾邮件筛选规则时，唯一不可用的设置是，可用于创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有垃圾邮件筛选规则，请参阅下一部分。

否则，在 PowerShell 中修改垃圾邮件筛选规则时，将无法使用其他任何设置。 创建规则时可用的设置，与本主题前面的[第 2 步：使用 PowerShell 创建垃圾邮件筛选规则](#step-2-use-powershell-to-create-a-spam-filter-rule)部分中介绍的设置相同。

若要修改垃圾邮件筛选规则，请使用以下语法：

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

下面的示例重命名现有名为“`{Fabrikam Spam Filter}`”的垃圾邮件筛选规则（可能无法在安全与合规中心内重命名）。

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

若要详细了解语法和参数，请参阅 [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule)。

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>使用 PowerShell 启用或禁用垃圾邮件筛选规则

在 PowerShell 中启用或禁用垃圾邮件筛选规则会启用或禁用整个反垃圾邮件策略（即垃圾邮件筛选规则和分配的垃圾邮件筛选策略）。 无法启用或禁用默认反垃圾邮件策略（它始终应用于所有收件人）。

若要在 PowerShell 中启用或禁用垃圾邮件筛选规则，请使用以下语法：

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

下面的示例禁用名为“Marketing Department”的垃圾邮件筛选规则。

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

若要详细了解语法和参数，请参阅 [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>使用 PowerShell 设置垃圾邮件筛选规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置垃圾邮件筛选规则的优先级，请使用以下语法：

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**注意**：

- 若要在新建规则时设置它的优先级，请改为对 **New-HostedContentFilterRule** cmdlet 使用 _Priority_ 参数。

- 默认垃圾邮件筛选策略没有相应的垃圾邮件筛选规则，且始终有不可修改的优先级值 **“最低”**。

### <a name="use-powershell-to-remove-spam-filter-policies"></a>使用 PowerShell 删除垃圾邮件筛选策略

如果使用 PowerShell 删除垃圾邮件筛选策略，不会删除相应的垃圾邮件筛选规则。

若要在 PowerShell 中删除垃圾邮件筛选策略，请使用以下语法：

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

下面的示例删除名为“Marketing Department”的垃圾邮件筛选策略。

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

若要详细了解语法和参数，请参阅 [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy)。

### <a name="use-powershell-to-remove-spam-filter-rules"></a>使用 PowerShell 删除垃圾邮件筛选规则

使用 PowerShell 删除垃圾邮件筛选规则时，不会删除相应的垃圾邮件筛选策略。

若要在 PowerShell 中删除垃圾邮件筛选规则，请使用以下语法：

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

下面的示例删除名为“Marketing Department”的垃圾邮件筛选规则。

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

若要详细了解语法和参数，请参阅 [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>发送 GTUBE 邮件测试垃圾邮件策略设置

> [!NOTE]
> 只有当你从中发送 GTUBE 邮件的电子邮件组织不扫描出站垃圾邮件时，才能执行这些步骤。 如果扫描，测试邮件便无法发送。

垃圾群发电子邮件的一般测试 (GTUBE) 是文本字符串，可以添加到测试邮件中，用于验证组织的反垃圾邮件设置。 GTUBE 邮件类似于用于测试恶意软件设置的欧洲反计算机病毒协会 (EICAR) 文本文件。

在电子邮件中的某一行上，添加以下 GTUBE 文本，不得有任何空格或换行符：

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>允许/阻止列表

有时候，筛选器会缺少邮件，或者我们的系统需要花费时间捕获邮件。 在这种情况下，反垃圾邮件策略提供了一个“允许”列表和一个“阻止”列表，可用于推翻现行裁决。 应谨慎使用此选项，因为列表可能变得不可管理，而且由于我们的筛选堆栈应该做它应该做的事情，因此只能暂时使用此选项。

> [!TIP]
> 在某些情况下，组织可能会不同意服务提供的结论。 在这种情况下, 你可能希望永久保留“允许”或“阻止”列表。 但是，如果你想要将一个域放在“允许”列表中一段时间，则应告知发件人确保其域已通过验证，并将其设置为“DMARC 拒绝”（如果不是）。
