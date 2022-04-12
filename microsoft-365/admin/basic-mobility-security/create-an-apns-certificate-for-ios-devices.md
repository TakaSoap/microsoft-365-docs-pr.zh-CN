---
title: 为 iOS 设备创建 APNs 证书
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: 在基本移动性和安全性中管理 iOS 设备。
ms.openlocfilehash: 99aa909bf9adab1464ad3858cfac4a04cc541609
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64781152"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>为 iOS 设备创建 APNs 证书

若要在基本移动性和安全性中管理 iOS 设备，例如 iPad 和 iPhone，请创建 APN 证书。

1. 使用全局管理员帐户登录到Microsoft 365。

2. 在浏览器中，键入 <https://protection.office.com/>。

3. 选择 **数据丢失防护** \> **设备管理**，并选择 **适用于 iOS 设备的 APN 证书**。

4. 在 Apple 推送通知证书设置页上，选择 **“下一步**”。

5. 选择“下载 CSR 文件”，并将证书签名请求保存到计算机上你将记住的某个位置。 选择 **下一步**。

6. 在“创建 APN 证书”页上：

    1. Select Apple APNS Portal to open the Apple Push Certificates Portal. 

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. 选择 **“创建证书** ”并接受使用条款。

    4. 浏览到从Microsoft 365下载到计算机的证书签名请求，然后选择 **Upload**。

       将 Apple Push Certificate Portal 创建的 APN 证书下载到计算机。

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. 返回Microsoft 365，然后选择 **“下一步**”转到 **Upload APNS 证书** 页。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. 选择 **“完成”**。

若要完成设置，请返回到安全&合规中心\>**安全策略** \> **设备管理** \> **管理设置**。
