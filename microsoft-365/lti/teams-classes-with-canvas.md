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
ms.openlocfilehash: 08edb2065cd91ccb0e0d52290dfe83f8a3e60392
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568995"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>将Microsoft Teams与 Canvas 一同使用

Microsoft Teams课程是 Learning Tools Interoperability (LTI) 应用，可帮助教师和学生轻松地在 Learning Management System (LMS) 和 Teams 之间导航。 用户可以直接从其 LMS 内部访问与其课程关联的课堂团队。

## <a name="prerequisites-before-deployment"></a>部署前的先决条件

> [!NOTE]
> 当前的 Teams 类 LTI 仅支持将 Canvas 用户与 Microsoft Azure Active Directory (AAD) 在有限范围内同步。
>
> - 租户必须具有 Microsoft 教育版许可证 (A1 或更高版本) 。
> - 只有一个 Microsoft 租户可用于在 Canvas 和 Microsoft 之间映射用户。
> - 租户必须完全匹配 Canvas 字段 (电子邮件、唯一用户 ID、SIS ID 或集成 ID) 以及 AAD (用户主体名称 (UPN) 、主电子邮件地址 (邮件) 或电子邮件别名 (mailNickname) ) 中的字段。
> - 如果使用 SDS 创建类和组，我们建议在 SDS 中禁用团队创建选项，并执行组清理以避免类重复[](/schooldatasync/group-cleanup)。 SDS 仍可用于同步组织和用户数据。

## <a name="enable-the-microsoft-teams-app-in-canvas"></a>在 Canvas Microsoft Teams应用

若要开始集成，你需要通过启用开发人员密钥、启用 Microsoft Teams 同步和批准 Microsoft-Teams-Sync-for-Canvas 应用在 Canvas 中启用应用。 请注意，批准应用仅能由可以批准应用的 Microsoft 租户管理员执行。

**若要启用Microsoft Teams同步并批准应用的访问权限：**

1. 以管理员角色登录到 Canvas。

2. 选择全局 **导航** 中的"管理员"链接，然后选择您的帐户。
3. 在管理员导航中，选择 **"开发人员密钥** "链接，然后选择" **继承"** 选项卡。
4. 通过选择每个相应应用的 **"打开** "状态，启用你要部署的 LTI 应用。

5. 在管理导航中 **，选择"** 设置"链接，然后选择"**集成"** 选项卡。

6. 通过Microsoft Teams启用"同步"。 此同步允许基于课程Teams在课程中创建课程。

   ![Canvas Teams Sync Updated png.](https://user-images.githubusercontent.com/87142492/128225881-abdfc52d-dc9e-48ad-aec5-f6617c6436f3.png)

7. 使用相应的信息填写以下字段。 这些字段将用于在 Canvas 中将用户与 AAD。
   - 租户 **名称** 是 Microsoft 租户名称。
   - Login **属性** 是以下 Canvas 用户属性之一，用于映射：
      - **电子邮件** 是 Canvas 用户的默认电子邮件地址。 如果用户在 Canvas 中更改其默认电子邮件地址，则可能会阻止他们在课程的注册同步Teams。
      - **唯一用户 ID** 是用户的 Canvas 登录 ID。
      - **SIS 用户 ID** 是从学生信息系统 (SIS) 中填充的 ID 值，并且可查看用户配置文件页面。
      - **集成 ID** 仅通过 SIS 导入进行填充，并且只能在用户配置文件页面上查看。 通常，此唯一标识符由机构提供，用于帐户信任或联盟情况，以跨多个帐户标识用户。

   - **后缀字段** 是可选的，当 Canvas 属性和 Microsoft 属性之间没有精确映射时，你可以指定AAD字段。 例如，如果 Canvas 电子邮件是"name@example.edu"，而 Microsoft AAD 中的 UPN 是"name"，则可以通过在后缀字段中输入"@example.edu"来匹配用户。 应在此字段中输入域，并加上前面的 @。
   - Active Directory Lookup 属性是 Canvas 属性AAD中的字段。 在 UPN、主电子邮件地址或电子邮件别名之间选择。

8. 选择 **"更新设置**"。

9. 若要批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用的访问权限，请选择"授予 **租户访问权限"** 链接。 你将被重定向到 Microsoft 标识平台管理员同意终结点。

   ![权限。](media/permissions.png)

   > [!NOTE]
   > 此步骤必须由可以批准应用的 Microsoft 租户管理员执行。

10. 选择“**接受**”。

## <a name="integrate-teams-classes-lti-in-canvas"></a>将Teams类 LTI 集成在 Canvas 中

启用同步和批准 Azure 应用后，Canvas 管理员现在可以将 Teams 类 LTI 应用添加到 Canvas 环境，以便它将显示在 Canvas 用户界面的导航中。

**若要将Teams LTI 应用添加到 Canvas 环境**：

1. 在"管理 **设置"****中的"** 应用"选项卡上，选择 **"+ 应用**"以Teams LTI 应用。

   ![外部应用。](media/external-apps.png)

2. 对于 **"配置类型**"，选择 **"按客户端 ID"**。

   ![添加应用。](media/add-app.png)

3. 对于 **"客户端 ID**"，**170000000000570**"Microsoft Teams"LTI"，然后选择"提交 **"**。

4. 在出现的确认中，验证应用名称 (Microsoft Teams类) ，然后选择"安装 **"**。

   现在Microsoft Teams类 LTI 应用添加到外部应用列表中。

## <a name="enabling-the-lti-app-for-canvas-courses"></a>为 Canvas 课程启用 LTI 应用

若要在课程内使用 LTI 应用，Canvas 课程的讲师必须启用集成同步。每个课程必须由讲师启用，以创建相应的团队;没有用于团队创建的全球机制。 这是为了防止创建不需要的团队的预防措施。

请查阅教师文档，[](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)以针对每个课程启用 LTI 应用并完成集成设置。
