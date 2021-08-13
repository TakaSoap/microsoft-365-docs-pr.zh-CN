---
title: Autopilot 设备错误疑难解答
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 了解如何解决在设备上使用 AutoPilot 设备文件时可能Microsoft 365 商业高级版。
ms.openlocfilehash: b74c57acbaa5682f6db97e7d8a090e6e28a40dcc3246f00cacc7984cb52cc758
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53809172"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Autopilot 设备错误疑难解答

## <a name="device-file-error-messages"></a>设备文件错误消息

以下是在设备上使用 AutoPilot 设备文件时可能看到的一Microsoft 365 商业高级版。 
  
|**错误代码**|**修复以尝试**|
|:-----|:-----|
|无效的请求正文  <br/> |此错误应该很少发生，如果看到此错误，请再次尝试该操作。  <br/> |
|设备的硬件哈希值不正确。  <br/> |如果看到此错误，则意味着 CSV 文件中为一台设备的硬件哈希提供的值不正确。 首先，验证键入的值是否正确。 如果您认为值正确，但此错误仍在发生，请咨询您的硬件供应商寻求帮助。  <br/> |
|分配给另一个租户的设备  <br/> |如果看到此错误，则意味着你在 CSV 文件中为一个或多个设备的序列号或产品密钥提供的值不正确。 首先，验证键入的值是否正确。 如果您认为值正确，但此错误仍在发生，请咨询您的硬件供应商寻求帮助。  <br/> |
|CSV 文件包含无效的序列号或产品密钥  <br/> |如果看到此错误，则意味着你尝试注册的设备已由另一个组织注册。 若要修复此错误，请向硬件供应商寻求帮助。  <br/> |
|此设备不支持使用 AutoPilot 进行设置  <br/> | 此错误意味着设备不符合 AutoPilot 部署要求。 设备需要满足以下要求：  <br/>  Windows 10 版本 1703 或更高版本。  <br/>  尚未体验全新体验Windows全新体验。  <br/> |
|未找到设备  <br/> |此错误意味着 CSV 文件的一个或多个设备未注册到组织。 若要解决此问题，请向硬件供应商寻求帮助。  <br/> |
