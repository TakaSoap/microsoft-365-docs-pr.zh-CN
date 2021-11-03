---
title: 添加其他内容提供程序Microsoft Viva Learning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 了解如何配置其他内容提供程序作为学习内容源，Microsoft Viva Learning。
ms.openlocfilehash: 4f1a8810f6b8615baa7e8b3fcd8d945ca08cf1d5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60668260"
---
# <a name="add-other-content-providers-for-microsoft-viva-learning"></a>添加其他内容提供程序Microsoft Viva Learning

通过 Viva 网站提供了越来越多的学习内容Learning。 随着更多提供程序加入程序或更改其状态，此组可能随时更改。

默认情况下将启用某些学习源，并且将在没有高级 Viva 许可证的情况下Learning源。 这些学习源包括：

- LinkedIn Learning选择 125 个课程
- Microsoft Learn
- Microsoft 365培训

默认情况下，不启用第三方内容源。 若要启用这些源，你需要将它们添加到[Microsoft 365 管理中心并按照下表](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources)中显示的特定说明进行操作。

>[!NOTE]
>你将需要一个高级版许可证来连接外部内容源，但选择 LinkedIn Learning课程除外。 [了解有关许可的更多信息](https://www.microsoft.com/microsoft-viva/learning)。

>[!NOTE]
>Viva 用户可能需要 24 到 48 Learning才能查看你在管理门户中启用的源的内容。 在管理门户中禁用 LinkedIn Learning、Microsoft Learn 和 Microsoft 365 培训后，可能需要 24 至 48 小时从 Viva Learning 中隐藏这些内容。

|内容提供程序  |配置说明  |
|---------|---------|
|Go1     |[将 Go1 配置为内容源](configure-go1-content-source.md)         |
|Skillsoft     |[将 Skillsoft 配置为内容源](configure-skillsoft-content-source.md)         |
|Udemy   |[将 Udemy 配置为内容源](configure-udemy-content-source.md)         |
|edX    |按照以下步骤将 edX 添加到Microsoft 365 管理中心。    |
|Coursera    |按照以下步骤将 Coursera 添加到你的Microsoft 365 管理中心。    |
|Pluralsight    |按照以下步骤在服务中添加"pluralsight"Microsoft 365 管理中心。    |
|Infosec    |按照以下步骤将 Infosec 添加到Microsoft 365 管理中心。    |
|Josh Bersin Academy    |按照以下步骤将 Josh Bersin Academy 添加到Microsoft 365 管理中心。    |

1. 登录到[你的Microsoft 365 管理中心。](https://admin.microsoft.com)
2. 导航到 **"设置"，** 再导航到"**组织设置"。** 选择"viva Learning"，然后启用面板中选定的内容提供程序或学习管理系统。
3. 填写详细信息。
4. 选择“**保存**”。

>[!NOTE]
>可用内容提供程序可能会更改。 根据组织的不同，您访问的内容提供程序可能多于此处列出的内容提供程序。

## <a name="content-ingestion-errors"></a>内容输入错误

如果在内容输入期间Microsoft 365 管理中心遇到任何错误，请参阅下表，查看下一步。 请注意，这是一个详尽的列表，将来可能会包含更多错误代码。

|内容提供程序 |错误代码 |错误代码说明 |
|:----------------|:----------|:----------------------|
|所有提供程序 |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |提供的身份验证凭据无效。 请确保输入正确的凭据。 有关更多详细信息，请联系 Microsoft 客户支持部门。 |
|所有提供程序 |USR_ERROR_ACCESS_DENIED |合作伙伴拒绝访问。 确认您输入的凭据正确无误，或与内容提供商的支持团队联系。 |

## <a name="content-consumption-for-end-users"></a>最终用户的内容使用

将内容提供程序添加为 Microsoft 365 管理中心 中的内容源后，来自该提供程序的内容将流到 Viva Learning 应用程序，并且对最终用户可见。

一旦用户选择在 Viva Learning 中玩课程，他们将被定向到内容提供商的网页，并且需要在提供商的登录页面上输入登录凭据。 [详细了解如何使用 Viva](https://support.microsoft.com/office/01bfed12-c327-41e0-a68f-7fa527dcc98a)Learning 。
