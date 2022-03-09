---
title: 将 Microsoft OneDrive LTI 与 Microsoft OneDrive 集成
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: 使用适用于 Microsoft OneDrive Learning 的新工具互操作性创建和评级作业、构建和选择课程内容，并实时协作处理文件。
ms.openlocfilehash: 94e77181244bbf02115bd706e86751a9382b906b
ms.sourcegitcommit: a9266e4e7470e8c1e8afd31fef8d266f7849d781
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2022
ms.locfileid: "63406510"
---
# <a name="integrate-microsoft-onedrive-lti-with-blackboard"></a>将 Microsoft OneDrive LTI 与 Microsoft OneDrive 集成

将 Microsoft OneDrive LTI 与改进是一个两步过程。 第一步是在Microsoft OneDrive中提供 LTI，第二步为Microsoft OneDrive启用 LTI。

> [!IMPORTANT]
> 执行此集成的人应是具有该租户的管理员和 Microsoft 365 管理员。

## <a name="recommended-browser-settings"></a>建议的浏览器设置

- 应允许 Cookie 用于Microsoft OneDrive。
- 不应阻止弹出窗口进行Microsoft OneDrive。

> [!NOTE]
>
> - 默认情况下，在 Chrome 浏览器隐身模式下不允许 Cookie，并且将需要允许 Cookie。
> - Microsoft OneDrive LTI 在专用模式下在专用Microsoft Edge运行。 确保未阻止默认情况下 (允许的 cookie) 。

## <a name="register-the-onedrive-lti-13-tool-in-blackboard"></a>在OneDrive注册 LTI 1.3 工具

1. 在"用户管理员面板"中，选择 **"LTI 工具提供程序"**。
2.  **SelectRegister LTI 1.3 工具**。
3. 在"客户端 ID"字段中，键入或复制并粘贴此 ID： ``78cd1b1c-ccbd-4318-9f90-22241f63b1f5``

  > [!NOTE]
  > 添加此客户端 ID 将在英语中配置两个不同的位置：一个允许从内容市场、书籍和工具以及格式文本编辑器访问该工具，另一个允许从超课程在线课程的"添加内容"菜单中访问该工具。

4. 选择“**提交**”。
5. Review all pre-populated settings in  **theTool Statusview** ， and make sure the **Tool Status** round button selected  **isApproved**.
6.  **InInstitution Policies**， select the **Role in course** and the **Name** checkboxes in the user fields to send. 所有其他用户字段都是可选的，但建议保留它们，以在将来证明您的OneDrive安装。
7. **允许成绩服务访问** 和  **Allow 成员资格服务访问** 目前也是可选的，但将来可能需要对 LTI 工具进行更新。
8. 复制 **部署 ID**。 你将需要它来配置 Microsoft LTI 工具。
9. 选择" **提交"** 按钮完成。

## <a name="configure-the-microsoft-lti-tool-to-work-with-blackboard"></a>将 Microsoft LTI 工具配置为与 Microsoft 合作

1. 登录到 Microsoft OneDrive [LTI 注册门户](https://onedrivelti.microsoft.com/admin)。
2. 选择 **"管理员同意"** 按钮并接受权限。

> [!CAUTION]
> 如果未执行此步骤，则以下步骤将出现错误，一旦获得错误，你将无法在一小时内执行此步骤。

3. 选择" **新建 LTI 租户"** 按钮。
4. 在"LTI 注册"页上，从"LTI 消费者平台"下拉列表中选择 **"完成** "，然后选择"下一 **步"** 按钮。
5. 粘贴 **在部署中** 注册工具时复制的部署 ID，然后选择下一 **步**。
6. 查看并保存更改。 成功注册后将显示一条消息。
7. 还可通过选择主页上的"查看 **LTI** 租户"按钮来查看注册详细信息。

完成这些步骤后，当教师使用"课程内容"OneDrive"加号"菜单时，他们将能够从该页面打开文档。

## <a name="recommended-content"></a>建议的内容

[适用于 Microsoft 的 Microsoft 集成](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft)

[Microsoft Teams类集成](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft_Classes)
