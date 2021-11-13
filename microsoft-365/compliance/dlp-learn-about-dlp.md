---
title: 了解终结点数据丢失防护
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 了解如何使用数据丢失防护策略和工具Microsoft 365敏感信息，并浏览 DLP 生命周期。
ms.openlocfilehash: 2552fe2482ba06fd34403fe2ff690bdf11c7bd20
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950553"
---
# <a name="learn-about-data-loss-prevention"></a>了解终结点数据丢失防护

组织拥有其控制的敏感信息，例如财务数据、专有数据、信用卡号、健康记录或社会保险号。 为了帮助保护此敏感数据并降低风险，他们需要一种方法来防止其用户与不应具有该数据的人不当共享它。 此做法称为 DLP (数据丢失) 。

在Microsoft 365中，通过定义和应用 DLP 策略来实现数据丢失防护。 使用 DLP 策略，可以标识、监视和自动保护以下各项中的敏感项目：

- Microsoft 365服务，如 Teams、Exchange、SharePoint 和 OneDrive
- Office Word、Excel 和 PowerPoint
- Windows 10终结点
- 非 Microsoft 云应用
- 本地文件共享和本地SharePoint。

Microsoft 365内容分析检测敏感项目，而不只是通过简单的文本扫描。 内容按以下方法进行分析：关键字的主数据匹配、正则表达式评估、内部函数验证和与主要数据匹配接近的辅助数据匹配。 此外，DLP 还使用机器学习算法和其他方法来检测与 DLP 策略匹配的内容。

## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a>DLP 是大型合规性Microsoft 365的一部分

Microsoft 365 DLP 只是一Microsoft 365合规性工具，可用于帮助保护您的敏感项目，无论它们身在何处或出差。 您应该了解 Microsoft 365 合规性工具集内的其他工具、它们如何相互关联以及如何更好地协同工作。  请参阅[Microsoft 365合规性工具](protect-information.md)，详细了解信息保护过程。

## <a name="protective-actions-of-dlp-policies"></a>DLP 策略的保护操作

Microsoft 365 DLP 策略是监视用户对其余敏感项目、传输中的敏感项或使用中的敏感项目执行的活动，并采取保护措施。 例如，当用户尝试采取禁止的操作（如将敏感项目复制到未批准的位置或在电子邮件中共享医疗信息或策略中规定的其他状况）时，DLP 可以：

- 向用户显示一个弹出策略提示，警告他们可能会尝试以不当方式共享敏感项目
- 阻止共享，并且通过策略提示允许用户覆盖阻止并捕获用户的理由
- 在没有替代选项的情况下阻止共享
- 对于处于其余状态的数据，敏感项目可以锁定并移动到安全隔离位置
- 对于Teams，将不会显示敏感信息

默认情况下，所有 DLP 受监视的活动都记录到Microsoft 365[审核日志](search-the-audit-log-in-security-and-compliance.md)，并路由到活动[资源管理器](data-classification-activity-explorer.md)。 当用户执行符合 DLP 策略条件的操作并且配置了警报时，DLP 将在 DLP 警报管理仪表板 [中发出警报](dlp-configure-view-alerts-policies.md)。

## <a name="dlp-lifecycle"></a>DLP 生命周期

DLP 实现通常遵循以下主要阶段。

- [DLP 计划](#plan-for-dlp)
- [准备 DLP](#prepare-for-dlp)
- [在生产中部署策略](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a>DLP 计划

Microsoft 365 DLP 监视和保护对于用户每天使用的应用程序是本机的。 这可帮助保护组织的敏感项目免受风险活动的影响，即使用户未习惯数据丢失防护的思路和做法。 如果您的组织和用户对数据丢失防护做法没有了解，则采用 DLP 可能需要更改业务流程，并且您的用户会进行文化转变。 但是，通过适当的规划、测试和调整，DLP 策略将保护敏感项目，同时最大限度地减少任何潜在的业务流程中断。

**DLP 技术规划**

请记住，作为一种技术，DLP 可以监视和保护处于非活动状态的数据、使用中的数据和跨 Microsoft 365 服务、Windows 10 设备、本地文件共享和本地 SharePoint 运行的数据。 对不同位置、要监视和保护的数据类型以及发生策略匹配时要采取的操作有规划影响。

**规划 DLP 的业务流程**

DLP 策略可以阻止禁止的活动，例如通过电子邮件不当共享敏感信息。 在规划 DLP 策略时，必须确定涉及敏感项目的业务流程。 用户业务流程可帮助你识别应允许的适当用户行为以及应防止的不当用户行为。 应先规划策略，在测试模式下部署策略，并首先通过活动资源管理器评估[](data-classification-activity-explorer.md)其影响，然后再在更严格的模式下应用策略。

**DLP 的组织文化规划**

成功的 DLP 实现与让用户接受数据丢失防护实践的训练和适应，就像在精心规划并调整策略上一样。 由于用户涉及大量内容，因此请务必为用户规划培训。 在将策略强制执行从测试模式更改为更严格的模式之前，你可以从战略上使用策略提示提高用户意识。

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a>准备 DLP

您可以将 DLP 策略应用于处于其余状态的数据、使用中的数据和位置中运动的数据，例如：

- Exchange Online电子邮件
- SharePoint Online 站点
- OneDrive 账户
- Teams 聊天和通道消息
- Microsoft Cloud App Security
- Windows 10 设备
- 本地存储库

每个先决条件各不相同。 某些位置（如 Exchange）中的敏感项目只需配置适用于它们的策略，就可以将其放在 DLP 保护之下。 其他项目（如本地文件库）需要部署 Azure 信息保护 (AIP) 扫描程序。 在激活任何阻止操作之前，你需要准备环境、代码草稿策略并全面测试它们。

### <a name="deploy-your-policies-in-production"></a>在生产中部署策略

#### <a name="design-your-policies"></a>设计策略

首先定义你的控制目标，以及如何在各自的工作负载中应用这些目标。 制定实现目标的策略。 可随意从一次一个工作负荷开始，也可以跨所有工作负载开始 ，这还没有任何影响。

#### <a name="implement-policy-in-test-mode"></a>在测试模式下实现策略

在测试模式下使用 DLP 策略实现控件，评估这些控件的影响。 可以在测试模式下将策略应用于所有工作负荷，以便你可以获得完整的结果，但如果需要，你可以从一个工作负荷开始。

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a>监视结果并微调策略

在测试模式下，监视策略结果并微调策略，以便它满足控制目标，同时确保不会对有效的用户工作流和工作效率造成负面影响或无意影响。 下面是要微调的一些内容示例：

- 调整范围内或超出范围的位置和人员/位置
- 调整用于确定项目及其所执行操作是否与策略匹配的条件和例外
- 敏感信息定义
- 操作
- 限制级别
- 添加新控件
- 添加新人员
- 添加新的受限应用
- 添加新的受限网站

#### <a name="enable-the-control-and-tune-your-policies"></a>启用控制并调整策略

策略满足所有目标后，将其打开。 继续监视策略应用程序的结果并根据需要进行调整。 

> [!NOTE]
> 一般情况下，策略在打开后大约一小时生效。

<!--See, LINK TO topic for SLAs for location specific  details-->

## <a name="dlp-policy-configuration-overview"></a>DLP 策略配置概述

您可以灵活地创建和配置 DLP 策略。 你可以从预定义模板开始，只需单击几下即可创建策略，也可以从头开始设计自己的策略。 无论你选择哪一个，所有 DLP 策略都需要您提供相同的信息。

1. **选择要监视的内容**- Microsoft 365许多预定义的策略模板，可帮助你入门或创建自定义策略。
    - 预定义的策略模板：财务数据、医疗健康数据、隐私数据，所有国家和地区的隐私数据。
    - 使用可用敏感信息类型、保留标签和敏感度标签的自定义策略。
2. **Choose where you want to monitor** - You pick one or more locations that you want DLP to monitor for sensitive information. 你可以监视：

位置 | 包含/排除方式|
|---------|---------|
|Exchange 电子邮件| 通讯组|
|SharePoint 网站 |网站 |
|OneDrive 账户 |帐户或通讯组 |
|Teams 聊天和通道消息 |账户 |
|Windows 10 设备 |用户或组 |
|Microsoft Cloud App Security |实例 |
|本地存储库| 存储库文件路径|

3. **选择要应用于项目** 的策略必须匹配的条件 - 可以接受预配置的条件或定义自定义条件。 示例如下：

- 项包含特定上下文中使用的指定类型的敏感信息。 例如，向组织外部的收件人发送电子邮件的 95 个社会保险号码。
- 项具有指定的敏感度标签
- 包含敏感信息的项目在内部或外部共享

4. **选择在满足策略** 条件时要采取的操作 - 操作取决于活动发生的位置。  示例如下：

- SharePoint/Exchange/OneDrive：阻止组织外部人员表单访问内容。 向用户显示提示，并发送电子邮件通知，告知他们正在采取 DLP 策略禁止的操作。
- Teams聊天和频道：阻止在聊天或频道中共享敏感信息
- Windows 10设备：审核或限制将敏感项复制到可删除的 USB 设备
- Office应用：显示一个弹出窗口，通知用户他们正在从事有风险的行为并阻止或阻止但允许替代。
- 本地文件共享：将文件从存储位置移动到隔离文件夹

> [!NOTE]
> 条件和要采取的操作在名为 Rule 的对象中定义。

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

在合规性中心创建 DLP 策略后，该策略将存储在中央策略存储中，然后同步到各种内容源，包括：

- Exchange Online，并从它同步到 Outlook 网页版和 Outlook。
- OneDrive for Business 网站。
- SharePoint Online 网站。
- Office 桌面程序（Excel、PowerPoint 和 Word）。
- Microsoft Teams 频道和聊天消息。

该策略同步到正确的位置后，它将开始评估内容并强制执行操作。

## <a name="viewing-policy-application-results"></a>查看策略应用程序结果

DLP 将大量信息报告Microsoft 365监视、策略匹配和操作以及用户活动。 你将需要使用和操作该信息，以调整策略和对敏感项目采取的会审操作。 遥测首先会进入Microsoft 365中心[](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center)审核日志，然后进行处理，然后转到不同的报告工具。 每个报告工具都有不同的用途。

### <a name="dlp-alerts-dashboard"></a>DLP 警报仪表板

当 DLP 对敏感项目采取操作时，可以通过可配置的警报通知您该操作。 合规性中心在 DLP 警报管理仪表板 中提供它们，而不是让这些警报在邮箱中可供你 [浏览](dlp-configure-view-alerts-policies.md)。 使用 DLP 警报仪表板配置警报、查看警报、对警报分类并跟踪 DLP 警报的解析。 下面是策略匹配和来自设备的活动生成的警报Windows 10示例。

> [!div class="mx-imgBorder"]
> ![警报信息](../media/Alert-info-1.png)。

你还可以在同一仪表板中查看关联事件的详细信息以及丰富元数据

> [!div class="mx-imgBorder"]
> ![事件信息](../media/Event-info-1.png)。

### <a name="reports"></a>报告

[DLP 报告](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention)显示了一段时间的广泛趋势，并提供了以下具体见解：

- **DLP 策略随着时间的推移匹配** ，并按日期范围、位置、策略或操作进行筛选
- **DLP 事件匹配** 还会显示一段时间的匹配项，但会透视项目而不是策略规则。
- **DLP 误报和重写** 显示误报计数，如果配置，则显示用户替代以及用户理由。

### <a name="dlp-activity-explorer"></a>DLP 活动资源管理器

DLP 页面上的活动资源管理器选项卡将 *活动筛选器预设* 为 *DLPRuleMatch*。 使用此工具查看与包含敏感信息或应用了标签的内容相关的活动，例如更改了哪些标签、修改了哪些文件以及匹配了规则。

![DLPRuleMatch 范围活动资源管理器的屏幕截图。](../media/dlp-activity-explorer.png)

有关详细信息，请参阅活动 [资源管理器入门](data-classification-activity-explorer.md)

若要了解有关 DLP Microsoft 365，请参阅：

- [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md)
- [了解 Microsoft Teams（预览版）中的默认数据丢失防护策略](dlp-teams-default-policy.md)
- [了解 Microsoft 365 本地扫描仪数据丢失防护（预览）](dlp-on-premises-scanner-learn.md)
- [了解 Microsoft 合规性扩展（预览版）](dlp-chrome-learn-about.md)
- [了解数据丢失防护警报仪表板](dlp-alerts-dashboard-learn.md)

若要了解如何使用数据丢失防护来遵守数据隐私法规，请参阅使用 Microsoft 365 (aka.ms/m365dataprivacy) 部署数据隐私[法规](../solutions/information-protection-deploy.md)的信息保护。

## <a name="licensing-and-subscriptions"></a>许可和订阅

有关支持 DLP [的订阅的详细信息，](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) 请参阅信息保护的许可要求。