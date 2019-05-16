---
title: 设备状态
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 了解 Microsoft 365 商业版中的设备状态。
ms.openlocfilehash: 06e5c800e6a104785c1fd0724223e05d7729722e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072712"
---
# <a name="device-states"></a>设备状态

## <a name="device-states"></a>设备状态

" **设备操作**"列表中的设备（管理员主页 \>" **设备操作**"）可具有以下状态。
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**状态**|**说明**|
|:-----|:-----|
|由 Intune 托管  <br/> |由 Microsoft 365 商业版 托管  <br/> |
|等待停用  <br/> |Microsoft 365 商业版 正准备从设备中删除公司数据。  <br/> |
|正在停用  <br/> |Microsoft 365 商业版 当前正在从设备中删除公司数据。  <br/> |
|停用失败  <br/> | 删除公司数据操作失败。  <br/> |
|已取消停用  <br/> |已取消"停用"操作。  <br/> |
|等待擦除  <br/> |正在等待恢复出厂重置。  <br/> |
|正在擦除  <br/> |已开始恢复出厂设置。  <br/> |
|擦除失败  <br/> |无法恢复出厂设置。  <br/> |
|已取消擦除  <br/> |已取消工厂擦除。  <br/> |
|不正常  <br/> |这表明某个操作正在等待执行（或正在执行），但设备未签入时间已超过 30 天。  <br/> |
|等待删除  <br/> |正在等待执行"删除"操作。  <br/> |
|已发现  <br/> |Microsoft 365 商业版 已检测到设备。  <br/> |
   
