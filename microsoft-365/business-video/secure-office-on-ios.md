---
title: 保护 iOS 上的 Office 应用
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何使用 Microsoft 365 商业高级版保护 iOS 上的 Office 应用。
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580458"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="390f6-103">保护 iOS 上的 Office 应用</span><span class="sxs-lookup"><span data-stu-id="390f6-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="390f6-104">可以设置要求移动用户输入 PIN 或指纹进行登录的用户访问策略，并加密存储在其设备上的工作文件。</span><span class="sxs-lookup"><span data-stu-id="390f6-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="390f6-105">试一试！</span><span class="sxs-lookup"><span data-stu-id="390f6-105">Try it!</span></span>

1. <span data-ttu-id="390f6-106">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="390f6-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="390f6-107">在 **"策略"** 下，选择 **"添加策略"。**</span><span class="sxs-lookup"><span data-stu-id="390f6-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="390f6-108">在"**添加策略"** 窗格中，在"策略名称"下输入名称，然后选择"策略类型"下想要 **的策略类型**。</span><span class="sxs-lookup"><span data-stu-id="390f6-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="390f6-109">打开 **"管理用户如何在移动设备上访问 Office 文件"，** 然后确保以下三个设置已打开：</span><span class="sxs-lookup"><span data-stu-id="390f6-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="390f6-110">**需要 PIN 或指纹才能访问 Office 应用**</span><span class="sxs-lookup"><span data-stu-id="390f6-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="390f6-111">**在设备丢失或被盗时保护工作文件**</span><span class="sxs-lookup"><span data-stu-id="390f6-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="390f6-112">**加密工作文件**</span><span class="sxs-lookup"><span data-stu-id="390f6-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="390f6-113">在 **"这些应用中的文件将受到保护"下**，选择要在移动设备上保护的 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="390f6-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="390f6-114">在“**谁将收到这些设置?**”下方，将默认选中所有用户，但可以选择“**更改**”以选择所创建的任何安全组。</span><span class="sxs-lookup"><span data-stu-id="390f6-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="390f6-115">选择“**添加**”，策略即创建完毕。</span><span class="sxs-lookup"><span data-stu-id="390f6-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="390f6-116">在“**添加策略**”页面上，选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="390f6-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="390f6-117">在管理中心主页上，选择“**策略**”并在“**策略**”页面上查看策略，确认已添加新策略。</span><span class="sxs-lookup"><span data-stu-id="390f6-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>