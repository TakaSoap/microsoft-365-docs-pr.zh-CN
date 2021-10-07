---
title: 了解特权访问管理
description: 本文概述了有关 Microsoft 365 中的特权访问管理，包括常见问题解答 (常见问题) 。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 4fb4b548d71cf3e1da11e3c861a16929ac7073d8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197517"
---
# <a name="learn-about-privileged-access-management"></a>了解特权访问管理

特权访问管理可以对 Office 365 中的特权管理任务进行粒度访问控制。 它可以帮助保护你的组织免受具有永久访问敏感数据或访问关键配置设置权限的现有特权管理账户带来的安全问题。 特权访问管理要求用户通过范围和时间高度受限的审核工作流，请求获取实时访问权限来完成提升和特权任务。 此配置授予用户适当的访问权限，以执行手头任务，而不会冒暴露敏感数据或关键配置设置的风险。 在组织中启用特权访问Microsoft 365使组织能够使用零长期特权运行，并针对长期管理访问漏洞提供一个防御层。

有关集成的客户密码箱和特权访问管理工作流的快速概述，请参阅此客户密码箱 [和特权访问管理视频](https://go.microsoft.com/fwlink/?linkid=2066800)。

## <a name="layers-of-protection"></a>保护层

特权访问管理补充了 Microsoft 365 安全中心体系结构中的其他数据和访问功能保护。 将特权访问管理作为集成的分层安全方法的一部分提供了一个安全模型，可以最大限度地保护敏感信息和 Microsoft 365 配置设置。 如图所示，特权访问管理建立在 Microsoft 365 数据本机加密提供的保护和 Microsoft 365 服务基于角色的访问控制安全模型的基础上。 当与[Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)一起使用时，这两个功能提供访问控制，在不同范围内提供实时访问。

![分层保护Microsoft 365。](../media/pam-layered-protection.png)

特权访问管理在任务级别定义和作用域，而Azure AD Privileged Identity Management在角色级别应用保护，能够执行多个任务。 Azure AD Privileged Identity Management 主要允许管理 AD 角色和角色组的访问，而 Microsoft 365 中的特权访问管理仅应用于任务级别。

- **启用特权访问管理，同时已使用 Azure AD Privileged Identity Management：** 添加特权访问管理提供了另一个精细的保护层和审核功能，用于对数据进行特权Microsoft 365访问。

- **启用 Azure AD Privileged Identity Management，同时已在 Office 365：** 将 Azure AD Privileged Identity Management添加到特权访问管理可以扩展对主要由用户角色或标识Microsoft 365外部数据的特权访问。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特权访问管理体系结构和流程

以下每个流程流概述了特权访问的体系结构，以及它如何与 Microsoft 365层、审核和 Exchange Management 运行空间进行交互。

### <a name="step-1-configure-a-privileged-access-policy"></a>步骤 1：配置特权访问策略

在使用[Microsoft 365 管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell 配置特权访问策略时，需要定义策略和特权访问功能进程以及 Microsoft 365 属性。 这些活动记录在安全与合规 &amp; 中心。 该策略现在已启用并可以处理传入的审批请求。

![步骤 1：创建策略。](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>第 2 步：访问请求

在[Microsoft 365 管理中心](https://admin.microsoft.com)或 Exchange PowerShell 中，用户可以请求对提升或特权任务的访问权限。 特权访问功能将请求发送到Microsoft 365配置的权限访问策略进行处理，并将活动记录在安全与合规中心 &amp; 日志中。

![步骤 2：访问请求。](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>步骤 3：访问审批

将生成批准请求，并通过电子邮件将待处理请求通知发送给审批者。 如果通过审批，特权访问请求将作为审批进行处理，并且可以完成任务。 如果遭到拒绝，任务将被阻止，请求者无法获得权限。 请求者通过电子邮件收到请求批准或拒绝的通知。

![步骤 3：访问审批。](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>第 4 步：访问处理

对于已批准的请求，任务由 Exchange 管理运行空间处理。 根据特权访问策略检查审批，并由 Microsoft 365 基底处理。 任务的所有活动都记录在安全与合规 &amp; 中心。

![步骤 4：访问处理。](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>哪些 SK 可以在应用程序内使用特权Office 365？

客户可以使用特权访问管理进行各种选择，Microsoft 365 Office 365订阅和加载项。 有关详细信息 [，请参阅特权访问管理](privileged-access-management-configuration.md) 入门。

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>特权访问何时支持Office 365 Exchange工作负载？。

Privileged access management will be available in other Office 365 workloads soon. 有关详细信息[，Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)路线图。

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>我的组织需要 30 多个特权访问策略，是否增加此限制？

是的，功能路线图中提供了提高每个组织 30 个特权访问策略的当前限制。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>是否需要成为全局管理员才能管理 Office 365？

否，您需要为Exchange管理特权访问的帐户分配角色管理Office 365。 如果不想将角色管理角色配置为独立帐户权限，则全局管理员角色默认包含此角色，可以管理特权访问。 审批者组中包含的用户无需是全局管理员或分配有角色管理角色，通过 PowerShell 审阅和批准请求。

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>特权访问管理与客户密码箱如何相关？

[当 Microsoft](/office365/admin/manage/customer-lockbox-requests) 访问数据时，客户密码箱允许组织进行一级访问控制。 特权访问管理允许对组织中所有特权任务进行Microsoft 365访问控制。

## <a name="ready-to-get-started"></a>准备好开始了吗？

开始 [为组织配置特权访问管理](privileged-access-management-configuration.md)。

## <a name="learn-more"></a>了解详细信息

[交互式指南：使用特权访问管理监视和控制管理员任务](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
