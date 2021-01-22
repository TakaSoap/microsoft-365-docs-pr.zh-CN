---
title: 管理安全链接
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何管理安全链接，以保护企业免受恶意网站的攻击。
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928014"
---
# <a name="manage-safe-links"></a><span data-ttu-id="e1e9c-103">管理安全链接</span><span class="sxs-lookup"><span data-stu-id="e1e9c-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="e1e9c-104">Microsoft Defender for Office 365（以前称为 Microsoft 365 ATP 或高级威胁防护）可帮助保护你的企业免受恶意网站的攻击，当用户单击 Office 应用中的链接时。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="e1e9c-105">试一试！</span><span class="sxs-lookup"><span data-stu-id="e1e9c-105">Try it!</span></span>

1. <span data-ttu-id="e1e9c-106">转到管理 [中心，](https://admin.microsoft.com)然后选择"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="e1e9c-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="e1e9c-107">向下滚动以 **增强对高级威胁的保护**。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="e1e9c-108">选择 **"查看\*\*\*\*、管理**"，然后选择 **"ATP 安全链接"。**</span><span class="sxs-lookup"><span data-stu-id="e1e9c-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="e1e9c-109">在 **"应用于整个组织的策略"下**，选择 **"** 默认策略"，然后选择"编辑 **"** 图标。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="e1e9c-110">输入要阻止的 URL。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="e1e9c-111">Select **Use safe links in Office apps， Office for iOS and Android**;select **Do not track when users click safe links**;并选择 **"不允许用户单击原始 URL 的安全链接"。**</span><span class="sxs-lookup"><span data-stu-id="e1e9c-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="e1e9c-112">如果设置默认策略，则可能已经选择了这些策略。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="e1e9c-113">选择 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-113">Select **Save**.</span></span>
1. <span data-ttu-id="e1e9c-114">在 **"适用于特定收件人的策略**"下，选择 **"推荐的安全链接** 规则"，然后选择"编辑 **"** 图标。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="e1e9c-115">选择 **设置**，向下滚动，输入不希望检查的 URL，然后选择"添加 **"** 图标。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="e1e9c-116">选择 **"应用于"，** 然后选择您的域名。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="e1e9c-117">选择要应用规则的其他域。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="e1e9c-118">选择 **"添加\*\*\*\*"，"** 确定"，然后 **保存**。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="e1e9c-119">ATP 安全链接现已配置。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="e1e9c-120">最多允许 30 分钟更改生效。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="e1e9c-121">当用户收到包含链接的电子邮件时，将扫描这些链接。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="e1e9c-122">如果认为链接是安全的，可单击这些链接。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="e1e9c-123">但是，如果链接位于阻止列表中，用户将看到一条消息，指出该链接已被阻止。</span><span class="sxs-lookup"><span data-stu-id="e1e9c-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>