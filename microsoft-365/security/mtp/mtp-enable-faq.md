---
title: 启用 Microsoft 威胁防护时的常见问题
description: 获取有关许可、权限、初始设置以及与启用 Microsoft 威胁防护相关的其他产品和服务的最常见询问性问题的答案。
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
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198835"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>启用 Microsoft 威胁防护时的常见问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

阅读有关启用 [Microsoft 威胁防护](microsoft-threat-protection.md)的最常见问题的解答，包括所需的许可证和权限、部署支持服务和初始设置。

有关如何启用服务的说明，请 [参阅启用 Microsoft 威胁防护](mtp-enable.md)。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>我没有 Microsoft 365 E5 许可证。 我仍可以使用 Microsoft 威胁防护吗？

具有以下非 E5 许可证的客户可以使用 Microsoft 威胁防护：

- Microsoft Defender 高级威胁防护
- Azure 高级威胁防护
- Microsoft Cloud App Security
- Office 365 高级威胁防护（计划 2）
 
若要获取受支持的许可证的完整列表，请 [阅读许可要求](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>我是否需要安装或部署任何内容以开始使用 Microsoft 威胁防护？

否，Microsoft 威胁防护功能将来自您已部署的 Microsoft 365 安全服务中的数据进行合并。 一旦将其打开，事件、自动化和搜寻体验将在已部署产品的范围内开始工作。 如果这些产品均未正确部署，则 Microsoft 威胁防护不会显示任何数据，也不能执行任何操作。

为了优化你的 Microsoft 威胁防护体验，我们建议部署 *所有* 受支持的 [microsoft 365 安全产品和服务](deploy-supported-services.md)。

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Microsoft 威胁防护过程和存储我的数据在哪里？
Microsoft 威胁防护会自动为数据中心选择一个用于处理和存储统一数据的最佳位置。 如果你有 Microsoft Defender ATP，它将选择 Microsoft Defender ATP 使用的相同位置。

>[!NOTE]
>通过 Azure 安全中心打开时，Microsoft Defender ATP 将自动在欧盟 (EU) 数据中心进行预配。 对于已使用此方式预配 Microsoft Defender ATP 的客户，microsoft 威胁防护将自动在同一 EU 数据中心中进行设置。 

在 Microsoft 威胁防护 (**设置 > Microsoft 威胁防护**) 中设置了服务之前和之后，数据中心位置将显示在 "设置" 页的 "设置" 页中。 如果您更愿意使用其他数据中心位置，请在 Microsoft 365 安全中心中选择 **"需要帮助？** " 以联系 microsoft 支持部门。

## <a name="where-can-i-access-microsoft-threat-protection"></a>在哪里可以访问 Microsoft 威胁防护？

Microsoft 365 安全中心提供 microsoft 威胁防护。 若要转到安全中心，请浏览到 URL [https://security.microsoft.com](https://security.microsoft.com) 。

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>在 Microsoft 365 安全中心中访问 Microsoft 威胁防护需要什么权限？

分配了以下 Azure Active Directory (AD) 角色的帐户可以访问 Microsoft 威胁防护功能和数据：

- 全局管理员
- 安全管理员
- 安全操作员
- 全局读取者
- 安全读取者

>[!NOTE]
>Microsoft Defender ATP 中基于角色的访问控制设置会影响对数据的访问。 有关详细信息，请参阅 [管理对 Microsoft 威胁防护的访问](mtp-permissions.md)。

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>Microsoft 威胁防护默认为什么时区？
默认情况下，Microsoft 威胁防护会在 UTC 时区中显示时间信息。 您可以将此设置更改为使用本地时区。 [了解有关设置时区的信息](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>如何才能了解新的 Microsoft 威胁防护功能和 UI 更新？

Microsoft 定期通过各种渠道提供信息，包括：

- Microsoft 365 管理中心中的[邮件中心](../../admin/manage/message-center.md)
- [Microsoft 365 security & 合规性技术社区](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的 Blogposts

通过打开 [预览功能](preview.md)获取最新的公开体验。

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 威胁防护是否可供美国政府社区云（GCC）或 GCC High使用？
目前不可用。

## <a name="related-topics"></a>相关主题

- [Microsoft 威胁防护概述](microsoft-threat-protection.md)
- [启用 Microsoft 威胁防护](mtp-enable.md)。
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [打开预览功能](preview.md)
