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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 了解集成的应用程序，以及如何将其打开以允许第三方应用访问用户的 Office 365 信息。
ms.openlocfilehash: 3c7c92e16b375fc374563e87ea2f6166c7384a29
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361383"
---
# <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="76f21-103">打开或关闭集成应用</span><span class="sxs-lookup"><span data-stu-id="76f21-103">Turning Integrated Apps on or off</span></span>

<span data-ttu-id="76f21-p101">当集成应用处于打开状态时，您的组织中的用户可以允许第三方应用访问其 Office 365 信息。 例如，当某用户使用第三方应用时，该应用可能会请求权限来访问其日历和编辑 OneDrive 文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="76f21-p101">When Integrated Apps is turned on, users in your organization can allow third-party apps to access their Office 365 information. For example, when someone uses a third-party app, that app might ask for permission to access their calendar and to edit files that are in a OneDrive folder.</span></span>

## <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="76f21-106">打开或关闭集成应用</span><span class="sxs-lookup"><span data-stu-id="76f21-106">Turning Integrated Apps on or off</span></span>
<span data-ttu-id="76f21-107"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="76f21-107"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="76f21-108">下面介绍了如何打开或关闭集成应用。</span><span class="sxs-lookup"><span data-stu-id="76f21-108">Here's how to turn Integrated Apps on or off.</span></span>

1. <span data-ttu-id="76f21-109">在管理中心中，转到 "**设置** \> [ &amp;服务外接程序](https://go.microsoft.com/fwlink/p/?linkid=2053743)" 页，然后选择 "**集成应用**"。</span><span class="sxs-lookup"><span data-stu-id="76f21-109">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **Integrated apps**.</span></span>

2. <span data-ttu-id="76f21-110">在 "**集成应用**" 页面上，选择要启用或禁用集成应用的选项。</span><span class="sxs-lookup"><span data-stu-id="76f21-110">On the **Integrated Apps** page, select the option to turn Integrated Apps on or off.</span></span>

## <a name="more-info-on-integrated-apps"></a><span data-ttu-id="76f21-111">有关集成应用的更多信息</span><span class="sxs-lookup"><span data-stu-id="76f21-111">More info on Integrated Apps</span></span>
<span data-ttu-id="76f21-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="76f21-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="76f21-113">集成应用可以从您自己的组织中创建，也可以来自另一个 Office 365 组织或第三方。</span><span class="sxs-lookup"><span data-stu-id="76f21-113">An integrated app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="76f21-p102">如果集成应用处于打开状态并且已在使用某个应用，则该应用会请求权限来设置在访问用户的信息时所需的访问权限级别。 用户可以仅向其拥有的、访问其 Office 365 信息的应用授予访问权限。 他们无法向应用授予对任何其他用户的信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="76f21-p102">When Integrated Apps is turned on and an app is used, the app asks for permission to set the level of access it needs when it accesses the user's information. A user can give access only to apps they own that access their Office 365 information. They can't give an app access to any other user's information.</span></span>

<span data-ttu-id="76f21-p103">在 Office 365 中使用集成应用时有两种类型的权限可以使用：用户权限和管理员权限。 例如，当您的组织已启用集成应用并且某个用户使用第三方应用时，该应用可能会请求用户的权限来读取其用户配置文件详细信息、编辑或删除其文件、读取网站集中包含的项目以及以该用户身份发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="76f21-p103">There are two kinds of permissions that are used when using Integrated Apps in Office 365: user permissions and admin permissions. For example, when your organization is enabled for Integrated Apps and a user uses a third-party app, the app might ask for the user's permission to read their user profile details, edit or delete their files, read items contained in site collections, and send email as that user.</span></span>

![集成应用用户权限](../../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)

<span data-ttu-id="76f21-120">如果管理员为组织中的所有用户注册应用程序，他/她将被要求有权让该应用访问组织中的信息和资源。</span><span class="sxs-lookup"><span data-stu-id="76f21-120">If an admin registers an app for all users in an organization, he or she is asked for permission to let that app access information and resources in the organization.</span></span> <span data-ttu-id="76f21-121">之后，当组织中的其他用户使用该应用时，则不会要求他们具有权限。</span><span class="sxs-lookup"><span data-stu-id="76f21-121">After this, when other users in the organization use that app, they won't be asked for permission.</span></span> <span data-ttu-id="76f21-122">当管理员注册某个应用时，该管理员必须确保他们信任该应用的发布者。</span><span class="sxs-lookup"><span data-stu-id="76f21-122">When an admin registers an app, that admin must make sure that they trust that app's publisher.</span></span> <span data-ttu-id="76f21-123">有关注册应用的详细信息，请参阅[添加、更新和删除应用程序](https://go.microsoft.com/fwlink/p/?LinkID=518600)。</span><span class="sxs-lookup"><span data-stu-id="76f21-123">For details on registering an app, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/p/?LinkID=518600).</span></span>

![集成应用管理员权限](../../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)

<span data-ttu-id="76f21-p105">如果集成应用已关闭，则已安装并有权访问信息的应用不会卸载，权限也不会被删除。 即使集成应用处于关闭状态，管理员仍然可以注册应用来使其对用户可用，并允许这些应用访问用户的信息。 有关删除已注册的应用程序及其权限的详细信息，请参阅[添加、更新和删除应用程序](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="76f21-p105">If Integrated Apps is turned off, apps that have already been installed and have permission to access information won't be uninstalled, and the permissions won't be removed. Even though Integrated Apps is turned off, admins can still register apps to make them available to their users and allow those apps access to the users' information. For details on removing a registered application and it's permissions, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).</span></span>


