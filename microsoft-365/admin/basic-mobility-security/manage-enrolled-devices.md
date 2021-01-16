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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本移动性和安全性可以帮助您保护和管理移动设备。
ms.openlocfilehash: 4954da0ff44276d9bd46cabc78bc52c7879e5e26
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876956"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>在 Microsoft 365 中管理在移动设备管理中注册的设备

Microsoft 365 的内置移动设备管理可帮助你保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 手机。 第一步是登录到 Microsoft 365 并设置基本移动性和安全性。 有关详细信息，请参阅["设置基本移动性和安全性"。](set-up.md)

设置后，组织中人员必须在服务中注册其设备。 有关详细信息，请参阅使用基本移动性和安全性 [注册移动设备](enroll-your-mobile-device.md)。然后，可以使用基本移动性和安全性来帮助管理组织中设备。 例如，可以使用设备安全策略来帮助限制电子邮件访问或其他服务、查看设备报告以及远程擦除设备。 你通常转到安全与合规&执行这些任务。 有关详细信息，请参阅 [Microsoft 365 合规中心](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)。

## <a name="device-management-tasks"></a>设备管理任务

若要访问设备管理面板，请按照以下步骤操作：

1. 转到 [Microsoft 365 管理中心](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)。

2. 在搜索字段中键入移动设备管理，然后从结果列表中选择   "移动设备管理"。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="移动设备管理选项":::

3. 选择  **"让我们开始"。**

## <a name="manage-mobile-devices"></a>管理移动设备

设置基本移动性和安全性后，可通过以下几种方法管理您组织的移动设备。

|**若要实现此目的**|**执行操作**|
|:----------------|:------------------------------------------------------------------------------|
|擦除设备 |在"设备管理"面板中，选择 *设备* 名称  ****，然后完全擦除以删除所有信息，或选择性擦除以仅删除     ****   设备上的组织信息。 有关详细信息，请参阅"基本移动性和安全性"中的"[擦除移动设备"。](wipe-mobile-device.md)|
|阻止不受支持的设备使用 Exchange ActiveSync 访问 Exchange 电子邮件 |在"设备管理"面板中，选择"  **阻止"。** |
|设置设备策略，如密码要求和安全设置 |在"设备管理"面板中，选择 **"设备安全策略添加**   >  **+ "。** 有关详细信息，请参阅在基本移动性和安全性中创建 [设备安全策略](create-device-security-policies.md)。|
|查看阻止的设备列表  |在设备管理面板中，在  **"选择视图"下选择**     **"阻止"。** |
|解除阻止单个用户或一组用户的不相容或不受支持的设备  |选择下列方法之一以取消阻止设备：<br/>- 从已应用策略的安全组中删除用户。 转到 Microsoft 365 管理中心> **组，** 然后选择组名称。 选择 **"编辑成员和管理员"。**<br/>- 从设备策略中删除用户是成员的安全组。 转到安全&合规> **安全策略**   >  **设备安全策略**。 选择设备策略名称，然后选择"编辑  >  **部署"。**<br/>- 取消阻止设备策略的所有不相容设备。 转到安全&合规> **安全策略**   >  **设备安全策略**。 选择设备策略名称，然后选择 **"编辑**  >  **访问要求"。** 选择 **"允许访问并报告冲突"。**<br/>- 若要 &取消阻止用户或用户组的不合规或不受支持的设备，请转到安全与合规中心 >安全策略 **设备管理** 设备访问   >  ****   >  **设置**。 添加包含要排除的成员的安全组，阻止其访问 Microsoft 365。 有关详细信息，请参阅在 [Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)管理中心创建、编辑或删除安全组。|
|删除用户，以便其设备不再由基本移动性和安全性管理 |若要删除用户，请编辑具有基本移动性和安全性的设备管理策略的安全组。 有关详细信息，请参阅在  [Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)管理中心创建、编辑或删除安全组。<br/>若要删除所有 Microsoft 365 用户的基本移动性和安全性，请参阅["关闭基本移动性和安全性"。](turn-off.md)|

v14 (live) 