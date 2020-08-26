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
ms.openlocfilehash: b586e687d6b61873b77fac8586396ab51fd90b9b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898060"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="e254a-103">保护 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="e254a-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="e254a-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="e254a-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="e254a-105">在此处配置的设置属于 Windows 10 的默认设备策略。</span><span class="sxs-lookup"><span data-stu-id="e254a-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="e254a-106">通过使用工作帐户登录来连接 Windows 10 设备（包括移动设备和电脑）的所有用户将自动接收这些设置。</span><span class="sxs-lookup"><span data-stu-id="e254a-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="e254a-107">建议在设置过程中接受默认策略，稍后添加面向特定用户组的策略。</span><span class="sxs-lookup"><span data-stu-id="e254a-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="e254a-108">保护 Windows 10 设备的设置</span><span class="sxs-lookup"><span data-stu-id="e254a-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="e254a-p102">默认情况下，所有设置为" **打开**"。可使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="e254a-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e254a-111">Setting</span><span class="sxs-lookup"><span data-stu-id="e254a-111">Setting</span></span>  <br/> |<span data-ttu-id="e254a-112">说明</span><span class="sxs-lookup"><span data-stu-id="e254a-112">Description</span></span>  <br/> |
|<span data-ttu-id="e254a-113">使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁</span><span class="sxs-lookup"><span data-stu-id="e254a-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="e254a-114">需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。</span><span class="sxs-lookup"><span data-stu-id="e254a-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="e254a-115">帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁</span><span class="sxs-lookup"><span data-stu-id="e254a-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="e254a-116">在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。</span><span class="sxs-lookup"><span data-stu-id="e254a-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="e254a-117">在空闲此时长后关闭设备屏幕</span><span class="sxs-lookup"><span data-stu-id="e254a-117">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="e254a-p103">确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。</span><span class="sxs-lookup"><span data-stu-id="e254a-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="e254a-121">允许用户从 Microsoft Store 下载应用</span><span class="sxs-lookup"><span data-stu-id="e254a-121">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="e254a-p104">允许用户从 Microsoft Store 下载和安装应用。应用种类繁多，囊括了游戏和生产力工具，因此将此设置保留为" **开**"，但可将其关闭以增强安全性。  </span><span class="sxs-lookup"><span data-stu-id="e254a-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|