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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: 将Microsoft Teams与 Canvas 集成
ms.openlocfilehash: 529cc27b6b63fca76d47487f26bd6deda7478640
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569570"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>将Microsoft Teams与 Canvas 一同使用

Microsoft Teams会议是 Learning Tools Interoperability (LTI) 应用，可帮助教师和学生轻松地在 Learning Management System (LMS) 和 Teams 之间导航。 用户可以直接从其 LMS 内部访问与其课程关联的课堂团队。

## <a name="prerequisites-before-deployment"></a>部署前的先决条件

> [!NOTE]
> 当前Teams会议 LTI 仅支持将 Canvas 用户与Microsoft Azure Active Directory (AAD) 范围进行同步。
>
> - 你的租户必须具有 Microsoft 教育版许可证。
> - 只有一个 Microsoft 租户可用于在 Canvas 和 Microsoft 之间映射用户。
> - 在使用 Class) LTI 之前学校数据同步 (SDS Teams，以避免重复组。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365管理员

在内部结构 Canvas 中管理 Microsoft Teams 集成之前，必须让 Microsoft Azure 租户中机构 Microsoft Office 365 管理员批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用，然后再完成 Canvas 管理员设置。

1. 登录到 Canvas。

2. 选择全局 **导航** 中的"管理员"链接，然后选择您的帐户。

3. 在管理导航中 **，选择"** 设置"链接，然后选择"**集成"** 选项卡。

   ![Canvas Teams Sync Updated png.](https://user-images.githubusercontent.com/87142492/128552407-78cb28e9-47cf-4026-954d-12dc3553af6f.png)

4. 输入你的 Microsoft 租户名称、登录属性、域后缀AAD查找属性。 这些字段将用于在 Canvas 中将用户与 Microsoft Azure Active Directory。
   - Login 属性是用于匹配的 Canvas 用户属性。
   - 后缀字段是可选的，当 Canvas 属性和 Microsoft 自定义字段之间没有精确映射时，你可以指定AAD域。 例如，如果你的 Canvas 电子邮件是"name@example.edu"，而 Microsoft AAD 中的 UPN 是"name"，则可以通过在后缀字段中输入"example.edu"来匹配用户。
   - Active Directory Lookup 属性是 Microsoft 端与 Canvas 属性匹配的字段。 在 UPN、主电子邮件地址或电子邮件别名之间选择。

5. 选择 **"完成设置** 更新"。

6. 若要批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用的访问权限，请选择"授予 **租户访问权限"** 链接。 你将被重定向到 Microsoft 标识平台管理员同意终结点。

   ![权限。](media/permissions.png)

7. 选择“**接受**”。

   > [!NOTE]
   > 同步是由 LMS 合作伙伴管理的一项功能，用于使用 Microsoft graph API 将课程级别的成员身份Teams团队同步。 这主要是教师在课程级别切换为 true 的功能。 随后，在 LMS 端为添加或删除成员所做的任何成员身份更改都使用 LMS 合作伙伴实现的 Sync 进行反映。 即使在为教师启用此过程之前，M365 教育协会管理员也允许教师使用下面的同步权限模式访问同步。 这些权限授予 LMS 合作伙伴，以便教师能够同步 LMS 课程和课堂Teams成员身份。

8. 通过打开Microsoft Teams启用同步。

   ![teams-sync。](media/teams-sync.png)

## <a name="canvas-admin"></a>Canvas 管理

设置 Microsoft Teams LTI 1.3 集成。

作为 Canvas 管理员，你需要在你的环境中Microsoft Teams会议 LTI 应用。 记下应用的 LTI 客户端 ID。

 - Microsoft Teams会议 - 170000000000703

1. Access **Admin** **settingsApps** > .

2. 选择 **+ 应用** 以添加Teams LTI 应用。

   ![外部应用。](media/external-apps.png)

3. 为 **配置类型选择"** 按客户端 ID"。

   ![添加应用。](media/add-app.png)

4. 输入提供的客户端 ID，**然后选择提交。**

   你将注意到客户端 ID Microsoft Teams会议 LTI 应用名称进行确认。

5. 选择“**安装**”。

   the Microsoft Teams meetings LTI app will be added to the list of external apps.

6. 通过导航到 Canvas 管理员帐户中的开发人员密钥、选择继承的项，然后为会议打开"打开"Microsoft Teams应用。

## <a name="enable-for-canvas-courses"></a>启用画布课程

若要在课程内使用 LTI，Canvas 课程的讲师必须启用集成同步。每个课程必须由讲师启用，Teams创建相应的课程;没有用于创建课程的Teams机制。 这是为防止创建不需要Teams设计。

请参考教师文档，以[](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)针对每个课程启用 LTI 并完成集成设置。
