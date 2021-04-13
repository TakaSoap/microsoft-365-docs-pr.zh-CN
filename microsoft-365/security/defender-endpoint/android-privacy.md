---
title: 适用于 Android 的 Microsoft Defender ATP - 隐私信息
description: 隐私控制，如何配置影响隐私的策略设置，以及有关在适用于 Android 的 Microsoft Defender ATP 中收集的诊断数据的信息。
keywords: microsoft， defender， atp， android， 隐私， 诊断
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d38d7a54aa860049e1968e5b92c801107bea0514
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687957"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="4d28a-104">Android 上的 Microsoft Defender for Endpoint - 隐私信息</span><span class="sxs-lookup"><span data-stu-id="4d28a-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="4d28a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4d28a-105">**Applies to:**</span></span>
- [<span data-ttu-id="4d28a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4d28a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4d28a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d28a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4d28a-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4d28a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4d28a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4d28a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="4d28a-110">适用于 Android 的 Defender for Endpoint 从已配置的 Android 设备收集信息，并存储在你拥有 Defender for Endpoint 的同一租户中。</span><span class="sxs-lookup"><span data-stu-id="4d28a-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span>

<span data-ttu-id="4d28a-111">收集的信息有助于使适用于 Android 的 Endpoint 的 Defender 保持安全、最新、如预期运行并支持服务。</span><span class="sxs-lookup"><span data-stu-id="4d28a-111">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="4d28a-112">所需数据</span><span class="sxs-lookup"><span data-stu-id="4d28a-112">Required Data</span></span> 

<span data-ttu-id="4d28a-113">必需数据包含使适用于 Android 的 Defender for Endpoint 按预期工作所需的数据。</span><span class="sxs-lookup"><span data-stu-id="4d28a-113">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="4d28a-114">此数据对于服务操作至关重要，可以包含与最终用户、组织、设备和应用相关的数据。</span><span class="sxs-lookup"><span data-stu-id="4d28a-114">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="4d28a-115">以下是要收集的数据类型列表：</span><span class="sxs-lookup"><span data-stu-id="4d28a-115">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="4d28a-116">应用信息</span><span class="sxs-lookup"><span data-stu-id="4d28a-116">App information</span></span>

<span data-ttu-id="4d28a-117">有关 Android 应用程序包 (设备上) API 的信息，包括</span><span class="sxs-lookup"><span data-stu-id="4d28a-117">Information about Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="4d28a-118">安装源</span><span class="sxs-lookup"><span data-stu-id="4d28a-118">Install source</span></span>
-  <span data-ttu-id="4d28a-119">存储 (APK) 文件路径</span><span class="sxs-lookup"><span data-stu-id="4d28a-119">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="4d28a-120">安装时间、APK 大小和权限</span><span class="sxs-lookup"><span data-stu-id="4d28a-120">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="4d28a-121">网页/网络信息</span><span class="sxs-lookup"><span data-stu-id="4d28a-121">Web page / Network information</span></span>

- <span data-ttu-id="4d28a-122">单击 (支持的浏览器) URL</span><span class="sxs-lookup"><span data-stu-id="4d28a-122">Full URL (on supported browsers), when clicked</span></span>
- <span data-ttu-id="4d28a-123">连接信息</span><span class="sxs-lookup"><span data-stu-id="4d28a-123">Connection information</span></span>
- <span data-ttu-id="4d28a-124">协议类型 (如 HTTP、HTTPS 等) </span><span class="sxs-lookup"><span data-stu-id="4d28a-124">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="4d28a-125">设备和帐户信息</span><span class="sxs-lookup"><span data-stu-id="4d28a-125">Device and account information</span></span>

- <span data-ttu-id="4d28a-126">设备信息，如&时间、Android 版本、OEM 型号、CPU 信息和设备标识符</span><span class="sxs-lookup"><span data-stu-id="4d28a-126">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="4d28a-127">设备标识符是以下项之一：</span><span class="sxs-lookup"><span data-stu-id="4d28a-127">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="4d28a-128">Wi-Fi适配器 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="4d28a-128">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="4d28a-129">[Android ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (在首次启动设备时由 Android 生成) </span><span class="sxs-lookup"><span data-stu-id="4d28a-129">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="4d28a-130">随机生成的全局唯一标识符 (GUID) </span><span class="sxs-lookup"><span data-stu-id="4d28a-130">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="4d28a-131">租户、设备和用户信息</span><span class="sxs-lookup"><span data-stu-id="4d28a-131">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="4d28a-132">Azure Active Directory (AD) 设备 ID 和 Azure 用户 ID：唯一标识设备，分别在 Azure Active directory 中标识用户。</span><span class="sxs-lookup"><span data-stu-id="4d28a-132">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="4d28a-133">Azure 租户 ID - 标识 Azure Active Directory 中的组织的 GUID</span><span class="sxs-lookup"><span data-stu-id="4d28a-133">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="4d28a-134">Microsoft Defender ATP 组织 ID - 与设备所属的企业关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="4d28a-134">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="4d28a-135">允许 Microsoft 确定问题是否影响一组选定企业以及有多少企业受到影响</span><span class="sxs-lookup"><span data-stu-id="4d28a-135">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="4d28a-136">用户主体名称 – 用户的电子邮件 ID</span><span class="sxs-lookup"><span data-stu-id="4d28a-136">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="4d28a-137">产品或服务使用情况数据</span><span class="sxs-lookup"><span data-stu-id="4d28a-137">Product and service usage data</span></span>
-   <span data-ttu-id="4d28a-138">应用包信息，包括名称、版本以及应用升级状态</span><span class="sxs-lookup"><span data-stu-id="4d28a-138">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="4d28a-139">在应用中执行的操作</span><span class="sxs-lookup"><span data-stu-id="4d28a-139">Actions performed in the app</span></span>

-   <span data-ttu-id="4d28a-140">威胁检测信息，例如威胁名称、类别等。</span><span class="sxs-lookup"><span data-stu-id="4d28a-140">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="4d28a-141">Android 生成的崩溃报告日志</span><span class="sxs-lookup"><span data-stu-id="4d28a-141">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="4d28a-142">可选数据</span><span class="sxs-lookup"><span data-stu-id="4d28a-142">Optional Data</span></span>

<span data-ttu-id="4d28a-143">可选数据包括诊断数据和反馈数据。</span><span class="sxs-lookup"><span data-stu-id="4d28a-143">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="4d28a-144">可选诊断数据是一种附加数据，有助于我们改进产品并提供增强的信息来帮助检测、诊断和修复问题。</span><span class="sxs-lookup"><span data-stu-id="4d28a-144">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="4d28a-145">可选诊断数据包括：</span><span class="sxs-lookup"><span data-stu-id="4d28a-145">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="4d28a-146">应用、CPU 和网络使用情况</span><span class="sxs-lookup"><span data-stu-id="4d28a-146">App, CPU, and network usage</span></span>

-   <span data-ttu-id="4d28a-147">从应用角度考虑设备的状态，包括扫描状态、扫描计时、授予的应用权限和升级状态</span><span class="sxs-lookup"><span data-stu-id="4d28a-147">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="4d28a-148">管理员配置的功能</span><span class="sxs-lookup"><span data-stu-id="4d28a-148">Features configured by the admin</span></span>

-   <span data-ttu-id="4d28a-149">有关设备上浏览器的基本信息</span><span class="sxs-lookup"><span data-stu-id="4d28a-149">Basic information about the browsers on the device</span></span>

<span data-ttu-id="4d28a-150">**反馈 通过** 用户提供的应用内反馈收集数据</span><span class="sxs-lookup"><span data-stu-id="4d28a-150">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="4d28a-151">用户的电子邮件地址（如果他们选择提供）</span><span class="sxs-lookup"><span data-stu-id="4d28a-151">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="4d28a-152">反馈类型 (、笑脸、想法) 以及用户提交的任何反馈评论</span><span class="sxs-lookup"><span data-stu-id="4d28a-152">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
