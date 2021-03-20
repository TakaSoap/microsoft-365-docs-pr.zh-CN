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
ms.openlocfilehash: e74a5df6d10f8f3fb7b420e428380af97ba75597
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906248"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="34963-103">Microsoft 365 的基本移动性和安全性概述</span><span class="sxs-lookup"><span data-stu-id="34963-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="34963-104">当移动设备连接到 Microsoft 365 组织时，可以使用基本移动性和安全性来管理这些设备，并保护这些设备的安全。</span><span class="sxs-lookup"><span data-stu-id="34963-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="34963-105">用于访问工作电子邮件、日历、联系人及文档的移动设备（如智能手机和平板电脑）在确保员工随时随地完成工作方面起着非常重要的作用。</span><span class="sxs-lookup"><span data-stu-id="34963-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="34963-106">因此，在用户使用设备时，帮助保护组织的信息至关重要。</span><span class="sxs-lookup"><span data-stu-id="34963-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="34963-107">您可以使用基本移动性和安全性设置设备安全策略和访问规则，以及擦除丢失或被盗的移动设备。</span><span class="sxs-lookup"><span data-stu-id="34963-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="基本移动和安装程序":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="34963-109">您可以管理哪些类型的设备？</span><span class="sxs-lookup"><span data-stu-id="34963-109">What types of devices can you manage?</span></span>

<span data-ttu-id="34963-110">您可以使用基本移动性和安全性来管理许多类型的移动设备，如 Windows Phone、Android、iPhone 和 iPad。</span><span class="sxs-lookup"><span data-stu-id="34963-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="34963-111">要管理组织中人员使用的移动设备，每个人必须具有适用的 Microsoft 365 许可证，并且其设备必须在基本移动性和安全性中注册。</span><span class="sxs-lookup"><span data-stu-id="34963-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="34963-112">若要了解基本移动性和安全性支持每种类型的设备，请参阅 [Capabilities of Basic Mobility and Security。](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="34963-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="34963-113">基本移动性和安全性的安装步骤</span><span class="sxs-lookup"><span data-stu-id="34963-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="34963-114">Microsoft 365 全局管理员必须完成以下步骤才能激活和设置基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="34963-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="34963-115">有关详细步骤，请按照设置基本 [移动性和安全性中的指导操作](set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="34963-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="34963-116">以下是步骤摘要：</span><span class="sxs-lookup"><span data-stu-id="34963-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="34963-117">**步骤 1：** 按照设置基本移动性和安全性 中的步骤激活  [基本移动性和安全性](set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="34963-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="34963-118">**步骤 2：** 例如，通过创建用于管理 iOS 设备的 APNs 证书和为域添加域名系统 (DNS) 记录以支持 Windows 电话来设置基本移动性和安全性。</span><span class="sxs-lookup"><span data-stu-id="34963-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="34963-119">**步骤 3：** 创建设备策略，并应用于用户组。</span><span class="sxs-lookup"><span data-stu-id="34963-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="34963-120">当你这样做时，你的用户会在你的设备上收到注册消息，当他们完成注册后，他们的设备将受限于你为它们设置的策略。</span><span class="sxs-lookup"><span data-stu-id="34963-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="34963-121">有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="34963-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全和移动策略设置":::

## <a name="device-management-tasks"></a><span data-ttu-id="34963-123">设备管理任务</span><span class="sxs-lookup"><span data-stu-id="34963-123">Device management tasks</span></span>

<span data-ttu-id="34963-124">在设置基本移动性和安全性并且用户已注册其设备后，你可以管理设备、阻止访问或擦除设备（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="34963-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="34963-125">若要了解有关一些常见设备管理任务（包括完成任务位置）的信息，请参阅管理 [在 Microsoft 365](manage-enrolled-devices.md)移动设备管理中注册的设备。</span><span class="sxs-lookup"><span data-stu-id="34963-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="34963-126">管理设备和应用的其他方法</span><span class="sxs-lookup"><span data-stu-id="34963-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="34963-127">如果你只需使用 MAM (移动应用) ，也许对于在其自己的设备上更新工作项目的人，Intune 提供了除注册和管理设备之外的另一个选项。</span><span class="sxs-lookup"><span data-stu-id="34963-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="34963-128">Intune 订阅允许你使用 Azure 门户设置 MAM 策略，即使用户的设备未在 Intune 中注册。</span><span class="sxs-lookup"><span data-stu-id="34963-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="34963-129">有关详细信息，请参阅应用 [保护策略概述](/mem/intune/apps/app-protection-policy)。</span><span class="sxs-lookup"><span data-stu-id="34963-129">For more info, see [App protection policies overview](/mem/intune/apps/app-protection-policy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="34963-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="34963-130">Related topics</span></span>

[<span data-ttu-id="34963-131">设置基本移动性和安全性</span><span class="sxs-lookup"><span data-stu-id="34963-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="34963-132">使用基本移动性和安全性注册移动设备</span><span class="sxs-lookup"><span data-stu-id="34963-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="34963-133">管理在 Microsoft 365 移动设备管理中注册的设备</span><span class="sxs-lookup"><span data-stu-id="34963-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="34963-134">获取有关由基本移动性和安全性管理的设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="34963-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)