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
description: 尝试以下步骤来跟踪基本移动性和安全性问题
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876848"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="8911a-103">基本移动性和安全性疑难解答</span><span class="sxs-lookup"><span data-stu-id="8911a-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="8911a-104">如果在尝试在基本移动性和安全性中注册设备时出现问题，请尝试此处的步骤来跟踪该问题。</span><span class="sxs-lookup"><span data-stu-id="8911a-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="8911a-105">如果常规步骤无法修复该问题，请参阅以下部分之一，了解设备类型的特定步骤。</span><span class="sxs-lookup"><span data-stu-id="8911a-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="8911a-106">首先尝试的步骤</span><span class="sxs-lookup"><span data-stu-id="8911a-106">Steps to try first</span></span>

<span data-ttu-id="8911a-107">若要开始，请检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="8911a-107">To start, check the following:</span></span>

- <span data-ttu-id="8911a-108">确保设备尚未向另一个移动设备管理提供程序（如 Intune）注册。</span><span class="sxs-lookup"><span data-stu-id="8911a-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="8911a-109">确保设备已设置为正确的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8911a-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="8911a-110">在设备上切换到其他 WIFI 或手机网络。</span><span class="sxs-lookup"><span data-stu-id="8911a-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="8911a-111">对于 Android 或 iOS 设备，卸载并重新安装设备上的 Intune 公司门户应用。</span><span class="sxs-lookup"><span data-stu-id="8911a-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="8911a-112">iOS 手机或平板电脑</span><span class="sxs-lookup"><span data-stu-id="8911a-112">iOS phone or tablet</span></span>

- <span data-ttu-id="8911a-113">请确保你已设置 APN 证书。</span><span class="sxs-lookup"><span data-stu-id="8911a-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="8911a-114">有关详细信息，请参阅为 [iOS 设备创建 APNs 证书](create-an-apns-certificate-for-ios-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="8911a-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="8911a-115">在 **"**   >  **设置**   >  **常规 (或设备**) 中，确保尚未安装管理配置文件。</span><span class="sxs-lookup"><span data-stu-id="8911a-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="8911a-116">如果是，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="8911a-116">If it is, remove it.</span></span>

- <span data-ttu-id="8911a-117">如果看到错误消息"设备注册失败"，请登录到 Microsoft 365，并确保已将包含 Exchange Online 的许可证分配给登录设备的用户。</span><span class="sxs-lookup"><span data-stu-id="8911a-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="8911a-118">如果看到错误消息"配置文件安装失败"，请尝试以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="8911a-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="8911a-119">确保 Safari 是设备上的默认浏览器，并且未禁用 Cookie。</span><span class="sxs-lookup"><span data-stu-id="8911a-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="8911a-120">重新启动设备，然后导航到portal.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="8911a-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="8911a-121">使用 Microsoft 365 用户 ID 和密码登录，并尝试手动安装配置文件。</span><span class="sxs-lookup"><span data-stu-id="8911a-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="8911a-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="8911a-122">Windows RT</span></span>

- <span data-ttu-id="8911a-123">请确保你的域在 Microsoft 365 中设置为使用基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="8911a-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="8911a-124">有关详细信息，请参阅"[设置基本移动性和安全性"。](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="8911a-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="8911a-125">确保用户选择"打开 \*\*\*\*   "，而不是选择" **加入"。**</span><span class="sxs-lookup"><span data-stu-id="8911a-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="8911a-126">Windows 10 电脑</span><span class="sxs-lookup"><span data-stu-id="8911a-126">Windows 10 PC</span></span>

- <span data-ttu-id="8911a-127">请确保你的域在 Microsoft 365 中设置为使用基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="8911a-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="8911a-128">有关详细信息，请参阅["设置基本移动性和安全性"。](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="8911a-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="8911a-129">除非你拥有 Azure Active Directory Premium，否则请确保用户 **仅选择"** 在设备管理中注册   "，而不是选择 **"连接"。**</span><span class="sxs-lookup"><span data-stu-id="8911a-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="8911a-130">Android 手机或平板电脑</span><span class="sxs-lookup"><span data-stu-id="8911a-130">Android phone or tablet</span></span>

- <span data-ttu-id="8911a-131">确保设备运行的是 Android 4.4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8911a-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="8911a-132">确保 Chrome 是最新的，并设置为默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="8911a-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="8911a-133">如果看到错误消息"我们无法注册此设备"，请登录到 Microsoft 365，并确保已将包含 Exchange Online 的许可证分配给登录设备的用户。</span><span class="sxs-lookup"><span data-stu-id="8911a-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="8911a-134">检查设备上的通知区域以查看任何所需的最终用户操作是否挂起，如果挂起，则完成这些操作。</span><span class="sxs-lookup"><span data-stu-id="8911a-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>