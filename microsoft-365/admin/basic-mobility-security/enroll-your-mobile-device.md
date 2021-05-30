---
title: 使用基本移动性和安全性注册移动设备
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
description: 在设备上Microsoft 365服务之前，可能需要先在基本移动性和安全性中注册Microsoft 365。
ms.openlocfilehash: 2ad0aac331969696bbf53d0b06c18ee5c0ee90f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706162"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="2accc-103">使用基本移动性和安全性注册移动设备</span><span class="sxs-lookup"><span data-stu-id="2accc-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="2accc-104">当你离开办公室时，使用手机、平板电脑和其他移动设备工作是了解情况并处理业务项目的一种很好的方法。</span><span class="sxs-lookup"><span data-stu-id="2accc-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="2accc-105">在设备上Microsoft 365服务之前，可能需要先使用 Microsoft Intune 公司门户 在基本移动性和安全性中注册Microsoft 365服务。</span><span class="sxs-lookup"><span data-stu-id="2accc-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="2accc-106">组织选择"基本移动性和安全性"，以便员工可以使用其移动设备安全地访问工作电子邮件、日历和文档，同时企业保护重要数据并满足其合规性要求。</span><span class="sxs-lookup"><span data-stu-id="2accc-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="2accc-107">若要了解更多信息，请参阅[Overview of Basic Mobility and Security for Microsoft 365](overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2accc-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="2accc-108">有关详细信息，请参阅 [我的组织在注册我的设备时会看到哪些信息？。](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)</span><span class="sxs-lookup"><span data-stu-id="2accc-108">For more info, see [What information can my organization see when I enroll my device?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="2accc-109">在基本移动性和安全性 for Microsoft 365 中注册设备时，可能需要设置密码，同时允许工作组织选择擦除设备。</span><span class="sxs-lookup"><span data-stu-id="2accc-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="2accc-110">例如，如果密码输入错误次数过多或使用条款损坏，可以从 Microsoft 365管理中心执行设备擦除以删除设备的所有数据。</span><span class="sxs-lookup"><span data-stu-id="2accc-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="2accc-111">支持的设备</span><span class="sxs-lookup"><span data-stu-id="2accc-111">Supported devices</span></span>

<span data-ttu-id="2accc-112">Intune 服务Microsoft 365用户的基本移动性和安全性适用于大多数（而不是全部）移动设备。</span><span class="sxs-lookup"><span data-stu-id="2accc-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="2accc-113">基本移动性和安全性支持以下内容：</span><span class="sxs-lookup"><span data-stu-id="2accc-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="2accc-114">iOS 10.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2accc-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="2accc-115">Android 4.4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2accc-115">Android 4.4 or later</span></span>

- <span data-ttu-id="2accc-116">Windows 8.1和Windows 10 (电话电脑) </span><span class="sxs-lookup"><span data-stu-id="2accc-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="2accc-117">如果你的设备未在上方列出，并且你需要将该设备与基本移动性和安全性一同使用，请与你的工作或学校管理员联系。</span><span class="sxs-lookup"><span data-stu-id="2accc-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="2accc-118">如果你在注册设备时遇到问题，请参阅解决 [基本移动性和安全性问题](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="2accc-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="2accc-119">使用 Intune 和基本移动性和安全性设置移动设备</span><span class="sxs-lookup"><span data-stu-id="2accc-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="2accc-120">此Intune 公司门户使设备能够由 Microsoft 365 和基本移动性和安全性进行管理。</span><span class="sxs-lookup"><span data-stu-id="2accc-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="2accc-121">iPhone 或 iPad</span><span class="sxs-lookup"><span data-stu-id="2accc-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="2accc-122">完成此步骤之前，你将无法发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2accc-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="2accc-123">转到 Apple App Store，然后下载并安装Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="2accc-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="2accc-124">若要通过公司门户连接和配置 iOS 手机或平板电脑Office 365，请参阅设置[iOS 设备对公司资源的访问](/mem/intune/user-help/enroll-your-device-in-intune-ios)。</span><span class="sxs-lookup"><span data-stu-id="2accc-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](/mem/intune/user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="2accc-125">Android 手机或平板电脑</span><span class="sxs-lookup"><span data-stu-id="2accc-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="2accc-126">完成此步骤之前，你将无法发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2accc-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="2accc-127">转到 Google Play 商店，然后下载并安装Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="2accc-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="2accc-128">若要使用公司门户连接和配置 Android 手机或平板电脑Microsoft 365，请参阅使用 公司门户[注册设备](/mem/intune/user-help/enroll-device-android-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="2accc-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="2accc-129">Windows 8.1 和 Windows 10</span><span class="sxs-lookup"><span data-stu-id="2accc-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="2accc-130">转到"Microsoft Store"，然后下载并安装Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="2accc-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="2accc-131">若要使用公司门户Windows和配置 Windows 电话或电脑Microsoft 365，请参阅 Windows[中的](/intune-user-help/windows-enrollment-company-portal)Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="2accc-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2accc-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2accc-132">Next steps</span></span>

<span data-ttu-id="2accc-133">在设备注册基本移动性和安全性后，你可以开始使用Office应用处理电子邮件、日历、联系人和文档。</span><span class="sxs-lookup"><span data-stu-id="2accc-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>