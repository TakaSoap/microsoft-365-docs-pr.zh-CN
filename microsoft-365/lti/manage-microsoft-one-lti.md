---
title: 管理任何 LMS 的 Microsoft OneLTI
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
description: 了解如何执行关键的 Microsoft OneLTI 管理任务，包括查看、删除、编辑和故障排除。
ms.openlocfilehash: 8b788028a453969f13c31bbe72962c1b7df955a6
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823455"
---
# <a name="manage-microsoft-onelti-for-any-lms"></a>管理任何 LMS 的 Microsoft OneLTI

Microsoft OneLTI 与多个 LMS 集成，包括 Canvas、Blackboard 和 Moodle。

在本文中，IT 管理员将找到有关关键 OneLTI 管理任务的说明。

- [查看 LTI 注册](#view-an-lti-registration)。
- [删除 LTI 注册](#delete-an-lti-registration)。
- [编辑 LTI 注册](#edit-an-lti-registration)。
- [排查 OneLTI 的问题](#troubleshoot-issues-with-onelti)。
- [报告 OneLTI 的问题](#report-problems-with-onelti)。

## <a name="view-an-lti-registration"></a>查看 LTI 注册

若要查看 LTI 注册的详细信息，请按照以下步骤操作。

1. 访问 [Microsoft LTI 门户](https://lti.microsoft.com/)。
2. 使用Microsoft 365管理员帐户登录。
3. 在注册列表中，找到要查看的 LTI 注册。
4. 选择列表旁边的 **“眼睛”图标** 。
5. 将打开注册详细信息面板。

## <a name="delete-an-lti-registration"></a>删除 LTI 注册

如果要删除 Microsoft OneLTI 注册，请执行以下步骤。

1. 访问 [Microsoft LTI 门户](https://lti.microsoft.com/)。
2. 使用Microsoft 365管理员帐户登录。
3. 在注册列表中，找到要删除的 LTI 注册。
4. 选择列表旁边的 **垃圾桶图标** 。
5. 在确认对话框中，选择 **“删除** ”以确认删除。
6. 删除成功消息后，你将看到该消息。

## <a name="edit-an-lti-registration"></a>编辑 LTI 注册

目前，我们不支持在添加现有 LTI 注册后对其进行编辑。

若要更改 LTI 注册，需要：

1. [删除现有注册](#delete-an-lti-registration)。
2. 添加新注册。

## <a name="troubleshoot-issues-with-onelti"></a>排查 OneLTI 问题

如果你或你的教育工作者遇到 Microsoft OneLTI 的问题，下面是你可以执行的一些操作来进行故障排除。

### <a name="issues-while-launching-an-lti-tool-from-the-lms"></a>从 LMS 启动 LTI 工具时出现的问题

教师在 LMS 中启动 Microsoft LTI 工具时可能会遇到问题。

如果是这样，下面是一些常见问题以及如何解决这些问题。

- **找不到 Cookie**
  - 在浏览器设置中，需要允许 **LMS URL** 使用第三方 Cookie。
  - 这些 Cookie 需要根据 IMS 规范完成 LTI 1.3 握手。

- **找不到注册详细信息**
  - 如果 LTI 工具的注册未完成，或者在 OneLTI 管理门户中删除了注册，则会发生此问题。
  - IT 管理员需要完成 LTI 工具的注册。

- **LMS 中的一些详细信息无效**
  - 当从工具启动请求中的 LMS 发送的详细信息与 IMS LTI 1.3 规范不一致时，会发生此问题。
  - 如果问题仍然存在，IT 管理员将需要联系 [Microsoft 的教育支持团队](https://edusupport.microsoft.com/support?product_id=lti_apps&platform_id=web) 。

### <a name="issues-with-signing-in-to-the-registration-portal"></a>登录注册门户时出现的问题

登录到 Microsoft LTI 注册门户时，访问注册页时可能会出现问题或收到登录错误。

下面是一些常见的登录问题以及如何解决这些问题。

- **授权错误**
  - 如果看到错误消息“你的帐户无权访问此页面”，则为：
    - 该帐户不属于已注册的租户，或者
    - 该帐户不属于教师或管理员。

  - 对于这两种情况，你将看到“ **注销&切换帐户** ”按钮。
    - 选择此按钮或选择用户配置文件菜单下的 **“注销** ”按钮。
    - 使用属于租户、教师或管理员的帐户登录。

  - 如果租户未注册，则 IT 管理员必须在尝试注册 LTI 集成之前对其进行注册。

  - 如果尝试这些步骤后，仍会看到此错误，然后注销并再次登录。
    - 还可以清除 LTI 注册门户和本地存储的 Cookie 和 `https://login.microsoftonline.com/`本地存储。
    - 尝试再次登录。
    - 如果问题仍然存在，请在右上角选择 **“报告问题** ”链接来报告问题。

- **身份验证错误**
  - 如果看到错误消息“身份验证失败。 重试，“登录会话可能已过期。
    - 注销并再次登录。
    - 还可以清除 LTI 注册门户和本地存储的 Cookie 和 `https://login.microsoftonline.com/`本地存储。
    - 尝试再次登录。
    - 如果问题仍然存在，请在右上角选择 **“报告问题** ”链接来报告问题。

- **其他错误**
  - 对于所有其他错误，你将看到错误消息“出现错误。 稍后再试。
    - 这可能是内部处理错误。
    - 几个小时后再次尝试登录。
      - 选择“ **转到主页** ”按钮。 这会导航回登陆页。
      - 选择 **“转到注册门户** ”按钮以返回到 LTI 注册门户。

## <a name="report-problems-with-onelti"></a>报告 OneLTI 的问题

若要报告任何问题或提交 Microsoft OneLTI 的反馈，请执行以下步骤。

1. 在 Microsoft OneLTI 注册门户中，选择页面标题中的 **问号图标** 。
2. 在下拉列表中，选择 **“报告问题**”。
3. 将打开“Microsoft 教育支持”页。 使用Microsoft 365凭据登录。
4. 填写表单并提交。
