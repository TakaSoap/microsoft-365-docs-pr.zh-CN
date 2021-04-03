---
title: 管理用户访问移动设备上的 Office 文档的方式
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 了解允许你管理用户如何从移动设备访问 Office 应用和工作文件的保护策略。
ms.openlocfilehash: a48aa241c9e70cf087da3f1701e859dae7238024
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578379"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="99bd6-103">管理用户访问移动设备上的 Office 文档的方式</span><span class="sxs-lookup"><span data-stu-id="99bd6-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="99bd6-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="99bd6-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="99bd6-105">用于控制用户如何在移动设备上访问 Office 文件的策略默认设置为" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="99bd6-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="99bd6-106">我们建议你在设置期间接受默认值，为适用于所有用户的 Android、iOS 和 Windows 10 创建应用程序策略。</span><span class="sxs-lookup"><span data-stu-id="99bd6-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="99bd6-107">在设置完成后，可以创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="99bd6-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="99bd6-108">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="99bd6-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="99bd6-109">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="99bd6-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="99bd6-110">设置</span><span class="sxs-lookup"><span data-stu-id="99bd6-110">Setting</span></span>  <br/> |<span data-ttu-id="99bd6-111">说明</span><span class="sxs-lookup"><span data-stu-id="99bd6-111">Description</span></span>  <br/> |
|<span data-ttu-id="99bd6-112">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="99bd6-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="99bd6-113">如果此设置为 **"打开**"，则除了用户名和密码之外，用户还必须提供另一种形式的身份验证，然后才能在移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="99bd6-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="99bd6-114">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="99bd6-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="99bd6-115">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="99bd6-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="99bd6-116">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="99bd6-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="99bd6-117">此设置确定用户在系统提示重新登录之前可以处于空闲状态的时间。</span><span class="sxs-lookup"><span data-stu-id="99bd6-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="99bd6-118">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="99bd6-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="99bd6-119">一些聪明的用户的设备可能已越狱或取得 root 权限。</span><span class="sxs-lookup"><span data-stu-id="99bd6-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="99bd6-120">这意味着用户可以修改操作系统，这会使设备更容易受到恶意软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="99bd6-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="99bd6-121">如果此设置为" **打开**"，会阻止这些设备。</span><span class="sxs-lookup"><span data-stu-id="99bd6-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="99bd6-122">不允许用户将内容从 Office 应用复制到个人应用</span><span class="sxs-lookup"><span data-stu-id="99bd6-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="99bd6-123">当设置为 **"打开"** 时，用户不能将工作文件中的信息复制到个人文件中。</span><span class="sxs-lookup"><span data-stu-id="99bd6-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="99bd6-124">如果设置为" **关闭"，** 用户可以将工作文件中的信息复制到个人应用或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="99bd6-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

