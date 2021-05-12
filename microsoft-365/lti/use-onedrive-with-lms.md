---
title: 使用 OneDrive 学习工具互操作性
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
description: 使用新的 OneDrive 学习工具互操作性应用创建作业并评分作业、生成和制作课程内容，并实时协作处理文件。
ms.openlocfilehash: 97baf3e524e483e879d00f5e0c8495b450e13c92
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327683"
---
# <a name="use-microsoft-onedrive-with-your-learning-management-system"></a>将 Microsoft OneDrive 与学习管理系统一同使用

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

了解将 Microsoft OneDrive 与学习管理系统与 LMS (一) 。

**将 Microsoft Office 365 直接引入工作流**

Microsoft OneDrive 学习工具互操作性 (LTI) 应用与 LMS 集成，将 Microsoft OneDrive 和 Microsoft Office 365 直接引入最重要的工作流，包括：

- 附加资源并组织内容。
- 启动协作文档。
- 创建工作分配并评分。

**安全且完全符合最新的 LTI 标准**

Microsoft OneDrive LTI 应用与 LTI 1.3 和 LTI 优势兼容。 此优势可实现高度安全且紧密集成的用户体验。

**新式和丰富用户体验**

Microsoft OneDrive LTI 应用将 Microsoft 的最佳功能融入到 LMS 体验中。 我们正在改进 LMS 中的现有 Office 365 集成，提供更现代用户体验，包括新的扩展 Microsoft OneDrive 文件选取器以及更丰富的 Office 文件编辑体验。 今后，Microsoft 还将完全拥有 Microsoft OneDrive LTI 应用，这意味着你始终可以自动从 Microsoft 获得最新且最最好的应用。

Microsoft OneDrive LTI 应用允许你：

- 从丰富内容编辑器附加 Office 365 文件，包括 Word 文档、PowerPoint 演示文稿和 Excel。

- 分发 Office 365 云分配。

- 查看和组织你的个人和课程 Microsoft OneDrive 文件。

- 创建协作，课程成员可以实时协作处理共享文档。

- 访问多个 Microsoft OneDrive 帐户，包括个人帐户和学校帐户。

- 将 Office 365 文件与课程模块集成。

- 使用 Microsoft 帐户对 LMS 进行单一登录。

## <a name="integrate-with-canvas"></a>与 Canvas 集成

执行此集成的人应是 Canvas 的管理员和 Microsoft 365 租户的管理员。

1. 使用租户管理员帐户登录到 Microsoft Azure 门户。 Azure 租户管理员还应具有组管理员角色。

    ![突出显示的组管理员](../media/lti-media/lti-group-admin.png)

2. 登录到 Microsoft [OneDrive LTI 门户](https://odltiappnl.azurewebsites.net/admin)。

3. 接受权限以完成登录。

    ![接受权限](../media/lti-media/lti-permissions.png)

4. 选择 **"添加 LTI 租户"。**

     ![添加 LTI 租户](../media/lti-media/lti-add-tenant.png)

5. 从 **下拉列表中选择 LTI 消费者****平台作为画布**。

6. 选择 **"画布基 URL"，** 然后选择"下一 **步"。**

    ![选择"画布"并添加基 URL](../media/lti-media/lti-canvas-base-url.png)

   下一个屏幕将显示对你有机密的字段。

7. Select **Next** from ？？ page. 审阅者可以在此处填写空白吗？

8. 在 **显示** 机密信息的屏幕上选择"下一步"。

   Azure 门户的最终屏幕显示添加 Canvas 实例的以下步骤。

9. 从此屏幕复制开发人员密钥。 你将在创建 Canvas 实例时使用。

## <a name="add-the-canvas-instance"></a>添加 Canvas 实例

1. 在 Canvas 实例中，取消选择 **"管理员**  >  **开发人员密钥"。**

2. 在 **"开发人员密钥"下拉列表中选择"LTI** **密钥"。**

   ![获取 LTI 开发人员密钥](../media/lti-media/lti-developer-keys.png)

3. 在此处粘贴开发人员密钥。

     ![粘贴开发人员密钥](../media/lti-media/lti-developer-keys.png)

   密钥在 **OFF** 模式下创建

   ![在关闭模式下创建的开发人员密钥](../media/lti-media/lti-copy-developer-keys.png)

4. 复制突出显示的文本。
    这充当 Microsoft OneDrive LTI 门户中的客户端 ID。

5. 将文本粘贴到 Microsoft OneDrive LTI 门户的"客户端 **ID"** 字段中，然后选择"下一 **步"。**

6. 选择“**保存**”。

7. 通过选择查看 **LTI 租户查看设置**。
