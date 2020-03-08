---
title: Autopilot 设备错误疑难解答
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
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
description: 了解如何解决在 Microsoft 365 Business 中使用 AutoPilot 设备文件时可能看到的错误。
ms.openlocfilehash: dc1abd508156c8525859f6ca7e291ab38fc8859c
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560692"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="da368-103">Autopilot 设备错误疑难解答</span><span class="sxs-lookup"><span data-stu-id="da368-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="da368-104">设备文件错误消息</span><span class="sxs-lookup"><span data-stu-id="da368-104">Device file error messages</span></span>

<span data-ttu-id="da368-105">以下是在使用 Microsoft 365 Business 中的 AutoPilot 设备文件时可能会看到的一些错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="da368-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="da368-106">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="da368-106">**Error code**</span></span>|<span data-ttu-id="da368-107">**修复以试用**</span><span class="sxs-lookup"><span data-stu-id="da368-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da368-108">请求正文无效</span><span class="sxs-lookup"><span data-stu-id="da368-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="da368-109">此错误应该很少发生，如果您看到此错误，请再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="da368-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="da368-110">设备的硬件哈希值不正确。</span><span class="sxs-lookup"><span data-stu-id="da368-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="da368-111">如果看到此错误，则表示你在 CSV 文件中为一个设备的硬件哈希提供的值不正确。</span><span class="sxs-lookup"><span data-stu-id="da368-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="da368-112">首先，请验证是否正确键入了值。</span><span class="sxs-lookup"><span data-stu-id="da368-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="da368-113">如果你认为该值是正确的，但仍会发生此错误，请向你的硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="da368-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="da368-114">分配给另一个租户的设备</span><span class="sxs-lookup"><span data-stu-id="da368-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="da368-115">如果看到此错误，则表示你在 CSV 文件中提供的值是一个或多个设备的序列号或产品密钥不正确。</span><span class="sxs-lookup"><span data-stu-id="da368-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="da368-116">首先，请验证是否正确键入了值。</span><span class="sxs-lookup"><span data-stu-id="da368-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="da368-117">如果你认为该值是正确的，但仍会发生此错误，请向你的硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="da368-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="da368-118">CSV 文件包含无效的序列号或产品密钥</span><span class="sxs-lookup"><span data-stu-id="da368-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="da368-119">如果看到此错误，则表示您尝试注册的设备已由另一个组织注册。</span><span class="sxs-lookup"><span data-stu-id="da368-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="da368-120">若要修复此错误，请向硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="da368-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="da368-121">此设备不支持通过使用 AutoPilot 进行安装</span><span class="sxs-lookup"><span data-stu-id="da368-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="da368-122">此错误表示设备不符合 AutoPilot 部署要求。</span><span class="sxs-lookup"><span data-stu-id="da368-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="da368-123">设备需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="da368-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="da368-124">Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="da368-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="da368-125">尚未通过 Windows 开箱即用体验的新设备。</span><span class="sxs-lookup"><span data-stu-id="da368-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="da368-126">找不到设备</span><span class="sxs-lookup"><span data-stu-id="da368-126">Device not found</span></span>  <br/> |<span data-ttu-id="da368-127">此错误表示 CSV 文件中的一个或多个设备未注册到您的组织。</span><span class="sxs-lookup"><span data-stu-id="da368-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="da368-128">若要解决此问题，请向硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="da368-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
