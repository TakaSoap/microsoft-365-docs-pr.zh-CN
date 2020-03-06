---
title: 管理用户访问移动设备上的 Office 文档的方式
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 了解允许您管理用户如何从移动设备访问 Office 应用程序和工作文件的保护策略。
ms.openlocfilehash: 21e83114664d06aaeb27b08d9f4e2153eea02030
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550309"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="4ee23-103">管理用户访问移动设备上的 Office 文档的方式</span><span class="sxs-lookup"><span data-stu-id="4ee23-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="4ee23-104">用于控制用户如何在移动设备上访问 Office 文件的策略默认设置为" **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="4ee23-104">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="4ee23-105">建议您在安装过程中接受默认值，以创建适用于所有用户的 Android、iOS 和 Windows 10 应用程序策略。</span><span class="sxs-lookup"><span data-stu-id="4ee23-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="4ee23-106">在设置完成后，可以创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="4ee23-106">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="4ee23-107">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="4ee23-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="4ee23-108">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="4ee23-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4ee23-109">设置</span><span class="sxs-lookup"><span data-stu-id="4ee23-109">Setting</span></span>  <br/> |<span data-ttu-id="4ee23-110">说明</span><span class="sxs-lookup"><span data-stu-id="4ee23-110">Description</span></span>  <br/> |
|<span data-ttu-id="4ee23-111">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="4ee23-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="4ee23-112">如果**启用**此设置，用户必须提供另一种形式的身份验证，以及其用户名和密码，然后才能在其移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="4ee23-112">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="4ee23-113">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="4ee23-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="4ee23-114">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="4ee23-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="4ee23-115">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="4ee23-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="4ee23-116">此设置确定用户在提示用户重新登录之前可以处于空闲状态的时间。</span><span class="sxs-lookup"><span data-stu-id="4ee23-116">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="4ee23-117">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="4ee23-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="4ee23-118">一些聪明的用户的设备可能已越狱或取得 root 权限。</span><span class="sxs-lookup"><span data-stu-id="4ee23-118">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="4ee23-119">这意味着用户可以修改操作系统，这会使设备更容易受到恶意软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="4ee23-119">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="4ee23-120">如果此设置为" **打开**"，会阻止这些设备。</span><span class="sxs-lookup"><span data-stu-id="4ee23-120">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="4ee23-121">不允许用户将 Office 应用程序中的内容复制到个人应用</span><span class="sxs-lookup"><span data-stu-id="4ee23-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="4ee23-122">设置为**打开**时，用户不能将工作文件中的信息复制到个人文件。</span><span class="sxs-lookup"><span data-stu-id="4ee23-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="4ee23-123">如果设置为 "**关闭**"，则用户可以将信息从工作文件复制到个人应用或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="4ee23-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

