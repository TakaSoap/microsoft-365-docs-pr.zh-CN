---
title: 在 Microsoft 365 中管理在移动设备管理中注册的设备
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- MET150
description: 基本移动性和安全性可帮助保护和管理组织移动设备。
ms.openlocfilehash: 02c8efbed8f781dfdb0e9abfaa2af3a2c92733ff
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780794"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>在 Microsoft 365 中管理在移动设备管理中注册的设备

适用于Microsoft 365的内置移动设备管理可帮助保护和管理用户的移动设备，如 iPhone、iPad、Androids 和Windows手机。 第一步是登录Microsoft 365并设置基本的移动性和安全性。 有关详细信息，请参阅 [“设置基本移动性和安全性](set-up.md)”。

设置后，组织中的人员必须在服务中注册其设备。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device.md)。 然后，可以使用基本移动性和安全性来帮助管理组织中的设备。 例如，可以使用设备安全策略来帮助限制电子邮件访问或其他服务、查看设备报告和远程擦除设备。 通常会转到安全&合规中心执行这些任务。 有关详细信息，请参阅[Microsoft 365 合规中心](../../compliance/microsoft-365-compliance-center.md)。

## <a name="device-management-tasks"></a>设备管理任务

若要转到设备管理面板，请执行以下步骤：

1. 转到[Microsoft 365 管理中心](../../admin/admin-overview/about-the-admin-center.md)。

2. 在搜索字段中键入移动设备管理，然后从结果列表中选择 **移动设备管理**。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="移动设备管理选项。":::

3. 选择 **“让我们开始** 吧”。

## <a name="manage-mobile-devices"></a>管理移动设备

设置基本移动性和安全性后，可通过以下方式管理组织中的移动设备。

|所执行的操作|具体操作|
|---|---|
|擦除设备|在设备管理面板中，选择 *设备名称*，然后 **完全擦除** 以删除所有信息或 **选择性擦除** 以仅删除设备上的组织信息。 有关详细信息，请参阅 [在基本移动性和安全性中擦除移动设备](wipe-mobile-device.md)。|
|阻止不受支持的设备使用 Exchange ActiveSync 访问 Exchange 电子邮件|在设备管理面板中，选择 **“阻止**”。|
|设置设备策略，例如密码要求和安全设置|在设备管理面板中，选择 **“设备安全** > **策略”+**。 有关详细信息，请参阅 [在基本移动性和安全性中创建设备安全策略](create-device-security-policies.md)。|
|查看阻止的设备列表|在设备管理面板中，在 **“选择视图**”下选择 **“阻止**”。|
|解除阻止单个用户或一组用户的不相容或不受支持的设备|选取以下选项之一以取消阻止设备：<br/>- 从已应用策略的安全组中删除用户或用户。 转到Microsoft 365 管理中心 ><a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**组**</a>，然后选择组名称。 选择 **“编辑成员和管理员**”。<br/>- 从设备策略中删除用户所属的安全组。 转到安全&合规中心> **安全策略** > **Device 安全策略**。 选择设备策略名称，然后选择 **EditDeployment** > 。<br/>- 取消阻止设备策略的所有不符合设备。 转到安全&合规中心> **安全策略** > **Device 安全策略**。 选择设备策略名称，然后选择 **EditAccess** >  要求。 选择 **“允许访问和报告冲突**”。<br/>- 若要为用户或一组用户取消阻止不符合或不受支持的设备，请转到安全&合规中心>**安全策略** > **Device managementManage** >  **设备访问设置**。 添加一个安全组，其中包含要排除的成员不受阻止访问Microsoft 365。 有关详细信息，请参阅[Microsoft 365 管理中心中创建、编辑或删除安全组](../../admin/email/create-edit-or-delete-a-security-group.md)。|
|删除用户，使其设备不再由基本移动性和安全性管理|若要删除用户，请编辑具有基本移动性和安全性设备管理策略的安全组。 有关详细信息，请参阅[Microsoft 365 管理中心中创建、编辑或删除安全组](../../admin/email/create-edit-or-delete-a-security-group.md)。<br/>若要从所有Microsoft 365用户中删除基本移动性和安全性，请[参阅“关闭基本移动性和安全性](turn-off.md)”。|

实时 (v14) 
