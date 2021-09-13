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
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59169891"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>为 iOS 设备创建 APNs 证书

若要在基本移动性和安全性中管理 iOS 设备（如 iPad 和 iPhone），请创建 APNs 证书。

1. 登录以Microsoft 365全局管理员帐户登录。

2. 在浏览器中，键入  <https://protection.office.com/> 。

3. 选择  **"数据丢失防护**   >  **""设备管理"，** 然后选择 **"适用于 iOS 设备的 APNs 证书"。**

4. 在"Apple 推送通知证书设置页上，选择"下一 **步"。**

5. 选择"下载 CSR 文件"，将证书签名请求保存到计算机上将记住的某个位置。 选择"  **下一步"。**

6. 在"创建 APNs 证书"页上：

    1. 选择 Apple APNS 门户以打开 Apple 推送证书门户。

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. 选择  **"创建证书**   "并接受使用条款。

    4. 浏览到您从 Microsoft 365 下载到计算机的证书签名请求，然后选择 **"Upload"。**

       将 Apple Push Certificate Portal 创建的 APNs 证书下载到您的计算机。

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. 返回到"Microsoft 365"，然后选择"下一步   "，Upload"APNS  **证书**   "页面。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. 选择"  **完成"。**

若要完成设置，请返回到安全与&中心> **安全策略"** 设备管理   >  ****   >  **""管理设置"。**
