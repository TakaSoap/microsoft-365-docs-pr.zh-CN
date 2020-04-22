---
title: 步骤7：配置特权访问管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 了解并配置特权访问管理。
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636984"
---
# <a name="step-7-configure-privileged-access-management"></a>步骤7：配置特权访问管理

*此步骤是可选的，仅适用于 Microsoft 365 企业版的 E5 版和高级合规版*

![第 6 阶段：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

通过配置在租户中为基于任务的活动指定实时访问的策略，启用了特权访问管理。 它可以帮助保护您的组织免受可能使用具有敏感数据访问权限的现有特权管理员帐户的危害，或访问关键配置设置。 例如，您可以配置需要明确批准访问和更改租户中的组织邮箱设置的特权访问管理策略。

在此步骤中，您将在租户中启用特权访问管理，并配置可为组织的数据和配置设置提供额外安全性的特权访问策略。 有三个基本步骤可开始使用组织中的特权访问：
- 创建审批者的组
- 启用特权访问
- 创建审批策略

配置完成后，特权访问管理可帮助组织实现零长期特权并针对这类长期管理访问权限造成的漏洞提供一个防御层。特权访问要求必须经过审批才能执行定义了相关审批策略的任务。用户如果需要执行某个审批策略中包含的任务，则必须提出请求并成功通过访问权限审批，以便获得执行该策略中定义的任务所需的权限。

若要启用特权访问管理，请参阅[配置特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题。

有关详细信息，请参阅[特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)主题。


|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  若要在测试实验室环境中练习此配置，请参阅[特权访问管理测试实验室指南](privileged-access-microsoft-365-enterprise-dev-test-environment.md)。 |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step7)。

## <a name="next-step"></a>后续步骤

[信息保护基础结构退出条件](infoprotect-exit-criteria.md)
