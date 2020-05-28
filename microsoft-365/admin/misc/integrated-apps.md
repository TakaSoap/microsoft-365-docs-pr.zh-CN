---
title: 打开或关闭集成应用
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 了解集成的应用程序，以及如何将其打开以允许第三方应用访问用户的 Microsoft 365 信息。
ms.openlocfilehash: 070150662daeefb2a4d02c7e0940dfd242bd4b5f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399334"
---
# <a name="turning-integrated-apps-on-or-off"></a>打开或关闭集成应用

启用集成应用程序后，你的组织中的用户可以允许第三方应用访问其 Microsoft 365 信息。 例如，当某用户使用第三方应用时，该应用可能会请求权限来访问其日历和编辑 OneDrive 文件夹中的文件。

## <a name="turning-integrated-apps-on-or-off"></a>打开或关闭集成应用
<a name="__toc379982114"> </a>

下面介绍了如何打开或关闭集成应用。

1. 在 Microsoft 365 管理中心，转到 "**设置** \> **设置**" 页 " \> **服务**" 选项卡，然后选择 "**集成应用**"。

2. 在 "**集成应用**" 页面上，选择要启用或禁用集成应用的选项。

## <a name="more-info-on-integrated-apps"></a>有关集成应用的更多信息
<a name="__toc379982114"> </a>

集成的应用程序可以从您自己的组织中创建，也可以来自其他组织或第三方。

如果集成应用处于打开状态并且已在使用某个应用，则该应用会请求权限来设置在访问用户的信息时所需的访问权限级别。 用户可以仅向他们拥有的可访问其 Microsoft 365 信息的应用授予访问权限。 他们无法向应用授予对任何其他用户的信息的访问权限。

在 Microsoft 365 中使用集成应用程序时，有两种权限可供使用：用户权限和管理员权限。 例如，当您的组织已启用集成应用并且某个用户使用第三方应用时，该应用可能会请求用户的权限来读取其用户配置文件详细信息、编辑或删除其文件、读取网站集中包含的项目以及以该用户身份发送电子邮件。

![集成应用用户权限](../../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)

如果管理员为组织中的所有用户注册应用程序，他/她将被要求有权让该应用访问组织中的信息和资源。 之后，当组织中的其他用户使用该应用时，则不会要求他们具有权限。 当管理员注册某个应用时，该管理员必须确保他们信任该应用的发布者。 有关注册应用的详细信息，请参阅[添加、更新和删除应用程序](https://go.microsoft.com/fwlink/p/?LinkID=518600)。

![集成应用管理员权限](../../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)

如果集成应用已关闭，则已安装并有权访问信息的应用不会卸载，权限也不会被删除。 即使集成应用处于关闭状态，管理员仍然可以注册应用来使其对用户可用，并允许这些应用访问用户的信息。 有关删除已注册的应用程序及其权限的详细信息，请参阅[添加、更新和删除应用程序](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409)。


