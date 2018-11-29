---
title: 管理用户访问移动设备上的 Office 文档的方式
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 了解有关保护策略，可从移动设备对 Office 应用程序帮助的安全访问。
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865714"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="e969a-103">管理用户访问移动设备上的 Office 文档的方式</span><span class="sxs-lookup"><span data-stu-id="e969a-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="e969a-p101">用于控制用户如何在移动设备上访问 Office 文件的策略默认设置为" **关闭**"。建议在设置过程中接受默认值，创建适用于所有用户的 Android、iOS 和 Windows 10 应用程序策略。在设置完成后，可以创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="e969a-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="e969a-107">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="e969a-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="e969a-108">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="e969a-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e969a-109">设置</span><span class="sxs-lookup"><span data-stu-id="e969a-109">Setting</span></span>  <br/> |<span data-ttu-id="e969a-110">说明</span><span class="sxs-lookup"><span data-stu-id="e969a-110">Description</span></span>  <br/> |
|<span data-ttu-id="e969a-111">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="e969a-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="e969a-112">如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="e969a-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="e969a-113">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="e969a-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="e969a-114">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="e969a-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="e969a-115">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="e969a-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="e969a-116">此设置确定用户保持空闲状态多久后系统会提示再次登录。</span><span class="sxs-lookup"><span data-stu-id="e969a-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="e969a-117">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="e969a-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="e969a-p102">一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **开** "，会阻止这些设备。  </span><span class="sxs-lookup"><span data-stu-id="e969a-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="e969a-121">允许用户从 Office 应用将内容复制到个人应用</span><span class="sxs-lookup"><span data-stu-id="e969a-121">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="e969a-p103">默认允许此设置，但设置为" **打开**"时，用户可以将工作文件中的信息复制到个人文件。如果设置为" **关闭**"，用户无法将工作文件中的信息复制到个人应用或个人帐户。  </span><span class="sxs-lookup"><span data-stu-id="e969a-p103">We allow this by default, but when the setting is **On**, the user can copy information in a work file to a personal file. If the setting is **Off**, the user can't copy information from a work file to a personal app or personal account.  </span></span><br/> |
   

