---
title: 在 iOS 上保护 Office 应用
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何使用 Microsoft 365 商业高级版保护 iOS 上的 Office 应用。
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701587"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="297f7-103">在 iOS 上保护 Office 应用</span><span class="sxs-lookup"><span data-stu-id="297f7-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="297f7-104">可以设置要求移动用户输入 PIN 或指纹才能登录的用户访问策略，并加密存储在其设备上的工作文件。</span><span class="sxs-lookup"><span data-stu-id="297f7-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="297f7-105">试一试！</span><span class="sxs-lookup"><span data-stu-id="297f7-105">Try it!</span></span>

1. <span data-ttu-id="297f7-106">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="297f7-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="297f7-107">在 **"策略"** 下，**选择"添加策略"。**</span><span class="sxs-lookup"><span data-stu-id="297f7-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="297f7-108">在 **"添加策略"** 窗格中，在"策略名称"下输入名称，然后选择"策略类型"下想要 **的策略类型**。</span><span class="sxs-lookup"><span data-stu-id="297f7-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="297f7-109">打开 **"管理用户如何在移动设备上** 访问 Office 文件"，然后确保以下三项设置已打开：</span><span class="sxs-lookup"><span data-stu-id="297f7-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="297f7-110">**需要 PIN 或指纹才能访问 Office 应用**</span><span class="sxs-lookup"><span data-stu-id="297f7-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="297f7-111">**在设备丢失或被盗时保护工作文件**</span><span class="sxs-lookup"><span data-stu-id="297f7-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="297f7-112">**加密工作文件**</span><span class="sxs-lookup"><span data-stu-id="297f7-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="297f7-113">在这些 **应用中的文件将受到保护下**，选择要在移动设备上保护的 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="297f7-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="297f7-114">在 **"谁将获取这些设置？"** 下，默认情况下会选择所有用户，但你可以选择"更改"来选择已创建的任何安全组。</span><span class="sxs-lookup"><span data-stu-id="297f7-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="297f7-115">若要完成策略创建，请选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="297f7-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="297f7-116">在"**添加策略"** 页上，选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="297f7-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="297f7-117">在管理中心主页上，通过选择"策略"并查看"策略"页上的策略，确认已添加 **新** 策略。</span><span class="sxs-lookup"><span data-stu-id="297f7-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>