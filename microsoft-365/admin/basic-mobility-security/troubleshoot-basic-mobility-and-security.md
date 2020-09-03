---
title: 基本移动性和安全性疑难解答
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
description: 请尝试执行以下步骤来跟踪基本移动性和安全问题
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336746"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="3c8bf-103">基本移动性和安全性疑难解答</span><span class="sxs-lookup"><span data-stu-id="3c8bf-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="3c8bf-104">如果您在尝试以基本移动性和安全性注册设备时遇到问题，请尝试此处的步骤来跟踪问题。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="3c8bf-105">如果常规步骤不能解决问题，请参阅后面的部分，其中包含针对你的设备类型的特定步骤。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="3c8bf-106">首先尝试的步骤</span><span class="sxs-lookup"><span data-stu-id="3c8bf-106">Steps to try first</span></span>

<span data-ttu-id="3c8bf-107">若要开始，请检查以下各项：</span><span class="sxs-lookup"><span data-stu-id="3c8bf-107">To start, check the following:</span></span>

- <span data-ttu-id="3c8bf-108">确保设备尚未使用其他移动设备管理提供程序（如 Intune）进行注册。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="3c8bf-109">请确保该设备已设置为正确的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="3c8bf-110">切换到设备上的不同 WIFI 或蜂窝网络。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="3c8bf-111">对于 Android 或 iOS 设备，请在设备上卸载并重新安装 Intune 公司门户应用。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="3c8bf-112">iOS 电话或平板电脑</span><span class="sxs-lookup"><span data-stu-id="3c8bf-112">iOS phone or tablet</span></span>

- <span data-ttu-id="3c8bf-113">请确保已设置 APNs 证书。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="3c8bf-114">有关详细信息，请参阅 [Create a APNs Certificate For iOS 设备](create-an-apns-certificate-for-ios-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="3c8bf-115">在 " **设置**   >  **常规**   >  \*\*配置文件 (" 或 "设备管理) \*\*" 中，确保尚未安装管理配置文件。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="3c8bf-116">如果是，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="3c8bf-117">如果您看到错误消息 "设备未能注册"，请登录 Microsoft 365，并确保已将包含 Exchange Online 的许可证分配给登录到该设备的用户。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="3c8bf-118">如果您看到错误消息 "配置文件无法安装"，请尝试以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="3c8bf-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="3c8bf-119">请确保 Safari 是设备上的默认浏览器，并且未禁用该 cookie。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="3c8bf-120">重新启动设备，然后导航到 portal.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="3c8bf-121">使用 Microsoft 365 用户 ID 和密码登录，并尝试手动安装配置文件。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="3c8bf-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="3c8bf-122">Windows RT</span></span>

- <span data-ttu-id="3c8bf-123">确保您的域已在 Microsoft 365 中设置为使用基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="3c8bf-124">有关详细信息，请参阅 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-124">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="3c8bf-125">确保用户选择 " **打开"**，   而不是选择 " **加入**"。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="3c8bf-126">Windows 10 电脑</span><span class="sxs-lookup"><span data-stu-id="3c8bf-126">Windows 10 PC</span></span>

- <span data-ttu-id="3c8bf-127">确保您的域已在 Microsoft 365 中设置为使用基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="3c8bf-128">有关详细信息，请参阅 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-128">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="3c8bf-129">除非您拥有 Azure Active Directory Premium，否则请确保用户 **只选择 "在设备管理中注册"**，   而不是选择 " **连接**"。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="3c8bf-130">Android 手机或平板电脑</span><span class="sxs-lookup"><span data-stu-id="3c8bf-130">Android phone or tablet</span></span>

- <span data-ttu-id="3c8bf-131">请确保设备运行的是 Android 4.4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="3c8bf-132">请确保 Chrome 是最新的，并且设置为默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="3c8bf-133">如果您看到错误消息 "我们无法注册此设备"，请登录 Microsoft 365，并确保已将包含 Exchange Online 的许可证分配给登录到该设备的用户。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="3c8bf-134">检查设备上的通知区域以查看是否有任何必需的最终用户操作挂起，如果是，则完成操作。</span><span class="sxs-lookup"><span data-stu-id="3c8bf-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>