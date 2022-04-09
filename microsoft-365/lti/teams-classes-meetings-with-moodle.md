---
title: 将Microsoft Teams类和会议与 Moodle 集成
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
description: 使用 Microsoft OneDrive Learning Tools Interoperability for Moodle 创建和管理Teams类和会议。
ms.openlocfilehash: 0eacbd846d4582312f8936e57c4f630836d9264c
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747381"
---
# <a name="integrate-microsoft-teams-classes-and-meetings-within-moodle"></a>在 Moodle 中集成Microsoft Teams类和会议

本指南提供有关在 Moodle 上注册Teams类和Teams会议 LTI 应用的 IT 管理员步骤。

有关管理任何 LMS 的所有 OneLTI 工具的详细信息，请参阅 [管理任何 LMS 的 Microsoft OneLTI](manage-microsoft-one-lti.md)。

## <a name="prerequisites-before-set-up"></a>设置前的先决条件

若要使 Moodle 与 Teams 之间的集成正常运行，必须设置 Moodle 和 Teams 以便彼此通信。

按照 [有关安装和配置 Moodle 插件的说明](moodle-plugin-configuration.md)操作。

## <a name="register-microsoft-onelti-tools-for-use-in-moodle"></a>注册 Microsoft OneLTI 工具以在 Moodle 中使用

> [!IMPORTANT]
> 执行此集成的人员应为 Moodle 管理员和Microsoft 365租户管理员。

1. 访问 [Microsoft LTI 门户](https://lti.microsoft.com/) ，然后选择 **“转到注册门户**”。

2. 使用Microsoft 365管理员帐户登录。

3. 登录后，选择 **“添加新注册**”。

4. 选择 **Teams会议 LTI** 或 **Teams类 LTI** 进行注册，然后选择 **“下一步**”。

5. 输入易于识别的 **注册** 名称，然后选择 **Moodle** 作为 LMS 平台。 选择 **下一步**。

6. 你将获得需要添加到 Moodle 网站的密钥列表。

7. 在另一个选项卡中打开 Moodle。请勿关闭 Microsoft LTI 门户选项卡。

8. 在 Moodle 中，转到 **Site** **administrationPluginsActivity** >  >  **模块External** >  **toolsManage** >  工具。

9. 在“ **管理工具** ”页上， **手动选择“配置工具**”。

10. 在 **“工具”设置** 下，输入 **工具名称****，如Microsoft Teams类**。 对于 **LTI 版本**，请选择 **LTI 1.3**。 对于 **公钥类型**，请选择 **“密钥集 URL**”。

11. 接下来，将 **密钥从 Microsoft LTI 密钥** 复制到相应的工具输入。
    1. Microsoft **的目标链接 URL** 密钥进入 Moodle 工具 **URL** 字段。
    1. Microsoft 的 **Open ID 连接 URL** 密钥进入 Moodle's **Initiate 登录 URL** 字段。
    1. Microsoft 的 **重定向 URL** 密钥进入 Moodle 的 **重定向 URI ()** 字段。

12. 选择“**保存更改**”。

13. 新工具现在应显示在 Moodle 的 **“管理工具**”页的 **“** 工具”部分中。 选择列表图标以查看 **工具配置详细信息**。

14. 返回到 Microsoft LTI 门户选项卡。选择 **“下一步**”转到 **LMS 提供的注册密钥** 步骤。

15. 将 Moodle **工具配置详细信息** 中的值复制并粘贴到 Microsoft 的 **LMS 提供的注册密钥** 步骤。

  按如下所示粘贴值：

  | 在穆德尔 | 在 Microsoft LTI 注册门户上 |
  | --------- | ------------------------------------ |
  | 平台 ID | 颁发者 ID URL |
  | 客户端 ID | 客户端 ID |
  | 部署 ID | 部署 ID |
  | 公钥集 URL | 密钥集 URL |
  | 访问令牌 URL | 访问令牌 URL |
  | 身份验证请求 URL | 平台身份验证 URL |

  选择 **下一步**。

16. 查看 **“审阅并添加** ”页面。 如果没有错误，请选择 **“保存”并退出**。 应会看到一条消息，指示注册成功。

你已完成Teams类或Teams会议 LTI 应用的注册。

如果还想添加其他应用，请重复上述步骤，在步骤 4 中选择其他Teams LTI 应用。

### <a name="add-teams-lti-tools-to-educators-moodle-courses"></a>向教师的 Moodle 课程添加Teams LTI 工具

注册Teams LTI 应用后，教师可以将Teams类应用和Teams会议应用添加到他们的 Moodle 课程。

- [教师关于添加Teams类应用的说明](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-ac6a1e34-32f7-45e6-b83e-094185a1e78a)。
- [有关添加Teams会议应用的教师说明](https://support.microsoft.com/topic/use-microsoft-teams-meetings-in-your-lms-11b6095d-f90b-42b9-ab77-4dcff2bb3b76)。
