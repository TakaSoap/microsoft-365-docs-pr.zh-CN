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
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="987aa-103">为 iOS 设备创建 APNs 证书</span><span class="sxs-lookup"><span data-stu-id="987aa-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="987aa-104">若要在基本移动性和安全性中管理 iOS 设备（如 Ipad 和 Iphone），请创建 APNs 证书。</span><span class="sxs-lookup"><span data-stu-id="987aa-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="987aa-105">使用全局管理员帐户登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="987aa-105">Sign in to Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="987aa-106">在浏览器中，键入  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="987aa-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>
    
3. <span data-ttu-id="987aa-107">选择 " **数据丢失防护**   >  **设备管理**"，并**为 iOS 设备选择 APNs 证书**。</span><span class="sxs-lookup"><span data-stu-id="987aa-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>    

4. <span data-ttu-id="987aa-108">在 "Apple 推送通知证书设置" 页上，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="987aa-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>
    
5. <span data-ttu-id="987aa-109">选择 "下载你的 CSR 文件"，并将证书签名请求保存到你将记住的计算机上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="987aa-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="987aa-110">选择 "  **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="987aa-110">Select  **Next**.</span></span>
    
6. <span data-ttu-id="987aa-111">在 "创建 APNs 证书" 页上：</span><span class="sxs-lookup"><span data-stu-id="987aa-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="987aa-112">选择 "Apple APNS 门户" 打开 "Apple 推送证书" 门户。</span><span class="sxs-lookup"><span data-stu-id="987aa-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    
    2. <span data-ttu-id="987aa-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="987aa-113">Sign in with an Apple ID.</span></span>   

    >[!IMPORTANT]
    ><span data-ttu-id="987aa-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="987aa-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="987aa-116">选择 "  **创建证书**"   并接受 "使用条款"。</span><span class="sxs-lookup"><span data-stu-id="987aa-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>
    
    4. <span data-ttu-id="987aa-117">浏览到从 Microsoft 365 下载到您的计算机的证书签名请求，然后选择 " **上传**"。</span><span class="sxs-lookup"><span data-stu-id="987aa-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>
    
        <span data-ttu-id="987aa-118">将 Apple 推送证书门户创建的 APNs 证书下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="987aa-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>
    
       >[!TIP]
       ><span data-ttu-id="987aa-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="987aa-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="987aa-120">返回到 Microsoft 365，然后选择 "**下一步**   "，转到 "  **上载 APNS 证书**"   页面。</span><span class="sxs-lookup"><span data-stu-id="987aa-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>
    
8. <span data-ttu-id="987aa-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="987aa-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
9. <span data-ttu-id="987aa-122">选择 "  **完成**"。</span><span class="sxs-lookup"><span data-stu-id="987aa-122">Select  **Finish**.</span></span>
    
<span data-ttu-id="987aa-123">若要完成安装，请返回到安全 & 合规性中心 > **安全策略**   >  **设备管理**   >  **管理设置**。</span><span class="sxs-lookup"><span data-stu-id="987aa-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
