---
title: Microsoft 365 Defender先决条件
description: 了解软件的许可、硬件和软件要求以及其他配置Microsoft 365 Defender
keywords: 要求， 先决条件， 硬件， 软件， 浏览器， Microsoft 365 Defender， M365， 许可证， E5， A5， EMS， 购买
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 84fad9dc273d020ee48e53c5d9edb57c88041e99dd077151f4b41e8de93da3e7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53862547"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender先决条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

了解预配和使用应用程序的许可和其他[Microsoft 365 Defender。](microsoft-365-defender.md)

## <a name="licensing-requirements"></a>许可要求
通过上述任一许可证，Microsoft 365 Defender安全Microsoft 365访问这些功能，而无需额外付费：

- Microsoft 365 E5 或 A5
- Microsoft 365 E3加载项Microsoft 365 E5 安全性加载项
- Microsoft 365 A3安全Microsoft 365 A5加载项一起添加
- Windows 10 企业版 E5 或 A5
- 企业移动性 + 安全性 (EMS) E5 或 A5 
- Office 365 E5 或 A5
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender for Office 365 (计划 2)

有关详细信息，请参阅[服务Microsoft 365 企业版计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> 还没有许可证？ [试用或购买 Microsoft 365 订阅](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>检查现有许可证
转到[Microsoft 365 管理中心 (admin.microsoft.com) ](https://admin.microsoft.com/)查看现有许可证。 在管理中心，转到“计费” > “许可证”。

>[!NOTE]
> 你需要分配有[Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的帐单管理员或全局读者角色，才能查看许可证信息。  如果遇到访问问题，请联系全局管理员。

## <a name="required-permissions"></a>所需权限
您必须是 **全局管理员** 或安全管理员Azure Active Directory才能启用Microsoft 365 Defender。 有关使用管理角色Microsoft 365 Defender以及如何控制对数据的访问权限的信息，请阅读有关管理对 Microsoft 365 Defender[的访问](m365d-permissions.md)。

## <a name="browser-requirements"></a>浏览器要求
使用Microsoft 365 Defender、Microsoft 365 11 Microsoft Edge、Internet Explorer 5 兼容的 Web 浏览器访问安全中心内的网站。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>可在美国GCC、GCC High 和其他美国政府机构使用
目前，Microsoft 365 Defender *不适用于：*
- 美国政府社区云 (GCC) 
- 美国政府社区云高 (GCC高) 
- 美国国防部
- 所有拥有商业许可证的美国政府机构


目前，以下数据中心Office 365 Office 365客户无法将 Microsoft Defender Office 365集成到统一 Microsoft 365 Defender 功能：

- 巴西 
- 德国 
- 挪威 
- 新加坡 
- 南非
- Switzerland（瑞士） 
- 阿拉伯联合酋长国 


## <a name="related-topics"></a>相关主题
- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [打开 Microsoft 365 Defender](m365d-enable.md)
- [管理访问和权限](m365d-permissions.md)
