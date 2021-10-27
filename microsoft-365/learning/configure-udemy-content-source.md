---
title: 将 Udemy 配置为用户的内容Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/07/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 了解如何将 Udemy 配置为用于学习Microsoft Viva Learning。
ROBOTS: NOINDEX
ms.openlocfilehash: 404f70983f1deadfac111829f026bd3ccdbcb633
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587941"
---
# <a name="configure-udemy-as-a-content-source-for-microsoft-viva-learning"></a>将 Udemy 配置为用户的内容Microsoft Viva Learning

>[!NOTE]
>此功能在预览版中不受支持。

本文演示如何将 Udemy 配置为适用于用户的第三方学习内容Microsoft Viva Learning。

>[!NOTE]
>通过 Viva Learning的内容受 Microsoft 产品条款外的其他条款所规定。 补偿内容以及任何关联的服务都受 Udemy 的隐私和服务条款的约束。

按照以下步骤在 Udemy Business 环境中启用 API，并生成用于 LMS/LXP 应用程序的客户端凭据以访问它们。

1. 导航到 **"管理"，** 然后 **设置，** 然后是 **API。** 检查 API 的状态。 如果禁用它们，你可以联系支持人员以启用它们，或按照以下步骤启用它们。

    <!--![Image of the API settings.](../media/learning/udemy-1.png)-->

2. 如果 API 已禁用，请导航到 **LMS/LXP 集成**，然后"开始设置"，然后选择"其他 **"。**

    <!--![Image of the Start Set Up > Other page.](../media/learning/udemy-2.png)-->

3. 在下面的屏幕中，键入自定义 LMS/LXP 或第三方应用程序的名称。 然后，打开或关闭自动注册选项，**然后选择保存。** 自动注册选项允许通过 LMS/LXP 启动课程的用户自动注册 Udemy。

    <!--![Image of the LMS/LXP integrations page.](../media/learning/udemy-3.png)-->

4. 保存后，将生成客户端 ID 和客户端密码，你可以从屏幕上复制它们。 现在，可以使用提供的客户端凭据访问 API。

    <!--![Image of the generated client ID and secret.](../media/learning/udemy-4.png)-->

5. 若要访问 API 终结点，你需要具有ACCOUNT_ID和终结点 URL。 你可以访问此信息，也可以导航到"管理"，然后导航到"管理"，然后设置 **API"来试用** **API。** 启用 API 后，应该会看到 API 的状态为"已启用"。 选择 API 文档链接。

    <!--![Image of the API page.](../media/learning/udemy-5.png)-->

6. 从概述页ACCOUNT_ID API 终结点 URL 和 URL。 导航到受支持的方法以尝试 API 调用。 现在，你已设置为调用 Udemy Business API。

    <!--![Image of the Supported methods page.](../media/learning/udemy-6.png)-->

    <!--![Image of the API call page where you can try it out.](../media/learning/udemy-7.png)-->

## <a name="configure-the-microsoft-365-admin-center"></a>配置Microsoft 365 管理中心

使用上述步骤从 Udemy 门户收到所需的配置详细信息后，租户管理员需要按照以下步骤在 Microsoft 365 管理中心 中将 Udemy 配置为学习源。

1. 导航[到](https://admin.microsoft.com)Microsoft 365 管理中心。

2. 导航到 **"设置"，** 再导航到"**组织设置"。** 搜索 Viva Learning选项启用 Udemy。

3. 填写以下所需的配置详细信息：

    - **客户端的主机 URL：** 这是在步骤 6 中从 Udemy 门户收集的 API 终结点 URL。
    - **组织 ID：** 这是ACCOUNT_ID步骤 6 中从 Udemy 门户收集的组。
    - **客户端 ID：** 这是从步骤 4 中的 Udemy 门户收集的客户端 ID。
    - **客户端密码**：这是从步骤 4 中的 Udemy 门户收集的客户端密码。

      <!--![Image of filled in configuration details.](../media/learning/udemy-8.png)-->

4. Select **Save** to activate Udemy content in Microsoft Viva Learning. 内容可能需要 24 小时才能在 Viva Learning。
