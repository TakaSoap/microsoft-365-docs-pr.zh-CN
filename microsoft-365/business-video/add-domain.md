---
title: 添加域
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将另一个域添加到订阅。
ms.openlocfilehash: a641005913f7dfd866366f0f8065019dd5c17fe8
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903738"
---
# <a name="add-another-domain"></a><span data-ttu-id="0efdd-103">添加其他域</span><span class="sxs-lookup"><span data-stu-id="0efdd-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="0efdd-104">您的公司可能出于不同目的需要多个域名。</span><span class="sxs-lookup"><span data-stu-id="0efdd-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="0efdd-105">例如，你可能想要添加公司名称的不同拼写，因为客户已在使用它，并且他们的通信未能到达你。</span><span class="sxs-lookup"><span data-stu-id="0efdd-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="0efdd-106">试一试！</span><span class="sxs-lookup"><span data-stu-id="0efdd-106">Try it!</span></span>

1. <span data-ttu-id="0efdd-107">In the Microsoft 365 admin center， choose **Setup**.</span><span class="sxs-lookup"><span data-stu-id="0efdd-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="0efdd-108">在 **"设置自定义域"下，选择**"查看 **"。**</span><span class="sxs-lookup"><span data-stu-id="0efdd-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="0efdd-109">选择 **"管理**"，然后选择"**添加域"。**</span><span class="sxs-lookup"><span data-stu-id="0efdd-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="0efdd-110">输入要添加的新域名，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="0efdd-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="0efdd-111">登录域注册机构（在这种情况下为 GoDaddy），然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="0efdd-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="0efdd-112">如果系统提示，登录注册机构，然后选择"授权 **"。**</span><span class="sxs-lookup"><span data-stu-id="0efdd-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="0efdd-113">选择 **"为我添加 DNS 记录"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0efdd-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="0efdd-114">选择新域的服务并清除将由其他域处理的任何服务的复选框。</span><span class="sxs-lookup"><span data-stu-id="0efdd-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="0efdd-115">例如，如果你只想将新域用于电子邮件，请选择"Exchange"，并清除"新建"和"Skype for Business Office 365 移动设备管理"。  </span><span class="sxs-lookup"><span data-stu-id="0efdd-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="0efdd-116">选择 **"下** 一 **步"，"** 授权 **"，"** 下一步"，然后选择"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="0efdd-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="0efdd-117">已添加新域。</span><span class="sxs-lookup"><span data-stu-id="0efdd-117">Your new domain has been added.</span></span>

<span data-ttu-id="0efdd-118">若要在你的新域中接收电子邮件，你需要为每个用户添加新的电子邮件别名：</span><span class="sxs-lookup"><span data-stu-id="0efdd-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="0efdd-119">选择 **"用户\*\*\*\*"** 和"活动用户"，然后选择将为其分配新别名的用户。</span><span class="sxs-lookup"><span data-stu-id="0efdd-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="0efdd-120">选择 **"管理电子邮件别名"，** 然后选择"**添加别名"。**</span><span class="sxs-lookup"><span data-stu-id="0efdd-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="0efdd-121">输入用户名，然后从下拉列表中选择新域。</span><span class="sxs-lookup"><span data-stu-id="0efdd-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="0efdd-122">选择 **"保存更改**"，然后关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="0efdd-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="0efdd-123">对应在新域中接收电子邮件的每个用户重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="0efdd-123">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="0efdd-124">相关内容</span><span class="sxs-lookup"><span data-stu-id="0efdd-124">Related content</span></span>

<span data-ttu-id="0efdd-125">[](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)将域添加到 Microsoft 365 (文章) 添加[DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)记录以连接您的域 (文章) [更改名称服务器](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)以设置 Microsoft 365 与任何域注册机构 (文章) [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (article) </span><span class="sxs-lookup"><span data-stu-id="0efdd-125">[Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (article) [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) (article) [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) (article) [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (article)</span></span>