---
title: 合规中心中的最新更新
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 03/22/2020
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- m365-security-compliance
description: 就像 Microsoft 365 合规性中心中的功能一样，我们的帮助内容始终在发展中。 了解本月新增和更新的内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3060cadb5752d8420667105113e23e235ab6f306
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127509"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Microsoft 365 合规性内容的最新更新

就像 Microsoft 365 合规性中心中的功能一样，我们的帮助内容始终在发展中。 我们将不断创建新文章，更新现有文章，并根据你的反馈进行更改。 请查看以下内容，了解本月新增和更新的内容。

> [!TIP]
> 若要在 Microsoft 365 合规性中心中保持最新功能更新，请查看[microsoft 365 合规性中心中的新增](whats-new.md)功能。

## <a name="march-2020"></a>2020 年 3 月

### <a name="auditing"></a>审核

[使用高级审核调查已损坏的帐户](mailitemsaccessed-forensics-investigations.md)（新增）<br>有关使用新*MailItemsAccessed*邮箱审核操作进行鉴证调查的新指南。

[搜索审核日志](search-the-audit-log-in-security-and-compliance.md)（更新）<br>这些更改包括：
- 包含有关 "app@sharepoint" 用户在审核记录中列出的详细信息的[新内容](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records)。
- 隔离活动的[新说明](search-the-audit-log-in-security-and-compliance.md#quarantine-activities)。
- 在 "[用户管理活动](search-the-audit-log-in-security-and-compliance.md#user-administration-activities)" 部分中，阐明了当用户更改自己的密码（通过自助密码重置）时，将触发 "更改用户密码事件"，当管理员重置用户的密码时，将触发 "重置用户密码" 事件。

### <a name="auto-expanding-archive"></a>自动扩展存档

[无限存档概述](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)（已更新）<br>添加了一些说明：在邮箱上启用自动扩展存档后，不能删除主存档或辅助存档中的任何文件夹。

### <a name="compliance-scorecompliance-manager"></a>合规性分数/合规性管理器

所有[合规性分数](compliance-score.md)和[合规性管理器](compliance-manager-overview.md)主题都会反映在四月早些时候发布的对这些产品的更新（这两者仍在公开预览中）。 主要更新包括：
- 简化了创建和修改模板的过程
- 模板和操作的版本控制通知和控制
- 跨组同步常见操作
- 语言支持现已扩展到简体中文、中文（繁体）、法语、德语、意大利语、日语、朝鲜语、葡萄牙语（巴西）、俄语和西班牙语

### <a name="communication-compliance"></a>通信合规性

[案例研究-Contoso 为 Microsoft 团队、Exchange 和 Yammer 通信快速配置冒犯性语言策略](communication-compliance-case-study.md)（新）<br>针对教育和小型企业组织的分步研究，可帮助他们快速配置冒犯性语言策略。 随着组织在 COVID19 响应中上升而增加的客户请求数。

[通信合规性入门](communication-compliance-configure.md)（更新）<br>更新了许可和权限要求。

### <a name="customer-key"></a>客户密钥

[滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)（已更新）<br>组织更新，可帮助阐明可和不能滚动的密钥。

[了解客户密钥的可用性密钥](customer-key-availability-key-understand.md)（已更新）<br>添加了针对客户密钥的 Exchange Online 体系结构的说明。

### <a name="data-loss-prevention"></a>数据丢失防护

[数据丢失防护概述](data-loss-prevention-policies.md)（更新）<br>更新了保留标签需要多长时间才能生效，且未配置任何警报的默认行为策略。

### <a name="ediscovery"></a>电子数据展示

[高级电子数据展示入门](get-started-with-advanced-ediscovery.md)（新）<br>提供有关许可和权限要求的信息、配置全局设置和创建新事例的步骤以及高级电子数据展示工作流的演练。

[旧电子数据展示工具的退休](legacy-ediscovery-retirement.md)（更新）<br>由于公共运行状况情况，退休日期移出三个月。 更新了文章 cites 新的退休日期。

### <a name="insider-risk-management"></a>内部风险管理

[内幕风险管理入门](insider-risk-management-configure.md)（已更新）<br>更新了许可和权限要求。

[定义信息障碍策略](information-barriers-policies.md)（已更新）<br>阐明了应用所需的处理速度和时间。 添加了有关如何不应设置任何通讯簿策略的详细信息。 此外，还有各种 PowerShell 代码更新，包括用于筛选的新代码。

[信息障碍](information-barriers.md)（已更新）<br>修复了一些断开的链接和已更新的 PDF 链接和标题。 根据客户反馈，阐明了信息障碍仅支持双向限制。 单向限制（例如，市场营销可以与日贸易贸易通信，但不支持将 day 商贸与营销进行通信）。

[信息障碍故障排除](information-barriers-troubleshooting.md)（已更新）<br>新增了 "疑难解答方案" 一节。 添加了指向有关如何重新应用信息障碍的步骤的链接。

### <a name="office-365-message-encryption"></a>Office 365 邮件加密

[管理 Office 365 邮件加密](manage-office-365-message-encryption.md)（已更新）<br>进行了更新，以反映强制包装函数是一个标准的 OME 功能，而不是一个高级功能。 Rewrote PowerShell 示例，以排除对高级 OME 功能的所有引用吊销和过期。

[邮件加密 FAQ](ome-faq.md) （已更新）<br>阐明了仅 Outlook for web 可以应用临时加密。 同样，对于所有 Outlook 客户端，邮件和未受保护的 PDF 附件都会继承 Exchange Online 中的数据丢失防护（DLP）策略或邮件流规则的 OME 保护。

### <a name="privileged-access-management"></a>特权访问管理

[特权访问管理入门](privileged-access-management-configuration.md)（更新）<br>更新了许可和权限要求。

### <a name="pst-import"></a>PST 导入

[有关导入 PST 文件的常见问题解答](faqimporting-pst-files-to-office-365.md)（更新）<br>添加了有关 PST 导入过程如何处理重复的电子邮件的常见问题解答。

### <a name="sensitivity-labels"></a>敏感度标签

[了解敏感度标签](sensitivity-labels.md)（已更新）<br>添加了有关 Azure 门户中的标签管理的弃用详细信息，包括[正式通知](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179)的链接。

[敏感度标签入门](get-started-with-sensitivity-labels.md)（已更新）<br>添加了有关新的敏感度标签阅读者角色的信息，最初仅为标记 PowerShell cmdlet 提供支持。

[创建和配置敏感度标签及其策略](create-sensitivity-labels.md#removing-and-deleting-labels)（已更新）<br>新增了一个部分，说明了删除和删除标签的后果。

[使用敏感度标签保护 Microsoft 团队、microsoft 365 组和 SharePoint 网站中的内容](sensitivity-labels-teams-groups-sites.md)（已更新）<br>这些更改包括：

- 删除了 Azure AD 说明，而不是链接到[AZURE ad 权威信息](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)。
- 更新了 "[如何配置网站和组设置](sensitivity-labels-teams-groups-sites.md#how-to-configure-site-and-group-settings)" 部分，其中包含有关**Office 365 组连接的团队网站**设置（包括新的 "**无**" 选项）的隐私信息。
- 添加了说明在用户创建团队、组和网站时，如何仅使用带有网站和组设置的标签的说明。 此功能将向组织逐步推出。

[使用敏感度标签限制对内容的访问权限，以应用加密](encryption-sensitivity-labels.md)（已更新）<br>[新分区](encryption-sensitivity-labels.md#example-configurations-for-the-encryption-settings)，其中包含用于保护文档和电子邮件的一些最常用配置的示例加密设置。

[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)（已更新）<br>对内置标记与 Azure 信息保护统一标记客户端之间的行为差异的说明。

[在 SharePoint 和 OneDrive 中启用 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)（更新）<br>这些更改包括：

- 阐明了启用此预览除了标记和加密的支持文档外，还会在 Office for web 中显示标签的功能区上的**灵敏度**按钮。
- 更新了 Office 365 多地理位置的说明。
- 限制列表包含一个新条目，其中包括当计算机脱机或睡眠时以及是否删除某个标签时，会发生什么情况。

[在 Office 应用中使用敏感度标签](sensitivity-labels-office-apps.md)（已更新）<br>这些更改包括：

- 将许可信息移动到以[开始使用敏感度标签](get-started-with-sensitivity-labels.md)。
- [新部分](sensitivity-labels-office-apps.md#labeling-client-for-desktop-apps)介绍如何使用内置于 office 桌面应用程序中的标签。您必须使用 office 的订阅版本，而不是独立版。
- 受支持的应用程序表包括适用于 iOS 和 Android 的 Office 应用，以及允许用户为 Word、Excel 和 PowerPoint 分配权限的配置。现在，向下滚动到 Windows 和 Mac 的每月频道。  
- [新部分](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-other-labeling-solutions)介绍了如何使用组策略设置禁用内置标签（如果你当前正在使用要为 Windows 计算机保持使用的其他标记解决方案）。 
- 更新了[信息权限管理（IRM）选项和敏感度标签](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)部分，并提供了使用应用加密（而非 IRM 选项）的标签的建议，并对两个保护解决方案混合使用时对潜在后果的解释。

### <a name="trainable-classifiers"></a>Trainable 类元

[Trainable 分类器的入门（预览）](classifier-getting-started-with.md) （已更新）<br>添加了有关冒犯性语言模板弃用方式的信息。 此外，还添加了一个表，其中列出了源代码内置分类器中使用的前25种代码语言。

## <a name="february-2020"></a>2020 年 2 月

> [!NOTE]
> 上个月中列出的文章可能已更新、移动或删除。 因此，下面的一些详细信息可能已过时，并且链接可能会断开。

### <a name="auditing"></a>审核

[Microsoft 365 中的高级审核](advanced-audit.md)（新）<br>适用于使用 Office 365 E5 或 Microsoft 365 企业版 E5 订阅的组织，高级审核通过引入功能（如审核日志的长保留期、新的审核日志保留策略和跟踪邮件读取的新邮箱审核操作）扩展了现有的审核功能。

[管理审核日志保留策略](audit-log-retention-policies.md)（新增）<br>有关管理审核日志保留策略的详细信息，新的高级审核功能允许您将不同服务的审核记录保存一年。

[管理邮箱审核](enable-mailbox-auditing.md#logon-types-and-mailbox-actions)（更新）<br>添加了有关新的 MailItemsAccessed 邮箱操作的信息，该操作是通过高级审核引入的。

[搜索审核日志](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)（更新）<br>新增了有关敏感度标签活动的新说明以及有关审核[表单协作活动](search-the-audit-log-in-security-and-compliance.md#forms-activities-performed-by-coauthors-and-anonymous-responders)的其他信息。

### <a name="compliance-offerings"></a>合规性产品/服务

[ENISA 信息保证框架](offering-enisa.md)（新）<br>支持欧洲网络和信息安全代理（ENISA）信息保障框架（IAF）的新主题。

[服务组织控制（SOC）](offering-SOC.md) （已更新）<br>添加了新的审核引用。

[澳大利亚 Prudential 规章机构（APRA）](offering-APRA-Australia.md) （已更新）<br>新法规标准的对齐内容。

### <a name="customer-key"></a>客户密钥

[使用客户密钥进行服务加密](customer-key-overview.md)（新）<br>向您介绍客户密钥的新文章、相关概念（如 BitLocker 和服务加密）以及它们如何协同工作。

[管理客户密钥](customer-key-manage.md)（新）<br>用于管理客户密钥的安装后说明，包括管理现有 DEPs 和密钥保管库权限的步骤、估计完成操作的时间、如何验证加密是否有效以及如何退出服务。

[滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)（新）<br>介绍如何为客户密钥滚动客户管理的密钥。

[了解客户密钥的可用性密钥](customer-key-availability-key-understand.md)（新）<br>可用性密钥的详细信息-何时以及如何使用它从密钥丢失以及在客户密钥层次结构中存在的地方恢复，等等。

[设置 Microsoft 365 的客户密钥](customer-key-set-up.md)（已更新）<br>以前标题为 "使用客户密钥控制 Microsoft 365 中的数据"，本文重点介绍如何设置 Office 365 的客户密钥（包括更新的说明）。

### <a name="data-classification"></a>数据分类

[数据分类公共预览版发布说明（预览）](data-classification-pub-preview-relnotes.md) （新）<br>公共预览版的发行说明介绍了新功能，在创建任何策略之前，会开始扫描您的敏感和带标签的内容。 这样，您就可以查看现有的保留和敏感度标签对组织有何影响，以帮助您评估保护和治理策略需求。

### <a name="gdpr"></a>GDPR

[Office 365 针对 GDPR 和 CCPA 的数据主体请求](gdpr-dsr-Office365.md)（更新）<br>删除了对 Microsoft StaffHub 的引用，因为应用已被[停](https://docs.microsoft.com/microsoftteams/expand-teams-across-your-org/shifts/microsoft-staffhub-to-be-retired)用。

在以下文章中添加了合规性管理器参考和更新的合规性分数链接。<br>
[常规数据保护管理法规摘要](gdpr.md)（本文还包括来自信任中心的新常见问题解答。）<br>
[Microsoft 365 GDPR 行动计划 - 前 30 天、前 90 天以及之后的首要行动](gdpr-action-plan.md)<br>
[通过责任就绪清单支持 GDPR 计划](gdpr-arc.md)<br>
[适用于 GDPR 的 Azure 责任准备情况清单](gdpr-arc-Azure.md)<br>
[适用于 GDPR 的 Dynamics 365 责任就绪清单](gdpr-arc-Dynamics365.md)<br>
[适用于 Microsoft Office 365 的责任准备情况清单](gdpr-arc-Office365.md)<br>

### <a name="insider-risk-management"></a>内部风险管理

更新了以下文章以支持内幕风险管理的正式发行版。<br>
[了解 Microsoft 365 中的内幕风险管理](insider-risk-management.md)<br>
[内部风险管理入门](insider-risk-management-configure.md)<br>
[创建和管理内部风险策略](insider-risk-management-policies.md)<br>
[调查内部风险警报](insider-risk-management-alerts.md)<br>
[对内部风险案例采取措施](insider-risk-management-cases.md)<br>
[使用内部风险内容资源管理器查看数据](insider-risk-management-content-explorer.md)<br>
[将用户添加到内部风险策略](insider-risk-management-users.md)<br>
[创建内幕风险通知](insider-risk-management-notices.md)<br>

### <a name="records-management"></a>记录管理

[保留标签概述](retention.md)（已更新）<br>基于条件应用保留标签的部分现在包括使用 trainable 分类器的选项。

### <a name="sensitivity-labels"></a>敏感度标签

[敏感度标签入门](get-started-with-sensitivity-labels.md)（新增）<br>包括 Azure 信息保护客户指南，简要概述了部署灵敏度标签的过程和步骤，创建和管理标签的权限、支持标签的常见方案列表以及可用最终用户文档的列表。

[了解敏感度标签](sensitivity-labels.md)（已更新）<br>Retitled from "敏感度标签概述"，并将 "入门" 一节中的信息移到新文章[开始使用敏感度标签](get-started-with-sensitivity-labels.md)。

[创建和配置敏感度标签及其策略](create-sensitivity-labels.md)（已更新）<br>将权限详细信息移动到新文章后，[开始使用敏感度标签](get-started-with-sensitivity-labels.md)。

[使用敏感度标签限制对内容的访问权限，以应用加密](encryption-sensitivity-labels.md)（已更新）<br>新的 "无" 和 "删除" 选项将替换加密切换，"添加任何经过身份验证的用户" 将添加为新的立即分配权限。 "允许用户分配权限" 部分现在更新，提示用户在 Word、PowerPoint 和 Excel 中选择自定义权限，以便在 Windows 和 Mac 预览中进行滚动。 新内容示例配置的示例配置，如何配置加密设置以支持特定用例。 列出了用于加密内容的注意事项的新部分。

[将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)（已更新）<br>为 Office 应用程序配置自动标记的部分现在包含了使用 trainable 分类器的新选项。

[使用敏感度标签保护 Microsoft 团队、microsoft 365 组和 SharePoint 网站中的内容](sensitivity-labels-teams-groups-sites.md)（已更新）<br>在整个中进行修订，以获得更好的阅读体验和技术说明。 此外，根据客户反馈，添加了指向[AZURE AD 文章](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels)的链接，用于启用预览并将敏感度标签应用于 azure 门户中的 Microsoft 365 组。 最后，为审核敏感度标签活动添加了一个新的部分。

[在 SharePoint 和 OneDrive 中启用 Office 文件的敏感度标签（公开预览）](sensitivity-labels-sharepoint-onedrive-files.md) （更新）<br>各种更新包括每个客户有关此功能的工作方式反馈的说明，强调新功能仅适用于新的和编辑过的文件，以及在删除标签时可能仅在测试阶段中看到的新限制。

[在 Office 应用中使用敏感度标签](sensitivity-labels-office-apps.md)（已更新）<br>更新了允许用户分配权限以及自动将标签应用于内容的功能表。 此外，根据客户反馈，为继承标签的电子邮件附件添加了例外。

### <a name="service-descriptions"></a>服务说明

[适用于安全性的 Microsoft 365 许可指南 & 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)（已更新）<br>Retitled 来自 "Microsoft 365 租户级服务许可指南" 以更好地反映内容。

