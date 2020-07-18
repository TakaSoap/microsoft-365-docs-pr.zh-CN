---
title: 应用程序控制入门
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170685"
---
# <a name="get-started-with-app-control"></a>应用程序控制入门

在您的环境中启用应用程序控制之前，请务必查看并了解[Microsoft 托管桌面如何实现 it](../service-description/app-control.md)以及您的角色和职责。

Microsoft 托管桌面通过解决获取安全基准策略的更具挑战性的方面，简化了应用程序控制。 您的 IT 管理员仍必须在测试环中测试您的应用程序，并查看日志中的任何警告或错误。 如果应用需要豁免，则可以对请求进行存档，也可以根据首先检测到的用户，Microsoft 托管桌面操作可能会发生此情况。

## <a name="initial-deployment-of-apps"></a>应用程序的初始部署

首次部署应用时，Microsoft 托管桌面需要评估其当前行为。 启用应用程序控制的具体步骤取决于是否已在您的环境中部署设备。

### <a name="devices-already-in-use"></a>设备已在使用中

如果已有至少一个 Microsoft 托管桌面设备在使用中，请按照以下步骤操作：

1. 打开包含 Microsoft 托管桌面操作的服务票证，请求我们启用应用程序控制。 操作将向所有设备部署[审核策略](../service-description/app-control.md#audit-policy)。
2. [测试应用程序](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app)以查看是否有任何将被阻止。 如果某个应用程序将被阻止，请打开一个[签署人请求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)。 
3. 完成测试后（无论结果如何），通知操作，记下任何待处理的签名者请求。 按照此计划，操作将逐步将策略部署到部署组：

|部署组  |策略类型  |Timing  |
|---------|---------|---------|
|测试     |  Audit       |  第0天       |
|First     | Enforced        | 第 1 天        |
|快速     | Enforced        |  第 3 天       |
|宽泛     | Enforced        |  第 7 天       |

在首次部署期间，您始终可以打开另一个服务请求以暂停或回滚此部署的部分。

### <a name="devices-not-yet-in-use"></a>尚未使用的设备

如果你还没有使用任何设备，请使用 Microsoft 托管桌面操作打开一个服务票证，请求我们启用应用程序控制。 按照此计划，操作将逐步将策略部署到部署组：

|部署组  |策略类型  |Timing  |
|---------|---------|---------|
|测试     |  Audit       |  第0天       |
|First     | Enforced        | 第 1 天        |
|快速     | Enforced        |  第 3 天       |
|宽泛     | Enforced        |  第 7 天       |

在首次部署期间，您始终可以打开另一个服务请求以暂停或回滚此部署的部分。

