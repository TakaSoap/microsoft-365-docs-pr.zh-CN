---
title: Microsoft 365Defender 先决条件
description: 了解适用于 Microsoft 365 Defender 的许可、硬件和软件要求以及其他配置设置
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
ms.openlocfilehash: 69345a0db42ec838dc0758cdb0e93a49a8ba6cfd
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259399"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365Defender 先决条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

了解预配和使用 defender 的许可Microsoft 365[要求](microsoft-365-defender.md)。

## <a name="licensing-requirements"></a>许可要求
通过以下任一许可证，Microsoft 365安全中心Microsoft 365 Defender 功能，无需额外付费：

- Microsoft 365 E5 或 A5
- Microsoft 365 E3加载项Microsoft 365 E5 安全性加载项
- Microsoft 365具有 Microsoft 365 A5 安全加载项的 A3
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
转到Microsoft 365管理中心 (admin.microsoft.com) 查看现有许可证[](https://admin.microsoft.com/)。 在管理中心，转到“计费” > “许可证”。

>[!NOTE]
> 你需要分配有[Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中的帐单管理员或全局读者角色，才能查看许可证信息。  如果遇到访问问题，请联系全局管理员。

## <a name="required-permissions"></a>所需权限
你必须是 **全局管理员** 或安全 **管理员才能Azure Active Directory** Defender Microsoft 365 Defender。 有关使用 defender 所需的角色列表Microsoft 365以及如何控制对数据的访问权限的信息，请阅读有关管理对[Microsoft 365 Defender 的访问权限](m365d-permissions.md)。

## <a name="browser-requirements"></a>浏览器要求
使用 Microsoft 365、Microsoft 365 11 或任何符合 HTML 5 Microsoft Edge访问安全中心中的 Microsoft Edge Internet Explorer Defender。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>可在美国GCC、GCC High 和其他美国政府机构使用
目前，Microsoft 365 Defender *不可用：*
- 美国政府社区云 (GCC) 
- 美国政府社区云高 (GCC高) 
- 美国国防部
- 所有拥有商业许可证的美国政府机构

## <a name="related-topics"></a>相关主题
- [Microsoft 365Defender 概述](microsoft-365-defender.md)
- [打开 Microsoft 365 Defender](m365d-enable.md)
- [管理访问和权限](m365d-permissions.md)
