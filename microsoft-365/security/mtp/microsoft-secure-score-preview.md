---
title: Microsoft 安全评分（预览）
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员使用它的方式。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: w10
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
ms.openlocfilehash: 8767174fa17aceab7d83adb96f938efad5074356
ms.sourcegitcommit: 1e9ce51efa583c33625299d17e37f58048a4169c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2020
ms.locfileid: "43804773"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft 安全评分（预览）

>[!IMPORTANT]
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。 可在 Microsoft 365 安全https://security.microsoft.com/securescore中心中找到。

按照安全得分建议，可以保护您的组织免受威胁。 从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。

安全分数可帮助组织：  

* 报告组织安全状况的当前状态。
* 通过提供可发现性、可见性、指导和控制改进其安全状况。  
* 与基准进行比较并建立关键绩效指标（Kpi）。

组织可以获得对指标和趋势的可靠可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较以及其他更多。 分数还可以反映第三方解决方案解决建议操作的时间。

此外，你还可以通过[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)访问你的建议和评分。 了解[安全分数资源类型](https://go.microsoft.com/fwlink/?linkid=2092996)。

## <a name="how-it-works"></a>运作方式

为您提供配置推荐安全功能、执行与安全相关的任务或使用第三方应用程序或软件解决改进操作的相关积分。 某些改进操作仅在完全完成时给出点，而有些改进操作在为某些设备或用户完成一些点时提供部分点。 如果不能或不希望执行其中一个改进操作，则可以选择接受风险或剩余风险。

我们为你展示了完整的一组可能的改进，而不考虑许可证，因此你可以了解安全最佳做法并提高你的成绩。 绝对安全状态由安全分数表示，无论贵组织拥有哪些产品许可证，这都保持不变。 请记住，安全应平衡可用性，而不是每个建议都适用于您的环境。

你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。 安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。

### <a name="how-improvement-actions-are-scored"></a>如何对改进行动进行评分

每个改进操作10磅或更少。 大多数都是以二进制方式进行评分—如果实现改进操作（如创建新策略或打开特定设置），则将获得100% 的点数。 对于其他改进操作，点作为总配置的百分比提供。 例如，如果使用多重身份验证保护您的所有用户，并且您仅有5% 以上100的用户受到保护，则 "改进" 操作将获得约30个点（共有2个分数，即5个 "受保护/100 总计 * 30 个最大值 = 2 pt 部分分数"）。

### <a name="products-included-in-secure-score"></a>安全分数中包括的产品

目前，我们提供了 Microsoft 365 的一些建议（包括 SharePoint Online、Exchange Online、OneDrive for Business、Microsoft 信息保护等）、Azure AD、Microsoft Defender ATP 和云应用安全性。 即将推出针对其他安全产品的建议。 这些建议不包含与每个产品相关联的所有攻击面，但都是一个很棒的基准。 您还可以将改进操作标记为第三方覆盖。

## <a name="required-permissions"></a>所需权限

若要拥有访问 Microsoft 安全分数的权限，您必须在 Azure Active Directory 中为以下角色分配一个角色。

### <a name="read-and-write-roles"></a>读取和写入角色

通过读取和写入访问权限，您可以进行更改，并直接与安全分数进行交互。 您还可以将只读访问权限分配给其他用户。

* 全局管理员
* 安全管理员
* Exchange 管理员
* SharePoint 管理员
* 帐户管理员

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

* Identity （Azure AD 帐户 & 角色）
* 数据（Microsoft 信息保护）
* 设备（现在无改进操作）
* 应用（电子邮件和云应用，包括 Office 365 和 Microsoft 云应用安全性）
* 基础结构（暂时不提供改进操作）

在 "Microsoft 安全分数概述" 页中，您可以看到在这些组之间如何拆分点以及哪些点可用。 [！注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置，以及可采取的优先改进措施以提高成绩。

![安全积分主页](../../media/secure-score/secure-score-homepage.png)
*图1： Microsoft 安全分数概述页面*

## <a name="take-action-to-improve-your-score"></a>采取行动以提高成绩

"改进操作" 选项卡列出了解决可能的攻击面的安全建议，以及它们的状态（已完成、已计划、风险已接受、第三方和 to address）。 您可以搜索、筛选和分组所有改进操作。  

### <a name="ranking"></a>排名

排名基于要达到的剩余点数、实现难度、用户影响和复杂性。 最高排名改进操作的剩余分数与较低的难度、用户影响和复杂性相同。

### <a name="actions"></a>操作

选择特定的 "改进" 操作时，将显示完整的 "页面" 飞出控件。  

![改进操作浮出](../../media/secure-score/secure-score-improvement-action.png)
控件示例*图2：改进操作浮出控件示例*

若要完成此操作，您有几个选项：

* 选择 "**管理**" 以转到配置屏幕并进行更改。 然后，您将获得该操作所需要的要点，在飞出中可见。点通常需要大约24小时才能更新。

* 选择 "**共享**" 将直接链接复制到 "改进" 操作，或选择用于共享链接（如电子邮件、microsoft 团队、microsoft Planner 或 ServiceNow）的平台。 选择 ServiceNow 将允许你创建将在 ServiceNow 和 Microsoft 365 安全中心主页中可见的更改票证。 若要了解详细信息，请参阅[Microsoft 365 安全中心和 ServiceNow 集成](tickets.md)。

* 选择 "**编辑状态和注释**" 可编辑特定于 "改进" 操作的任何手动状态或记录笔记。 您可以按 "改进操作" 选项卡中的状态进行筛选或分组。您可以选择的 statues 如下

    * **若要解决**此需要，您可以认识到改进操作是必需的，并计划在将来某一时间解决此操作。 此状态也适用于检测为部分但未完全完成的操作。
    * **规划**—完成改进操作有一些具体的规划。
    * **接受风险**—安全性应始终与可用性平衡，而不是每个建议对您的环境都适用。 在这种情况下，您可以选择接受风险或剩余风险，而不是执行改进操作。 不会向你提供任何点，但操作将不再显示在改进操作列表中。 您可以在历史记录中查看此操作，也可以随时撤消。
    * **通过第三方解决**—改进操作已由第三方应用程序或软件解决。 你将获得该操作所需要的要点，因此你的得分更好地反映了你的总体安全状况。 如果第三方不再涵盖该控件，您可以选择另一个状态。 请记住，如果将改进操作标记为通过第三方解决，Microsoft 将无法深入了解实施的完整性

### <a name="prerequisites"></a>先决条件

"实施" 部分中的先决条件将列出任何需要获取的许可证或在解决改进操作之前需要完成的操作。 请确保你的许可证中有足够的座位来完成改进操作，并且这些许可证适用于所需的用户。  

## <a name="track-your-score-history-and-meet-goals"></a>跟踪分数历史记录并实现目标

您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。在图下方是在所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。 您可以自定义日期范围并按类别进行筛选。

在 "**指标 & 趋势**" 选项卡中，有几个图表和图表可让您更好地了解趋势和设置目标。 您可以为整个可视化页设置日期范围。 可视化效果包括：

* **安全分数区域**—根据组织的目标和 "好"、"好" 和 "差" 得分范围的定义自定义。
* **回归趋势**-由于配置、用户或设备更改而 regressed 的点的时间线。  
* **比较趋势**—组织的安全分数与其他人的对比情况。 此视图可包含表示具有类似座位计数的组织的平均分数和可设置的自定义比较视图的行。
* **风险接受趋势**-标记为 "风险已接受" 的 "改进" 操作的时间线。
* **得分变化**—在指定的日期范围内，所实现的点数、点 regressed 或添加的新操作以及后续得分的变化。

## <a name="risk-awareness"></a>风险感知

Microsoft 安全分数是基于系统配置、用户行为和其他安全相关度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。 相反，它表示您在 Microsoft 环境中已采用安全控制的程度，这有助于抵消受到破坏的风险。 无在线服务完全不受安全破坏，并且安全分数不应以任何方式解释为保证安全。

## <a name="whats-new"></a>有哪些新增功能？ 

若要使 Microsoft 安全得分更好地代表安全状态，我们做了一些更改。 若要了解计划的更改，请参阅[Microsoft Secure 评分中的内容？](microsoft-secure-score-whats-coming.md)。

### <a name="april-21st-2020"></a>2020年4月21日

#### <a name="added-azure-active-directory-improvement-action"></a>添加了 Azure Active Directory 提高操作

- 不允许用户向非托管应用程序授予许可（当前在已发布版本中可用）

#### <a name="added-azure-advanced-threat-protection-improvement-actions"></a>添加了 Azure 高级威胁防护改进操作

- 在域控制器上禁用打印后台处理程序服务
- 修改不安全的 Kerberos 委派以阻止模拟
- 使用 Microsoft LAPS 保护和管理本地管理员密码
- 降低横向移动路径对敏感实体的风险
- 删除敏感组中的非活动帐户
- 从实体中删除不安全的 SID 历史记录属性
- 解决不安全帐户属性
- 停止明文凭据公开
- 停止旧协议通信
- 停止弱密码使用

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>对 Microsoft Defender ATP 威胁的支持 & 漏洞管理（TVM）安全建议

现已提供 TVM 提供的所有已发布的安全建议。

### <a name="january---march-2020"></a>1月-2020 年3月

#### <a name="updated-interface-and-functionality"></a>更新的界面和功能

* CISO 和潜在客户级别讨论的所有新指标和趋势视图
* 跟踪和基准成绩的新方法
* 更好地跟踪和理解分数回归
* 筛选、标记、搜索和分组您的改进操作
* 使用分数预测和计划操作来管理未来目标
* 更多！

#### <a name="removed-not-scored-and-review-improvement-actions"></a>删除 "未评分" 和 "审阅" 改进操作

安全得分的原则之一是，分数应标准化且易于关联。 具有不可衡量或可操作的改进操作已导致混淆。 仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。 不计分的提高操作不可度量，并且与其他改进操作相比，不会将 "改进" 操作评估为与相同标准。

出于这些原因，所有未评分或要求的改进操作都暂时删除了审阅节奏。 您的部件不需要执行任何操作。

#### <a name="simplification-of-the-point-system"></a>简化了点系统

若要在多个体验中标准化点，每个安全分数改进操作点总数已更新为10磅或更少。 在我们目前所拥有的安全控制的广泛 breather 和将来将添加的安全控制中，必须更加一致。 虽然这是一项重大更改，并且你将在点汇总中看到一个拖放，但你的安全状态不会有任何变化。

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的来信

如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。 我们正在监视社区，并将提供帮助。
