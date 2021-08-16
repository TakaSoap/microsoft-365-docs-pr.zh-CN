---
title: 将Microsoft Teams与 Canvas 一同使用
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 将Microsoft Teams与 Canvas 集成
ms.openlocfilehash: 8091d84e1d0f26c820979450001a1e0c9ad1cdec775ac9e34317f69c24bd2df6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53898703"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>将Microsoft Teams与 Canvas 一同使用

Microsoft Teams课程是 Learning Tools Interoperability (LTI) 应用，可帮助教师和学生轻松地在 Learning Management System (LMS) 和 Teams 之间导航。 用户可以直接从 LMS 中访问与其课程关联的课堂团队。

## <a name="prerequisites-before-deployment"></a>部署前的先决条件

> [!NOTE]
> 当前的 Class Teams LTI 仅支持将 Canvas 用户与 Microsoft Azure Active Directory (AAD) 在有限范围内同步。 
> - 你的租户必须在 Canvas 字段与 Microsoft AAD (电子邮件、用户 ID 或 SIS ID) UPN 之间完全匹配。 我们正在努力扩展同步功能的灵活性，但与此同时，Canvas 中与 AAD 中的 UPN 不匹配的任何用户将不会添加到与 Canvas 同步的 Teams 类。 
> - 只有一个 Microsoft 租户可用于在 Canvas 和 Microsoft 之间映射用户。
> - 在将 Class Teams LTI 之前，必须关闭 SDS，以避免重复组。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365管理员

在内部结构 Canvas 中管理 Microsoft Teams 集成之前，必须让 Microsoft Azure 租户中的机构 Microsoft Office 365 管理员批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用，然后再完成 Canvas 管理员设置。

1. 登录到 Canvas。

2. 选择全局 **导航** 中的"管理员"链接，然后选择您的帐户。

3. 在管理员导航中 **，选择**"设置"链接，然后选择"**集成"** 选项卡。

4. 通过Microsoft Teams启用"同步"。

   ![teams-sync](media/teams-sync.png)

5. 输入你的 Microsoft 租户名称和登录属性。

   login 属性将用于将 Canvas 用户与用户Azure Active Directory关联。

6. 选择 **"完成设置** 更新"。

7. 若要批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用的访问权限，请选择"授予 **租户访问权限"** 链接。 你将被重定向到 Microsoft 标识平台管理员同意终结点。

   ![权限](media/permissions.png)

8. 选择“**接受**”。

## <a name="canvas-admin"></a>Canvas 管理

设置 Microsoft Teams LTI 1.3 集成。

作为 Canvas 管理员，你需要在你的环境中添加Microsoft Teams类 LTI 应用。 访问主帐户中的"开发人员密钥"列表，切换到继承的密钥，Teams LTI 工具。 记下应用的 LTI 客户端 ID。

 - Microsoft Teams类 - 170000000000570

1. 访问 **管理员设置**  >  **应用**。

2. 选择 **+ 应用** 以添加Teams LTI 应用。

   ![external-apps](media/external-apps.png)

3. 为 **配置类型选择"** 按客户端 ID"。

   ![添加应用](media/add-app.png)

4. 输入提供的客户端 ID，然后选择"提交 **"。**

   你会注意到客户端 ID 的Microsoft Teams LTI 应用名称，用于确认。

5. 选择“安装”。

   the Microsoft Teams classes LTI app will be added to the list of external apps.
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>为 Canvas 课程启用 LTI 应用

若要在课程内使用 LTI 应用，Canvas 课程的讲师必须启用集成同步。每个课程必须由讲师启用，以创建相应的团队;没有用于团队创建的全球机制。 这是为了防止创建不需要的团队的预防措施。

请查阅教师文档，[](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)以针对每个课程启用 LTI 应用并完成集成设置。
