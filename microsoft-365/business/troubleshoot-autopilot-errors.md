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
# <a name="troubleshoot-autopilot-device-errors"></a>解决 AutoPilot 设备错误

## <a name="device-file-error-messages"></a>设备文件的错误消息

下面是一些错误信息可能会看到时使用 Microsoft 365 企业版中的自动执行某些操作设备文件。 
  
|**错误代码**|**修复尝试**|
|:-----|:-----|
|无效请求正文  <br/> |应很少，发生此错误，如果您看到此错误，再次尝试该操作。  <br/> |
|设备硬件哈希值不正确。  <br/> |如果您看到此错误，则意味着您的设备硬件哈希值的 CSV 文件中提供的值不正确。首先，确认已正确键入的值。如果您认为的值正确，但仍然发生此错误，可将硬件供应商寻求帮助。  <br/> |
|分配给另一个租户的设备  <br/> |如果您看到此错误，则意味着为的序列号或产品密钥的一个或多个设备的 CSV 文件中提供的值不正确。首先，确认已正确键入的值。如果您认为的值正确，但仍然发生此错误，可将硬件供应商寻求帮助。  <br/> |
|CSV 文件包含无效的序列号或产品密钥  <br/> |如果您看到此错误意味着要尝试注册的设备都由其他组织已注册。若要解决此问题，请将硬件供应商寻求帮助。  <br/> |
|此设备使用自动执行某些操作不支持的安装程序  <br/> | 此错误表示设备不符合自动执行某些操作部署要求。设备需要满足以下要求：  <br/>  Windows 10 版本 1703 或更高版本。  <br/>  未获得过 Windows 现成体验的新设备。  <br/> |
|找不到设备  <br/> |此错误表示的 CSV 文件中的一个或多个设备未注册您的组织。若要解决此问题，请将硬件供应商寻求帮助。  <br/> |
   
