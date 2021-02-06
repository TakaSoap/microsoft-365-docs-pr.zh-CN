---
title: 了解特权访问管理
description: 本文概述了 Microsoft 365 中的特权访问管理，包括常见问题解答 (常见问题) 。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
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
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126601"
---
# <a name="learn-about-privileged-access-management"></a>了解特权访问管理

特权访问管理允许对 Office 365 中的特权管理任务进行精细的访问控制。 它可以帮助保护组织免受使用现有特权管理员帐户的漏洞，这些帐户具有对敏感数据的常访问权或关键配置设置的访问权限。 特权访问管理要求用户请求实时访问权限，以通过范围和时间限制较高的审批工作流完成提升的特权任务。 此配置使用户能够具有足够的访问权限来执行当前任务，而不会面临敏感数据或关键配置设置泄露的风险。 在 Microsoft 365 中启用特权访问管理后，你的组织可以零长期特权运行，并提供一层防御长期管理访问漏洞的防御层。

有关集成的客户密码箱和特权访问管理工作流的快速概述，请参阅此客户密码箱和 [特权访问管理视频](https://go.microsoft.com/fwlink/?linkid=2066800)。

## <a name="layers-of-protection"></a>保护层

特权访问管理补充了 Microsoft 365 安全体系结构内的其他数据和访问功能保护。 将特权访问管理作为集成和分层安全方法的一部分提供一种安全模型，可最大限度地保护敏感信息和 Microsoft 365 配置设置。 如图所示，特权访问管理基于 Microsoft 365 数据的本机加密提供的保护以及 Microsoft 365 服务的基于角色的访问控制安全模型。 当与 [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)一起使用时，这两项功能为访问控制提供不同范围的实时访问权限。

![Microsoft 365 中的分层保护](../media/pam-layered-protection.png)

特权访问管理在任务级别定义和作用域，而Azure AD Privileged Identity Management 在角色级别应用保护，能够执行多个任务。 Azure AD Privileged Identity Management 主要允许管理 AD 角色和角色组的访问权限，而 Microsoft 365 中的特权访问管理仅适用于任务级别。

- **在已使用 Azure AD Privileged Identity Management** 的同时启用特权访问管理：添加特权访问管理为特权访问 Microsoft 365 数据提供了另一层精细的保护和审核功能。

- **在 Office 365**  中已使用特权访问管理的同时启用 Azure AD Privileged Identity Management： 将 Azure AD Privileged Identity Management 添加到特权访问管理可以扩展对 Microsoft 365 外部数据的特权访问，这些数据主要由用户角色或标识定义。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特权访问管理体系结构和流程

以下每个流程流概述了特权访问的体系结构及其与 Microsoft 365 底层、审核和 Exchange 管理运行空间的交互方式。

### <a name="step-1-configure-a-privileged-access-policy"></a>步骤 1：配置特权访问策略

使用 [Microsoft 365](https://admin.microsoft.com) 管理中心或 Exchange 管理 PowerShell 配置特权访问策略时，在 Microsoft 365 底层中定义策略、特权访问功能进程和策略属性。 这些活动记录在安全合规 &amp; 中心。 该策略现已启用，并已准备好处理传入的审批请求。

![步骤 1：策略创建](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>步骤 2：访问请求

在 [Microsoft 365 管理](https://admin.microsoft.com) 中心或 Exchange 管理 PowerShell 中，用户可以请求对提升或特权任务的访问权限。 特权访问功能将请求发送到 Microsoft 365 底层，以根据配置的权限访问策略进行处理，并将活动记录在安全 &amp; 合规中心日志中。

![步骤 2：访问请求](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>步骤 3：访问审批

将生成审批请求，并通过电子邮件将待处理的请求通知通过电子邮件发送给审批者。 如果获得批准，特权访问请求将处理为审批，并且任务已准备好完成。 如果拒绝，则阻止该任务，并且不会向请求者授予任何访问权限。 通过电子邮件向请求者通知请求审批或拒绝。

![步骤 3：访问审批](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>步骤 4：访问处理

对于已批准的请求，任务由 Exchange 管理运行空间处理。 根据特权访问策略检查批准，由 Microsoft 365 底层处理。 任务的所有活动都记录在安全合规 &amp; 中心。

![步骤 4：访问处理](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>哪些 SUS 可以在 Office 365 中使用特权访问？

特权访问管理适用于各种 Microsoft 365 和 Office 365 订阅和加载项的客户。 有关详细信息 [，请参阅特权访问管理](privileged-access-management-configuration.md) 入门。

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>特权访问何时将支持 Exchange 之外的 Office 365 工作负载？

特权访问管理将很快在其他 Office 365 工作负载中提供。 有关详细信息，请访问 [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) 路线图。

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>我的组织需要 30 多个特权访问策略，是否将提高此限制？

是的，提升每个组织当前 30 个特权访问策略的限制取决于功能路线图。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>是否需要成为全局管理员才能管理 Office 365 中的特权访问？

不需要，您需要为管理 Office 365 中的特权访问的帐户分配 Exchange 角色管理角色。 如果不想将角色管理角色配置为独立帐户权限，则默认情况下全局管理员角色包括此角色，并可以管理特权访问。 审批者组中包含的用户无需是全局管理员或分配有角色管理角色，即使用 PowerShell 审阅和批准请求。

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>特权访问管理与客户密码箱如何相关？

[当 Microsoft](/office365/admin/manage/customer-lockbox-requests) 访问数据时，客户密码箱允许组织进行一级访问控制。 特权访问管理允许对组织中所有 Microsoft 365 特权任务进行精细访问控制。

## <a name="ready-to-get-started"></a>准备好开始了吗？

开始 [为组织配置特权访问管理](privileged-access-management-configuration.md)。

## <a name="learn-more"></a>了解更多

[交互式指南：使用特权访问管理监视和控制管理员任务](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
