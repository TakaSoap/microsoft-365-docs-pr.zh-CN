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
ms.openlocfilehash: 51dd2404f03dc58d5975a37c386ba9c8f1333763
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327247"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse

Microsoft 365 Lighthouse是一个管理门户，可帮助托管服务提供商 (MSP) 为中小型商业 (SMB) 客户大规模保护和管理设备、数据和用户。  

MSP 必须以间接经销商或直接帐单合作伙伴云解决方案提供商 (云解决方案提供商计划) 注册，以使用 Lighthouse。  

此外，每个 MSP 客户租户都必须满足以下要求，才有资格使用 Lighthouse： 
 
- 针对 MSP (DAP) 委派的管理员 (或) 委派管理员权限 
- 至少一个Microsoft 365 商业高级版或Microsoft 365 E3许可证 
- 少于 1000 个许可用户  

## <a name="requirements-for-enablingdevice-management"></a>启用设备管理的要求

若要在设备管理页面上查看客户租户设备，MSP 必须：

- 在 MEM Microsoft Endpoint Manager (注册) 。有关详细信息，请参阅在[设备上注册Microsoft Intune](/mem/intune/enrollment/)。
- 将合规性策略分配给所有客户设备。有关详细信息，请参阅在 [Microsoft Intune。](/mem/intune/protect/create-compliance-policy) 

## <a name="requirements-for-enabling-usermanagement"></a>启用用户管理的要求 

若要使客户数据显示在用户管理页面上的报告（包括风险用户、多重身份验证和密码重置）中，客户租户必须具有 Azure Active Directory 高级版 P1 或更高版本的许可证。 Azure AD Premium P1和 Microsoft 365 商业高级版 Microsoft 365 E3。   

## <a name="requirements-for-enablingthreat-management"></a>启用威胁管理的要求 

若要在威胁管理页面上查看客户租户设备和威胁，必须在 Microsoft Endpoint Manager (MEM) 注册所有客户租户设备，并运行 Microsoft Defender 防病毒。  

有关详细信息，请参阅在[设备上注册Microsoft Intune](/mem/intune/enrollment/)。  

Microsoft Defender 防病毒是 Windows操作系统的一部分，并且默认情况下在运行 Windows 10 的设备上启用。  

> [!NOTE] 
> 如果使用的是非 Microsoft 防病毒解决方案，但Microsoft Defender 防病毒，Microsoft Defender 防病毒自动禁用。 卸载非 Microsoft 防病毒解决方案时，Microsoft Defender 防病毒自动激活，Windows设备免受威胁。    

## <a name="related-content"></a>相关内容

[Configure Microsoft 365 Lighthouse portal security (](m365-lighthouse-configure-portal-security.md) article) \
[Microsoft 365 Lighthouse设备合规性页面概述 (](m365-lighthouse-device-compliance-page-overview.md)文章) \
[Microsoft 365 Lighthouse用户页面概述 (](m365-lighthouse-users-page-overview.md)文章) \
[Microsoft 365 Lighthouse威胁管理页面概述 (](m365-lighthouse-threat-management-page-overview.md)文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml)  (文章) 

