---
title: 检测具有通信合规性的通道信号
description: 详细了解如何检测通信合规性的通道信号。
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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 36707b372467bebdee5c5bcee114511ce7c385d1
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321347"
---
# <a name="detect-channel-signals-with-communication-compliance"></a>检测具有通信合规性的通道信号

借助通信合规性策略，可以选择作为组或作为独立源扫描以下一个或多个通信平台中的邮件。 根据组织的保留和保留策略，跨这些平台捕获的原始邮件将保留在原始平台 [位置](/microsoft-365/compliance/information-governance)。 只要策略已就位，通信合规性策略用于分析和调查的邮件副本将保留一段时间，即使用户离开您的组织并删除其邮箱。 删除通信策略时，也会删除与该策略关联的邮件的副本。

## <a name="microsoft-teams"></a>Microsoft Teams

可以扫描公共和专用Microsoft Teams和单个聊天中的聊天通信。 当用户分配到通信合规性策略，Microsoft Teams范围时，将在用户是成员的所有 Microsoft Teams自动监视用户的聊天通信。 Microsoft Teams预定义的策略模板自动包含此范围，并且默认情况下会在自定义策略模板中选中此范围。 Teams匹配通信合规性策略条件的聊天最多可能需要 48 小时才能处理。

对于私人聊天和私人频道，通信合规性策略支持新式附件扫描。 新式附件是一些来自[OneDrive SharePoint或](/onedrive/plan-onedrive-enterprise#modern-attachments)网站的文件[](/sharepoint/dev/solution-guidance/modern-experience-customizations)，这些文件包含在Teams中。 自动从这些附件中提取文本，以自动处理文本，并可能与活动通信合规性策略条件和分类器匹配。 新式附件检测和处理不需要任何其他配置。 仅为匹配策略条件的附件提取文本。 即使附件还具有策略匹配项，也不为包含策略匹配项的邮件的附件提取文本。

以下文件类型支持新式附件扫描：

- Microsoft Word (.docx) 
- Microsoft Excel (.xlsx) 
- Microsoft PowerPoint (.pptx) 
- 文本 (.txt) 
- 可移植文档格式 (.pdf)

用于新式附件的提取文本包含在策略的" **挂起警报"** 仪表板上的关联邮件中。 附件的提取文本被命名为附件文件名和 (扩展名) 扩展名.txt扩展名。 例如，名为ContosoBusinessPlan.docx的附件的提取文本 *ContosoBusinessPlan.docx.txt在策略* 的挂起警报仪表板中显示。** 

选择提取的附件文本以查看"源"视图、"纯文本"或"批注"*视图中* 的详细信息。 查看后，可以使用命令栏控件解析附件文本或对附件文本采取操作。 还可以选择下载附件，以在通信合规性审阅流程之外查看。

使用以下组管理配置来监督用户聊天和频道中Teams：

- **For Teams chat communications：** Assign individual users or assign a [distribution group](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) to the communication compliance policy. 这个设置适用于一对一或一对多聊天。
- **For Teams Channel communications：** Assign every Microsoft Teams channel or Microsoft 365 group you want to scan that contains a specific user to the communication compliance policy. 如果你将同一用户添加到其他 Microsoft Teams 频道或者 Microsoft 365 组，要确保将这些新频道和组也添加到通信合规性策略中。 如果频道的任何成员是策略中的受监督用户，并且策略中配置了入站方向，那么在频道内发送的所有邮件都需接受审阅，并且可能的策略与 (即使对于未明确监督) 的频道中的用户也一样。 例如，用户 A 是频道的所有者或成员。 用户 B 和用户 C 是同一频道的成员，并且使用与仅监督用户 A 的不当内容策略相匹配的语言。用户 B 和用户 C 为频道内的对话创建策略匹配项，即使它们未直接在不适当的内容策略中受到监督。 Teams包括用户 A 的频道之外的用户 B 和用户 C 之间的对话不会受包含用户 A 的不当内容策略的影响。若要在频道的其他成员受到明确监督时排除频道成员监督，请关闭适用通信合规性策略中的入站通信方向设置。
- **For Teams chat communications with hybrid email environments**： Communication compliance can monitor chat messages for organizations with an Exchange on-premises deployment or an external email provider that have enabled Microsoft Teams. 您必须为具有要监视本地邮箱或外部邮箱的用户创建通讯组。 创建通信合规性策略时，您将此通讯组分配为策略向导中的监督用户和组选择。 有关为本地用户启用基于云的存储和 Teams 支持的要求和限制，请参阅搜索本地用户的 Teams 聊天[数据](search-cloud-based-mailboxes-for-on-premises-users.md)。

## <a name="exchange-email"></a>Exchange 电子邮件

托管在 Exchange Online 订阅或 Microsoft 365 Office 365 上的邮箱都符合邮件扫描条件。 Exchange合规性策略条件匹配的电子邮件和附件可能需要 24 小时才能处理。 通信合规性支持的附件类型与 [Exchange 邮件流规则内容检查支持的文件类型](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)相同。

## <a name="yammer"></a>Yammer

可以扫描社区中的私人Yammer对话以及关联的附件。 将用户添加到将 Yammer定义为定义的频道的通信合规性策略时，该用户是其中成员的所有 Yammer 社区之间的通信将包含在扫描过程中。 Yammer合规性策略条件匹配的聊天和附件最多可能需要 24 小时处理。 

Yammer必须进入[本机模式](/yammer/configure-your-yammer-network/overview-native-mode)，通信合规性策略Yammer通信和附件。 在本机模式下，Yammer用户都Azure Active Directory (AAD) 组，所有组Office 365组，所有文件都存储在 SharePoint Online 中。

## <a name="skype-for-business-online"></a>Skype for Business Online

可以监督 Skype for Business Online 中的聊天通信和相关附件。 Skype for Business Online 中匹配通信合规性策略条件的聊天内容和附件可能需要 24 小时处理。 监督的聊天对话来自之前[保存在 Skype for Business Online 的对话](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)。  

使用以下组管理配置监督 Skype for Business Online 中的用户聊天通信：

- **For Skype for Business Online chat communications**： Assign individual users or assign a [distribution group](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) to the communication compliance policy. 这个设置适用于一对一或一对多聊天。

## <a name="third-party-sources"></a>第三方源

你可以扫描通信，以从第三方源（如 [Instant Bloomberg](archive-instant-bloomberg-data.md)、[Slack](archive-slack-data.md)、[Zoom](archive-zoommeetings-data.md)、SMS 和许多其他源）Microsoft 365组织中导入到邮箱的数据。 有关通信合规性支持的连接器的完整列表，请参阅存档 [第三方数据](archiving-third-party-data.md)。

必须先为组织配置第三方Microsoft 365，然后才能将连接器分配到通信合规性策略。 通信 **合规性策略** 向导的"第三方源"部分仅显示当前配置的第三方连接器。
