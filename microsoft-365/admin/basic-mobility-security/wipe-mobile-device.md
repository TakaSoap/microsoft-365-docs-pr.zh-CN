---
title: 在基本移动和安全性中擦除移动设备
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用内置的基本移动性和安全性从已注册的设备中删除信息。
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336739"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="85839-103">在基本移动和安全性中擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="85839-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="85839-104">可以使用 Microsoft 365 的内置基本移动性和安全性来仅删除组织信息，或执行恢复出厂设置以删除移动设备中的所有信息并将其还原为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="85839-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="85839-105">准备工作</span><span class="sxs-lookup"><span data-stu-id="85839-105">Before you begin</span></span>

<span data-ttu-id="85839-106">移动设备可以存储敏感的组织信息，并提供对组织的 Microsoft 365 资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="85839-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="85839-107">为了帮助保护您的组织的信息，您可以执行原始重置或删除公司数据：</span><span class="sxs-lookup"><span data-stu-id="85839-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="85839-108">**出厂重置**：删除用户移动设备上的所有数据，包括已安装的应用程序、照片和个人信息。</span><span class="sxs-lookup"><span data-stu-id="85839-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="85839-109">擦除完成后，设备将还原为其出厂设置。</span><span class="sxs-lookup"><span data-stu-id="85839-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="85839-110">**删除公司数据**：仅删除组织数据并将安装的应用程序、照片和个人信息保留在用户的移动设备上。</span><span class="sxs-lookup"><span data-stu-id="85839-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="85839-111">\*\*擦除设备 (出厂重置或删除公司数据) 时 \*\*，设备将从受管理的设备列表中删除。</span><span class="sxs-lookup"><span data-stu-id="85839-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="85839-112">**自动重置设备**：您可以设置基本移动性和安全策略，以便在用户未成功输入设备密码一段特定次数后自动出厂时重置设备。</span><span class="sxs-lookup"><span data-stu-id="85839-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="85839-113">为此，请按照 " [基本移动性和安全性" 中的创建设备安全策略](create-device-security-policies-in-basic-mmobility-and-security.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="85839-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies-in-basic-mmobility-and-security.md).</span></span>
    
- <span data-ttu-id="85839-114">如果想要在擦除设备时**知道用户体验**，请参阅  [用户和设备影响是什么？](#whats-the-user-and-device-impact)。</span><span class="sxs-lookup"><span data-stu-id="85839-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="85839-115">擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="85839-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="85839-116">转到 [Microsoft 365 管理中心](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)。</span><span class="sxs-lookup"><span data-stu-id="85839-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="85839-117">在 "搜索" 字段中键入移动设备管理，并从结果列表中选择 " **移动设备管理** "。</span><span class="sxs-lookup"><span data-stu-id="85839-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本移动性和 Secruity 移动设备管理选项":::

3. <span data-ttu-id="85839-119">选择 " **管理设备**"。</span><span class="sxs-lookup"><span data-stu-id="85839-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="85839-120">选择要擦除的设备。</span><span class="sxs-lookup"><span data-stu-id="85839-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="85839-121">选择 " **管理**"。</span><span class="sxs-lookup"><span data-stu-id="85839-121">Select **Manage**.</span></span>

6. <span data-ttu-id="85839-122">选择要执行的远程擦除类型。</span><span class="sxs-lookup"><span data-stu-id="85839-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="85839-123">若要执行完全擦除并将设备还原到其出厂设置，请选择 "恢复 **出厂**设置"。</span><span class="sxs-lookup"><span data-stu-id="85839-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="85839-124">若要执行选择性擦除并仅删除 Microsoft 365 组织信息，请选择 " **删除公司数据**"。</span><span class="sxs-lookup"><span data-stu-id="85839-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="85839-125">若要从组织中删除设备，请选择 " **删除设备**"。</span><span class="sxs-lookup"><span data-stu-id="85839-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="85839-126">选择“**是**”进行确认。</span><span class="sxs-lookup"><span data-stu-id="85839-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="85839-127">我如何知道它已正常工作？</span><span class="sxs-lookup"><span data-stu-id="85839-127">How do I know it worked?</span></span>

<span data-ttu-id="85839-128">在受管理的设备列表中，您将不会再看到该移动设备。</span><span class="sxs-lookup"><span data-stu-id="85839-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="85839-129">为什么要擦除设备？</span><span class="sxs-lookup"><span data-stu-id="85839-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="85839-130">由于以下原因，请擦除设备：</span><span class="sxs-lookup"><span data-stu-id="85839-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="85839-131">像智能手机和平板电脑这样的移动设备在所有时间都变得更加完善。</span><span class="sxs-lookup"><span data-stu-id="85839-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="85839-132">这意味着，您的用户可以更轻松地存储敏感的公司信息，如个人身份标识或机密通信，并在旅途中对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="85839-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="85839-133">如果其中一个移动设备丢失或被盗，则擦除设备有助于防止您的组织的信息在错误的手中终止。</span><span class="sxs-lookup"><span data-stu-id="85839-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="85839-134">当用户将组织的个人设备设置为使用基本移动性和安全性进行注册时，您可以通过执行恢复出厂设置来帮助防止组织信息与该用户配合使用。</span><span class="sxs-lookup"><span data-stu-id="85839-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="85839-135">如果您的组织向用户提供移动设备，则可能需要随时重新分配设备。</span><span class="sxs-lookup"><span data-stu-id="85839-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="85839-136">在将设备分配给新用户之前在设备上执行恢复出厂设置有助于确保删除先前所有者的所有敏感信息。</span><span class="sxs-lookup"><span data-stu-id="85839-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="85839-137">用户和设备的影响是什么？</span><span class="sxs-lookup"><span data-stu-id="85839-137">What's the user and device impact?</span></span>

<span data-ttu-id="85839-138">擦除会立即发送到移动设备，并且设备在 Azure active directory 中被标记为不合规。</span><span class="sxs-lookup"><span data-stu-id="85839-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="85839-139">虽然在将设备重置为出厂默认值时删除了所有数据，但下表介绍了在删除公司数据时，在设备上删除的每种设备类型的内容。</span><span class="sxs-lookup"><span data-stu-id="85839-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="85839-140">**内容 impace**</span><span class="sxs-lookup"><span data-stu-id="85839-140">**Content impace**</span></span>|<span data-ttu-id="85839-141">**iOS 10 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="85839-141">**iOS 10 and later**</span></span>|<span data-ttu-id="85839-142">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="85839-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85839-143">如果设备受 Intune 应用保护策略保护，则会擦除 Microsoft 365 应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="85839-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="85839-144">不会删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="85839-144">The apps aren't removed.</span></span> <span data-ttu-id="85839-145">对于不受移动应用程序管理 (MAM) 策略保护的设备，Outlook 和 OneDrive 不会删除缓存的数据。</span><span class="sxs-lookup"><span data-stu-id="85839-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="85839-146">**注释** 若要应用 Intune 应用保护策略，您必须具有 Intune 许可证。</span><span class="sxs-lookup"><span data-stu-id="85839-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="85839-147">是</span><span class="sxs-lookup"><span data-stu-id="85839-147">Yes</span></span>|<span data-ttu-id="85839-148">是</span><span class="sxs-lookup"><span data-stu-id="85839-148">Yes</span></span>|
|<span data-ttu-id="85839-149">基本移动性应用的策略设置和对设备的安全性不再强制实施;用户可以更改设置。</span><span class="sxs-lookup"><span data-stu-id="85839-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="85839-150">是</span><span class="sxs-lookup"><span data-stu-id="85839-150">Yes</span></span>|<span data-ttu-id="85839-151">是</span><span class="sxs-lookup"><span data-stu-id="85839-151">Yes</span></span>|
|<span data-ttu-id="85839-152">将删除基本移动性和安全性创建的电子邮件配置文件，并删除设备上缓存的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="85839-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="85839-153">是</span><span class="sxs-lookup"><span data-stu-id="85839-153">Yes</span></span>|<span data-ttu-id="85839-154">不适用</span><span class="sxs-lookup"><span data-stu-id="85839-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="85839-155">公司门户应用程序适用于 iOS 应用商店和 Android 设备的 Play 商店。</span><span class="sxs-lookup"><span data-stu-id="85839-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="85839-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="85839-156">Related topics</span></span>

[<span data-ttu-id="85839-157">设置基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="85839-157">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)