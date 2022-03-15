---
title: 空闲会话超时Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Adm_TOC
description: 设置用户会话在用户Microsoft 365之前持续的时间。
ms.openlocfilehash: 215b900315b2d98b01a8cf87b14a6fa65289e121
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504870"
---
# <a name="idle-session-timeout-for-microsoft-365-public-preview"></a>公共预览Microsoft 365 (空闲会话) 

<!-- Add metadata: localization, AdminSurgePortfolio, admindeeplinkMAC. remove robots nofollow -->

使用空闲会话超时配置有关用户在从 Web 应用退出之前在组织中处于非活动Microsoft 365的策略。 这有助于保护敏感的公司数据，为在非公司或共享设备上工作的最终用户添加另一层安全保护。

当用户达到你设置的空闲超时会话时，他们收到一条通知，告知他们即将退出。他们必须选择保持登录，否则将自动从所有 web Microsoft 365登录。

> [!IMPORTANT]
> 空闲会话超时不会影响桌面Microsoft 365移动应用。

## <a name="turn-on-idle-session-timeout"></a>打开空闲会话超时

如果你不是全局管理员Microsoft 365 Office 365，你将看不到"安全&**隐私"** 选项卡。

1. In the Microsoft 365 管理中心， select **Org 设置** **->**[Security & privacy](https://go.microsoft.com/fwlink/p/?linkid=2072756) tab and select **Idle session timeout**.  

2. 在" **空闲会话超时** "上，选择切换以将其打开。 可以选择默认设置或选择自己的自定义时间。 在组织中打开空闲会话之前，需要几分钟时间。

> [!NOTE]
> 如果你为 [Outlook Web](https://support.microsoft.com/topic/description-of-the-activity-based-authentication-timeout-for-owa-in-office-365-0c101e1b-020e-69c1-a0b0-26532d60c0a4) 应用和 [SharePoint Online](/sharepoint/sign-out-inactive-users) 设置了空闲会话超时策略，在 Microsoft 365 管理中心 中打开空闲会话超时将覆盖 Outlook Web 应用和 SharePoint 设置。

空闲会话超时是安全保护中的众多安全措施Microsoft 365。 若要了解 Microsoft 365 中的其他安全任务，请参阅 Microsoft 365 [中的主要安全Microsoft 365](../../security/top-security-tasks-for-remote-work.md)。  

## <a name="what-users-will-see"></a>用户将看到哪些内容

当用户在您选择的时间段内Microsoft 365 Web 应用中处于非活动状态时，他们将看到以下提示。 他们必须选择" **保持登录** "，否则将退出。

:::image type="content" source="../../media/idle-session-timeout.png" alt-text="Screenshot： Prompt that you know that your session is about to expire.选择&quot;继续登录&quot;，这样你才能从 web Microsoft 365登录":::

## <a name="details-about-idle-session-timeout"></a>有关空闲会话超时的详细信息

- 支持Microsoft 365 Web 应用。 即将添加更多 Web 应用。

    - Outlook Web App

    - OneDrive for Business

    - SharePoint Online (SPO) 

    - Office.com 和其他起始页

    - Office (Word、Excel、PowerPoint) 网页发布

    - Microsoft 365 管理中心

- 活动是指 Web 应用上下文中发生的任何客户端用户交互。 例如，鼠标单击和键盘按下。  

- 空闲会话超时基于每个浏览器会话工作。 用户对浏览器Microsoft Edge与其他浏览器（如 Google Chrome）中的活动处理方式不同。 用户将从与浏览器会话中的帐户对应的所有选项卡中退出。

- 打开空闲会话超时后，它适用于整个组织，并且不能作用域为特定用户、组织单位或组。 对[Azure AD](/azure/active-directory/conditional-access/)组的策略使用条件访问。

- 在配置持续时间内，用户Microsoft 365 Web 应用选项卡上必须处于非活动状态。 如果用户在一个选项卡上处于活动状态， (说 OWA) 在另一个选项卡上处于非活动状态 (例如 SPO) ，他们将被视为活动状态，不会退出。  

- 在这些情况下，用户不会登录。
    - 如果他们从设备加入帐户 (SSO) 单一登录，或者选择"在登录时保持登录"。 有关为组织隐藏此选项的信息，请参阅将品牌添加到 [组织的登录页面](/azure/active-directory/fundamentals/customize-branding)。
    - 如果用户在托管设备上 (符合要求或已加入域) ，并且使用受支持的浏览器（如 Microsoft Edge 或 Google Chrome (和 [Windows 帐户](https://chrome.google.com/webstore/detail/windows-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji)扩展) ）。 若要在托管设备上不触发此功能，需要符合条件的 Azure AD Premium P1 P2 订阅和特定条件访问策略。 有关详细信息，请参阅下文。

> [!IMPORTANT]
> 在德国或德国，空闲由世纪互联运营的 Microsoft 365超时Microsoft 365可用。

## <a name="idle-session-timeout-on-unmanaged-devices"></a>非托管设备的空闲会话超时  

若要在非托管设备上触发空闲会话超时，你需要在管理中心中添加Azure AD访问策略。

1. 在条件 **访问|管理** 中心的"策略Azure AD，选择"**新建** 策略"，然后输入策略的名称。

2. 选择 **"用户或工作负荷标识"**，然后选择" **所有用户"**。

3. 选择 **"云应用或操作****"，选择应用****，然后搜索** Office 365。 选择 **Office 365**"，然后选择"**选择"**。  

4. 选择 **条件**、**客户端应用****、配置为是****、浏览器**，**然后选择完成。**

5. 选择 **"会话****"，"使用应用强制的限制"**，然后选择"**选择"**。

6. 打开该策略，**然后选择创建。**

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="are-there-any-browsers-or-browser-scenarios-in-which-idle-session-timeout-feature-doesnt-work"></a>是否有空闲会话超时功能不起作用的任何浏览器或浏览器方案？  

在浏览器中禁用第三方 Cookie 时，不支持空闲会话超时。 用户不会看到任何注销提示。 我们建议将跟踪防护设置保持为"平衡 ([默认](/microsoft-edge/web-platform/tracking-prevention)) ，Microsoft Edge浏览器中启用的第三方 Cookie。 Microsoft 365 2021 年 8 月 17 Internet Explorer停止支持 11。

### <a name="how-should-i-prepare-if-my-organization-is-already-using-existing-outlook-web-app-and-sharepoint-online-idle-timeout-policies"></a>如果组织已在使用现有 Web 应用和联机空闲超时Outlook，我SharePoint准备？  

如果你已在使用现有 Outlook Web 应用SharePoint联机空闲超时策略，你仍然可以打开空闲会话超时功能。 当你打开空闲超时策略时，它将优先于现有 Outlook Web 应用和 SharePoint Online 策略。 我们计划即将弃用现有 Outlook Web 应用SharePoint Online 策略。 为了更好地准备组织，我们建议你打开空闲会话超时。

### <a name="what-happens-if-i-am-inactive-on-an-included-microsoft-365-web-app-but-active-on-a-microsoft-web-app-or-saas-web-app-that-doesnt-have-idle-session-timeout-turned-on"></a>如果我在包含的 web Microsoft 365上处于非活动状态，但在未打开空闲会话超时的 Microsoft Web 应用或 SaaS Web 应用上处于活动状态，会发生什么情况？  

支持Microsoft 365 Web 应用。

- Outlook Web App

- OneDrive for Business

- SharePoint Online (SPO) 

- Office.com 和其他起始页

- Office (Word、Excel、PowerPoint) 网页发布

- Microsoft 365 管理中心

如果你使用同一帐户在不同的 Web 应用上工作，该 Web 应用中的活动不会应用于空闲会话超时。

### <a name="i-want-to-make-changes-to-the-idle-session-timeout-policy-or-delete-it-how-can-i-do-that"></a>我希望对空闲会话超时策略进行更改或删除它。 如何执行？

更新策略：

1. In the Microsoft 365 管理中心， select **Org settings**， go to the **Security & Privacy** tab and select **Idle session timeout**.

2. 在下拉菜单中，选择不同的超时值，然后选择"保存 **"**。  

删除策略：

1. In the Microsoft 365 管理中心， select **Org settings**， go to the **Security & Privacy** tab and select **Idle session timeout**.

2. 取消 **选中"打开"以设置** 用户从 Web 应用中注销的不Office，然后选择"保存 **"**。
