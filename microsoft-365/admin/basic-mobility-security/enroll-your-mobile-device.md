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
description: 你可能需要先在 Microsoft 365 的基本移动和安全性中对其进行注册，然后才能将 Microsoft 365 服务用于你的设备。
ms.openlocfilehash: e31054621ba44a4d5f08de9b366fa0978b738cd9
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430093"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="93b43-103">使用基本移动性和安全性注册移动设备</span><span class="sxs-lookup"><span data-stu-id="93b43-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="93b43-104">使用手机、平板电脑和其他移动设备进行工作是在离开办公室时随时了解并处理业务项目的极好方法。</span><span class="sxs-lookup"><span data-stu-id="93b43-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="93b43-105">你可能需要先使用 microsoft Intune 公司门户在 Microsoft 365 的基本移动性和安全性中对其进行注册，然后才能将 Microsoft 365 服务用于你的设备。</span><span class="sxs-lookup"><span data-stu-id="93b43-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="93b43-106">组织选择基本移动性和安全性，以便员工可以使用其移动设备来安全地访问工作电子邮件、日历和文档，同时企业保护重要数据并满足其合规性要求。</span><span class="sxs-lookup"><span data-stu-id="93b43-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="93b43-107">若要了解详细信息，请参阅 [Microsoft 365 的基本移动性和安全性概述](overview.md)。</span><span class="sxs-lookup"><span data-stu-id="93b43-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="93b43-108">有关详细信息，请参阅 [在注册设备时我的组织可以看到哪些信息？](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="93b43-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="93b43-109">在 Microsoft 365 的基本移动性和安全性中注册设备时，可能需要设置密码，并允许您的工作组织的选项来擦除设备。</span><span class="sxs-lookup"><span data-stu-id="93b43-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="93b43-110">可以从 Microsoft 365 管理中心执行设备擦除，例如，如果输入的密码的次数过多，或者输入的使用期限是否断开，则删除设备中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="93b43-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="93b43-111">支持的设备</span><span class="sxs-lookup"><span data-stu-id="93b43-111">Supported devices</span></span>

<span data-ttu-id="93b43-112">由 Intune 服务托管的 Microsoft 365 的基本移动性和安全性适用于大多数（但不是所有）移动设备。</span><span class="sxs-lookup"><span data-stu-id="93b43-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="93b43-113">基本移动性和安全性支持以下各项：</span><span class="sxs-lookup"><span data-stu-id="93b43-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="93b43-114">iOS 10.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="93b43-114">iOS 10.0 or later</span></span>
    
- <span data-ttu-id="93b43-115">Android 4.4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="93b43-115">Android 4.4 or later</span></span>
    
- <span data-ttu-id="93b43-116">Windows 8.1 和 Windows 10 (电话和电脑) </span><span class="sxs-lookup"><span data-stu-id="93b43-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>
    
<span data-ttu-id="93b43-117">如果你的设备未在上面列出，且你需要将其用于基本移动性和安全性，请与你的工作或学校管理员联系。</span><span class="sxs-lookup"><span data-stu-id="93b43-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP] 
><span data-ttu-id="93b43-118">如果在注册设备时遇到问题，请参阅 [基本移动性和安全性疑难解答](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="93b43-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="93b43-119">使用 Intune 和基本移动性和安全性设置移动设备</span><span class="sxs-lookup"><span data-stu-id="93b43-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="93b43-120">Intune 公司门户使设备能够通过 Microsoft 365 和基本移动性和安全性进行管理。</span><span class="sxs-lookup"><span data-stu-id="93b43-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="93b43-121">iPhone 或 iPad</span><span class="sxs-lookup"><span data-stu-id="93b43-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="93b43-122">在完成此步骤之前，您将无法发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="93b43-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="93b43-123">转到 Apple 应用商店，并下载并安装 Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="93b43-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="93b43-124">若要使用公司门户将 iOS 电话或平板电脑连接并配置到 Office 365，请参阅 [设置对公司资源的 ios 设备访问](https://go.microsoft.com/fwlink/?linkid=875316)。</span><span class="sxs-lookup"><span data-stu-id="93b43-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="93b43-125">Android 手机或平板电脑</span><span class="sxs-lookup"><span data-stu-id="93b43-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="93b43-126">在完成此步骤之前，您将无法发送和接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="93b43-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="93b43-127">转到 Google Play 商店，并下载并安装 Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="93b43-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="93b43-128">若要使用公司门户将 Android 手机或平板电脑连接并配置为 Microsoft 365，请参阅 [使用公司门户注册设备](https://go.microsoft.com/fwlink/?linkid=875317)。</span><span class="sxs-lookup"><span data-stu-id="93b43-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="93b43-129">Windows 8.1 和 Windows 10</span><span class="sxs-lookup"><span data-stu-id="93b43-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="93b43-130">转到 Microsoft Store，下载并安装 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="93b43-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="93b43-131">若要使用公司门户将 Windows phone 或电脑与 Microsoft 365 连接并配置为 Microsoft，请参阅 [Intune 公司门户中的 windows 设备注册](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="93b43-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="93b43-132">下一步做什么？</span><span class="sxs-lookup"><span data-stu-id="93b43-132">What's next?</span></span>

<span data-ttu-id="93b43-133">在基本移动性和安全性中注册设备后，您可以开始使用设备上的 Office 应用来处理电子邮件、日历、联系人和文档。</span><span class="sxs-lookup"><span data-stu-id="93b43-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>