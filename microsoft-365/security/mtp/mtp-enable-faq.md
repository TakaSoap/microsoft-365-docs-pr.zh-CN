---
title: 启用 Microsoft 365 Defender 时的常见问题
description: 获取有关许可、权限、初始设置以及与启用 Microsoft 365 Defender 相关的其他产品和服务的最常见提问的答案
keywords: 常见问题解答、FAQ、GCC、入门、启用 MTP、Microsoft 威胁防护、M365、security、data location、必需权限、许可证资格、设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842412"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>启用 Microsoft 365 Defender 时的常见问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

阅读有关启用 [Microsoft 365 Defender](microsoft-threat-protection.md)的最常见问题的答复，包括所需的许可证和权限、部署支持服务和初始设置。

有关如何启用服务的说明，请 [参阅启用 Microsoft 365 Defender](mtp-enable.md)。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>我没有 Microsoft 365 E5 许可证。 我是否可以继续使用 Microsoft 365 Defender？

具有以下非 E5 许可证的客户可以使用 Microsoft 365 Defender：

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- 适用于 Office 的 Defender 365 (计划 2) 
 
若要获取受支持的许可证的完整列表，请 [阅读许可要求](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>我是否需要安装或部署任何内容以开始使用 Microsoft 365 Defender？

否，Microsoft 365 Defender 将从已部署的 Microsoft 365 安全服务中合并数据。 一旦将其打开，事件、自动化和搜寻体验将在已部署产品的范围内开始工作。 如果未正确部署这些产品，Microsoft 365 Defender 将不会显示任何数据，并且无法执行任何操作。

为了优化你的 Microsoft 365 Defender 体验，我们建议部署 *所有* 支持的 [microsoft 365 安全产品和服务](deploy-supported-services.md)。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender 处理和存储我的数据的位置是什么？
Microsoft 365 Defender 自动为数据中心选择一个用于处理和存储统一数据的最佳位置。 如果你有 Microsoft Defender for Endpoint，则会选择用于终结点的 Defender 的相同位置。

>[!NOTE]
>Microsoft Defender for Endpoint 在欧洲联合 (EU 通过 Azure Defender * 打开时自动设置) 数据中心。 对于已通过这种方式为 Microsoft Defender for Endpoint 设置的客户，microsoft 365 Defender 将自动在相同的欧盟数据中心中预配。 

在 microsoft 365 Defender ( **设置 > microsoft 365 defender** ) 中设置服务之前和之后，将显示数据中心位置。 如果您更愿意使用其他数据中心位置，请在 Microsoft 365 安全中心中选择 **"需要帮助？** " 以联系 microsoft 支持部门。

## <a name="where-can-i-access-microsoft-365-defender"></a>在哪里可以访问 Microsoft 365 Defender？

Microsoft 365 Defender 在 Microsoft 365 安全中心中提供。 若要转到安全中心，请浏览到 URL [https://security.microsoft.com](https://security.microsoft.com) 。

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>在 Microsoft 365 安全中心访问 Microsoft 365 Defender 需要什么权限？

分配了以下 Azure Active Directory (AD) 角色的帐户可以访问 Microsoft 365 Defender 功能和数据：

- 全局管理员
- 安全管理员
- 安全操作员
- 全局读取者
- 安全读取者

>[!NOTE]
>Microsoft Defender for Endpoint 中基于角色的访问控制设置会影响对数据的访问。 有关详细信息，请参阅 [管理对 Microsoft 365 Defender 的访问](mtp-permissions.md)。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Microsoft 365 Defender 的默认设置是什么时区？
默认情况下，Microsoft 365 Defender 在 UTC 时区中显示时间信息。 您可以将此设置更改为使用本地时区。 [了解有关设置时区的信息](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>如何才能了解新的 Microsoft 365 Defender 功能和 UI 更新？

Microsoft 定期通过各种渠道提供信息，包括：

- Microsoft 365 管理中心中的[邮件中心](../../admin/manage/message-center.md)
- [Microsoft 365 security & 合规性技术社区](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的 Blogposts

通过打开 [预览功能](preview.md)获取最新的公开体验。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender 是否适用于美国政府社区云 (GCC) 或 GCC 高版？
目前不可用。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 Defender 概述](microsoft-threat-protection.md)
- [打开 Microsoft 365 Defender](mtp-enable.md)。
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [启用预览功能](preview.md)
