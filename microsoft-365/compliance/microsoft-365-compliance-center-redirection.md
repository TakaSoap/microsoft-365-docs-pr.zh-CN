---
title: 将用户从 Office 365 安全与合规中心重定向到Microsoft 365 合规中心
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
description: 了解如何自动Office 365安全与合规中心用户重定向到Microsoft 365 合规中心。
ms.collection: M365-security-compliance
ms.openlocfilehash: d31cb4d86d914c9406996c4e6fdf7bab9c5d02e0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201033"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>将用户从 Office 365 安全与合规中心重定向到Microsoft 365 合规中心

本文介绍了自动重定向如何适用于从安全与合规中心Office 365合规性解决方案 (protection.office.com) 到Microsoft 365 合规中心 (compliance.microsoft.com) 。

## <a name="what-to-expect"></a>预期结果

默认情况下，在安全与合规策略中访问合规性相关解决方案的所有用户Office 365自动 (protection.office.com) ：

- [高级电子数据展示](overview-ediscovery-20.md)
- [通信合规性](communication-compliance.md)
- [内容搜索](search-for-content.md)
- [核心电子数据展示](get-started-core-ediscovery.md)
- [数据分类](data-classification-overview.md)
- [Data loss prevention (DLP)](dlp-learn-about-dlp.md)
- [数据主体请求](/compliance/regulatory/gdpr-manage-gdpr-data-subject-requests-with-the-dsr-case-tool)
- [信息治理](manage-information-governance.md)
- [记录管理](records-management.md)

用户将自动路由到 Microsoft 365 合规中心 (compliance.microsoft.com) 中的相同合规性解决方案。

此功能和相关控件不支持自动重定向 Microsoft Defender for Office 365。 若要启用安全功能重定向，请参阅将帐户从[Microsoft Defender](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for Office 365重定向到 Microsoft 365 安全中心了解详细信息。

## <a name="can-i-go-back-to-using-the-former-portal"></a>我能否返回到使用以前的门户？

如果无法通过 Microsoft 365 合规中心 门户完成某些操作或无法完成某些操作，可以暂时禁用所有用户的自动重定向。

> [!IMPORTANT]
> 此Microsoft 365 合规中心是当前在安全与合规中心内管理的合规性Office 365管理门户。 所有Microsoft 365合规性解决方案将仅在 Microsoft 365 合规中心 中进行管理。 禁用对 Microsoft 365 合规中心的重定向应视为短期解决方案。

若要切换回Office 365安全与合规 (protection.microsoft.com) ，请完成以下步骤：

1. 以全局管理员[Microsoft 365 合规中心](https://compliance.microsoft.com)Azure Active directory 中具有合规性管理员权限的任何帐户登录帐户。
2. 导航到 **设置**  >  **合规中心重定向。**
3. 将"自动重定向"设置切换为 **"关"。**
4. 选择 **"关闭** "，在系统提示时共享反馈。

禁用后，用户将不再被路由到 compliance.microsoft.com 他们将被定向到 Office 365 安全与合规中心 (protection.microsoft.com) 。 全局管理员或合规性管理员可以随时再次启用此设置。

## <a name="related-information"></a>相关信息

- [Microsoft 365 合规中心概述](/microsoft-365/compliance/microsoft-365-compliance-center)
