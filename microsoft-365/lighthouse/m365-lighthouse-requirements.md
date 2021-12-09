---
title: Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (MSP) ，获取使用托管服务提供商Microsoft 365 Lighthouse。
ms.openlocfilehash: 8a502e056d570ef81e1bdb02321f0492c2b50395
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371888"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse

> [!NOTE]
> 本文中所述的功能在预览版中可能会更改，并且仅对满足本文中列出的要求的合作伙伴可用。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse是一个管理门户，可帮助托管服务提供商 (MSP) 为中小型商业 (SMB 客户大规模保护和管理设备、数据和) 用户。  

MSP 必须以间接经销商或直接帐单合作伙伴云解决方案提供商 (云解决方案提供商计划) 注册，以使用 Lighthouse。  

此外，每个 MSP 客户租户都必须满足以下要求，才有资格使用 Lighthouse： 
 
- MSP 的 (DAP) 委派管理员权限 
- 至少一个Microsoft 365 商业高级版或Microsoft 365 E3许可证 
- 少于 500 个许可用户  

## <a name="requirements-for-enablingdevice-management"></a>启用设备管理的要求   

若要在设备管理页面上查看客户租户设备，MSP 必须：    

- 在 MEM 中注册Microsoft Endpoint Manager (客户) 。有关详细信息，请参阅在 Microsoft Intune[中注册设备](/mem/intune/enrollment/)。
- 将合规性策略分配给所有客户设备。有关详细信息，请参阅 Create [a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy)。 

## <a name="requirements-for-enabling-usermanagement"></a>启用用户管理的要求 

若要使客户数据显示在用户管理页面上的报告（包括风险用户、多重身份验证和密码重置）中，客户租户必须具有 Azure Active Directory 高级版 P1 或更高版本的许可证。 Azure AD Premium P1 和 Microsoft 365 E3 中Microsoft 365 商业高级版。   

## <a name="requirements-for-enablingthreat-management"></a>启用威胁管理的要求 

若要在威胁管理页面上查看客户租户设备和威胁，必须在 Microsoft Endpoint Manager (MEM) 注册所有客户租户设备，并运行 Microsoft Defender 防病毒。  

有关详细信息，请参阅在 Microsoft Intune[中注册设备](/mem/intune/enrollment/)。  

Microsoft Defender 防病毒是 Windows操作系统的一部分，并且默认情况下在运行 Windows 10 的设备上启用。  

> [!NOTE] 
> 如果使用的是非 Microsoft 防病毒解决方案，但Microsoft Defender 防病毒，Microsoft Defender 防病毒自动禁用。 卸载非 Microsoft 防病毒解决方案时，Microsoft Defender 防病毒自动激活，以保护Windows设备免受威胁。    

## <a name="related-content"></a>相关内容   

[Configure Microsoft 365 Lighthouse portal security (](m365-lighthouse-configure-portal-security.md) article) \
[Microsoft 365 Lighthouse设备合规性页面概述 (](m365-lighthouse-device-compliance-page-overview.md)文章) \
[Microsoft 365 Lighthouse用户页面概述 (](m365-lighthouse-users-page-overview.md)文章) \
[Microsoft 365 Lighthouse威胁管理页面概述 (](m365-lighthouse-threat-management-page-overview.md)文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml)   (文章) 

