---
title: 将 Saba 配置为网站内容Microsoft Viva Learning
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
description: 了解如何配置 Saba 作为学习内容源进行Microsoft Viva Learning。
ms.openlocfilehash: 07c0148d7e1fefcd920a03426efba77ac91f374b
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60664896"
---
# <a name="configure-saba-as-a-content-source-for-microsoft-viva-learning"></a>将 Saba 配置为网站内容Microsoft Viva Learning

本文演示如何将 Saba 配置为用于 web 应用程序的第三方Microsoft Viva Learning。 您必须是 Saba 系统管理员或超级用户才能执行这些步骤。

>[!NOTE]
>通过 Viva Learning的内容受 Microsoft 产品条款外的其他条款所规定。 Saba 内容和任何关联的服务都受 Saba 的隐私和服务条款的约束。

>[!NOTE]
>Viva Learning Saba 集成将使用每月 API 调用桶中的 API，并计入限制限制。

## <a name="configure-in-your-saba-portal"></a>在 Saba 门户中配置

>[!NOTE]
>你需要在萨巴拥有管理员权限才能完成这些步骤。

### <a name="clients-host-url"></a>客户端的主机 URL

1. 标识主要 Saba 云 URL (例如"org".sabacloud.com) 。 如果 API 仪表板 URL org-api.sabacloud.com，主机 URL 将 org.sabacloud.com。
2. 通过访问 **Saba Cloud**  >  **Admin**  >  **System Admin** Manage  >  **Integrations** API Dashboard 确定  >  **API 仪表板 URL。** 找到 API 仪表板 URL，然后删除"https://"和"-api"，获取主机 URL。

### <a name="client-id-and-client-secret"></a>客户端 ID 和客户端密码

1. 在获得主机 URL 的同一屏幕上，复制客户端 ID 和客户端密码（如果已生成）。

2. 如果客户端密码尚不存在，请选择" **生成** "按钮以生成它。

## <a name="configure-in-your-microsoft-365-admin-center"></a>在部署中Microsoft 365 管理中心

你需要在部署中完成Microsoft 365 管理中心。

>[!NOTE]
>你将需要拥有管理员权限才能Microsoft 365这些步骤。

1. 登录到[你的Microsoft 365 管理中心。](https://admin.microsoft.com)
2. 导航到 **"设置"，** 再导航到"**组织设置"。** Select Viva Learning and enable Saba Cloud from the panel.
3. 填写从 Saba 门户获得的详细信息。
    >[!NOTE]
    >显示名称是循环式会议的名称，在它下，Saba 学习内容将在 Viva Learning 中为组织用户显示。 如果不输入新名称，则会显示默认名称"Saba Cloud"。
4. 选择 **"保存**"以激活 Microsoft Viva Learning 中的 Saba 云Microsoft Viva Learning。 内容可能需要 24 小时才能显示在 Viva Learning。

> [!Note]
> 对于 Saba 云集成，主机 URL 中 sabacloud.com 一个域。 如果你有不同的域名，你将需要提出支持票证以允许你的域名。

>[!NOTE]
>租户元数据集中存储在我们的数据存储中，而不是存储在特定于地理位置的数据存储中。

>[!NOTE]
>目前，组织内的所有用户都可以发现所有租户特定的课程，但他们只能使用他们有权访问的课程。 已针对将来版本规划基于角色和权限的用户特定内容发现。
