---
title: 在两个帐户之间手动传输数据
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 了解在更改计划或公司名称时如何在两个 Microsoft 365 帐户之间手动转移数据，或将多个订阅组合为一个。
ms.openlocfilehash: 6e64872ad7e145b63eb71d89ea2d69e5d8697eb6
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780165"
---
# <a name="transfer-data-manually-between-two-accounts"></a><span data-ttu-id="ff5a4-103">在两个帐户之间手动传输数据</span><span class="sxs-lookup"><span data-stu-id="ff5a4-103">Transfer data manually between two accounts</span></span>

<span data-ttu-id="ff5a4-104">准备汇总你的 sleeves，并在日历上阻止一段时间：在两个 Microsoft 365 帐户之间传输数据是一个手动、复杂且耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-104">Prepare to roll up your sleeves and block out a chunk of time on your calendar: transferring data between two Microsoft 365 accounts is a manual, complicated, and time-consuming process.</span></span> <span data-ttu-id="ff5a4-105">这不是自动或受支持的过程。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-105">This is not an automated or supported process.</span></span> <span data-ttu-id="ff5a4-106">我们将开始着手。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-106">We'll get you started.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ff5a4-107">在流程的过程中，Microsoft 365 上托管的电子邮件、Skype for Business 和公共网站将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-107">There will be down time during the process where email, Skype for Business and a public website hosted on Microsoft 365 won't work.</span></span> <span data-ttu-id="ff5a4-108">用户将获取新的用户名和密码，并将需要重置 Outlook。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-108">Users will get new user names and passwords, and they'll need to reset up Outlook.</span></span>

<span data-ttu-id="ff5a4-109">**如果应用了以下任一情况，则仅使用本主题中的说明手动传输数据：**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-109">**Only transfer data manually using the instructions in this topic if one of the following applies:**</span></span>
  
- <span data-ttu-id="ff5a4-110">您需要更改为其他服务系列中的计划。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-110">You need to change to a plan in a different service family.</span></span>

- <span data-ttu-id="ff5a4-111">您的公司名称已更改，并且您决定创建新的订阅并迁移数据，因为您要使用不同的初始域名称。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-111">Your company name changed, and you decided to create a new subscription and migrate your data because you want to use different initial domain names.</span></span>

- <span data-ttu-id="ff5a4-112">您需要将多个订阅合并为一个新的。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-112">You need to combine multiple subscriptions into one new one.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff5a4-113">如果您需要[更改订阅计划](../../commerce/subscriptions/switch-to-a-different-plan.md)并可以使用 "切换计划向导"，或者如果您需要转移到同一订阅系列中的新订阅计划，即使 "切换计划向导" 不起作用，您也不需要手动传输数据，并且没有停机时间。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-113">If you need to [change your subscription plan](../../commerce/subscriptions/switch-to-a-different-plan.md) and can use the Switch plans wizard, or if you need to transfer to a new subscription plan in the same subscription family even when the Switch plans wizard doesn't work, you don't need to manually transfer your data, and there is no down time.</span></span>

|<span data-ttu-id="ff5a4-114">**Tasks**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-114">**Tasks**</span></span>|<span data-ttu-id="ff5a4-115">**Steps**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-115">**Steps**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff5a4-116">购买要移到的计划。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-116">Purchase the plan you want to move to.</span></span>  <br/> |<span data-ttu-id="ff5a4-117">当你注册时，请在初始域名中指定要使用的公司名称： *yourcompany* 、 *yourcompany* -public.sharepoint.com 和*yourcompany* 。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-117">When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com.</span></span> <span data-ttu-id="ff5a4-118">您需要使用与为任何现有订阅所做的*yourcompany*不同的名称。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-118">You need to use a different  *yourcompany*  name than you did for any existing subscriptions.</span></span>  <br/> <span data-ttu-id="ff5a4-119">> [!NOTE]> 在取消订阅以释放从我们的系统中使用*yourcompany*的初始域名时，通常至少需要几个月。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-119">> [!NOTE]>  It typically takes a minimum of several months after cancelling a subscription to release the initial domain names that use  *yourcompany*  from our systems.</span></span> <span data-ttu-id="ff5a4-120">即使您计划保存旧 Microsoft 365 订阅中的所有数据，并取消该订阅，旧的*yourcompany*值也不会立即可用于新的订阅。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-120">Even if you plan to save all your data from your old Microsoft 365 subscription, and cancel that subscription, the old  *yourcompany*  value is not immediately available for use in a new subscription.</span></span>           |
|<span data-ttu-id="ff5a4-121">从旧 Microsoft 365 订阅中删除你的自定义域。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-121">Remove your custom domain from your old Microsoft 365 subscription.</span></span>  <br/> | <span data-ttu-id="ff5a4-122">在删除域以从用户电子邮件地址中删除域名并删除自定义域的电子邮件和 Lync 的 DNS 记录之前，请执行[所需的步骤](remove-a-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-122">Follow the [required steps before you remove a domain](remove-a-domain.md) to remove the domain name from user email addresses and remove DNS records for email and Lync for the custom domain.</span></span> <span data-ttu-id="ff5a4-123">如果你在 Microsoft 365 上托管你的公共网站，你还需要删除指向它的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-123">If you host your public website on Microsoft 365, you'll also need to remove the CNAME record that points to it.</span></span>  <br/> <span data-ttu-id="ff5a4-124">> [!IMPORTANT]> 删除了将电子邮件路由到此自定义域的 MX 记录后，电子邮件将停止工作，直到您向新帐户添加了域、设置新的 MX 记录并设置您的用户。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-124">> [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users.</span></span> <span data-ttu-id="ff5a4-125">当您删除 Lync 的 DNS 记录时，Lync 将停止工作。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-125">When you remove the DNS records for Lync, Lync will stop working.</span></span> <span data-ttu-id="ff5a4-126">删除指向公共网站的 CNAME 记录后，该记录将不可用。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-126">And after you remove the CNAME record that points to your public website, it will not be available.</span></span>           <span data-ttu-id="ff5a4-127">[删除域](remove-a-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-127">[Remove the domain](remove-a-domain.md) .</span></span>  <br/> |
|<span data-ttu-id="ff5a4-128">为新订阅设置自定义域，并设置您的用户。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-128">Set up your custom domain for your new subscription, and set up your users.</span></span>  <br/> | <span data-ttu-id="ff5a4-129">设置新的订阅，包括为自定义域创建所需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-129">Set up your new subscription, including creating the required DNS records for your custom domain.</span></span>  <br/>  <span data-ttu-id="ff5a4-130">创建您的用户并在自定义域上使用电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-130">Create your users, with email addresses on your custom domain.</span></span>  <br/> |
|<span data-ttu-id="ff5a4-131">将数据从旧订阅传输到新订阅。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-131">Transfer data from your old subscription to your new subscription.</span></span>  <br/> | <span data-ttu-id="ff5a4-132">在单独的浏览器窗口中登录两个帐户：</span><span class="sxs-lookup"><span data-stu-id="ff5a4-132">Sign in to both accounts in separate browser windows:</span></span>  <br/>  <span data-ttu-id="ff5a4-133">右键单击 "Internet Explorer" 图标，然后打开两个 "InPrivate 浏览器" 窗口。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-133">Right-click the Internet Explorer icon, and open two InPrivate browser windows.</span></span> <span data-ttu-id="ff5a4-134">您可以在两个窗口中使用不同的凭据登录这两个帐户。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-134">You can use different credentials in the two windows to sign in on both accounts.</span></span>  <br/> [<span data-ttu-id="ff5a4-135">在订阅之间传输管理设置</span><span class="sxs-lookup"><span data-stu-id="ff5a4-135">Transfer administrative settings between subscriptions</span></span>](#email) <br/> [<span data-ttu-id="ff5a4-136">传输团队网站结构和数据</span><span class="sxs-lookup"><span data-stu-id="ff5a4-136">Transfer team site structure and data</span></span>](#transfer-team-site-structure-and-data) <br/> [<span data-ttu-id="ff5a4-137">在订阅之间传输公共网站</span><span class="sxs-lookup"><span data-stu-id="ff5a4-137">Transfer a public website between subscriptions</span></span>](#transfer-a-public-website-between-subscriptions) <br/> [<span data-ttu-id="ff5a4-138">在订阅之间传输管理设置</span><span class="sxs-lookup"><span data-stu-id="ff5a4-138">Transfer administrative settings between subscriptions</span></span>](#email) <br/> |
|<span data-ttu-id="ff5a4-139">通过调用 microsoft Microsoft Microsoft 支持 for Microsoft 365，取消已完成计划的订阅。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-139">Cancel the subscription for the plan you're done with by calling Microsoft Support for Microsoft 365.</span></span>  <br/> | <span data-ttu-id="ff5a4-140">验证新订阅是否正常工作以及是否已传输所有数据。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-140">Verify that your new subscription is working and all data has been transferred.</span></span>  <br/>  <span data-ttu-id="ff5a4-141">[联系客户支持](../contact-support-for-business-products.md)以取消旧订阅。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-141">[Contact customer support](../contact-support-for-business-products.md) to cancel your old subscription.</span></span>  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a><span data-ttu-id="ff5a4-142">在订阅之间传输管理设置</span><span class="sxs-lookup"><span data-stu-id="ff5a4-142">Transfer administrative settings between subscriptions</span></span>

<span data-ttu-id="ff5a4-143">转到每个帐户上的以下页面，并根据旧帐户的设置设置新帐户。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-143">Go to the following pages on each account, and set up the new account based on the old account's settings.</span></span>
  
<span data-ttu-id="ff5a4-144">如果要将数据从 Microsoft 365 传输到 Microsoft 365 中型企业版或 Microsoft 365 企业版，则管理页面的结构各不相同。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-144">If you are transferring data from Microsoft 365 to Microsoft 365 Midsize Business or Microsoft 365 Enterprise, the admin pages are structured differently.</span></span> <span data-ttu-id="ff5a4-145">观看[视频：介绍 Microsoft 365 企业版](https://docs.microsoft.com/microsoft-365/admin/)，并转到以下位置以查看管理员设置。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-145">Watch a [Video: Introducing Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/), and go to the following places to look at admin settings.</span></span>
  
<span data-ttu-id="ff5a4-146">对于 Microsoft 365 企业版和 Microsoft 365 中型企业版：</span><span class="sxs-lookup"><span data-stu-id="ff5a4-146">For Microsoft 365 Enterprise and Microsoft 365 Midsize Business:</span></span>
  
|<span data-ttu-id="ff5a4-147">**位置**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-147">**Location**</span></span>|<span data-ttu-id="ff5a4-148">**用途**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-148">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff5a4-149">**管理员** \>**Microsoft 365** \>**服务设置**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-149">**Admin** \> **Microsoft 365** \> **Service settings**</span></span> <br/> |<span data-ttu-id="ff5a4-150">选择每个选项卡，以获取邮件、网站、Lync、用户软件、密码、社区、权限管理和移动的设置。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-150">Select each tab for settings for mail, sites, Lync, user software, passwords, community, rights management, and mobile.</span></span>  <br/> |
|<span data-ttu-id="ff5a4-151">**管理员** \>**Exchange**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-151">**Admin** \> **Exchange**</span></span> <br/> | <span data-ttu-id="ff5a4-152">Exchange Online 设置</span><span class="sxs-lookup"><span data-stu-id="ff5a4-152">Exchange Online settings</span></span>  <br/> |
|<span data-ttu-id="ff5a4-153">**管理员** \>**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-153">**Admin** \> **SharePoint**</span></span> <br/> | <span data-ttu-id="ff5a4-154">SharePoint Online 设置</span><span class="sxs-lookup"><span data-stu-id="ff5a4-154">SharePoint Online settings</span></span>  <br/> |
|<span data-ttu-id="ff5a4-155">**管理员** \>**Skype For business**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-155">**Admin** \> **Skype for Business**</span></span> <br/> |<span data-ttu-id="ff5a4-156">其他 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="ff5a4-156">Additional Skype for Business settings</span></span>  <br/> |

<span data-ttu-id="ff5a4-157">适用于 Microsoft 365 小型企业版</span><span class="sxs-lookup"><span data-stu-id="ff5a4-157">For Microsoft 365 Small Business</span></span>
  
|<span data-ttu-id="ff5a4-158">**位置**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-158">**Location**</span></span>|<span data-ttu-id="ff5a4-159">**用途**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-159">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff5a4-160">**管理员** \>**管理组织范围的设置**</span><span class="sxs-lookup"><span data-stu-id="ff5a4-160">**Admin** \> **Manage organization-wide settings**</span></span> <br/> |<span data-ttu-id="ff5a4-161">管理设置</span><span class="sxs-lookup"><span data-stu-id="ff5a4-161">Administrative settings</span></span>  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a><span data-ttu-id="ff5a4-162">在订阅之间传输公共网站</span><span class="sxs-lookup"><span data-stu-id="ff5a4-162">Transfer a public website between subscriptions</span></span>

<span data-ttu-id="ff5a4-163">如果在 Microsoft 365 上托管了一个公共网站，则需要将其保存并在新订阅上重新创建它。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-163">If you have a public website hosted on Microsoft 365, you need to save it and re-create it on your new subscription.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff5a4-164">如果您的公共网站托管在 DNS 托管提供商处，则不需要进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-164">If your public website is hosted at a DNS hosting provider, no changes are required.</span></span> <span data-ttu-id="ff5a4-165">您的转换不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-165">It will not be affected by your transition.</span></span>
  
<span data-ttu-id="ff5a4-166">若要将文档库或列表内容从 SharePoint Online 环境保存到文件共享或本地计算机，请参阅[SharePoint online 内容的手动迁移](https://go.microsoft.com/fwlink/p/?LinkId=402910)。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-166">To save a document library or list content from a SharePoint Online environment to file shares or to a local computer, see [Manual migration of SharePoint Online content](https://go.microsoft.com/fwlink/p/?LinkId=402910).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff5a4-167">公共网站迁移应用无法将数据传输到其他订阅。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-167">The Public site migration app can't transfer data to a different subscription.</span></span>
  
## <a name="transfer-team-site-structure-and-data"></a><span data-ttu-id="ff5a4-168">传输团队网站结构和数据</span><span class="sxs-lookup"><span data-stu-id="ff5a4-168">Transfer team site structure and data</span></span>

<span data-ttu-id="ff5a4-169">有几种方法可以保存或传输团队网站数据：</span><span class="sxs-lookup"><span data-stu-id="ff5a4-169">There are several ways to save or transfer team site data:</span></span>
  
- <span data-ttu-id="ff5a4-170">您可以将旧网站另存为模板，并将该模板导入到新网站。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-170">You can save the old site as a template and import the template into the new site.</span></span>

- <span data-ttu-id="ff5a4-171">若要传输文档，请首先手动在新网站上重新创建层次结构。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-171">To transfer documents, first manually recreate your hierarchy on the new site.</span></span> <span data-ttu-id="ff5a4-172">然后，您可以同时打开这两个 SharePoint 团队网站，同时使用 Windows 资源管理器打开文档库，并复制并粘贴文档。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-172">Then you can open both SharePoint team sites at the same time, open both document libraries with Windows Explorer, and copy and paste the documents.</span></span> <span data-ttu-id="ff5a4-173">请参阅[视频：使用 "使用资源管理器打开" 复制或移动库文件](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-173">See [Video: Copy or move library files by using Open with Explorer](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).</span></span>

- <span data-ttu-id="ff5a4-174">若要转移列表数据，请保存[列表模板](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)，并使用保存的模板在新网站上重新创建列表。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-174">To transfer list data, save a [list template](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393), and use the saved template to re-create the list on the new site.</span></span>

- <span data-ttu-id="ff5a4-175">若要将文档库或列表内容从 SharePoint Online 环境（OneDrive for Business 或工作组网站）保存到文件共享或本地计算机，请参阅[有关手动迁移 Sharepoint online 内容的信息](https://support.microsoft.com/kb/2783484)。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-175">To save a document library or list content from a SharePoint Online environment (OneDrive for Business or team sites) to file shares or to a local computer, see [Information about manual migration of SharePoint Online content](https://support.microsoft.com/kb/2783484).</span></span>

## <a name="transfer-users-data-between-subscriptions"></a><span data-ttu-id="ff5a4-176">在订阅之间传输用户数据</span><span class="sxs-lookup"><span data-stu-id="ff5a4-176">Transfer users' data between subscriptions</span></span>

### <a name="email"></a><span data-ttu-id="ff5a4-177">电子邮件：</span><span class="sxs-lookup"><span data-stu-id="ff5a4-177">Email:</span></span>

<span data-ttu-id="ff5a4-178">在设置新的订阅之后，要求用户[移动其电子邮件、联系人、任务和日历信息](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc)。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-178">Ask users to [move their email, contacts, tasks, and calendar information](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) after you set up your new subscription.</span></span> <span data-ttu-id="ff5a4-179">他们可以使用其初始用户名（如 sue@contoso.onmicrosoft.com）访问其旧的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-179">They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.</span></span>
  
### <a name="onedrive-for-business-data"></a><span data-ttu-id="ff5a4-180">OneDrive For Business 数据：</span><span class="sxs-lookup"><span data-stu-id="ff5a4-180">OneDrive For Business data:</span></span>

<span data-ttu-id="ff5a4-181">请用户将 OneDrive for business 内容复制/同步[到其计算机](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)，然后将其添加回其新订阅。</span><span class="sxs-lookup"><span data-stu-id="ff5a4-181">Ask users to Copy/Sync [OneDrive for Business content to their computer](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd), and then add it back to their new subscription.</span></span>
