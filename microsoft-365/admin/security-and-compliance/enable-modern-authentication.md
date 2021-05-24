---
title: 在 Windows 设备上启用适用于 Office 2013 的新式验证
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 了解如何设置注册表项，以对已安装 2013 Microsoft Office新式验证。
ms.openlocfilehash: 917ecd5c668ea43b0627ba2361f951ebc5e19725
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635686"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="42f9a-103">在 Windows 设备上启用适用于 Office 2013 的新式验证</span><span class="sxs-lookup"><span data-stu-id="42f9a-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="42f9a-104">若要为安装了 Office 2013 的任何 Windows 设备启用新式验证，需设置特定的注册表项。</span><span class="sxs-lookup"><span data-stu-id="42f9a-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="42f9a-105">为 Office 2013 客户端启用新式验证</span><span class="sxs-lookup"><span data-stu-id="42f9a-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="42f9a-106">已为 Office 2016 客户端启用新式验证，无需设置 Office 2016 的注册表项。</span><span class="sxs-lookup"><span data-stu-id="42f9a-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="42f9a-p101">若要为运行 Windows 且安装了 Microsoft Office 2013 的任何设备（例如笔记本电脑和平板电脑）启用新式验证，需设置以下注册表项。必须在每台要启用新式验证的设备上设置注册表项：</span><span class="sxs-lookup"><span data-stu-id="42f9a-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="42f9a-109">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="42f9a-109">**Registry key**</span></span>|<span data-ttu-id="42f9a-110">**类型**</span><span class="sxs-lookup"><span data-stu-id="42f9a-110">**Type**</span></span>|<span data-ttu-id="42f9a-111">**值**</span><span class="sxs-lookup"><span data-stu-id="42f9a-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="42f9a-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="42f9a-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="42f9a-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="42f9a-113">REG_DWORD</span></span>  |<span data-ttu-id="42f9a-114">1</span><span class="sxs-lookup"><span data-stu-id="42f9a-114">1</span></span>  |
|<span data-ttu-id="42f9a-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="42f9a-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="42f9a-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="42f9a-116">REG_DWORD</span></span> |<span data-ttu-id="42f9a-117">1</span><span class="sxs-lookup"><span data-stu-id="42f9a-117">1</span></span> |
   
<span data-ttu-id="42f9a-118">设置注册表项后，可以将 Office 2013 设备应用设置为将多重身份验证 (MFA) [MFA](set-up-multi-factor-authentication.md) Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="42f9a-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="42f9a-p102">如果当前登录了任何客户端应用，需注销并重新登录以使更改生效。否则，在建立 ADAL 标识之前，MRU 和漫游设置将不可用。</span><span class="sxs-lookup"><span data-stu-id="42f9a-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="42f9a-121">在设备上禁用新式验证</span><span class="sxs-lookup"><span data-stu-id="42f9a-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="42f9a-122">若要在设备上禁用新式验证，请在设备上设置以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="42f9a-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="42f9a-123">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="42f9a-123">**Registry key**</span></span>|<span data-ttu-id="42f9a-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="42f9a-124">**Type**</span></span>|<span data-ttu-id="42f9a-125">**值**</span><span class="sxs-lookup"><span data-stu-id="42f9a-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="42f9a-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="42f9a-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="42f9a-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="42f9a-127">REG_DWORD</span></span>|<span data-ttu-id="42f9a-128">0</span><span class="sxs-lookup"><span data-stu-id="42f9a-128">0</span></span>|
   
## <a name="related-content"></a><span data-ttu-id="42f9a-129">相关内容</span><span class="sxs-lookup"><span data-stu-id="42f9a-129">Related content</span></span>

<span data-ttu-id="42f9a-130">使用本文Office验证方法登录到 ([2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)) </span><span class="sxs-lookup"><span data-stu-id="42f9a-130">[Sign in to Office 2013 with a second verification method](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (article)</span></span>\
<span data-ttu-id="42f9a-131">[Outlook提示输入密码](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)，并且不使用新式验证连接到 Office 365 (文章) </span><span class="sxs-lookup"><span data-stu-id="42f9a-131">[Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (article)</span></span>

