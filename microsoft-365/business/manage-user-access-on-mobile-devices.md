---
title: 管理用户访问移动设备上的 Office 文档的方式
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 了解允许你管理用户如何从移动设备Office应用和工作文件的保护策略。
ms.openlocfilehash: 7602b712f2dfc3ba369fd76979baaaa8d5da5c5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925271"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>管理用户访问移动设备上的 Office 文档的方式

本文适用于Microsoft 365 商业高级版。

用于控制用户如何在移动设备上访问 Office 文件的策略默认设置为" **关闭**"。 建议在设置过程中接受默认值，为适用于所有用户的 Android、iOS 和 Windows 10创建应用程序策略。 在设置完成后，可以创建多个策略。 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>用于控制用户如何在移动设备上访问 Office 文件的设置

以下设置可用于管理用户访问 Office 工作文件的方式：

|设置  <br/> |说明  <br/> |
|:-----|:-----|
|需要 PIN 或指纹才能访问 Office 应用  <br/> |如果此设置为 **"打开**"，则除了用户名和密码之外，用户还必须提供另一种形式的身份验证，然后才能在移动设备上Office应用。  <br/> |
|登录失败以下次数后重置 PIN  <br/> |若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。  <br/> |
|要求用户在 Office 应用空闲以下时间后重新登录  <br/> |此设置确定用户在系统提示重新登录之前可以处于空闲状态的时间。  <br/> |
|在已越狱或取得 root 权限的设备上拒绝对工作文件的访问  <br/> |一些聪明的用户的设备可能已越狱或取得 root 权限。 这意味着用户可以修改操作系统，这会使设备更容易受到恶意软件的攻击。 如果此设置为" **打开**"，会阻止这些设备。  <br/> |
|不允许用户将内容从应用Office个人应用中  <br/> |当设置为 **"打开"** 时，用户不能将工作文件中的信息复制到个人文件中。 如果设置为" **关闭"，** 用户可以将工作文件中的信息复制到个人应用或个人帐户。  <br/> |
   

