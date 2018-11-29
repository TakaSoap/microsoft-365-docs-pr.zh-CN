---
title: 解决 AutoPilot 设备错误
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 了解如何解决自动执行某些操作设备文件错误。
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865579"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="977dd-103">解决 AutoPilot 设备错误</span><span class="sxs-lookup"><span data-stu-id="977dd-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="977dd-104">设备文件的错误消息</span><span class="sxs-lookup"><span data-stu-id="977dd-104">Device file error messages</span></span>

<span data-ttu-id="977dd-105">下面是一些错误信息可能会看到时使用 Microsoft 365 企业版中的自动执行某些操作设备文件。</span><span class="sxs-lookup"><span data-stu-id="977dd-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="977dd-106">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="977dd-106">**Error code**</span></span>|<span data-ttu-id="977dd-107">**修复尝试**</span><span class="sxs-lookup"><span data-stu-id="977dd-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="977dd-108">无效请求正文</span><span class="sxs-lookup"><span data-stu-id="977dd-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="977dd-109">应很少，发生此错误，如果您看到此错误，再次尝试该操作。</span><span class="sxs-lookup"><span data-stu-id="977dd-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="977dd-110">设备硬件哈希值不正确。</span><span class="sxs-lookup"><span data-stu-id="977dd-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="977dd-p101">如果您看到此错误，则意味着您的设备硬件哈希值的 CSV 文件中提供的值不正确。首先，确认已正确键入的值。如果您认为的值正确，但仍然发生此错误，可将硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="977dd-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="977dd-114">分配给另一个租户的设备</span><span class="sxs-lookup"><span data-stu-id="977dd-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="977dd-p102">如果您看到此错误，则意味着为的序列号或产品密钥的一个或多个设备的 CSV 文件中提供的值不正确。首先，确认已正确键入的值。如果您认为的值正确，但仍然发生此错误，可将硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="977dd-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="977dd-118">CSV 文件包含无效的序列号或产品密钥</span><span class="sxs-lookup"><span data-stu-id="977dd-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="977dd-p103">如果您看到此错误意味着要尝试注册的设备都由其他组织已注册。若要解决此问题，请将硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="977dd-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="977dd-121">此设备使用自动执行某些操作不支持的安装程序</span><span class="sxs-lookup"><span data-stu-id="977dd-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="977dd-p104">此错误表示设备不符合自动执行某些操作部署要求。设备需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="977dd-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="977dd-124">Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="977dd-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="977dd-125">未获得过 Windows 现成体验的新设备。</span><span class="sxs-lookup"><span data-stu-id="977dd-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="977dd-126">找不到设备</span><span class="sxs-lookup"><span data-stu-id="977dd-126">Device not found</span></span>  <br/> |<span data-ttu-id="977dd-p105">此错误表示的 CSV 文件中的一个或多个设备未注册您的组织。若要解决此问题，请将硬件供应商寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="977dd-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
