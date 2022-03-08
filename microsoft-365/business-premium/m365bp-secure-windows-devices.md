---
title: 安全Windows设备
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 了解如何配置设备登录工作或学校帐户Windows接收的默认设备策略的设置。
ms.openlocfilehash: b58e63abf19c3078eb5d4356b155df13804c95d5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330720"
---
# <a name="secure-windows-devices"></a>安全Windows设备

本文适用于Microsoft 365 商业高级版。

此处配置的设置是默认设备策略的一部分，Windows 10 11。 通过使用工作帐户Windows移动设备和电脑）连接移动设备的所有用户将自动收到这些设置。 建议在设置过程中接受默认策略，稍后添加面向特定用户组的策略。
  
## <a name="settings-to-secure-windows-10-devices"></a>保护 Windows 10 设备的设置

默认情况下，所有设置为" **打开**"。可使用以下设置：<br/><br/>

|Setting  <br/> |说明  <br/> |
|:-----|:-----|
|使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁  <br/> |需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。  <br/> |
|帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁  <br/> |在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。  <br/> |
|使用 BitLocker 帮助保护 PC 上的文件和文件夹免遭未经授权的访问  <br/> |BitLocker 通过加密计算机硬盘驱动器来保护数据，在计算机丢失或被盗时防止数据泄露。 有关详细信息，请参阅 [BitLocker 常见问题](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)解答。  <br/> |
|在空闲此时长后关闭设备屏幕  <br/> |确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。  <br/> |
