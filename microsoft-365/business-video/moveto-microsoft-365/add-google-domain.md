---
title: 添加 Google Workspace 域
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将域从 Google Workspace 移动到 Microsoft 365 商业版。
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49924998"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="e2dc6-103">将 Google Workspace 域添加到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2dc6-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="e2dc6-104">将 Google Workspace 域添加到 Microsoft 365 商业版，以便你可以继续使用你的企业电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e2dc6-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="e2dc6-105">试一试！</span><span class="sxs-lookup"><span data-stu-id="e2dc6-105">Try it!</span></span>

1. <span data-ttu-id="e2dc6-106">转到 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e2dc6-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="e2dc6-107">在 Microsoft 365 管理中心的左侧导航中，选择"显示全部"、"设置"和"**域"。**</span><span class="sxs-lookup"><span data-stu-id="e2dc6-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="e2dc6-108">选择 **"添加域**"，输入域名，然后选择 **"使用此域"。**</span><span class="sxs-lookup"><span data-stu-id="e2dc6-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="e2dc6-109">选择" **将 TXT 记录添加到域 DNS** 记录 **"，选择"** 继续"，然后复制 TXT 值。</span><span class="sxs-lookup"><span data-stu-id="e2dc6-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="e2dc6-110">返回到 Google [管理控制台](https://admin.google.com)**，选择"** 域"、"管理域"、"**查看详细信息**"、"管理 **域**"和 **"DNS"，** 然后向下滚动到 **自定义资源记录**。 </span><span class="sxs-lookup"><span data-stu-id="e2dc6-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="e2dc6-111">打开记录类型下拉列表，选择 **TXT，** 粘贴复制的 TXT 值，然后选择"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="e2dc6-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="e2dc6-112">更新通常需要几分钟内完成，但最多可能需要 48 小时。</span><span class="sxs-lookup"><span data-stu-id="e2dc6-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="e2dc6-113">返回到 Microsoft 365 管理中心，选择 **"** 验证"，然后 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="e2dc6-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="e2dc6-114">若要将域设置为用户的主电子邮件，请在左侧导航 **中，选择**"用户  >  **活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="e2dc6-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="e2dc6-115">选择用户，选择 **"管理用户名和电子邮件\*\*\*\*"，"** 编辑"，从下拉列表中选择域，然后选择"**完成** 并 **保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="e2dc6-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="e2dc6-116">为每个用户重复此过程。</span><span class="sxs-lookup"><span data-stu-id="e2dc6-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="e2dc6-117">完成后，即可安装 Office 应用，将电子邮件和日历项目迁移到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e2dc6-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 