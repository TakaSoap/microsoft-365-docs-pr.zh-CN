---
title: Microsoft 365 设备管理指南
keywords: Microsoft 365、Microsoft 365企业版、Microsoft 365文档、移动设备管理、Intune
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
description: 为设备设置设备管理的Microsoft 365。
ms.openlocfilehash: ec284a96fc8e7285f89e8a909b76c782b4469ce1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051456"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="5b408-104">Microsoft 365 设备管理指南</span><span class="sxs-lookup"><span data-stu-id="5b408-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="5b408-105">Microsoft 365企业版包括可帮助在组织中管理设备及其应用的功能。</span><span class="sxs-lookup"><span data-stu-id="5b408-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="5b408-106">管理移动设备可帮助您保护组织的资源。</span><span class="sxs-lookup"><span data-stu-id="5b408-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="5b408-107">设备管理有两个选项：</span><span class="sxs-lookup"><span data-stu-id="5b408-107">There are two options for device management:</span></span>

- [<span data-ttu-id="5b408-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5b408-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="5b408-109">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="5b408-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="5b408-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5b408-110">Microsoft Intune</span></span>

<span data-ttu-id="5b408-111">可以使用Microsoft Intune移动设备管理或移动应用程序管理来管理对组织的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5b408-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="5b408-112">移动设备管理是当用户在 Intune 中"注册"其设备时。</span><span class="sxs-lookup"><span data-stu-id="5b408-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="5b408-113">注册设备后，它是托管设备;因此，它可以接收组织的策略、规则和设置。</span><span class="sxs-lookup"><span data-stu-id="5b408-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="5b408-114">例如，你可以安装特定应用、创建密码策略、安装 VPN 连接等。</span><span class="sxs-lookup"><span data-stu-id="5b408-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="5b408-115">具有其自己的个人设备的用户可能不希望注册其设备或由 Intune 和组织的策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="5b408-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="5b408-116">但仍需要保护组织的资源和数据。</span><span class="sxs-lookup"><span data-stu-id="5b408-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="5b408-117">在此方案中，可以使用移动应用程序管理来保护应用。</span><span class="sxs-lookup"><span data-stu-id="5b408-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="5b408-118">例如，可以使用移动应用程序管理策略，要求用户在访问 SharePoint Online 时输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="5b408-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="5b408-119">你还将确定如何管理个人设备和组织拥有的设备。</span><span class="sxs-lookup"><span data-stu-id="5b408-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="5b408-120">你可能希望以不同方式处理设备，具体取决于设备的用途。</span><span class="sxs-lookup"><span data-stu-id="5b408-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="5b408-121">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="5b408-121">Basic Mobility and Security</span></span>

<span data-ttu-id="5b408-122">这内置于 Microsoft 365，可帮助你保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 手机。</span><span class="sxs-lookup"><span data-stu-id="5b408-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="5b408-123">可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。</span><span class="sxs-lookup"><span data-stu-id="5b408-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="5b408-124">在两个选项中进行选择</span><span class="sxs-lookup"><span data-stu-id="5b408-124">Choose between the two options</span></span>

<span data-ttu-id="5b408-125">为了帮助你更好地评估最适合你的设备管理选项，请参阅在 [基本移动性安全性和 Intune](/office365/securitycompliance/choose-between-mdm-and-intune)之间选择。</span><span class="sxs-lookup"><span data-stu-id="5b408-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="5b408-126">根据你的评估，开始使用：</span><span class="sxs-lookup"><span data-stu-id="5b408-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="5b408-127">Intune</span><span class="sxs-lookup"><span data-stu-id="5b408-127">Intune</span></span>](/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="5b408-128">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="5b408-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="5b408-129">标识和设备访问建议</span><span class="sxs-lookup"><span data-stu-id="5b408-129">Identity and device access recommendations</span></span>

<span data-ttu-id="5b408-130">Microsoft 提供了一组有关[身份和设备访问](../security/defender-365-security/microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。</span><span class="sxs-lookup"><span data-stu-id="5b408-130">Microsoft provides a set of recommendations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="5b408-131">对于设备访问，请使用以下文章中的建议和设置：</span><span class="sxs-lookup"><span data-stu-id="5b408-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="5b408-132">先决条件</span><span class="sxs-lookup"><span data-stu-id="5b408-132">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="5b408-133">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="5b408-133">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="5b408-134">Contoso 如何管理设备Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b408-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="5b408-135">有关虚构但具有代表性的跨国家/公司如何使用 Microsoft 365 部署其移动设备管理基础结构的信息，请参阅[Contoso](contoso-mdm.md)移动设备管理。</span><span class="sxs-lookup"><span data-stu-id="5b408-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>