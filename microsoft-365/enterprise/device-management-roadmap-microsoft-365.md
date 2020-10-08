---
title: Microsoft 365 的设备管理路线图
keywords: Microsoft 365，Microsoft 365 for enterprise，Microsoft 365 文档，移动设备管理，Intune
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
description: 为 Microsoft 365 设置设备管理的路线图。
ms.openlocfilehash: 0efe7098f90064184f222acb671ae6f96c1b38d5
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384757"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="402e0-104">Microsoft 365 的设备管理路线图</span><span class="sxs-lookup"><span data-stu-id="402e0-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="402e0-105">适用于企业的 Microsoft 365 包括帮助管理组织内的设备及其应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="402e0-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="402e0-106">管理移动设备可帮助您保护组织的资源。</span><span class="sxs-lookup"><span data-stu-id="402e0-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="402e0-107">设备管理有两个选项：</span><span class="sxs-lookup"><span data-stu-id="402e0-107">There are two options for device management:</span></span>

- [<span data-ttu-id="402e0-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="402e0-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="402e0-109">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="402e0-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="402e0-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="402e0-110">Microsoft Intune</span></span>

<span data-ttu-id="402e0-111">你可以使用 Microsoft Intune 管理对你的组织的使用移动设备管理或移动应用程序管理的访问。</span><span class="sxs-lookup"><span data-stu-id="402e0-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="402e0-112">移动设备管理是用户在 Intune 中 "注册" 其设备时。</span><span class="sxs-lookup"><span data-stu-id="402e0-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="402e0-113">设备注册后，就是管理设备;因此，它可以接收你的组织的策略、规则和设置。</span><span class="sxs-lookup"><span data-stu-id="402e0-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="402e0-114">例如，您可以安装特定应用程序，创建密码策略，安装 VPN 连接，等等。</span><span class="sxs-lookup"><span data-stu-id="402e0-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="402e0-115">拥有自己的个人设备的用户可能不希望注册其设备，也不能由 Intune 和组织的策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="402e0-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="402e0-116">但您仍需要保护您组织的资源和数据。</span><span class="sxs-lookup"><span data-stu-id="402e0-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="402e0-117">在这种情况下，您可以使用移动应用程序管理来保护您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="402e0-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="402e0-118">例如，您可以使用移动应用程序管理策略，该策略要求用户在设备上访问 SharePoint Online 时输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="402e0-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="402e0-119">您还将确定如何管理个人设备和组织拥有的设备。</span><span class="sxs-lookup"><span data-stu-id="402e0-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="402e0-120">您可能需要以不同的方式处理设备，具体取决于设备的用途。</span><span class="sxs-lookup"><span data-stu-id="402e0-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="402e0-121">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="402e0-121">Basic Mobility and Security</span></span>

<span data-ttu-id="402e0-122">此功能内置于 Microsoft 365 中，可帮助您保护和管理用户的移动设备，如 Iphone、Ipad、Androids 和 Windows phone。</span><span class="sxs-lookup"><span data-stu-id="402e0-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="402e0-123">可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。</span><span class="sxs-lookup"><span data-stu-id="402e0-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="402e0-124">在两个选项之间进行选择</span><span class="sxs-lookup"><span data-stu-id="402e0-124">Choose between the two options</span></span>

<span data-ttu-id="402e0-125">若要帮助您更好地评估最适合您的设备管理选项，请参阅在 [基本移动安全性和 Intune 之间进行选择](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)。</span><span class="sxs-lookup"><span data-stu-id="402e0-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="402e0-126">根据你的评估，开始管理设备的方式如下：</span><span class="sxs-lookup"><span data-stu-id="402e0-126">Based on your assessment, get started managing your devices with:</span></span>

- <span data-ttu-id="402e0-127">[Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)。</span><span class="sxs-lookup"><span data-stu-id="402e0-127">[Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>
- <span data-ttu-id="402e0-128">[基本移动性和安全性](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)。</span><span class="sxs-lookup"><span data-stu-id="402e0-128">[Basic Mobility and Security](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="402e0-129">标识和设备访问建议</span><span class="sxs-lookup"><span data-stu-id="402e0-129">Identity and device access recommendations</span></span>

<span data-ttu-id="402e0-130">Microsoft 提供了一组有关[身份和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。</span><span class="sxs-lookup"><span data-stu-id="402e0-130">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="402e0-131">对于设备访问，请使用这些文章中的建议和设置：</span><span class="sxs-lookup"><span data-stu-id="402e0-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="402e0-132">先决条件</span><span class="sxs-lookup"><span data-stu-id="402e0-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="402e0-133">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="402e0-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="402e0-134">Contoso 如何为 Microsoft 365 进行设备管理</span><span class="sxs-lookup"><span data-stu-id="402e0-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="402e0-135">有关虚构但具有代表性的多国企业如何使用 Microsoft 365 云服务部署其移动设备管理基础结构的信息，请参阅 [mobile device management For Contoso](contoso-mdm.md)。</span><span class="sxs-lookup"><span data-stu-id="402e0-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
