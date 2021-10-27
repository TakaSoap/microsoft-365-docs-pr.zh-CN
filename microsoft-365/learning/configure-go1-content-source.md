---
title: 将 Go1 配置为网站内容Microsoft Viva Learning
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
description: 了解如何将 Go1 配置为适用于 Microsoft Viva Learning 的学习内容源。
ROBOTS: NOINDEX
ms.openlocfilehash: ade44c0cc7607ab1b7a247ee60bdd2ca3505e6e9
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586157"
---
# <a name="configure-go1-as-a-content-source-for-microsoft-viva-learning"></a>将 Go1 配置为网站内容Microsoft Viva Learning

>[!NOTE]
>此功能在预览版中不受支持。

本文演示如何在 Viva Learning 中将 Go1 配置为第三方学习内容源。

>[!NOTE]
>通过 Viva Learning的内容受 Microsoft 产品条款外的其他条款所规定。 Go1 内容和任何关联服务都受 Go1 的隐私和服务条款的约束。

Go1 提供对来自顶级内容提供商的数千个课程的访问权限。 [详细了解 Go1。](https://www.go1.com/go1-microsoft-viva) 按照以下步骤在 Viva Learning 中添加 Go1 作为学习Learning。

## <a name="create-a-developers-app-in-go1"></a>在 Go1 中创建开发人员的应用

首先，你需要按照以下步骤在 Go1 门户中创建应用。 此应用将生成 API 密钥，可用于向 Go1 进行身份验证并请求 API。

1. 以管理员角色登录到 Go1 门户。

2. 从 **菜单选项** 中选择"集成"。

3. 选择 **"开发人员"。**

    <!--![Image of the Developers option in the Integrations menu.](../media/learning/go1-1.png)-->

4. 选择" **创建应用"** 按钮。

    <!--![Image of the Create App button.](../media/learning/go1-2.png)-->

5. 输入应用的名称，例如"My-go1-viva-integration"。

6. 输入回叫 URL，例如"Mycompany.mygo1.com"。

    <!--![Image of the field where you enter the name and callback URL.](../media/learning/go1-3.png)-->

7. 保存您输入的信息。

8. 将显示你的信息，并隐藏"机密"。 选择省略号 (**...) ，** 然后选择" **查看** 密码"以显示密码。

9. 复制以下值：

    - **客户端的主机 URL：** 这是 Go1 门户 URL。 它看起来像" https://mycompany.mygo1.com "。
    - **客户端 ID：** 可以在"集成/开发人员"菜单选项下的 Go1 门户 **中查找** ID。
    - **密码：** 可以在"集成/开发人员"菜单选项下的 Go1 门户 **中查找** 你的密码。

## <a name="complete-configuration-in-the-microsoft-365-admin-center"></a>完整配置Microsoft 365 管理中心

将从 Go1 门户检索到的值复制并粘贴到"开始"屏幕中的"Go1 设置"Microsoft 365 管理中心。

详细了解如何 [为 Go1 创建私有开发人员的应用](https://help.go1.com/en/articles/4642648-integrate-with-the-go1-api)。
