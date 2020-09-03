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
description: 基本移动性和安全性可帮助您保护和管理移动设备。
ms.openlocfilehash: 36ea0d12becca2e97a56aceea107fa1f5bf6ded4
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336747"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>在 Microsoft 365 中管理在移动设备管理中注册的设备

内置的 Microsoft 365 移动设备管理可帮助您保护和管理用户的移动设备，如 Iphone、Ipad、Androids 和 Windows phone。 第一步是登录到 Microsoft 365 并设置基本移动性和安全性。 有关详细信息，请参阅 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)。

完成设置后，组织中的人员必须在服务中注册其设备。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device-using-basic-mobility-and-security.md)。然后，您可以使用基本移动性和安全性来帮助管理组织中的设备。 例如，可以使用设备安全策略来帮助限制电子邮件访问或其他服务、查看设备报告和远程擦除设备。 您通常会转到安全 & 合规中心来执行这些任务。 有关详细信息，请参阅 [Microsoft 365 合规性中心](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)。

## <a name="device-management-tasks"></a>设备管理任务

若要转到 "设备管理" 面板，请按照以下步骤操作：

1. 转到 [Microsoft 365 管理中心](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)。
    
2. 在 "搜索" 字段中键入移动设备管理，并从结果列表中选择 "**移动设备管理**"   。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="移动设备管理选项":::

3. 选择 "  **管理设备**"。

## <a name="manage-mobile-devices"></a>管理移动设备
    
在建立了基本的移动性和安全性之后，可以通过以下几种方法来管理组织中的移动设备。

|**若要实现此目的**|**执行操作**|
|:----------------|:------------------------------------------------------------------------------|
|擦除设备 |在 "设备管理" 面板中，选择 " *设备名称*"，然后选择 "  **完全擦除**"   以删除所有信息或  **选择性擦除**   以仅删除设备上的组织信息。 有关详细信息，请参阅 [在基本移动和安全中擦除移动设备](wipe-mobile-device.md)。|
|阻止不受支持的设备使用 Exchange ActiveSync 访问 Exchange 电子邮件 |在 "设备管理" 面板中，选择 "  **阻止**"。 |
|设置设备策略，如密码要求和安全设置 |在 "设备管理" 面板中，选择 "**设备安全策略**   >  **添加 +**"。 有关详细信息，请参阅 [在基本移动性和安全性中创建设备安全策略](create-device-security-policies-in-basic-mmobility-and-security.md)。|
|查看阻止的设备列表  |在 "设备管理" 面板中的 "  **选择视图**" 下，选择 "已     **阻止**"。 |
|解除阻止单个用户或一组用户的不相容或不受支持的设备  |选择下列选项之一以取消阻止设备：<br/>-从应用了策略的安全组中删除一个或一组用户。 转到 "Microsoft 365 管理中心" > **组**，然后选择 "组名称"。 选择 " **编辑成员和管理员**"。<br/>-从设备策略中删除用户所属的安全组。 转到 security & 合规性中心 > **安全策略**   >  **设备安全策略**。 选择 "设备策略名称"，然后选择 "**编辑**  >  **部署**"。<br/>-取消阻止设备策略的所有不符合设备。 转到 security & 合规性中心 > **安全策略**   >  **设备安全策略**。 选择 "设备策略名称"，然后选择 "**编辑**  >  **访问要求**"。 选择 "  **允许访问和报告冲突**"。<br/>-若要取消阻止某个用户或一组用户的不符合或不受支持的设备，请转到 security & 合规性中心 > **安全策略**   >  **设备管理**   >  **管理设备访问设置**。 将包含要排除的成员的安全组添加到 Microsoft 365 的阻止访问权限中。 有关详细信息，请参阅 [在 Microsoft 365 管理中心中创建、编辑或删除安全组](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)。|
|获取组织中设备的详细信息  |有关详细信息，例如哪些设备已注册且符合设备安全策略，请参阅 [获取有关基本移动和安全托管设备的详细信息](get-details-about-basic-mobility-and-security-managed-devices.md)。|
|删除用户，使其设备不再受基本移动性和安全性管理 |若要删除用户，请编辑具有设备管理策略的安全组，以实现基本移动性和安全性。 有关详细信息，请参阅  [在 Microsoft 365 管理中心中创建、编辑或删除安全组](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)。<br/>若要从所有 Microsoft 365 用户中删除基本的移动性和安全性，请参阅 [关闭基本移动性和安全性](turn-off-basic-mobility-and-security.md)。|

Live (v14) 