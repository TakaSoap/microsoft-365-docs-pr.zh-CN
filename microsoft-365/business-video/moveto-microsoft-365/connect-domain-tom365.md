---
title: 将你的域连接到 Microsoft 365
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将域连接到 Microsoft 365。
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925106"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="16869-103">将域连接到 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="16869-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="16869-104">设置 Microsoft 365 并移动来自 Google Workspace 的电子邮件数据后，可以将域连接到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="16869-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="16869-105">首先，你需要从 Google 中删除现有 DNS 记录，然后我们可以从 Microsoft 365 添加新的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="16869-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="16869-106">试一试！</span><span class="sxs-lookup"><span data-stu-id="16869-106">Try it!</span></span>

1. <span data-ttu-id="16869-107">登录 Google Workspace 管理控制台[，admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="16869-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="16869-108">选择 **域**，**管理域**，**查看详细信息\*\*\*\*，管理域**，然后在左侧导航中选择 **DNS。**</span><span class="sxs-lookup"><span data-stu-id="16869-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="16869-109">向下滚动到综合 **记录**，打开 **Google Workspace，** 选择 **"删除**"，然后 **再次** 删除。</span><span class="sxs-lookup"><span data-stu-id="16869-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="16869-110">向下滚动到 **自定义资源** 记录并删除显示的任何现有 DNS 记录，包括之前可能为 Microsoft 365 创建的任何 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="16869-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="16869-111">转到 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="16869-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="16869-112">在左侧导航中，选择"显示 **所有"、"\*\*\*\*设置"和\*\*\*\*"域"。**</span><span class="sxs-lookup"><span data-stu-id="16869-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="16869-113">然后选择默认域。</span><span class="sxs-lookup"><span data-stu-id="16869-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="16869-114">选择 **"继续** 设置"，然后，若要连接域，请选择"**继续"。**</span><span class="sxs-lookup"><span data-stu-id="16869-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="16869-115">向下滚动以查看需要复制到 Google 的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="16869-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="16869-116">打开 **MX 记录**，在"指向 **地址或值**"下复制记录。</span><span class="sxs-lookup"><span data-stu-id="16869-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="16869-117">返回到 Google，在"自定义资源记录 **"部分，** 打开记录类型下拉列表并选择 **MX。**</span><span class="sxs-lookup"><span data-stu-id="16869-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="16869-118">在 **"数据** "字段中，粘贴复制的记录。</span><span class="sxs-lookup"><span data-stu-id="16869-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="16869-119">然后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="16869-119">Then select **Add**.</span></span>
1. <span data-ttu-id="16869-120">对 CNAME 和 TXT 记录重复此过程，并添加 Google DNS 管理页中的值。</span><span class="sxs-lookup"><span data-stu-id="16869-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="16869-121">返回到 Microsoft 365 管理中心，然后选择"**继续"。**</span><span class="sxs-lookup"><span data-stu-id="16869-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="16869-122">域设置已完成。</span><span class="sxs-lookup"><span data-stu-id="16869-122">Your domain setup is complete.</span></span>