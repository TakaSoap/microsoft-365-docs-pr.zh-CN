---
title: 在两个 Office 365 帐户之间手动传输数据
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
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 了解在更改计划或公司名称或将多个订阅组合到一个中时，如何在两个 Office 365 帐户之间手动传输数据。
ms.openlocfilehash: 004dd586c207678157afdb418e54f3c3b5353304
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251137"
---
# <a name="transfer-data-manually-between-two-office-365-accounts"></a><span data-ttu-id="e75d5-103">在两个 Office 365 帐户之间手动传输数据</span><span class="sxs-lookup"><span data-stu-id="e75d5-103">Transfer data manually between two Office 365 accounts</span></span>

<span data-ttu-id="e75d5-104">准备汇总你的 sleeves，并在日历上阻止一段时间：在两个 Office 365 帐户之间传输数据是一种手动、复杂且耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="e75d5-104">Prepare to roll up your sleeves and block out a chunk of time on your calendar: transferring data between two Office 365 accounts is a manual, complicated, and time-consuming process.</span></span> <span data-ttu-id="e75d5-105">这不是自动或受支持的过程。</span><span class="sxs-lookup"><span data-stu-id="e75d5-105">This is not an automated or supported process.</span></span> <span data-ttu-id="e75d5-106">我们将开始着手。</span><span class="sxs-lookup"><span data-stu-id="e75d5-106">We'll get you started.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e75d5-107">在此过程中，在处理电子邮件、Skype for Business 和托管在 Office 365 上的公共网站时，将无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="e75d5-107">There will be down time during the process where email, Skype for Business and a public website hosted on Office 365 won't work.</span></span> <span data-ttu-id="e75d5-108">用户将获取新的用户名和密码，并将需要重置 Outlook。</span><span class="sxs-lookup"><span data-stu-id="e75d5-108">Users will get new user names and passwords, and they'll need to reset up Outlook.</span></span>

<span data-ttu-id="e75d5-109">**如果应用了以下任一情况，则仅使用本主题中的说明手动传输数据：**</span><span class="sxs-lookup"><span data-stu-id="e75d5-109">**Only transfer data manually using the instructions in this topic if one of the following applies:**</span></span>
  
- <span data-ttu-id="e75d5-110">您需要更改为其他服务系列中的计划。</span><span class="sxs-lookup"><span data-stu-id="e75d5-110">You need to change to a plan in a different service family.</span></span>

- <span data-ttu-id="e75d5-111">您的公司名称已更改，并且您决定创建新的订阅并迁移数据，因为您要使用不同的初始域名称。</span><span class="sxs-lookup"><span data-stu-id="e75d5-111">Your company name changed, and you decided to create a new subscription and migrate your data because you want to use different initial domain names.</span></span>

- <span data-ttu-id="e75d5-112">您需要将多个订阅合并为一个新的。</span><span class="sxs-lookup"><span data-stu-id="e75d5-112">You need to combine multiple subscriptions into one new one.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e75d5-113">如果您需要[更改订阅计划](../../commerce/subscriptions/switch-to-a-different-plan.md)并可以使用 "切换计划向导"，或者如果您需要转移到同一订阅系列中的新订阅计划，即使 "切换计划向导" 不起作用，您也不需要手动传输数据，并且没有停机时间。</span><span class="sxs-lookup"><span data-stu-id="e75d5-113">If you need to [change your subscription plan](../../commerce/subscriptions/switch-to-a-different-plan.md) and can use the Switch plans wizard, or if you need to transfer to a new subscription plan in the same subscription family even when the Switch plans wizard doesn't work, you don't need to manually transfer your data, and there is no down time.</span></span>

|<span data-ttu-id="e75d5-114">**Tasks**</span><span class="sxs-lookup"><span data-stu-id="e75d5-114">**Tasks**</span></span>|<span data-ttu-id="e75d5-115">**Steps**</span><span class="sxs-lookup"><span data-stu-id="e75d5-115">**Steps**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e75d5-116">购买要移到的计划。</span><span class="sxs-lookup"><span data-stu-id="e75d5-116">Purchase the plan you want to move to.</span></span>  <br/> |<span data-ttu-id="e75d5-117">当你注册时，请在初始域名中指定要使用的公司名称： *yourcompany* 、 *yourcompany* -public.sharepoint.com 和*yourcompany* 。</span><span class="sxs-lookup"><span data-stu-id="e75d5-117">When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com.</span></span> <span data-ttu-id="e75d5-118">您需要使用与为任何现有订阅所做的*yourcompany*不同的名称。</span><span class="sxs-lookup"><span data-stu-id="e75d5-118">You need to use a different  *yourcompany*  name than you did for any existing subscriptions.</span></span>  <br/> <span data-ttu-id="e75d5-119">> [!NOTE]> 在取消订阅以释放从我们的系统中使用*yourcompany*的初始域名时，通常至少需要几个月。</span><span class="sxs-lookup"><span data-stu-id="e75d5-119">> [!NOTE]>  It typically takes a minimum of several months after cancelling a subscription to release the initial domain names that use  *yourcompany*  from our systems.</span></span> <span data-ttu-id="e75d5-120">即使您计划保存旧 Office 365 订阅中的所有数据，并取消该订阅，旧的*yourcompany*值也不会立即可用于新订阅。</span><span class="sxs-lookup"><span data-stu-id="e75d5-120">Even if you plan to save all your data from your old Office 365 subscription, and cancel that subscription, the old  *yourcompany*  value is not immediately available for use in a new subscription.</span></span>           |
|<span data-ttu-id="e75d5-121">从旧的 Office 365 订阅中删除您的自定义域。</span><span class="sxs-lookup"><span data-stu-id="e75d5-121">Remove your custom domain from your old Office 365 subscription.</span></span>  <br/> | <span data-ttu-id="e75d5-122">在删除域以从用户电子邮件地址中删除域名并删除自定义域的电子邮件和 Lync 的 DNS 记录之前，请执行[所需的步骤](remove-a-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="e75d5-122">Follow the [required steps before you remove a domain](remove-a-domain.md) to remove the domain name from user email addresses and remove DNS records for email and Lync for the custom domain.</span></span> <span data-ttu-id="e75d5-123">如果您在 Office 365 上托管公共网站，则还需要删除指向它的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="e75d5-123">If you host your public website on Office 365, you'll also need to remove the CNAME record that points to it.</span></span>  <br/> <span data-ttu-id="e75d5-124">> [!IMPORTANT]> 删除了将电子邮件路由到此自定义域的 MX 记录后，电子邮件将停止工作，直到您向新帐户添加了域、设置新的 MX 记录并设置您的用户。</span><span class="sxs-lookup"><span data-stu-id="e75d5-124">> [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users.</span></span> <span data-ttu-id="e75d5-125">当您删除 Lync 的 DNS 记录时，Lync 将停止工作。</span><span class="sxs-lookup"><span data-stu-id="e75d5-125">When you remove the DNS records for Lync, Lync will stop working.</span></span> <span data-ttu-id="e75d5-126">删除指向公共网站的 CNAME 记录后，该记录将不可用。</span><span class="sxs-lookup"><span data-stu-id="e75d5-126">And after you remove the CNAME record that points to your public website, it will not be available.</span></span>           <span data-ttu-id="e75d5-127">[删除域](remove-a-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="e75d5-127">[Remove the domain](remove-a-domain.md) .</span></span>  <br/> |
|<span data-ttu-id="e75d5-128">为新订阅设置自定义域，并设置您的用户。</span><span class="sxs-lookup"><span data-stu-id="e75d5-128">Set up your custom domain for your new subscription, and set up your users.</span></span>  <br/> | <span data-ttu-id="e75d5-129">设置新的订阅，包括为自定义域创建所需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="e75d5-129">Set up your new subscription, including creating the required DNS records for your custom domain.</span></span>  <br/>  <span data-ttu-id="e75d5-130">创建您的用户并在自定义域上使用电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e75d5-130">Create your users, with email addresses on your custom domain.</span></span>  <br/> |
|<span data-ttu-id="e75d5-131">将数据从旧订阅传输到新订阅。</span><span class="sxs-lookup"><span data-stu-id="e75d5-131">Transfer data from your old subscription to your new subscription.</span></span>  <br/> | <span data-ttu-id="e75d5-132">在单独的浏览器窗口中登录两个帐户：</span><span class="sxs-lookup"><span data-stu-id="e75d5-132">Sign in to both accounts in separate browser windows:</span></span>  <br/>  <span data-ttu-id="e75d5-133">右键单击 "Internet Explorer" 图标，然后打开两个 "InPrivate 浏览器" 窗口。</span><span class="sxs-lookup"><span data-stu-id="e75d5-133">Right-click the Internet Explorer icon, and open two InPrivate browser windows.</span></span> <span data-ttu-id="e75d5-134">您可以在两个窗口中使用不同的凭据登录这两个帐户。</span><span class="sxs-lookup"><span data-stu-id="e75d5-134">You can use different credentials in the two windows to sign in on both accounts.</span></span>  <br/> [<span data-ttu-id="e75d5-135">在订阅之间传输管理设置</span><span class="sxs-lookup"><span data-stu-id="e75d5-135">Transfer administrative settings between subscriptions</span></span>](#email) <br/> [<span data-ttu-id="e75d5-136">传输团队网站结构和数据</span><span class="sxs-lookup"><span data-stu-id="e75d5-136">Transfer team site structure and data</span></span>](#transfer-team-site-structure-and-data) <br/> [<span data-ttu-id="e75d5-137">在订阅之间传输公共网站</span><span class="sxs-lookup"><span data-stu-id="e75d5-137">Transfer a public website between subscriptions</span></span>](#transfer-a-public-website-between-subscriptions) <br/> [<span data-ttu-id="e75d5-138">在订阅之间传输管理设置</span><span class="sxs-lookup"><span data-stu-id="e75d5-138">Transfer administrative settings between subscriptions</span></span>](#email) <br/> |
|<span data-ttu-id="e75d5-139">通过调用 Microsoft 支持 Office 365，取消所做计划的订阅。</span><span class="sxs-lookup"><span data-stu-id="e75d5-139">Cancel the subscription for the plan you're done with by calling Microsoft Support for Office 365.</span></span>  <br/> | <span data-ttu-id="e75d5-140">验证新订阅是否正常工作以及是否已传输所有数据。</span><span class="sxs-lookup"><span data-stu-id="e75d5-140">Verify that your new subscription is working and all data has been transferred.</span></span>  <br/>  <span data-ttu-id="e75d5-141">[联系客户支持](../contact-support-for-business-products.md)以取消旧订阅。</span><span class="sxs-lookup"><span data-stu-id="e75d5-141">[Contact customer support](../contact-support-for-business-products.md) to cancel your old subscription.</span></span>  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a><span data-ttu-id="e75d5-142">在订阅之间传输管理设置</span><span class="sxs-lookup"><span data-stu-id="e75d5-142">Transfer administrative settings between subscriptions</span></span>

<span data-ttu-id="e75d5-143">转到每个帐户上的以下页面，并根据旧帐户的设置设置新帐户。</span><span class="sxs-lookup"><span data-stu-id="e75d5-143">Go to the following pages on each account, and set up the new account based on the old account's settings.</span></span>
  
<span data-ttu-id="e75d5-144">如果要将数据从 Office 365 传输到 Office 365 中型企业版或 Office 365 企业版，则管理页面的结构各不相同。</span><span class="sxs-lookup"><span data-stu-id="e75d5-144">If you are transferring data from Office 365 to Office 365 Midsize Business or Office 365 Enterprise, the admin pages are structured differently.</span></span> <span data-ttu-id="e75d5-145">观看[视频：引入 Office 365 企业版](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx)，然后转到以下位置查看管理设置。</span><span class="sxs-lookup"><span data-stu-id="e75d5-145">Watch a [Video: Introducing Office 365 Enterprise](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx), and go to the following places to look at admin settings.</span></span>
  
<span data-ttu-id="e75d5-146">对于 Office 365 企业版和 Office 365 中型企业版：</span><span class="sxs-lookup"><span data-stu-id="e75d5-146">For Office 365 Enterprise and Office 365 Midsize Business:</span></span>
  
|<span data-ttu-id="e75d5-147">**Location**</span><span class="sxs-lookup"><span data-stu-id="e75d5-147">**Location**</span></span>|<span data-ttu-id="e75d5-148">**用途**</span><span class="sxs-lookup"><span data-stu-id="e75d5-148">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e75d5-149">**管理** \> **Office 365** \> **服务设置**</span><span class="sxs-lookup"><span data-stu-id="e75d5-149">**Admin** \> **Office 365** \> **Service settings**</span></span> <br/> |<span data-ttu-id="e75d5-150">选择每个选项卡，以获取邮件、网站、Lync、用户软件、密码、社区、权限管理和移动的设置。</span><span class="sxs-lookup"><span data-stu-id="e75d5-150">Select each tab for settings for mail, sites, Lync, user software, passwords, community, rights management, and mobile.</span></span>  <br/> |
|<span data-ttu-id="e75d5-151">**管理员** \> **Exchange**</span><span class="sxs-lookup"><span data-stu-id="e75d5-151">**Admin** \> **Exchange**</span></span> <br/> | <span data-ttu-id="e75d5-152">Exchange Online 设置</span><span class="sxs-lookup"><span data-stu-id="e75d5-152">Exchange Online settings</span></span>  <br/> |
|<span data-ttu-id="e75d5-153">**管理** \> **SharePoint**</span><span class="sxs-lookup"><span data-stu-id="e75d5-153">**Admin** \> **SharePoint**</span></span> <br/> | <span data-ttu-id="e75d5-154">SharePoint Online 设置</span><span class="sxs-lookup"><span data-stu-id="e75d5-154">SharePoint Online settings</span></span>  <br/> |
|<span data-ttu-id="e75d5-155">**管理员** \> **Skype for business**</span><span class="sxs-lookup"><span data-stu-id="e75d5-155">**Admin** \> **Skype for Business**</span></span> <br/> |<span data-ttu-id="e75d5-156">其他 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="e75d5-156">Additional Skype for Business settings</span></span>  <br/> |

<span data-ttu-id="e75d5-157">对于 Office 365 小型企业版</span><span class="sxs-lookup"><span data-stu-id="e75d5-157">For Office 365 Small Business</span></span>
  
|<span data-ttu-id="e75d5-158">**Location**</span><span class="sxs-lookup"><span data-stu-id="e75d5-158">**Location**</span></span>|<span data-ttu-id="e75d5-159">**用途**</span><span class="sxs-lookup"><span data-stu-id="e75d5-159">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e75d5-160">**管理员** \> **管理组织范围的设置**</span><span class="sxs-lookup"><span data-stu-id="e75d5-160">**Admin** \> **Manage organization-wide settings**</span></span> <br/> |<span data-ttu-id="e75d5-161">管理设置</span><span class="sxs-lookup"><span data-stu-id="e75d5-161">Administrative settings</span></span>  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a><span data-ttu-id="e75d5-162">在订阅之间传输公共网站</span><span class="sxs-lookup"><span data-stu-id="e75d5-162">Transfer a public website between subscriptions</span></span>

<span data-ttu-id="e75d5-163">如果在 Office 365 上托管有一个公共网站，则需要将其保存并在新订阅上重新创建它。</span><span class="sxs-lookup"><span data-stu-id="e75d5-163">If you have a public website hosted on Office 365, you need to save it and re-create it on your new subscription.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e75d5-164">如果您的公共网站托管在 DNS 托管提供商处，则不需要进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="e75d5-164">If your public website is hosted at a DNS hosting provider, no changes are required.</span></span> <span data-ttu-id="e75d5-165">您的转换不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="e75d5-165">It will not be affected by your transition.</span></span>
  
<span data-ttu-id="e75d5-166">若要将文档库或列表内容从 SharePoint Online 环境保存到文件共享或本地计算机，请参阅[SharePoint online 内容的手动迁移](https://go.microsoft.com/fwlink/p/?LinkId=402910)。</span><span class="sxs-lookup"><span data-stu-id="e75d5-166">To save a document library or list content from a SharePoint Online environment to file shares or to a local computer, see [Manual migration of SharePoint Online content](https://go.microsoft.com/fwlink/p/?LinkId=402910).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e75d5-167">公共网站迁移应用无法将数据传输到其他订阅。</span><span class="sxs-lookup"><span data-stu-id="e75d5-167">The Public site migration app can't transfer data to a different subscription.</span></span>
  
## <a name="transfer-team-site-structure-and-data"></a><span data-ttu-id="e75d5-168">传输团队网站结构和数据</span><span class="sxs-lookup"><span data-stu-id="e75d5-168">Transfer team site structure and data</span></span>

<span data-ttu-id="e75d5-169">有几种方法可以保存或传输团队网站数据：</span><span class="sxs-lookup"><span data-stu-id="e75d5-169">There are several ways to save or transfer team site data:</span></span>
  
- <span data-ttu-id="e75d5-170">您可以将旧网站另存为模板，并将该模板导入到新网站。</span><span class="sxs-lookup"><span data-stu-id="e75d5-170">You can save the old site as a template and import the template into the new site.</span></span>

- <span data-ttu-id="e75d5-171">若要传输文档，请首先手动在新网站上重新创建层次结构。</span><span class="sxs-lookup"><span data-stu-id="e75d5-171">To transfer documents, first manually recreate your hierarchy on the new site.</span></span> <span data-ttu-id="e75d5-172">然后，您可以同时打开这两个 SharePoint 团队网站，同时使用 Windows 资源管理器打开文档库，并复制并粘贴文档。</span><span class="sxs-lookup"><span data-stu-id="e75d5-172">Then you can open both SharePoint team sites at the same time, open both document libraries with Windows Explorer, and copy and paste the documents.</span></span> <span data-ttu-id="e75d5-173">请参阅[视频：使用 "使用资源管理器打开" 复制或移动库文件](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e75d5-173">See [Video: Copy or move library files by using Open with Explorer](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx).</span></span>

- <span data-ttu-id="e75d5-174">若要转移列表数据，请保存[列表模板](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx)，并使用保存的模板在新网站上重新创建列表。</span><span class="sxs-lookup"><span data-stu-id="e75d5-174">To transfer list data, save a [list template](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx), and use the saved template to re-create the list on the new site.</span></span>

- <span data-ttu-id="e75d5-175">若要将文档库或列表内容从 SharePoint Online 环境（OneDrive for Business 或工作组网站）保存到文件共享或本地计算机，请参阅[有关手动迁移 Sharepoint online 内容的信息](https://support.microsoft.com/kb/2783484)。</span><span class="sxs-lookup"><span data-stu-id="e75d5-175">To save a document library or list content from a SharePoint Online environment (OneDrive for Business or team sites) to file shares or to a local computer, see [Information about manual migration of SharePoint Online content](https://support.microsoft.com/kb/2783484).</span></span>

## <a name="transfer-users-data-between-subscriptions"></a><span data-ttu-id="e75d5-176">在订阅之间传输用户数据</span><span class="sxs-lookup"><span data-stu-id="e75d5-176">Transfer users' data between subscriptions</span></span>

### <a name="email"></a><span data-ttu-id="e75d5-177">电子邮件：</span><span class="sxs-lookup"><span data-stu-id="e75d5-177">Email:</span></span>

<span data-ttu-id="e75d5-178">在设置新的订阅之后，要求用户[移动其电子邮件、联系人、任务和日历信息](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e75d5-178">Ask users to [move their email, contacts, tasks, and calendar information](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx) after you set up your new subscription.</span></span> <span data-ttu-id="e75d5-179">他们可以使用其初始用户名（如 sue@contoso.onmicrosoft.com）访问其旧的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e75d5-179">They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.</span></span>
  
### <a name="onedrive-for-business-data"></a><span data-ttu-id="e75d5-180">OneDrive For Business 数据：</span><span class="sxs-lookup"><span data-stu-id="e75d5-180">OneDrive For Business data:</span></span>

<span data-ttu-id="e75d5-181">请用户将 OneDrive for business 内容复制/同步[到其计算机](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)，然后将其添加回其新订阅。</span><span class="sxs-lookup"><span data-stu-id="e75d5-181">Ask users to Copy/Sync [OneDrive for Business content to their computer](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx), and then add it back to their new subscription.</span></span>