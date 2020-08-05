---
title: 合规中心的新增功能
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 我们不断将新功能添加到 Microsoft 365 合规性中心。 了解我们在本月所做的操作。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77ba6f0926a1826fe6c946ff4f8c05cf913c57ed
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560259"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Microsoft 365 合规性中心的新增功能

我们不断将新功能添加到[Microsoft 365 合规性中心](microsoft-365-compliance-center.md)，修复我们了解的问题，并根据你的反馈进行更改。 请查看下面的内容，查看今天可为你提供的内容。 有些功能以不同的速度向客户推出。 如果尚未看到功能，请尝试将自己添加到[目标版本](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)。

> [!TIP]
> 对其他管理中心中的内容有兴趣？ 查看以下文章：<br>[Microsoft 365 管理中心的新增功能](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 管理中心的新增功能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br><br>
并访问[microsoft 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap)，了解已启动的 microsoft 365 功能、正在开发、已被取消或之前已发布的功能。

## <a name="june-2020"></a>2020 年 6 月

### <a name="spotlight-new-data-connectors-hit-preview"></a>聚光灯：新数据连接器命中预览

为了帮助您将数据从更多的第三方源导入 Microsoft 365，我们很高兴地宣布推出两个更多数据连接器的预览版本：

- [Bloomberg 消息](archive-bloomberg-message-data.md)。 从 Bloomberg 邮件协作工具导入和存档金融服务电子邮件数据。 在存储在邮箱中的数据后，您可以访问和使用合规性功能中的数据，如诉讼保留、内容搜索、就地存档、审核、通信合规性和保留策略。
- [ICE 聊天](archive-icechat-data.md)。 从 "ICE 聊天协作" 工具导入和存档金融服务聊天数据。 在存储在邮箱中的数据后，您可以访问和使用合规性功能中的数据，如诉讼保留、电子数据展示、存档、审核、通信合规性和保留策略。

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>合规性分数 & 合规性管理器：已继续进行了访问

六月更新包括[符合性分数](compliance-score.md)中的新评估向下钻取视图。 监视器控制进度、添加、删除评估直接依据合规性分数等。

想要掌握对合规性分数和合规性管理器的更新的最新信息？ 为[合规性分数发布说明](compliance-score-release-notes.md)加上书签，并经常查看。

## <a name="may-2020"></a>2020 年 5 月

### <a name="spotlight-data-classification-is-officially-released"></a>聚光灯：已正式发布数据分类

数据分类（亦称为 "[了解数据](data-classification-overview.md)"）功能 (分析、内容资源管理器和活动资源管理器) 从预览阶段开始渐变，并可供所有组织使用。 功能强大的见解和工具可帮助您发现和评估在您的组织中的内容中使用的敏感信息和标签 (保留和敏感度) 。 查看包含敏感信息或应用了标签的内容、跨 Microsoft 365 位置浏览标签活动、创建自定义敏感信息类型等。

获取视频教程 .。。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>Trainable 分类程序：修补程序和功能

可能对 trainable 分类器进行了更多增强：

- 基于你的反馈的修补程序：当你设定自定义分类器的种子和训练时，不再需要手动输入 SharePoint 网站 Url 和文件夹路径。 您现在可以从预先填充的网站和文件夹列表中进行选择。
- 新功能：创建灵敏度标签和配置 Office 应用的自动标记设置时，您现在可以自动应用 (或建议用户将标签应用于与 trainable 分类程序匹配的内容) 。 [了解更多](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>通信合规性：此处为 Yammer 支持

在通信合规性策略中支持 Yammer 中的私人邮件和公共社区对话。 Yammer 是一个可选的频道，并且必须处于[本机模式](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)以支持邮件和附件的扫描。

### <a name="data-loss-prevention-new-sharing-restriction"></a>数据丢失防护：新的共享限制

在设置 DLP 策略以保护 SharePoint 或 OneDrive 中的内容时，您现在可以配置 "限制对内容的访问" 操作，以阻止通过 "[具有链接的任何人](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)" 选项访问内容的人员。

### <a name="insider-risk-management-tailor-your-alert-volume"></a>内幕风险管理：定制警报音量

由内幕风险策略检测到的用户活动被分配了特定风险分数，这反过来又决定了警报严重性 (低、中、高) 。 默认情况下，Microsoft 365 会生成一定数量的低、中和高严重性警报，但在新的[警报卷设置](insider-risk-management-settings.md#alert-volume)中，可以根据需要增加或减小该卷。

### <a name="pst-import-new-region-supported"></a>PST 导入：支持的新区域

网络上传现已推出阿拉伯联合酋长国。

### <a name="sensitivity-labels-new-privacy-option"></a>敏感度标签：新隐私选项

为标签配置[网站和组设置](sensitivity-labels-teams-groups-sites.md#how-to-configure-site-and-group-settings)时，您现在可以将 "隐私" 选项设置为 "**无-允许用户选择可以访问网站的用户**"。 如果要使用敏感度标签保护容器中的内容，但仍允许用户自行配置隐私设置，这将非常有用。

## <a name="april-2020"></a>2020 年 4 月

### <a name="records-management-overhauland-a-new-addition"></a>记录管理：检修 .。。以及新的添加

四月份包含对我们的记录管理解决方案的几个关键更新：

- "记录管理" 部分现已在合规性中心中完全可用。 充分利用更新的用户界面和功能，用于文件计划、保留标签和标签策略、事件和处置。
- 说到了处置，我们还为 SharePoint 和 OneDrive 中的记录提供了[处置证明](disposition.md#disposition-of-records)。 现在，您可以在已自动或在处置评审之后处置的这些位置中的项目列表进行查看。

:::image type="content" source="../media/mcc-records-management-page.png" alt-text="Microsoft 365 合规性中心中的 "记录管理" 部分":::

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>敏感度标签：预览自动标记策略

使用自动标记策略，您现在可以自动将敏感度标签应用于已保存的 SharePoint 和 OneDrive 文档， (是 "静态数据") 和已发送或接收的电子邮件 (又称为 "传输中的电子邮件" ) 。 由于此标记由服务（而不是应用程序）应用，因此无需担心用户拥有哪些应用以及什么版本。

此功能扩展了在创建灵敏度标签时，已包含在 "Office 应用程序的自动标记" 设置中的现有客户端标签。 若要快速了解这两种自动标记选项的区别和优点，请查看[更新后的文章](apply-sensitivity-label-automatically.md)。

## <a name="march-2020"></a>2020 年 3 月

### <a name="introducing-advanced-audit"></a>高级审核简介

[Microsoft 365 中的高级审核](advanced-audit.md)引入了新的审核功能，可帮助组织进行取证和合规性调查。 要点包括长期保留审核日志、自定义审核日志保留策略、新*MailItemsAccessed*邮箱审核操作，以及引入新的租户级别限制限制，这将为组织提供自己的完全分配的带宽配额以访问审核数据。

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>合规性分数 & 合规性管理器：预览最新的增强功能

此预览版版本的关键更新包括：

- 简化了创建和修改模板的过程
- 模板和操作的版本控制通知和控制
- 跨组同步常见操作
- 语言支持现已扩展到中文 (简化) 、中文 (传统) 、法语、德语、意大利语、日语、朝鲜语、葡萄牙语 (巴西) 、俄语和西班牙语

了解有关[合规性分数](compliance-score.md)和[合规性管理器](compliance-manager-overview.md)的详细信息

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>敏感度标签：在 SharePoint 和 OneDrive 中对 Office 文件进行标记的支持 (预览) 

启用预览后，用户可以在 web 上的 Office 中应用敏感度标签。 他们将能够在状态栏上看到功能区上的**灵敏度**按钮和应用的标签名称。 此外，如果用户在 SharePoint 或 OneDrive 上使用桌面应用程序标记并保存文件，Microsoft 365 现在将能够处理这些文件的内容（如果标签应用了加密设置）。 在这些情况下，还将支持合著、电子数据丢失、数据丢失防护、搜索以及其他协作功能。

[了解如何启用预览](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>2020 年 2 月

### <a name="insider-risk-management-is-officially-released"></a>正式发布的内幕风险管理

鼓总纸，请 .。。<br>内幕风险管理现在可供具有以下订阅的组织使用：

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (付费或试用) 
- Microsoft [E5 合规性加载](https://go.microsoft.com/fwlink/?linkid=2120432)项的 Microsoft 365 企业版 E3 订阅

在预览版本（包括[新的角色组](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)和[解决方案范围的设置](insider-risk-management-configure.md#step-4-configure-insider-risk-settings)）之后进行了一些改进。

与往常一样，请在使用解决方案时留下反馈，以便我们可以继续进行改进。

### <a name="records-management"></a>记录管理

这一新的解决方案将所有记录管理功能都引入到一个伞中。 重点包括引入了 SharePoint 和 OneDrive 的记录版本控制以及记录的处置证明。

![Microsoft 365 合规性中心中的 "记录管理" 页](../media/mcc-records-management-page.png)

[了解有关记录管理的详细信息](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>解决方案焦点： Facebook 和 Twitter 的数据连接器

[上个月发布](#just-launched)的数据连接器，我们将在测试以下连接器时查找您的帮助。

- [Facebook 商业页面](archive-facebook-data-with-sample-connector.md)。 将 Facebook 商业页面中的数据导入和存档到 Microsoft 365。 对法规遵从性解决方案（如记录管理和电子数据展示）有益。
- [Twitter](archive-twitter-data-with-sample-connector.md)。 将 Twitter 中的数据导入和存档到 Microsoft 365。 对法规遵从性解决方案（如记录管理和电子数据展示）有益。

在您设置和验证这些连接器时，请向我们提供有关什么情况的反馈、什么不是什么，以及我们可以执行哪些操作来改进体验。

## <a name="january-2020"></a>2020 年 1 月

等待已结束。 我们很高兴宣布 Microsoft 365 合规性中心可供所有客户使用 Microsoft 365、Office 365、企业移动性 + 安全性 (EMS) 和 Windows 10 企业版计划。 在安全 & 合规性中心中管理的任何数据或策略在合规性中心中均可用，因此无需来回跳转。

> [!TIP]
> 再次阅读上个月的更新，以了解最近预览的一些[新解决方案](#new-compliance-solutions)的刷新器，以及说明安全 & 合规性中心中的合规性功能现在在 Microsoft 365 中的活动的[路线图](#updated-compliance-solutions)。

书签并将其置于现在，以 [https://compliance.microsoft.com](https://compliance.microsoft.com) 浏览您的一站式管理合规性，以跨整个组织 .。。或者[阅读本文](microsoft-365-compliance-center.md)以进一步深入研究。

![Microsoft 365 合规性中心主页](../media/mcc-home-ga.png)

我们也在本月发布了新的和更新的解决方案。 下面将快速浏览一下重点。

### <a name="now-in-preview"></a>现在预览

**内幕风险管理 (预览) **

我们很高兴宣布，我们的内幕风险管理解决方案现已处于公共预览版中。 简言之，内幕风险管理可帮助您的组织智能化地识别和采取对内幕风险的操作，方法是提供：

- 可帮助确保用户隐私的匿名控件。
- 智能策略模板，带有可识别内幕威胁的本机和第三方指示符，如数据泄露。
- 跨 IT、HR 和法律团队的集成的端到端调查工作流。

我们乐意听到你的想法。 在使用解决方案时，请将反馈留给我们，以确保我们在实现常规可用性时能够满足你的需求。

[了解有关内幕风险管理的详细信息](insider-risk-management.md)

### <a name="just-launched"></a>刚刚启动

**通信合规性**

毕业从预览阶段到完整可用性，通信合规性是我们新的内幕风险解决方案集的关键组件。 此强健的解决方案可帮助最大限度地减少使用工作流对不符合组织标准的邮件进行检测、调查和采取补救措施的工作流的通信风险。

在预览过程中，客户反馈很棒。 它产生了几项增强功能，包括首次运行体验，使您能够开始、调查和修正操作的改进等。

[了解有关通信合规性的详细信息](communication-compliance.md)

![Microsoft 365 合规性中心中的通信合规性页面，显示欢迎体验的第一张卡片](../media/mcc-communication-compliance-page-with-fre.png)

**数据连接器**

以前与 Office 365 安全 & 合规中心中的其他 "导入" 功能共享空间，数据连接器现在在 Microsoft 365 合规性中心拥有自己的主址。 使用新的 "数据连接器" 页面导入组织的人力资源中的数据，并将其存档 (HR) 文件和各种第三方平台 (如 Facebook、LinkedIn、Twitter 和即时 Bloomberg) 到 Microsoft 365 组织中的邮箱。 导入后，可以在几个合规性解决方案中管理此类数据，包括电子数据展示、内幕风险管理、通信合规性、审核、保留策略等。

[了解有关数据连接器的详细信息](archiving-third-party-data.md)

![Microsoft 365 合规性中心中的 "数据连接器" 页](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>值得注意的更新

**适用于合规性分数的新评估模板 (预览版) **

始终致力于帮助您提前掌握日益发展的合规性，我们的合规性分数团队提供了一组新的模板，以帮助您评估组织对最新法规的合规性情况，并获取有关如何实施更有效的控制措施的指导。 你将看到以下内容的新模板：

- ISO/IEC 27701:2019
- 加州消费者隐私法案 (CCPA)
- 巴西常规数据保护法律 (Lei Geral de Proteção de Dados-LGPD) 
- SOC 1 类型2和 SOC 2 类型2

[了解有关合规性分数模板的详细信息](compliance-score.md#templates)

## <a name="november--december-2019"></a>2019年11月 &

在节日中，我们开始推出 Ignite 中演示的所有极好的合规性解决方案。 大多数情况下都处于预览状态，因此请将其测试出来，并确保通过打开合规性中心右侧右侧的反馈卡片来了解你的想法。

![反馈](../media/Feedback_card_MCC.JPG)

### <a name="get-to-know-the-new-neighborhood"></a>了解新的邻居

新的 Microsoft 365 合规性中心包含全新的解决方案以及 Office 365 安全性 & 合规性中心中了解和喜欢的合规性功能。 让我们更深入地了解 .。。

#### <a name="new-compliance-solutions"></a>新的合规性解决方案

您可能想知道什么是*解决方案*。 与云相比，云已彻底改变了业务的完成方式，它还为新的数据盗用和欺诈和必要的新法规提供了门。 我们的合规性解决方案是集成功能的集合，可帮助您帮助您管理这些不断发展的合规性要求。 解决方案的功能可能包括策略、警报、报告等的组合。

以下是你将发现的新解决方案的摘要。 请留意即将推出的其他人。

> [!NOTE]
> 这些解决方案仅位于 Microsoft 365 合规性中心。 不能在 Office 365 安全 & 合规性中心中进行管理。
<br/>

|**新解决方案**|**说明**|**了解更多**|
|:-----|:-----|:-----|
|Microsoft (预览版中的 Microsoft 合规性分数)  <br/>|根据[合规性管理器](compliance-manager-overview.md)，合规性分数是一项独立功能，可帮助您了解和改进组织的合规性状态，这是一个更简单、更易于用户友好的设计。 它将计算基于风险的分数，以衡量您在帮助降低数据保护和法规标准方面的风险的完成操作的进度。 <br/>|[ (预览的 Microsoft 合规性分数概述) ](compliance-score.md)|
| (预览的解决方案目录)  <br/>|解决方案目录是用于发现、了解和快速开始使用合规性和风险管理解决方案的一站式业务。 目录分为三个符合性类别，每个类别都包含有关组成该类别的解决方案的详细信息。 类别包括信息保护 & 治理、内幕风险管理和发现 & 响应 <br/>|[解决方案目录 (预览的概述) ](microsoft-365-solution-catalog.md)|
| (预览的通信合规性)  <br/>|通信合规性是新的内幕风险管理类别的一部分，可帮助您对组织中不适当的邮件进行检测、捕获和采取补救措施，以帮助最大限度地减少通信风险。 该解决方案通过引入几项新的增强功能（如智能模板、灵活的修正工作流和可操作的见解）扩展了监督策略在 Office 365 中的功能。 <br/>|[Microsoft 365 (预览版中的通信合规性) ](communication-compliance.md)|
|数据分类 (预览)  <br/>|我们新的数据分类页面包含强大的见解和工具，可帮助您发现和评估在您的组织中的内容中使用的敏感信息和标签 (保留和敏感度) 。 查看包含敏感信息或应用了标签的内容、跨 Microsoft 365 位置浏览标签活动、创建自定义敏感信息类型，以及更多。<br/>|[数据分类概述（预览）](data-classification-overview.md)|
|Trainable 类元 (预览)  <br/>|此功能强大的新工具使用我们的机器学习引擎帮助确定您的组织中的内容类别，如法规文档或员工协议。 创建后，可以在几个合规性解决方案中使用分类器来检测相关内容并对其进行分类、保护、保留等。<br/>|[可训练分类器入门（预览）](classifier-getting-started-with.md)|

#### <a name="updated-compliance-solutions"></a>更新了合规性解决方案

如果你已使用 Office 365 安全 & 合规性中心满足你的合规性需求，你可能会想知道在新的 Microsoft 365 合规性中心中，一些功能现在处于活动状态。 以下是帮助查找其新家庭的快速路线图。

> [!NOTE]
> 某些功能仍仅在 Office 365 安全 & 合规性中心中提供，如下所示。 但我们正在努力在 Microsoft 365 合规性中心预览这些问题，因此请随时关注更新。 
<br/>

|**功能**|**Office 365 安全与合规中心**|**Microsoft 365 合规中心**|**了解更多**|
|:-----|:-----|:-----|:-----|
|高级电子数据展示|电子数据展示 > 高级电子数据展示 <br/> https://protection.office.com/advancedediscoverycases |电子数据展示 > 高级 <br/> https://compliance.microsoft.com/advancedediscovery | [Microsoft 365 中的高级电子数据展示解决方案概述](overview-ediscovery-20.md) |
|警报策略|警报 > 通知策略 <br/> https://protection.office.com/alertpolicies |目前，仅在 Office 365 安全性 & 合规性中心中管理警报策略。 |[安全与合规中心警报策略](alert-policies.md) |
|警报|警报 > 查看警报 <br/> https://protection.office.com/viewalerts |警报 <br/> https://compliance.microsoft.com/compliancealerts |[查看警报](alert-policies.md#viewing-alerts)|
|存档|信息治理 > 存档 <br/> https://protection.office.com/archiving |信息治理 > 存档 "选项卡 <br/> https://compliance.microsoft.com/informationgovernance?viewid=archive |[启用存档邮箱](enable-archive-mailboxes.md)|
|审核日志搜索|搜索 > 审核日志搜索 <br/> https://protection.office.com/unifiedauditlog |Audit <br/> https://compliance.microsoft.com/auditlogsearch | [在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)|
|内容搜索|搜索 > 内容搜索 <br/> https://protection.office.com/contentsearchbeta?ContentOnly=1 | 内容搜索 <br/> https://compliance.microsoft.com/contentsearch |[在 Office 365 中搜索内容](search-for-content.md) |
|数据连接器|信息治理 > 存档第三方数据 <br/> https://protection.office.com/nativeconnector | 数据连接器 <br/> https://compliance.microsoft.com/connectorlanding |[存档第三方数据](archiving-third-party-data.md)|
|数据丢失防护|数据丢失防护 <br/> https://protection.office.com/datalossprevention |数据丢失防护 <br/> https://compliance.microsoft.com/datalossprevention |[数据丢失防护概述](data-loss-prevention-policies.md)|
|数据主体请求 |数据隐私 > 数据主体请求 <br/> https://protection.office.com/dsrcases |数据主体请求 <br/> https://compliance.microsoft.com/datasubjectrequest |[使用 DSR case 工具管理 GDPR 数据主体请求](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md)|
|电子数据展示|电子数据展示 > 电子数据展示 <br/> https://protection.office.com/ediscoveryv1 |电子数据展示 > 核心 <br/> https://compliance.microsoft.com/classicediscovery |[管理电子数据展示事例](ediscovery-cases.md) |
|活动|记录管理 > 事件 <br/> https://protection.office.com/events |记录管理 > 事件选项卡 <br/> https://compliance.microsoft.com/recordsmanagement?viewid=events |[从事件发生时开始计算保留期](event-driven-retention.md)|
|文件计划|记录管理 > 文件计划 <br/> https://protection.office.com/fileplan |记录管理 > 文件计划选项卡 <br/> https://compliance.microsoft.com/recordsmanagement?viewid=fileplan |[使用文件计划管理保留标签](file-plan-manager.md)|
|导入 PST 文件|信息治理 > 导入 PST 文件 <br/> https://protection.office.com/importV2 |信息管理 > 导入选项卡 <br/> https://compliance.microsoft.com/informationgovernance?viewid=import |[有关导入组织的 PST 文件的概述](importing-pst-files-to-office-365.md)|
|标签活动资源管理器|信息治理 > 标签活动资源管理器 <br/> https://protection.office.com/labelexplorer |"数据分类 > 活动资源管理器" 选项卡 <br/> https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer |[查看关于标记的内容的活动（预览版）](data-classification-activity-explorer.md)|
|保留标签和标签策略 |分类 > 保留标签 > 标签和标签策略选项卡 <br/> https://protection.office.com/retentionlabels |信息治理 > 标签和标签策略选项卡 <br/> https://compliance.microsoft.com/informationgovernance?viewid=labels <br/> https://compliance.microsoft.com/informationgovernance?viewid=labelpolicies | [保留标签概述](retention.md)|
|保留策略|信息治理 > 保留 <br/> https://protection.office.com/retention |信息治理 > 保留选项卡 <br/> https://compliance.microsoft.com/informationgovernance?viewid=retention |[了解保留策略和保留标签](retention.md)|
|敏感信息类型|分类 > 敏感信息类型 <br/> https://protection.office.com/sensitivetypes |数据分类 > 敏感信息类型选项卡 <br/> https://compliance.microsoft.com/dataclassification?viewid=sensitiveinfotypes |[敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)|
|敏感度标签和标签策略|分类 > 敏感度标签 > 标签和标签策略 "选项卡 <br/> https://protection.office.com/sensitivity |信息保护 > 标签和标签策略选项卡 <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabels <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabelpolicies |[了解敏感度标签](sensitivity-labels.md) |
|服务保证|服务保证 <br/> https://protection.office.com/serviceassurance/dashboard |目前，服务保证资源只能在 Office 365 安全 & 合规性中心中访问。 |[安全与合规中心内的服务保证](service-assurance.md)|
|监督|监督 <br/> https://protection.office.com/supervisoryreviewv2 |通信合规性 <br/> https://compliance.microsoft.com/supervisoryreview |[Microsoft 365 (预览版中的通信合规性) ](communication-compliance.md) |

## <a name="september-2019"></a>2019 年 9 月

不知为什么在本月的版本中静音？ 我们正在开发的新的创新合规性解决方案将在11月的[Microsoft Ignite](https://www.microsoft.com/ignite)中 unveiled。 请随时关注！

### <a name="new-encryption-options-for-sensitivity-labels"></a>用于敏感度标签的新加密选项 

为敏感度标签配置加密时，您现在有两个选项，可让用户在手动将标签应用于电子邮件和文档时分配权限：<br>
- 将标签应用于**Outlook 电子邮件**时，用户可以强制实施与 "不转发" 选项等效的限制。 收件人将能够读取邮件，但不能转发、打印或复制内容。
- 将标签应用于**Word、PowerPoint 和 Excel 文件**时，系统将提示用户为特定用户和组分配访问权限。

转到 "[使用敏感度标签限制对内容的访问" 以应用加密](encryption-sensitivity-labels.md#let-users-assign-permissions)以了解详细信息。

## <a name="august-2019"></a>2019 年 8 月

### <a name="update-to-data-investigations"></a>对数据调查的更新

在执行数据调查时，您现在可以从其原始位置删除项目。 这意味着您可以在组织中删除 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户中的项目。 由于已将项目作为证据收集，因此您可以将这些项目的副本保留在证据集中，以便您可以进一步调查或仅保留为参考。 请转到[管理 Microsoft 365 中的 data 外泄事件](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data)以了解详细信息。 

## <a name="july-2019"></a>2019 年 7 月

### <a name="new-admin-roles"></a>新管理员角色

我们发布了两个新的管理员角色，以帮助管理您的组织中的安全性和合规性。请告诉你的所有朋友。

- **合规性数据管理员**。具有此角色的用户具有在 Microsoft 365 合规性中心、Microsoft 365 管理中心和 Azure 中保护和跟踪数据的权限。 它们还可以管理 Exchange 管理中心、合规性管理器、团队 & Skype for Business 管理中心并为 Azure 和 Microsoft 365 创建支持票证。
- **Security 运算符**。 具有此角色的用户可以管理警报并拥有对安全相关功能的全局只读访问权限，其中包括 Microsoft 365 安全中心、Azure Active Directory、Identity Protection、特权身份管理和 Office 365 安全性 & 合规性中心中的所有内容。

[了解有关这些角色的详细信息](https://docs.microsoft.com/microsoft-365/security//office-365-security/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>搜索和筛选报告

不会再滚动浏览报告的海洋，以查找您需要的报告。 现在，您可以根据报表 (的标题) 和筛选类别（如 "标签" 和 "合规性"）和源（如 "Office 365" 和 "Microsoft 云应用安全性"）搜索报表。

![包含已应用筛选器的报表的搜索和筛选按钮的屏幕捕获](../media/mcc_report_filtering.png)
