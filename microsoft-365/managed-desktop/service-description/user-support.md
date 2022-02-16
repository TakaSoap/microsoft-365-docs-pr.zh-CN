---
title: 用户支持
description: 介绍客户引导和合作伙伴引导支持的选项。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 43b1addbf1b1d5e0d0134f80e4a90c420a4d6789
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825393"
---
# <a name="user-support"></a>用户支持

你的Microsoft 托管桌面用户可以从你的组织 ("客户引导"支持) 或所选合作伙伴 ("合作伙伴引导的"支持中心) 。

我们的目标是为用户提供一致的体验，同时通过这两种支持选项确保设备安全。 无论你选择哪个选项，以下相同的原则都适用：

- 将 Microsoft 托管桌面 设备与现有支持流程灵活集成。
- 明确支持提供程序、IT 管理员和管理员之间的角色Microsoft 托管桌面。
- [定义的升级路径](#workflow-for-support-providers)。
- 由 Microsoft 托管桌面提供的文档以及门户，可根据需要请求提升的设备访问权限并上报给支持人员。
- 由安全中心每天Microsoft 托管桌面威胁监视和缓解。

## <a name="roles-and-responsibilities"></a>角色和职责

为了确保服务质量而不会损害安全性，支持提供程序、IT 管理员Microsoft 托管桌面具有不同的角色和职责。

| 角色 | 责任 |
| ------ | ------ |
| 支持提供程序 | 由你 (客户引导的支持，或者由合作伙伴引导的合作伙伴提供支持) 负责以下项目： <ul><li>为用户提供从第一个联系人到解决方案的所有用户支持和技术支持。</li><li>实现组织建立或与所选支持提供商合作建立的用户支持的所有服务级别协议。</li><li>执行特定的故障排除操作，例如请求提升的设备权限，如 [获取用户帮助中所述](../working-with-managed-desktop/end-user-support.md)。</li><li>排查并修正用户问题，包括： <ul><li>操作系统 (Windows) </li><li>Microsoft Apps企业版</li><li>浏览器功能</li><li>设备问题</li><li>基础结构问题，如打印机、驱动程序和 VPN</li><li>业务线应用程序</li></ul></ul> |
| IT 管理员 | IT 管理员负责以下各项： <ul><li>与支持提供商合作，为用户支持设置和管理服务级别协议</li><li>管理批准的支持人员提升的访问权限。 有关详细信息，请参阅启用 [用户支持功能](../get-started/enable-support.md)。</li><li>如果存在影响用户的设备问题，请通过使用管理员支持流程Microsoft 托管桌面升级问题。 有关详细信息，请参阅管理员[对 Microsoft 托管桌面](../working-with-managed-desktop/admin-support.md)。</li><li>将硬件相关问题路由到相应的供应商。</li><li>维护和保护设备上设备安全策略Microsoft 托管桌面设置。 不要更改我们设置的策略。 </li></ul> |
| Microsoft 托管桌面 |作为服务提供商，我们负责以下各项： <ul><li>提供提升的设备访问和问题升级（包括文档）的方式。</li><li>将此信息与角色和职责保持最新。</li><li>根据严重性定义响应管理员支持请求。</li><li>每天为注册的所有设备提供威胁监视和缓解。</li></ul> |

## <a name="workflow-for-support-providers"></a>支持提供程序的工作流

无论支持是客户引导式还是合作伙伴引导式，用户支持请求的活动流都遵循以下路径：

:::image type="content" source="../../media/mmd-support-flow.png" alt-text="当用户联系支持人员时，他们将通过你设计的分层员工系统工作。必须指定一组支持人员，这些人员将具有提升和升级的能力，称为支持上报团队。对于特定Microsoft 托管桌面问题，他们可上报至我们的运营团队。对于其他 Microsoft 问题，他们可路由到现有的支持渠道（统一或顶级）。硬件问题应始终路由到已建立的提供商或供应商":::

将现有流程与适用于Microsoft 托管桌面的此工作流集成非常灵活，因此详细信息可能会有所不同。 通常，支持提供程序遵循现有的基于层或讲台的方法。 支持提供程序指定能够提升权限或上报问题的特定用户Microsoft 托管桌面操作。 最好使此组小于更广泛的支持团队。

如果必须将问题上报给Microsoft 托管桌面，则有助于确定问题应定向到哪个团队。 我们可以适当地转移事例，但可以节省从一开始将它们路由到正确位置的时间。

| 问题 | 联系此团队 |
| ------ | ------ |
| 特定于用户Microsoft 托管桌面 | 例如，由服务本身部署的策略或设置。 通过创建新的支持请求直接上报给运营团队。 有关详细信息，请参阅 [获取用户帮助](../working-with-managed-desktop/end-user-support.md)。
| 硬件问题 | 直接到硬件供应商。
| 其他问题| 通过现有支持渠道进行升级，无论这是统一订阅还是顶级订阅。

## <a name="provided-support-framework"></a>提供支持框架

### <a name="elevation-portal"></a>提升门户

由于Microsoft 托管桌面在标准用户上运行，因此某些任务需要提升权限。 有关用户帐户控制详细信息，请参阅 [用户帐户控制](/windows/security/identity-protection/user-account-control/user-account-control-overview)。 为了使支持人员能够在排查用户问题时执行任务[](../working-with-managed-desktop/end-user-support.md#elevation-requests)，我们提供对管理员帐户的"实时"访问。 只有你指定的用户才能安全访问此密码，并且每几小时轮换一次。  

若要了解如何设置用户以访问此门户，请参阅启用 [用户支持功能](../get-started/enable-support.md)。

有关提交提升请求的步骤，请参阅 [提升请求](../working-with-managed-desktop/end-user-support.md#elevation-requests)。

### <a name="escalation-portal"></a>升级门户

如果问题需要上报给Microsoft 托管桌面团队，指定的支持人员可能与 IT 管理员支持请求类似。  

> [!NOTE]
> 只有 Sev C 支持请求可以这样存档。 对于与其他严重性描述相匹配的问题，建议联系相应的 IT 管理员进行文件处理。 有关详细信息，请参阅支持 [请求严重性定义](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions)。

若要了解如何设置用户以访问此门户，请参阅启用 [用户支持功能](../get-started/enable-support.md)。

有关提交升级请求的步骤，请参阅 [提升请求](../working-with-managed-desktop/end-user-support.md#escalation-requests)。
