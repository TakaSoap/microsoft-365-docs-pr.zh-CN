---
title: 关于"AutoPilot 配置文件"设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自动执行某些操作配置文件可帮助您控制如何获取 Windows 安装到用户设备上。配置文件包含默认和可选设置如跳过 Cortana 安装。
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865425"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="be5b2-104">关于"AutoPilot 配置文件"设置</span><span class="sxs-lookup"><span data-stu-id="be5b2-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="be5b2-105">自动执行某些操作配置文件设置</span><span class="sxs-lookup"><span data-stu-id="be5b2-105">AutoPilot profile settings</span></span>

<span data-ttu-id="be5b2-p102">您可以控制 Windows 获取如何通过使用自动执行某些操作配置文件安装到用户设备上。配置文件包含以下设置。</span><span class="sxs-lookup"><span data-stu-id="be5b2-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="be5b2-108">**自动执行某些操作默认 （必需） 的功能将自动设置：**</span><span class="sxs-lookup"><span data-stu-id="be5b2-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="be5b2-109">**设置**</span><span class="sxs-lookup"><span data-stu-id="be5b2-109">**Setting**</span></span>|<span data-ttu-id="be5b2-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="be5b2-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be5b2-111">跳过 Cortana、 OneDrive 和 OEM 注册</span><span class="sxs-lookup"><span data-stu-id="be5b2-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="be5b2-p103">跳过使用者应用程序，如 Cortana 和个人 OneDrive 的安装。只要他或她是在设备上的本地管理员，则设备用户可以安装这些更高版本。原始制造商注册被跳过，因为设备将由 Microsoft 365 企业版。</span><span class="sxs-lookup"><span data-stu-id="be5b2-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="be5b2-115">登录体验与您公司品牌</span><span class="sxs-lookup"><span data-stu-id="be5b2-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="be5b2-116">如果您的公司具有[添加贵公司品牌到 Office 365 登录页](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)，设备用户在登录后获得的体验。</span><span class="sxs-lookup"><span data-stu-id="be5b2-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="be5b2-117">MDM 自动注册配置 AAD 帐户。</span><span class="sxs-lookup"><span data-stu-id="be5b2-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="be5b2-118">将由 Azure Active directory，来管理用户标识和用户将使用其 Microsoft 365 业务凭据登录到 Windows 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="be5b2-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="be5b2-119">**可选设置：**</span><span class="sxs-lookup"><span data-stu-id="be5b2-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="be5b2-120">**设置**</span><span class="sxs-lookup"><span data-stu-id="be5b2-120">**Setting**</span></span>|<span data-ttu-id="be5b2-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="be5b2-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be5b2-122">跳过隐私设置 （默认情况下关闭）</span><span class="sxs-lookup"><span data-stu-id="be5b2-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="be5b2-123">如果此选项设置为**在**设备用户将不会看到设备和窗口的许可协议，他/她第一次登录时。</span><span class="sxs-lookup"><span data-stu-id="be5b2-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="be5b2-124">不允许用户成为本地管理员</span><span class="sxs-lookup"><span data-stu-id="be5b2-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="be5b2-125">如果此选项设置为**在**设备用户不能安装任何个人的应用程序，如 Cortana。</span><span class="sxs-lookup"><span data-stu-id="be5b2-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
