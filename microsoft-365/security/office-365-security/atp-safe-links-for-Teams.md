---
title: Office 365 ATP 安全链接，适用于团队、safelinks、安全链接、阻止恶意链接、office 365 ATP、团队安全链接、阻止用户单击 "不良链接"、"恶意链接"
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 团队现在可以在你单击时访问安全链接。 无论您是否在使用聊天1开/1 聊天、组之间或频道以及选项卡，如果您有 Office 365 ATP 的订阅，您都可以启用和使用此安全功能。
ms.openlocfilehash: 49a49bd41e71daf0afc9e7a24e79898ff98ad798
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212541"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a>团队中的 Office 365 安全链接

> [!IMPORTANT]
> 此功能适用于 Microsoft 团队技术采用计划（点击）中的客户在2020年2月28日之前的**公共预览版**。 当团队的安全链接更广泛可用时，将从文章中删除此注释。

Microsoft 团队（用于管理工作的 Office 365 基于云的应用程序）已经使用安全附件（针对 Office 365），但在您单击时，它现在可以访问安全链接。 无论您是否在使用聊天1开/1 聊天、在组之间或在频道中以及在选项卡上，如果您有 Office 365 ATP 的订阅，您将能够启用和使用此安全措施。

以下是相应的工作方式： 

1. 当您启动团队应用程序时，Office 365 将进行检查以确保用户属于具有 Office 365 ATP 的组织，并且该用户是已为 Microsoft 团队启用了保护的活动安全链接策略的一部分。

2. 如果上述值为 true，则在聊天、组聊天、频道和该用户的选项卡中单击时，将对 Url 进行验证。

> [!NOTE]
> 安全链接通过来宾用户、联合用户、租户用户发送的链接来保护用户。 如果登录的用户具有启用了团队的安全链接，则将应用安全链接保护。
 
## <a name="what-will-users-experience"></a>用户会遇到什么情况？ 

所有受保护的用户都将获得以下危险 Url 体验： 

- 如果从团队对话、分组聊天或频道中单击了该链接，则页面将在默认浏览器中呈现。 如果从固定的选项卡上单击了该链接，该页面将显示在该选项卡中的团队 GUI 中，并且出于安全考虑，将禁用在浏览器中打开的选项。

- 将阻止此用户继续转到 URL 的网站。

如果发送链接的用户未受到 Office 365 ATP 的保护，他/她可以随意单击其计算机上的 URL 并解决问题网站。 这样一来，Office 365 管理员就可以知道其受保护的用户是谁，这一点非常重要。

![工作组的安全链接页面报告恶意链接并阻止向页面传输。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

在团队中单击此页*上的 "返回"* 按钮将关闭它（也可能导致空白页用户可以关闭）。 但是，再次单击链接将导致 reassessment 网站的声誉，从而再次出现此页面。

> [!NOTE]
>某些 Office 365 管理员将启用阻止页面上的 "**继续下去**" 消息。 但是，如果安全链接测量网站的声誉并发现缺少它，则不应进一步单击。 不建议用户绕过安全措施。 请将其与你的注意事项进行权衡，然后再启用 "继续"。 

