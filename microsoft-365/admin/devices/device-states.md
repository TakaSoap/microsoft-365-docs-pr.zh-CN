---
title: 设备状态
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 了解适用于企业管理员主页的"设备操作"列表中的Microsoft 365状态。
ms.openlocfilehash: 798a753f6d523a3f586ac32698cda80a127c44b5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313813"
---
# <a name="device-states"></a>设备状态

本文适用于Microsoft 365 商业高级版。

> [!NOTE]
> 从 2022 年 3 月 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 此产品/服务为设备提供其他安全功能。 [详细了解 Defender for Business](../../security/defender-business/mdb-overview.md)。

" **设备操作**"列表中的设备（管理员主页 \>" **设备操作**"）可具有以下状态。
  
![In the Device actions list, you can see the Devices states.](../../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**状态**|**说明**|
|:-----|:-----|
|由 Intune 托管  <br/> |由 Microsoft 365 商业高级版。  <br/> |
|等待停用  <br/> |Microsoft 365 商业高级版准备从设备中删除公司数据。  <br/> |
|正在停用  <br/> |Microsoft 365 商业高级版当前正在从设备中删除公司数据。  <br/> |
|停用失败  <br/> | 删除公司数据操作失败。  <br/> |
|已取消停用  <br/> |已取消停用操作。  <br/> |
|等待擦除  <br/> |正在等待恢复出厂重置。  <br/> |
|正在擦除  <br/> |已开始恢复出厂设置。  <br/> |
|擦除失败  <br/> |无法恢复出厂设置。  <br/> |
|已取消擦除  <br/> |已取消出厂擦除。  <br/> |
|不正常  <br/> |操作在 (或正在进行) ，但设备已 30 多天未签入。  <br/> |
|等待删除  <br/> |正在等待执行"删除"操作。  <br/> |
|已发现  <br/> |Microsoft 365 商业高级版检测到设备。  <br/> |
   

## <a name="see-also"></a>另请参阅

[保护业务Microsoft 365的十大方法](../security-and-compliance/secure-your-business-data.md)