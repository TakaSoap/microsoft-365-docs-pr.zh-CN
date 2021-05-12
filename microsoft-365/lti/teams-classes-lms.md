---
title: 使用Microsoft Teams管理系统中的课程
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 在Microsoft Teams管理系统中集成课程
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327703"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a>使用Microsoft Teams管理系统中的课程

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

Microsoft Teams课堂团队是学习工具互操作性 (LTI) 应用，可帮助教师和学生轻松地在学习管理系统 (LMS) 和 Teams 之间导航。 用户可以直接从 LMS 中访问与其课程关联的课堂团队。

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a>在租户中批准Microsoft Azure应用程序

以下任务由应用管理员和 Microsoft Office 365 Learn 超管理员完成。

在管理在Microsoft Office 365 Learn 超 中的集成之前，Microsoft Office 365管理员必须批准适用于机构 Microsoft Azure 租户的适用于 **Learn 超 Azure** 应用的适用于 Learn 超 Azure Teams。

1. 查找你的 Microsoft 租户 ID。 请参阅 [如何查找租户](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)。

2. 根据以下示例重定向 Microsoft Identity Platform Admin Consent 终结点：

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > 将 {tenant} 替换为组织的 Microsoft 租户 ID。

## <a name="register-the-integration-apps"></a>注册集成应用

作为一名 Learn 超管理员，你需要在测试环境中注册 2 个 LTI 1.3 集成应用：

- 为支持名单Teams进行集成

- Microsoft Teams课堂团队 LTI 应用

1. 记下这两个应用的以下 LTI 客户端 ID：

    - 美洲 - f1561daa-1b21-4693-ba90-6c55f1a0eb41

    - Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89

2. 访问管理面板，在 **"集成"下** 找到 LTI 工具提供程序。

   ![这是 LTI 工具提供程序对话框，显示提供程序列表](../media/lti-media/lti-tool-providers.png)

3. 选择 **"注册 LTI1.3/优势工具"。**

4. 输入提供的第一个客户端 ID (或 Microsoft) ，**然后选择提交。**

   ![LTI 注册工具，使用字段输入客户端 ID](../media/lti-media/register-tool.png)

5. 查看预填充的设置，并确保工具状态标记为已批准。

6. 滚动到底部，然后选择"提交 **"。**

7. 重复上述步骤，在环境中注册第二个 LTI 应用。

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a>设置 REST 应用程序和跨源资源共享

The 部署学习超管理员还需要配置 REST 应用程序和跨源资源共享配置。

完成以下操作以设置 REST 应用程序

1. 访问"了解管理工具"，然后从"集成" **部分选择"REST API** **集成** "。

2. 选择 **"创建集成"，** 然后输入与为"适用于集成 LTI"工具的"Teams/客户端 ID 相同的应用程序/客户端 ID。

3. 输入"了解用户 (这可能是你自己的学习管理员用户名) ， **或选择"** 浏览"查找。

4. 为 **"****最终用户访问"选择"是"。**

5. 选择 **"是****"以授权充当用户**

6. 选择 **"完成后** 提交"。

## <a name="set-up-cross-origin-resource-sharing"></a>设置跨源资源共享

1. 访问"了解管理工具"， **然后从** "集成"部分选择"跨 **源资源共享** "。

2. 选择 **"创建配置"。**

3. 在 `https://bb-ms-teams-ultra-ext.api.blackboard.com` 源中输入。

4. 在允许的标头中添加 **单词** **Authorization。**

5. 设置为 **"可用**"**为"是"。**

6. 选择 **"完成后** 提交"。

## <a name="enable-class-teams-in-blackboard-learn"></a>在"Teams中启用课堂学习"

启用 LTI 工具后，下一步是从你自己的 Teams 租户设置 Microsoft 类Microsoft Office 365集成。 为此，你可以按照以下步骤操作，作为"完成""学习""超"管理员。

1. 在 **"了解**  >  **管理工具和实用程序"中**，Microsoft Teams **集成管理员"。**

   ![包含可用工具列表的工具和实用程序对话框](../media/lti-media/tools-utilities.png)

2. 选中"启用"复选框 **Microsoft Teams。**

3. 输入 Microsoft O365 管理员下部分中引用的租户 ID

 > [!NOTE]
 > 在 O365 管理员批准应用之前，无法保存设置。请参阅[批准租户中的Microsoft Azure。](#approve-the-app-in-the-microsoft-azure-tenant)

4. 当全局 O365 管理员批准 Microsoft 租户中的"Teams应用程序"后，选择"提交 **"。**
