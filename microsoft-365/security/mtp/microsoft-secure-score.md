---
title: Microsoft 安全功能分数
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b19c48161d5d0f43c2beb207dd0ee2db8bfb1470
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372020"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全功能分数

Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。 按照安全得分建议，可以保护您的组织免受威胁。 从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。

安全分数可帮助组织：

* 报告组织安全状况的当前状态。
* 通过提供可发现性、可见性、指导和控制改进其安全状况。  
* 与基准进行比较并建立关键绩效指标（Kpi）。

组织可以获得对指标和趋势的可靠可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较以及其他更多。 分数还可以反映第三方解决方案解决建议操作的时间。

此外，你还可以通过[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)访问你的建议和评分。 了解[安全分数资源类型](https://go.microsoft.com/fwlink/?linkid=2092996)。

## <a name="how-it-works"></a>工作原理

为您提供配置推荐安全功能、执行与安全相关的任务（如查看报告）或使用第三方应用程序或软件解决改进操作的相关积分。 某些改进操作仅在完全完成时给出点，而有些改进操作在为某些设备或用户完成一些点时提供部分点。

我们为你展示了完整的一组可能的改进，而不考虑许可证，因此你可以了解安全最佳做法并提高你的成绩。 绝对安全状态由安全分数表示，无论贵组织拥有哪些产品许可证，这都保持不变。 请记住，安全应平衡可用性，而不是每个建议都适用于您的环境。

你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。 安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。

### <a name="how-improvement-actions-are-scored"></a>如何对改进行动进行评分

大多数都是以二进制方式进行评分—如果实现改进操作（如创建新策略或打开特定设置），则将获得100% 的点数。 对于其他改进操作，点作为总配置的百分比提供。 例如，如果使用多重身份验证保护您的所有用户，并且您仅有5% 以上100的用户受到保护，则 "改进" 操作将获得约30个点（共有2个分数，即5个 "受保护/100 总计 * 30 个最大值 = 2 pt 部分分数"）。

### <a name="products-included-in-secure-score"></a>安全分数中包括的产品

目前，我们提供了 Office 365 的一些建议（包括 SharePoint Online、Exchange Online、OneDrive for Business、Microsoft 信息保护等）、Azure AD 和云应用安全性。 对其他安全产品（如 Azure ATP 和 Microsoft Defender ATP）的建议即将推出。 这些建议不包含与每个产品相关联的所有攻击面，但都是一个很棒的基准。 您还可以将改进操作标记为第三方覆盖。

## <a name="required-permissions"></a>所需权限

若要拥有访问 Microsoft 安全分数的权限，您必须在 Azure Active Directory 中为以下角色分配一个角色。

### <a name="read-and-write-roles"></a>读取和写入角色

通过读取和写入访问权限，您可以进行更改，并直接与安全分数进行交互。 您还可以将只读访问权限分配给其他用户。

* 全局管理员
* 安全管理员
* Exchange 管理员
* SharePoint 管理员

### <a name="read-only-roles"></a>只读角色

如果具有只读访问权限，您将无法编辑 "改进" 操作的状态或注释、编辑分数区域或编辑自定义比较。

* 帮助台管理员
* 用户管理员
* 服务管理员
* 安全读取者
* 安全操作员
* 全局读取者

### <a name="graph-api"></a>Graph API

若要访问 Graph API，除了角色之外，还需要具有以下作用域之一：

* Securityevents.readwrite.all （适用于只读角色）
* Securityevents.readwrite.all （用于读取和写入角色）

## <a name="gain-visibility-into-your-security-posture"></a>深入了解你的安全状况

为了帮助您更快地了解所需的信息，Microsoft 改善操作将组织成组：

* Identity （Azure AD 帐户 & 角色，即将推出 Azure ATP）
* 数据（Microsoft 信息保护）
* 设备（Microsoft Defender ATP 设备，即将推出）
* 应用（电子邮件和云应用，包括 Office 365 和 Microsoft 云应用安全性）
* 基础结构（Azure 资源）

在 "Microsoft 安全分数概述" 页中，您可以看到在这些组之间如何拆分点以及哪些点可用。 [！注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置，以及可采取的优先改进措施以提高成绩。

![安全积分主页](../../media/secure-score/homepage-original.png)
*图1： Microsoft 安全分数概述页面*

## <a name="take-action-to-improve-your-score"></a>采取行动以提高成绩

"改进操作" 选项卡列出了解决可能的攻击面的安全建议，以及它们的状态（已完成、未完成、已通过第三方解决和忽略）。 您可以搜索、筛选和分组所有改进操作。

### <a name="ranking"></a>排名

排名基于要达到的剩余点数、实现难度、用户影响和复杂性。 最高排名改进操作的剩余分数与较低的难度、用户影响和复杂性相同。

### <a name="actions"></a>操作

Microsoft 安全分数不会跟踪标记为 [未评分] 的操作。 你仍可以采取措施，但完成这些操作不会影响你的分数。 如果某个操作在将来被 Microsoft 安全得分跟踪，并且您已完成该操作，则安全得分将自动反映所做的更改。

当您选择特定的 "改进" 操作时，将显示 "飞出"。 若要完成此操作，您有几个选项：

1. 选择 "**查看设置**" 以转到配置屏幕并进行更改。 然后，您可以在飞出的顶部看到该操作值得的要点。点可能需要长达24小时才能更新。

2. 选择 "**通过第三方解决**"，因为改进操作已由第三方应用程序或软件解决。 您可以获得该操作所需要的要点，这样您的安全分数就能更好地反映您的总体安全状况。 如果第三方不再涵盖该控件，则可以将 "改进" 操作标记为 "不完成"。 请注意，如果将改进操作标记为通过第三方解决，Microsoft 无法了解是否满足评分要求。

3. 选择 "**忽略**"，因为您已决定接受风险而不执行改进操作。 忽略 "改进" 操作后，您可以实现的安全分数点总数将减少。 您可以在历史记录中查看此操作，也可以随时撤消。

4. 选择 "**审阅**"，因为改进操作要求您定期查看环境的一部分以获取和保留点。 例如，应每周查看邮箱转发规则，以确保不会从您的网络中泄露数据。 您无需进行任何更改，但需要执行操作。 如果您定期查看规则，您将收到要点。 如果不是，则减少分数。

![安全分数提高操作示例](../../media/secure-score/secure-score1x450.png) ![安全分数评审改进操作示例](../../media/secure-score/secure-score2x450.png)

*图 2 & 3：改进操作 flyouts*

## <a name="monitor-improvements-over-time"></a>随着时间的推移监视改进

您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。在图下方是在所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。 您可以自定义日期范围并按类别进行筛选。

## <a name="risk-awareness"></a>风险感知

Microsoft 安全分数是基于系统配置、用户行为和其他与安全相关的度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。 相反，它表示您在 Microsoft 环境中已采用安全控制的程度，这有助于抵消受到破坏的风险。 无在线服务完全不受安全破坏，并且安全分数不应以任何方式解释为保证安全。

## <a name="whats-new"></a>新增功能

若要使 Microsoft 安全得分更好地代表安全状态，我们做出了一些更改。

若要了解计划的更改，请参阅[Microsoft 安全分数中的内容？](microsoft-secure-score-whats-coming.md)

### <a name="removed-not-scored-improvement-actions"></a>删除了 "未评分" 的改进操作

安全得分的原则之一是，分数应标准化且易于关联。 具有不可衡量或可操作的改进操作已导致混淆。 仅当每个建议可能对分数有明显影响时，Microsoft 安全分数才有意义。 不计分的提高操作不可度量。  

出于这些原因，未评分的所有改进操作均已删除。 您的部件不需要执行任何操作。

### <a name="removed-device-improvement-actions"></a>删除了设备改进操作

评估 Microsoft 安全得分设备类别的改进操作后，确定这些操作当前评估策略状态，而不是设备的配置状态。 由于配置直接与安全状态相关联，因此已确定现有的设备操作未完全代表组织的状况。  我们将删除设备类别中的当前操作，因为我们将提供一组直接使用诊断数据以更完整地表示设备安全状态的建议。

已删除以下改进操作：

- 启用 Microsoft Intune 移动设备管理
- 创建适用于 Android 的 Microsoft Intune 合规性策略
- 创建适用于 Android 的 Microsoft Intune 合规性策略
- 创建适用于 Android 的 Microsoft Intune 应用保护策略
- 创建适用于 iOS 的 Microsoft Intune 应用保护策略
- 标记不符合 Microsoft Intune 合规性策略的设备（未分配为不合规）
- 创建适用于 iOS 的 Microsoft Intune 合规性策略
- 为 macOS 创建 Microsoft Intune 合规性策略
- 创建适用于 Windows 的 Microsoft Intune 合规性策略
- 创建适用于 Android 的 Microsoft Intune 配置配置文件
- 为适用于 Android 的工作创建 Microsoft Intune 配置配置文件
- 为 macOS 创建 Microsoft Intune 配置文件
- 为 iOS 创建 Microsoft Intune 配置文件
- 为 Windows 创建 Microsoft Intune 配置文件
- 在 Microsoft Intune 中启用增强型 jailbreak 检测
- 要求对所有设备进行修补，并启用防病毒和防火墙
- 启用 Microsoft Intune 中的 Windows Defender ATP 集成
- 创建 Microsoft Intune Windows 信息保护策略
- 要求所有设备都具有高级安全配置
- 每周查看阻止的设备报告

### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>删除了不符合可靠测量预期的改进措施

为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们删除了以下改进操作：

- 启用审核数据记录
- 发现有风险和不兼容的卷影 IT 应用程序
- 查看权限 & 阻止连接到您的环境的有风险的 OAuth 应用程序
- 在 SharePoint online 文档库中设置版本控制

### <a name="mfa-improvement-action-updates"></a>MFA 改进操作更新

为了反映企业在应用使用其业务的策略时确保 upmost 安全性的需求，Microsoft 安全分数已删除了围绕多重身份验证的三个改进操作，并添加了两个操作。

删除了改进操作：

- 为多因素身份验证注册所有用户
- 要求对所有用户进行 MFA
- 需要对 Azure AD 特权角色进行 MFA

添加了改进操作：

- 确保所有用户都可以完成多重身份验证以实现安全访问
- 需要对管理角色进行 MFA

 这些新的改进操作需要为你的用户或管理员在你的目录中注册多重身份验证（MFA），并建立符合你的组织需求的一组适当的策略。 主要目标具有灵活性，同时确保所有用户和管理员都可以通过多个因素或基于风险的身份验证提示进行身份验证。 这可以采用具有多个策略的形式，这些策略将应用范围决定，或者设置安全默认值（即将3月16日），让 Microsoft 决定何时对用户进行 MFA 质询。

### <a name="removed-review-improvement-actions"></a>删除了 "审阅" 改进操作

安全得分的原则之一是，分数应标准化且易于关联。 具有不可衡量或可操作的改进操作已导致混淆。 仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。 与其他改进操作相比，评审改进操作的计算方式不是相同标准。  

出于这些原因，需要审阅节奏的所有改进操作都已暂时删除。 您的部件不需要执行任何操作。

### <a name="preview-features"></a>预览功能

[预览版本](microsoft-secure-score-preview.md)中将包含以下功能：

* CISO 和潜在客户级别讨论的所有新指标和趋势视图
* 跟踪和基准成绩的新方法
* 更好地跟踪和监控分数回归
* 筛选、标记、搜索和分组您的改进操作
* 使用分数预测和计划操作来管理未来目标
* 简化了要点系统
* 更多！

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的来信

如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。 我们正在监视社区，并将提供帮助。
