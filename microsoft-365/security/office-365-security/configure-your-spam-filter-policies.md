---
title: 配置垃圾邮件筛选策略
f1.keywords:
  - NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: null
audience: ITPro
ms.topic: how-to
ms.localizationpriority: high
search.appverid:
  - MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
  - M365-security-compliance
ms.custom: null
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中查看、创建、修改和删除反垃圾邮件策略。
ms.technology: mdo
ms.prod: m365-security
---

# <a name="configure-anti-spam-policies-in-eop"></a>在 EOP 中配置反垃圾邮件策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在有 Exchange Online 的 Microsoft 365 组织，或没有 Exchange Online 邮箱的 Exchange Online Protection (EOP) 组织中，EOP 都会自动保护入站电子邮件免受垃圾邮件威胁。 EOP 使用反垃圾邮件策略（亦称为“垃圾邮件筛选策略”或“内容筛选策略”），作为组织全面抵御垃圾邮件的措施的一部分。 有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。

管理员可以查看、编辑和配置（但不能删除）默认反垃圾邮件策略。 还可以创建应用于组织中特定用户、组或域的自定义反垃圾邮件策略，以实现更细致的控制。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

若要配置反垃圾邮件策略，可以使用 Microsoft 365 Defender 门户，也可以使用 PowerShell（对于拥有 Exchange Online 邮箱的 Microsoft 365 组织为 Exchange Online PowerShell；对于没有 Exchange Online邮箱的组织为独立 EOP PowerShell）。

反垃圾邮件策略的基本要素如下：

- **垃圾邮件筛选策略**：指定根据垃圾邮件筛选裁定执行的操作和通知选项。
- **垃圾邮件筛选规则**：指定垃圾邮件筛选策略的优先级和收件人筛选器（即对谁应用策略）。

在 Microsoft 365 Defender 门户中管理反垃圾邮件策略时，这两个要素之间的区别并不明显：

- 在创建反垃圾邮件策略时，实际上是同时创建了垃圾邮件筛选规则和关联的垃圾邮件筛选策略，并对二者使用相同的名称。
- 如果你修改反垃圾邮件策略，与名称、优先级、启用/禁用以及收件人筛选器有关的设置会修改垃圾邮件筛选规则。 其他所有设置会修改关联的垃圾邮件筛选策略。
- 如果你删除反垃圾邮件策略，垃圾邮件筛选规则和关联的垃圾邮件筛选策略也会随之删除。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文后面的[使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置反垃圾邮件策略](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies)部分。

每个组织都有名为“默认”的内置反垃圾邮件策略，它具有以下属性：

- 该策略会应用于组织中的所有收件人，即使没有与此策略关联的垃圾邮件筛选规则（亦称为“收件人筛选器”），也不例外。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略始终具有更高的优先级。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

为了提高垃圾邮件筛选的有效性，可以创建自定义反垃圾邮件策略，它包含应用于特定用户或用户组的更严格设置。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 必须是 **“组织管理”** 或 **“安全管理员”** 角色组的成员，才能添加、修改和删除反垃圾邮件策略。
  - 若要获得对受限用户门户的只读访问权限，必须成为 **全球读者** 或 **安全读者** 角色组的成员。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的权限。有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关建议的反垃圾软件策略设置，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

- 无法完全关闭垃圾邮件筛选，但可以使用邮件流规则（也称为传输规则）绕过对传入邮件的大多数垃圾邮件筛选（例如，如果在传递到Microsoft 365之前通过第三方保护服务或设备路由电子邮件）。 有关详细信息，请参阅[使用邮件流规则设置邮件中的垃圾邮件可信度 （SCL）](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)。
  - 仍会筛选高可信度钓鱼邮件。 EOP 中的其他功能不受影响（例如，始终扫描邮件以查找恶意软件）。
  - 如果需要绕过 SecOps 邮箱或网络钓鱼模拟的垃圾邮件筛选，请不要使用邮件流规则。 有关详细信息，请参阅 [配置将第三方网络钓鱼模拟传递给用户和未筛选邮件到 SecOps 邮箱](configure-advanced-delivery.md)。

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a>使用 Microsoft 365 Defender 门户创建反垃圾邮件策略

在 Microsoft 365 Defender 门户中创建自定义反垃圾邮件策略，会同时使用相同的名称创建垃圾邮件筛选规则和关联的垃圾邮件筛选策略。

1. 在 Microsoft 365 Defender 门户的 <https://security.microsoft.com> 中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>“**反垃圾邮件**”。 若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。

2. 在“**反垃圾邮件** 策略”页面上点击“![创建图标](../../media/m365-cc-sc-create-icon.png)”，“**创建策略**”，然后从下拉列表中选择“**入站**”。

3. 策略向导随即打开。在 **命名策略页面** 上，配置以下设置：
   - **名称**：输入策略的唯一描述性名称。
   - **说明**：输入策略的可选说明。

   完成后，单击“**下一步**”。

4. 在出现的“**用户、组和域**”页面上，标识策略应用于的内部收件人（收件人条件）：
   - **用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。
   - **组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。
   - **域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。

   单击相应的框，开始键入值，然后从结果中选择所需的值。 根据需要多次重复此过程。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   对于用户或组，可以使用大多数标识符（名称、显示名称、别名、电子邮件地址、帐户名称等），但相应的显示名称则显示在结果中。对于用户，请自行输入星号（\*），以查看所有可用值。

   同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   - **排除这些用户、组和域**：要为策略所应用的内部收件人添加例外（收件人例外），请选择此选项并配置例外。设置和行为与条件完全相同。

   完成后，单击“**下一步**”。

5. 在出现的“**群发电子邮件阈值和垃圾邮件属性**”页面上，配置以下设置：

   - **群发电子邮件阈值**：针对触发你在下一页上配置“**群发电子邮件**”垃圾邮件筛选裁定指定操作的邮件指定批量投诉级别 (BCL)（大于指定值、不大于或等于）。 值越高，邮件就越不理想（是垃圾邮件的可能性就越大）。 默认值为 7。 有关详细信息，请参阅 [EOP 中的批量投诉级别 (BCL)](bulk-complaint-level-values.md)，以及[垃圾邮件与群发电子邮件有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

     默认情况下，在反垃圾邮件策略中，仅在 PowerShell 中可配置的设置 _MarkAsSpamBulkMail_ 的值为 `On`。 此设置极大地影响“**群发电子邮件**”筛选裁定结果：

     - **_MarkAsSpamBulkMail_ 的值为“打开”**：大于阈值的 BCL 将转换为对应于“**垃圾邮件**”筛选裁定的 SCL 6，并会对邮件执行“**群发电子邮件**”筛选裁定对应的操作。
     - **_MarkAsSpamBulkMail_ 的值为“关闭”**：虽然邮件已有 BCL 标记，但 _不会_ 根据“**群发电子邮件**”筛选裁定执行任何操作。 实际上，BCL 阈值和“**群发电子邮件**”筛选裁定操作不相关。

   - “**增加垃圾邮件分数**”、“**标记为垃圾邮件**”<sup>\*</sup>和“**测试模式**”：默认情况下关闭的高级垃圾邮件过滤器 (ASF) 设置。

     若要详细了解这些设置，请参阅 [EOP 中的高级垃圾邮件筛选设置](advanced-spam-filtering-asf-options.md)。

      <sup>\*</sup>“**包含特定语言**”和“**来自这些国家/地区**”设置不是 ASF 的一部分。

   - **包含特定语言**: 点击该框，然后从下拉列表中选择 **“打开”** 或 **“关闭”**。 如果将其打开，则将显示一个框。 开始在框中键入语言的名称。 将显示支持的语言筛选列表。 找到要查找的语言后，请将其选中。 根据需要重复执行此步骤（次数不限）。 若要删除现有值，请单击删除 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) 它位于值的旁边。

   - **从这些国家/地区** _: 点击该框，然后从下拉列表中选择_ *“打开”** 或 **“关闭”**。 如果将其打开，则将显示一个框。 开始在框中键入国家/地区的名称。 将显示支持的国家/地区筛选列表。 找到要查找的国家/地区后，请将其选中。 根据需要重复执行此步骤（次数不限）。 若要删除现有值，请单击删除 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) 它位于值的旁边。

   完成后，单击“**下一步**”。

6. 在出现的“**操作**”页面上，配置下列设置：

   - **邮件操作**：选择或查看根据以下垃圾邮件筛选裁定而对邮件执行的操作：
     - **垃圾邮件**
     - **高可信度垃圾邮件**
     - **钓鱼**
     - **高可信度网络钓鱼电子邮件**
     - **大量邮件**

     下表介绍了可以根据垃圾邮件筛选裁定而执行的操作。

     - 复选标记 ( ![复选标记。](../../media/checkmark.png)）表示操作可以执行（并不是所有操作都适用于所有裁定）。
     - 复选标记后面的星号 (<sup>\*</sup>) 表示垃圾邮件筛选裁定对应的默认操作。

     <br>

     ****

     |操作|垃圾邮件|高<br>置信<br>垃圾邮件 (spam)|网络钓鱼|高<br>置信<br>仿冒|批量邮件|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**将邮件移动到“垃圾邮件”文件夹**：邮件递送到邮箱，并移动到“垃圾邮件”文件夹。<sup>1</sup>|![复选标记。](../../media/checkmark.png)<sup>\*</sup>|![复选标记。](../../media/checkmark.png)<sup>\*</sup>|![复选标记。](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)<sup>\*</sup>|
     |**添加 X 标头**：向邮件头添加 X 标头，并将邮件递送到邮箱。 <p> 稍后将在 **“添加此 X 标头文本”** 框中，输入 X 标头字段名称（而不是值）。 <p> 对于 **“垃圾邮件”** 和 **“高可信度垃圾邮件”** 裁定，邮件移动到“垃圾邮件”文件夹。<sup>1、2</sup>|![复选标记。](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)||![复选标记](../../media/checkmark.png)|
     |**在主题行前面追加文本**：向邮件的主题行开头添加文本。 邮件递送到邮箱，并移动到“垃圾邮件”文件夹。<sup>1、2</sup> <p> 稍后将在 **“在主题行前面添加此文本作为前缀”** 框中输入文本。|![复选标记。](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)||![复选标记](../../media/checkmark.png)|
     |**将邮件重定向到电子邮件地址**：将邮件发送给其他收件人，而不是目标收件人。 <p> 稍后将在 **“重定向到此电子邮件地址”** 框中指定收件人。|![复选标记。](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
     |**删除邮件**：无提示删除整个邮件，包括所有附件。|![复选标记。](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)||![复选标记](../../media/checkmark.png)|
     |**隔离邮件**：将邮件发送到隔离，而不是目标收件人。 <p> 稍后将在 **“隔离”** 框中指定所需的邮件隔离时长。 <p> 在出现的“**选择策略** 框中指定 [隔离策略](quarantine-policies.md)，以将其应用于垃圾邮件筛选器裁定的隔离邮件。有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。<sup>3</sup>|![复选标记。](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)<sup>\*</sup>|![复选标记](../../media/checkmark.png)<sup>\*</sup>|![复选标记](../../media/checkmark.png)|
     |**无操作**|||||![复选标记](../../media/checkmark.png)|
     |

     > <sup>1</sup> EOP 现在使用自己的邮件流传递代理将邮件路由到垃圾邮件文件夹，而不是使用垃圾邮件规则。 **Set-MailboxJunkEmailConfiguration** cmdlet 上的 _Enabled_ 参数不再对邮件流有任何影响。 有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。
     >
     > 在 EOP 保护本地 Exchange 邮箱的混合环境中，需要在本地 Exchange 中配置邮件流规则（也称为传输规则）。这些邮件流量规则转换 EOP 垃圾邮件筛选裁定，以便邮箱中的垃圾邮件规则可以将邮件移动到垃圾邮件文件夹。有关详细信息，请参阅 [配置 EOP 以将垃圾邮件传递到混合环境中的垃圾邮件文件夹](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。
     >
     > <sup>2</sup>可以将此使用值用作邮件流规则（亦称为“传输规则”）中的条件来筛选或路由邮件。
     >
     > <sup>3</sup> 空白的 **选择策略** 值表示使用该特定裁定的默认隔离策略。 稍后编辑反垃圾邮件策略或查看设置时，将显示默认隔离策略名称。 有关用于垃圾邮件筛选器裁定的默认隔离策略的详细信息，请参阅 [此表](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)。

   - **将垃圾邮件保留在隔离区内此天数**：指定在你选择“**隔离邮件**”作为垃圾邮件筛选裁定操作时将邮件放在隔离区内的时长。 时间段到期后，将删除邮件，并且不可恢复。 有效值介于 1 和 30 天之间。

     > [!NOTE]
     > 在默认反垃圾邮件策略中和在 PowerShell 中创建的新反垃圾邮件策略中的默认值均为 15 天。 在 Microsoft 365 Defender 门户中创建的新反垃圾邮件策略中的默认值为 30 天。
     >
     > 此设置还控制由 **防钓鱼** 策略隔离的邮件的保留时间。 有关详细信息，请参阅 [EOP 和 Defender for Office 365 中的隔离邮件](quarantine-email-messages.md)。

   - **添加此 X 标头文本**：只有当你选择 **“添加 X 标头”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。 指定的值是添加到邮件头的标头字段 *名称*。 标头字段 *值* 始终为 `This message appears to be spam`。

     长度上限为 255 个字符，且值不得包含空格或冒号 (:)。

     例如，如果你输入值 `X-This-is-my-custom-header`，则添加到邮件的 X 标头为 `X-This-is-my-custom-header: This message appears to be spam.`

     如果你输入的值包含空格或冒号 (:)，输入值会遭忽略，且添加到邮件中的是默认 X 标头 (`X-This-Is-Spam: This message appears to be spam.`)。

   - **在主题行前面追加此文本**：此框是必需的，并且仅在你选择“**在主题行前追加文本**”作为垃圾邮件筛选裁定的操作时方可可用。请输入要添加到邮件主题行开头的文本。

   - **重定向到此电子邮件地址**：只有当你选择 **“将邮件重定向到电子邮件地址”** 作为垃圾邮件筛选裁定对应的操作时，此框才会显示且必须选中。 输入要将邮件递送到的电子邮件地址。 可以输入多个值，用分号 (;) 分隔。

   - **启用安全提示**：安全提示默认处于启用状态，但你可以通过清除该复选框来禁用它们。

   - **启用零时差自动清除 (ZAP)**：ZAP 检测已递送到 Exchange Online 邮箱的邮件，并对邮件执行操作。 有关详细信息，请参阅[零时差自动清除 - 抵御垃圾邮件和恶意软件](zero-hour-auto-purge.md)。

     默认情况下，ZAP 处于启用状态。 当启用 ZAP 时，可以使用以下设置：

     - **为钓鱼邮件启用 ZAP**：默认情况下，为钓鱼检测启用 ZAP，但可通过清除复选框来禁用它。
     - **为垃圾邮件启用 ZAP**：默认情况下，为垃圾邮件检测启用 ZAP，但可通过清除复选框来禁用它。

   > [!NOTE]
   > 最终用户垃圾邮件通知已替换为隔离策略中的 _隔离通知_。 隔离通知包含有关所有受支持保护功能（不仅仅是反垃圾邮件策略和反网络钓鱼策略裁定）的隔离邮件的信息。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

   完成后，单击“**下一步**”。

7. 在出现的“**允许和阻止列表**”浮出控件上，你能够按允许跳过垃圾邮件筛选的电子邮件地址或电子邮件域配置邮件发件人。

   在“**已允许**”部分中，可以配置允许的发件人和允许的域。 在“**已阻止**”部分中，可以配置阻止的发件人和阻止的域。

   > [!IMPORTANT]
   >
   > 在将域添加到允许的域列表之前，请慎重考虑。 有关详细信息，请参阅[在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)
   >
   > 切勿将你自己的[接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)或公共域（例如 microsoft.com 或 office.com）添加到允许的域列表中。 如果允许这些域名绕过垃圾邮件过滤，攻击者则可以很容易地将欺骗这些可信域名的消息发送到组织。
   >
   > 通过将域添加到阻止的域列表来手动阻止域并不危险，但这会增加你的管理工作量。 有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。
   >
   > 有时，我们的筛选器会漏掉一封邮件，你不同意筛选裁定，或者我们的系统需要时间来跟进。 在这些情况下，允许列表和阻止列表可用于覆盖当前筛选裁定。 但是，你应该谨慎和临时使用这些列表：冗长列表可能无法管理，我们的筛选堆栈应正在执行它应该执行的操作。 如果你打算长时间保留允许的域，则应该告知发件人验证其域是否已通过身份验证，如果没有，则设置为“DMARC 拒绝”。

   将条目添加到任何列表的步骤相同：

   1. 单击要配置的列表的链接：
      - **允许的**\>**发件人**：单击“**管理 (nn) 发件人**”。
      - **允许的**\>**域**：单击“**允许域**”。
      - **阻止的**\>**发件人**：单击“**管理 (nn) 发件人**”。
      - **阻止的**\>**域**：单击“**阻止域**”。

   2. 在出现的浮出控件中，执行下列步骤：
      1. 单击![“创建”图标](../../media/m365-cc-sc-create-icon.png)**“添加发件人”** 或 **“添加域”**。
      2. 在出现的“**添加发件人**”或“**添加域**”浮出控件中，在“**发件人**”框中输入发件人的电子邮件地址，或者在“**域**”框中输入域。 键入时，值将显示在框下方。 完成键入电子邮件地址或域后，请选择框下方的值。
      3. 根据需要多次重复上一步。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

      完成后，单击“**添加发件人**”或“**添加域**”。

      返回到主浮出控件，页面上列出了你添加的发件人或域。 若要从此页面中删除条目，请执行以下步骤：

      1. 从列表中选择一个或多个条目。 还可使用“**搜索**”框查找列表中的值。
      2. 在你选择至少一个条目后，“删除”图标 ![删除图标。](../../media/m365-cc-sc-delete-icon.png) 将会出现。
      3. 单击“删除”图标 ![删除图标。](../../media/m365-cc-sc-delete-icon.png) 以删除所选条目。

      完成后，单击“**完成**”。

      返回到“**允许和阻止列表**”页面，准备好继续时单击“**下一步**”。

8. 在出现的“**审阅**”页面上，查看你的设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，单击“**创建**”。

9. 在出现的确认页面上，单击“**完成**”。

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a>使用 Microsoft 365 Defender 门户查看反垃圾邮件策略

1. 在 Microsoft 365 Defender 门户的 <https://security.microsoft.com> 中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>“**反垃圾邮件**”。 若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。

2. 在 **“反垃圾邮件”策略** 页面上，查找以下值之一:
   - “**类型**”值是“**自定义反垃圾邮件策略**”
   - “**名称**”值是“**反垃圾邮件入站策略（默认）**”

   反垃圾邮件策略列表中将显示以下属性：

   - **名称**
   - **状态**
   - **优先级**
   - **类型**

3. 单击名称选择反垃圾邮件策略时，策略设置会显示在浮出控件中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a>使用 Microsoft 365 Defender 门户修改反垃圾邮件策略

1. 在 Microsoft 365 Defender 门户的 <https://security.microsoft.com> 中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>“**反垃圾邮件**”。 若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。

2. 在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择反垃圾邮件策略：
   - 你创建的自定义策略，其中“**类型**”列中的值为“**自定义反垃圾邮件策略**”。
   - 名为“**反垃圾邮件入站策略（默认）**”的默认策略。

3. 在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。 有关设置的详细信息，请参阅本文前面的“[使用 Microsoft 365 Defender 门户创建反垃圾邮件策略](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)”部分。

   对于默认反垃圾邮件策略，没有“**应用于**”部分（该策略应用于所有人），且无法重命名该策略。

若要启用或禁用策略或设置策略优先级顺序，请参阅以下几节。

### <a name="enable-or-disable-anti-spam-policies"></a>启用或禁用反垃圾邮件策略

无法禁用默认反垃圾邮件策略。

1. 在 Microsoft 365 Defender 门户的 <https://security.microsoft.com> 中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>“**反垃圾邮件**”。 若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。

2. 在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择“**类型”** 值为“**自定义反垃圾邮件策略**”的策略。

3. 在出现的策略详细信息浮出控件顶部，你将看到以下值之一：
   - **策略关闭**：若要打开策略，请单击![“打开”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“打开”**。
   - **策略打开**：若要关闭策略，请单击![“关闭”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“关闭”**。

4. 在出现的确认对话框中，单击“**打开**”或“**关闭**”。

5. 单击策略详细信息浮出控件中的“**关闭**”。

返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>设置自定义反垃圾邮件策略的优先级

默认情况下，反垃圾邮件策略根据创建顺序来获得优先级（新策略的优先级低于旧策略）。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

要更改策略的优先级，请在策略属性中单击“**提高优先级**”或“**降低优先级**”（不能在 Microsoft 365 Defender 门户中直接修改 **优先级** 编号）。仅当具有多个策略时，更改策略的优先级才有意义。

 **注意**：

- 在 Microsoft 365 Defender 门户中，你只能在创建反垃圾邮件策略后更改其优先级。在 PowerShell 中，你可以在创建垃圾邮件筛选规则时覆盖默认优先级（这可能会影响现有规则的优先级）。
- 反垃圾邮件策略将按其显示顺序进行处理（第一个策略的“**优先级**”值为 0）。 默认反垃圾邮件策略的优先级值为“**最低**”，你无法更改此值。

1. 在 Microsoft 365 Defender 门户的 <https://security.microsoft.com> 中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>“**反垃圾邮件**”。 若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。

2. 在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择“**类型”** 值为“**自定义反垃圾邮件策略**”的策略。

3. 在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：
   - “**优先级**”值为 **0** 的反垃圾邮件策略只有“**降低优先级**”选项可用。
   - 具有最低“**优先级**”值（例如 **3**）的反垃圾邮件策略只有“**提高优先级**”选项可用。
   - 如果你有三个或更多反垃圾邮件策略，则最高和最低优先级值之间的策略同时有“**提高优先级**”和“**降低优先级**”两个选项可用。

   单击![“提高优先级”图标。](../../media/m365-cc-sc-increase-icon.png) **“提高优先级”** 或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png) **“降低优先级”** 以更改 **“优先级”** 值。

4. 完成后，单击策略详细信息浮出控件中的“**关闭**”。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a>使用 Microsoft 365 Defender 门户删除自定义反垃圾邮件策略

当你使用 Microsoft 365 Defender 门户删除自定义反垃圾邮件策略时，垃圾邮件筛选规则和相应的垃圾邮件筛选策略都将被删除。无法删除默认反垃圾邮件策略。

1. 在 Microsoft 365 Defender 门户的 <https://security.microsoft.com> 中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>“**反垃圾邮件**”。 若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。

2. 在“**反垃圾邮件策略**”页面上，单击名称以从列表中选择“**类型”** 值为“**自定义反垃圾邮件策略**”的策略。 在显示的策略详细信息浮出控件顶部，单击![更多操作图标。](../../media/m365-cc-sc-more-actions-icon.png) **更多操作** \> ![删除策略图标](../../media/m365-cc-sc-delete-icon.png) **删除策略**。

3. 在出现的确认对话框中，单击“**是**”。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置反垃圾邮件策略

如前文所述，反垃圾邮件策略由垃圾邮件筛选策略和垃圾邮件筛选规则组成。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，垃圾邮件筛选策略与垃圾邮件筛选规则之间的区别很明显。 可以使用 **\*-HostedContentFilterPolicy** cmdlet 管理垃圾邮件筛选策略，并使用 **\*-HostedContentFilterRule** cmdlet 管理垃圾邮件筛选规则。

- 在 PowerShell 中，先创建垃圾邮件筛选策略，再创建确定向哪个策略应用规则的垃圾邮件筛选规则。
- 在 PowerShell 中，分别修改垃圾邮件筛选策略和垃圾邮件筛选规则中的设置。
- 如果你通过 PowerShell 删除垃圾邮件筛选策略，相应的垃圾邮件筛选规则不会自动随之删除，反之亦然。

以下反垃圾邮件策略设置仅在 PowerShell 中可配置：

- _MarkAsSpamBulkMail_ 参数默认为 `On`。本文中前面的 [使用 Microsoft 365 Defender 门户创建反垃圾邮件策略](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) 部分介绍了此设置的效果。
- 以下设置用于最终用户垃圾邮件隔离通知：
  - _DownloadLink_ 参数：显示或隐藏 Outlook 垃圾邮件报告工具的链接。
  - _EndUserSpamNotificationCustomSubject_ 参数：可用于自定义通知的主题行。

### <a name="use-powershell-to-create-anti-spam-policies"></a>使用 PowerShell 创建反垃圾邮件策略

在 PowerShell 中创建反垃圾邮件策略的过程分为两步：

1. 创建垃圾邮件筛选策略。
2. 创建垃圾邮件筛选规则，它指定了向哪个垃圾邮件筛选策略应用规则。

 **注意**：

- 可以新建垃圾邮件筛选规则，并向它分配未关联的现有垃圾邮件筛选策略。 垃圾邮件筛选规则不能与多个垃圾邮件筛选策略关联。
- 可以在 PowerShell 中对新垃圾邮件筛选策略配置以下设置（在 Microsoft 365 Defender 门户中，只有在创建策略后，才能配置这些设置）：
  - 新建禁用的策略（在 **New-HostedContentFilterRule** cmdlet 上 _Enabled_ 为 `$false`）。
  - 在创建过程中，在 **New-HostedContentFilterRule** cmdlet 上设置策略优先级（_优先级_ _\<Number\>_）。

- 在 PowerShell 中新建的垃圾邮件筛选策略在 Microsoft 365 Defender 门户内不可见，除非你将策略分配到垃圾邮件筛选规则。

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>第 1 步：使用 PowerShell 创建垃圾邮件筛选策略

若要创建垃圾邮件筛选策略，请使用以下语法：

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

下面的示例使用以下设置创建名为“Contoso Executives”的垃圾邮件筛选策略：

- 当垃圾邮件筛选裁定为垃圾邮件或高可信度垃圾邮件时隔离邮件，并使用隔离邮件的默认 [隔离策略](quarantine-policies.md)（不使用 _SpamQuarantineTag_ 或 _HighConfidenceSpamQuarantineTag_ 参数）。
- BCL 7、8 或 9 触发群发电子邮件垃圾邮件筛选裁定对应的操作。

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。

> [!NOTE]
> 有关指定要在垃圾邮件筛选策略中使用的 [隔离策略](quarantine-policies.md) 的详细说明，请参阅 [使用 PowerShell 在反垃圾邮件策略中指定隔离策略](quarantine-policies.md#anti-spam-policies-in-powershell)。

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

若要详细了解语法和参数，请参阅 [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule)。

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

若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。

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

若要详细了解语法和参数，请参阅 [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule)。

### <a name="use-powershell-to-modify-spam-filter-policies"></a>使用 PowerShell 修改垃圾邮件筛选策略

除了以下几项之外，在 PowerShell 中修改垃圾邮件筛选策略时可用的设置，与本文前面的[第 1 步：使用 PowerShell 创建垃圾邮件筛选策略](#step-1-use-powershell-to-create-a-spam-filter-policy)部分中介绍的可用于创建策略的设置相同。

- 只有在 PowerShell 中修改垃圾邮件筛选策略时，才能使用 _MakeDefault_ 开关，它可将指定策略转换为默认策略（应用于所有人，优先级值始终为 **“最低”**，且无法删除）。
- 无法重命名垃圾邮件筛选策略（**Set-HostedContentFilterPolicy** cmdlet 没有 _Name_ 参数）。 在 Microsoft 365 Defender 门户中重命名反垃圾邮件策略时，只是在重命名垃圾邮件筛选 _规则_。

若要修改垃圾邮件筛选策略，请使用以下语法：

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。

> [!NOTE]
> 有关指定要在垃圾邮件筛选策略中使用的 [隔离策略](quarantine-policies.md) 的详细说明，请参阅 [使用 PowerShell 在反垃圾邮件策略中指定隔离策略](quarantine-policies.md#anti-spam-policies-in-powershell)。

### <a name="use-powershell-to-modify-spam-filter-rules"></a>使用 PowerShell 修改垃圾邮件筛选规则

在 PowerShell 中修改垃圾邮件筛选规则时，唯一不可用的设置是 _已启用_ 参数。通过该参数，可以创建禁用的规则。要启用或禁用现有的垃圾邮件筛选规则，请参阅下一部分。

否则，在 PowerShell 中修改垃圾邮件筛选规则时，将无法使用其他任何设置。 创建规则时可用的设置与本文前面的[第 2 步：使用 PowerShell 创建垃圾邮件筛选规则](#step-2-use-powershell-to-create-a-spam-filter-rule)部分中介绍的设置相同。

若要修改垃圾邮件筛选规则，请使用以下语法：

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

此示例重命名名为 `{Fabrikam Spam Filter}` 的现有垃圾邮件筛选规则。

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

若要详细了解语法和参数，请参阅 [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule)。

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>使用 PowerShell 启用或禁用垃圾邮件筛选规则

在 PowerShell 中启用或禁用垃圾邮件筛选规则会启用或禁用整个反垃圾邮件策略（即垃圾邮件筛选规则和分配的垃圾邮件筛选策略）。 无法启用或禁用默认反垃圾邮件策略（该策略始终应用于所有收件人）。

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

若要详细了解语法和参数，请参阅 [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) 和 [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>使用 PowerShell 设置垃圾邮件筛选规则的优先级

可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。

若要在 PowerShell 中设置垃圾邮件筛选规则的优先级，请使用以下语法：

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。

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

若要详细了解语法和参数，请参阅 [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy)。

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

若要详细了解语法和参数，请参阅 [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>发送 GTUBE 邮件测试垃圾邮件策略设置

> [!NOTE]
> 只有当你从中发送 GTUBE 邮件的电子邮件组织不扫描出站垃圾邮件时，才能执行这些步骤。如果不是，则无法发送测试邮件。

垃圾群发电子邮件的一般测试 (GTUBE) 是文本字符串，可以添加到测试邮件中，用于验证组织的反垃圾邮件设置。 GTUBE 邮件类似于用于测试恶意软件设置的欧洲反计算机病毒协会 (EICAR) 文本文件。

在电子邮件中的某一行上，添加以下 GTUBE 文本，不得有任何空格或换行符：

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
