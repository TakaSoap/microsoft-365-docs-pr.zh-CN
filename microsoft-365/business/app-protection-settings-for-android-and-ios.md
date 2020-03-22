---
title: 设置 Android 或 iOS 设备的应用保护设置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何创建、编辑或删除应用管理策略，以及如何保护 Android 或 iOS 设备上的工作文件。
ms.openlocfilehash: 0adb103ac3bef72e340c1f5daf54a6b8a184d85c
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894272"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="dd929-103">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="dd929-103">Set app protection settings for Android or iOS devices</span></span>

![指向的标题https://aka.ms/aboutM365preview。](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="dd929-105">创建应用管理策略</span><span class="sxs-lookup"><span data-stu-id="dd929-105">Create an app management policy</span></span>

1. <span data-ttu-id="dd929-106">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="dd929-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="dd929-107">在左侧导航中，选择 "**设备** \> **策略** \> " "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="dd929-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="dd929-108">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="dd929-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="dd929-109">在 "**策略类型**" 下，选择 "基于**Android 的应用程序管理**" 或 "**应用程序管理**"，具体取决于要创建的策略集。</span><span class="sxs-lookup"><span data-stu-id="dd929-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="dd929-110">扩展**当设备丢失或被盗时保护工作文件**，并**管理用户如何在移动设备上访问 Office 文件**。</span><span class="sxs-lookup"><span data-stu-id="dd929-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="dd929-111">配置所需的设置。</span><span class="sxs-lookup"><span data-stu-id="dd929-111">Configure the settings how you would like.</span></span> <span data-ttu-id="dd929-112">**管理用户在移动设备上访问 Office 文件的方式**默认情况下是**关闭**的，但我们建议您**将其打开**并接受默认值。</span><span class="sxs-lookup"><span data-stu-id="dd929-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="dd929-113">有关详细信息，请参阅[可用设置](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="dd929-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="dd929-114">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="dd929-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="dd929-116">Next decide **Who will get these settings?**</span><span class="sxs-lookup"><span data-stu-id="dd929-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="dd929-117">如果不想使用默认的 "**所有用户**" 安全组，请选择 "**更改**" \> **，选择获取这些设置的**安全组。</span><span class="sxs-lookup"><span data-stu-id="dd929-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="dd929-118">最后，选择" **完成**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="dd929-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="dd929-119">编辑应用管理策略</span><span class="sxs-lookup"><span data-stu-id="dd929-119">Edit an app management policy</span></span>

1. <span data-ttu-id="dd929-120">在**策略**卡上，选择 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="dd929-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="dd929-121">在" **编辑策略**"窗格中，选择要更改的策略</span><span class="sxs-lookup"><span data-stu-id="dd929-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="dd929-122">选择每个设置旁边的" **编辑**"来更改策略中的值。</span><span class="sxs-lookup"><span data-stu-id="dd929-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="dd929-123">当您更改某个值时，它会自动保存在策略中。</span><span class="sxs-lookup"><span data-stu-id="dd929-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="dd929-124">完成后，请关闭 "**编辑策略**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="dd929-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="dd929-125">删除应用管理策略</span><span class="sxs-lookup"><span data-stu-id="dd929-125">Delete an app management policy</span></span>

1. <span data-ttu-id="dd929-126">在 "**策略**" 页上，选择策略，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="dd929-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="dd929-127">在 "**删除策略**" 窗格中，选择 "**确认**" 以删除所选的策略或策略。</span><span class="sxs-lookup"><span data-stu-id="dd929-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="dd929-128">可用设置</span><span class="sxs-lookup"><span data-stu-id="dd929-128">Available settings</span></span>

<span data-ttu-id="dd929-129">下表提供了可用于保护设备上的工作文件的设置的详细信息，以及控制用户如何从其移动设备访问 Office 文件的设置。</span><span class="sxs-lookup"><span data-stu-id="dd929-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="dd929-130">有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="dd929-130">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="dd929-131">用户保护工作文件的设置</span><span class="sxs-lookup"><span data-stu-id="dd929-131">Settings that protect work files</span></span>

<span data-ttu-id="dd929-132">如果用户的设备丢失或被盗，以下设置可用于保护工作文件：</span><span class="sxs-lookup"><span data-stu-id="dd929-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dd929-133">设置</span><span class="sxs-lookup"><span data-stu-id="dd929-133">Setting</span></span>  <br/> |<span data-ttu-id="dd929-134">说明</span><span class="sxs-lookup"><span data-stu-id="dd929-134">Description</span></span>  <br/> |
|<span data-ttu-id="dd929-135">在以下天数后，从非活动的设备删除工作文件</span><span class="sxs-lookup"><span data-stu-id="dd929-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="dd929-136">如果设备未用于您在此处指定的天数，则将自动删除存储在该设备上的所有工作文件。</span><span class="sxs-lookup"><span data-stu-id="dd929-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="dd929-137">强制要求用户将所有的工作文件保存到 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="dd929-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="dd929-138">如果此设置为 **"打开**"，则工作文件的唯一可用保存位置是 OneDrive for business。</span><span class="sxs-lookup"><span data-stu-id="dd929-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="dd929-139">对工作文件进行加密</span><span class="sxs-lookup"><span data-stu-id="dd929-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="dd929-140">将此设置保持为" **打开**"，可通过加密保护工作文件。</span><span class="sxs-lookup"><span data-stu-id="dd929-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="dd929-141">即使设备丢失或被盗，也没有人能够读取您的公司数据。</span><span class="sxs-lookup"><span data-stu-id="dd929-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="dd929-142">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="dd929-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="dd929-143">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="dd929-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dd929-144">设置</span><span class="sxs-lookup"><span data-stu-id="dd929-144">Setting</span></span>  <br/> |<span data-ttu-id="dd929-145">说明</span><span class="sxs-lookup"><span data-stu-id="dd929-145">Description</span></span>  <br/> |
|<span data-ttu-id="dd929-146">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="dd929-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="dd929-147">如果此设置为 **，则用户必须**提供另一种形式的身份验证，以及其用户名和密码，然后才能在其移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="dd929-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="dd929-148">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="dd929-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="dd929-149">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="dd929-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="dd929-150">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="dd929-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="dd929-151">此设置确定用户在提示用户重新登录之前可以处于空闲状态的时间。</span><span class="sxs-lookup"><span data-stu-id="dd929-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="dd929-152">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="dd929-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="dd929-p105">一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **打开**"，会阻止这些设备。  </span><span class="sxs-lookup"><span data-stu-id="dd929-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="dd929-156">不允许用户将 Office 应用程序中的内容复制到个人应用</span><span class="sxs-lookup"><span data-stu-id="dd929-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="dd929-157">默认允许此设置，但如果设置为" **开**"，用户可将工作文件中的信息复制到个人文件。</span><span class="sxs-lookup"><span data-stu-id="dd929-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="dd929-158">如果设置为" **关** "，用户无法将工作帐户中的信息复制到个人应用或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="dd929-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
