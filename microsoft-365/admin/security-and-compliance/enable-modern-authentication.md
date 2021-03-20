---
title: 在 Windows 设备上启用适用于 Office 2013 的新式验证
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 了解如何设置注册表项，为已安装 2013 Microsoft Office新式验证。
ms.openlocfilehash: f12511ad6d685647b3b38fd424f1d4611a3119b4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914530"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="c3b4c-103">在 Windows 设备上启用适用于 Office 2013 的新式验证</span><span class="sxs-lookup"><span data-stu-id="c3b4c-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="c3b4c-104">若要为安装了 Office 2013 的任何 Windows 设备启用新式验证，需设置特定的注册表项。</span><span class="sxs-lookup"><span data-stu-id="c3b4c-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="c3b4c-105">为 Office 2013 客户端启用新式验证</span><span class="sxs-lookup"><span data-stu-id="c3b4c-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="c3b4c-106">已为 Office 2016 客户端启用新式验证，无需设置 Office 2016 的注册表项。</span><span class="sxs-lookup"><span data-stu-id="c3b4c-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="c3b4c-p101">若要为运行 Windows 且安装了 Microsoft Office 2013 的任何设备（例如笔记本电脑和平板电脑）启用新式验证，需设置以下注册表项。必须在每台要启用新式验证的设备上设置注册表项：</span><span class="sxs-lookup"><span data-stu-id="c3b4c-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="c3b4c-109">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="c3b4c-109">**Registry key**</span></span>|<span data-ttu-id="c3b4c-110">**类型**</span><span class="sxs-lookup"><span data-stu-id="c3b4c-110">**Type**</span></span>|<span data-ttu-id="c3b4c-111">**值**</span><span class="sxs-lookup"><span data-stu-id="c3b4c-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="c3b4c-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="c3b4c-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="c3b4c-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c3b4c-113">REG_DWORD</span></span>  |<span data-ttu-id="c3b4c-114">1</span><span class="sxs-lookup"><span data-stu-id="c3b4c-114">1</span></span>  |
|<span data-ttu-id="c3b4c-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="c3b4c-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="c3b4c-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c3b4c-116">REG_DWORD</span></span> |<span data-ttu-id="c3b4c-117">1</span><span class="sxs-lookup"><span data-stu-id="c3b4c-117">1</span></span> |
   
<span data-ttu-id="c3b4c-118">设置注册表项后，可以将 Office 2013 设备应用设置为使用 Microsoft 365 的 [MFA ](set-up-multi-factor-authentication.md) (多重) 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c3b4c-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="c3b4c-p102">如果当前登录了任何客户端应用，需注销并重新登录以使更改生效。否则，在建立 ADAL 标识之前，MRU 和漫游设置将不可用。</span><span class="sxs-lookup"><span data-stu-id="c3b4c-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="c3b4c-121">在设备上禁用新式验证</span><span class="sxs-lookup"><span data-stu-id="c3b4c-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="c3b4c-122">若要在设备上禁用新式验证，请在设备上设置以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="c3b4c-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="c3b4c-123">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="c3b4c-123">**Registry key**</span></span>|<span data-ttu-id="c3b4c-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="c3b4c-124">**Type**</span></span>|<span data-ttu-id="c3b4c-125">**值**</span><span class="sxs-lookup"><span data-stu-id="c3b4c-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="c3b4c-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="c3b4c-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="c3b4c-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c3b4c-127">REG_DWORD</span></span>|<span data-ttu-id="c3b4c-128">0</span><span class="sxs-lookup"><span data-stu-id="c3b4c-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="c3b4c-129">相关文章</span><span class="sxs-lookup"><span data-stu-id="c3b4c-129">Related articles</span></span>
[<span data-ttu-id="c3b4c-130">使用第二种验证方法登录 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c3b4c-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[<span data-ttu-id="c3b4c-131">Outlook 提示输入密码，并且不使用新式验证连接到 Office 365</span><span class="sxs-lookup"><span data-stu-id="c3b4c-131">Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365</span></span>](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)

