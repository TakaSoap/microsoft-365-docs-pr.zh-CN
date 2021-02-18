---
title: 使用自动调查和响应的自定义报告解决方案
keywords: SIEM， API， AIR， autoIR， ATP， 自动调查， 集成， 自定义报告
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 了解如何将自动调查和响应与自定义或第三方报告解决方案集成。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13782a8e0a8c691a66f214d3f9f03ef9cad4da1f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287133"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 的自定义或第三方报告解决方案

使用 [Microsoft Defender for Office 365，](office-365-atp.md)你可以 [获取有关自动调查的详细信息](air-view-investigation-results.md)。 但是，某些组织还使用自定义或第三方报告解决方案。 如果你的组织想要将有关自动调查的信息与[](office-365-air.md)此类解决方案集成，可以使用 Office 365 管理活动 API。

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

使用 [Microsoft Defender for Office 365，](office-365-atp.md)你可以 [获取有关自动调查的详细信息](air-view-investigation-results.md)。 但是，某些组织还使用自定义或第三方报告解决方案。 如果你的组织想要将有关自动调查的信息与此类解决方案集成，可以使用 Office 365 管理活动 API。

|资源|说明|
|:---|:---|
|[Office 365 管理 API 概述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|Office 365 管理活动 API 提供有关 Microsoft 365 和 Azure Active Directory 活动日志中的各种用户、管理员、系统和策略操作和事件的信息。|
|[Office 365 管理 API 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 管理 API 使用 Azure AD 为应用程序提供身份验证服务，以访问 Microsoft 365 数据。 按照本文中的步骤设置此操作。|
|[Office 365 管理活动 API 参考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|可以使用 Office 365 管理活动 API 从 Microsoft 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作和事件的信息。 阅读本文可了解有关此工作原理的更多信息。|
|[Office 365 管理活动 API 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|大致了解 [常见](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 架构和 [Defender for Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 以及威胁调查和响应架构，以了解通过 Office 365 管理活动 API 提供的特定数据类型。|
|

## <a name="see-also"></a>另请参阅

- [Microsoft Defender for Office 365](office-365-atp.md)
- [Microsoft 365 Defender 中的自动调查和响应](../mtp/mtp-autoir.md)
