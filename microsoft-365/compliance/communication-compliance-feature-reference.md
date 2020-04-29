---
title: 通信合规性功能参考
description: Microsoft 365 中的通信合规性的功能参考。 了解每个功能组件的详细信息和规格。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 1a63e71df0d9ac6d43fce31ad2e974b787697a9a
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919669"
---
# <a name="communication-compliance-feature-reference"></a>通信合规性功能参考

## <a name="policies"></a>策略

>[!Important]
>不支持使用 PowerShell 创建和管理通信合规性策略。 若要创建和管理这些策略，必须使用[Microsoft 365 通信合规性解决方案](https://compliance.microsoft.com/supervisoryreview)中的策略管理控件。

在 Microsoft 365 合规性中心为 Microsoft 365 组织创建通信合规性策略。 如果你拥有 Microsoft 365 组织，你将在安全 & 合规中心中[配置监督策略](configure-supervision-policies.md)。 通信合规性策略定义哪些通信和用户将在组织中进行审阅，定义通信必须满足的自定义条件，并指定应进行审核的用户。 **监管审核管理员**角色组中包括的用户可以设置策略，并且分配了此角色的任何人都可以访问 Microsoft 365 合规性中心中的**通信合规性**页面。 如果需要，您可以将对策略所做修改的历史记录导出到 .csv 文件中，该文件还包括待审阅的通知、已升级的项目和已解决的项目的状态。 策略不能重命名，在不再需要时可删除。

>[!NOTE]
>在安全 & 合规中心中创建的针对 Office 365 订阅的监督策略不能迁移到 Microsoft 365。 如果要从 Office 365 订阅迁移到 Microsoft 365 订阅，您需要创建新的通信合规性策略以替换现有的监督策略。

## <a name="policy-templates"></a>策略模板

策略模板是预定义的策略设置，可用于快速创建策略以解决常见的合规性情况。 这些模板中的每一个都有不同的条件和范围，并且所有模板都使用相同类型的扫描信号。 您可以从以下策略模板中进行选择：

|**区域**|**策略模板**|**Details**|
|:-----|:-----|:-----|
| **冒犯性语言和反骚扰** | 监视攻击性语言的通信 | -位置： Exchange Online、Microsoft 团队、Yammer、Skype for Business <br> -方向：入站、出站、内部 <br> -审阅百分比：100% <br> -条件：冒犯性语言分类符 |
| **敏感信息** | 监视敏感信息的通信 | -位置： Exchange Online、Microsoft 团队、Yammer、Skype for Business <br> -方向：入站、出站、内部 <br> -审阅百分比：10% <br> -条件：敏感信息、现成的内容模式和类型、自定义词典选项、大于 1 MB 的附件 |
| **合规性** | 监视与金融合规性相关的信息的通信 | -位置： Exchange Online、Microsoft 团队、Yammer、Skype for Business <br> -方向：入站、出站 <br> -审阅百分比：10% <br> -条件：自定义词典选项，附件大于 1 MB |

## <a name="supervised-users"></a>受监督用户

在开始使用通信合规性之前，必须确定哪些用户需要查看其通信。 在策略中，用户电子邮件地址标识要监督的个人或人员组。 这些组的一些示例是 Microsoft 365 组、基于 Exchange 的通讯组列表、Yammer 社区和 Microsoft 团队频道。 此外，还可以将特定用户或组排除在扫描时使用特定的排除组或组列表。

>[!IMPORTANT]
>通信合规性策略涵盖的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证，或包含在 Office 365 企业版 E5 订阅中。如果你没有现有的企业版 E5 计划，并且想要尝试进行通信合规性，则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。

## <a name="reviewers"></a>Reviewers

创建通信合规性策略时，必须确定谁审查受监督的用户的邮件。 在该策略中，用户电子邮件地址标识了要查看受监督的通信的个人或人员组。 所有审阅者都必须在 Exchange Online 上托管邮箱，并且必须为其分配**事例管理**和**审核**角色。

## <a name="groups-for-supervised-users-and-reviewers"></a>受监督的用户和审阅者的组

若要简化设置，请为需要查看其通信的用户创建组，并为查看这些通信的用户分组。 如果使用的是组，可能需要多个。 例如，如果要扫描两个不同的人员组之间的通信，或者要指定未受监督的组。

当您为受监督的用户选择 Microsoft 365 组时，该策略将扫描共享邮箱的内容以及与该组关联的 Microsoft 团队频道。 当您选择通讯组列表时，该策略将扫描单个用户邮箱。

## <a name="supported-communication-types"></a>支持的通信类型

通过通信合规性策略，您可以选择将以下一个或多个通信平台中的邮件作为组或独立的源进行扫描。 默认情况下，跨这些平台捕获的通信每个策略保留7年，即使用户离开组织并删除了其邮箱也是如此。

- **Microsoft 团队**：可以扫描公共和私有 Microsoft 团队频道和个人聊天中的交流通信和相关附件。 团队聊天和附件匹配通信合规性策略条件可能需要长达24小时才能完成处理。 使用以下组管理配置监督团队中的个人用户聊天和通道通信：

    - **对于团队聊天通信：** 分配单个用户或将[通讯组](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)分配给通信合规性策略。 此设置适用于一对一或一对多的用户/聊天关系。
    - **对于团队渠道通信：** 分配要扫描的每个 Microsoft 团队频道或 Microsoft 365 组，其中包含特定用户的通信合规性策略。 如果将同一用户添加到其他 Microsoft 团队频道或 Microsoft 365 组，请确保将这些新的频道和组添加到通信合规性策略中。

- **Exchange 电子邮件**：作为 Microsoft 365 或 Office 365 订阅的一部分托管在 Exchange Online 上的邮箱都有资格进行邮件扫描。 Exchange 电子邮件和与通信合规性策略条件匹配的附件可能需要长达24小时才能完成处理。 通信合规性支持的附件类型与[Exchange 邮件流规则内容检查支持的文件类型](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)相同。

- **Yammer**：可以扫描 yammer 社区中的私人邮件和公共对话以及关联的附件。 将用户添加到包含 Yammer 作为定义的频道的通信合规性策略时，扫描过程中将包含该用户所属的所有 Yammer 社区之间的通信。 Yammer 聊天和与通信合规性策略条件匹配的附件可能需要长达24小时才能完成处理。 Yammer 必须处于[本机模式](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)，以使通信合规性策略监视 Yammer 通信和附件。 在本机模式中，所有 Yammer 用户都在 Azure Active Directory （AAD）中，所有组都是 Office 365 组，并且所有文件都存储在 SharePoint Online 中。

- **Skype For Business online**：可以监督 skype For business online 中的聊天通信和相关附件。 符合通信合规性策略条件的 Skype for Business Online 聊天可能需要长达24小时才能完成处理。 受监督聊天对话源于[以前在 Skype for Business Online 中保存的对话](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)。  使用以下组管理配置监督 Skype for Business Online 中的用户聊天通信：

    - **对于 Skype For Business Online 聊天通信**：分配个人用户或将[通讯组](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)分配给通信合规性策略。 此设置适用于一对一或一对多的用户/聊天关系。

- **第三方来源**：可以扫描第三方源的通信，以获取导入到 Microsoft 365 组织中的邮箱的数据。 连接器支持以下第三方资源：

    - [即时 Bloomberg](archive-instant-bloomberg-data.md)
    - [Facebook](archive-facebook-data-with-sample-connector.md)
    - [领英](archive-linkedin-data.md)
    - [Twitter](archive-twitter-data-with-sample-connector.md)
    - [自定义数据连接器](archiving-third-party-data.md)

您必须先为 Microsoft 365 组织配置第三方连接器，然后才能将连接器分配给通信合规性策略。 "通信合规性策略向导" 的 "**第三方源**" 部分仅显示当前配置的第三方连接器。

## <a name="transitioning-from-supervision-in-office-365"></a>从 Office 365 中的监察转换

在 Office 365 中使用监督策略并计划在 Microsoft 365 中过渡到通信合规性策略的组织需要了解这些重要事项：

- 这两种解决方案可在您的组织中并行使用，但是在每个解决方案中使用的策略必须具有唯一的策略名称。 在转换期间，可以在解决方案之间共享组和自定义关键字词典。
- 在 Office 365 策略匹配中保存的邮件无法在 Microsoft 365 中移动或共享到通信合规性中。
- Office 365 中的监督解决方案将被 Microsoft 365 中的通信合规性解决方案完全取代。 我们建议在通信合规性中创建新策略，这些策略与现有监督策略具有相同的设置，以使用新的调查和补救措施改进。 在 Microsoft 365 中转换到通信合规性时，如果您具有内部合规性保留策略要求，则应计划在 Office 365 中的监察时导出报告数据。

有关 Office 365 中监察的退休信息，请参阅[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)了解详细信息。

## <a name="policy-settings"></a>策略设置

### <a name="users"></a>用户

您可以选择选择 "**所有用户**" 或 "在通信合规性策略中定义特定用户"。 如果选择 "**所有用户**"，则会将该策略应用于作为成员包含的所有用户和所有组的所有用户。 定义特定用户可将该策略应用于已定义的用户以及作为成员包含的已定义用户的任何组。

### <a name="direction"></a>Direction

默认情况下，显示**方向是**条件，不能删除。 策略中的通信方向设置分别或一起选择：

- **入站**：可以选择 "**入站**" 以查看发送**到**您选择监督的人员的通信。
- **出站**：如果想要查看**从**你选择进行监督的人员发送的通信，可以选择 "**出站**"。
- **Internal**：可以选择 "**内部**" 以查看在策略中标识的人员**之间**发送的通信。

### <a name="sensitive-information-types"></a>敏感信息类型

您可以选择将敏感信息类型作为通信合规性策略的一部分包括在内。 敏感信息类型可以是预定义的，也可以是自定义的数据类型，可帮助确定和保护信用卡号码、银行帐号、护照号码等。 作为[数据丢失防护（DLP）](data-loss-prevention-policies.md)的一部分，敏感信息配置可以使用模式、字符邻近度、可信度和偶数自定义数据类型，以帮助识别和标记可能敏感的内容。 默认的敏感信息类型为：

- 金融
- 医疗和运行状况
- 隐私
- 自定义信息类型

若要了解有关敏感信息详细信息和默认类型中包含的模式的详细信息，请参阅[要查找的敏感信息类型](what-the-sensitive-information-types-look-for.md)。

### <a name="custom-keyword-dictionaries"></a>自定义关键字词典

配置自定义关键字词典（或词典），以提供特定于您的组织或行业的关键字的简单管理。 关键字字典支持每个字典最高为100000个术语，并支持任何语言。 如果需要，您可以将多个自定义关键字词典应用于单个策略或每个策略包含一个关键字词典。 这些词典在通信合规性策略中分配，可从文件（如 .csv 或 .txt 列表）或可以[在合规中心中导入](create-a-keyword-dictionary.md)的列表中获得。 当您需要支持特定于您的组织和策略的术语或语言时，请使用自定义词典。

### <a name="classifiers"></a>符

内置分类程序在组织中的所有通信通道中扫描发送或接收的邮件，以解决不同类型的合规性问题。 分类器使用人工智能和关键字的组合来确定邮件中可能违反反骚扰策略的语言。 内置的分类器目前仅支持在邮件中提供英语关键字。

通信合规性内置分类程序针对以下语言类型扫描术语和看法的通信：

- **威胁**：扫描对人员或属性的暴力或物理伤害的威胁。
- **骚扰**：扫描针对竞争、颜色、宗教、国家/地区的相关人员的攻击性行为。
- **猥亵语言**：扫描大多数人 embarrass 的 profane 表达式。

内置分类器不提供跨这些区域的术语的详尽列表。 此外，语言和文化标准不断变化，而在这些现实中，Microsoft 保留在决定时随时更新分类器的权利。 虽然分类器可以帮助组织监控这些方面，但分类程序并不旨在提供组织的唯一方法来监视或解决此类语言。 您的组织（而不是 Microsoft）仍负责与这些领域中的扫描和阻止语言相关的所有决策。

有关 Microsoft 365 中的分类器的信息，请参阅[分类](classifier-getting-started-with.md)器。

### <a name="conditional-settings"></a>条件设置
<a name="ConditionalSettings"> </a>

您为策略选择的条件适用于来自组织中的电子邮件和第三方来源的通信（如 Facebook 或 DropBox）。

下表对每个条件进行了详细说明。
  
|**条件**|**如何使用此条件**|
|:-----|:-----|
| **内容与这些分类器中的任何类元匹配** | 在邮件中包含或排除任何分类器时，应用于该策略。 某些分类器在租户中预定义，必须单独配置自定义分类器，然后才可用于此条件。 只能将一个分类器定义为策略中的条件。 有关配置分类器的详细信息，请参阅[分类](classifier-getting-started-with.md)器。 |
| **内容包含这些敏感信息类型中的任何一种** | 在邮件中包含或排除任何敏感信息类型时，应用于该策略。 有些分类器是在租户中预定义的，可以单独配置自定义分类程序，也可以将其作为条件分配过程的一部分进行配置。 您选择的每种敏感信息类型都是单独应用的，只有其中一种敏感信息类型必须适用于该策略应用于邮件。 有关自定义敏感信息类型的详细信息，请参阅[自定义敏感信息类型](custom-sensitive-info-types.md)。 |
| **从这些域中的任何域接收邮件**  <br><br> **不从这些域中的任何域接收邮件** | 应用该策略以在接收的邮件中包含或排除特定域或电子邮件地址。 输入每个域或电子邮件地址，并使用逗号分隔多个域或电子邮件地址。 输入的每个域或电子邮件地址将单独应用，只有一个域或电子邮件地址必须应用于该邮件的策略。 <br><br> 如果要扫描来自特定域的所有电子邮件，但又要排除不需要审阅的邮件（新闻稿、通知等），则必须配置**不会从任何不接收**电子邮件地址的域条件（示例 "newsletter@contoso.com"）中接收邮件。 |
| **将邮件发送到这些域中的任何域**  <br><br> **邮件不会发送到这些域中的任何域** | 应用该策略以在已发送邮件中包含或排除特定域或电子邮件地址。 输入每个域或电子邮件地址，并使用逗号分隔多个域或电子邮件地址。 每个域或电子邮件地址单独应用，只有一个域或电子邮件地址必须申请策略才能应用于邮件。 <br><br> 如果要扫描发送到特定域的所有电子邮件，但要排除不需要审阅的已发送邮件，则必须配置两个条件： <br> -将**消息发送到**定义域的任何域条件（"contoso.com"），并 <br> -**邮件不会发送到任何**不包括电子邮件地址（"subscriptions@contoso.com"）的域条件。 |
| **邮件使用以下任何标签进行分类**  <br><br> **不使用这些标签中的任何一个对邮件进行分类** | 在邮件中包含或排除某些保留标签时应用策略。 必须单独配置保留标签，并在此条件中选择已配置的标签。 您选择的每个标签都将单独应用（必须只有其中一个标签适用于该策略应用于邮件）。 有关配置保留标签的详细信息，请参阅[保留标签概述](labels.md)。|
| **邮件包含以下任何词语**  <br><br> **邮件不包含以下任何词语** | 若要在邮件中包含或排除某些字词或短语时应用策略，请输入以逗号分隔的每个单词。 对于两个或多个单词的短语，请在短语两边使用引号。 您输入的每个单词或短语都将单独应用（必须只有一个词适用于该策略应用于邮件）。 若要详细了解如何输入字词或短语，请参阅下一部分[Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords)。|
| **附件包含这些词语中的任何一个**  <br><br> **附件中不包含任何词语** | 若要在邮件附件（如 Word 文档）中包含或排除某些字词或短语时应用该策略，请输入以逗号分隔的每个单词。 对于两个或多个单词的短语，请在短语两边使用引号。 您输入的每个单词或短语都将单独应用（必须只有一个词适用于该策略应用于附件）。 若要详细了解如何输入字词或短语，请参阅下一部分[Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords)。|
| **附件是这些文件类型中的任何一种**  <br><br> **附件是这些文件类型中的任何一种** | 若要监督包含或排除特定类型附件的通信，请输入文件扩展名（如 .exe 或 .pdf）。 如果要包含或排除多个文件扩展名，请在单独的行上输入这些扩展名。 要应用的策略仅有一个附件扩展名必须匹配。|
| **邮件大小大于**  <br><br> **邮件大小不大于** | 若要查看基于特定大小的邮件，请使用这些条件来指定邮件在被审阅前可以达到的最大或最小大小。 例如，如果您指定的**邮件大小大于** \> **1.0 mb**，则所有 1.01 MB 和更大的邮件都将被审阅。 这种情况下，您可以选择字节、千字节、兆字节或千兆字节。|
| **附件大于**  <br><br> **附件不大于** | 若要根据附件的大小查看邮件，请指定邮件之前的附件的最大或最小大小，并且其附件可能会被审阅。 例如，如果指定**附件大于** \> **2.0 mb**，则所有附件为 2.01 mb 的邮件都将被审阅。 这种情况下，您可以选择字节、千字节、兆字节或千兆字节。|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>将字词和短语与电子邮件或附件匹配
<a name="Matchwords"> </a>

您输入的每个单词将单独应用（必须只有一个词适用于策略条件应用于电子邮件或附件）。 例如，我们将使用条件，**邮件包含这些词语中的任何词语**，关键字为 "银行家"、"机密" 和 "内幕交易"，由逗号（银行家，机密，"内幕交易"）分隔。 该策略适用于任何邮件，其中包括 "银行家"、"保密" 或短语 "内幕交易" 一词。 只有出现其中一个字词或短语，才能应用此策略条件。 邮件或附件中的单词必须与您输入的内容完全匹配。

>[!IMPORTANT]
>在导入自定义词典文件时，每个单词或短语必须用回车符分隔，并在单独的行上。 <br> 例如： <br><br>
>*五* <br>
>*秘密* <br>
>*内幕交易*

若要扫描相同关键字的电子邮件和附件，请为您希望在邮件中扫描的术语创建一个包含[自定义关键字词典](create-a-keyword-dictionary.md)的[数据丢失防护策略](create-test-tune-dlp-policy.md)。 此策略配置标识在电子邮件**或**电子邮件附件中显示的已定义关键字。 使用标准条件策略设置（*邮件包含以下任何词语*和*附件包含这些词语中的*任意词语）标识邮件中和附件中的术语时，需要在邮件和附件**BOTH**中显示这些术语。
  
#### <a name="enter-multiple-conditions"></a>输入多个条件

如果您输入多个条件，Microsoft 365 将所有条件一起使用，以确定何时将监督策略应用于通信项目。 在设置多个条件时，必须满足所有条件，才能应用策略，除非您输入了异常。 例如，如果邮件包含 "商贸" 一词，并且大于 2 MB，则需要适用的策略。 但是，如果邮件还包含 "由 Contoso 财务批准批准" 的词，则该策略不应应用。 在此示例中，将按如下所示定义三个条件：
  
- **邮件包含这些词语中的任何词语**，关键字为 "商贸"
- **邮件大小大于**，值为 2 MB
- **邮件不包含这些词语**，关键字 "由 Contoso 财务团队批准"

### <a name="review-percentage"></a>审阅百分比

如果要减少要查看的内容量，可以指定监督策略控制的所有通信的百分比。 从符合所选策略条件的内容的总百分比中选择内容的实时、随机样本。 如果您希望审阅者审阅所有项目，则可以在通信合规性策略中配置**100%** 。

## <a name="notices"></a>通知

如果要在问题解决过程中向用户发送策略匹配的电子邮件提醒通知，则可以创建通知模板。 仅可将通知发送到与生成特定的补救警报的策略匹配项关联的员工电子邮件地址。 在选择要应用于作为修正工作流一部分的策略违规的声明模板时，您可以选择接受模板中定义的字段值，也可以根据需要覆盖这些字段。

通知模板是自定义电子邮件模板，可在其中定义以下消息字段：

|**Field**|**Required**| **Details** |
|:-----|:-----|:-----|
|**模板名称** | 是 | "通知" 模板的友好名称，您将在修正期间的 "通知" 工作流中选择，支持文本字符。 |
| **发件人地址** | 是 | 将邮件发送给具有策略匹配的员工的一个或多个用户或组的地址，该用户或组是从 Active Directory 中为订阅选择的一个或多个用户或组。 |
| **抄送和密件抄送地址** | 否 | 从 Active Directory 为你的订阅选择的策略匹配通知的可选用户或组。 |
| **主题** | 是 | 显示在邮件主题行中的信息支持文本字符。 |
| **邮件正文** | 是 | 显示在邮件正文中的信息支持文本或 HTML 值。 |

### <a name="html-for-notices"></a>用于通知的 HTML

如果要创建多个简单的基于文本的电子邮件通知，可以通过使用通知模板的邮件正文字段中的 HTML 来创建更详细的消息。 下面的示例提供基于 HTML 的基本电子邮件通知模板的邮件正文格式：

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

>[!NOTE]
>通信合规性通知模板中的 HTML href 属性实现目前仅支持对 URL 引用采用单引号而不是双引号。

## <a name="filters"></a>筛选器

通过通信合规性筛选器，可以对警报消息进行筛选和排序，以便更快地进行调查和修正操作。 筛选在每个策略的 "**挂起**" 和 "**已解决**" 选项卡上可用。 若要将筛选器或筛选器集保存为已保存的筛选器查询，必须将一个或多个值配置为筛选器选择。 下表概述了筛选器详细信息：

|**Filter**|**Details**|
|:-----|:-----|
| **Date** | 组织中的用户发送或接收邮件的日期。 |
| **File 类** | 基于邮件类型（*邮件*或*附件*）的邮件类。 |
| **有附件** | 邮件中的附件状态。 |
| **Item 类** | 基于邮件类型、电子邮件、Microsoft 团队聊天、Bloonmberg 等的邮件源。 |
| **收件人域** | 向其发送邮件的域。 默认情况下，此域通常为 Microsoft 365 订阅域。 |
| **收件人** | 向其发送邮件的用户。 |
| **Sender** | 发送邮件的人员。 |
| **发件人域** | 发送邮件的域。 |
| **大小** | 邮件的大小，以 KB 为单位。 |
| **主题/职务** | 邮件主题或聊天标题。 |
| **Tags** | 分配给邮件的标记，无论是*可疑*的*还是**不兼容*的。 |
| **升级到** | 作为邮件升级操作的一部分包含的人员的用户名。 |
| **符** | 应用于邮件的内置和自定义分类器的名称。 一些示例包括*冒犯性语言*、*目标骚扰*、*猥亵*、*威胁*等。

## <a name="alert-policies"></a>警报策略

配置策略后，系统会自动创建相应的通知策略，并为符合策略中定义的条件的邮件生成警报。 默认情况下，在关联的警报策略中，会为所有策略匹配警报触发器，并将其严重性级别分配为介质。 在关联的警报策略中满足聚合触发器阈值级别后，将为通信合规性策略生成警报。

对于通信合规性策略，默认情况下配置以下警报策略值：

|**通知策略触发器**|**默认值**|
|:-----|:-----|
| 聚合 | 简单聚合 |
| 阈值 | 4个活动 |
| Window | 60分钟 |

>[!Note]
>活动的警报策略阈值触发设置支持的通信合规性策略的最小值为3或更高。

您可以在 "安全性 & 合规性中心的"**通知**策略 "页上的活动数量、活动期限和" 通知策略 "页上的特定用户更改触发器的默认设置。

### <a name="change-the-severity-level-for-an-alert-policy"></a>更改通知策略的严重性级别

如果您想要更改针对特定通信合规性策略的通知策略中分配的严重性级别，请完成以下步骤：

1. 在 Microsoft [https://compliance.microsoft.com](https://compliance.microsoft.com) 365 组织中使用管理员帐户的凭据进行登录。

2. 在 Microsoft 365 合规性中心中，转到 "**策略**"。

3. 在 "**策略**" 页上选择 " **office 365 警报**"，打开**office 365 安全性 & 合规中心**"中的"**通知策略**"页。

4. 选中要更新的通信合规性策略的复选框，然后选择 "**编辑策略**"。

5. 在 "**说明**" 选项卡上，选择 "**严重性**" 下拉列表以配置策略警报级别。

6. 选择 "**保存**" 以将新的严重性级别应用于策略。

7. 选择 "**关闭**" 以退出 "通知策略详细信息" 页。

## <a name="audit"></a>跟踪

在某些情况下，您必须向法规或合规性审核人员提供信息，以证明员工活动和通信的监督。 此信息可能是与定义的组织策略相关联的所有活动的摘要，也可能是与通信合规性策略的任何更改。 通信合规性策略具有内置审核跟踪，可以实现内部或外部审核的完整就绪状态。 您的通信策略将捕获每个创建、编辑和删除操作的详细审核历史记录，以提供监督过程的证明。

>[!Important]
>必须为你的组织启用审核，然后才会记录通信合规性事件。 若要启用审核，请参阅[启用审核日志](communication-compliance-configure.md#step-2-required-enable-the-audit-log)。

若要查看通信合规性策略活动，请在主页上为任何策略选择 "**导出审阅活动**" 控件。 此操作将生成 .csv 格式的审核文件，其中包含以下信息：

|**Field**|**Details**|
|:-----|:-----|
| **CreationDate** | 在策略中执行活动的日期。 |
| **UserIds** | 在策略中执行活动的用户。 |
| **Operations** | 对策略执行的操作。 |
| **AuditData** | 此字段是所有策略活动的主要数据源。 将记录所有活动，并以逗号分隔符分隔。 |

您还可以在统一审核日志中或使用[UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell cmdlet 查看审核活动。

例如，下面的示例返回所有监管审核活动（策略和规则）的活动：

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

本示例返回您的通信合规性策略的更新活动：

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>准备好开始了吗？

若要为 Microsoft 365 组织配置通信合规性，请参阅[配置 microsoft 365 组织的通信合规性](communication-compliance-configure.md)。
