---
title: Microsoft 安全功能分数
description: 介绍 Microsoft 安全分数Microsoft 365 Defender门户、如何改善安全状态以及安全管理员期望的内容。
keywords: microsoft 安全分数， 安全分数， office 365 安全分数， microsoft 安全分数， Microsoft 365 Defender门户， 改进操作
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- Adm_TOC
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 3bce20b1b86ea569014313f345bcf7e4f6dd2cc0
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724316"
---
# <a name="microsoft-secure-score"></a>Microsoft 安全功能分数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 安全功能分数是衡量组织安全状况的指标，数字越高表示采取的改进措施越多。 可以在网站门户 的 Microsoft 365 Defender https://security.microsoft.com/securescore [找到它](microsoft-365-defender.md#the-microsoft-365-defender-portal)。

执行安全功能分数建议可保护组织免遭威胁。 从企业门户中的Microsoft 365 Defender仪表板，组织可以监视并处理其Microsoft 365、应用和设备的安全性。

安全功能分数可帮助组织：  

* 报告组织安全状况的当前状态。
* 通过提供可发现性、可见性、指导和控制来提升安全性。  
* 与基准进行比较，并建立关键绩效指标 (KPI)。

组织可以访问指标和趋势的稳固可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较等。 该分数还可以反映第三方解决方案何时解决了建议的操作。

![安全分数主页。](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a>运作方式

你获得以下操作点数：

- 配置建议的安全功能
- 执行与安全相关的任务
- 使用第三方应用程序或软件或备用缓解解决改进操作

有些改进操作仅在完全完成时提供分数。 如果为某些设备或用户完成了这些操作，一些会提供部分分数。 如果无法或不希望评估其中一项改进操作，可以选择接受风险或剩余风险。

如果你有受支持的 Microsoft 产品之一的许可证，你将看到这些产品的建议。 我们将向您展示产品的完整可能改进集，无论许可证版本、订阅或计划如何。 这样，你可以了解安全性最佳实践并提升分数。 无论组织拥有特定产品的许可证是什么，你的绝对安全状态（以安全分数表示）都保持不变。 请记住，安全性应该与可用性相平衡，同时请注意不是每个建议都适合您的环境。

你的分数会实时更新，以反映可视化和改进操作页面中显示的信息。 安全分数还会每天同步一次，以接收有关每个操作所得分的系统数据。

### <a name="key-scenarios"></a>关键方案

- [检查当前分数](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [将分数与组织（如组织）进行比较](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [查看改进操作并决定行动计划](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [启动要调查或实施的工作流](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>如何对改进操作进行评分

每个改进操作都值 10 分或更少，大多数改进操作都以二进制方式进行评分。 如果实施改进操作（如创建新策略或启用特定设置），则获得 100% 的分数。 对于其他改进操作，分数以总配置百分比表示。

例如，改进操作通过多重身份验证保护所有用户而获得 10 分。 你只有 50 个保护的总数为 100 个用户，因此你获得的部分分数为 5 分 (50 分/共 100 分 * 10 最大 pts = 5 pts) 。

### <a name="products-included-in-secure-score"></a>安全分数中包含的产品

目前，有针对以下产品的建议：

- Microsoft 365 (包括Exchange Online) 
- Azure Active Directory
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- 云应用安全
- Microsoft Teams

推荐即将推出其他安全产品。 建议不会涵盖与每个产品关联的所有攻击面，但它们是一个很好的基线。 还可以将改进操作标记为第三方或备用缓解涵盖。

### <a name="security-defaults"></a>安全性默认值

Microsoft 安全分数已更新了改进操作，以支持[Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)中的安全默认值，从而可以更轻松地使用针对常见攻击的预配置安全设置来帮助保护组织。

如果启用安全默认值，将被授予以下改进操作的完整分数：

- 确保所有用户都可以完成多重身份验证， (9 个点) 
- 管理角色需要 MFA (10) 
- 启用策略以阻止 7 (旧身份验证) 

>[!IMPORTANT]
>安全默认值包括提供与"登录风险策略"和"用户风险策略"改进操作类似的安全性的安全功能。 建议不要根据安全默认值设置这些策略，而应更新其状态为"通过替代缓解解决"。

## <a name="required-permissions"></a>所需权限

若要有权访问 Microsoft 安全分数，必须在 Microsoft 安全分数中分配以下角色之Azure Active Directory。

### <a name="read-and-write-roles"></a>读取和写入角色

通过读取和写入访问权限，你可以进行更改并直接与安全分数进行交互。 您还可以向其他用户分配只读访问权限。

* 全局管理员
* 安全管理员
* Exchange 管理员
* SharePoint 管理员

### <a name="read-only-roles"></a>只读角色

使用只读访问权限，你无法编辑改进操作的状态或备注、编辑分数区域或编辑自定义比较。

* 支持人员管理员
* 用户管理员
* 服务支持管理员
* 安全读者
* 安全操作员
* 全局读取者

## <a name="risk-awareness"></a>风险感知

Microsoft 安全分数是安全状态的数字摘要，基于系统配置、用户行为和其他与安全相关的度量。 它不是系统或数据泄露的可能性的绝对度量。 而是表示在 Microsoft 环境中采用安全控件的程度，可帮助消除泄露风险。 任何联机服务都不应受到安全漏洞的影响，安全分数不应被解释为防止任何形式的安全漏洞的保证。

## <a name="we-want-to-hear-from-you"></a>欢迎提出宝贵意见

如果有任何问题，请通过发布到安全、隐私和合规性社区 [&告知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 我们。 We're monitoring the community and will provide help.

## <a name="related-resources"></a>相关资源

- [评估安全状况](microsoft-secure-score-improvement-actions.md)
- [跟踪 Microsoft 安全分数历史记录并实现目标](microsoft-secure-score-history-metrics-trends.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
- [新增功能](microsoft-secure-score-whats-new.md)
