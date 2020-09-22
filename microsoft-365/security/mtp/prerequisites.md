---
title: Microsoft 威胁防护先决条件
description: 了解有关 Microsoft 威胁防护的许可、硬件和软件要求以及其他配置设置
keywords: 要求、先决条件、硬件、软件、浏览器、MTP、M365、许可证、E5、A5、EMS、purchase
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 50ca606a6bef9cec528b6b0ef78142f050e37c51
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195487"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Microsoft 威胁防护先决条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

了解设置和使用 [Microsoft 威胁防护](microsoft-threat-protection.md)的许可和其他要求。

## <a name="licensing-requirements"></a>许可要求
这些许可证中的任何一个都允许您访问 Microsoft 365 安全中心中的 Microsoft 威胁防护功能，而无需额外费用：

- Microsoft 365 E5 或 A5
- Microsoft 365 E5 Security or A5 Security
- Windows 10 企业版 E5 或 A5
- 企业移动性 + 安全性 (EMS) E5 或 A5 
- Office 365 E5 或 A5
- Microsoft Defender 高级威胁防护
- Azure 高级威胁防护 
- Microsoft Cloud App Security
- Office 365 高级威胁防护（计划 2）

> [!NOTE]
> Office 365 试用版许可证目前不提供对 Microsoft 威胁防护的访问权限。

有关详细信息，请 [查看 Microsoft 365 企业版服务计划](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> 还没有许可证？ [试用或购买 Microsoft 365 订阅](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>检查现有许可证
转到 Microsoft 365 管理中心 ([admin.microsoft.com](https://admin.microsoft.com/)) 查看现有许可证。 在管理中心，转到“计费”**** > “许可证”****。

>[!NOTE]
> 您需要在[AZURE AD 中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)为**帐单管理员**或**全局读者**角色分配，以便能够查看许可证信息。 如果遇到访问问题，请联系全局管理员。

## <a name="required-permissions"></a>所需权限
您必须是 **全局管理员** 或 Azure Active Directory 中的 **安全管理员** 才能打开 Microsoft 威胁防护。 有关使用 Microsoft 威胁防护所需角色的列表，以及如何对数据访问进行管控的信息，请阅读 [管理 Microsoft 威胁防护的访问权限](mtp-permissions.md)。

## <a name="browser-requirements"></a>浏览器要求
使用 microsoft Edge、Internet Explorer 11 或任何符合 HTML 5 的 web 浏览器访问 microsoft 365 安全中心中的 Microsoft 威胁防护。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>对美国 GCC、GCC 高和其他美国政府机构的可用性
目前，Microsoft 威胁 *防护不适用于* ：
- 美国政府社区云 (GCC) 
- 美国政府社区云高 (GCC 高) 
- 美国国防部
- 拥有商业许可证的所有美国政府机构

## <a name="related-topics"></a>相关主题
- [Microsoft 威胁防护概述](microsoft-threat-protection.md)
- [打开 Microsoft 威胁防护](mtp-enable.md)
- [管理访问权限和权限](mtp-permissions.md)
