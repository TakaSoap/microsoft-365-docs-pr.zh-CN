---
title: 在 macOS 设备上注册 Microsoft Defender for Endpoint 到 Jamf Pro
description: 在 macOS 设备上注册 Microsoft Defender for Endpoint 到 Jamf Pro
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， 部署， 卸载， intune， jamfpro， macos， catalina， mojave， high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0fa0db3ba85ff003d91b43d06c709ab66c37ce02
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933093"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="48f79-104">在 macOS 设备上注册 Microsoft Defender for Endpoint 到 Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="48f79-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="48f79-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="48f79-105">**Applies to:**</span></span>
- [<span data-ttu-id="48f79-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="48f79-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="48f79-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48f79-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="48f79-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="48f79-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48f79-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="48f79-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="48f79-110">注册 macOS 设备</span><span class="sxs-lookup"><span data-stu-id="48f79-110">Enroll macOS devices</span></span>

<span data-ttu-id="48f79-111">有多种方法注册 JamF。</span><span class="sxs-lookup"><span data-stu-id="48f79-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="48f79-112">本文将指导你采用两种方法：</span><span class="sxs-lookup"><span data-stu-id="48f79-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="48f79-113">方法 1：注册邀请</span><span class="sxs-lookup"><span data-stu-id="48f79-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="48f79-114">方法 2：Prestage 注册</span><span class="sxs-lookup"><span data-stu-id="48f79-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="48f79-115">有关完整列表，请参阅关于 [计算机注册](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)。</span><span class="sxs-lookup"><span data-stu-id="48f79-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="48f79-116">注册方法 1：注册邀请</span><span class="sxs-lookup"><span data-stu-id="48f79-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="48f79-117">在 Jamf Pro仪表板中，导航到"**注册邀请"。**</span><span class="sxs-lookup"><span data-stu-id="48f79-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![配置设置的图像1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="48f79-119">选择 **+ 新建**。</span><span class="sxs-lookup"><span data-stu-id="48f79-119">Select **+ New**.</span></span>

    ![自动生成的说明徽标特写](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="48f79-121">在 **"为邀请指定** 收件人>电子邮件地址"下，输入收件人 (电子邮件地址) 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="48f79-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![配置设置的图像2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![配置设置的图像3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="48f79-124">例如：janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="48f79-124">For example: janedoe@contoso.com</span></span>

    ![配置设置的图像4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="48f79-126">为邀请配置邮件。</span><span class="sxs-lookup"><span data-stu-id="48f79-126">Configure the message for the invitation.</span></span>

    ![配置设置的图像5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![配置设置的图像6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![配置设置的图像7](images/3ced5383a6be788486d89d407d042f28.png)

    ![配置设置的图像8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="48f79-131">注册方法 2：预阶段注册</span><span class="sxs-lookup"><span data-stu-id="48f79-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="48f79-132">在 Jamf Pro仪表板中，导航到 **Prestage 注册**。</span><span class="sxs-lookup"><span data-stu-id="48f79-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![配置设置的图像9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="48f79-134">按照 Computer [PreStage Enrollments 中的说明操作](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)。</span><span class="sxs-lookup"><span data-stu-id="48f79-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="48f79-135">注册 macOS 设备</span><span class="sxs-lookup"><span data-stu-id="48f79-135">Enroll macOS device</span></span>

1. <span data-ttu-id="48f79-136">选择 **"继续** "，然后从"系统首选项" **窗口安装 CA** 证书。</span><span class="sxs-lookup"><span data-stu-id="48f79-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Jamf 注册Pro图像1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="48f79-138">安装 CA 证书后，返回到浏览器窗口，然后选择" **继续** "并安装 MDM 配置文件。</span><span class="sxs-lookup"><span data-stu-id="48f79-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Jamf 注册Pro图像2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="48f79-140">选择 **允许** 从 JAMF 下载。</span><span class="sxs-lookup"><span data-stu-id="48f79-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Jamf 注册Pro图像3](images/jamfpro-download.png)

4. <span data-ttu-id="48f79-142">选择 **"** 继续"继续安装 MDM 配置文件。</span><span class="sxs-lookup"><span data-stu-id="48f79-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Jamf 注册Pro图像4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="48f79-144">选择 **"继续** "以安装 MDM 配置文件。</span><span class="sxs-lookup"><span data-stu-id="48f79-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Jamf 注册Pro图像5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="48f79-146">选择 **"继续**  "以完成配置。</span><span class="sxs-lookup"><span data-stu-id="48f79-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Jamf 注册Pro图像6](images/jamfpro-mdm-profile.png)
