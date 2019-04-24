---
title: 针对 GDPR 的 Visual Studio 系列数据主体请求
description: 针对 GDPR 的 Visual Studio 系列数据主体请求
keywords: Visual Studio, Visual Studio Code, Visual Studio for Mac, Visual Studio 文档, 隐私, GDPR
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: PoulChapman
ms.author: olholder
manager: pchapman
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 5b07cefa4a850d5de7c858f180c8f7688fd0a6d7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286920"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="004af-104">针对 GDPR 的 Visual Studio 系列数据主体请求</span><span class="sxs-lookup"><span data-stu-id="004af-104">Visual Studio Family Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="004af-p101">根据欧盟[一般数据保护条例 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)，用户（在条例中称为_数据主体_）有权管理其个人数据。根据 GDPR，个人数据的定义非常广泛，包括与身份已识别或可识别的自然人相关的任何数据。根据 GDPR，数据主体有权对自己的个人数据执行以下操作：获取个人数据副本、请求更正个人数据、限制个人数据处理、删除个人数据或接受电子格式的个人数据。数据主体为了对自己的个人数据执行操作而向数据控制者（雇主或有权控制个人数据的其他类型的机构或组织）发出的正式请求称为_数据主体请求_或 DSR。有关 GDPR 的 一般信息，请参阅[服务信任门户的 GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) 部分。</span><span class="sxs-lookup"><span data-stu-id="004af-p101">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as _data subjects_) to manage their personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format. A formal request by a data subject to a data controller (an employer or other type of agency or organization that has control over personal data) to take an action on that data subject's personal data is called a _data subject request_ or DSR. For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

## <a name="products-covered-by-this-guide"></a><span data-ttu-id="004af-110">本指南涵盖的产品</span><span class="sxs-lookup"><span data-stu-id="004af-110">Products covered by this guide</span></span>

<span data-ttu-id="004af-p102">本指南介绍如何使用 Microsoft 工具来导出或删除经过身份验证的（已登录）会话在使用 Visual Studio 和 Visual Studio for Mac 以及针对它们和 Visual Studio Code 的 Microsoft 扩展过程中所收集的个人数据。本指南还介绍如何对使用 Visual Studio 开发人员社区、NuGet.org 和 ASP.NET 网站时所收集的个人数据提出数据主体请求。这些产品可能允许使用非 Microsoft 工具和扩展，Microsoft 不是这些工具和扩展的数据处理者或控制者。用户应联系工具或扩展提供商，以了解针对这些工具和扩展的个人数据和收集策略。</span><span class="sxs-lookup"><span data-stu-id="004af-p102">This guide discusses how to use Microsoft tools to export or delete personal data collected during authenticated (signed-in) session usage of Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. This guide also covers how to make data subject requests for personal data collected when using Visual Studio Developer Community, NuGet.org, and the ASP.NET website. These products may enable use of non-Microsoft tools and extensions, and Microsoft is not a data processor or controller for these tools and extensions. Users should contact the tool or extension provider to understand the personal data and collection policies for these tools and extensions.</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="004af-115">其他隐私信息</span><span class="sxs-lookup"><span data-stu-id="004af-115">Additional privacy information</span></span>

<span data-ttu-id="004af-116">产品附带的 Microsoft 软件许可条款，[Microsoft 隐私声明](https://go.microsoft.com/fwlink/?LinkId=660726)和 [Microsoft 有关 GDPR 的义务](https://docs.microsoft.com/legal/gdpr)介绍了我们的数据处理做法。</span><span class="sxs-lookup"><span data-stu-id="004af-116">The Microsoft Software License Terms accompanying the products, the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=660726), and [Microsoft's GDPR Commitments](https://docs.microsoft.com/legal/gdpr) describe our data processing practices.</span></span>

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a><span data-ttu-id="004af-117">Visual Studio, Visual Studio for Mac 和 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="004af-117">Visual Studio, Visual Studio for Mac, and Visual Studio Code</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="004af-118">我们收集的个人数据</span><span class="sxs-lookup"><span data-stu-id="004af-118">Personal data we collect</span></span>

<span data-ttu-id="004af-p103">根据 GDPR，Microsoft 作为数据处理者 从用户那里收集我们所需的数据，在提供对 Visual Studio 和 Visual Studio for Mac，以及对它们和 Visual Studio Code 的 Microsoft 扩展的使用体验的同时，提升使用体验。数据分为两类：客户数据和系统生成的日志。客户数据包括这些产品执行其提供的服务时所需的用户可识别事务和交互数据。例如，为了向用户提供漫游设置等个性化体验，我们需要收集用户帐户信息和设置数据。系统生成的日志是用于帮助标识和排查问题并改进我们的产品和服务的使用情况数据或诊断数据，可能也包含有关最终用户的可识别信息（例如，用户名）。系统生成的日志的保留期不超过 18 个月。例如，针对产品每天的使用情况聚合系统生成的日志，并包含使用日期、使用的产品（例如，“Visual Studio 2017”）、执行的操作（例如，“vs/core/packagecostsummary/solutionload”）以及执行操作的次数，如此示例中所示：</span><span class="sxs-lookup"><span data-stu-id="004af-p103">As a data processor under the GDPR, Microsoft collects the data we need from users to provide experiences for and improve Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. There are two categories of data: customer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that these products need to perform the service they provide. For example, to provide users with personalized experiences such as roaming settings, we need to collect user account information and settings data. System-generated logs are usage or diagnostic data that are used to help identify and troubleshoot problems and improve our products and services, and may also contain identifiable information about end users, such as a user name. System-generated logs are retained for no more than 18 months. As an example, system-generated logs are aggregated for each day of product usage and include the usage date, the product used (for example, "Visual Studio 2017"), the action you took (for example, "vs/core/packagecostsummary/solutionload"), and the number of times the action was taken, as shown in this sample:</span></span>

```
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

<span data-ttu-id="004af-126">有关详细信息，请参阅[由 Visual Studio 收集的系统生成的日志](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection)。</span><span class="sxs-lookup"><span data-stu-id="004af-126">For more information, see [System-generated logs collected by Visual Studio](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection).</span></span>

<span data-ttu-id="004af-p104">DSR 只能对附加到经过身份验证的标识的个人数据提供服务。例如，由于 Visual Studio Code 不支持登录，因此，来自 Visual Studio Code 的系统生成的日志无法被附加到经过身份验证的标识，所以无法对其提供服务。但是，针对 Visual Studio Code 的某些 Microsoft 扩展可提供经过身份验证的数据，DSR 可对此数据提供服务。有关详细信息，请参阅 [GPDR 和 Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code)。一般情况下，我们不存储 Visual Studio 2013 和更早版本的数据；但是，某些扩展和组件可能提供附加到经过身份验证的标识的数据，DSR 可对其提供服务，如下所述。</span><span class="sxs-lookup"><span data-stu-id="004af-p104">Only personal data that is attached to authenticated identities can be serviced by a DSR. So, for example, because Visual Studio Code does not support sign-in, system-generated logs from it are not attached to an authenticated identity and cannot be serviced. However, some Microsoft extensions for Visual Studio Code may provide authenticated data, and this data can be serviced by a DSR. For more information, see [GDPR and Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). In general, we do not store data for Visual Studio 2013 and earlier; however, certain extensions and components may provide data attached to authenticated identities and can be serviced by a DSR as outlined below.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="004af-132">用户如何控制个人数据</span><span class="sxs-lookup"><span data-stu-id="004af-132">How users can control personal data</span></span>

<span data-ttu-id="004af-133">Visual Studio 2015 及更高版本、Visual Studio for Mac 和 Visual Studio Code 为用户提供了以下方法来停止数据收集，并为作为控制者的你提供了导出或删除已被收集的数据的方法。</span><span class="sxs-lookup"><span data-stu-id="004af-133">Visual Studio 2015 and later, Visual Studio for Mac, and Visual Studio Code provide the following means for your users to stop data collection, and for you as controller to export, or delete data that has already been gathered.</span></span>

#### <a name="in-app-settings"></a><span data-ttu-id="004af-134">应用内设置</span><span class="sxs-lookup"><span data-stu-id="004af-134">In-app settings</span></span>

<span data-ttu-id="004af-p105">用户可以控制这些产品的隐私设置。有关详细信息，请参阅以下内容</span><span class="sxs-lookup"><span data-stu-id="004af-p105">Users can control the privacy settings for these products. For more information, see the following</span></span>

- <span data-ttu-id="004af-137">[如何在 Visual Studio 中管理隐私设置](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program)。</span><span class="sxs-lookup"><span data-stu-id="004af-137">[How to manage privacy settings in Visual Studio](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="004af-138">[如何在 Visual Studio for Mac 中管理隐私设置](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program)。</span><span class="sxs-lookup"><span data-stu-id="004af-138">[How to manage privacy settings in Visual Studio for Mac](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="004af-139">[如何在 Visual Studio Code 中禁用遥测报告](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)。</span><span class="sxs-lookup"><span data-stu-id="004af-139">[How to disable telemetry reporting in Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).</span></span>

#### <a name="exporting-or-deleting-data"></a><span data-ttu-id="004af-140">导出或删除数据</span><span class="sxs-lookup"><span data-stu-id="004af-140">Exporting or deleting data</span></span>

<span data-ttu-id="004af-p106">控制者可以使用两种方法中的任意一种来管理客户数据以及从其数据主体收集的系统生成的日志，具体取决于其 Visual Studio 系列产品或 Microsoft 扩展注册的方式。在某些情况下，必须同时使用这两种方法。两者都允许控制者下载由该方法管理的活动历史记录的副本。关闭 AAD 或 MSA 帐户将删除相关联的 Visual Studio 客户数据，并对系统生成的日志中与这些产品相关的个人可识别数据匿名处理。匿名处理的系统生成的日志的保留期限不超过 18 个月。</span><span class="sxs-lookup"><span data-stu-id="004af-p106">Controllers can manage customer data and system-generated logs collected from their data subjects by one of two methods, depending upon how their Visual Studio Family product or Microsoft extensions were registered. In some cases, both methods must be used. Both methods allow Controllers to download a copy of their activity history managed by that method. Closure of an AAD or MSA account deletes associated Visual Studio customer data, and anonymizes personally identifiable data in system-generated logs pertaining to these products. Anonymized system-generated logs are retained for no more than 18 months.</span></span>

- <span data-ttu-id="004af-146">使用由 Azure 租户支持的帐户（例如，AAD 帐户或与 Azure 订阅关联的 MSA 帐户）注册 Visual Studio 系列产品的用户可以按照[针对 GDPR 的 Azure 数据主体请求](gdpr-dsr-azure.md)中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="004af-146">Users that have registered a Visual Studio Family product by using an account that is backed by an Azure tenant&mdash;for example, AAD account or  MSA account associated with an Azure subscription&mdash;can follow the instructions in [Azure Data Subject Requests for the GDPR](gdpr-dsr-azure.md).</span></span>
- <span data-ttu-id="004af-p107">未使用由 Azure 租户支持的帐户（例如，使用 Microsoft 帐户 (MSA) 的许多帐户）注册 Visual Studio 系列产品的用户可以使用其 Microsoft 帐户提供的[基于 Web 的 Microsoft 隐私响应中心](https://aka.ms/userprivacysite)跨多个 Microsoft 服务来查看、控制和删除绑定到他们的 Microsoft 帐户的活动数据。在此应用场景中，用户是自己个人数据的控制者。</span><span class="sxs-lookup"><span data-stu-id="004af-p107">Users that have registered a Visual Studio Family product without an account that is backed by an Azure tenant&mdash;for example many accounts using a Microsoft Account (MSA)&mdash;can use [the web-based Microsoft Privacy Response Center](https://aka.ms/userprivacysite) available through their Microsoft account to view, control, and delete activity data tied to their Microsoft account across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

> [!NOTE]
> <span data-ttu-id="004af-149">当 MSA 帐户持有者删除其帐户时，所有与这些产品相关的个人可识别数据都将被删除（无论该帐户是否受 Azure 租户支持），并且将对系统生成的日志匿名处理。</span><span class="sxs-lookup"><span data-stu-id="004af-149">When an MSA account holder deletes their account, all their personally identifiable data pertaining to these products is deleted, whether the account is backed by an Azure tenant or not, and system-generated logs are anonymized.</span></span>

<span data-ttu-id="004af-p108">对于 Visual Studio 2013，我们收集的数据将经过匿名处理。对于 Visual Studio 2012 和之前的版本，我们将在收到请求后立即删除数据。在这两种情况下，在以后都没有查看、导出或删除的内容。</span><span class="sxs-lookup"><span data-stu-id="004af-p108">For Visual Studio 2013, the data we collect is anonymized. For Visual Studio 2012 and prior releases, we immediately delete the data upon receipt. In both cases, there is nothing to view, export, or delete at a later time.</span></span>

## <a name="visual-studio-developer-community"></a><span data-ttu-id="004af-153">Visual Studio 开发人员社区</span><span class="sxs-lookup"><span data-stu-id="004af-153">Visual Studio Developer Community</span></span>

<span data-ttu-id="004af-p109">我们支持通过[开发人员社区](https://developercommunity.visualstudio.com)网站提交的[一般数据保护条例 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 请求。用户可以查看、导出或删除自己的反馈数据。</span><span class="sxs-lookup"><span data-stu-id="004af-p109">We support [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) requests through the [Developer Community](https://developercommunity.visualstudio.com) website. You can View, Export, or Delete your feedback data.</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="004af-156">我们收集的个人数据</span><span class="sxs-lookup"><span data-stu-id="004af-156">Personal data we collect</span></span>

<span data-ttu-id="004af-p110">Microsoft 收集数据，帮助我们重现和排查你报告的 Visual Studio 系列产品中的问题。此数据包括个人数据和公共反馈。个人数据包括：</span><span class="sxs-lookup"><span data-stu-id="004af-p110">Microsoft collects data to help us reproduce and troubleshoot issues you report with Visual Studio Family products. This data includes personal data and public feedback. Personal data includes:</span></span>

- <span data-ttu-id="004af-160">你的[开发人员社区](https://developercommunity.visualstudio.com)个人资料信息；</span><span class="sxs-lookup"><span data-stu-id="004af-160">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="004af-161">首选项和通知；</span><span class="sxs-lookup"><span data-stu-id="004af-161">Preferences and notifications;</span></span>
- <span data-ttu-id="004af-162">通过[报告 Visual Studio 中的问题](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或通过[开发人员社区](https://developercommunity.visualstudio.com)提供的附件和系统生成的日志；</span><span class="sxs-lookup"><span data-stu-id="004af-162">Attachments and system-generated logs you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com);</span></span>
- <span data-ttu-id="004af-163">你的投票。</span><span class="sxs-lookup"><span data-stu-id="004af-163">Your votes.</span></span>

<span data-ttu-id="004af-164">公共反馈包括：报告的问题、评论和解决方案。</span><span class="sxs-lookup"><span data-stu-id="004af-164">Public feedback includes: reported problems, comments, and solutions.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="004af-165">用户如何控制个人数据</span><span class="sxs-lookup"><span data-stu-id="004af-165">How users can control personal data</span></span>

#### <a name="view"></a><span data-ttu-id="004af-166">查看</span><span class="sxs-lookup"><span data-stu-id="004af-166">View</span></span>

<span data-ttu-id="004af-167">若要查看与你的反馈相关的数据，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="004af-167">To View your feedback-related data, follow these steps:</span></span>

1. <span data-ttu-id="004af-168">登录到[开发人员社区](https://developercommunity.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="004af-168">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="004af-169">在右上角，单击个人资料并选择“个人资料和首选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="004af-169">Sign into Developer Community. From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="004af-170">单击任何“个人资料”\*\*\*\*、“通知”\*\*\*\*、“活动”\*\*\*\* 和“附件”\*\*\*\* 选项卡，查看提交到反馈系统的数据。</span><span class="sxs-lookup"><span data-stu-id="004af-170">Click on any of the **Profile**, **Notifications**, **Activity**, and **Attachments** tabs to view the data submitted to the feedback systems.</span></span>
   1. <span data-ttu-id="004af-171">“个人资料”\*\*\*\* 指的是你的[开发人员社区](https://developercommunity.visualstudio.com)个人资料，包括用户名、电子邮件地址、个人相关信息等。</span><span class="sxs-lookup"><span data-stu-id="004af-171">**Profile** refers to your [Developer Community](https://developercommunity.visualstudio.com) profile, including user name, email address, about, etc.</span></span>
   2. <span data-ttu-id="004af-172">“通知”\*\*\*\* 是你控制接收电子邮件通知的方式。</span><span class="sxs-lookup"><span data-stu-id="004af-172">**Notifications** is how you control the email notifications you receive.</span></span>
   3. <span data-ttu-id="004af-173">“活动”\*\*\*\* 将为你提供你曾活跃的反馈项（发表的帖子、评论等）和执行的活动。</span><span class="sxs-lookup"><span data-stu-id="004af-173">**Activity** will give you the feedback items you have been active on (posted, commented, etc.), and the activities performed.</span></span>
   4. <span data-ttu-id="004af-174">“附件”\*\*\*\* 是你的附件历史记录的列表，格式如下：`FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`</span><span class="sxs-lookup"><span data-stu-id="004af-174">**Attachments** is a list of your attachment history in a format like `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`.</span></span>

#### <a name="export"></a><span data-ttu-id="004af-175">导出</span><span class="sxs-lookup"><span data-stu-id="004af-175">Export</span></span>

<span data-ttu-id="004af-p112">可以将反馈数据作为 DSR 的一部分导出，我们将创建一个或多个 .zip 存档，它将包括：</span><span class="sxs-lookup"><span data-stu-id="004af-p112">You can export your feedback data as part of DSR. We will create one or more .zip archives that will include:</span></span>

- <span data-ttu-id="004af-178">你的[开发人员社区](https://developercommunity.visualstudio.com)个人资料信息；</span><span class="sxs-lookup"><span data-stu-id="004af-178">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="004af-179">首选项和通知设置；</span><span class="sxs-lookup"><span data-stu-id="004af-179">Preferences and notification settings;</span></span>
- <span data-ttu-id="004af-180">通过[报告 Visual Studio 中的问题](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或通过[开发人员社区](https://developercommunity.visualstudio.com)提供的附件。</span><span class="sxs-lookup"><span data-stu-id="004af-180">Attachments you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>

> [!NOTE]
> <span data-ttu-id="004af-181">我们将从你的存档中排除你提供的以下公共反馈：评论、解决方案、报告的问题。</span><span class="sxs-lookup"><span data-stu-id="004af-181">We will exclude the following public feedback you have provided from your archive: comments, solutions, reported problems.</span></span>

<span data-ttu-id="004af-182">若要开始导出，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="004af-182">To start an Export, follow these steps:</span></span>

1. <span data-ttu-id="004af-183">登录到[开发人员社区](https://developercommunity.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="004af-183">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="004af-184">在右上角，单击个人资料并选择“个人资料和首选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="004af-184">Sign into Developer Community. From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="004af-185">单击“隐私”\*\*\*\* 选项卡，然后单击“创建存档”\*\*\*\*，请求导出数据。</span><span class="sxs-lookup"><span data-stu-id="004af-185">Click the **Privacy** tab, and then click **Create an archive** to request exporting your data.</span></span>
3. <span data-ttu-id="004af-p114">“存档状态”\*\*\*\* 将更新，显示我们正在准备数据。准备数据的时间取决于我们需要导出的数据量。</span><span class="sxs-lookup"><span data-stu-id="004af-p114">The **Archive Status** will update to show that we are preparing the data. The length of time before the data is available depends on the amount of data we need to export.</span></span>
4. <span data-ttu-id="004af-188">数据准备就绪后，我们会向你发送一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="004af-188">Once the data is ready, we will send you an email.</span></span>
5. <span data-ttu-id="004af-189">单击电子邮件中的“下载存档”\*\*\*\*，或返回到“隐私”选项卡以下载数据。</span><span class="sxs-lookup"><span data-stu-id="004af-189">Click **Download Archive** in the email, or go back to the Privacy tab to download your data.</span></span>

> [!NOTE]
> - <span data-ttu-id="004af-190">如果你在“通知”选项卡中选择了不接收通知，我们将不会发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="004af-190">We will not send email if you chose not to receive notifications in the Notifications tab.</span></span>
> - <span data-ttu-id="004af-191">如果请求重新导出，我们将删除旧存档，并创建新存档。</span><span class="sxs-lookup"><span data-stu-id="004af-191">If you request Export again, we will remove your old archive and create a new one.</span></span>

#### <a name="delete"></a><span data-ttu-id="004af-192">删除</span><span class="sxs-lookup"><span data-stu-id="004af-192">Delete</span></span>

<span data-ttu-id="004af-193">删除操作将从[开发人员社区](https://developercommunity.visualstudio.com)中删除与你相关的以下信息：</span><span class="sxs-lookup"><span data-stu-id="004af-193">Deleting will remove the following information about you from [Developer Community](https://developercommunity.visualstudio.com):</span></span>

- <span data-ttu-id="004af-194">个人资料信息；</span><span class="sxs-lookup"><span data-stu-id="004af-194">Profile information;</span></span>
- <span data-ttu-id="004af-195">首选项和通知设置；</span><span class="sxs-lookup"><span data-stu-id="004af-195">Preferences and notification settings;</span></span>
- <span data-ttu-id="004af-196">通过[报告 Visual Studio 中的问题](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或通过[开发人员社区](https://developercommunity.visualstudio.com)提供的附件。</span><span class="sxs-lookup"><span data-stu-id="004af-196">Attachments you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>
- <span data-ttu-id="004af-197">你的投票</span><span class="sxs-lookup"><span data-stu-id="004af-197">Your votes</span></span>

> [!NOTE]
> <span data-ttu-id="004af-198">我们不会删除以下公共信息，但会对其进行匿名处理：你的评论、你的解决方案以及你报告的问题。</span><span class="sxs-lookup"><span data-stu-id="004af-198">We will not delete, but will anonymize, the following public information: your comments, your solutions, problems that you reported.</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="004af-199">删除 AAD 或 MSA 帐户将会触发[开发人员社区](https://developercommunity.visualstudio.com)的删除过程。</span><span class="sxs-lookup"><span data-stu-id="004af-199">Delete of an AAD or MSA account triggers the Delete process for [Developer Community](https://developercommunity.visualstudio.com).</span></span>

<span data-ttu-id="004af-200">若要启动删除操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="004af-200">To initiate a Delete, follow these steps:</span></span>

1. <span data-ttu-id="004af-p115">登录到[开发人员社区](https://developercommunity.visualstudio.com)。在右上角，单击个人资料并选择“个人资料和首选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="004af-p115">Sign into [Developer Community](https://developercommunity.visualstudio.com). From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="004af-203">单击“隐私”\*\*\*\* 选项卡，然后单击“删除数据和帐户”\*\*\*\* 开始删除你的数据。</span><span class="sxs-lookup"><span data-stu-id="004af-203">Click the **Privacy** tab, and then click **Delete your data and account** to start deleting your data.</span></span>
3. <span data-ttu-id="004af-204">将显示确认屏幕。</span><span class="sxs-lookup"><span data-stu-id="004af-204">A confirmation screen will appear.</span></span>
4. <span data-ttu-id="004af-205">在框中键入“delete”，然后单击“删除我的帐户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="004af-205">Type "delete" in the box, and then click **Delete my account**.</span></span>

<span data-ttu-id="004af-206">单击“删除我的帐户:”\*\*\*\* 后，</span><span class="sxs-lookup"><span data-stu-id="004af-206">Once you click **Delete my account:**</span></span>

- <span data-ttu-id="004af-207">你的帐户将注销。</span><span class="sxs-lookup"><span data-stu-id="004af-207">We will sign you out.</span></span>
- <span data-ttu-id="004af-208">我们将删除你的[开发人员社区](https://developercommunity.visualstudio.com)帐户、你的个人数据以及附件。</span><span class="sxs-lookup"><span data-stu-id="004af-208">We will delete your [Developer Community](https://developercommunity.visualstudio.com) account, your personal data, and attachments.</span></span>
- <span data-ttu-id="004af-p116">我们将对你的公共反馈进行匿名处理。你的公共反馈仍会在开发人员社区显示，但会指示此反馈是由匿名用户报告的。</span><span class="sxs-lookup"><span data-stu-id="004af-p116">We will anonymize your public feedback. Your public feedback will remain available on Developer Community, and will be indicated as reported by an Anonymous user.</span></span>
- <span data-ttu-id="004af-211">在删除你的帐户后，我们不会向你发送电子邮件，因为你已不再存在于系统中。</span><span class="sxs-lookup"><span data-stu-id="004af-211">We won't email you after we delete your account, because you will no longer be present in the system.</span></span>
- <span data-ttu-id="004af-212">如果报告新问题或登录到[开发人员社区](https://developercommunity.visualstudio.com)，你将被标识为新用户。</span><span class="sxs-lookup"><span data-stu-id="004af-212">If you report a new problem or log into [Developer Community](https://developercommunity.visualstudio.com), you will be identified as a new user.</span></span>
- <span data-ttu-id="004af-213">如果你将自己的帐户从[开发人员社区](https://developercommunity.visualstudio.com)中删除，我们将不会从其他 Microsoft 服务中删除该帐户。</span><span class="sxs-lookup"><span data-stu-id="004af-213">If you delete your account from [Developer Community](https://developercommunity.visualstudio.com), we will not delete it from other Microsoft services.</span></span>

## <a name="xamarin-forums-and-bugzilla"></a><span data-ttu-id="004af-214">Xamarin 论坛和 Bugzilla</span><span class="sxs-lookup"><span data-stu-id="004af-214">Xamarin Forums and Bugzilla</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="004af-215">我们收集的个人数据</span><span class="sxs-lookup"><span data-stu-id="004af-215">Personal Data We Collect</span></span>

<span data-ttu-id="004af-p117">Microsoft 通过 [Xamarin 论坛](https://forums.xamarin.com)用户社区和 [Xamarin Bugzilla](https://bugzilla.xamarin.com/) bug 报告网站收集你提供的数据，帮助我们重现和排查你在使用 Microsoft 产品和服务时可能遇到的问题。此数据包括个人数据和公共反馈。我们收集的个人数据是用户帐户数据（例如，与你的 Xamarin 论坛或 Bugzilla 帐户相关联的用户名和电子邮件地址），我们收集的公共反馈包括你通过 Xamarin 论坛或 Xamarin Bugzilla bug 报告网站所提供的 bug、问题、评论和解决方案。</span><span class="sxs-lookup"><span data-stu-id="004af-p117">Through the [Xamarin Forums](https://forums.xamarin.com) user community and [Xamarin Bugzilla](https://bugzilla.xamarin.com/) bug reporting websites, Microsoft collects data you provide to help us reproduce and troubleshoot issues you may have with Microsoft products and services. This data includes personal data and public feedback. The personal data we collect is user account data (for example, user names and email addresses associated with your Xamarin Forums or Bugzilla accounts), and the public feedback we collect includes bugs, problems, comments, and solutions you provide via the Xamarin Forums or Xamarin Bugzilla bug reporting website.</span></span>

### <a name="how-you-can-control-your-data"></a><span data-ttu-id="004af-219">如何控制数据</span><span class="sxs-lookup"><span data-stu-id="004af-219">How You Can Control Your Data</span></span>

#### <a name="xamarin-forums"></a><span data-ttu-id="004af-220">Xamarin 论坛</span><span class="sxs-lookup"><span data-stu-id="004af-220">Xamarin Forums</span></span>

##### <a name="view"></a><span data-ttu-id="004af-221">查看</span><span class="sxs-lookup"><span data-stu-id="004af-221">View</span></span>

<span data-ttu-id="004af-p118">具有 Xamarin 论坛活动帐户的用户可以从其 Xamarin 论坛帐户页查看个人数据和公共反馈（例如，发布的所有主题和帖子）。用户还可以通过帐户页面来编辑个人数据。</span><span class="sxs-lookup"><span data-stu-id="004af-p118">Users with active Xamarin Forums accounts may view their personal data and public feedback (for example, all of their posted threads and posts) from their Xamarin Forums account page. Users may also edit their personal data through their account page.</span></span>

##### <a name="export"></a><span data-ttu-id="004af-224">导出</span><span class="sxs-lookup"><span data-stu-id="004af-224">Export</span></span>

<span data-ttu-id="004af-p119">Xamarin 论坛由第三方 Vanilla 论坛托管。若要请求导出你的公共数据，应联系 forums@xamarin.com（由 Xamarin 团队监控）。我们将直接与 Vanilla 论坛协同处理此请求。</span><span class="sxs-lookup"><span data-stu-id="004af-p119">Xamarin Forums are hosted by a third party, Vanilla Forums. To request export of your public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then work directly with Vanilla Forums to process this request.</span></span>

##### <a name="delete"></a><span data-ttu-id="004af-228">Delete</span><span class="sxs-lookup"><span data-stu-id="004af-228">Delete</span></span>

<span data-ttu-id="004af-p120">Xamarin 论坛由第三方 Vanilla 论坛托管。若要请求删除你的个人数据和公共数据，请联系 forums@xamarin.com（由 Xamarin 团队监控）。然后，我们将根据用户请求手动删除个人数据。</span><span class="sxs-lookup"><span data-stu-id="004af-p120">Xamarin Forums are hosted by a third party, Vanilla Forums. To request deletion of your personal and public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then manually service the user's personal data deletion request.</span></span>

#### <a name="bugzilla-for-xamarin"></a><span data-ttu-id="004af-232">Xamarin 的 Bugzilla</span><span class="sxs-lookup"><span data-stu-id="004af-232">Bugzilla for Xamarin</span></span>

##### <a name="view"></a><span data-ttu-id="004af-233">查看</span><span class="sxs-lookup"><span data-stu-id="004af-233">View</span></span>

<span data-ttu-id="004af-234">具有 Xamarin Bugzilla 活动帐户的用户可以查看他们已报告的所有 bug，以及他们向 bug 添加的所有注释，方法是单击 Xamarin Bugzilla 主页上相应的链接。</span><span class="sxs-lookup"><span data-stu-id="004af-234">Users with active Xamarin Bugzilla accounts can view all bugs they've reported and all comments they've added to bugs by clicking the appropriate links on the Xamarin Bugzilla home page.</span></span>

##### <a name="export"></a><span data-ttu-id="004af-235">导出</span><span class="sxs-lookup"><span data-stu-id="004af-235">Export</span></span>

<span data-ttu-id="004af-236">不支持导出个人数据。</span><span class="sxs-lookup"><span data-stu-id="004af-236">Exporting of personal data is not supported.</span></span>

##### <a name="delete"></a><span data-ttu-id="004af-237">删除</span><span class="sxs-lookup"><span data-stu-id="004af-237">Delete</span></span>

<span data-ttu-id="004af-p121">若要请求删除 Xamarin 的 Bugzilla bug 报告网站中所使用的个人数据，用户可以关闭其 Xamarin Bugzilla 帐户，方法是导航到[用户首选项页](https://bugzilla.xamarin.com/userprefs.cgi)并选择“关闭帐户”\*\*\*\* 选项卡。输入 Bugzilla 密码并勾选“确认你已了解此操作将永久删除你的帐户”框。收到删除请求后，将不会删除用户已发布到 Xamarin Bugzilla 的公共反馈（例如，bug、问题、评论和解决方案）。公共反馈改为以匿名形式显示，这是通过删除与提交删除请求的用户所创建的任何公共反馈关联的名称和电子邮件地址实现的。</span><span class="sxs-lookup"><span data-stu-id="004af-p121">To request deletion of personal data used in connection with Xamarin's Bugzilla bug reporting website, users can close their Xamarin Bugzilla account by going to the [user preferences page](https://bugzilla.xamarin.com/userprefs.cgi) and choosing the **Close Account tab**. Enter your Bugzilla password and check the box confirming that you understand that this will permanently delete your account. Public feedback (for example, bugs, problems, comments, and solutions) that users have posted to the Xamarin Bugzilla will not be deleted after receipt of a delete request. Public feedback will instead be anonymized by removing the name and email address associated with any public feedback created by the user submitting the delete request.</span></span>

## <a name="nuget"></a><span data-ttu-id="004af-241">NuGet</span><span class="sxs-lookup"><span data-stu-id="004af-241">NuGet</span></span>

<span data-ttu-id="004af-242">有关针对 NuGet.org 的 DSR 的详细信息，请参阅 [NuGet 用户数据请求](https://docs.microsoft.com/nuget/policies/data-requests)。</span><span class="sxs-lookup"><span data-stu-id="004af-242">For more information on DSR for NuGet.org, see [NuGet User Data Requests](https://docs.microsoft.com/nuget/policies/data-requests).</span></span>

## <a name="aspnet"></a><span data-ttu-id="004af-243">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="004af-243">ASP.NET</span></span>

<span data-ttu-id="004af-244">有关针对 ASP.NET 网站的 DSR 的信息，请参阅 [ASP.NET 网站和 GDPR 数据主体请求处理](https://www.asp.net/gdpr)。</span><span class="sxs-lookup"><span data-stu-id="004af-244">For information on DSR for the ASP.NET website, see [The ASP.NET Website and GDPR Data Subject Request processing](https://www.asp.net/gdpr).</span></span>

## <a name="iisnet"></a><span data-ttu-id="004af-245">IIS.NET</span><span class="sxs-lookup"><span data-stu-id="004af-245">IIS.NET</span></span>

<span data-ttu-id="004af-246">有关针对 IIS.NET 网站的 DSR 的信息，请参阅 [IIS.NET 网站和 GDPR 数据主体请求处理](https://www.iis.net/gdpr)。</span><span class="sxs-lookup"><span data-stu-id="004af-246">For information on DSR for the IIS.NET website, see [The IIS.NET Website and GDPR Data Subject Request processing](https://www.iis.net/gdpr).</span></span>

## <a name="other-visual-studio-family-services"></a><span data-ttu-id="004af-247">其他 Visual Studio 系列服务</span><span class="sxs-lookup"><span data-stu-id="004af-247">Other Visual Studio Family Services</span></span>

### <a name="surveymonkey"></a><span data-ttu-id="004af-248">SurveyMonkey</span><span class="sxs-lookup"><span data-stu-id="004af-248">SurveyMonkey</span></span>

<span data-ttu-id="004af-p122">有时，我们会邀请客户通过 SurveyMonkey 提供有关这些产品的反馈。此数据将在 28 天内删除。为这些产品提供数据主体请求服务时，如果我们已验证了调查响应，会将其添加到导出和删除数据主体请求中。</span><span class="sxs-lookup"><span data-stu-id="004af-p122">From time to time, we invite customers to provide feedback on these products via SurveyMonkey. This data is deleted within 28 days. When servicing data subject requests for these products, if we have authenticated survey responses we include them in export and delete data subject requests.</span></span>

### <a name="uservoice"></a><span data-ttu-id="004af-252">UserVoice</span><span class="sxs-lookup"><span data-stu-id="004af-252">UserVoice</span></span>

<span data-ttu-id="004af-p123">我们邀请客户在 UserVoice.com 网站上提供有关这些产品的产品建议。这些网站是由 UserVoice 独立运营的，数据主体请求由 UserVoice 管理。</span><span class="sxs-lookup"><span data-stu-id="004af-p123">We invite customers to provide product suggestions at UserVoice.com sites for these products. These sites are independently operated by UserVoice, and data subject requests are managed by UserVoice.</span></span>

- [https://visualstudio.uservoice.com/](https://visualstudio.uservoice.com/)
- [https://aspnet.uservoice.com/](https://aspnet.uservoice.com/)
- [https://xamarin.uservoice.com/](https://xamarin.uservoice.com/)

<span data-ttu-id="004af-255">有关此数据的数据主体请求，请参阅[如何导出数据](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data)或[如何删除数据](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information)上的 UserVoice 指南。</span><span class="sxs-lookup"><span data-stu-id="004af-255">For data subject requests on this data, see the UserVoice guidance on [how to export your data](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data) or on [how to delete your data](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information).</span></span>

## <a name="learn-more"></a><span data-ttu-id="004af-256">了解更多</span><span class="sxs-lookup"><span data-stu-id="004af-256">Learn more</span></span>

- [<span data-ttu-id="004af-257">Microsoft 对我们公开发布的企业软件产品的客户的 GDPR 义务</span><span class="sxs-lookup"><span data-stu-id="004af-257">Microsoft's GDPR Commitments to Customers of our Generally Available Enterprise Software Products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="004af-258">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="004af-258">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [<span data-ttu-id="004af-259">服务信任门户</span><span class="sxs-lookup"><span data-stu-id="004af-259">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="004af-260">Microsoft 隐私仪表板</span><span class="sxs-lookup"><span data-stu-id="004af-260">Microsoft Privacy Dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="004af-261">Microsoft 隐私响应中心</span><span class="sxs-lookup"><span data-stu-id="004af-261">Microsoft Privacy Response Center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="004af-262">针对 GDPR 的 Azure 数据主体请求</span><span class="sxs-lookup"><span data-stu-id="004af-262">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)
