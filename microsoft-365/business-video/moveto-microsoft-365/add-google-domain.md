---
title: 添加 Google Workspace 域
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
description: 了解如何将域从 Google Workspace 移动到 Microsoft 365 for business。
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578767"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="d2d71-103">将 Google Workspace 域添加到Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d2d71-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="d2d71-104">将 Google Workspace 域Microsoft 365商业应用，以便你可以一直使用你的企业电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d2d71-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="d2d71-105">试一试！</span><span class="sxs-lookup"><span data-stu-id="d2d71-105">Try it!</span></span>

1. <span data-ttu-id="d2d71-106">转到管理[Microsoft 365中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="d2d71-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="d2d71-107">在"Microsoft 365管理中心"的左侧导航中，选择"**显示** 全部"、设置"和"域 **"。**</span><span class="sxs-lookup"><span data-stu-id="d2d71-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="d2d71-108">选择 **"添加域**"，输入您的域名，然后选择"**使用此域"。**</span><span class="sxs-lookup"><span data-stu-id="d2d71-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="d2d71-109">选择" **将 TXT 记录添加到域 DNS** 记录"，选择" **继续**"，然后复制 TXT 值。</span><span class="sxs-lookup"><span data-stu-id="d2d71-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="d2d71-110">返回到 Google [管理](https://admin.google.com)控制台，选择"域"，"管理域"，"查看详细信息 **"，"** 管理域 **"，"DNS"，** 然后向下滚动到"**自定义资源记录"。**</span><span class="sxs-lookup"><span data-stu-id="d2d71-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="d2d71-111">打开记录类型下拉列表，选择 **"TXT"，** 粘贴复制的 TXT 值，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="d2d71-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="d2d71-112">更新通常需要几分钟时间，但最多可能需要 48 小时。</span><span class="sxs-lookup"><span data-stu-id="d2d71-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="d2d71-113">返回到管理Microsoft 365，选择 **"验证**"，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="d2d71-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="d2d71-114">若要将域设置为用户的主电子邮件，请在左侧导航中，选择"用户""  >  **活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="d2d71-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="d2d71-115">Choose a user， select **Manage username and email**， **Edit**， select your domain from the dropdown， then select **Done** and **Save changes**.</span><span class="sxs-lookup"><span data-stu-id="d2d71-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="d2d71-116">对每个用户重复此过程。</span><span class="sxs-lookup"><span data-stu-id="d2d71-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="d2d71-117">完成后，即可安装应用，Office电子邮件和日历项目迁移到Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d2d71-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 