---
title: Microsoft 365 设备管理指南
keywords: Microsoft 365， Microsoft 365 企业版， Microsoft 365 文档， 移动设备管理， Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: 设置 Microsoft 365 设备管理的路线图。
ms.openlocfilehash: 4c37033898865372fea19ddbb53ec9c8586f27b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918962"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="fecc9-104">Microsoft 365 设备管理指南</span><span class="sxs-lookup"><span data-stu-id="fecc9-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="fecc9-105">Microsoft 365 企业版包括可帮助在组织中管理设备及其应用的功能。</span><span class="sxs-lookup"><span data-stu-id="fecc9-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="fecc9-106">管理移动设备可帮助您保护组织的资源。</span><span class="sxs-lookup"><span data-stu-id="fecc9-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="fecc9-107">设备管理有两个选项：</span><span class="sxs-lookup"><span data-stu-id="fecc9-107">There are two options for device management:</span></span>

- [<span data-ttu-id="fecc9-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fecc9-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="fecc9-109">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="fecc9-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="fecc9-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fecc9-110">Microsoft Intune</span></span>

<span data-ttu-id="fecc9-111">可以使用 Microsoft Intune 通过移动设备管理或移动应用程序管理来管理对组织的访问权限。</span><span class="sxs-lookup"><span data-stu-id="fecc9-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="fecc9-112">移动设备管理是当用户在 Intune 中"注册"其设备时。</span><span class="sxs-lookup"><span data-stu-id="fecc9-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="fecc9-113">注册设备后，它是托管设备;因此，它可以接收组织的策略、规则和设置。</span><span class="sxs-lookup"><span data-stu-id="fecc9-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="fecc9-114">例如，你可以安装特定应用、创建密码策略、安装 VPN 连接等。</span><span class="sxs-lookup"><span data-stu-id="fecc9-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="fecc9-115">具有其自己的个人设备的用户可能不希望注册其设备或由 Intune 和组织的策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="fecc9-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="fecc9-116">但仍需要保护组织的资源和数据。</span><span class="sxs-lookup"><span data-stu-id="fecc9-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="fecc9-117">在此方案中，可以使用移动应用程序管理来保护应用。</span><span class="sxs-lookup"><span data-stu-id="fecc9-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="fecc9-118">例如，可以使用移动应用程序管理策略，要求用户在设备上访问 SharePoint Online 时输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="fecc9-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="fecc9-119">你还将确定如何管理个人设备和组织拥有的设备。</span><span class="sxs-lookup"><span data-stu-id="fecc9-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="fecc9-120">你可能希望以不同方式处理设备，具体取决于设备的用途。</span><span class="sxs-lookup"><span data-stu-id="fecc9-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="fecc9-121">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="fecc9-121">Basic Mobility and Security</span></span>

<span data-ttu-id="fecc9-122">这内置于 Microsoft 365 中，可帮助你保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 手机。</span><span class="sxs-lookup"><span data-stu-id="fecc9-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="fecc9-123">可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。</span><span class="sxs-lookup"><span data-stu-id="fecc9-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="fecc9-124">在两个选项中进行选择</span><span class="sxs-lookup"><span data-stu-id="fecc9-124">Choose between the two options</span></span>

<span data-ttu-id="fecc9-125">为了帮助你更好地评估最适合你的设备管理选项，请参阅在 [基本移动性安全性和 Intune](/office365/securitycompliance/choose-between-mdm-and-intune)之间选择。</span><span class="sxs-lookup"><span data-stu-id="fecc9-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="fecc9-126">根据你的评估，开始使用：</span><span class="sxs-lookup"><span data-stu-id="fecc9-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="fecc9-127">Intune</span><span class="sxs-lookup"><span data-stu-id="fecc9-127">Intune</span></span>](/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="fecc9-128">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="fecc9-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="fecc9-129">标识和设备访问建议</span><span class="sxs-lookup"><span data-stu-id="fecc9-129">Identity and device access recommendations</span></span>

<span data-ttu-id="fecc9-130">Microsoft 提供了一组有关[身份和设备访问](../security/office-365-security/microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。</span><span class="sxs-lookup"><span data-stu-id="fecc9-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="fecc9-131">对于设备访问，请使用以下文章中的建议和设置：</span><span class="sxs-lookup"><span data-stu-id="fecc9-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="fecc9-132">先决条件</span><span class="sxs-lookup"><span data-stu-id="fecc9-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="fecc9-133">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="fecc9-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="fecc9-134">Contoso 如何管理 Microsoft 365 的设备</span><span class="sxs-lookup"><span data-stu-id="fecc9-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="fecc9-135">有关虚构但具有代表性的多方企业如何使用 Microsoft 365 云服务部署其移动设备管理基础结构的信息，请参阅 [Contoso](contoso-mdm.md)移动设备管理。</span><span class="sxs-lookup"><span data-stu-id="fecc9-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>