---
title: 为用户添加其他内容Microsoft Viva Learning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/22/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 了解如何配置其他提供程序作为学习内容源进行Microsoft Viva Learning。
ROBOTS: NOINDEX
ms.openlocfilehash: 006b3e6690df253f80bc8e47d93264b9bf19ea0f
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556622"
---
# <a name="add-other-content-providers-for-microsoft-viva-learning"></a>为用户添加其他内容Microsoft Viva Learning

通过 Viva Learning 提供了越来越多的学习内容提供程序和学习Learning。 随着更多提供程序加入程序或更改其状态，此组可能随时更改。

默认情况下，不启用第三方内容源。 若要启用这些源，你需要将它们添加到[Microsoft 365 管理中心并按照下表](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources)中显示的特定说明进行操作。

|内容提供程序  |配置说明  |
|---------|---------|
|Cornerstone OnDemand |[将Demand 配置为内容源](configure-cornerstone-content-source.md)         |
|Go1     |[将 Go1 配置为内容源](configure-go1-content-source.md)         |
|萨巴    |[将 Saba 配置为内容源](configure-saba-content-source.md)         |
|Skillsoft     |[将 Skillsoft 配置为内容源](configure-skillsoft-content-source.md)         |
|SAP SuccessFactors   |[将 SAP SuccessFactors 配置为内容源](configure-successfactors-content-source.md)         |
|Udemy   |[将 Udemy 配置为内容源](configure-udemy-content-source.md)         |

## <a name="content-ingestion-errors"></a>内容输入错误

如果在内容Microsoft 365 管理中心过程中遇到任何错误，请参阅下表，查看下一步。 请注意，这是一个详尽的列表，将来可能会包含更多错误代码。

|内容提供程序 |错误代码 |错误代码说明 |
|:----------------|:----------|:----------------------|
|所有提供程序 |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |提供的身份验证凭据无效。 请确保输入正确的凭据。 有关更多详细信息，请联系 Microsoft 客户支持部门。 |
|所有提供程序 |USR_ERROR_ACCESS_DENIED |合作伙伴拒绝访问。 确认您输入的凭据正确无误，或与内容提供商的支持团队联系。 |
|SuccessFactors |USR_ERROR_SFTP_NO_FILES_FOUND |没有新内容，因为 SuccessFactors SFTP 服务器中不存在文件。 |
|SuccessFactors |USR_ERROR_SF_PACKAGE_NOT_FOUND |在 SuccessFactors SFTP 服务器中找不到作为所需包被作为所需包的新内容。 |
|Cornerstone OnDemand |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |提供的身份验证凭据无效。 确保凭据从在"Learning"门户中的 Viva"应用"复制。 |

## <a name="third-party-content-consumption"></a>第三方内容使用

将第三方内容提供程序添加为 Microsoft 365 管理中心 中的内容源后，来自该提供程序的内容将流到 Viva Learning 应用，并且对最终用户可见。

一旦用户选择在 Viva Learning 中播放课程，他们将被定向到内容提供商的网页，并且需要在提供商的登录页面上输入登录凭据。 [详细了解如何使用 Viva](https://support.microsoft.com/office/viva-learning-preview-01bfed12-c327-41e0-a68f-7fa527dcc98a)Learning 。
