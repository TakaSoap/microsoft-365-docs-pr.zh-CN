---
title: 用户支持
description: 介绍客户引导和合作伙伴引导支持的选项。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: ea2e6e95ec76965e01d73bb1ecbd53c798eeca71
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205709"
---
# <a name="user-support"></a>用户支持

你的Microsoft 托管桌面可以从你的组织获取支持 (我们将此支持称为"客户引导"支持) ，也可以从选定的合作伙伴 ("合作伙伴引导"支持) 。 我们的目标是为用户提供一致的体验，同时通过这两种支持选项确保设备安全。 无论你选择哪个选项，以下相同的原则都适用： 

- 将Microsoft 托管桌面设备与现有支持流程灵活集成。 
- 明确支持提供程序、IT 管理员和管理员之间的角色Microsoft 托管桌面 
- [定义的升级路径](#workflow-for-support-providers)
- 由 Microsoft 托管桌面文档，以及一个门户，可根据需要请求提升的设备访问权限并上报给支持人员。
- 由安全中心每天Microsoft 托管桌面威胁监视和缓解

## <a name="roles-and-responsibilities"></a>角色与责任

为了确保服务质量而不会损害安全性，支持提供商、IT 管理员Microsoft 托管桌面各自具有不同的角色和职责。

### <a name="support-provider"></a>支持提供程序

由你 (客户引导的支持或合作伙伴引导的合作伙伴提供支持) 负责以下项目：

- 从第一次联系到用户解决方案，提供所有用户支持和技术协助
- 实现你的组织建立或与所选支持提供商合作建立的用户支持的所有服务级别协议
- 执行特定的故障排除操作，例如请求提升的设备权限，如 [获取用户帮助中所述](../working-with-managed-desktop/end-user-support.md)
- 排查和修正用户问题，包括：
    - 操作系统 (Windows) 
    - Microsoft Apps企业版
    - 浏览器功能
    - 设备问题
    - 基础结构问题，如打印机、驱动程序和 VPN
    - 业务线应用程序

### <a name="it-admin"></a>IT 管理员

IT 管理员负责以下各项：

- 与支持提供商合作，为用户支持设置和管理服务级别协议
- 管理批准的支持人员提升的访问权限。 有关详细信息，请参阅启用 [用户支持功能](../get-started/enable-support.md)
- 如果存在影响用户的设备问题，则使用管理员支持流程Microsoft 托管桌面升级这些问题。 有关详细信息，请参阅管理员[对 Microsoft 托管桌面](../working-with-managed-desktop/admin-support.md)的支持。
- 将硬件相关问题路由到相应的供应商
- 通过阻止更改我们设置的策略Microsoft 托管桌面设备上维护和保护设备安全策略设置。

### <a name="microsoft-managed-desktop"></a>Microsoft 托管桌面

作为服务提供商，我们负责以下各项：

- 提供提升的设备访问和问题升级方法，包括文档
- 将有关角色和职责的信息保持最新
- 根据严重性定义响应管理员支持请求
- 每天为所有注册的设备提供威胁监视和缓解

## <a name="workflow-for-support-providers"></a>支持提供程序的工作流

无论支持是客户引导式还是合作伙伴引导式，用户支持请求的活动流都遵循以下路径：

:::image type="content" source="../../media/mmd-support-flow.png" alt-text="当用户联系支持人员时，他们将通过您设计的分层员工系统工作。必须指定一组支持人员，这些人员将具有提升和升级的能力，称为支持上报团队。对于特定的Microsoft 托管桌面问题，他们可上报至我们的运营团队。对于其他 Microsoft 问题，他们可路由到现有的支持渠道（统一或顶级）。应始终将硬件问题路由到已建立的提供商或供应商":::

将现有流程与适用于Microsoft 托管桌面的此工作流集成非常灵活，因此详细信息可能会有所不同。 通常，支持提供程序遵循现有的基于层或分配的方法，指定能够提升权限或将问题上报给 Microsoft 托管桌面 操作的特定用户。 最好使此组小于更广泛的支持团队。

如果需要将用户问题上报为Microsoft 托管桌面，则有助于确定问题应定向到哪个团队。 我们可以适当地转移事例，但可以节省从一开始将它们路由到正确位置的时间。

- 特定于Microsoft 托管桌面 (例如，服务本身部署的策略或设置) ：通过创建新的支持请求直接上报给运营团队。 有关详细信息，请参阅 [获取用户帮助](../working-with-managed-desktop/end-user-support.md)。
- 硬件问题：直接到硬件供应商或供应商
- 其他问题：通过现有支持渠道升级，无论这是统一订阅还是顶级订阅。

## <a name="provided-support-framework"></a>提供支持框架


### <a name="elevation-portal"></a>提升门户 

由于Microsoft 托管桌面在标准用户上运行，因此某些任务需要提升权限。 有关用户帐户控制详细信息，请参阅 [用户帐户控制](/windows/security/identity-protection/user-account-control/user-account-control-overview)。 为了使支持人员能够在排查用户问题时执行任务[](../working-with-managed-desktop/end-user-support.md#elevation-requests)，我们提供对管理员帐户的"实时"访问权限。 只有指定的用户才能安全访问此密码，并每隔几小时轮换一次。  

若要了解如何设置用户以访问此门户，请参阅启用 [用户支持功能](../get-started/enable-support.md)。

有关提交提升请求的步骤，请参阅 [提升请求](../working-with-managed-desktop/end-user-support.md#elevation-requests)。

### <a name="escalation-portal"></a>升级门户 

如果问题需要上报给Microsoft 托管桌面团队，指定的支持人员可能指示类似于 IT 管理员支持请求。  

> [!NOTE]
> 只有 Sev C 支持请求可以这样存档。 对于与其他严重性描述相匹配的问题，建议联系相应的 IT 管理员进行文件处理。 有关详细信息，请参阅支持 [请求严重性定义](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions)。

若要了解如何设置用户以访问此门户，请参阅启用 [用户支持功能](../get-started/enable-support.md)。

有关提交升级请求的步骤，请参阅 [提升请求](../working-with-managed-desktop/end-user-support.md#escalation-requests)。
