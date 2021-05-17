---
title: 将域从 Microsoft 转移到其他主机
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '在此处查找将域从 Microsoft 转移到另一个注册机构的步骤。 '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126343"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="e3887-103">将域从 Microsoft 转移到其他主机</span><span class="sxs-lookup"><span data-stu-id="e3887-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="e3887-104">在从 Microsoft 购买域Microsoft 365 60 天内，你无法将域转移到另一个注册机构。</span><span class="sxs-lookup"><span data-stu-id="e3887-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="e3887-105">Whois _查询_   显示 Microsoft 购买的域注册机构为"Wild West Domains LLC"。</span><span class="sxs-lookup"><span data-stu-id="e3887-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="e3887-106">但是，应仅就你购买Microsoft 365联系 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="e3887-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="e3887-107">按照以下步骤在 Microsoft 365 获取代码，然后转到其他域注册机构网站以设置将域名传输到新注册机构。</span><span class="sxs-lookup"><span data-stu-id="e3887-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="e3887-108">转移域</span><span class="sxs-lookup"><span data-stu-id="e3887-108">Transfer a domain</span></span>

1. <span data-ttu-id="e3887-109">在管理中心，  **转到"设置**   >  **域"。**</span><span class="sxs-lookup"><span data-stu-id="e3887-109">In the admin center, go to   **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="e3887-110">On the **Domains** page， select the Microsoft 365 domain that you want to transfer to another domain registrar， and then select **Check health**.</span><span class="sxs-lookup"><span data-stu-id="e3887-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="e3887-111">在页面顶部，选择"转移 **域"。**</span><span class="sxs-lookup"><span data-stu-id="e3887-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="e3887-112">在"**选择域的传输位置**"页上，选择 **"其他注册机构"，** 然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="e3887-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="e3887-113">在解锁 **域传输页面上**，选择解锁 **传输<_你的域，_ >** 然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="e3887-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="e3887-114">检查域传输联系人信息，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="e3887-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="e3887-115">复制授权代码并等待大约 30 分钟，让域传输状态在"注册"选项卡上更改为"已解锁"进行传输，然后再继续执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e3887-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="e3887-116">转到要管理域名的域注册机构的网站。</span><span class="sxs-lookup"><span data-stu-id="e3887-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="e3887-117">按照说明传输域 (在网站上搜索帮助) 。</span><span class="sxs-lookup"><span data-stu-id="e3887-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="e3887-118">这通常意味着支付转移费用，将 Authcode 给予新注册机构，以便他们可以启动转移。</span><span class="sxs-lookup"><span data-stu-id="e3887-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="e3887-119">Microsoft 将通过电子邮件确认我们已收到转移请求，域将在 5 天内转移。</span><span class="sxs-lookup"><span data-stu-id="e3887-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="e3887-120">您可以在"域"页面上找到授权代码"注册" **选项卡Microsoft 365。**</span><span class="sxs-lookup"><span data-stu-id="e3887-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e3887-121">.uk 域需要不同的过程。</span><span class="sxs-lookup"><span data-stu-id="e3887-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="e3887-122">请联系 Microsoft 支持部门并请求 **IPS 标记更改** ，以匹配要管理域的注册机构。</span><span class="sxs-lookup"><span data-stu-id="e3887-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="e3887-123">标记更改后，域将立即转移到新注册机构。</span><span class="sxs-lookup"><span data-stu-id="e3887-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="e3887-124">然后，你需要与新的注册机构合作来完成转移，可能支付转移费用，并借助你的新注册机构将已转移的域添加到你的帐户。</span><span class="sxs-lookup"><span data-stu-id="e3887-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="e3887-125">传输完成后，你将在新的域注册机构续订域。</span><span class="sxs-lookup"><span data-stu-id="e3887-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="e3887-126">若要完成此过程，请返回到管理中心中的"域"页面，然后选择"完成  **域传输"。**</span><span class="sxs-lookup"><span data-stu-id="e3887-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="e3887-127">这会将域标记为不再从 Microsoft 365 购买，并禁用域订阅。</span><span class="sxs-lookup"><span data-stu-id="e3887-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="e3887-128">它将不会从租户中删除域，并且不会影响域中的现有用户和邮箱。</span><span class="sxs-lookup"><span data-stu-id="e3887-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="e3887-129">Microsoft 365购买的域不符合名称服务器更改或在组织之间传输Microsoft 365资格。</span><span class="sxs-lookup"><span data-stu-id="e3887-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="e3887-130">如果其中任一项是必需的，则必须将域注册转移到另一个注册机构。</span><span class="sxs-lookup"><span data-stu-id="e3887-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
