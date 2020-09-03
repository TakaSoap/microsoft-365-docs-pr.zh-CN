---
title: 在基本移动性和安全性中管理设备访问设置
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
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336735"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a>在基本移动性和安全性中管理设备访问设置

如果使用的是基本移动性和安全性，则可能存在无法使用基本移动性和安全性进行管理的设备。 如果是这样，则应阻止 Exchange ActiveSync 应用程序访问 Microsoft 365 电子邮件，以获取基本移动性和安全性不受支持的移动设备。 这有助于在更多设备上保护组织信息。

请按照以下步骤操作：

1. 使用全局管理员帐户登录到 Microsoft 365。
    
2. 在浏览器中，键入：  [https://protection.office.com](https://protection.office.com/) 。    

    >[!IMPORTANT]
    >如果这是你第一次使用 MDM for Microsoft 365 商业标准，请在此处激活： [激活移动设备管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。 激活后，使用 [Office 365 安全性管理设备 & 合规性](https://protection.office.com/)。

3. 转到 "数据丢失防护" > **设备管理**   > " **设备策略**，然后选择" **管理组织范围的设备访问设置**"。
    
4. 选择 " **阻止**"。

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本移动性和安全块访问复选框":::

5. 选择 " **保存**"。 

若要了解基本移动性和安全性支持的设备，请参阅 [基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)。