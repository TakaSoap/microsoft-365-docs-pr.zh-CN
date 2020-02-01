---
title: 关于"AutoPilot 配置文件"设置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 配置文件可帮助您控制 Windows 在用户设备上的安装方式。 配置文件包含 "跳过 Cortana 安装" 等默认和可选设置。
ms.openlocfilehash: 1cc8a3171bbc4a1e5cb531b9364c7791586fc339
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593325"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="60d14-104">关于"AutoPilot 配置文件"设置</span><span class="sxs-lookup"><span data-stu-id="60d14-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="60d14-105">AutoPilot 配置文件设置</span><span class="sxs-lookup"><span data-stu-id="60d14-105">AutoPilot profile settings</span></span>

<span data-ttu-id="60d14-106">您可以使用 AutoPilot 配置文件来控制 Windows 在用户设备上的安装方式。</span><span class="sxs-lookup"><span data-stu-id="60d14-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="60d14-107">配置文件包含以下设置。</span><span class="sxs-lookup"><span data-stu-id="60d14-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="60d14-108">**自动设置的 AutoPilot 默认功能（必需）：**</span><span class="sxs-lookup"><span data-stu-id="60d14-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="60d14-109">**设置**</span><span class="sxs-lookup"><span data-stu-id="60d14-109">**Setting**</span></span>|<span data-ttu-id="60d14-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="60d14-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60d14-111">跳过 Cortana、OneDrive 和 OEM 注册</span><span class="sxs-lookup"><span data-stu-id="60d14-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="60d14-112">跳过安装使用者应用程序，如 Cortana 和个人 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="60d14-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="60d14-113">只要用户是设备上的本地管理员，设备用户就可以在以后安装这些设备。</span><span class="sxs-lookup"><span data-stu-id="60d14-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="60d14-114">由于设备将由 Microsoft 365 商业版管理，因此将跳过原始制造商注册。</span><span class="sxs-lookup"><span data-stu-id="60d14-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="60d14-115">使用贵公司品牌登录体验</span><span class="sxs-lookup"><span data-stu-id="60d14-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="60d14-116">如果您的公司[将公司商标添加到 Office 365 登录页面](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)，则设备用户将在登录时获得该体验。</span><span class="sxs-lookup"><span data-stu-id="60d14-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="60d14-117">使用已配置的 AAD 帐户的 MDM 自动注册。</span><span class="sxs-lookup"><span data-stu-id="60d14-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="60d14-118">用户标识将由 Azure Active Directory 管理，并且用户将使用其 Microsoft 365 商业版凭据登录到 Windows 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="60d14-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="60d14-119">**可选设置：**</span><span class="sxs-lookup"><span data-stu-id="60d14-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="60d14-120">**设置**</span><span class="sxs-lookup"><span data-stu-id="60d14-120">**Setting**</span></span>|<span data-ttu-id="60d14-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="60d14-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60d14-122">跳过隐私设置（默认情况下禁用）</span><span class="sxs-lookup"><span data-stu-id="60d14-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="60d14-123">如果此选项设置为 **"开**"，则在用户首次登录时，设备用户将看不到设备和 Windows 的许可协议。</span><span class="sxs-lookup"><span data-stu-id="60d14-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="60d14-124">不允许用户成为本地管理员</span><span class="sxs-lookup"><span data-stu-id="60d14-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="60d14-125">如果此选项设置为 **"开**"，则设备用户将无法安装任何个人应用程序，如 Cortana。</span><span class="sxs-lookup"><span data-stu-id="60d14-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
