---
title: 使用 Microsoft 365 商业高级版管理 Windows 10 专业版设备策略
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
description: 了解如何使用 Microsoft 365 商业高级版管理 Windows 10 专业版设备策略。
ms.openlocfilehash: 0f7cfff227e1ab4ea992414b513e341adbd9ef22
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578683"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="761ff-103">管理 Windows 10 专业版设备策略</span><span class="sxs-lookup"><span data-stu-id="761ff-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="761ff-104">使用 Microsoft 365 商业版，可确保 Windows Defender 防病毒功能在 Windows 10 设备上处于激活状态，而且 Microsoft 更新可自动下载到用户设备上。</span><span class="sxs-lookup"><span data-stu-id="761ff-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="761ff-105">试一试！</span><span class="sxs-lookup"><span data-stu-id="761ff-105">Try it!</span></span>

1. <span data-ttu-id="761ff-106">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="761ff-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="761ff-107">在“**策略**”下方，选择“添加策略”。</span><span class="sxs-lookup"><span data-stu-id="761ff-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="761ff-108">在“**添加策略**”窗格的“**策略名称**”下方输入名称，然后在“**策略类型**”下选择“**Windows 10 设备配置**”。</span><span class="sxs-lookup"><span data-stu-id="761ff-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="761ff-109">选择“**保护 Windows 10 设备**”即可查看子选项。</span><span class="sxs-lookup"><span data-stu-id="761ff-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="761ff-110">确保“**使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁**”和“**让 Windows 10 设备自动保持最新状态**”处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="761ff-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="761ff-111">在“**谁将收到这些设置?**”下方，将默认选中所有用户，但可以选择“**更改**”以选择所创建的任何安全组。</span><span class="sxs-lookup"><span data-stu-id="761ff-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="761ff-112">选择“**添加**”，策略即创建完毕。</span><span class="sxs-lookup"><span data-stu-id="761ff-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="761ff-113">在“**添加策略**”页面上，选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="761ff-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="761ff-114">在管理中心主页上，选择“**策略**”并在“**策略**”页面上查看策略，确认已添加新策略。</span><span class="sxs-lookup"><span data-stu-id="761ff-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="761ff-115">要验证策略是否已生效，请在用户的 Windows 10 设备上转到 Windows 更新，选择“**高级选项**”，然后确认设置显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="761ff-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="761ff-116">然后，单击“**选择更新交付方式**”，并确认设置显示是否为灰色并显示以下消息：**某些设置由组织隐藏或管理**。</span><span class="sxs-lookup"><span data-stu-id="761ff-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

