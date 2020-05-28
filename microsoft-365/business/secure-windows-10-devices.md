---
title: 保护 Windows 10 设备
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 了解如何配置 Windows 10 设备在登录到其工作或学校帐户时将接收的默认设备策略的设置。
ms.openlocfilehash: 7714a6e47de8a254d836ca2e158b92907b87f8c3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402726"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="fb6b4-103">保护 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="fb6b4-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="fb6b4-104">在此处配置的设置属于 Windows 10 的默认设备策略。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-104">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="fb6b4-105">通过使用工作帐户登录来连接 Windows 10 设备（包括移动设备和电脑）的所有用户将自动接收这些设置。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-105">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="fb6b4-106">建议在设置过程中接受默认策略，稍后添加面向特定用户组的策略。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-106">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="fb6b4-107">保护 Windows 10 设备的设置</span><span class="sxs-lookup"><span data-stu-id="fb6b4-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="fb6b4-p102">默认情况下，所有设置为" **打开**"。可使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="fb6b4-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fb6b4-110">设置</span><span class="sxs-lookup"><span data-stu-id="fb6b4-110">Setting</span></span>  <br/> |<span data-ttu-id="fb6b4-111">说明</span><span class="sxs-lookup"><span data-stu-id="fb6b4-111">Description</span></span>  <br/> |
|<span data-ttu-id="fb6b4-112">使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁</span><span class="sxs-lookup"><span data-stu-id="fb6b4-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="fb6b4-113">需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="fb6b4-114">帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁</span><span class="sxs-lookup"><span data-stu-id="fb6b4-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="fb6b4-115">在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="fb6b4-116">在空闲此时长后关闭设备屏幕</span><span class="sxs-lookup"><span data-stu-id="fb6b4-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="fb6b4-p103">确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="fb6b4-120">允许用户从 Microsoft Store 下载应用</span><span class="sxs-lookup"><span data-stu-id="fb6b4-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="fb6b4-p104">允许用户从 Microsoft Store 下载和安装应用。应用种类繁多，囊括了游戏和生产力工具，因此将此设置保留为" **开**"，但可将其关闭以增强安全性。  </span><span class="sxs-lookup"><span data-stu-id="fb6b4-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="fb6b4-123">允许用户访问 Cortana</span><span class="sxs-lookup"><span data-stu-id="fb6b4-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="fb6b4-124">Cortana 非常有用！</span><span class="sxs-lookup"><span data-stu-id="fb6b4-124">Cortana can be very helpful!</span></span> <span data-ttu-id="fb6b4-125">Cortana 可以为你打开或关闭设置、提供说明，并确保你的约会时间已过，因此，默认情况下将此设置保持为**打开**。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-125">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="fb6b4-126">允许用户接收来自 Microsoft 的 Windows 提示和广告</span><span class="sxs-lookup"><span data-stu-id="fb6b4-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="fb6b4-127">Windows 提示非常方便，可在新功能发布时为用户提供指导。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="fb6b4-128">让 Windows 10 设备自动保持最新状态</span><span class="sxs-lookup"><span data-stu-id="fb6b4-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="fb6b4-129">确保 Windows 10 设备会自动接收最新的更新。</span><span class="sxs-lookup"><span data-stu-id="fb6b4-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

