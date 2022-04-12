---
title: 在基本移动性和安全性中擦除移动设备
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
description: 使用内置的基本移动性和安全性从已注册的设备中删除信息。
ms.openlocfilehash: 932380b735e3fea2543832417e7911e9216f70fc
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780778"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>在基本移动性和安全性中擦除移动设备

可以使用内置的基本移动性和安全性来Microsoft 365仅删除组织信息，或执行工厂重置以从移动设备中删除所有信息并将其还原到工厂设置。

## <a name="before-you-begin"></a>准备工作

移动设备可以存储敏感的组织信息，并提供对组织Microsoft 365资源的访问权限。 若要帮助保护组织的信息，可以执行工厂重置或删除公司数据：

- **工厂重置**：删除用户移动设备上的所有数据，包括已安装的应用程序、照片和个人信息。 擦除完成后，设备将还原到其出厂设置。

- **删除公司数据**：仅删除组织数据，并在用户的移动设备上留下已安装的应用程序、照片和个人信息。

- **(工厂重置或删除公司数据) 擦除设备时**，设备将从托管设备列表中删除。

- **自动重置设备**：可以设置基本移动性和安全性策略，在用户尝试输入设备密码的特定次数失败后，自动对设备进行出厂重置。 为此，请按照 [基本移动性和安全性中的“创建设备安全策略”中的](create-device-security-policies.md)步骤进行操作。

- **如果想要在擦除其设备时了解用户体验**，请参阅 [用户和设备的影响是什么？](#whats-the-user-and-device-impact)

## <a name="wipe-a-mobile-device"></a>擦除移动设备

1. 转到[Microsoft 365 管理中心](../../admin/admin-overview/about-the-admin-center.md)。

2. 在搜索字段中键入移动设备管理，然后从结果列表中选择 **移动设备管理**。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本移动性和 Secruity 移动设备管理选项。":::

3. 选择 **“管理设备**”。

4. 选择要擦除的设备。

5. 选择 **“管理**”。

6. 选择要执行的远程擦除类型。

    - 若要执行完全擦除并将设备还原到其出厂设置，请选择 **“工厂重置**”。
    - 若要执行选择性擦除并仅删除Microsoft 365组织信息，请选择 **“删除公司数据**”。
    - 若要从组织中删除设备，请选择 **“删除设备**”。

7. 选择“**是**”进行确认。

## <a name="how-do-i-know-it-worked"></a>如何实现知道它有效吗？

你将不再在托管设备列表中看到移动设备。

## <a name="why-would-you-want-to-wipe-a-device"></a>为什么要擦除设备？

出于以下原因擦除设备：

- 智能手机和平板电脑等移动设备正变得越来越功能齐全。 这意味着用户可以更轻松地存储敏感的公司信息，例如个人身份识别或机密通信，并在外出时访问它。 如果其中一个移动设备丢失或被盗，擦除设备有助于防止组织的信息最终落入坏人之手。
- 当用户使用在基本移动性和安全性中注册的个人设备离开组织时，可以通过执行工厂重置来帮助防止组织信息与该用户一起使用。
- 如果组织向用户提供移动设备，则可能需要不时重新分配设备。 在将设备分配给新用户之前对设备执行工厂重置可帮助确保删除来自前所有者的任何敏感信息。

## <a name="whats-the-user-and-device-impact"></a>用户和设备有什么影响？

擦除会立即发送到移动设备，并且设备在 Azure Active Directory 中标记为不符合。 当设备重置为出厂默认值时，将删除所有数据，但下表描述了删除公司数据时，每个设备类型删除的内容。

|内容影响|iOS|Android|
|---|---|---|
|如果设备受应用保护策略Intune保护，则Microsoft 365应用数据会擦除。 不会删除这些应用。 对于不受移动应用程序管理 (MAM) 策略保护的设备，Outlook和OneDrive不会删除缓存的数据。<br/>**注意** 若要应用Intune 应用保护策略，必须具有Intune许可证。|是|是|
|不再强制执行基本移动性和安全性应用于设备的策略设置;用户可以更改设置。|是|是|
|基本移动性和安全性创建的电子邮件配置文件将被删除，设备上的缓存电子邮件将被删除。|是|不适用|

> [!NOTE]
> 公司门户应用在适用于 iOS 的App Store和适用于 Android 设备的 Play 应用商店中可用。
