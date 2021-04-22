---
title: 隐私信息 - 适用于 iOS 上的终结点的 Microsoft Defender
ms.reviewer: ''
description: 介绍 iOS 上适用于终结点的 Microsoft Defender 的隐私信息
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 策略， 概述
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 15c22a6f6b581ff68488db6628f7647d49487652
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934281"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="4e4ca-104">隐私信息 - 适用于 iOS 上的终结点的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4e4ca-104">Privacy information - Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="4e4ca-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4e4ca-105">**Applies to:**</span></span>
- [<span data-ttu-id="4e4ca-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4e4ca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4e4ca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e4ca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4e4ca-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4e4ca-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4e4ca-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> <span data-ttu-id="4e4ca-110">iOS 上的 Defender for Endpoint 使用 VPN 提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-110">Defender for Endpoint on iOS uses a VPN to provide the Web Protection feature.</span></span> <span data-ttu-id="4e4ca-111">这不是常规 VPN，它是不接受设备外流量的本地或自循环 VPN。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-111">This is not a regular VPN and is a local or self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="4e4ca-112">**Microsoft 或你的组织看不到你的浏览活动。**</span><span class="sxs-lookup"><span data-stu-id="4e4ca-112">**Microsoft or your organization, does not see your browsing activity.**</span></span>

<span data-ttu-id="4e4ca-113">iOS 上的 Defender for Endpoint 从已配置的 iOS 设备收集信息，并存储在你拥有 Defender for Endpoint 的同一租户中。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-113">Defender for Endpoint on iOS collects information from your configured iOS devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="4e4ca-114">收集此信息有助于使 iOS 上的 Defender for Endpoint 保持安全、最新、如预期运行并支持服务。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-114">The information is collected to help keep Defender for Endpoint on iOS secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="4e4ca-115">有关数据存储详细信息，请参阅适用于终结点数据存储[和隐私的 Microsoft Defender。](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="4e4ca-115">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

## <a name="required-data"></a><span data-ttu-id="4e4ca-116">所需数据</span><span class="sxs-lookup"><span data-stu-id="4e4ca-116">Required data</span></span> 

<span data-ttu-id="4e4ca-117">必需数据包含使 iOS 上的 Defender for Endpoint 按预期工作所必需的数据。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-117">Required data consists of data that is necessary to make Defender for Endpoint on iOS work as expected.</span></span> <span data-ttu-id="4e4ca-118">此数据对于服务操作至关重要，可以包含与最终用户、组织、设备和应用相关的数据。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-118">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> 

<span data-ttu-id="4e4ca-119">下面列出了要收集的数据类型：</span><span class="sxs-lookup"><span data-stu-id="4e4ca-119">Here is a list of the types of data being collected:</span></span> 

### <a name="web-page-or-network-information"></a><span data-ttu-id="4e4ca-120">网页或网络信息</span><span class="sxs-lookup"><span data-stu-id="4e4ca-120">Web page or Network information</span></span> 

- <span data-ttu-id="4e4ca-121">仅在检测到恶意连接或网页时网站的域名。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-121">Domain name of the website only when a malicious connection or web page is detected.</span></span> 

### <a name="device-and-account-information"></a><span data-ttu-id="4e4ca-122">设备和帐户信息</span><span class="sxs-lookup"><span data-stu-id="4e4ca-122">Device and account information</span></span> 

- <span data-ttu-id="4e4ca-123">设备信息，例如&、iOS 版本、CPU 信息和设备标识符，其中设备标识符为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="4e4ca-123">Device information such as date & time, iOS version, CPU info, and Device identifier, where Device identifier is one of the following:</span></span> 

    - <span data-ttu-id="4e4ca-124">Wi-Fi适配器 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="4e4ca-124">Wi-Fi adapter MAC address</span></span> 

    - <span data-ttu-id="4e4ca-125">随机生成的全局唯一标识符 (GUID) </span><span class="sxs-lookup"><span data-stu-id="4e4ca-125">Randomly generated globally unique identifier (GUID)</span></span> 

- <span data-ttu-id="4e4ca-126">租户、设备和用户信息</span><span class="sxs-lookup"><span data-stu-id="4e4ca-126">Tenant, Device, and User information</span></span> 

    - <span data-ttu-id="4e4ca-127">Azure Active Directory (AD) 设备 ID 和 Azure 用户 ID - 唯一标识设备，分别位于 Azure Active directory 中的用户。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-127">Azure Active Directory (AD) Device ID and Azure User ID - Uniquely identifies the device, User respectively at Azure Active directory.</span></span> 

    - <span data-ttu-id="4e4ca-128">Azure 租户 ID - 标识 Azure Active Directory 中的组织的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-128">Azure tenant ID - GUID that identifies your organization within Azure Active Directory.</span></span> 

    - <span data-ttu-id="4e4ca-129">Microsoft Defender for Endpoint 组织 ID - 与设备所属的企业关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-129">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="4e4ca-130">允许 Microsoft 确定是否有影响一组选定企业的问题以及受到影响的企业数量。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-130">Allows Microsoft to identify if there are issues affecting a select set of enterprises and the number of enterprises impacted.</span></span> 

    - <span data-ttu-id="4e4ca-131">用户主体名称 - 用户的电子邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-131">User Principal Name - Email ID of the user.</span></span> 

### <a name="product-and-service-usage-data"></a><span data-ttu-id="4e4ca-132">产品或服务使用情况数据</span><span class="sxs-lookup"><span data-stu-id="4e4ca-132">Product and service usage data</span></span> 

<span data-ttu-id="4e4ca-133">仅为设备上安装的 Microsoft Defender for Endpoint 应用收集以下信息。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-133">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

- <span data-ttu-id="4e4ca-134">应用包信息，包括名称、版本以及应用升级状态。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-134">App package info, including name, version, and app upgrade status.</span></span> 

- <span data-ttu-id="4e4ca-135">在应用中完成的操作。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-135">Actions done in the app.</span></span> 

- <span data-ttu-id="4e4ca-136">iOS 生成的崩溃报告日志。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-136">Crash report logs generated by iOS.</span></span> 

- <span data-ttu-id="4e4ca-137">内存使用率数据。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-137">Memory usage data.</span></span> 

## <a name="optional-data"></a><span data-ttu-id="4e4ca-138">可选数据</span><span class="sxs-lookup"><span data-stu-id="4e4ca-138">Optional Data</span></span> 

<span data-ttu-id="4e4ca-139">可选数据包括来自客户端的诊断数据和反馈数据。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-139">Optional data includes diagnostic data and feedback data from the client.</span></span> <span data-ttu-id="4e4ca-140">可选诊断数据是一种附加数据，有助于我们改进产品并提供增强的信息来帮助检测、诊断和修复问题。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-140">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="4e4ca-141">此数据仅供诊断使用，服务本身不需要。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-141">This data is only for diagnostic purposes and is not required for the service itself.</span></span> 

<span data-ttu-id="4e4ca-142">可选诊断数据包括：</span><span class="sxs-lookup"><span data-stu-id="4e4ca-142">Optional diagnostic data includes:</span></span> 

- <span data-ttu-id="4e4ca-143">适用于终结点的 Defender 的应用、CPU 和网络使用情况。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-143">App, CPU, and network usage for Defender for Endpoint.</span></span> 

- <span data-ttu-id="4e4ca-144">管理员为 Defender for Endpoint 配置的功能。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-144">Features configured by the admin for Defender for Endpoint.</span></span> 

<span data-ttu-id="4e4ca-145">反馈 通过用户提供的应用内反馈收集数据。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-145">Feedback Data is collected through in-app feedback provided by the user.</span></span> 

- <span data-ttu-id="4e4ca-146">用户的电子邮件地址（如果他们选择提供它）。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-146">The user's email address, if they choose to provide it.</span></span>

- <span data-ttu-id="4e4ca-147">反馈类型 (、笑脸、想法) 以及用户提交的任何反馈评论。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-147">Feedback type (smile, frown, idea) and any feedback comments submitted by the user.</span></span> 

<span data-ttu-id="4e4ca-148">有关详细信息，请参阅关于 [隐私的更多信息](https://aka.ms/mdatpiosprivacystatement)。</span><span class="sxs-lookup"><span data-stu-id="4e4ca-148">For more information, see [More on Privacy](https://aka.ms/mdatpiosprivacystatement).</span></span>


