---
title: 将域从 Microsoft 传输到另一台主机
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '在此处查找将域从 Microsoft 转移到另一个注册器的步骤。 '
ms.openlocfilehash: d960b57a2c82b804d61ead1c672c00f0543b3ae8
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370320"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="fb365-103">将域从 Microsoft 传输到另一台主机</span><span class="sxs-lookup"><span data-stu-id="fb365-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="fb365-104">从 Microsoft 购买域后，不能将 Microsoft 365 域传输到另一个注册器60天。</span><span class="sxs-lookup"><span data-stu-id="fb365-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="fb365-105">_Whois_   查询显示 Microsoft 购买的域注册器作为通配符西部域 LLC。</span><span class="sxs-lookup"><span data-stu-id="fb365-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="fb365-106">但是，应仅联系 microsoft 365 购买的域的相关 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="fb365-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="fb365-107">按照以下步骤在 Microsoft 365 获取代码，然后转到其他域注册器网站，以将您的域名转移到新的注册机构。</span><span class="sxs-lookup"><span data-stu-id="fb365-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="fb365-108">转移域</span><span class="sxs-lookup"><span data-stu-id="fb365-108">Transfer a domain</span></span>

1. <span data-ttu-id="fb365-109">在管理中心中，转到  **设置**   >  **域**。</span><span class="sxs-lookup"><span data-stu-id="fb365-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="fb365-110">在 " **域** " 页上，选择要转移到其他域注册机构的 Microsoft 365 域，然后选择 " **检查运行状况**"。</span><span class="sxs-lookup"><span data-stu-id="fb365-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="fb365-111">在页面顶部，选择 " **转移域**"。</span><span class="sxs-lookup"><span data-stu-id="fb365-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="fb365-112">在 " **选择转移域的位置** " 页上，选择 **不同的注册**器，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fb365-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="fb365-113">在 "**解锁域转移**" 页上，选择 "**解锁 <_您的域_ > 的传输**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fb365-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="fb365-114">检查你的域传输联系信息，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fb365-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="fb365-115">复制授权代码，并等待大约30分钟，让您的域传输状态更改为 "**注册**" 选项卡上的 "已**解锁以供转移**"，然后再继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="fb365-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="fb365-116">转到要对其进行管理的域名注册机构的网站，以继续进行。</span><span class="sxs-lookup"><span data-stu-id="fb365-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="fb365-117">按照传输域的说明 (搜索其网站) 的帮助。</span><span class="sxs-lookup"><span data-stu-id="fb365-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="fb365-118">这通常意味着支付转帐费用并为新的注册机构提供 Authcode，以便他们可以启动传输。</span><span class="sxs-lookup"><span data-stu-id="fb365-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="fb365-119">Microsoft 会向你发送电子邮件以确认我们已收到传输请求，并且域将在5天内转移。</span><span class="sxs-lookup"><span data-stu-id="fb365-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="fb365-120">您可以在 Microsoft 365 中的 " **域**" 页上找到 "授权代码**注册**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fb365-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="fb365-121">英国域需要不同的过程。</span><span class="sxs-lookup"><span data-stu-id="fb365-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="fb365-122">请与 Microsoft 支持部门联系并请求 **IPS 标记更改** ，以匹配您要管理的域的注册器。</span><span class="sxs-lookup"><span data-stu-id="fb365-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="fb365-123">标记发生更改后，域将立即转移到新的注册器。</span><span class="sxs-lookup"><span data-stu-id="fb365-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="fb365-124">然后，您需要使用新的注册器完成转移，很可能会支付转让费用，并使用新的注册机构将转移的域添加到您的帐户。</span><span class="sxs-lookup"><span data-stu-id="fb365-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="fb365-125">传输完成后，你将在新域注册机构中续订你的域。</span><span class="sxs-lookup"><span data-stu-id="fb365-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="fb365-126">若要完成此过程，请返回管理中心的 " **域** " 页，然后选择 "  **完成域传输**"。</span><span class="sxs-lookup"><span data-stu-id="fb365-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="fb365-127">这将把域标记为不再从 Microsoft 365 购买，并将禁用域订阅。</span><span class="sxs-lookup"><span data-stu-id="fb365-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="fb365-128">它不会从租户中删除域，也不会影响域中的现有用户和邮箱。</span><span class="sxs-lookup"><span data-stu-id="fb365-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="fb365-129">Microsoft 365 购买的域不符合 nameserver 更改或在 Microsoft 365 组织之间传输域的条件。</span><span class="sxs-lookup"><span data-stu-id="fb365-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="fb365-130">如果需要其中任一项，则必须将域注册转移到其他注册器。</span><span class="sxs-lookup"><span data-stu-id="fb365-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
