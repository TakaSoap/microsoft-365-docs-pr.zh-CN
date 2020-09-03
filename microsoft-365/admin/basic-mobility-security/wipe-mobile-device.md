---
title: 在基本移动和安全性中擦除移动设备
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
description: 使用内置的基本移动性和安全性从已注册的设备中删除信息。
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336739"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>在基本移动和安全性中擦除移动设备

可以使用 Microsoft 365 的内置基本移动性和安全性来仅删除组织信息，或执行恢复出厂设置以删除移动设备中的所有信息并将其还原为出厂设置。

## <a name="before-you-begin"></a>准备工作

移动设备可以存储敏感的组织信息，并提供对组织的 Microsoft 365 资源的访问权限。 为了帮助保护您的组织的信息，您可以执行原始重置或删除公司数据：
    
- **出厂重置**：删除用户移动设备上的所有数据，包括已安装的应用程序、照片和个人信息。 擦除完成后，设备将还原为其出厂设置。
    
- **删除公司数据**：仅删除组织数据并将安装的应用程序、照片和个人信息保留在用户的移动设备上。   

- **擦除设备 (出厂重置或删除公司数据) 时 **，设备将从受管理的设备列表中删除。
    
- **自动重置设备**：您可以设置基本移动性和安全策略，以便在用户未成功输入设备密码一段特定次数后自动出厂时重置设备。 为此，请按照 " [基本移动性和安全性" 中的创建设备安全策略](create-device-security-policies-in-basic-mmobility-and-security.md)中的步骤操作。
    
- 如果想要在擦除设备时**知道用户体验**，请参阅  [用户和设备影响是什么？](#whats-the-user-and-device-impact)。   

## <a name="wipe-a-mobile-device"></a>擦除移动设备

1. 转到 [Microsoft 365 管理中心](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)。
    
2. 在 "搜索" 字段中键入移动设备管理，并从结果列表中选择 " **移动设备管理** "。 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本移动性和 Secruity 移动设备管理选项":::

3. 选择 " **管理设备**"。

4. 选择要擦除的设备。

5. 选择 " **管理**"。

6. 选择要执行的远程擦除类型。

    - 若要执行完全擦除并将设备还原到其出厂设置，请选择 "恢复 **出厂**设置"。
    - 若要执行选择性擦除并仅删除 Microsoft 365 组织信息，请选择 " **删除公司数据**"。
    - 若要从组织中删除设备，请选择 " **删除设备**"。

7. 选择“**是**”进行确认。

## <a name="how-do-i-know-it-worked"></a>我如何知道它已正常工作？

在受管理的设备列表中，您将不会再看到该移动设备。

## <a name="why-would-you-want-to-wipe-a-device"></a>为什么要擦除设备？

由于以下原因，请擦除设备：

- 像智能手机和平板电脑这样的移动设备在所有时间都变得更加完善。 这意味着，您的用户可以更轻松地存储敏感的公司信息，如个人身份标识或机密通信，并在旅途中对其进行访问。 如果其中一个移动设备丢失或被盗，则擦除设备有助于防止您的组织的信息在错误的手中终止。
- 当用户将组织的个人设备设置为使用基本移动性和安全性进行注册时，您可以通过执行恢复出厂设置来帮助防止组织信息与该用户配合使用。
- 如果您的组织向用户提供移动设备，则可能需要随时重新分配设备。 在将设备分配给新用户之前在设备上执行恢复出厂设置有助于确保删除先前所有者的所有敏感信息。

## <a name="whats-the-user-and-device-impact"></a>用户和设备的影响是什么？

擦除会立即发送到移动设备，并且设备在 Azure active directory 中被标记为不合规。 虽然在将设备重置为出厂默认值时删除了所有数据，但下表介绍了在删除公司数据时，在设备上删除的每种设备类型的内容。

|**内容 impace**|**iOS 10 及更高版本**|**Android 5 及更高版本**|
|:-----|:-----|:-----|
|如果设备受 Intune 应用保护策略保护，则会擦除 Microsoft 365 应用程序数据。 不会删除应用程序。 对于不受移动应用程序管理 (MAM) 策略保护的设备，Outlook 和 OneDrive 不会删除缓存的数据。<br/>**注释** 若要应用 Intune 应用保护策略，您必须具有 Intune 许可证。|是|是|
|基本移动性应用的策略设置和对设备的安全性不再强制实施;用户可以更改设置。|是|是|
|将删除基本移动性和安全性创建的电子邮件配置文件，并删除设备上缓存的电子邮件。|是|不适用|
>[!NOTE] 
>公司门户应用程序适用于 iOS 应用商店和 Android 设备的 Play 商店。

## <a name="related-topics"></a>相关主题

[设置基本移动性和安全性](set-up-basic-mobility-and-security.md)