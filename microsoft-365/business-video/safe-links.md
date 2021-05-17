---
title: 管理保险箱链接
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 了解如何管理保险箱链接，以保护你的企业免受恶意站点的攻击。
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580626"
---
# <a name="manage-safe-links"></a><span data-ttu-id="472e6-103">管理保险箱链接</span><span class="sxs-lookup"><span data-stu-id="472e6-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="472e6-104">Microsoft Defender for Office 365（以前称为 Microsoft 365 ATP 或高级威胁防护）可帮助保护你的企业免受恶意站点的攻击，当用户单击应用中Office链接。</span><span class="sxs-lookup"><span data-stu-id="472e6-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="472e6-105">试一试！</span><span class="sxs-lookup"><span data-stu-id="472e6-105">Try it!</span></span>

1. <span data-ttu-id="472e6-106">转到管理 [中心，然后选择](https://admin.microsoft.com)"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="472e6-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="472e6-107">向下滚动以 **提升对高级威胁的保护**。</span><span class="sxs-lookup"><span data-stu-id="472e6-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="472e6-108">选择 **"查看\*\*\*\*、管理**"，然后选择 **"ATP 保险箱链接"。**</span><span class="sxs-lookup"><span data-stu-id="472e6-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="472e6-109">在 **"应用于整个组织的策略"下**，选择" **默认策略** "，然后选择"编辑 **"** 图标。</span><span class="sxs-lookup"><span data-stu-id="472e6-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="472e6-110">输入要阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="472e6-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="472e6-111">在 **iOS 和 Android Office应用中选择Office安全链接**"选择 **"当用户单击安全链接时不跟踪";** 并选择 **"不允许用户通过安全链接单击到原始 URL"。**</span><span class="sxs-lookup"><span data-stu-id="472e6-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="472e6-112">如果设置了默认策略，则可能已经选择了这些策略。</span><span class="sxs-lookup"><span data-stu-id="472e6-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="472e6-113">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="472e6-113">Select **Save**.</span></span>
1. <span data-ttu-id="472e6-114">在 **"适用于特定收件人的策略"下**，选择 **"推荐的安全链接** 规则"，然后选择"编辑 **"** 图标。</span><span class="sxs-lookup"><span data-stu-id="472e6-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="472e6-115">选择 **"** 设置"，向下滚动，输入不希望检查的 URL，然后选择"添加 **"** 图标。</span><span class="sxs-lookup"><span data-stu-id="472e6-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="472e6-116">选择 **"应用到"，** 然后选择您的域名。</span><span class="sxs-lookup"><span data-stu-id="472e6-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="472e6-117">选择您希望规则应用于的其他任何域。</span><span class="sxs-lookup"><span data-stu-id="472e6-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="472e6-118">选择 **"添加\*\*\*\*"，"确定**"，然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="472e6-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="472e6-119">ATP 保险箱链接现已配置。</span><span class="sxs-lookup"><span data-stu-id="472e6-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="472e6-120">最多允许更改 30 分钟生效。</span><span class="sxs-lookup"><span data-stu-id="472e6-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="472e6-121">当用户收到包含链接的电子邮件时，将扫描这些链接。</span><span class="sxs-lookup"><span data-stu-id="472e6-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="472e6-122">如果认为链接是安全的，则这些链接是可单击的。</span><span class="sxs-lookup"><span data-stu-id="472e6-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="472e6-123">但是，如果链接位于阻止列表中，用户将看到一条消息，表明该链接已被阻止。</span><span class="sxs-lookup"><span data-stu-id="472e6-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>