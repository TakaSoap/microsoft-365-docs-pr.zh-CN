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
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454669"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>将Microsoft Teams与 Canvas 一同使用

Microsoft Teams会议是 Learning Tools Interoperability (LTI) 应用，可帮助教师和学生轻松地在 Learning Management System (LMS) 和 Teams 之间导航。 用户可以直接从 LMS 中访问与其课程关联的课堂团队。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365管理员

在内部结构 Canvas 中管理 Microsoft Teams 集成之前，必须让 Microsoft Azure 租户中的机构 Microsoft Office 365 管理员批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用，然后再完成 Canvas 管理员设置。

1. 登录到 Canvas。

2. 选择全局 **导航** 中的"管理员"链接，然后选择您的帐户。

3. 在管理员导航中 **，选择**"设置"链接，然后选择"**集成"** 选项卡。

4. 输入你的 Microsoft 租户名称和登录属性。

   login 属性将用于将 Canvas 用户与用户Azure Active Directory关联。

5. 选择 **"完成设置** 更新"。

6. 若要批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用的访问权限，请选择"授予 **租户访问权限"** 链接。 你将被重定向到 Microsoft 标识平台管理员同意终结点。

   ![权限](media/permissions.png)

7. 选择 **接受**。

8. 通过打开Microsoft Teams启用同步。

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Canvas 管理

设置 Microsoft Teams LTI 1.3 集成。

作为 Canvas 管理员，你需要在你的环境中Microsoft Teams会议 LTI 应用。 记下应用的 LTI 客户端 ID。

 - Microsoft Teams会议 - 170000000000703

1. 访问 **管理员设置**  >  **应用**。

2. 选择 **+ 应用** 以添加Teams LTI 应用。

   ![external-apps](media/external-apps.png)

3. 为 **配置类型选择"** 按客户端 ID"。

   ![添加应用](media/add-app.png)

4. 输入提供的客户端 ID，然后选择"提交 **"。**

   你将注意到客户端 ID Microsoft Teams会议 LTI 应用名称进行确认。

5. 选择“安装”。

   the Microsoft Teams meetings LTI app will be added to the list of external apps.
   
## <a name="enable-for-canvas-courses"></a>启用画布课程

若要在课程内使用 LTI，Canvas 课程的讲师必须启用集成同步。每个课程必须由讲师启用，以创建Teams课程;没有用于创建全局Teams机制。 这是为防止创建不需要Teams设计。

请参考教师文档，以[](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)针对每个课程启用 LTI 并完成集成设置。
