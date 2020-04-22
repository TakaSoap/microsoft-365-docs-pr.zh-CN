---
title: Autopilot 设备错误疑难解答
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 了解如何解决在 Microsoft 365 商业高级版中使用 AutoPilot 设备文件时可能会看到的错误。
ms.openlocfilehash: 0c0742e5bf17c85cedfb421cabfd87c0e2184ba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635036"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="8af65-103">Autopilot 设备错误疑难解答</span><span class="sxs-lookup"><span data-stu-id="8af65-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="8af65-104">设备文件错误消息</span><span class="sxs-lookup"><span data-stu-id="8af65-104">Device file error messages</span></span>

<span data-ttu-id="8af65-105">以下是在使用 Microsoft 365 商业高级版中的 AutoPilot 设备文件时可能会看到的一些错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="8af65-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="8af65-106">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="8af65-106">**Error code**</span></span>|<span data-ttu-id="8af65-107">**修复以试用**</span><span class="sxs-lookup"><span data-stu-id="8af65-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8af65-108">请求正文无效</span><span class="sxs-lookup"><span data-stu-id="8af65-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="8af65-109">此错误应该很少发生，如果您看到此错误，请再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="8af65-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="8af65-110">设备的硬件哈希值不正确。</span><span class="sxs-lookup"><span data-stu-id="8af65-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="8af65-111">如果看到此错误，则表示你在 CSV 文件中为一个设备的硬件哈希提供的值不正确。</span><span class="sxs-lookup"><span data-stu-id="8af65-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="8af65-112">首先，请验证是否正确键入了值。</span><span class="sxs-lookup"><span data-stu-id="8af65-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="8af65-113">如果你认为该值是正确的，但仍会发生此错误，请向你的硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="8af65-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="8af65-114">分配给另一个租户的设备</span><span class="sxs-lookup"><span data-stu-id="8af65-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="8af65-115">如果看到此错误，则表示你在 CSV 文件中提供的值是一个或多个设备的序列号或产品密钥不正确。</span><span class="sxs-lookup"><span data-stu-id="8af65-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="8af65-116">首先，请验证是否正确键入了值。</span><span class="sxs-lookup"><span data-stu-id="8af65-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="8af65-117">如果你认为该值是正确的，但仍会发生此错误，请向你的硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="8af65-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="8af65-118">CSV 文件包含无效的序列号或产品密钥</span><span class="sxs-lookup"><span data-stu-id="8af65-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="8af65-119">如果看到此错误，则表示您尝试注册的设备已由另一个组织注册。</span><span class="sxs-lookup"><span data-stu-id="8af65-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="8af65-120">若要修复此错误，请向硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="8af65-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="8af65-121">此设备不支持通过使用 AutoPilot 进行安装</span><span class="sxs-lookup"><span data-stu-id="8af65-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="8af65-122">此错误表示设备不符合 AutoPilot 部署要求。</span><span class="sxs-lookup"><span data-stu-id="8af65-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="8af65-123">设备需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="8af65-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="8af65-124">Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8af65-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="8af65-125">尚未通过 Windows 开箱即用体验的新设备。</span><span class="sxs-lookup"><span data-stu-id="8af65-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="8af65-126">找不到设备</span><span class="sxs-lookup"><span data-stu-id="8af65-126">Device not found</span></span>  <br/> |<span data-ttu-id="8af65-127">此错误表示 CSV 文件中的一个或多个设备未注册到您的组织。</span><span class="sxs-lookup"><span data-stu-id="8af65-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="8af65-128">若要解决此问题，请向硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="8af65-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
