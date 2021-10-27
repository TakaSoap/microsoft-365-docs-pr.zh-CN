---
title: 将 Saba 配置为网站内容Microsoft Viva Learning
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
description: 了解如何将 Saba 配置为 Microsoft Viva Learning 的学习内容源。
ROBOTS: NOINDEX
ms.openlocfilehash: e259c7d7af3a7ff645017b2eccf76ff89c9a0bdf
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587309"
---
# <a name="configure-saba-as-a-content-source-for-microsoft-viva-learning"></a>将 Saba 配置为网站内容Microsoft Viva Learning

>[!NOTE]
>此功能在预览版中不受支持。

本文演示如何将 Saba 配置为用于 web 应用程序的第三方学习内容Microsoft Viva Learning。 您必须是 Saba 系统管理员或超级用户才能执行这些步骤。

>[!NOTE]
>通过 Viva Learning的内容受 Microsoft 产品条款外的其他条款所规定。 Saba 内容和任何关联的服务都受 Saba 的隐私和服务条款的约束。

## <a name="clients-host-url"></a>客户端的主机 URL

1. 标识主要 Saba 云 URL (例如"org".sabacloud.com) 。 如果 API 仪表板 URL org-api.sabacloud.com，主机 URL 将 org.sabacloud.com。

2. 通过访问 **Saba Cloud**  >  **Admin**  >  **System Admin** Manage  >  **Integrations** API Dashboard 确定  >  **API 仪表板 URL。** 找到 API 仪表板 URL，然后删除"https://"和"-api"，获取主机 URL。

<!--![Image of the API dashboard.](../media/learning/saba-1.png)-->

## <a name="client-id-and-client-secret"></a>客户端 ID 和客户端密码

1. 在获得主机 URL 的同一屏幕上，复制客户端 ID 和客户端密码（如果已生成）。

2. 如果客户端密码尚不存在，请选择" **生成** "按钮以生成它。

    <!--![Image of the button to generate the Client secret.](../media/learning/saba-2.png)-->

## <a name="username-and-password"></a>用户名和密码

提供管理帐户的用户名和密码，Microsoft Viva REST API 从 Saba 云拉取课程、完成以及相关信息。 理想情况下，此帐户应为超级用户。 如果该帐户不是超级用户，它必须至少具有 **Learning 管理员 -** 目录生成器和人力资源管理员角色 (或等效的自定义安全角色) 位于萨巴。

## <a name="last-steps"></a>最后的步骤

你需要在部署中完成Microsoft 365 管理中心。

1. 登录到[你的Microsoft 365 管理中心。](https://admin.microsoft.com)
2. 导航到 **"设置"，** 再导航到"**组织设置"。** Select Viva Learning and enable Saba Cloud from the panel.
3. 填写从 Saba 门户获得的详细信息。
    >[!NOTE]
    >"显示名称"是组织在 Viva Learning 中显示 Saba 学习内容时进行循环Learning。 如果不输入新名称，则会显示默认名称"Saba Cloud"。

    <!--![Image of where you post configuration details in the admin center.](../media/learning/saba-3.png)-->

4. 选择 **"保存**"以激活 Microsoft Viva Learning 中的 Saba 云Microsoft Viva Learning。 内容可能需要 24 小时才能显示在 Viva Learning。

> [!Note]
> 对于 Saba 云集成，您需要在主机 URL sabacloud.com 一个域。 如果你有不同的域名，你将需要提出支持票证以允许你的域名。

## <a name="data-residency"></a>数据驻留

租户元数据集中存储在我们的数据存储中，而不是存储在特定于地理位置的数据存储中。

## <a name="roles-and-permissions"></a>角色和权限

目前，组织内的所有用户将能够发现所有租户特定的课程。 但是，他们只能使用他们有权访问的课程。 根据角色和权限 (用户特定的内容) 计划在未来推出。
