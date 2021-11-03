---
title: 为用户添加学习Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 11/01/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 了解如何将学习管理系统配置为用于学习Microsoft Viva Learning。
ms.openlocfilehash: 84f2e0d50b36f7fe54d82db9fb5564dcbbcbe9fa
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60676973"
---
# <a name="add-learning-management-systems-for-microsoft-viva-learning"></a>为用户添加学习Microsoft Viva Learning

通过 Viva Learning 提供了越来越多的学习管理系统。 随着更多提供程序加入程序或更改其状态，此组可能随时更改。

Learning系统默认情况下未启用。 若要启用这些源，你需要将它们添加到[Microsoft 365 管理中心并按照下表](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources)中显示的特定说明进行操作。

>[!NOTE]
>你将需要一个高级版许可证来连接学习管理系统。 [了解有关许可的更多信息](https://www.microsoft.com/microsoft-viva/learning)。

>[!NOTE]
>Viva 用户可能需要 24 到 48 Learning才能查看你在管理门户中启用的源的内容。

## <a name="learning-management-systems"></a>Learning管理系统

|Learning管理系统  |配置说明  |
|---------|---------|
|Cornerstone OnDemand |[将Demand 配置为内容源](configure-cornerstone-content-source.md)         |
|萨巴    |[将 Saba 配置为内容源](configure-saba-content-source.md)         |
|SAP SuccessFactors   |[将 SAP SuccessFactors 配置为内容源](configure-successfactors-content-source.md)         |

>[!NOTE]
>可用的学习管理系统可能会发生变化。 根据组织的不同，你可以访问与此处列出的不同的学习管理系统。

## <a name="content-ingestion-errors"></a>内容输入错误

如果在内容输入期间Microsoft 365 管理中心遇到任何错误，请参阅下表，查看下一步。 请注意，这是一个详尽的列表，将来可能会包含更多错误代码。

|Learning管理系统 |错误代码 |错误代码说明 |
|:----------------|:----------|:----------------------|
|所有 LMS |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |提供的身份验证凭据无效。 请确保输入正确的凭据。 有关更多详细信息，请联系 Microsoft 客户支持部门。 |
|所有 LMS |USR_ERROR_ACCESS_DENIED |合作伙伴拒绝访问。 确认您输入的凭据正确无误，或与内容提供商的支持团队联系。 |
|SuccessFactors |USR_ERROR_SFTP_NO_FILES_FOUND |没有新内容，因为 SuccessFactors SFTP 服务器中不存在文件。 |
|SuccessFactors |USR_ERROR_SF_PACKAGE_NOT_FOUND |在 SuccessFactors SFTP 服务器中找不到作为所需包被作为所需包的新内容。 |
|Cornerstone OnDemand |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |提供的身份验证凭据无效。 确保凭据从在Microsoft Viva Learning中复制。 |

## <a name="content-consumption-for-end-users"></a>最终用户的内容使用

将学习管理系统添加为 Microsoft 365 管理中心 中的内容源后，LMS 中的内容将流入 Viva Learning 应用，并且对最终用户可见。

一旦用户选择在 Viva Learning中学习课程，他们将被定向到 LMS 网页，并且需要在 LMS 登录页面上输入登录凭据。 [详细了解如何使用 Viva](https://support.microsoft.com/office/01bfed12-c327-41e0-a68f-7fa527dcc98a)Learning。
