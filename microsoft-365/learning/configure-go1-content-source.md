---
title: 将 Go1 配置为网站内容Microsoft Viva Learning
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
description: 了解如何将 Go1 配置为适用于 Microsoft Viva Learning 的学习内容源。
ms.openlocfilehash: 1adef6275be2a8656eaad9a7f47805d13299e3c7
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950529"
---
# <a name="configure-go1-as-a-content-source-for-microsoft-viva-learning"></a>将 Go1 配置为网站内容Microsoft Viva Learning

本文演示如何在 Viva Learning 中将 Go1 配置为第三方学习内容源。

>[!NOTE]
>通过 Viva Learning的内容受 Microsoft 产品条款外的其他条款所规定。 Go1 内容和任何关联服务都受 Go1 的隐私和服务条款的约束。

Go1 提供对来自顶级内容提供商的数千个课程的访问权限。 [详细了解 Go1。](https://www.go1.com/go1-microsoft-viva) 按照以下步骤在 Viva Learning 中添加 Go1 作为学习Learning。

## <a name="configure-in-your-go1-portal"></a>在 Go1 门户中配置

>[!NOTE]
>你需要在 Go1 中拥有管理员权限才能完成这些步骤。

首先，你需要按照以下步骤在 Go1 门户中创建应用。 此应用将生成 API 密钥，可用于向 Go1 进行身份验证并请求 API。

1. 以管理员角色登录到 Go1 门户。

2. 从 **菜单选项** 中选择"集成"。

3. 选择 **"开发人员"。**
4. 选择" **创建应用"** 按钮。
5. 输入应用的名称，例如"My-go1-viva-integration"。
6. 输入回叫 URL，例如"Mycompany.mygo1.com"。
7. 保存您输入的信息。
8. 将显示你的信息，并隐藏"机密"。 选择省略号 (**...**) ，然后选择"查看密码"以显示密码。 
9. 复制以下值：

    - **客户端的主机 URL：** 这是 Go1 门户 URL。 它看起来像" https://mycompany.mygo1.com "。
    - **客户端 ID：** 可以在"集成/开发人员"菜单选项下的 Go1 门户 **中查找** ID。
    - **密码：** 可以在"集成/开发人员"菜单选项下的 Go1 门户 **中查找** 你的密码。

详细了解如何 [为 Go1 创建私有开发人员的应用](https://help.go1.com/en/articles/4642648-integrate-with-the-go1-api)。

## <a name="configure-in-your-microsoft-365-admin-center"></a>在部署中Microsoft 365 管理中心

>[!NOTE]
>你需要拥有管理员权限才能Microsoft 365这些步骤。

1. 登录到[你的Microsoft 365 管理中心。](https://admin.microsoft.com)
2. 导航到 **"设置"，** 再导航到"**组织设置"。** 选择"Viva Learning"，然后启用面板中的"Go1"。
3. 填写从 Go1 门户检索到的配置详细信息。
4. 选择 **"保存**"以激活 Viva Learning 中的 Go1 内容。 内容可能需要 24 小时才能显示在 Viva Learning应用中。
