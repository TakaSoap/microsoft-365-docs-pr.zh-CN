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
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877076"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="61522-103">为 iOS 设备创建 APNs 证书</span><span class="sxs-lookup"><span data-stu-id="61522-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="61522-104">若要在基本移动性和安全性中管理 iOS 设备（如 iPad 和 iPhone），请创建 APNs 证书。</span><span class="sxs-lookup"><span data-stu-id="61522-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="61522-105">Sign in to Microsoft 365 with your global admin account.</span><span class="sxs-lookup"><span data-stu-id="61522-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="61522-106">在浏览器中，键入  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="61522-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="61522-107">选择  **"数据丢失防护**   >  **""设备管理**"，然后选择"**适用于 iOS 设备的 APNs 证书"。**</span><span class="sxs-lookup"><span data-stu-id="61522-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="61522-108">在"Apple 推送通知证书设置页上，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="61522-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="61522-109">选择"下载 CSR 文件"，将证书签名请求保存到计算机上将记住的某个位置。</span><span class="sxs-lookup"><span data-stu-id="61522-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="61522-110">选择"  **下一步"。**</span><span class="sxs-lookup"><span data-stu-id="61522-110">Select  **Next**.</span></span>

6. <span data-ttu-id="61522-111">在"创建 APNs 证书"页上：</span><span class="sxs-lookup"><span data-stu-id="61522-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="61522-112">选择 Apple APNS 门户以打开 Apple 推送证书门户。</span><span class="sxs-lookup"><span data-stu-id="61522-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="61522-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="61522-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="61522-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="61522-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="61522-116">选择  **"创建证书**   "并接受使用条款。</span><span class="sxs-lookup"><span data-stu-id="61522-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="61522-117">浏览到从 Microsoft 365 下载到计算机的证书签名请求，然后选择 **"Upload"。**</span><span class="sxs-lookup"><span data-stu-id="61522-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="61522-118">将 Apple Push Certificate Portal 创建的 APNs 证书下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="61522-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="61522-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="61522-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="61522-120">返回到"Microsoft 365"，然后选择"下一步     **"，Upload"APNS 证书**   "页面。</span><span class="sxs-lookup"><span data-stu-id="61522-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="61522-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="61522-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="61522-122">选择"  **完成"。**</span><span class="sxs-lookup"><span data-stu-id="61522-122">Select  **Finish**.</span></span>

<span data-ttu-id="61522-123">若要完成设置，请返回到安全与&中心 **>"设备** 管理   >  \*\*\*\*   >  **""管理设置"。**</span><span class="sxs-lookup"><span data-stu-id="61522-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
