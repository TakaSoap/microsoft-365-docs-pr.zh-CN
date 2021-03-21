---
title: Microsoft 365 Defender 先决条件
description: 了解 Microsoft 365 Defender 的许可、硬件和软件要求以及其他配置设置
keywords: 要求， 先决条件， 硬件， 软件， 浏览器， MTP， M365， 许可证， E5， A5， EMS， 购买
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0184b2c05121e1ea3bf365263df880548f1b9232
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918866"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender 先决条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

了解有关预配和使用 [Microsoft 365 Defender](microsoft-threat-protection.md)的许可和其他要求。

## <a name="licensing-requirements"></a>许可要求
通过以下任一许可证，你无需额外付费即可访问 Microsoft 365 安全中心中的 Microsoft 365 Defender 功能：

- Microsoft 365 E5 或 A5
- Microsoft 365 E5 安全或 A5 安全
- Windows 10 企业版 E5 或 A5
- 企业移动性 + 安全性 (EMS) E5 或 A5 
- Office 365 E5 或 A5
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender for Office 365 (计划 2) 

有关详细信息，请参阅 [Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> 还没有许可证？ [试用或购买 Microsoft 365 订阅](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>检查现有许可证
转到 Microsoft 365 管理中心 [ (admin.microsoft.com) ](https://admin.microsoft.com/) 查看现有许可证。 在管理中心，转到“计费” > “许可证”。

>[!NOTE]
> 你需要分配有[Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的帐单管理员或全局读者角色，才能查看许可证信息。  如果遇到访问问题，请联系全局管理员。

## <a name="required-permissions"></a>所需权限
你必须是 **Azure** Active Directory 中的全局管理员或安全管理员才能启用 Microsoft 365 Defender。  有关使用 Microsoft 365 Defender 所需的角色列表以及如何控制对数据的访问权限的信息，请阅读有关管理对 [Microsoft 365 Defender 的访问权限](mtp-permissions.md)的信息。

## <a name="browser-requirements"></a>浏览器要求
使用 Microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 Web 浏览器访问 Microsoft 365 安全中心中的 Microsoft 365 Defender。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>可在美国 GCC、GCC High 和其他美国政府机构使用
目前，Microsoft 365 Defender *不可用于* ：
- 美国政府社区云 (GCC) 
- 美国政府社区云高 (GCC 高) 
- 美国国防部
- 所有拥有商业许可证的美国政府机构

## <a name="related-topics"></a>相关主题
- [Microsoft 365 Defender 概述](microsoft-threat-protection.md)
- [打开 Microsoft 365 Defender](mtp-enable.md)
- [管理访问和权限](mtp-permissions.md)