---
title: 数据丢失防护参考
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 数据丢失防护参考资料
ms.openlocfilehash: 5c01b6419a9af100cfaedccbd5a9c4923ca3e42f
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061791"
---
# <a name="data-loss-prevention-reference"></a>数据丢失防护参考
 
> [!IMPORTANT]
> 此参考主题不再是 DLP Microsoft 365数据丢失防护 (的主要) 资源。 DLP 内容集正在更新和重新构建。 本文中介绍的主题将移动到新的更新的文章。 有关 DLP 详细信息，请参阅 [了解数据丢失防护](dlp-learn-about-dlp.md)。

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> 对于具有 Office 365 高级合规版许可证的用户，最近为 Microsoft Teams 聊天和频道消息添加了数据丢失防护功能。它是一种独立选项，包含在 Office 365 E5 和 Microsoft 365 E5 合规版中。 要详细了解许可要求，请参阅 [Microsoft 365 租户级服务许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)。



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a>创建和管理 DLP 策略

你可在 Microsoft 365 安全合规中心的“数据丢失防护”页上创建和管理 DLP 策略。
  
![Office 365 安全 &amp; 合规中心的数据丢失防护页](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
可使用规则来满足特定保护要求，然后使用 DLP 策略将常见保护要求组合在一起，例如符合特定规则所需的所有规则。
  
例如，DLP 策略可能会帮助您检测是否存在受健康保险可携性与责任法案 (HIPAA) 约束的信息。 此 DLP 策略可以通过查找与你的组织外部人员共享的包含此敏感信息（条件）的任何文档，来帮助保护所有 SharePoint Online 站点和所有 OneDrive for Business 站点（位置）的 HIPAA 数据（对象），然后阻止对该文档的访问并发送通知（操作）。 这些要求存储为单个规则，并作为一项 DLP 策略组合在一起以简化管理和报告。
  
![图表显示了 DLP 策略包含位置和规则](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

如果选择将特定通讯组包含在 Exchange 中，则 DLP 策略的影响范围将仅限于该组的成员。 同样，排除通讯组将把该通讯组的所有成员从策略评估中排除。 可选择将策略的影响范围限定为通讯组列表、动态通讯组和安全组的成员。 一条 DLP 策略可包含不超过 50 个这种包含和排除。

如果你选择包含或排除特定 SharePoint 网站，则 DLP 策略可包含不超过 100 个此类包含项和排除项。 尽管存在此限制，你可应用组织范围策略或位置整体策略来超出此限制。

如果你选择包括或排除特定 OneDrive 帐户或组，则 DLP 策略可包含不超过 100 个用户帐户或 50 个组作为包含项或排除项。
  
### <a name="rules"></a>Rules

> [!NOTE]
> 当未配置警报时，DLP 策略的默认行为是，不发出警报或不触发事件。 这仅适用于默认信息类型。 对于自定义信息类型，即使策略中未定义任何操作，系统也会发出警报。

规则用于对组织的内容强制执行业务要求。 策略包含一条或多条规则，每条规则由多个条件和操作组成。 对于每条规则，只要满足了条件，就会自动执行操作。 规则按顺序执行，从每个策略中优先级最高的规则开始。
  
规则还提供一些选项，用于通知用户（使用策略提示和电子邮件通知）和管理员（使用电子邮件事件报告）内容与规则相匹配。
  
以下是规则的各组成部分，并提供了相应说明。
  
![DLP 规则编辑器的各部分](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>条件

条件非常重要，因为它们确定要查找的信息类型以及执行操作的时间。 例如，你可能会选择忽略包含护照号的内容，除非内容包含 10 个以上此类数字并与组织外部的人员进行了共享。
  
条件侧重于 **内容**，例如要查找的敏感信息类型，还侧重于 **上下文**，例如共享文档的人员。 你可以使用条件向不同的风险级别分配不同操作。 例如，相较与组织外部人员共享的敏感信息，可在内部共享的敏感内容的风险更低、需要执行的操作更少。 
  
![显示可用的 DLP 条件的列表](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
现在的可用条件可以确定以下内容：
  
- 包含某种敏感信息的内容。
    
- 包含标签的内容。 有关详细信息，请参阅下方的[将保留标签用作 DLP 策略中的条件](#using-a-retention-label-as-a-condition-in-a-dlp-policy)部分。
    
- 内容是与贵组织的外部还是内部人员共享。

  > [!NOTE]
  > 在主体组织的 Active Directory 或 Azure Active Directory 租户中具有非来宾帐户的用户是否被视为该组织内部人员。
    
#### <a name="types-of-sensitive-information"></a>敏感信息类型

DLP 策略可帮助保护定义为 **敏感信息类型** 的敏感信息。 Microsoft 365 包含对多个不同地区供你使用的众多常见敏感信息类型的定义，例如信用卡号、银行账号、国民身份证号及护照号等。 
  
![可用敏感信息类型列表](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
当 DLP 策略查找信用卡号之类的敏感信息类型时，它不只是在查找 16 位数字。 通过以下组合对每种敏感信息类型进行定义和检测：
  
- 关键字。
    
- 用于验证校验和或撰写的内部函数。
    
- 用于查找模式匹配的正则表达式评估。
    
- 其他内容检查。
    
这将有助于实现高度准确的 DLP 检测，同时减少导致用户工作中断的误报数。
  
#### <a name="actions"></a>操作

当内容与规则中的条件匹配时，可应用操作以自动保护内容。
  
![可用 DLP 操作列表](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
借助可用操作，能够：
  
- **限制对内容的访问权限**，根据需要，可通过以下三种方式限制对内容的访问权限：

  1. 限制所有人对内容的访问权限。
  2. 限制组织外部人员对内容的访问权限。
  3. 将访问权限限制为“拥有链接的任何人”。

  对于网站内容，这就意味着，除主要网站集管理员、文档所有者和上次修改文档的人员外，所有人访问该文档均受限。 这些用户可从文档中删除敏感信息或执行其他补救操作。 如果文档符合规则，则会自动恢复原始权限。 访问文档受阻时，文档将在网站的库中显示一个特殊策略提示图标。 
    
  ![显示文档访问被拦截的策略提示](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  对于电子邮件内容，此操作阻止发送该邮件。 根据 DLP 规则的配置方式，发件人将看到 NDR 或（如果规则使用通知）策略提示和/或电子邮件通知。
    
  ![警告：必须从邮件中删除未经授权的收件人](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>用户通知和用户覆盖

你可以使用通知和覆盖向用户介绍 DLP 策略，并帮助他们保持兼容性，同时不会中断工作。 例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。
  
![DLP 规则编辑器的用户通知和用户覆盖部分](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
电子邮件可向发送、共享或最后修改内容的人员发送通知，对于网站内容，则可通知主要网站集管理员和文档所有者。 此外，还可向电子邮件通知中添加人员或删除所选人员。
  
除发送电子邮件通知外，用户通知还会显示一条策略提示：
  
- 在 Outlook 和 Outlook 网页版中。
    
- 对于 SharePoint Online 或 OneDrive for Business 网站上的文档。
    
- 在 Excel、PowerPoint 和 Word 中（如果文档存储在 DLP 策略中包含的网站上）。
    
电子邮件通知和策略提示解释内容与 DLP 策略相冲突的原因。 如果您选择，电子邮件通知和策略提示可以允许用户通过报告误报或提供业务理由来替代规则。 这可以帮助您让用户了解您的 DLP 策略和强制执行它们，而不会阻止用户完成其工作。 有关替代和误报的信息还记录报告（请参阅下文提供的 DLP 报告）并且包含在事件报告（下一节）中，以便合规部主管可以定期查看此信息。
  
以下是 OneDrive for Business 帐户中的策略提示。
  
![针对 OneDrive 帐户中文档的策略提示](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 若要了解有关 DLP 策略中的用户通知和策略提示的详细信息，请参阅[使用通知和策略提示](use-notifications-and-policy-tips.md)。

#### <a name="alerts-and-incident-reports"></a>警报和事件报告

当规则匹配时，可向法律人员（或所选的任何人员）发送包含事件详情的警报电子邮件。 此警报电子邮件将提供 [DLP 警报管理仪表板](dlp-configure-view-alerts-policies.md)的链接，法律人员可以使用该链接查看警报和事件的详细信息。 仪表板包含触发警报的事件的详细信息，以及匹配的 DLP 策略和检测到的敏感内容的详细信息。

此外，你还可以发送包含事件详细信息的事件报告。 此报告中的信息包括，匹配的项目的信息、与规则匹配的实际内容以及上次修改内容的人员的姓名。 对于电子邮件，报告还将与 DLP 策略匹配的原始邮件包含为附件。

> [!div class="mx-imgBorder"]
> ![用于配置事件报告的页面](../media/Alerts-and-incident-report.png)

DLP 扫描电子邮件的方式与 SharePoint Online 或 OneDrive for Business 中的项目不同。 在 SharePoint Online 和 OneDrive for Business 中，DLP 可扫描现有项目以及新项目，并在找到匹配项时生成警报和事件报告。 在 Exchange Online 中，DLP 仅扫描新电子邮件，并在存在策略匹配项时生成报告。 DLP ***不会*** 扫描或匹配邮箱或存档中存储的先前存在的电子邮件项目。
  
## <a name="grouping-and-logical-operators"></a>分组和逻辑运算符

DLP 策略的要求通常比较简单，例如标识包含美国社会安全号码的所有内容。 但在其他情况下，DLP 策略可能需要标识定义更松散的数据。
  
例如，若要标识应遵循美国健康保险法案 (HIPAA) 的内容，需要查找：
  
- 包含特定类型敏感信息的内容，例如美国。社会安全号码或毒品管制局 (DEA) 号码。
    
    AND
    
- 更难以标识的内容，例如有关患者护理的通信，或者提供的医疗服务说明。 识别此内容需要匹配极庞大的关键字列表中的关键字，如国际疾病分类（ICD-9-CM 或 ICD-10-CM）。
    
使用分组和逻辑运算符（AND、OR），可轻松标识此类定义松散的数据。 创建 DLP 策略时，可以执行以下操作：
  
- 对敏感信息类型进行分组。
    
- 选择组内敏感信息类型之间以及组与组之间的逻辑运算符。
    
### <a name="choosing-the-operator-within-a-group"></a>选择组内的运算符

在组中，可选择要将内容视为与规则匹配，是只需满足该组中的任一条件，还是必须满足所有条件。
  
![显示组内运算符的组](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>添加组

可以快速添加组，该组内可包含自己的条件和运算符。
  
![添加组按钮](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>选择组之间的运算符

在组之间，为使内容与规则匹配，可选择只需满足一个组中的条件，还是必须满足所有组的条件。
  
例如，内置“**美国 HIPAA**”政策有一项规则，规定在组之间使用 **AND** 运算符，因此它标识的内容将包括： 
  
- 从组“**PII 标识符**”（至少一个 SSN 数字 **OR** DEA 数字） 
    
    AND
    
- 从组“**医疗条件**”（至少一个 ICD-9-CM 关键字 **OR** 一个 ICD-10-CM 关键字） 
    
![显示组之间运算符的组](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>处理规则的优先级

在策略中创建规则时，每条规则都按创建顺序分配了优先级 — 这意味着，首先创建的规则具有第一优先级，创建的第二条规则具有第二优先级，以此类推。

> [!div class="mx-imgBorder"]
> ![按优先级顺序排列的规则](../media/dlp-rules-in-priority-order.png)
  
设置多个 DLP 策略后，可以更改一个或多个策略的优先级。 若要执行此操作，请选择一个策略，选择“**编辑策略**”，然后使用“**优先级**”列表指定其优先级。

> [!div class="mx-imgBorder"]
> ![设置策略的优先级](../media/dlp-set-policy-priority.png)

对照规则评估内容时，按优先级顺序处理规则。 如果内容符合多个规则，按优先级顺序处理规则，并强制实施最严格的操作。 例如，如果内容符合以下所有规则，将实施规则 3，因为它具有最高优先级且最严格：
  
- 规则 1：仅通知用户
    
- 规则 2：通知用户、限制访问并允许用户替代
    
- 规则 3：通知用户、限制访问且不允许用户替代
    
- 规则 4：仅通知用户
    
- 规则 5：限制访问
    
- 规则 6：通知用户、限制访问且不允许用户替代
    
在此示例中，要注意的是尽管只实施最严格的规则，仍会将所有匹配的规则记录在审核日志中，并显示在 DLP 报表中。
  
对于策略提示，请注意:
  
- 仅显示来自最高优先级、最具限制性的规则的策略提示。 例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。 这会让用户看不到策略提示的级联方式。
    
- 如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>调整规则，使它们更易或更难匹配

用户创建并启用 DLP 策略后，他们有时会遇到以下问题：
  
- 太多 **不是** 敏感信息的内容与规则匹配 — 也就是说，太多误报。 
    
- 太少 **是** 敏感信息的内容与规则匹配。 也就是说，未对敏感信息强制执行保护操作。 
    
若要解决这些问题，可以通过调整实例计数和匹配准确度来调整规则，使内容更难或更易匹配规则。 规则中使用的每一类敏感信息都有实例计数和匹配准确度。
  
### <a name="instance-count"></a>实例计数

实例计数是指若要使内容与规则匹配，某类敏感信息必须出现的次数。 例如，如果将美国或英国护照号码标识为 1 到 9， 则内容将与如下所示的规则匹配。

> [!NOTE]
> 实例计数仅包括敏感信息类型和关键字的 **唯一** 匹配项。 例如，如果一个电子邮件中相同的信用卡号码出现了 10 次，则这 10 次计为信用卡号码的单个实例。
  
若要使用实例计数来调整规则，则指南非常简单：
  
- 若要使规则更易匹配，减少“**最小**”计数和/或增加“**最大**”计数。 也可以通过删除数值，将“**最大**”设置为“**任意**”。 
    
- 若要使规则更难匹配，增加“**最小**”计数。 
    
在实例计数较低（例如，1-9）的规则中，通常会使用较为宽松的操作，如发送用户通知。 在实例计数较高（例如，10–任意）的规则中，使用更严格的操作，如限制访问内容且不允许用户替代。
  
![规则编辑器中的实例计数](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>匹配准确度

如上文所述，使用不同类型的证据组合定义并检测敏感信息类型。 敏感信息类型通常由多个此类组合（称为模式）定义。 需要越少证据的模式匹配准确度（即置信水平）越低，而需要越多证据的模式匹配准确度（即置信水平）更高。 若要了解每种敏感信息类型使用的实际模式和置信水平，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)。
  
例如，名为“信用卡号”的敏感信息类型由两种模式定义：
  
- 置信度为 65% 的模式需要：
    
  - 信用卡号格式的数字。
    
  - 传递校验和的数字。
    
- 置信度为 85% 的模式需要：
    
  - 信用卡号格式的数字。
    
  - 传递校验和的数字。
    
  - 格式正确的关键字或到期日期。
    
可在规则中使用这些置信水平（或匹配准确度）。 在匹配准确度较低的规则中通常使用较为宽松的操作，如发送用户通知。 在匹配准确度较高的规则中使用更严格的操作，如限制访问内容且不允许用户替代。
  
务必了解在内容中标识特定类型的敏感信息（如信用卡号）时，只会返回单个置信水平：
  
- 如果所有匹配项适用于单个模式，则返回该模式的置信水平。
    
- 如果存在多个模式的匹配项（即，存在具有两种不同置信水平的匹配项），则返回高于任一单个模式的置信水平。 这就是难点。 例如，对于信用卡号，如果同时匹配 65% 和 85% 模式，则该敏感信息类型返回的置信水平超过 90%，因为证据越多，置信度越高。
    
因此，如果要为信用卡创建两条互斥的规则，一条用于 65% 的匹配准确度，另一条用于 85% 的匹配准确度，匹配准确度的范围将如下所示。 第一条规则仅选取 65% 模式的匹配项。 第二条规则选取 **至少一个** 85% 匹配项，并且 **可能具有** 其他置信度较低的匹配项。 
  
![两条具有不同匹配准确度范围的规则](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
由于以上原因，使用不同的匹配准确性创建规则的指南为：
  
- 最低置信水平通常使用相同的“**最小**”和“**最大**”值（而不是范围）。 
    
- 最高置信水平通常是一个范围，该范围为略高于置信水平下限到 100。
    
- 任何中间置信水平范围通常为略高于置信水平下限，略低于置信水平上限。
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>将保留标签用作 DLP 策略中的条件

将以前创建和发布的[保留标签](retention.md#retention-labels)用作 DLP 策略中的条件时，请注意以下事项：

- 必须先创建和发布保留标签，然后才能尝试将它用作 DLP 策略中的条件。
- 已发布的保留标签可能需要一到七天的时间才能同步。有关详细信息，请参阅[当保留标签可应用时](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply)（对于已在保留策略中发布的保留标签），以及[保留标签多长时间生效](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect)（对于已自动发布的保留标签）。
- **只有 SharePoint 和 OneDrive 中的项才支持***在策略中使用保留标签。

  ![用作条件的标签](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  如果你有项目处于保留和处置状态，并且还希望为其应用其他控件，则可能需要在 DLP 策略中使用保留标签，例如：

  - 你发布了一个名为“**2018 纳税年度**”的保留标签，当它应用于存储在 SharePoint 中的 2018 年税务文档后，系统会将其保留 10 年，并在此期限后处置它们。 你也不希望在组织外部共享这些项目，你可以使用 DLP 策略来完成此操作。

  > [!IMPORTANT]
  > 如果在 DLP 策略中将保留标签指定为条件，而且你还包含 Exchange 和/或 Teams 作为位置，则你将收到以下错误：**“不支持保护电子邮件和团队消息中带标签的内容。请删除下述标签或取消将 Exchange 和 Teams 设为位置。”** 这是因为 Exchange 传输在消息提交和传递过程中不会评估标签元数据。 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a>使用敏感度标签作为在DLP策略中的条件

[详细了解](./dlp-sensitivity-label-as-condition.md) 在 DLP 策略中将敏感度标签用作条件。
  
### <a name="how-this-feature-relates-to-other-features"></a>此功能与其他功能的联系

可对包含敏感信息的内容应用多个功能：
  
- [保留标签和保留策略](retention.md)都可以对此内容强制执行 **保留** 操作。 
    
- DLP 策略可对此内容执行 **保护** 操作。 执行这些操作之前，DLP 策略可要求内容除包含标签之外还需满足其他条件。 
    
![可应用于敏感信息的功能图表](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
请注意，相较于对敏感信息应用的标签或保留策略，DLP 策略的检测功能更强。 DLP 策略可以对包含敏感信息的内容执行保护操作；从内容中删除敏感信息之后，这些保护操作会在下一次扫描内容时撤消。 但如果对包含敏感信息的内容应用了保留策略或标签，则该操作是一次性操作，即使删除了敏感信息也不会撤消该操作。
  
在 DLP 策略中使用标签作为条件之后，可对包含该标签的内容执行保留和保护操作。 可将带标签的内容完全视为包含敏感信息的内容；标签和敏感信息类型都是用于对内容进行分类的属性，以便对该内容执行操作。
  
![使用标签作为条件的 DLP 策略图表](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>简单设置与高级设置

创建 DLP 策略时，将在简单或高级设置中进行选择：
  
- **简单设置**，可轻松创建最常见类型的 DLP 策略，无需使用规则编辑器创建或修改规则。 
    
- **高级设置**，使用规则编辑器，让使用者可完全控制 DLP 策略的每个设置。 
    
不要担心，实际上简单设置和高级设置的工作方式完全相同，都是强制执行由条件和操作组成的规则，只是使用简单设置时，看不到规则编辑器。 这是快速创建 DLP 策略的方法。
  
### <a name="simple-settings"></a>简单设置

到目前为止，最常见的 DLP 方案是创建策略，帮助保护含敏感信息的内容，防止与组织外人员共享该内容，并采取自动补救措施，例如限制可访问内容的人员、向最终用户或管理员发送通知、对事件进行审核以备后续调查。 人们使用 DLP 防止意外泄露敏感信息。
  
为轻松实现这一目标，创建 DLP 策略时，可选择 **使用简单设置**。 这些设置可提供实现最常见 DLP 策略所需的一切，无需使用规则编辑器。
  
![DLP 简单和高级设置选项](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>高级设置

如需创建自定义程度更高的 DLP 策略，可选择 **使用高级设置**。
  
高级设置会显示规则编辑器，可通过它完全控制每个可能的选项，包括每个规则的实例计数和匹配准确度（可信度级别）。
  
若要快速跳转到某一部分，请单击规则编辑器顶部导航中的项，转到下面的部分。
  
![DLP 规则编辑器的顶部导航菜单](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>DLP 策略模板

创建 DLP 策略的第一步是选择要保护的内容。 从 DLP 模板开始创建，无需从头构建一组新规则，无需指出默认应包含哪些信息类型。 然后即可添加或修改这些要求，微调规则以满足组织的特定要求。
  
预配置的 DLP 策略模板可帮助你检测特定类型的敏感信息，如 HIPAA 数据、PCI-DSS 数据、格雷姆-里奇-比利雷法案数据，甚至是特定区域设置的个人身份信息 (P.I.)。 要使你能够轻松地查找和保护常见类型的敏感信息，包含在 Microsoft 365 中的策略模板已包含你要开始构建策略所需的最常见的敏感信息类型。
  
![数据丢失防护策略模板列表，重点放在美国爱国者法案模板上](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
组织可能还有自己特定的要求，在这种情况下可通过选择“**自定义策略**”选项从头创建 DLP 策略。 自定义策略为空，且不包含任何预制定的规则。 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a>DLP 报告

创建并启用 DLP 策略后，你会希望验证这些策略是否按预期工作，以及是否有助于保持合规性。 使用 DLP 报告，您可以快速查看随着时间的推移 DLP 策略和规则匹配的次数，以及误报和替代数。 对于每个报告，您都可以按位置、时间范围，甚至缩小为特定的策略、规则或操作来筛选这些匹配项。
  
使用 DLP 报告，您可以获取业务见解并了解以下内容：
  
- 重点关注特定的时间段，并了解峰值和发展趋势的原因。
    
- 发现违反贵组织的合规性策略的业务流程。
    
- 了解 DLP 策略的任何业务影响。
    
此外，您可以使用 DLP 报告在运行时微调您的 DLP 策略。
  
![安全与合规中心的报表仪表板](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>DLP 策略的工作原理

DLP 使用深入内容分析（而不仅仅是简单的文本扫描）来检测敏感信息。这种深入内容分析使用关键字匹配、字典匹配、正则表达式评估、内部函数以及其他方法来检测匹配 DLP 策略的内容。您的数据中可能只有一小部分数据被视为敏感数据。DLP 策略可以只识别、监视和自动保护那些敏感数据，而不会妨碍或影响处理您的内容的其余部分的人员。
  
### <a name="policies-are-synced"></a>策略会进行同步

在安全 &amp; 合规中心创建 DLP 策略后，它将存储在中心策略存储中，然后同步到各种内容源，其中包括：
  
- Exchange Online，并从它同步到 Outlook 网页版和 Outlook。
    
- OneDrive for Business 网站。
    
- SharePoint Online 网站。
    
- Office 桌面程序（Excel、PowerPoint 和 Word）。

- Microsoft Teams 频道和聊天消息。
    
该策略同步到正确的位置后，它将开始评估内容并强制执行操作。
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>OneDrive for Business 和 SharePoint Online 站点中的策略评估

文档在你的所有 SharePoint Online 站点和 OneDrive for Business 站点中会不断更改，用户会持续对文档执行创建、编辑、共享等操作。 这意味着文档可能随时会与 DLP 策略发生冲突，或变为合规状态。 例如，一个用户上载的文档可能不包含与团队站点相关的敏感信息，但之后，另一个客户可能会编辑同一文档，并向文档添加了敏感信息。
  
为此，DLP 策略经常检查后台中是否包含与策略相符的文档。您可以将这视为异步策略评估。<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>运作方式
 
在用户添加或更改其站点中的文档时，搜索引擎会扫描内容，以便你稍后对其进行搜索。 同时，还对此内容进行敏感信息扫描，以检查是否进行过共享。 找到的任何敏感信息都安全地存储在搜索索引中，以便仅供合规性团队而不是典型用户进行访问。 已启用的每个 DLP 策略在后台（异步）运行，它会经常检查搜索中是否包含与某个策略相符的内容，并应用操作以防止由于疏忽而导致泄漏。
  
![显示 DLP 策略如何异步计算内容的图表](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --> 最后，文档可能与 DLP 策略相冲突，但也可能符合 DLP 策略。例如，如果用户将信用卡号添加到文档，可能会导致 DLP 策略自动阻止对该文档的访问。但是，如果该用户稍后删除此敏感信息，则下一次根据此策略对此文档进行评估时，该操作（在这种情况下，阻止操作）将自动撤消。
  
DLP 评估可编制索引的任何内容。 有关默认的爬网文件类型的详细信息，请参阅 [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。

> [!NOTE]
> 为了防止在 DLP 策略有机会分析文档之前共享文档，可阻止在 SharePoint 中共享新文件，直到对其内容编制索引。 有关详细信息，请参阅[默认情况下，将新文件标记为敏感](/sharepoint/sensitive-by-default)。 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Exchange Online、Outlook 和 Outlook 网页版中的策略评估

当创建一个将 Exchange Online 包含为位置的 DLP 策略时，系统会将策略从 Office 365 安全 &amp; 合规中心同步到 Exchange Online，然后从 Exchange Online 同步到 Outlook 网页版和 Outlook。
  
在 Outlook 中撰写消息时，会显示策略提示，因为会根据 DLP 策略对创建的内容进行评估。 邮件发送后，会根据 DLP 策略对其进行评估，作为邮件流程的正常部分，还会使用 Exchange 管理中心中创建的 Exchange 邮件流规则（也称为传输规则）和 DLP 策略进行评估。 DLP 策略会扫描邮件及其所有附件。
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Office 桌面程序中的策略评估

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel、PowerPoint 和 Word 包含相同的功能，可像 SharePoint Online 和 OneDrive for Business 一样识别敏感信息和应用 DLP 策略。 这些 Office 程序直接从中心策略存储同步其 DLP 策略，然后在用户处理从包含在 DLP 策略中的网站打开的文档时，不断根据 DLP 策略对内容进行评估。
  
Office 中的 DLP 策略评估旨在不对程序的性能或处理内容的用户的工作效率产生任何影响。 如果他们正在处理大型文档，或用户的计算机正忙，可能需要几秒钟才能显示策略提示。

### <a name="policy-evaluation-in-microsoft-teams"></a>Microsoft Teams 中的策略评估
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

当创建一个将 Microsoft Teams 包含为位置的 DLP 策略时，系统会将策略从 Office 365 安全 &amp; 合规中心同步到用户帐户和 Microsoft Teams 频道和聊天消息。 根据 DLP 策略的配置方式，当某人尝试在 Microsoft Teams 聊天或频道消息中共享敏感信息时，可以阻止或撤消该消息。 并且，这些用户将无法打开包含敏感信息以及与来宾（外部用户）共享的文档。 若要了解详细信息，请参阅[数据丢失防护和 Microsoft Teams](dlp-microsoft-teams.md)。
 
## <a name="permissions"></a>权限

默认情况下，全局管理员、安全管理员和合规性管理员将有权访问创建和应用 DLP 策略。 创建 DLP 策略的合规性团队的其他成员需要安全与合规中心 &amp; 的权限。 默认情况下，租户管理员有权访问此位置，并可以授予合规部官员和其他人员对安全与合规中心的访问权限，而不授予租户管理员 &amp; 的所有权限。为此，我们建议您：
  
1. 在 Microsoft 365 中创建组并向其添加合规部主管。
    
2. 在安全 &amp; 合规中心的“**权限**”页面上创建一个角色组。 

3. 创建角色组时，使用“**选择角色**”部分向角色组添加以下角色：**DLP 合规性管理**。
    
4. 使用“**选择成员**”部分，将先前创建的 Microsoft 365 组添加到角色组中。

此外，还可通过授予“**仅查看 DLP 合规性管理**”角色，创建对 DLP 策略和 DLP 报告具有仅查看权限的角色组。

有关详细信息，请访问[向用户授予对 Office 365 合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
  
只有在创建和应用 DLP 策略时才需要这些权限。策略执行不需要访问此内容。
  
## <a name="find-the-dlp-cmdlets"></a>查找 DLP cmdlet

若要使用安全 &amp; 合规中心的大多数 cmdlet，你需要执行以下操作：
  
1. [使用远程 PowerShell 连接到 Office 365 安全与合规中心](/powershell/exchange/connect-to-scc-powershell)。
    
2. 使用任一 [policy-and-compliance-dlp cmdlet](/powershell/module/exchange/export-dlppolicycollection)。
    
但是，DLP 报告需要从 Microsoft 365（包括 Exchange Online）提取数据。 因此，**可以在 Exchange Online Powershell 中使用 DLP 报告的 cmdlet，而不能在安全 &amp; 合规中心 Powershell 中使用**。 因此，若要使用适用于 DLP 报告的 cmdlet，你需要执行以下操作：
  
1. [使用远程 PowerShell 连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。
    
2. 对 DLP 报告使用以下任意 cmdlet：
    
    - [Get-DlpDetectionsReport](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [Get-DlpDetailReport](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a>更多信息

- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
    
- [发送通知，并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)
    
- [创建 DLP 策略来保护具有 FCI 或其他属性的文档](protect-documents-that-have-fci-or-other-properties.md)
    
- [DLP 策略模板包含的内容](what-the-dlp-policy-templates-include.md)
    
- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
    
- [DLP 函数查找什么](what-the-dlp-functions-look-for.md)
    
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
