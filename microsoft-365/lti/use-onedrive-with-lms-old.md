---
title: 使用 OneDrive Learning 工具互操作性
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
description: 使用新的 OneDrive Learning 互操作性应用创建和评级作业、构建和选择课程内容，并实时协作处理文件。
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256936"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>将 Microsoft OneDrive LTI 与 Canvas 一同使用

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

## <a name="integrate-with-canvas"></a>与 Canvas 集成

执行此集成的人应是 Canvas 的管理员和 Microsoft 365 管理员。

1. 使用租户管理员Microsoft Azure登录租户门户。 Azure 租户管理员还应具有组管理员角色。

    ![突出显示的组管理员](../media/lti-media/lti-group-admin.png)

2. 登录到 Microsoft OneDrive [LTI 门户](https://odltiappnl.azurewebsites.net/admin)。

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
    在 LTI 门户中，Microsoft OneDrive客户端 ID。

5. 将文本粘贴到 LTI 门户Microsoft OneDrive"客户端 **ID"** 字段中，然后选择"下一 **步"。**

6. 选择“**保存**”。

7. 通过选择查看 **LTI 租户查看设置**。
