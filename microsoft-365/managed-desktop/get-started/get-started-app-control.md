---
title: 开始使用应用程序控制
description: 本文介绍如何启用应用控件
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: a671bf36e957ffc416f51ec531aaeed6ddfa41b3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315395"
---
# <a name="get-started-with-app-control"></a>开始使用应用程序控制

在环境中启用应用控制之前，请务必查看并了解Microsoft 托管桌面[实现它](../service-description/app-control.md)以及你的角色和责任。

Microsoft 托管桌面关注获取安全基本策略的更具挑战性方面，从而简化了应用控制。

IT 管理员必须在测试圈中测试你的应用，并查看日志中是否有警告或错误。 如果应用需要豁免，你可以提出请求，Microsoft 托管桌面操作可能，具体取决于谁先检测到它。

## <a name="initial-deployment-of-apps"></a>应用的初始部署

首次部署应用时，Microsoft 托管桌面评估其当前行为。 启用应用控制的确切步骤取决于是否已在你的环境中部署设备。

### <a name="devices-not-yet-in-use"></a>尚未使用的设备

如果尚未使用任何设备，请通过 Microsoft 托管桌面 操作打开支持票证，以请求打开应用控制。 按照此计划，操作将逐步将策略部署到部署组：

| 部署组 | 策略类型 | Timing |
| ------ | ------ | ------ |
| 测试 |  Audit |  第 0 天 |
| First | Enforced | 第 1 天 |
| 快速 | Enforced |  第 2 天 |
| 宽泛 | Enforced |  第 3 天 |

你始终可以打开另一个支持请求，以在推出期间随时暂停或回滚此部署的一部分。

### <a name="devices-already-in-use"></a>已在使用的设备

如果已至少有一个Microsoft 托管桌面设备，请按照以下步骤操作：

1. 使用请求打开应用Microsoft 托管桌面的"操作"打开服务票证。 操作将审核 [策略部署到](../service-description/app-control.md#audit-policy) 所有设备。
2. [测试应用程序](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 以查看是否阻止了任何应用程序。 如果应用程序被阻止，请打开 [签名者请求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)。
3. 完成测试后，无论 (结果如何，) 通知操作，并通知任何挂起的签名者请求。 按照此计划，操作将逐步将策略部署到部署组：

| 部署组 | 策略类型 | Timing |
| ------ | ------ | ------ |
| 测试     | Audit |  第 0 天 |
| First     | Enforced | 第 1 天 |
| 快速     | Enforced |  已暂停，根据请求推出 |
| 宽泛     | Enforced |  已暂停，根据请求推出 |

你始终可以打开另一个支持请求，以在推出期间随时暂停或回滚此部署的一部分。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. 访问 [管理员门户](access-admin-portal.md)。
1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)。
1. [注册后调整设置](conditional-access.md)。
1. 部署并分配 [Intune 公司门户](company-portal.md)。
1. [分配许可证](assign-licenses.md)。
1. [部署应用](deploy-apps.md)。
1. [准备设备](prepare-devices.md)。
1. 设置 [使用 Autopilot 和注册状态页的首次运行体验](esp-first-run.md)。
1. [启用用户支持功能](enable-support.md)。
1. [让用户做好使用设备的准备](get-started-devices.md)。
1. 本文介绍的应用控制 (入门) 。
