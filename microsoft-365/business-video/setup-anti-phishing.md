---
title: 设置防钓鱼保护
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何设置防钓鱼保护。
ms.openlocfilehash: 8cef8f916a8a3e2b27dd7f76ddecd921d59ca0c4
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421999"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="7c54b-103">设置防网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="7c54b-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="7c54b-104">网络钓鱼是一种恶意攻击，其中电子邮件看起来像是从熟悉的源发送的，但它会尝试收集个人信息。</span><span class="sxs-lookup"><span data-stu-id="7c54b-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="7c54b-105">默认情况下，Microsoft 365 包括一些防钓鱼保护，但您可以通过精简设置来增强该保护。</span><span class="sxs-lookup"><span data-stu-id="7c54b-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="7c54b-106">让我们看一下。</span><span class="sxs-lookup"><span data-stu-id="7c54b-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="7c54b-107">试一试！</span><span class="sxs-lookup"><span data-stu-id="7c54b-107">Try it!</span></span>

1. <span data-ttu-id="7c54b-108">在管理中心中，选择 [https://admin.microsoft.com](https://admin.microsoft.com) **"安全**、**威胁管理**、**策略**"，然后选择 **"ATP 防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="7c54b-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="7c54b-109">选择 **"默认策略** "以优化它。</span><span class="sxs-lookup"><span data-stu-id="7c54b-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="7c54b-110">在 **"模拟"部分**，选择"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="7c54b-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="7c54b-111">转到 **"添加域"进行保护** ，然后选择切换以自动包含你拥有的域。</span><span class="sxs-lookup"><span data-stu-id="7c54b-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="7c54b-112">转到 **"操作**"，打开下拉列表 如果 **电子邮件** 是由模拟用户发送的，然后选择您想要的操作。</span><span class="sxs-lookup"><span data-stu-id="7c54b-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="7c54b-113">打开下拉列表 如果 **电子邮件是由** 模拟域发送的，然后选择您想要的操作。</span><span class="sxs-lookup"><span data-stu-id="7c54b-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="7c54b-114">选择 **"打开模拟安全提示"。**</span><span class="sxs-lookup"><span data-stu-id="7c54b-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="7c54b-115">选择当系统检测到模拟用户、域或异常字符时，是否应该为用户提供提示。</span><span class="sxs-lookup"><span data-stu-id="7c54b-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="7c54b-116">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7c54b-116">Select **Save**.</span></span>
1. <span data-ttu-id="7c54b-117">选择 **邮箱智能** 并验证其是否打开。</span><span class="sxs-lookup"><span data-stu-id="7c54b-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="7c54b-118">这使您的电子邮件通过学习使用模式提高效率。</span><span class="sxs-lookup"><span data-stu-id="7c54b-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="7c54b-119">选择 **"添加受信任的发件人和域"。**</span><span class="sxs-lookup"><span data-stu-id="7c54b-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="7c54b-120">你可以在此处添加不应分类为模拟的电子邮件地址或域。</span><span class="sxs-lookup"><span data-stu-id="7c54b-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="7c54b-121">选择 **"查看设置"，** 确保一切正确，选择" **保存"，** 然后 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="7c54b-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="7c54b-122">贵组织现在可以更好地防范网络钓鱼威胁。</span><span class="sxs-lookup"><span data-stu-id="7c54b-122">Your organization now has better protection from phishing threats.</span></span>