---
title: 将自定义报告解决方案与自动调查和响应结合使用
keywords: SIEM、API、AIR、autoIR、ATP、自动调查、集成、自定义报告
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解如何将自动调查和响应与自定义或第三方报告解决方案集成。
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 08502516ae03dc7c6e7b58aa77939723e7532ef0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308916"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>将管理活动 API 用于自定义或第三方报告解决方案

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


使用 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)，可以获取 [有关自动调查的详细信息](air-view-investigation-results.md)。 但是，一些组织也使用自定义或第三方报告解决方案。 如果您的组织想要使用此解决方案集成有关自动调查的信息，您可以使用 Office 365 管理活动 API。

使用以下资源对此进行设置：

****

|资源|说明|
|---|---|
|[Office 365 管理 API 概述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|Office 365 管理活动 API 提供了有关来自 Microsoft 365 和 Azure Active Directory 活动日志的各种用户、管理员、系统和策略操作以及事件的信息。|
|[Office 365 管理 API 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|Office 365 管理 API 使用 Azure AD 为应用程序提供身份验证服务，以访问 Microsoft 365 数据。 请按照本文中的步骤进行设置。|
|[Office 365 管理活动 API 参考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|您可以使用 Office 365 管理活动 API，从 Microsoft 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作以及事件的信息。 阅读本文以了解有关如何工作的详细信息。|
|[Office 365 管理活动 API 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|获取 [常见架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 和 [office 365 ATP 以及威胁调查和响应架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 的概述，以了解通过 OFFICE 365 管理活动 API 提供的特定类型的数据。|
|

## <a name="see-also"></a>另请参阅

- [Microsoft Defender for Office 365](office-365-atp.md)

- [Microsoft 365 Defender 中的自动化调查和响应](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
