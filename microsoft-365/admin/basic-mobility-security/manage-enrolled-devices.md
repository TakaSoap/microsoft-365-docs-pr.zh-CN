---
title: 管理在移动设备管理中注册的设备Microsoft 365
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
description: 基本移动性和安全性可帮助您保护和管理组织的移动设备。
ms.openlocfilehash: 152b4cc33fab740516d7138cca8f4a15096c8312
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166008"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>管理在移动设备管理中注册的设备Microsoft 365

内置移动设备管理适用于 Microsoft 365 可帮助你保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 电话。 第一步是登录到 Microsoft 365并设置基本移动性和安全性。 有关详细信息，请参阅设置 [基本移动性和安全性](set-up.md)。

设置后，组织人员必须在服务中注册其设备。 有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)。然后，可以使用基本移动性和安全性来帮助管理贵组织的设备。 例如，可以使用设备安全策略来帮助限制电子邮件访问或其他服务、查看设备报告以及远程擦除设备。 通常，你将转到安全与&中心执行这些任务。 有关详细信息，[请参阅Microsoft 365 合规中心。](../../compliance/microsoft-365-compliance-center.md)

## <a name="device-management-tasks"></a>设备管理任务

若要访问设备管理面板，请按照以下步骤操作：

1. 转到 ["Microsoft 365 管理中心"。](../../admin/admin-overview/about-the-admin-center.md)

2. 在搜索字段中键入"移动设备管理"，然后从结果列表中选择"移动设备   管理"。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="移动设备管理选项。":::

3. 选择  **让我们开始吧**。

## <a name="manage-mobile-devices"></a>管理移动设备

设置基本移动性和安全性后，可通过以下方法管理组织中移动设备。

|**若要实现此目的**|**执行操作**|
|:----------------|:------------------------------------------------------------------------------|
|擦除设备 |在"设备管理"面板中 **，选择"设备  **** 名称"，然后选择"完全擦除"以删除所有信息，或选择"选择性擦除"以仅删除     ****   设备上的组织信息。 有关详细信息，请参阅 [Basic Mobility and Security](wipe-mobile-device.md)中的擦除移动设备。|
|阻止不受支持的设备使用 Exchange ActiveSync 访问 Exchange 电子邮件 |在"设备管理"面板中，选择"阻止  **"。** |
|设置设备策略，如密码要求和安全设置 |在设备管理面板中，选择 **设备安全策略**   >  **添加 +**。 有关详细信息，请参阅在基本移动性和安全性中 [创建设备安全策略](create-device-security-policies.md)。|
|查看阻止的设备列表  |在"设备管理"面板的"  **选择视图"下，选择**   "  **已阻止"。** |
|解除阻止单个用户或一组用户的不相容或不受支持的设备  |选择下列方法之一以取消阻止设备：<br/>- 从已应用策略的安全组中删除一个或多个用户。 转到"Microsoft 365 管理中心 >组"，<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>然后选择组名称。 选择 **"编辑成员和管理员"。**<br/>- 从设备策略中删除用户是成员的安全组。 转到安全&合规> **安全策略 设备**   >  **安全策略**。 选择设备策略名称，然后选择"编辑 **部署**  >  **"。**<br/>- 取消阻止设备策略的所有不相容设备。 转到安全&合规> **安全策略 设备**   >  **安全策略**。 选择设备策略名称，然后选择"**编辑**  >  **访问要求"。** 选择 **"允许访问并报告冲突"。**<br/>- 若要取消阻止用户或用户组的不兼容或不受支持的设备，请转到安全 & 合规中心 > **安全策略** 设备管理 管理   >  ****   >  **设备访问设置**。 添加包含要排除的成员的安全组，以阻止其访问Microsoft 365。 有关详细信息，请参阅创建、编辑或删除安全组[Microsoft 365 管理中心。](../../admin/email/create-edit-or-delete-a-security-group.md)|
|删除用户，以便其设备不再由基本移动性和安全性管理 |若要删除用户，请编辑具有基本移动性和安全性的设备管理策略的安全组。 有关详细信息，请参阅创建、编辑或删除安全组  [Microsoft 365 管理中心。](../../admin/email/create-edit-or-delete-a-security-group.md)<br/>若要从所有用户中删除基本移动性和安全性Microsoft 365，请参阅关闭[基本移动性和安全性](turn-off.md)。|

live (v14) 