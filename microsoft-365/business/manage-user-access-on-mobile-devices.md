---
title: 管理用户访问移动设备上的 Office 文档的方式
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 了解有关保护策略，可从移动设备对 Office 应用程序帮助的安全访问。
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865714"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>管理用户访问移动设备上的 Office 文档的方式

 用于控制用户如何在移动设备上访问 Office 文件的策略默认设置为" **关闭**"。建议在设置过程中接受默认值，创建适用于所有用户的 Android、iOS 和 Windows 10 应用程序策略。在设置完成后，可以创建多个策略。 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>用于控制用户如何在移动设备上访问 Office 文件的设置

以下设置可用于管理用户访问 Office 工作文件的方式：
  
|||
|:-----|:-----|
|设置  <br/> |说明  <br/> |
|需要 PIN 或指纹才能访问 Office 应用  <br/> |如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。  <br/> |
|登录失败以下次数后重置 PIN  <br/> |若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。  <br/> |
|要求用户在 Office 应用空闲以下时间后重新登录  <br/> |此设置确定用户保持空闲状态多久后系统会提示再次登录。  <br/> |
|在已越狱或取得 root 权限的设备上拒绝对工作文件的访问  <br/> |一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **开** "，会阻止这些设备。  <br/> |
|允许用户从 Office 应用将内容复制到个人应用  <br/> |默认允许此设置，但设置为" **打开**"时，用户可以将工作文件中的信息复制到个人文件。如果设置为" **关闭**"，用户无法将工作文件中的信息复制到个人应用或个人帐户。  <br/> |
   

