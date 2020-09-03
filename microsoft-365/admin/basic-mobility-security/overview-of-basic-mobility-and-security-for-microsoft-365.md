---
title: Microsoft 365 的基本移动性和安全性概述
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
description: 使用基本移动性和安全性设置设备安全策略和访问规则。
ms.openlocfilehash: 7c1a4bc5ddf476463788f99305215ee6853190f1
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336740"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="f0670-103">Microsoft 365 的基本移动性和安全性概述</span><span class="sxs-lookup"><span data-stu-id="f0670-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="f0670-104">使用基本移动性和安全性连接到 Microsoft 365 组织时，可以管理和保护移动设备。</span><span class="sxs-lookup"><span data-stu-id="f0670-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="f0670-105">用于访问工作电子邮件、日历、联系人及文档的移动设备（如智能手机和平板电脑）在确保员工随时随地完成工作方面起着非常重要的作用。</span><span class="sxs-lookup"><span data-stu-id="f0670-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="f0670-106">因此，在用户使用设备时，帮助保护组织的信息非常关键。</span><span class="sxs-lookup"><span data-stu-id="f0670-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="f0670-107">您可以使用基本移动性和安全性来设置设备安全策略和访问规则，并在移动设备丢失或被盗时将其擦除。</span><span class="sxs-lookup"><span data-stu-id="f0670-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本移动性和安全设置":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="f0670-109">您可以管理哪些类型的设备？</span><span class="sxs-lookup"><span data-stu-id="f0670-109">What types of devices can you manage?</span></span>

<span data-ttu-id="f0670-110">您可以使用基本移动性和安全性来管理多种类型的移动设备，如 Windows Phone、Android、iPhone 和 iPad。</span><span class="sxs-lookup"><span data-stu-id="f0670-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="f0670-111">若要管理组织中的人员使用的移动设备，每个人都必须具有适用的 Microsoft 365 许可证，并且其设备必须在基本移动性和安全性中进行注册。</span><span class="sxs-lookup"><span data-stu-id="f0670-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="f0670-112">若要查看每种类型的设备的基本移动性和安全性支持，请参阅 [基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)。</span><span class="sxs-lookup"><span data-stu-id="f0670-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="f0670-113">基本移动性和安全性的设置步骤</span><span class="sxs-lookup"><span data-stu-id="f0670-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="f0670-114">Microsoft 365 全局管理员必须完成以下步骤才能激活和设置基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="f0670-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="f0670-115">有关详细步骤，请按照 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)中的指导进行操作。</span><span class="sxs-lookup"><span data-stu-id="f0670-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span> 

<span data-ttu-id="f0670-116">以下是这些步骤的摘要：</span><span class="sxs-lookup"><span data-stu-id="f0670-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="f0670-117">**步骤1：** 按照 [设置基本移动性和安全性](set-up-basic-mobility-and-security.md)中的步骤激活基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="f0670-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>

<span data-ttu-id="f0670-118">**步骤2：** 设置基本移动性和安全性，例如，创建用于管理 iOS 设备的 APNs 证书和添加域名系统 (域的 DNS) 记录以支持 Windows phone。</span><span class="sxs-lookup"><span data-stu-id="f0670-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="f0670-119">**步骤3：** 创建设备策略并将其应用到用户组。</span><span class="sxs-lookup"><span data-stu-id="f0670-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="f0670-120">在执行此操作时，用户将在其设备上获取注册消息，并在完成注册后，其设备将受到您为其设置的策略的限制。</span><span class="sxs-lookup"><span data-stu-id="f0670-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="f0670-121">有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device-using-basic-mobility-and-security.md)。</span><span class="sxs-lookup"><span data-stu-id="f0670-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全性和移动性策略设置":::

## <a name="device-management-tasks"></a><span data-ttu-id="f0670-123">设备管理任务</span><span class="sxs-lookup"><span data-stu-id="f0670-123">Device management tasks</span></span>

<span data-ttu-id="f0670-124">在设置了基本的移动性和安全性并对用户注册了其设备之后，您可以管理设备、阻止访问或擦除设备（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="f0670-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="f0670-125">若要了解有关一些常见设备管理任务（包括在何处完成这些任务）的详细信息，请参阅 [管理在 Microsoft 365 的移动设备管理中注册的设备](manage-devices-enrolled-in-mdm-in-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f0670-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-devices-enrolled-in-mdm-in-microsoft-365.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="f0670-126">管理设备和应用程序的其他方法</span><span class="sxs-lookup"><span data-stu-id="f0670-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="f0670-127">如果只需要移动应用管理 (MAM) （可能是用户在自己的设备上更新工作项目），Intune 除了注册和管理设备之外，还提供另一个选项。</span><span class="sxs-lookup"><span data-stu-id="f0670-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="f0670-128">Intune 订阅允许你使用 Azure 门户设置 MAM 策略，即使用户的设备未在 Intune 中注册也是如此。</span><span class="sxs-lookup"><span data-stu-id="f0670-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="f0670-129">有关详细信息，请参阅 [App protection 策略概述](https://go.microsoft.com/fwlink/?LinkId=2132517)。</span><span class="sxs-lookup"><span data-stu-id="f0670-129">For more info, see [App protection policies overview](https://go.microsoft.com/fwlink/?LinkId=2132517).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f0670-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="f0670-130">Related topics</span></span>

[<span data-ttu-id="f0670-131">设置基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="f0670-131">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)

[<span data-ttu-id="f0670-132">使用基本移动性和安全性注册移动设备</span><span class="sxs-lookup"><span data-stu-id="f0670-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device-using-basic-mobility-and-security.md)

[<span data-ttu-id="f0670-133">管理在 Microsoft 365 的移动设备管理中注册的设备</span><span class="sxs-lookup"><span data-stu-id="f0670-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-devices-enrolled-in-mdm-in-microsoft-365.md)

[<span data-ttu-id="f0670-134">获取有关由基本移动性和安全性管理的设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="f0670-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-basic-mobility-and-security-managed-devices.md)