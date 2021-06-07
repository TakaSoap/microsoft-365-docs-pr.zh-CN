---
title: 将用户从 Office 365 安全与合规中心重定向到Microsoft 365合规中心
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: 了解如何自动Office 365安全与合规中心用户重定向到Microsoft 365中心。
ms.collection: M365-security-compliance
ms.openlocfilehash: fb667e8f19b26cbe229b3aceffe194a86133c261
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772424"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>将用户从 Office 365 安全与合规中心重定向到Microsoft 365合规中心

本文介绍了自动重定向如何适用于从 Office 365 安全与合规中心 (protection.office.com) 访问合规性解决方案Microsoft 365合规性 (compliance.microsoft.com) 。

## <a name="what-to-expect"></a>预期结果

默认情况下，在安全与合规策略中访问以下合规性相关解决方案的所有用户Office 365自动 (protection.office.com) ：

- 数据丢失防护 (DLP)
- 分类
- 信息治理
- 记录管理
- 通信合规性 (以前是"监督") 

系统会自动将用户路由到 Microsoft 365 合规中心 (compliance.microsoft.com) 。

>[!NOTE]
>对于 Office 365 安全与合规中心中包含的其他合规性解决方案，用户将继续在 Microsoft 365 合规中心或 Office 365 安全与合规中心管理这些解决方案。 这些合规性解决方案的自动重定向即将推出。*

此功能和相关控件不支持自动重定向 Microsoft Defender for Office 365。 若要启用安全功能重定向，请参阅将帐户从[Microsoft Defender](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for Office 365重定向到 Microsoft 365 安全中心了解详细信息。

## <a name="can-i-go-back-to-using-the-former-portal"></a>我能否返回到使用以前的门户？

如果无法通过 Microsoft 365 合规中心门户完成某些操作，可以暂时禁用所有用户的自动重定向。

>[!IMPORTANT]
>Microsoft 365合规中心是当前在安全与合规中心内管理的合规性Office 365管理门户。 所有Microsoft 365合规性解决方案将仅在 Microsoft 365 合规中心进行管理。 禁用重定向到 Microsoft 365 合规中心应该是一个短期解决方案。*

若要切换回Office 365安全与合规 (protection.microsoft.com) ，请完成以下步骤：

1. 以全局管理员[Microsoft 365](https://compliance.microsoft.com) Azure Active directory 中具有合规性管理员权限的任何帐户登录合规性中心。
2. 导航到 **设置**  >  **合规中心重定向。**
3. 将"自动重定向"设置切换为 **"关"。**
4. 选择 **"禁用** "，在系统提示时共享反馈。

禁用后，用户将不再被路由到 compliance.microsoft.com 他们将被定向到 Office 365 安全与合规中心 (protection.microsoft.com) 。 全局管理员或合规性管理员可以随时再次启用此设置。

## <a name="related-information"></a>相关信息

- [Microsoft 365合规中心概述](/microsoft-365/compliance/microsoft-365-compliance-center)
