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
ms.openlocfilehash: 1c5a06c75ede11697e2ecf17c47eb035e78dcd27
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687818"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="464f8-104">Microsoft 365 的设备管理路线图</span><span class="sxs-lookup"><span data-stu-id="464f8-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="464f8-105">适用于企业的 Microsoft 365 包括帮助管理组织内的设备及其应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="464f8-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="464f8-106">管理移动设备可帮助您保护组织的资源。</span><span class="sxs-lookup"><span data-stu-id="464f8-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="464f8-107">设备管理有两个选项。</span><span class="sxs-lookup"><span data-stu-id="464f8-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="464f8-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="464f8-108">Microsoft Intune</span></span>

<span data-ttu-id="464f8-109">Intune 为你提供了使用移动设备管理 (MDM) 或移动应用程序管理 (MAM) 管理对组织的访问权限的选项。</span><span class="sxs-lookup"><span data-stu-id="464f8-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="464f8-110">MDM 是用户在 Intune 中 "注册" 其设备。</span><span class="sxs-lookup"><span data-stu-id="464f8-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="464f8-111">注册后，它们就是受管理的设备，并且可以接收组织使用的任何策略、规则和设置。</span><span class="sxs-lookup"><span data-stu-id="464f8-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="464f8-112">例如，您可以安装特定应用程序，创建密码策略，安装 VPN 连接，等等。</span><span class="sxs-lookup"><span data-stu-id="464f8-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="464f8-113">拥有自己的个人设备的用户可能不希望注册其设备，也不能由 Intune 和你的策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="464f8-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="464f8-114">但您仍需要保护您组织的资源和数据。</span><span class="sxs-lookup"><span data-stu-id="464f8-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="464f8-115">在这种情况下，您可以使用 MAM 保护您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="464f8-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="464f8-116">例如，您可以使用一个 MAM 策略，该策略要求用户在设备上访问 SharePoint 时输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="464f8-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="464f8-117">您还将确定如何管理个人或组织拥有的设备。</span><span class="sxs-lookup"><span data-stu-id="464f8-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="464f8-118">您可能需要以不同的方式处理设备，具体取决于设备的用途。</span><span class="sxs-lookup"><span data-stu-id="464f8-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="464f8-119">从 [这里](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)开始。</span><span class="sxs-lookup"><span data-stu-id="464f8-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="464f8-120">基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="464f8-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="464f8-121">此功能内置于 Microsoft 365 中，可帮助您保护和管理用户的移动设备，如 Iphone、Ipad、Androids 和 Windows phone。</span><span class="sxs-lookup"><span data-stu-id="464f8-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="464f8-122">可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。</span><span class="sxs-lookup"><span data-stu-id="464f8-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="464f8-123">从 [这里](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)开始。</span><span class="sxs-lookup"><span data-stu-id="464f8-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="464f8-124">标识和设备访问建议</span><span class="sxs-lookup"><span data-stu-id="464f8-124">Identity and device access recommendations</span></span>

<span data-ttu-id="464f8-125">Microsoft 提供了一组有关[身份和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。</span><span class="sxs-lookup"><span data-stu-id="464f8-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="464f8-126">对于设备访问，请使用以下文章中的建议和设置以及此阶段中的步骤：</span><span class="sxs-lookup"><span data-stu-id="464f8-126">For device access, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="464f8-127">先决条件</span><span class="sxs-lookup"><span data-stu-id="464f8-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="464f8-128">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="464f8-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-device-management-for-microsoft-365"></a><span data-ttu-id="464f8-129">Microsoft 如何将设备管理用于 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="464f8-129">How Microsoft does device management for Microsoft 365</span></span>

<span data-ttu-id="464f8-130">了解 Microsoft IT 专家如何 [使用 EMS 管理设备](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8)。</span><span class="sxs-lookup"><span data-stu-id="464f8-130">Learn how IT experts at Microsoft [manage devices with EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).</span></span>

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="464f8-131">Contoso 如何为 Microsoft 365 进行设备管理</span><span class="sxs-lookup"><span data-stu-id="464f8-131">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="464f8-132">了解 Contoso Corporation （一个虚构但具有代表性的多国企业）如何使用 Microsoft 365 云服务 [部署其移动设备管理基础结构](contoso-mdm.md) 。</span><span class="sxs-lookup"><span data-stu-id="464f8-132">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)
