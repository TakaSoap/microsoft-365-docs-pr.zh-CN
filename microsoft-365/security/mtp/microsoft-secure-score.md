---
title: Microsoft 安全功能分数
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何提高安全状态以及安全管理员可预期的功能。
keywords: microsoft 安全分数，安全分数，office 365 安全分数，microsoft 安全分数，microsoft 365 安全中心，改进操作
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a41e05f54a8ba94752c6df91628a2200367ac0f3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843836"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全功能分数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。 可在 https://security.microsoft.com/securescore [Microsoft 365 安全中心](overview-security-center.md)中找到。

遵循安全得分建议可保护您的组织免受威胁。 从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。

安全分数可帮助组织：  

* 报告组织安全状况的当前状态。
* 通过提供可发现性、可见性、指导和控制改进其安全状况。  
* 与基准测试进行比较，并建立 (Kpi) 的关键绩效指标。

组织可以获得对指标和趋势的可靠可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较以及其他更多。 分数还可以反映第三方解决方案解决建议操作的时间。

![安全得分主页](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>运作方式

为您提供了以下操作的要点：

- 配置建议的安全功能
- 执行与安全相关的任务
- 使用第三方应用程序或软件或其他缓解措施解决改进操作

某些改进操作仅在完全完成时提供积分。 某些设备或用户的已完成部分会提供一些要点。 如果您无法或不希望执行其中一个改进操作，则可以选择接受风险或剩余风险。

如果你拥有某个受支持的 Microsoft 产品的许可证，你将看到这些产品的建议。 我们将向您展示产品的全部可能改进，而不考虑许可证版本、订阅或计划。 通过这种方式，您可以了解安全最佳实践并提高成绩。 无论您的组织对特定产品拥有哪些许可证，绝对安全状态（按安全分数表示）保持不变。 请记住，安全应平衡可用性，而不是每个建议都适用于您的环境。

你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。 安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。

### <a name="key-scenarios"></a>关键方案

- [检查当前分数](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [比较你的成绩与你的组织（如你的组织）](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [查看改进操作并决定行动计划](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [启动工作流以进行调查或实施](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 安全中心和 ServiceNow 集成](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>如何对改进行动进行评分

每个改进操作10磅或更少，并且都是以二进制方式进行评分。 如果实施改进操作（如创建新策略或打开特定设置），则将获得100% 的点数。 对于其他改进操作，点作为总配置的百分比提供。

例如，改进操作表明您通过使用多重身份验证来保护您的所有用户，从而获得10分。 您只有50的100个用户受保护，因此，您可以得到5分的部分分数 (50 受保护/100 总计 * 10 max 磅 = 5 磅) 。

### <a name="products-included-in-secure-score"></a>安全分数中包括的产品

目前有关于 Microsoft 365 (的建议，其中包括 Exchange Online) 、Azure Active Directory、Microsoft Defender for Endpoint、Microsoft Defender for Identity 和云应用安全性。 即将推出针对其他安全产品的建议。 这些建议不包含与每个产品相关联的所有攻击面，但它们是一个很棒的基准。 您还可以将改进操作标记为由第三方或备用缓解措施覆盖。

### <a name="security-defaults"></a>安全性默认值

Microsoft 安全评分已更新了 [在 Azure Active Directory 中支持安全默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)的改进操作，这使组织能够更轻松地使用预配置的安全设置进行常见攻击，从而帮助保护组织。

如果启用安全默认设置，你将获得以下改进操作的完整积分：

- 确保所有用户都可以完成多重身份验证以实现 (9 点的安全访问) 
- 要求对管理角色进行 MFA (10 磅) 
- 启用策略以阻止旧版身份验证 (7 点) 

>[!IMPORTANT]
>安全性默认值包括为 "登录风险策略" 和 "用户风险策略" 改进操作提供类似安全性的安全功能。 建议将这些策略的安全默认值更新为 "通过其他缓解措施进行解决"，而不是将这些策略设置为 "通过其他缓解措施"。

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

如果具有只读访问权限，则无法编辑改进操作的状态或注释、编辑分数区域或编辑自定义比较。

* 支持人员管理员
* 用户管理员
* 服务管理员
* 安全读者
* 安全操作员
* 全局读取者

## <a name="risk-awareness"></a>风险感知

Microsoft 安全分数是基于系统配置、用户行为和其他与安全相关的度量的安全状态的数字摘要。 它并不是对系统或数据受到破坏的可能性的绝对度量。 相反，它表示您在 Microsoft 环境中已采用安全控制的程度，可帮助弥补受到破坏的风险。 无在线服务完全不受安全破坏，安全分数不应以任何方式解释为保证安全违规。

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的来信

如果你有任何问题，请通过在 [安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社区中发布来告知我们。 我们正在监视社区，并将提供帮助。

## <a name="related-resources"></a>相关资源

- [评估你的安全状况](microsoft-secure-score-improvement-actions.md)
- [跟踪你的 Microsoft 安全分数历史记录并实现目标](microsoft-secure-score-history-metrics-trends.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
- [新增功能](microsoft-secure-score-whats-new.md)
