---
title: 第 4 步：配置 Office 365 的特权访问管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 了解并配置 Office 365 的特权访问管理。
ms.openlocfilehash: 297d8e042c2a22c93b4ea566081d258e7ca0a5ab
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286945"
---
# <a name="step-4-configure-privileged-access-management-for-office-365"></a>第 4 步：配置 Office 365 的特权访问管理

*此步骤是可选的，仅适用于 Microsoft 365 企业版的 E5 版和高级合规版*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Office 365 租户中的特权访问管理可通过配置相应策略来实现，这些策略会为基于任务的活动指定实时访问权限。这种管理可为组织提供保护，防止他人使用具有长期敏感数据访问权限或关键配置设置访问权限的现有特权访问帐户。例如，你可以配置一个特权访问管理策略，要求必须经过显示审批才能访问和更改 Office 365 租户中的组织邮箱设置。

在此步骤中，你将在 Office 365 租户中启用特权访问管理并配置特权访问策略，这些策略可为基于任务对组织的 Office 365 数据和配置设置进行的访问提供额外的安全性。若要开始在 Office 365 组织中使用特权访问，需要执行三个基本步骤：
- 创建审批者的组
- 启用特权访问
- 创建审批策略

配置完成后，特权访问管理可帮助组织实现零长期特权并针对这类长期管理访问权限造成的漏洞提供一个防御层。特权访问要求必须经过审批才能执行定义了相关审批策略的任务。用户如果需要执行某个审批策略中包含的任务，则必须提出请求并成功通过访问权限审批，以便获得执行该策略中定义的任务所需的权限。

若要启用 Office 365 特权访问管理，请参阅[配置 Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题。

有关详细信息，请参阅 [Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)主题。

## <a name="results"></a>结果

此步骤的结果是，你通过启用对组织关键数据和配置设置的实时访问控制提高了 Office 365 的安全性。

作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step5)。

## <a name="next-step"></a>后续步骤

[信息保护基础结构退出条件](infoprotect-exit-criteria.md)