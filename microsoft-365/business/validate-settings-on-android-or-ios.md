---
title: 验证 Android 或 iOS 设备上的应用保护设置
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 了解如何验证 android Microsoft 365 商业高级版 iOS 设备中的应用保护设置。
ms.openlocfilehash: a0a4a6e6cff59f66a506929e97c99d361472a68b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578059"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="d83b2-103">验证 Android 或 iOS 设备上的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="d83b2-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="d83b2-104">按照以下部分中的说明验证 Android 或 iOS 设备上的应用保护设置。</span><span class="sxs-lookup"><span data-stu-id="d83b2-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="d83b2-105">Android</span><span class="sxs-lookup"><span data-stu-id="d83b2-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="d83b2-106">检查应用保护设置在用户设备上是否正常工作</span><span class="sxs-lookup"><span data-stu-id="d83b2-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="d83b2-107">在[设置用于 Android 设备的应用配置](app-protection-settings-for-android-and-ios.md)以保护应用后，可按以下步骤验证所选设置是否有效。</span><span class="sxs-lookup"><span data-stu-id="d83b2-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="d83b2-108">首先，确保该策略适用于你要验证它的应用。</span><span class="sxs-lookup"><span data-stu-id="d83b2-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="d83b2-109">在管理 [Microsoft 365 商业高级版，](https://portal.office.com)转到"策略 **""** \> **编辑策略"。**</span><span class="sxs-lookup"><span data-stu-id="d83b2-109">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="d83b2-110">选择 **"Android 应用程序** 策略"作为你在设置时创建的设置，或选择你创建的另一个策略，并验证是否Outlook应用策略。</span><span class="sxs-lookup"><span data-stu-id="d83b2-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="d83b2-112">验证"需要 PIN 或指纹才能访问 Office 应用"</span><span class="sxs-lookup"><span data-stu-id="d83b2-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="d83b2-113">在" **编辑策略**"窗格中，选择" **Office 文档的访问控制**"旁边的" **编辑**"，展开" **管理用户如何在移动设备上访问 Office 文件**"，并确保将" **需要 PIN 或指纹才能访问 Office 应用**"设置为" **开**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![确保将"需要 PIN 或指纹来访问Office"设置为"打开"。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="d83b2-115">在用户的 Android 设备中，Outlook，然后使用用户的凭据Microsoft 365 商业高级版登录。</span><span class="sxs-lookup"><span data-stu-id="d83b2-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="d83b2-116">系统还会提示你输入 PIN 或使用指纹。</span><span class="sxs-lookup"><span data-stu-id="d83b2-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="d83b2-118">验证"超过登录失败次数限制后重置 PIN"</span><span class="sxs-lookup"><span data-stu-id="d83b2-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="d83b2-119">在"编辑策略"窗格中，选择 **"Office** 文档访问控制"旁边的"编辑"，展开"管理用户如何访问移动设备上的 **Office** 文件"，并确保"在尝试失败后重置 **PIN"** 设置为一个数字。</span><span class="sxs-lookup"><span data-stu-id="d83b2-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="d83b2-120">默认情况下为 5。</span><span class="sxs-lookup"><span data-stu-id="d83b2-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="d83b2-121">在用户的 Android 设备中，Outlook，然后使用用户的凭据Microsoft 365 商业高级版登录。</span><span class="sxs-lookup"><span data-stu-id="d83b2-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="d83b2-122">输入错误 PIN 的次数达到策略指定次数。</span><span class="sxs-lookup"><span data-stu-id="d83b2-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="d83b2-123">你将看到一条提示，指出 **"PIN 尝试限制已到达** "以重置 PIN。</span><span class="sxs-lookup"><span data-stu-id="d83b2-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="d83b2-125">按" **重置 PIN**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-125">Press **Reset PIN**.</span></span> <span data-ttu-id="d83b2-126">系统将提示你使用用户的凭据Microsoft 365 商业高级版登录，然后需要设置新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="d83b2-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="d83b2-127">验证"强制用户将所有工作文件保存到 OneDrive for Business"</span><span class="sxs-lookup"><span data-stu-id="d83b2-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="d83b2-128">在" **编辑策略**"窗格中，选择" **设备丢失或被盗防护**"旁边的" **编辑**"，展开" **设备丢失或被盗时保护工作文件**"，并确保将" **强制用户将所有工作文件保存到 OneDrive for Business**"设置为" **开**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="d83b2-130">在用户的 Android 设备上，打开Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="d83b2-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d83b2-131">打开带附件的电子邮件，然后点击附件信息旁边的向下箭头图标。</span><span class="sxs-lookup"><span data-stu-id="d83b2-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="d83b2-133">你将在屏幕 **底部看到** 无法保存到设备。</span><span class="sxs-lookup"><span data-stu-id="d83b2-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="d83b2-135">目前尚不可在 Android 上保存到 OneDrive for Business，因此仅会看到本地保存被阻止。</span><span class="sxs-lookup"><span data-stu-id="d83b2-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="d83b2-136">验证"Office 应用空闲指定时间后要求用户再次登录"</span><span class="sxs-lookup"><span data-stu-id="d83b2-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="d83b2-137">在"编辑策略"窗格中，选择 **"Office** 文档访问控制"旁边的"编辑"，展开"管理用户如何访问移动设备上的 **Office** 文件"，并确保将"要求用户在 Office 应用空闲后重新登录 **"** 设置为一定的分钟数。</span><span class="sxs-lookup"><span data-stu-id="d83b2-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="d83b2-138">默认情况下为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="d83b2-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="d83b2-139">在用户的 Android 设备上，打开Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="d83b2-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d83b2-p105">现应该会显示 Outlook 收件箱。（最低标准）30 分钟不触碰 Android 设备而使其闲置（或者长于策略中指定时长的其他时间）。设备屏幕可能变暗。</span><span class="sxs-lookup"><span data-stu-id="d83b2-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="d83b2-143">再次Outlook Android 设备上的应用。</span><span class="sxs-lookup"><span data-stu-id="d83b2-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="d83b2-144">系统将提示你输入 PIN，然后才能再次访问Outlook PIN。</span><span class="sxs-lookup"><span data-stu-id="d83b2-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="d83b2-145">验证"使用加密保护工作文件"</span><span class="sxs-lookup"><span data-stu-id="d83b2-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="d83b2-146">在" **编辑策略**"窗格中，选择" **设备丢失或被盗防护**"旁边的" **编辑**"，展开" **设备丢失或被盗时保护工作文件**"，并确保将" **使用加密保护工作文件**"设置为" **开**"，将" **强制用户将所有工作文件保存到 OneDrive for Business**"设置为" **关**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="d83b2-147">在用户的 Android 设备上，打开Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="d83b2-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d83b2-148">打开一封包含一些图像文件附件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d83b2-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="d83b2-149">点击附件信息旁边的向下箭头图标进行保存。</span><span class="sxs-lookup"><span data-stu-id="d83b2-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="d83b2-p106">系统可能会提示允许 Outlook 访问设备中的照片、媒体和文件。点击" **允许**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="d83b2-153">在屏幕底部，选择" **保存到设备**"，然后打开" **库** "应用。</span><span class="sxs-lookup"><span data-stu-id="d83b2-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="d83b2-p107">列表中应该会显示一张已加密的照片（如果保存了多个图像文件，将显示多张）。它可能会在"图片"列表中显示为灰色方框，其中心显示带白色感叹号的白色圆圈。</span><span class="sxs-lookup"><span data-stu-id="d83b2-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="d83b2-157">iOS</span><span class="sxs-lookup"><span data-stu-id="d83b2-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="d83b2-158">检查"应用保护"设置在用户设备上是否正常工作</span><span class="sxs-lookup"><span data-stu-id="d83b2-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="d83b2-159">在[设置 iOS 设备的应用配置](app-protection-settings-for-android-and-ios.md)以保护应用后，可按以下步骤验证所选设置是否有效。</span><span class="sxs-lookup"><span data-stu-id="d83b2-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="d83b2-160">首先，确保该策略适用于你要验证它的应用。</span><span class="sxs-lookup"><span data-stu-id="d83b2-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="d83b2-161">在管理 [Microsoft 365 商业高级版，](https://portal.office.com)转到"策略 **""** \> **编辑策略"。**</span><span class="sxs-lookup"><span data-stu-id="d83b2-161">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="d83b2-162">选择 **"iOS** 的应用程序策略"作为你在设置时创建的设置，或你创建的另一个策略，并验证是否强制Outlook例如。</span><span class="sxs-lookup"><span data-stu-id="d83b2-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="d83b2-164">验证需要 PIN 才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="d83b2-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="d83b2-165">在" **编辑策略**"窗格中，选择" **Office 文档的访问控制**"旁边的" **编辑**"，展开" **管理用户如何在移动设备上访问 Office 文件**"，并确保将" **需要 PIN 或指纹才能访问 Office 应用**"设置为" **开**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![确保将"需要 PIN 或指纹来访问Office"设置为"打开"。](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="d83b2-167">在用户的 iOS 设备中，Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="d83b2-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="d83b2-168">系统还会提示你输入 PIN 或使用指纹。</span><span class="sxs-lookup"><span data-stu-id="d83b2-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="d83b2-170">验证"超过登录失败次数限制后重置 PIN"</span><span class="sxs-lookup"><span data-stu-id="d83b2-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="d83b2-171">在"编辑策略"窗格中，选择 **"Office** 文档访问控制"旁边的"编辑"，展开"管理用户如何访问移动设备上的 **Office** 文件"，并确保"在尝试失败后重置 **PIN"** 设置为一个数字。</span><span class="sxs-lookup"><span data-stu-id="d83b2-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="d83b2-172">默认情况下为 5。</span><span class="sxs-lookup"><span data-stu-id="d83b2-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="d83b2-173">在用户的 iOS 设备中，Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="d83b2-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="d83b2-174">输入错误 PIN 的次数达到策略指定次数。</span><span class="sxs-lookup"><span data-stu-id="d83b2-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="d83b2-175">你将看到一条提示，指出 **"PIN 尝试限制已到达** "以重置 PIN。</span><span class="sxs-lookup"><span data-stu-id="d83b2-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="d83b2-177">按" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-177">Press **OK**.</span></span> <span data-ttu-id="d83b2-178">系统将提示你使用用户的凭据Microsoft 365 商业高级版登录，然后需要设置新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="d83b2-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="d83b2-179">验证"强制用户将所有工作文件保存到 OneDrive for Business"</span><span class="sxs-lookup"><span data-stu-id="d83b2-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="d83b2-180">在" **编辑策略**"窗格中，选择" **设备丢失或被盗防护**"旁边的" **编辑**"，展开" **设备丢失或被盗时保护工作文件**"，并确保将" **强制用户将所有工作文件保存到 OneDrive for Business**"设置为" **开**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="d83b2-182">在用户的 iOS 设备中，Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="d83b2-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d83b2-183">打开包含附件的电子邮件，然后打开附件，在屏幕底部选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="d83b2-185">应只会看到用于 OneDrive for Business 的选项。</span><span class="sxs-lookup"><span data-stu-id="d83b2-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="d83b2-186">如果不是，请点击"**添加帐户\*\*\*\*"，OneDrive for Business"** 添加帐户存储 **选择"帐户"。**</span><span class="sxs-lookup"><span data-stu-id="d83b2-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="d83b2-187">提供最终用户的登录Microsoft 365 商业高级版提示时进行登录。</span><span class="sxs-lookup"><span data-stu-id="d83b2-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="d83b2-188">点击" **保存**"，选择" **OneDrive for Business**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="d83b2-189">验证"Office 应用空闲指定时间后要求用户再次登录"</span><span class="sxs-lookup"><span data-stu-id="d83b2-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="d83b2-190">在"编辑策略"窗格中，选择 **"Office** 文档访问控制"旁边的"编辑"，展开"管理用户如何访问移动设备上的 **Office** 文件"，并确保将"要求用户在 Office 应用空闲后重新登录 **"** 设置为一定的分钟数。</span><span class="sxs-lookup"><span data-stu-id="d83b2-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="d83b2-191">默认情况下为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="d83b2-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="d83b2-192">在用户的 iOS 设备中，Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="d83b2-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d83b2-p113">现应该会显示 Outlook 收件箱。在至少 30 分钟（或长于策略中指定时间的其他时间）内不触碰 iOS 设备。设备屏幕可能变暗。</span><span class="sxs-lookup"><span data-stu-id="d83b2-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="d83b2-196">再次Outlook iOS 设备上访问设备。</span><span class="sxs-lookup"><span data-stu-id="d83b2-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="d83b2-197">系统将提示你输入 PIN，然后才能再次访问Outlook PIN。</span><span class="sxs-lookup"><span data-stu-id="d83b2-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="d83b2-198">验证"使用加密保护工作文件"</span><span class="sxs-lookup"><span data-stu-id="d83b2-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="d83b2-199">在" **编辑策略**"窗格中，选择" **设备丢失或被盗防护**"旁边的" **编辑**"，展开" **设备丢失或被盗时保护工作文件**"，并确保将" **使用加密保护工作文件**"设置为" **开**"，将" **强制用户将所有工作文件保存到 OneDrive for Business**"设置为" **关**"。</span><span class="sxs-lookup"><span data-stu-id="d83b2-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="d83b2-200">在用户的 iOS 设备中，Outlook，然后使用用户的 Microsoft 365 商业高级版 凭据登录，并输入 PIN（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="d83b2-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="d83b2-201">打开一封包含一些图像文件附件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d83b2-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="d83b2-202">点击该附件，然后点击其下的" **保存**"选项。</span><span class="sxs-lookup"><span data-stu-id="d83b2-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="d83b2-p114">从主屏幕打开" **照片**"应用。应看到已保存且加密的照片（如果保存了多个图像文件附件，将看到更多照片）。</span><span class="sxs-lookup"><span data-stu-id="d83b2-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

