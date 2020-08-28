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
ms.openlocfilehash: 85448507835b6310ca4136849be6a40caf6bb919
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289069"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="85003-103">保护 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="85003-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="85003-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="85003-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="85003-105">在此处配置的设置属于 Windows 10 的默认设备策略。</span><span class="sxs-lookup"><span data-stu-id="85003-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="85003-106">通过使用工作帐户登录来连接 Windows 10 设备（包括移动设备和电脑）的所有用户将自动接收这些设置。</span><span class="sxs-lookup"><span data-stu-id="85003-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="85003-107">建议在设置过程中接受默认策略，稍后添加面向特定用户组的策略。</span><span class="sxs-lookup"><span data-stu-id="85003-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="85003-108">保护 Windows 10 设备的设置</span><span class="sxs-lookup"><span data-stu-id="85003-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="85003-p102">默认情况下，所有设置为" **打开**"。可使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="85003-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="85003-111">Setting</span><span class="sxs-lookup"><span data-stu-id="85003-111">Setting</span></span>  <br/> |<span data-ttu-id="85003-112">说明</span><span class="sxs-lookup"><span data-stu-id="85003-112">Description</span></span>  <br/> |
|<span data-ttu-id="85003-113">使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁</span><span class="sxs-lookup"><span data-stu-id="85003-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="85003-114">需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。</span><span class="sxs-lookup"><span data-stu-id="85003-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="85003-115">帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁</span><span class="sxs-lookup"><span data-stu-id="85003-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="85003-116">在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。</span><span class="sxs-lookup"><span data-stu-id="85003-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="85003-117">使用 BitLocker 帮助保护 PC 上的文件和文件夹免遭未经授权的访问</span><span class="sxs-lookup"><span data-stu-id="85003-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="85003-118">Bitlocker 通过加密计算机硬盘来保护数据，在计算机丢失或被盗时防止数据泄露。</span><span class="sxs-lookup"><span data-stu-id="85003-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="85003-119">有关详细信息，请参阅 [BITLOCKER FAQ](https://go.microsoft.com/fwlink/?linkid=871000)。</span><span class="sxs-lookup"><span data-stu-id="85003-119">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="85003-120">在空闲此时长后关闭设备屏幕</span><span class="sxs-lookup"><span data-stu-id="85003-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="85003-p104">确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。</span><span class="sxs-lookup"><span data-stu-id="85003-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|