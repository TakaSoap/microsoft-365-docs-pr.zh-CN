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
description: 使用内置的"基本移动性和安全性"从已注册的设备中删除信息。
ms.openlocfilehash: d5f610e2a9180f1d147f68e6aabf4a7291787033
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400164"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>在基本移动性和安全性中擦除移动设备

可以使用内置的 Microsoft 365 基本移动性和安全性来仅删除组织信息，或执行出厂重置以从移动设备中删除所有信息，并还原到出厂设置。

## <a name="before-you-begin"></a>开始之前

移动设备可以存储敏感的组织信息，并提供对组织资源Microsoft 365的访问权限。 为了帮助保护组织的信息，可以执行"恢复出厂设置"或"删除公司数据"操作：

- **恢复** 出厂设置：删除用户移动设备上的所有数据，包括已安装的应用程序、照片和个人信息。 擦除完成后，设备将还原到出厂设置。

- **删除公司数据**：仅删除组织数据，并保留用户的移动设备上已安装的应用程序、照片和个人信息。

- **在恢复出厂 (** 或删除公司数据) 擦除设备时，设备将从托管设备列表中删除。
    
- **自动重置设备**：可以设置基本移动性和安全策略，在用户尝试输入设备密码特定次数失败后自动恢复设备出厂设置。 为此，请按照 [Create device security policies in basic mobility and security中的步骤操作](create-device-security-policies.md)。
    
- **如果你希望了解擦除** 其设备的用户体验，请参阅   [用户和设备的影响是什么？](#whats-the-user-and-device-impact)。

## <a name="wipe-a-mobile-device"></a>擦除移动设备

1. 转到 [Microsoft 365 管理中心。](../../admin/admin-overview/about-the-admin-center.md)

2. 在搜索字段中键入"移动设备管理"，然后从结果列表中选择"移动设备管理"。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本移动性和安全移动设备管理选项。":::

3. 选择 **"管理设备"**。

4. 选择要擦除的设备。

5. 选择" **管理"**。

6. 选择要执行的远程擦除类型。

    - 若要执行完全擦除，将设备还原到出厂设置，请选择"恢复 **出厂设置"**。
    - 若要仅对组织信息执行选择性擦除Microsoft 365，请选择"**删除公司数据"**。
    - 若要从组织中删除设备，请选择" **删除设备"**。

7. 选择“**是**”进行确认。

## <a name="how-do-i-know-it-worked"></a>我如何知道它有效？

您不再在托管设备列表中看到移动设备。

## <a name="why-would-you-want-to-wipe-a-device"></a>为什么你想要擦除设备？

由于以下原因，擦除设备：

- 智能手机和平板电脑等移动设备功能越来越全面。 这意味着用户能够更轻松地存储敏感的公司信息（如个人标识或机密通信）并同时访问这些信息。 如果其中一个移动设备丢失或被盗，则擦除设备有助于防止组织的信息最终被误用。
- 当用户使用注册基本移动性和安全性的个人设备离开组织时，可以通过执行出厂重置来帮助防止组织信息与该用户一起访问。
- 如果你的组织为用户提供移动设备，你可能需要时时重新分配设备。 在将设备分配给新用户之前，在设备上执行出厂重置可帮助确保删除以前所有者的任何敏感信息。

## <a name="whats-the-user-and-device-impact"></a>用户和设备有什么影响？

擦除将立即发送到移动设备，并且设备在 Azure Active Directory 中标记为不兼容。 当设备重置为出厂默认设置时，会删除所有数据，但下表介绍了在设备删除公司数据时，将删除每种设备类型的内容。

|**内容影响**|**iOS**|**Android**|
|:-----|:-----|:-----|
|Microsoft 365受 Intune 应用保护策略保护，则擦除应用数据。 不会删除这些应用。 对于不受移动应用程序管理保护的设备 (MAM) 策略，Outlook OneDrive不会删除缓存数据。<br/>**注意** 要应用 Intune 应用保护策略，你必须拥有 Intune 许可证。|是|是|
|不再强制执行基本移动性和安全性应用于设备的策略设置;用户可以更改设置。|是|是|
|将删除由基本移动性和安全性创建的电子邮件配置文件，并删除设备上缓存的电子邮件。|是|不适用|

> [!NOTE]
> 公司门户应用在适用于 iOS 的应用商店和适用于 Android 设备的 Play 应用商店中提供。
