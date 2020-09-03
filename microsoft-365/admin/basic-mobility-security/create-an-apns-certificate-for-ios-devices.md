---
title: 为 iOS 设备创建 APNs 证书
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: 在基本移动性和安全性中管理 iOS 设备。
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336757"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>为 iOS 设备创建 APNs 证书

若要在基本移动性和安全性中管理 iOS 设备（如 Ipad 和 Iphone），请创建 APNs 证书。

1. 使用全局管理员帐户登录到 Microsoft 365。
    
2. 在浏览器中，键入  [https://protection.office.com](https://protection.office.com/) 。
    
3. 选择 " **数据丢失防护**   >  **设备管理**"，并**为 iOS 设备选择 APNs 证书**。    

4. 在 "Apple 推送通知证书设置" 页上，选择 " **下一步**"。
    
5. 选择 "下载你的 CSR 文件"，并将证书签名请求保存到你将记住的计算机上的某个位置。 选择 "  **下一步**"。
    
6. 在 "创建 APNs 证书" 页上：  

    1. 选择 "Apple APNS 门户" 打开 "Apple 推送证书" 门户。
    
    2. Sign in with an Apple ID.   

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. 选择 "  **创建证书**"   并接受 "使用条款"。
    
    4. 浏览到从 Microsoft 365 下载到您的计算机的证书签名请求，然后选择 " **上传**"。
    
        将 Apple 推送证书门户创建的 APNs 证书下载到您的计算机。
    
       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. 返回到 Microsoft 365，然后选择 "**下一步**   "，转到 "  **上载 APNS 证书**"   页面。
    
8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
9. 选择 "  **完成**"。
    
若要完成安装，请返回到安全 & 合规性中心 > **安全策略**   >  **设备管理**   >  **管理设置**。
