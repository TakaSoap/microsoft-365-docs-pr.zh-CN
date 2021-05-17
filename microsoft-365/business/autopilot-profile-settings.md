---
title: 关于"AutoPilot 配置文件"设置
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 配置文件可帮助你控制Windows安装用户设备。 配置文件包含默认和可选设置，如跳过 Cortana 安装。
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578499"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="8538c-104">关于"AutoPilot 配置文件"设置</span><span class="sxs-lookup"><span data-stu-id="8538c-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="8538c-105">AutoPilot 配置文件设置</span><span class="sxs-lookup"><span data-stu-id="8538c-105">AutoPilot profile settings</span></span>

<span data-ttu-id="8538c-106">可以使用 AutoPilot 配置文件来控制用户Windows安装方法。</span><span class="sxs-lookup"><span data-stu-id="8538c-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="8538c-107">配置文件包含以下设置。</span><span class="sxs-lookup"><span data-stu-id="8538c-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="8538c-108">**AutoPilot 默认 (需要) 自动设置的功能：**</span><span class="sxs-lookup"><span data-stu-id="8538c-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="8538c-109">**设置**</span><span class="sxs-lookup"><span data-stu-id="8538c-109">**Setting**</span></span>|<span data-ttu-id="8538c-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="8538c-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8538c-111">跳过 Cortana、OneDrive 和 OEM 注册</span><span class="sxs-lookup"><span data-stu-id="8538c-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="8538c-112">跳过 Cortana 和个人应用等消费者应用的OneDrive。</span><span class="sxs-lookup"><span data-stu-id="8538c-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="8538c-113">只要用户是设备的本地管理员，设备用户就可以稍后安装它们。</span><span class="sxs-lookup"><span data-stu-id="8538c-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="8538c-114">将跳过原始制造商注册，因为设备由 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="8538c-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="8538c-115">使用公司品牌登录体验</span><span class="sxs-lookup"><span data-stu-id="8538c-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="8538c-116">如果你的公司有"将公司品牌添加到Microsoft 365[登录](../admin/setup/customize-sign-in-page.md)"页面，设备用户将在登录时获得该体验。</span><span class="sxs-lookup"><span data-stu-id="8538c-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](../admin/setup/customize-sign-in-page.md), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="8538c-117">使用已配置的 AAD 帐户自动注册 MDM。</span><span class="sxs-lookup"><span data-stu-id="8538c-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="8538c-118">用户标识由用户Azure Active Directory，用户将登录到 Windows，Microsoft 365其Microsoft 365 商业高级版凭据。</span><span class="sxs-lookup"><span data-stu-id="8538c-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="8538c-119">**可选设置：**</span><span class="sxs-lookup"><span data-stu-id="8538c-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="8538c-120">**设置**</span><span class="sxs-lookup"><span data-stu-id="8538c-120">**Setting**</span></span>|<span data-ttu-id="8538c-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="8538c-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8538c-122">默认情况下，跳过 ("关闭") </span><span class="sxs-lookup"><span data-stu-id="8538c-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="8538c-123">如果此选项设置为 **"** 打开"，则设备用户将看不到设备的许可协议，Windows首次登录时将看不到该设备。</span><span class="sxs-lookup"><span data-stu-id="8538c-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="8538c-124">不允许用户成为本地管理员</span><span class="sxs-lookup"><span data-stu-id="8538c-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="8538c-125">如果此选项设置为 **"打开"，** 则设备用户将无法安装任何个人应用，例如 Cortana。</span><span class="sxs-lookup"><span data-stu-id="8538c-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
