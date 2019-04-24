---
title: Autopilot 设备错误疑难解答
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
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 了解如何对 AutoPilot 设备文件错误进行故障排除。
ms.openlocfilehash: 9d4a47f78c38d8c076f5b3876a36b6bf46eaaaf3
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279830"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Autopilot 设备错误疑难解答

## <a name="device-file-error-messages"></a>设备文件错误消息

以下是在使用 Microsoft 365 Business 中的 AutoPilot 设备文件时可能会看到的一些错误的相关信息。 
  
|**错误代码**|**修复以试用**|
|:-----|:-----|
|请求正文无效  <br/> |此错误应该很少发生, 如果您看到此错误, 请再次尝试该操作。  <br/> |
|设备的硬件哈希值不正确。  <br/> |如果看到此错误, 则表示你在 CSV 文件中为一个设备的硬件哈希提供的值不正确。 首先, 请验证是否正确键入了值。 如果你认为该值是正确的, 但仍会发生此错误, 请向你的硬件供应商寻求帮助。  <br/> |
|分配给另一个租户的设备  <br/> |如果看到此错误, 则表示你在 CSV 文件中提供的值是一个或多个设备的序列号或产品密钥不正确。 首先, 请验证是否正确键入了值。 如果你认为该值是正确的, 但仍会发生此错误, 请向你的硬件供应商寻求帮助。  <br/> |
|CSV 文件包含无效的序列号或产品密钥  <br/> |如果看到此错误, 则表示您要注册的设备已由其他组织注册 tyring。 若要解决此问题, 请向硬件供应商寻求帮助。  <br/> |
|此设备不支持通过使用 AutoPilot 进行安装  <br/> | 此错误表示设备不符合 AutoPilot 部署要求。 设备需要满足以下要求：  <br/>  Windows 10 版本 1703 或更高版本。  <br/>  未获得过 Windows 现成体验的新设备。  <br/> |
|找不到设备  <br/> |此错误表示 CSV 文件中的一个或多个设备未注册到您的组织。 若要解决此问题, 请向硬件供应商寻求帮助。  <br/> |
   
