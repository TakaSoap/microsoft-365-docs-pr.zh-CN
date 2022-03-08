---
title: Microsoft 合规性管理器中的新增功能
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解合规性管理程序中的新增功能以及将提供哪些功能。 阅读更新后的评估、新的评估模板、新操作等。
ms.openlocfilehash: 48aed2e173231e3945bcdd3de73052de9f970a5b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317649"
---
# <a name="whats-new-in-microsoft-compliance-manager"></a>Microsoft 合规性管理器中的新增功能

**本文内容：** 了解合规性管理器中的最近更新。

## <a name="february-2022"></a>2022 年 2 月

### <a name="continuous-compliance-assessment-of-improvement-actions"></a>对改进操作的持续合规性评估

我们正在合规性管理器中添加针对超过 35 个改进操作（之前未在安全分数中涵盖）的自动化测试和证据生成。 通过持续合规性评估，如果这些改进操作与合规性评估相关且你已获得访问相关解决方案的许可，则你可以收到有关已完成的这些改进操作的更新。 持续合规性评估还让用户了解改进措施的评分逻辑，并提供有关为何获得特定分数的见解和证据。 此功能与安全分数Microsoft 365集成一起运行，并且之前配置的任何自动操作将继续正常工作。 详细了解自动 [测试设置](compliance-manager-setup.md#set-up-automated-testing)。
### <a name="alerts-and-alert-policies"></a>警报和警报策略

用户现在可以在合规性管理器中设置组织要跟踪的更改的警报。使用简单的设置向导，您可以构建警报策略，以在下列类型的事件发生时创建通知：改进操作分数更改、改进操作分配更改、改进操作中的测试或实现状态更改，以及改进操作的文档选项卡中的文件上载或删除。通过访问合规性 [管理器警报和警报策略了解更多信息](compliance-manager-alert-policies.md)。

### <a name="try-recommended-assessment-templates-for-your-organization"></a>尝试为组织推荐评估模板

贵组织现在可以从合规性管理器获取有关哪些评估可能最相关的建议，并快速设置流程以启动并运行。 若要详细了解建议以及如何在购买许可证之前试用高级评估模板，请参阅启动 [高级评估试用版](compliance-manager-setup.md#start-a-premium-assessments-trial)。

## <a name="november-2021"></a>2021 年 11 月

### <a name="zero-trust-integration-for-the-data-protection-baseline-template"></a>数据保护基线模板的零信任集成

零信任是跨数字资产所有层实现安全性的主动集成方法，可明确并持续验证每个事务，声明最小特权，并依赖于智能、高级检测和实时威胁响应。 合规性管理器的数据保护基线模板（包括所有用户）现在集成了 57 个新控件和 36 个针对零信任的新操作，这些新操作在下列控件系列中对齐：

- 零信任应用程序
- 零信任应用开发指南
- 零信任终结点
- 零信任数据
- 零信任标识
- 零信任基础结构
- 零信任网络
- 零信任可见性、自动化和业务流程

### <a name="new-preview-templates"></a>新的预览模板

现在预览版中提供了以下评估模板：

- 适用于 Azure (Preview 的 ISO 27001：2013) 
- 适用于 Dynamics 365 预览版 (ISO 27001：2013) 
- FedRAMP Moderate for Dynamics 365 (Preview) 
- FedRAMP Moderate for Azure (Preview) 
- FedRAMP High for Azure (Preview) 
- FedRAMP High for Dynamics 365 (Preview) 
- 适用于 Azure (Preview) 的 SOC 2
- Dynamics 365 预览版 (SOC 2) 
- 适用于 Azure (Preview 的 ISO 27018：2019) 
- 适用于 Dynamics 365 预览版 (ISO 27018：2019) 

## <a name="october-2021"></a>2021 年 10 月

### <a name="new-assessment-templates"></a>新的评估模板

我们发布了新的评估模板，包括：

- Colorado Privacy Act (CPA) 
- Cdn Consumer Data Privacy Act (CDPA) 
- 埃及 - 数据保护法
- 澳大利亚 - ASD Essential 8 Maturity Level 1
- 澳大利亚 - ASD Essential 8 Maturity Level 2
- 澳大利亚 - ASD Essential 8 Maturity Level 3

### <a name="integration-with-microsoft-priva"></a>与 Microsoft 一起集成

合规性管理器现在可以与 Microsoft 管理中心合作，这是一种可帮助您保护组织存储在 Microsoft 365 中的个人数据的解决方案。 用户提供了一些工具，可帮助你可视化和了解数据、实施策略来管理关键风险方案以及处理主体权限请求。 当你在管理区中执行保护你存储的个人数据的步骤时，这可以帮助你在合规性管理器中进行隐私评估，并且可以帮助你提高合规性分数。 若要了解一下一些功能和其他解决方案如何为分数做出贡献，并了解进一步改进的潜在机会，请参阅合规性管理器中的"解决方案"选项卡。 您还可以在了解 Microsoft 用户信息中查找有关一位用户 [的详细信息](/privacy/priva)。

## <a name="july-2021"></a>2021 年 7 月

我们添加了根据模板的新通用版本为除 Microsoft 365 产品创建评估的功能。 若要了解更多信息，请 [从使用评估模板开始](compliance-manager-templates.md)。

## <a name="may-2021"></a>2021 年 5 月

### <a name="new-assessment-templates"></a>新的评估模板

我们发布了 75 个新的评估模板，其中包括：
- 澳大利亚隐私法案
- CIS Microsoft 365 Foundation 级别 1 和 2
- 德国 - 针对金融机构 IT 部门 (或) 
- Sarbanes-Oxley法案
- 南非 - 促进信息访问法案

查看评估模板 [的完整列表](compliance-manager-templates-list.md)。

## <a name="april-2021"></a>2021 年 4 月

### <a name="support-for-us-government-dod-customers"></a>支持美国政府 DoD 客户

除了美国政府 DoD 客户之外，美国政府 DoD 客户现在Community (GCC) 中等和GCC合规性管理器。

## <a name="march-2021"></a>2021 年 3 月

### <a name="active-and-inactive-templates"></a>活动模板和无效模板

每个评估页面和评估模板页面都有一个激活的模板计数器。 此计数器显示根据许可协议使用多少个符合条件的模板。 查看 [模板可用性和许可](compliance-manager-templates.md#template-availability-and-licensing) 以了解更多信息。
