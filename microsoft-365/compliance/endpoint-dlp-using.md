---
title: 使用终结点数据丢失防护
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 了解如何配置数据丢失防护 (DLP) 策略以使用 Microsoft 365 终结点数据丢失防护 (EPDLP) 位置。
ms.openlocfilehash: 64cdfeab4b527dd3b84e7586d1419e5bf8b383df
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073101"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="c2d88-103">使用端点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="c2d88-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="c2d88-104">本文将向你介绍创建和修改将设备用作位置的 DLP 策略的三种情况。</span><span class="sxs-lookup"><span data-stu-id="c2d88-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="c2d88-105">DLP 设置</span><span class="sxs-lookup"><span data-stu-id="c2d88-105">DLP settings</span></span>

<span data-ttu-id="c2d88-p101">在开始之前，你应该先设置 DLP 设置，该设置将应用于所有设备的 DLP 策略。如果打算创建强制执行的策略，则必须配置这些设置：</span><span class="sxs-lookup"><span data-stu-id="c2d88-p101">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices. You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="c2d88-108">云出口限制</span><span class="sxs-lookup"><span data-stu-id="c2d88-108">cloud egress restrictions</span></span>
- <span data-ttu-id="c2d88-109">不允许的应用限制</span><span class="sxs-lookup"><span data-stu-id="c2d88-109">unallowed apps restrictions</span></span>

<span data-ttu-id="c2d88-110">或</span><span class="sxs-lookup"><span data-stu-id="c2d88-110">Or</span></span>

- <span data-ttu-id="c2d88-111">如果要从监视中排除杂乱的文件路径</span><span class="sxs-lookup"><span data-stu-id="c2d88-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="c2d88-112">![DLP 设置](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="c2d88-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="c2d88-113">文件路径排除</span><span class="sxs-lookup"><span data-stu-id="c2d88-113">File path exclusions</span></span>

<span data-ttu-id="c2d88-p102">你可能希望从设备上的 DLP 监视、DLP 警报和 DLP 策略执行中排除某些路径，因为它们太杂乱或未包含你所感兴趣的文件。不会审核这些位置中的文件，且在这些位置中创建或修改的任何文件都不会受到 DLP 策略执行的影响。可以在 DLP 设置中将配置路径排除。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p102">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in. Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement. You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="c2d88-117">可使用此逻辑构建排除路径：</span><span class="sxs-lookup"><span data-stu-id="c2d88-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="c2d88-118">以“\”结尾的有效文件路径，仅表示直接位于文件夹下的文件。</span><span class="sxs-lookup"><span data-stu-id="c2d88-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="c2d88-119">例如：C:\Temp</span><span class="sxs-lookup"><span data-stu-id="c2d88-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="c2d88-120">以“\*”结尾的有效文件路径，仅表示位于子文件夹下的文件，以及直接位于文件夹下方的文件。</span><span class="sxs-lookup"><span data-stu-id="c2d88-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="c2d88-121">例如：C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="c2d88-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="c2d88-122">以“\”或“\*”结尾的有效文件路径，表示直接位于文件夹和所有子文件夹下的所有文件。</span><span class="sxs-lookup"><span data-stu-id="c2d88-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="c2d88-123">例如：C:\Temp</span><span class="sxs-lookup"><span data-stu-id="c2d88-123">For example: C:\Temp</span></span>

- <span data-ttu-id="c2d88-124">两端“\”之间带有通配符的路径。</span><span class="sxs-lookup"><span data-stu-id="c2d88-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="c2d88-125">例如：C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="c2d88-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="c2d88-126">两端“\”之间带有通配符，并通过 ‘(number)’ 给出确切的子文件夹数量的路径。</span><span class="sxs-lookup"><span data-stu-id="c2d88-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="c2d88-127">例如：C:\Users\*(1)\Downloads</span><span class="sxs-lookup"><span data-stu-id="c2d88-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="c2d88-128">带有 SYSTEM 环境变量的路径。</span><span class="sxs-lookup"><span data-stu-id="c2d88-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="c2d88-129">例如：%SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="c2d88-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="c2d88-130">综合了上述所有情况。</span><span class="sxs-lookup"><span data-stu-id="c2d88-130">A mix of all the above.</span></span> <br/><span data-ttu-id="c2d88-131">例如：%SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="c2d88-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="service-domains"></a><span data-ttu-id="c2d88-132">服务域</span><span class="sxs-lookup"><span data-stu-id="c2d88-132">Service domains</span></span>

<span data-ttu-id="c2d88-133">可以将域添加到此列表，Microsoft Edge Chromium 会在执行终结点 DLP 策略云上载访问限制时引用该列表。</span><span class="sxs-lookup"><span data-stu-id="c2d88-133">You can add domains to this list that Edge Chromium will refer to when enforcing the Endpoint DLP policy cloud upload access restriction.</span></span> 

<span data-ttu-id="c2d88-p103">如果列表模式设置为 **阻止** ，则用户将无法向这些域上载敏感项目。当因为某个项目符合 DLP 策略而阻止上传操作时，DLP 将产生一个警告或阻止敏感项目的上传。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p103">If the list mode is set to **Block** , then user will not be able to upload sensitive items to those domains. When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="c2d88-136">如果列表模式设置为“ **允许** ”，则用户将\* *_只能_* _将敏感项目上载到那些域，并且不允许对所有其他域的上载访问。</span><span class="sxs-lookup"><span data-stu-id="c2d88-136">If the list mode is set to **Allow** , then users will be able to upload sensitive items \* *_only_* _ to those domains, and upload access to all other domains is not allowed.</span></span>

### <a name="unallowed-apps"></a><span data-ttu-id="c2d88-137">不允许的应用</span><span class="sxs-lookup"><span data-stu-id="c2d88-137">Unallowed apps</span></span>

<span data-ttu-id="c2d88-p104">当开启策略的_ *通过不允许的应用程序和浏览器访问* \*设置，并且用户试图使用这些应用程序访问受保护的文件时，将会允许、阻止或者阻止但用户可覆盖限制该活动。会审核所有活动，并可在活动资源管理器中查看。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p104">When a policy's _ *Access by unallowed apps and browsers* \* setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction. All activity is audited and available to review in activity explorer.</span></span>

### <a name="unallowed-browsers"></a><span data-ttu-id="c2d88-140">不允许的浏览器</span><span class="sxs-lookup"><span data-stu-id="c2d88-140">Unallowed browsers</span></span>

<span data-ttu-id="c2d88-p105">你通过其可执行名称来添加所标识的浏览器，将阻止这些浏览器访问符合强制执行的 DLP 策略条件的文件，其中设置上传到云服务的限制为阻止或阻止覆盖。当访问文件阻止这些浏览器时，最终用户将看到一个 toast 通知要求他们通过 Edge Chromium 打开文件。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p105">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override. When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

[!IMPORTANT]
<span data-ttu-id="c2d88-143">不包括可执行文件的路径，而仅包括可执行文件的名称（即browser.exe）。</span><span class="sxs-lookup"><span data-stu-id="c2d88-143">Do not include the path to the executable, but only the executable name (i.e., browser.exe).</span></span>

## <a name="tying-dlp-settings-together"></a><span data-ttu-id="c2d88-144">将 DLP 设置捆绑在一起</span><span class="sxs-lookup"><span data-stu-id="c2d88-144">Tying DLP settings together</span></span>

<span data-ttu-id="c2d88-p106">通过端点 DLP 和 Edge Chromium Web 浏览器，可以限制将敏感项目无意中分享到不允许的云应用和服务。Edge Chromium 能够了解终端 DLP策略在何时限制了哪个项目，并执行访问限制。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p106">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services. Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="c2d88-p107">当使用端点 DLP 作为正确配置的 DLP 策略和 Edge Chromium 浏览器中的位置时，将阻止在这些设置中所定义的不允许的浏览器访问与 DLP 策略控制相匹配的敏感项目。相反，将重定向用户到使用 Edge Chromium，而 Edge Chromium 凭借其对 DLP 施加限制的理解，可以在满足 DLP 策略中的条件时阻止或限制活动。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p107">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls. Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="c2d88-149">若要使用此限制，需要配置三个重要的部分：</span><span class="sxs-lookup"><span data-stu-id="c2d88-149">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="c2d88-150">指定要防止敏感项目共享到的位置（服务、域、IP 地址）。</span><span class="sxs-lookup"><span data-stu-id="c2d88-150">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="c2d88-151">添加出现 DLP 策略匹配时不允许访问某些敏感项目的浏览器。</span><span class="sxs-lookup"><span data-stu-id="c2d88-151">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="c2d88-152">通过启用“ **上载到云服务** ”和“ **从不允许的浏览器访问** ”，配置 DLP 策略以定义应限制在这些位置的敏感项目的种类。</span><span class="sxs-lookup"><span data-stu-id="c2d88-152">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="c2d88-153">你可以继续添加新的服务、应用和策略，以扩展和扩大你的限制，从而满足业务需求并保护敏感数据。</span><span class="sxs-lookup"><span data-stu-id="c2d88-153">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="c2d88-154">此配置将帮助确保你的数据安全，同时避免不必要的限制，防止或限制用户访问和共享不敏感的项目。</span><span class="sxs-lookup"><span data-stu-id="c2d88-154">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="c2d88-155">终结点 DLP 策略方案</span><span class="sxs-lookup"><span data-stu-id="c2d88-155">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="c2d88-p108">为了帮助你熟悉端点 DLP 功能以及其在 DLP 策略中所呈现的方式，我们整理了一些方案。当终点 DLP 变得公开可用时，所有的终点 DLP 内容将折叠到主 DLP 内容集中。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p108">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow. All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2d88-p109">这些端点 DLP 方案不是创建和优化 DLP 策略的正式过程。当你需要在一般情况下使用 DLP 策略时，请参考以下主题：</span><span class="sxs-lookup"><span data-stu-id="c2d88-p109">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies. Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="c2d88-160">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="c2d88-160">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="c2d88-161">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c2d88-161">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="c2d88-162">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c2d88-162">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="c2d88-163">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c2d88-163">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="c2d88-164">方案 1：从模板创建策略，仅审核</span><span class="sxs-lookup"><span data-stu-id="c2d88-164">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="c2d88-p110">这些方案要求你已登录设备，并向Activity explorer报告。如果你尚未登录设备，请参阅[使用端点数据丢失防护入门](endpoint-dlp-getting-started.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p110">These scenarios require that you already have devices onboarded and reporting into Activity explorer. If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="c2d88-167">打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="c2d88-167">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="c2d88-168">选择 **创建策略** 。</span><span class="sxs-lookup"><span data-stu-id="c2d88-168">Choose **Create policy**.</span></span>

3. <span data-ttu-id="c2d88-169">在此方案中，依次选择“ **隐私** ”和“ **美国个人身份信息 (PII) 数据** ”，然后选择“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-169">For this scenario, choose **Privacy** , then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="c2d88-p111">将除 **设备** 外的所有位置的 **状态** 字段切换为关闭。选择 **下一步** 。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p111">Toggle the **Status** field to off for all locations except **Devices**. Choose **Next**.</span></span>

5. <span data-ttu-id="c2d88-172">接受默认的“ **从模板中查看和自定义设置** ”选择，然后选择“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-172">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="c2d88-173">接受默认的“ **保护操作** ”值，然后选择“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-173">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="c2d88-p112">选择 **审核或限制 Windows 设备上的活动** ，然后将操作设置为 **仅审核** 。选择 **下一步** 。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p112">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**. Choose **Next**.</span></span>

8. <span data-ttu-id="c2d88-p113">接受默认的 **我想首先测试** 值，然后选择 **在测试模式下显示策略提示** 。选择 **下一步** 。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p113">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**. Choose **Next**.</span></span>

9. <span data-ttu-id="c2d88-178">查看设置，然后选择“ **提交** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-178">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="c2d88-179">新的 DLP 策略将显示在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="c2d88-179">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="c2d88-p114">检查活动资源管理器中是否有来自受监视终结点的数据。设置设备的位置筛选器并添加策略，然后按策略名称筛选以查看此策略的影响。如果需要，请参阅 [活动资源管理器入门](data-classification-activity-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p114">Check Activity explorer for data from the monitored endpoints. Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy. See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="c2d88-p115">尝试与组织外的人员共享包含将触发美国个人身份信息（PII）数据条件的内容的测试。这应该会触发该政策。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p115">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

13. <span data-ttu-id="c2d88-185">检查活动资源管理器中的事件。</span><span class="sxs-lookup"><span data-stu-id="c2d88-185">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="c2d88-186">方案 2：修改现有策略，设置警报</span><span class="sxs-lookup"><span data-stu-id="c2d88-186">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="c2d88-187">打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="c2d88-187">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="c2d88-188">选择在方案 1 中创建的“ **美国个人身份信息 (PII) 数据** ”策略。</span><span class="sxs-lookup"><span data-stu-id="c2d88-188">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="c2d88-189">选择 **编辑策略** 。</span><span class="sxs-lookup"><span data-stu-id="c2d88-189">Choose **edit policy**.</span></span>

4. <span data-ttu-id="c2d88-190">转到“ **高级 DLP 规则** ”页面，然后编辑“ **检测到少量内容的美国个人身份信息** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-190">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="c2d88-p116">向下滚动到 **事件报告** 部分，然后将 **在规则匹配出现时向管理员发送警报** 设置为 **开启** 。电子邮件警报将会自动发送给管理员，以及你所添加到收件人列表中的其他人员。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p116">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**. Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2d88-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="c2d88-193">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="c2d88-194">出于本方案的目的，请选择“ **每次活动与规则匹配时选择发送警报** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-194">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="c2d88-195">选择“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-195">Choose **Save**.</span></span>

8. <span data-ttu-id="c2d88-196">通过选择“ **下一步** ”，然后“ **提交** ”策略更改来保留所有先前的设置。</span><span class="sxs-lookup"><span data-stu-id="c2d88-196">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="c2d88-p117">尝试与组织外的人员共享包含将触发美国个人身份信息（PII）数据条件的内容的测试。这应该会触发该政策。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p117">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

10. <span data-ttu-id="c2d88-199">检查活动资源管理器中的事件。</span><span class="sxs-lookup"><span data-stu-id="c2d88-199">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="c2d88-200">方案 3：修改现有策略，阻止操作但允许覆盖</span><span class="sxs-lookup"><span data-stu-id="c2d88-200">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="c2d88-201">打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="c2d88-201">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="c2d88-202">选择在方案 1 中创建的“ **美国个人身份信息 (PII) 数据** ”策略。</span><span class="sxs-lookup"><span data-stu-id="c2d88-202">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="c2d88-203">选择 **编辑策略** 。</span><span class="sxs-lookup"><span data-stu-id="c2d88-203">Choose **edit policy**.</span></span>

4. <span data-ttu-id="c2d88-204">转到“ **高级 DLP 规则** ”页面，然后编辑“ **检测到少量内容的美国个人身份信息** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-204">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="c2d88-205">向下滚动到“ **审核或限制 Windows 设备上的活动** ”部分，并对每个活动将相应的操作设置为“ **阻止但允许覆盖** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-205">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2d88-206">![设置阻止但允许覆盖操作](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="c2d88-206">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="c2d88-207">选择“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="c2d88-207">Choose **Save**.</span></span>

7. <span data-ttu-id="c2d88-208">对 **检测到大量内容的美国个人身份信息** 重复步骤 4-7。</span><span class="sxs-lookup"><span data-stu-id="c2d88-208">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="c2d88-209">通过选择“ **下一步** ”，然后“ **提交** ”策略更改来保留所有先前的设置。</span><span class="sxs-lookup"><span data-stu-id="c2d88-209">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="c2d88-p118">尝试与组织外的人员共享包含将触发美国个人身份信息（PII）数据条件的内容的测试。这应该会触发该政策。</span><span class="sxs-lookup"><span data-stu-id="c2d88-p118">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization. This should trigger the policy.</span></span>

   <span data-ttu-id="c2d88-212">客户端设备上将显示如下所示的弹出窗口：</span><span class="sxs-lookup"><span data-stu-id="c2d88-212">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2d88-213">![终结点 DLP 客户端阻止覆盖通知](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="c2d88-213">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="c2d88-214">检查活动资源管理器中的事件。</span><span class="sxs-lookup"><span data-stu-id="c2d88-214">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2d88-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2d88-215">See also</span></span>

- [<span data-ttu-id="c2d88-216">了解终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="c2d88-216">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="c2d88-217">终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="c2d88-217">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="c2d88-218">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="c2d88-218">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="c2d88-219">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c2d88-219">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="c2d88-220">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="c2d88-220">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="c2d88-221">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c2d88-221">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="c2d88-222">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="c2d88-222">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="c2d88-223">Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="c2d88-223">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="c2d88-224">已加入 Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="c2d88-224">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="c2d88-225">下载基于 Chromium 的新 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c2d88-225">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="c2d88-226">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c2d88-226">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="c2d88-227">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c2d88-227">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
