---
title: 将 Udemy 配置为用户的内容Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
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
description: 了解如何配置 Udemy 作为学习内容源，Microsoft Viva Learning。
ms.openlocfilehash: f5cbb140d2bf76fdf03eba5de0e09ad70fbf4afb
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60883849"
---
# <a name="configure-udemy-as-a-content-source-for-microsoft-viva-learning"></a>将 Udemy 配置为用户的内容Microsoft Viva Learning

本文演示如何将 Udemy 配置为适用于用户的第三方学习内容Microsoft Viva Learning。

>[!NOTE]
>通过 Viva Learning的内容受 Microsoft 产品条款外的其他条款所规定。 补偿内容以及任何关联的服务都受 Udemy 的隐私和服务条款的约束。

## <a name="configure-in-your-udemy-portal"></a>在 Udemy 门户中配置

>[!NOTE]
>你需要拥有 Udemy 中的管理员权限才能完成这些步骤。

按照以下步骤在 Udemy Business 环境中启用 API，并生成用于 LMS/LXP 应用程序的客户端凭据以访问它们。

1. 导航到 **"管理"，** 然后 **设置，** 然后是 **API。** 检查 API 的状态。 如果禁用它们，你可以联系支持人员以启用它们，或按照以下步骤启用它们。

    ![API 设置页面的图像。](../media/learning/udemy-1.png)

2. 如果 API 已禁用，请导航到 **LMS/LXP 集成**，然后"开始设置"，然后选择"其他 **"。**

    [![LMS/LXP 集成设置页面的图像。](../media/learning/udemy-2small.png)](../media/learning/udemy-2.png#lightbox)

3. 在下面的屏幕中，键入自定义 LMS/LXP 或第三方应用程序的名称。 然后，打开或关闭自动注册选项，**然后选择保存。** 自动注册选项允许通过 LMS/LXP 启动课程的用户自动注册 Udemy。

    ![用于自动注册的开/关切换的图像。](../media/learning/udemy-3.png)

4. 保存后，将生成客户端 ID 和客户端密码，你可以从屏幕上复制它们。 现在，可以使用提供的客户端凭据访问 API。

    ![生成的客户端 ID 和客户端密码的图像。](../media/learning/udemy-4.png)

5. 若要访问 API 终结点，你需要具有ACCOUNT_ID和终结点 URL。 你可以访问此信息，也可以导航到"管理"，然后导航到"管理"，然后设置 **API"来试用** **API。** 启用 API 后，应该会看到 API 的状态为"已启用"。 选择 API 文档链接。

    ![显示已启用的 API 的 API 设置的图像。](../media/learning/udemy-5.png)

6. 从概述页ACCOUNT_ID API 终结点 URL 和 URL。 导航到受支持的方法以尝试 API 调用。 现在，你已设置为调用 Udemy Business API。

    ![显示终结点 URL 和客户端 ID 的概述页面的图像。](../media/learning/udemy-6.png)
    !["你自己尝试"页面的图像，可在其中输入 URL 和客户端 ID。](../media/learning/udemy-7.png)

## <a name="configure-in-your-microsoft-365-admin-center"></a>在部署中Microsoft 365 管理中心

>[!NOTE]
>你需要拥有管理员权限才能Microsoft 365这些步骤。

使用上述步骤从 Udemy 门户收到所需的配置详细信息后，租户管理员需要按照以下步骤在 Microsoft 365 管理中心 中将 Udemy 配置为学习源。

1. 导航[到](https://admin.microsoft.com)Microsoft 365 管理中心。

2. 导航到 **"设置"，** 再导航到"**组织设置"。** 搜索 Viva Learning选项启用 Udemy。

3. 填写以下所需的配置详细信息：

    - **客户端的主机 URL：** 这是在步骤 6 中从 Udemy 门户收集的 API 终结点 URL。
    - **组织 ID：** 这是在ACCOUNT_ID 6 中从 Udemy 门户收集的组。
    - **客户端 ID：** 这是从步骤 4 中的 Udemy 门户收集的客户端 ID。
    - **客户端密码**：这是从步骤 4 中的 Udemy 门户收集的客户端密码。

4. 选择 **"保存**"以激活设备Microsoft Viva Learning。 内容可能需要 24 小时才能在 Viva Learning。

>[!NOTE]
>租户元数据集中存储在我们的数据存储中，而不是存储在特定于地理位置的数据存储中。
