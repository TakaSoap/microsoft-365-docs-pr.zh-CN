---
title: 开始使用应用治理
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 开始使用应用治理功能来治理你的应用。
ms.openlocfilehash: d4bf5314772ab37c2b79c1895e3094fdb2b66593
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2021
ms.locfileid: "53594906"
---
# <a name="get-started-with-app-governance-in-preview"></a>开始使用应用治理（预览版）

开始使用 Microsoft Cloud App Security 的应用治理附加产品:

1. 验证账户是否有适当的许可级别。应用治理是 Microsoft Cloud App Security (MCAS) 的附加功能，因此 MCAS 必须作为独立产品或作为下面列出的各种许可证包的一部分存在于帐户中。
1. 你必须具有下面列出的管理员角色之一才能访问门户中的应用治理页面。
1. 组织的租户注册必须位于 [受支持的北美、欧洲或非洲区域](app-governance-countries.md) 之一。

## <a name="licensing-for-app-governance"></a>应用治理许可

在开始使用应用治理之前，应该先确认 [Microsoft 365 管理中心 - 订阅](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/subscriptions) 和任何加载项。 若要访问和使用应用治理，你的组织必须拥有以下订阅或加载项之一：

- Microsoft Cloud App Security
- Microsoft 365 E5
- Microsoft 365 E5 合规
- Microsoft 365 E5 开发者（不包括 Windows 和音频会议）
- Microsoft 365 E5 信息保护和治理
- Microsoft 365 E5 安全性
- Microsoft 365 E5（含呼叫分钟数）
- 不含音频会议的 Microsoft 365 E5
- Microsoft 365 A5 合规中心教职员工版
- Microsoft 365 A5 合规中心学生版
- Microsoft 365 A5 教职员工版
- Microsoft 365 A5 学生版
- Microsoft 365 A5 信息保护和治理教职员工版
- Microsoft 365 A5 信息保护和治理学生版
- Microsoft 365 A5 安全中心教职员工版
- Microsoft 365 A5 安全中心学生版
- Microsoft 365 A5 学生版使用权益
- Microsoft 365 A5（含呼叫分钟数）教职员工版
- Microsoft 365 A5（含呼叫分钟数）学生版
- Microsoft 365 A5（不包括音频会议）教职员工版
- Microsoft 365 A5（包括音频会议）学生版
- Microsoft 365 A5（不包括音频会议）学生版使用权益

## <a name="administrator-roles"></a>管理员角色

要查看应用治理页面或管理策略和设置，需要以下管理员角色之一：

-  应用程序管理员
- 云 应用程序管理员
- 公司管理员
- 合规管理员
- 合规数据管理员
- 合规信息读取者（只读）
- 全局读取者
- 安全管理员
- 安全操作员
- 安全信息读取者（只读）

> [!NOTE]
> 只有全局管理员可以激活应用治理免费试用版。

以下是每个角色的能力。

| 角色 | 阅读仪表板 | 读取所有应用 |读取策略 | 创建、更新或删除策略 | 读取警报 | 更新警报 | 读取设置 | 更新设置 | 读取修正 | 更新修正 |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| 应用程序管理员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| 云应用程序管理员 | ![复选标记](..\media\checkmark.png) | | | | | | | | | |
| 公司管理员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| 合规管理员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | |
| 合规数据管理员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | |
| 合规信息读取者 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | | |
| 全局读取者  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | | |
| 安全管理员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | |
| 安全操作员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | |
| 安全信息读取者  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) | |
|||||||||| | |

有关每个角色的其他信息，请参阅[管理员角色权限](/azure/active-directory/roles/permissions-reference)。

## <a name="add-app-governance-to-your-microsoft-365-account"></a>将应用治理添加到你的 Microsoft 365 帐户

对于现有的 Microsoft 365 客户：

1. 在你的“[Microsoft 365 管理中心](https://admin.microsoft.com)”，导航到 **“计费”-“购买服务”**，然后单击“**加载项**”。
1. 在应用治理卡片中，单击“**详细信息**”。
1. 单击“**开始免费试用**”。
1. 填写请求的信息，以将应用治理添加到所选租户。 如果你是新客户，必须先提供信息来建立帐户并创建针对你的试用期的租户。 完成此操作后，即可将应用治理添加到试用版。

对于新的 Microsoft 365 客户：

1. 在此页面顶部，单击“**免费帐户**”按钮。
1. 在“**试用 Microsoft 365 商业版**”下，单击“**免费试用 1 个月**”。

对于新客户和现有客户：

1. 在注册门户中，提供用于试用的电子邮件地址。 如果你是现有客户，请使用与你的帐户关联的电子邮件。 单击“**下一步**”。
1. 登录后，单击“**立即试用**”以获取免费试用版。
1. 单击“**继续**”关闭页面并开始设置试用版。 对于应用治理的新客户，应用治理实例最多需要两个小时才可用。 对于现有客户，现有服务不会中断。

  > [!NOTE]
  如果你还没有帐户，系统会提示你先设置一个新帐户，然后才能继续试用。

1. 为你的 AAD 租户输入一个可用的域名，然后单击“**检查可用性**”。 系统会自动为你分配一个管理员角色（如果你没有用于应用治理的现有角色），并且可以随时更改域名和/或稍后通过 Microsoft 365 管理中心购买更多租户。
1. 输入要用于登录帐户的用户名和密码。 单击“**注册**”。
1. 单击“**开始使用**”转至应用治理门户，或者单击“**管理订阅**”转至 Microsoft 365 管理中心。

## <a name="add-integration-with-mcas"></a>添加与 MCAS 的集成 

先决条件：

- Office 365 已在云应用安全中连接
- Office 365 Azure AD 应用已启用

要启用与云应用安全的应用治理同步，请执行以下步骤：

1. 转到 Microsoft Cloud App Security 门户 - [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)
1. 单击齿轮图标（右上角），然后选择“**设置**”。
1. 在 **威胁防护** 下，选择“**应用治理**”。
1. 单击“**启用应用治理集成**”，然后选择“**保存**”。

接下来，查看 MCAS 中新启用的策略。 启用集成后，新策略可能需要几分钟才能显示。

- Microsoft 365 OAuth 应用信誉
- Microsoft 365 OAuth 网络钓鱼检测
- Microsoft 365 OAuth 应用治理
- 在 MCAS 仪表板中查看应用治理小组件
- 查看 MCAS 警报中新生成的应用治理警报
- 查看应用治理策略列表中的 MCAS M365 OAuth 策略
- 在应用治理警报中查看新生成的 MCAS M365 OAuth 警报

## <a name="canceling-your-trial"></a>正在取消试用版

如果未参与个人预览，并且希望取消应用治理试用版，则可以与 CXE 联系人通信，或使用以下步骤：

1. 在 Microsoft 365 管理中心中，转到“**账单**” > “**你的产品**”。
1. 导航到应用治理试用版，单击三个点，然后选择“**取消订阅**”。
1. 在生成的浮出窗格中，提供取消原因、任何其他反馈，然后选择“**取消订阅**”。
1. 在生成的弹出屏幕中选择“**取消订阅**”。 你的试用版已取消，你将失去对应用治理的访问权限，并将删除你的应用治理数据（用于创建应用治理见解和检测的日志数据 - 不会影响电子邮件或其他文件）。

## <a name="known-issues-for-the-public-preview"></a>公共预览版的已知问题

应用治理团队已确定预览版的以下已知问题： 

- Microsoft Defender 和应用治理警报之间的双向同步 - 目前，在 Defender 中已解决的警报也必须在应用治理中手动解决。
- 对于某些用户，应用用户和使用情况选项卡中的优先级帐户见解将无法按预期工作。
