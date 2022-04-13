---
title: Microsoft 365 Lighthouse的要求
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
description: 对于托管服务提供商 (MSP) ，获取使用Microsoft 365 Lighthouse的要求列表。
ms.openlocfilehash: d5f04c39cbce9726fefa4b410be63cd5ee4e959d
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823665"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse的要求

Microsoft 365 Lighthouse是一个管理门户，可帮助托管服务提供商 (MSP) 为中小型企业 (SMB) 客户大规模保护和管理设备、数据和用户。

MSP 必须作为间接经销商或直接帐单合作伙伴注册到 云解决方案提供商 (CSP) 计划，才能使用 Lighthouse。

此外，每个 MSP 客户租户必须符合以下要求，才能获得 Lighthouse：

- 必须为托管服务提供程序设置委派的访问权限 (MSP) 才能管理客户租户*
- 必须至少有一个Microsoft 365 商业高级版、Microsoft 365 E3或Windows 365 商业版许可证
- 必须拥有不超过 1000 个许可用户

*委派的管理员权限 (DAP) 需要将客户载入 Lighthouse。 我们还建议与客户建立 GDAP)  (粒度委派的管理员权限，以实现更安全的委派访问。 虽然 DAP 和 GDAP 共存，但 GDAP 将优先于两个模型所在的客户。 很快，只有 GDAP (且没有 DAP) 的客户将能够加入 Lighthouse。

## <a name="requirements-for-enabling-device-management"></a>启用设备管理的要求

若要在设备管理页上查看客户租户设备，MSP 必须：

- 在 MICROSOFT ENDPOINT MANAGER (MEM) 中注册所有客户设备。 有关详细信息，请参阅[Microsoft Intune中注册设备](/mem/intune/enrollment/)。
- 将符合性策略分配给所有客户设备。 有关详细信息，请参阅[Microsoft Intune中创建合规性策略](/mem/intune/protect/create-compliance-policy)。

## <a name="requirements-for-enabling-user-management"></a>启用用户管理的要求

要使客户数据显示在用户管理页面的报表中，包括风险用户、多重身份验证和密码重置，客户租户必须具有Azure Active Directory Premium P1或更高版本的许可证。 Azure AD Premium P1包含在Microsoft 365 商业高级版和Microsoft 365 E3中。

## <a name="requirements-for-enabling-threat-management"></a>启用威胁管理的要求

若要在威胁管理页上查看客户租户设备和威胁，必须在 Microsoft Endpoint Manager (MEM) 中注册所有客户租户设备，并通过运行Microsoft Defender 防病毒来保护它们。

有关详细信息，请参阅[Microsoft Intune中注册设备](/mem/intune/enrollment/)。

Microsoft Defender 防病毒是Windows操作系统的一部分，默认情况下在运行Windows 10的设备上启用。

> [!NOTE]
> 如果使用的是非 Microsoft 防病毒解决方案而不是Microsoft Defender 防病毒，则会自动禁用Microsoft Defender 防病毒。 卸载非 Microsoft 防病毒解决方案时，会自动激活Microsoft Defender 防病毒以保护Windows设备免受威胁。

## <a name="related-content"></a>相关内容

[配置门户Microsoft 365 Lighthouse安全](m365-lighthouse-configure-portal-security.md)性 (文章) \
[Microsoft 365 Lighthouse设备符合性页面概述](m365-lighthouse-device-compliance-page-overview.md) (文章) \
[Microsoft 365 Lighthouse“用户”页概述](m365-lighthouse-users-page-overview.md) (文章) \
[Microsoft 365 Lighthouse威胁管理页概述](m365-lighthouse-threat-management-page-overview.md) (文章) \
[Microsoft 365 Lighthouse常见问题解](m365-lighthouse-faq.yml)答 (文章) 
