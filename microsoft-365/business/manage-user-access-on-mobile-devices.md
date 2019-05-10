---
title: 管理用户访问移动设备上的 Office 文档的方式
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: 了解可帮助安全访问移动设备上的 Office 应用的保护策略。
ms.openlocfilehash: b49ec33f4899a25f92ffd9d7a25d3e435016749e
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660315"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="7af65-103">管理用户访问移动设备上的 Office 文档的方式</span><span class="sxs-lookup"><span data-stu-id="7af65-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="7af65-p101">用于控制用户如何在移动设备上访问 Office 文件的策略默认设置为" **关闭**"。建议在设置过程中接受默认值，创建适用于所有用户的 Android、iOS 和 Windows 10 应用程序策略。在设置完成后，可以创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="7af65-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="7af65-107">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="7af65-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="7af65-108">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="7af65-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7af65-109">设置</span><span class="sxs-lookup"><span data-stu-id="7af65-109">Setting</span></span>  <br/> |<span data-ttu-id="7af65-110">说明</span><span class="sxs-lookup"><span data-stu-id="7af65-110">Description</span></span>  <br/> |
|<span data-ttu-id="7af65-111">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="7af65-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="7af65-112">如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="7af65-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="7af65-113">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="7af65-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="7af65-114">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="7af65-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="7af65-115">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="7af65-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="7af65-116">此设置确定用户保持空闲状态多久后系统会提示再次登录。</span><span class="sxs-lookup"><span data-stu-id="7af65-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="7af65-117">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="7af65-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="7af65-p102">一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **打开**"，会阻止这些设备。  </span><span class="sxs-lookup"><span data-stu-id="7af65-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="7af65-121">不允许用户将 Office 应用程序中的内容复制到个人应用</span><span class="sxs-lookup"><span data-stu-id="7af65-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="7af65-122">设置为**打开**时, 用户不能将工作文件中的信息复制到个人文件。</span><span class="sxs-lookup"><span data-stu-id="7af65-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="7af65-123">如果设置为 "**关闭**", 则用户可以将信息从工作文件复制到个人应用或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="7af65-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

