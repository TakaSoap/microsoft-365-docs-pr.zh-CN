---
title: 将 Microsoft OneDrive LTI 与 Blackboard 集成
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
description: 使用新的 Microsoft OneDrive Learning Tools Interoperability for Blackboard 创建和分级分配、生成和策划课程内容，以及实时协作处理文件。
ms.openlocfilehash: 7e43ff51a069db55be06236fb0318aa4453d8feb
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824643"
---
# <a name="integrate-microsoft-onedrive-lti-with-blackboard"></a>将 Microsoft OneDrive LTI 与 Blackboard 集成

将 Microsoft OneDrive LTI 与 Blackboard 集成是一个双重过程。 第一步使Microsoft OneDrive LTI 在 Blackboard 课程中可用，第二步为 Blackboard 启用Microsoft OneDrive。

> [!IMPORTANT]
> 执行此集成的人员应是 Blackboard 的管理员和Microsoft 365租户的管理员。

## <a name="recommended-browser-settings"></a>建议的浏览器设置

- 应允许使用 Cookie 进行Microsoft OneDrive。
- 不应为Microsoft OneDrive阻止弹出窗口。

> [!NOTE]
>
> - 默认情况下，在 Chrome 浏览器隐身模式下不允许 Cookie，并且需要允许。
> - Microsoft OneDrive LTI 在Microsoft Edge浏览器的专用模式下工作。 确保未阻止默认) 允许的 cookie (。

## <a name="register-the-onedrive-lti-13-tool-in-blackboard"></a>在 Blackboard 中注册 OneDrive LTI 1.3 工具

1. 在 Blackboard 的管理员面板中，选择 **LTI 工具提供程序**。
2. 选择 **“注册 LTI 1.3 工具**”。
3. 在“客户端 ID”字段中，键入或复制并粘贴此 ID： ``78cd1b1c-ccbd-4318-9f90-22241f63b1f5``

   > [!NOTE]
   > 添加此客户端 ID 将在 Blackboard 中配置两个不同的位置：一种是允许从内容市场、书籍和工具以及富文本编辑器访问该工具，另一种允许从超级课程在线课程的“添加内容”菜单访问该工具。

4. 选择“**提交**”。
5. 查看 **“工具状态** ”视图中所有预填充的设置，并确保选择的 **“工具状态** ”圆形按钮已 **获批准**。
6. 在 **“机构策略**”中，依 **次选择“角色** ”和要发送的用户字段中的 **“名称** ”复选框。 所有其他用户字段都是可选的，但建议将它们保留在将来证明安装OneDrive。
7. **目前，允许等级服务访问** 和 **允许成员身份服务访问** 也是可选的，但将来可能需要更新 LTI 工具。
8. 复制 **部署 ID**。 需要它来配置 Microsoft LTI 工具。
9. 选择要完成的 **“提交** ”按钮。

## <a name="configure-the-microsoft-lti-tool-to-work-with-blackboard"></a>配置 Microsoft LTI 工具以使用 Blackboard

1. 登录[到 Microsoft OneDrive LTI 注册门户](https://onedrivelti.microsoft.com/admin)。
2. 选择 **“管理员同意** ”按钮并接受权限。

> [!CAUTION]
> 如果未执行此步骤，以下步骤将给你一个错误，并且一旦收到错误，你将无法执行此步骤一小时。

3. 选择 **“新建 LTI 租户** ”按钮。
4. 在“LTI 注册”页上，从 LTI 使用者平台下拉列表中选择 **Blackboard** ，然后选择“ **下一步** ”按钮。
5. 粘贴在 Blackboard 中注册工具时复制的 **部署 ID** ，然后选择 **“下一步**”。
6. 查看并保存所做的更改。 成功注册后将显示一条消息。
7. 也可以通过在主页上选择 **“查看 LTI 租户** ”按钮来查看注册详细信息。

完成这些步骤后，讲师可以在课程内容页中使用“plus”菜单时打开OneDrive文档。

## <a name="recommended-content"></a>建议的内容

[Microsoft Integrations for Blackboard](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft)

[Microsoft Teams类集成](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Microsoft_Classes)
