---
title: 关于"AutoPilot 配置文件"设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自动执行某些操作配置文件可帮助您控制如何获取 Windows 安装到用户设备上。配置文件包含默认和可选设置如跳过 Cortana 安装。
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865425"
---
# <a name="about-autopilot-profile-settings"></a>关于"AutoPilot 配置文件"设置

## <a name="autopilot-profile-settings"></a>自动执行某些操作配置文件设置

您可以控制 Windows 获取如何通过使用自动执行某些操作配置文件安装到用户设备上。配置文件包含以下设置。
  
 **自动执行某些操作默认 （必需） 的功能将自动设置：**
  
|**设置**|**说明**|
|:-----|:-----|
|跳过 Cortana、 OneDrive 和 OEM 注册  <br/> |跳过使用者应用程序，如 Cortana 和个人 OneDrive 的安装。只要他或她是在设备上的本地管理员，则设备用户可以安装这些更高版本。原始制造商注册被跳过，因为设备将由 Microsoft 365 企业版。  <br/> |
|登录体验与您公司品牌  <br/> |如果您的公司具有[添加贵公司品牌到 Office 365 登录页](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)，设备用户在登录后获得的体验。  <br/> |
|MDM 自动注册配置 AAD 帐户。  <br/> |将由 Azure Active directory，来管理用户标识和用户将使用其 Microsoft 365 业务凭据登录到 Windows 和 Office 365。  <br/> |
   
 **可选设置：**
  
|**设置**|**说明**|
|:-----|:-----|
|跳过隐私设置 （默认情况下关闭）  <br/> |如果此选项设置为**在**设备用户将不会看到设备和窗口的许可协议，他/她第一次登录时。  <br/> |
|不允许用户成为本地管理员  <br/> |如果此选项设置为**在**设备用户不能安装任何个人的应用程序，如 Cortana。  <br/> |
   
