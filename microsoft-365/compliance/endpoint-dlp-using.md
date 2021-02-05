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
ms.openlocfilehash: 15a540c323c8f49cfa6c15358cfec89034667378
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094793"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="78781-103">使用端点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="78781-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="78781-104">本文将向你介绍创建和修改将设备用作位置的 DLP 策略的三种情况。</span><span class="sxs-lookup"><span data-stu-id="78781-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="78781-105">DLP 设置</span><span class="sxs-lookup"><span data-stu-id="78781-105">DLP settings</span></span>

<span data-ttu-id="78781-106">在开始之前，你应该先设置 DLP 设置，该设置将应用于设备的所有 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="78781-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="78781-107">如果要创建实施以下操作的策略，则必须配置这些策略：</span><span class="sxs-lookup"><span data-stu-id="78781-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="78781-108">云出口限制</span><span class="sxs-lookup"><span data-stu-id="78781-108">cloud egress restrictions</span></span>
- <span data-ttu-id="78781-109">不允许的应用限制</span><span class="sxs-lookup"><span data-stu-id="78781-109">unallowed apps restrictions</span></span>

<span data-ttu-id="78781-110">或</span><span class="sxs-lookup"><span data-stu-id="78781-110">Or</span></span>

- <span data-ttu-id="78781-111">如果要从监视中排除杂乱的文件路径</span><span class="sxs-lookup"><span data-stu-id="78781-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="78781-112">![DLP 设置](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="78781-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="78781-113">文件路径排除</span><span class="sxs-lookup"><span data-stu-id="78781-113">File path exclusions</span></span>

<span data-ttu-id="78781-114">你可能希望从设备上的 DLP 监视、DLP 警报和 DLP 策略执行中排除某些路径，因为它们太杂乱或未包含你感兴趣的文件。</span><span class="sxs-lookup"><span data-stu-id="78781-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="78781-115">系统将不会审核这些位置中的文件，并且在这些位置创建或修改的任何文件都将不受 DLP 策略执行的约束。</span><span class="sxs-lookup"><span data-stu-id="78781-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="78781-116">可在 DLP 设置中配置路径排除项。</span><span class="sxs-lookup"><span data-stu-id="78781-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="78781-117">可使用此逻辑构建排除路径：</span><span class="sxs-lookup"><span data-stu-id="78781-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="78781-118">以“\”结尾的有效文件路径，仅表示直接位于文件夹下的文件。</span><span class="sxs-lookup"><span data-stu-id="78781-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="78781-119">例如：C:\Temp</span><span class="sxs-lookup"><span data-stu-id="78781-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="78781-120">以“\*”结尾的有效文件路径，仅表示位于子文件夹下的文件，以及直接位于文件夹下方的文件。</span><span class="sxs-lookup"><span data-stu-id="78781-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="78781-121">例如：C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="78781-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="78781-122">以“\”或“\*”结尾的有效文件路径，表示直接位于文件夹和所有子文件夹下的所有文件。</span><span class="sxs-lookup"><span data-stu-id="78781-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="78781-123">例如：C:\Temp</span><span class="sxs-lookup"><span data-stu-id="78781-123">For example: C:\Temp</span></span>

- <span data-ttu-id="78781-124">两端“\”之间带有通配符的路径。</span><span class="sxs-lookup"><span data-stu-id="78781-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="78781-125">例如：C:\Users\*\Desktop</span><span class="sxs-lookup"><span data-stu-id="78781-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="78781-126">两端“\”之间带有通配符，并通过 ‘(number)’ 给出确切的子文件夹数量的路径。</span><span class="sxs-lookup"><span data-stu-id="78781-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="78781-127">例如：C:\Users\*(1)\Downloads</span><span class="sxs-lookup"><span data-stu-id="78781-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="78781-128">带有 SYSTEM 环境变量的路径。</span><span class="sxs-lookup"><span data-stu-id="78781-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="78781-129">例如：%SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="78781-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="78781-130">综合了上述所有情况。</span><span class="sxs-lookup"><span data-stu-id="78781-130">A mix of all the above.</span></span> <br/><span data-ttu-id="78781-131">例如：%SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="78781-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="78781-132">不允许的应用</span><span class="sxs-lookup"><span data-stu-id="78781-132">Unallowed apps</span></span>

<span data-ttu-id="78781-133">启用策略的“**通过不允许的应用程序和浏览器访问**”设置，并且用户尝试使用这些应用程序访问受保护的文件时，活动将被允许、阻止或者阻止，但用户可以覆盖该限制。</span><span class="sxs-lookup"><span data-stu-id="78781-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="78781-134">所有活动均经过审核，可在活动资源管理器中查看。</span><span class="sxs-lookup"><span data-stu-id="78781-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78781-135">不包括可执行文件的路径，而仅包括可执行文件的名称（如 browser.exe）。</span><span class="sxs-lookup"><span data-stu-id="78781-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="78781-136">浏览器和域限制</span><span class="sxs-lookup"><span data-stu-id="78781-136">Browser and domain restrictions</span></span>
<span data-ttu-id="78781-137">限制与策略匹配的敏感文件与不受限制的云服务域共享。</span><span class="sxs-lookup"><span data-stu-id="78781-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="78781-138">服务域</span><span class="sxs-lookup"><span data-stu-id="78781-138">Service domains</span></span>

<span data-ttu-id="78781-139">你可以控制受你的策略保护的敏感文件是否可以从 Microsoft Edge 上传到特定服务域。</span><span class="sxs-lookup"><span data-stu-id="78781-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="78781-140">如果列表模式设置为“**阻止**”，用户将无法向这些域上传敏感项目。</span><span class="sxs-lookup"><span data-stu-id="78781-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="78781-141">如果由于某项目符合 DLP 策略而阻止了上载操作，则 DLP 会生成警告或阻止敏感项目的上载。</span><span class="sxs-lookup"><span data-stu-id="78781-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="78781-142">如果列表模式设置为“**允许**”，则用户将 **_只能_** 将敏感项目上传到那些域，并且不允许对所有其他域的上传访问。</span><span class="sxs-lookup"><span data-stu-id="78781-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="78781-143">不允许的浏览器</span><span class="sxs-lookup"><span data-stu-id="78781-143">Unallowed browsers</span></span>

<span data-ttu-id="78781-144">你将添加由执行文件名标识的浏览器，这些浏览器将被阻止访问与强制 DLP 策略的条件匹配的文件，在该 DLP 策略中，“上载到云服务的限制”设置为“阻止”或“阻止覆盖”。</span><span class="sxs-lookup"><span data-stu-id="78781-144">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="78781-145">当这些浏览器被阻止访问文件时，最终用户将看到一则定制通知，要求他们通过 Microsoft Edge Chromium 打开文件。</span><span class="sxs-lookup"><span data-stu-id="78781-145">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="78781-146">策略提示中的业务理由</span><span class="sxs-lookup"><span data-stu-id="78781-146">Business justification in policy tips</span></span>

<span data-ttu-id="78781-147">可在 DLP 策略提示通知中控制用户与业务理由选项的交互方式。</span><span class="sxs-lookup"><span data-stu-id="78781-147">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="78781-148">当用户执行受 DLP 策略中 **以超越阻止** 设置所保护的活动时，将出现此选项。</span><span class="sxs-lookup"><span data-stu-id="78781-148">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="78781-149">可从下列选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="78781-149">You can choose from one the following options:</span></span>

- <span data-ttu-id="78781-150">默认情况下，用户可以选择内置理由或输入自己的文本。</span><span class="sxs-lookup"><span data-stu-id="78781-150">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="78781-151">用户只能选择内置理由。</span><span class="sxs-lookup"><span data-stu-id="78781-151">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="78781-152">用户只能输入自己的理由。</span><span class="sxs-lookup"><span data-stu-id="78781-152">Users can only enter their own justification.</span></span>


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="78781-153">将 DLP 设置捆绑在一起</span><span class="sxs-lookup"><span data-stu-id="78781-153">Tying DLP settings together</span></span>

<span data-ttu-id="78781-154">通过终结点 DLP 和 Microsoft Edge Chromium Web 浏览器，可以将意外共享敏感项目限制为不允许的云应用和服务。</span><span class="sxs-lookup"><span data-stu-id="78781-154">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="78781-155">Microsoft Edge Chromium可以了解终结点 DLP 策略何时限制项目，并实施访问限制。</span><span class="sxs-lookup"><span data-stu-id="78781-155">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="78781-156">在将终结点 DLP 用作正确配置的 DLP 策略和 Microsoft Edge Chromium 浏览器中的位置时，你在这些设置中定义的不允许的浏览器将无法访问与 DLP 策略控件匹配的敏感项目。</span><span class="sxs-lookup"><span data-stu-id="78781-156">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="78781-157">相反，用户将被重定向以使用 Microsoft Edge Chromium，该浏览器了解 DLP 施加的限制，可以在满足 DLP 策略中的条件时阻止或限制活动。</span><span class="sxs-lookup"><span data-stu-id="78781-157">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="78781-158">若要使用此限制，需要配置三个重要的部分：</span><span class="sxs-lookup"><span data-stu-id="78781-158">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="78781-159">指定要防止敏感项目共享到的位置（服务、域、IP 地址）。</span><span class="sxs-lookup"><span data-stu-id="78781-159">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="78781-160">添加出现 DLP 策略匹配时不允许访问某些敏感项目的浏览器。</span><span class="sxs-lookup"><span data-stu-id="78781-160">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="78781-161">通过启用“**上载到云服务**”和“**从不允许的浏览器访问**”，配置 DLP 策略以定义应限制在这些位置的敏感项目的种类。</span><span class="sxs-lookup"><span data-stu-id="78781-161">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="78781-162">你可以继续添加新的服务、应用和策略，以扩展和扩大你的限制，从而满足业务需求并保护敏感数据。</span><span class="sxs-lookup"><span data-stu-id="78781-162">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="78781-163">此配置将帮助确保你的数据安全，同时避免不必要的限制，防止或限制用户访问和共享不敏感的项目。</span><span class="sxs-lookup"><span data-stu-id="78781-163">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="78781-164">终结点 DLP 策略方案</span><span class="sxs-lookup"><span data-stu-id="78781-164">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="78781-165">为了帮助你熟悉终结点 DLP 功能及其在 DLP 策略中的呈现方式，我们整理了一些方案供你遵循。</span><span class="sxs-lookup"><span data-stu-id="78781-165">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="78781-166">当终结点 DLP 普遍可用时，所有终结点 DLP 内容都将被折叠到主要 DLP 内容集中。</span><span class="sxs-lookup"><span data-stu-id="78781-166">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78781-167">这些终结点 DLP 方案不是创建和优化 DLP 策略的正式过程。</span><span class="sxs-lookup"><span data-stu-id="78781-167">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="78781-168">当你需要在常规情况下使用 DLP 策略，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="78781-168">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="78781-169">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="78781-169">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="78781-170">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="78781-170">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="78781-171">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="78781-171">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="78781-172">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="78781-172">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="78781-173">方案 1：从模板创建策略，仅审核</span><span class="sxs-lookup"><span data-stu-id="78781-173">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="78781-174">这些方案要求你已载入设备并向活动资源管理器浏览器报告。</span><span class="sxs-lookup"><span data-stu-id="78781-174">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="78781-175">如果尚未载入设备，请参阅[终结点数据丢失防护入门](endpoint-dlp-getting-started.md)。</span><span class="sxs-lookup"><span data-stu-id="78781-175">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="78781-176">打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="78781-176">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="78781-177">选择 **创建策略**。</span><span class="sxs-lookup"><span data-stu-id="78781-177">Choose **Create policy**.</span></span>

3. <span data-ttu-id="78781-178">在此方案中，依次选择“**隐私**”和“**美国个人身份信息 (PII) 数据**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="78781-178">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="78781-179">将“**设备**”以外所有位置的“**状态**”字段切换为“关”。</span><span class="sxs-lookup"><span data-stu-id="78781-179">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="78781-180">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="78781-180">Choose **Next**.</span></span>

5. <span data-ttu-id="78781-181">接受默认的“**从模板中查看和自定义设置**”选择，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="78781-181">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="78781-182">接受默认的“**保护操作**”值，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="78781-182">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="78781-183">选择“**审核或限制 Windows 设备上的活动**”，然后将“操作”设置为“**仅审核**”。</span><span class="sxs-lookup"><span data-stu-id="78781-183">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="78781-184">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="78781-184">Choose **Next**.</span></span>

8. <span data-ttu-id="78781-185">接受默认的“**我想要先测试**”值，然后选择“**在测试模式下显示策略提示**”。</span><span class="sxs-lookup"><span data-stu-id="78781-185">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="78781-186">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="78781-186">Choose **Next**.</span></span>

9. <span data-ttu-id="78781-187">查看设置，然后选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="78781-187">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="78781-188">新的 DLP 策略将显示在策略列表中。</span><span class="sxs-lookup"><span data-stu-id="78781-188">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="78781-189">检查活动资源管理器中是否有来自受监视终结点的数据。</span><span class="sxs-lookup"><span data-stu-id="78781-189">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="78781-190">设置设备的位置筛选器并添加策略，然后按策略名称筛选以查看此策略的影响。</span><span class="sxs-lookup"><span data-stu-id="78781-190">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="78781-191">如有需要，请参见[活动资源管理器（预览）入门](data-classification-activity-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="78781-191">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="78781-192">尝试与组织外的人员共享包含将触发美国个人身份信息 (PII) 数据条件的内容的测试。</span><span class="sxs-lookup"><span data-stu-id="78781-192">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="78781-193">这应该会触发策略。</span><span class="sxs-lookup"><span data-stu-id="78781-193">This should trigger the policy.</span></span>

13. <span data-ttu-id="78781-194">检查活动资源管理器中的事件。</span><span class="sxs-lookup"><span data-stu-id="78781-194">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="78781-195">方案 2：修改现有策略，设置警报</span><span class="sxs-lookup"><span data-stu-id="78781-195">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="78781-196">打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="78781-196">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="78781-197">选择在方案 1 中创建的“**美国个人身份信息 (PII) 数据**”策略。</span><span class="sxs-lookup"><span data-stu-id="78781-197">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="78781-198">选择 **编辑策略**。</span><span class="sxs-lookup"><span data-stu-id="78781-198">Choose **edit policy**.</span></span>

4. <span data-ttu-id="78781-199">转到“**高级 DLP 规则**”页面，然后编辑“**检测到少量内容的美国个人身份信息**”。</span><span class="sxs-lookup"><span data-stu-id="78781-199">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="78781-200">向下滚动到“**事件报告**”部分，然后将“**在规则匹配出现时向管理员发送警报**”设置为“**开**”。</span><span class="sxs-lookup"><span data-stu-id="78781-200">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="78781-201">系统会将电子邮件警报自动发送给管理员，以及你添加到收件人列表的任何其他人员。</span><span class="sxs-lookup"><span data-stu-id="78781-201">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78781-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="78781-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="78781-203">出于本方案的目的，请选择“**每次活动与规则匹配时选择发送警报**”。</span><span class="sxs-lookup"><span data-stu-id="78781-203">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="78781-204">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="78781-204">Choose **Save**.</span></span>

8. <span data-ttu-id="78781-205">通过选择“**下一步**”，然后“**提交**”策略更改来保留所有先前的设置。</span><span class="sxs-lookup"><span data-stu-id="78781-205">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="78781-206">尝试与组织外的人员共享包含将触发美国个人身份信息 (PII) 数据条件的内容的测试。</span><span class="sxs-lookup"><span data-stu-id="78781-206">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="78781-207">这应该会触发策略。</span><span class="sxs-lookup"><span data-stu-id="78781-207">This should trigger the policy.</span></span>

10. <span data-ttu-id="78781-208">检查活动资源管理器中的事件。</span><span class="sxs-lookup"><span data-stu-id="78781-208">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="78781-209">方案 3：修改现有策略，阻止操作但允许覆盖</span><span class="sxs-lookup"><span data-stu-id="78781-209">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="78781-210">打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。</span><span class="sxs-lookup"><span data-stu-id="78781-210">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="78781-211">选择在方案 1 中创建的“**美国个人身份信息 (PII) 数据**”策略。</span><span class="sxs-lookup"><span data-stu-id="78781-211">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="78781-212">选择 **编辑策略**。</span><span class="sxs-lookup"><span data-stu-id="78781-212">Choose **edit policy**.</span></span>

4. <span data-ttu-id="78781-213">转到“**高级 DLP 规则**”页面，然后编辑“**检测到少量内容的美国个人身份信息**”。</span><span class="sxs-lookup"><span data-stu-id="78781-213">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="78781-214">向下滚动到“**审核或限制 Windows 设备上的活动**”部分，并对每个活动将相应的操作设置为“**阻止但允许覆盖**”。</span><span class="sxs-lookup"><span data-stu-id="78781-214">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78781-215">![设置阻止但允许覆盖操作](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="78781-215">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="78781-216">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="78781-216">Choose **Save**.</span></span>

7. <span data-ttu-id="78781-217">对 **检测到大量内容的美国个人身份信息** 重复步骤 4-7。</span><span class="sxs-lookup"><span data-stu-id="78781-217">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="78781-218">通过选择“**下一步**”，然后“**提交**”策略更改来保留所有先前的设置。</span><span class="sxs-lookup"><span data-stu-id="78781-218">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="78781-219">尝试与组织外的人员共享包含将触发美国个人身份信息 (PII) 数据条件的内容的测试。</span><span class="sxs-lookup"><span data-stu-id="78781-219">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="78781-220">这应该会触发策略。</span><span class="sxs-lookup"><span data-stu-id="78781-220">This should trigger the policy.</span></span>

   <span data-ttu-id="78781-221">客户端设备上将显示如下所示的弹出窗口：</span><span class="sxs-lookup"><span data-stu-id="78781-221">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78781-222">![终结点 DLP 客户端阻止覆盖通知](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="78781-222">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="78781-223">检查活动资源管理器中的事件。</span><span class="sxs-lookup"><span data-stu-id="78781-223">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="78781-224">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78781-224">See also</span></span>

- [<span data-ttu-id="78781-225">了解终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="78781-225">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="78781-226">终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="78781-226">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="78781-227">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="78781-227">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="78781-228">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="78781-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="78781-229">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="78781-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="78781-230">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="78781-230">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="78781-231">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="78781-231">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="78781-232">Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="78781-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="78781-233">已加入 Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="78781-233">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="78781-234">下载基于 Chromium 的新 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="78781-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="78781-235">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="78781-235">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="78781-236">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="78781-236">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
