---
title: Microsoft 托管桌面的可配置设置
description: 关于 Microsoft 托管桌面的可配置设置的信息
keywords: microsoft 托管桌面、microsoft 365、服务、文档、设置、可配置的设置
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 64560a1eb597072dd99c1538b0131e3cd807899c
ms.sourcegitcommit: 1942a860d1b65e1f8062564ec4703b953e0c2fd7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30122242"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="83300-104">可配置的设置-Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="83300-104">Configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="83300-p101">microsoft 托管桌面部署应用于由 Microsoft 托管桌面管理的所有设备的设置和策略。有关详细信息, 请参阅[设备配置](../service-description/device-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="83300-p101">Microsoft Managed Desktop deploys settings and policies that are applied to all devices managed by Microsoft Managed Desktop. For more information, see [Device configuration](../service-description/device-policies.md).</span></span>

<span data-ttu-id="83300-p102">Microsoft 托管桌面中的可配置设置为 IT 管理员提供了一种自定义和部署对其组织和业务需求而言独有的设置的方法。这些设置是对由 Microsoft 托管桌面管理的设备配置设置和策略的补充。</span><span class="sxs-lookup"><span data-stu-id="83300-p102">Configurable settings in Microsoft Managed Desktop give IT admins a way to customize and deploy settings that are unique to their organization and business needs. These settings are in addition to device configuration settings and policies that are managed by Microsoft Managed Desktop.</span></span>  

<span data-ttu-id="83300-p103">可配置的设置更改在云中进行, 并在定义的部署环中应用于 Microsoft 托管桌面设备。此过程类似于 Microsoft 托管桌面如何管理对设备 configuruation 设置和由该服务所定义和管理的策略所做的更改。通过使用 Microsoft 托管桌面用于部署更改的相同过程, 你将继续使用新式 IT 管理实践向前移动你的组织。</span><span class="sxs-lookup"><span data-stu-id="83300-p103">Configurable setting changes are made in the cloud and applied to your Microsoft Managed Desktop devices in defined deployment rings. This process is similar to how Microsoft Managed Desktop manages changes to device configuruation settings and policies that are defined and managed by the service. By using the same process that Microsoft Managed Desktop uses for deploying changes,you continue to move your organization forward, using modern IT management practices.</span></span>

## <a name="when-to-use-configurable-settings"></a><span data-ttu-id="83300-112">何时使用可配置的设置？</span><span class="sxs-lookup"><span data-stu-id="83300-112">When to use configurable settings?</span></span>

<span data-ttu-id="83300-113">有几次使用可配置的设置。</span><span class="sxs-lookup"><span data-stu-id="83300-113">There are a few times to use configurable settings.</span></span> 

<span data-ttu-id="83300-p104">**载入过程**– microsoft 托管桌面建议您在集成 Microsoft 托管桌面服务时, 或在你板载的设备 (20 或更多) 时自定义可配置的设置。设置类别是在 Microsoft 托管桌面管理门户中配置的。在载入并拥有对管理门户的访问权限后, 可以确定要为组织自定义的设置类别, 进行更改, 暂存部署, 然后部署所做的更改。</span><span class="sxs-lookup"><span data-stu-id="83300-p104">**Onboarding process** – Microsoft Managed Desktop recommends that you customize configurable settings when you onboard to Microsoft Managed Desktop service, or when you onboard a large number of devices (20 or more). Setting categories are configured in Microsoft Managed Desktop admin portal. After you’ve onboarded and have access to the admin portal, you can decide which setting categories you want to customize for your organization, make the changes, stage a deployment, and then deploy your changes.</span></span>

<span data-ttu-id="83300-p105">**维护设置**-定期查看您的设置并进行必要的更新。您可能需要进行更改以支持您的业务更改。</span><span class="sxs-lookup"><span data-stu-id="83300-p105">**Maintain settings** - Review your settings regularly and make needed updates. You might need to make changes to support a change in your business.</span></span>   

## <a name="setting-categories"></a><span data-ttu-id="83300-119">设置类别</span><span class="sxs-lookup"><span data-stu-id="83300-119">Setting categories</span></span>

<span data-ttu-id="83300-120">以下是可以自定义的可配置设置类别:</span><span class="sxs-lookup"><span data-stu-id="83300-120">These are the configurable settings categories that you can customize:</span></span>
- <span data-ttu-id="83300-121">[桌面背景图片](config-setting-ref.md#desktop-background-picture)–自定义 Microsoft 托管桌面设备的桌面背景图片。</span><span class="sxs-lookup"><span data-stu-id="83300-121">[Desktop background picture](config-setting-ref.md#desktop-background-picture) – Customize the desktop background picture for Microsoft Managed Desktop devices.</span></span> 
- <span data-ttu-id="83300-p106">[浏览器起始页](config-setting-ref.md#browser-start-pages)–添加要与 Microsoft Edge 一起使用的起始页。请参阅浏览器起始页</span><span class="sxs-lookup"><span data-stu-id="83300-p106">[Browser start pages](config-setting-ref.md#browser-start-pages) – Add start pages to use with Microsoft Edge. See Browser start page</span></span>
- <span data-ttu-id="83300-p107">[企业模式网站列表](config-setting-ref.md#enterprise-mode-site-list-location)-添加网站及其兼容性模式。列表中的网站将在 Internet Explorer 中启动。</span><span class="sxs-lookup"><span data-stu-id="83300-p107">[Enterprise mode site list](config-setting-ref.md#enterprise-mode-site-list-location) – Add sites, and their compatibility mode. Sites on the list will start in Internet Explorer.</span></span> 
- <span data-ttu-id="83300-126">[受信任的站点](config-setting-ref.md#trusted-sites)–添加受信任的站点并为每个站点设置安全区域。</span><span class="sxs-lookup"><span data-stu-id="83300-126">[Trusted sites](config-setting-ref.md#trusted-sites) – Add trusted sites and set security zones for each site.</span></span> 
- <span data-ttu-id="83300-127">[代理站点例外](config-setting-ref.md#proxy)–设置代理服务器地址编号和端口号, 并添加代理站点例外。</span><span class="sxs-lookup"><span data-stu-id="83300-127">[Proxy site exceptions](config-setting-ref.md#proxy) – Set up your proxy server address number and port number, and add proxy site exceptions.</span></span>

<span data-ttu-id="83300-p108">可以自行自定义和部署每个设置类别。您可以同时将更改部署到多个设置类别, 但是, 一次只能将一个更改部署到一个设置类别。</span><span class="sxs-lookup"><span data-stu-id="83300-p108">Each setting category can be customized and deployed on its own. You can deploy changes to multiple setting categories at the same time, however, you can only deploy one change at a time to a setting category.</span></span>

<span data-ttu-id="83300-130">例如：</span><span class="sxs-lookup"><span data-stu-id="83300-130">For example:</span></span>
- <span data-ttu-id="83300-131">您可以同时将对桌面背景图片和受信任网站的更改部署为自己的部署。</span><span class="sxs-lookup"><span data-stu-id="83300-131">You can deploy changes to desktop background picture and trusted sites, each as their own deployment, at the same time.</span></span> 
- <span data-ttu-id="83300-p109">无法同时将两个部署部署到浏览器起始页。最近的部署将停止仍在进行的早期部署。</span><span class="sxs-lookup"><span data-stu-id="83300-p109">You can’t deploy two deployments to browser start pages at the same time. The most recent deployment will stop earlier deployments that are still in progress.</span></span>

## <a name="configurable-setting-process"></a><span data-ttu-id="83300-134">可配置的设置过程</span><span class="sxs-lookup"><span data-stu-id="83300-134">Configurable setting process</span></span>

<span data-ttu-id="83300-135">整个过程如下所示。</span><span class="sxs-lookup"><span data-stu-id="83300-135">The overall process looks like this.</span></span> 

<span data-ttu-id="83300-p110">**步骤 1-规划**-了解可配置的设置, 并决定要为组织配置哪些设置类别。规划与您的内部更改管理过程相符合您的用户的通信。例如, 如果要添加浏览器起始页, 请让你的用户知道, 在部署后, 他们将在其浏览器中添加一组新的起始页。</span><span class="sxs-lookup"><span data-stu-id="83300-p110">**Step 1 - Plan** - Learn about configurable settings and decide which setting categories you want to configure for your organization. Plan communication to your users that meets your internal change management processes. For example, if you're adding browser start pages, let your users know that they'll have a new set of start pages in their browser after the deployment.</span></span>  

<span data-ttu-id="83300-p111">**步骤 2-配置和暂存部署**-在 Microsoft 托管桌面管理门户中更改可配置的设置。暂存更改, 以便它们可以部署。请记住让你的用户了解这些更改, 以及更改将如何更改其设备体验。</span><span class="sxs-lookup"><span data-stu-id="83300-p111">**Step 2 - Configure and stage deployment** - Make changes to configurable settings in Microsoft Managed Desktop admin portal. Stage the changes so they’re ready to deploy. Remember to let your users know about the changes, and how the changes will change their device experience.</span></span>   

<span data-ttu-id="83300-p112">在 Microsoft 托管桌面管理门户中配置和暂存更改。有关详细信息, 请参阅[自定义可配置设置](config-setting-ref.md)。</span><span class="sxs-lookup"><span data-stu-id="83300-p112">You configure and stage changes in the Microsoft Managed Desktop admin portal. For more information, see [Customize configurable settings](config-setting-ref.md).</span></span> 

<span data-ttu-id="83300-p113">**第3步-传达更改**传达有关即将到来的用户更改的信息。对于每个部署, 完成属于更改管理过程的通信。您应清楚地传达影响用户工作方式或他们在设备上将看到的内容的任何更改。</span><span class="sxs-lookup"><span data-stu-id="83300-p113">**Step 3 - Communicate changes** Communicate information about upcoming changes to your users. For each deployment, complete the communication that is part of your change management processes. You should clearly communicate any change that impacts how a user works, or what they will see on their devices.</span></span>

<span data-ttu-id="83300-p114">**步骤 4-部署更改**–部署更改 (从测试环开始)。通过测试环, 可以在将更改部署到较大的设备组之前, 使用较少的设备验证和解决任何问题。如果遇到任何问题, 您可以还原更改、更新设置并暂存新的部署。Microsoft 托管桌面建议您遵循结构化方法并按以下顺序将其部署到环: Test、First、Fast 和广义。</span><span class="sxs-lookup"><span data-stu-id="83300-p114">**Step 4 - Deploy changes** – Deploy your changes, starting with the Test ring. The Test ring allows you to validate and troubleshoot any issues in a ring with fewer devices, before deploying changes to larger groups of devices. If you run into any issues, you can revert the change, update the setting, and stage a new deployment. Microsoft Managed Desktop recommends that you follow the structured approach and deploy to rings in this order: Test, First, Fast, and then Broad.</span></span>   

<span data-ttu-id="83300-p115">所有可配置的设置均使用 Microsoft 托管桌面管理门户进行管理。有关详细信息, 请参阅[部署更改](config-setting-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="83300-p115">All configurable settings are managed using the Microsoft Managed Desktop admin portal. For more information, see [Deploy changes](config-setting-deploy.md).</span></span> 

<span data-ttu-id="83300-p116">**步骤 5-跟踪更改**–跟踪部署状态更改的进度。对于每个设置, 您可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="83300-p116">**Step 5 - Track changes** – Track the progress for your changes on Deployment status. For each setting, you can:</span></span>
- <span data-ttu-id="83300-p117">**跟踪进度**–在部署更改后跟踪状态。状态将更改为 "**正在进行中**", 然后**完成**或**失败**。如果部署失败, 将自动为 Microsoft 托管桌面操作打开支持请求, 以调查问题。</span><span class="sxs-lookup"><span data-stu-id="83300-p117">**Track progress** – Track status after you deploy the change. The status will change to **In progress**, and then either **Complete**, or **Failed**. If a deployment fails, a support request is automatically opened for Microsoft Managed Desktop Operations to investigate the issue.</span></span>  
- <span data-ttu-id="83300-158">**请参阅已部署版本**–每个部署的更改都有版本号。</span><span class="sxs-lookup"><span data-stu-id="83300-158">**See version deployed** – Each deployed change has a version number.</span></span>
- <span data-ttu-id="83300-p118">**还原**更改–还原更改将停止当前部署, 并将所有响铃还原为所有已部署到所有环的最后更改。您正在回滚到上一个已知良好的设置值。</span><span class="sxs-lookup"><span data-stu-id="83300-p118">**Revert changes** – Reverting a change stops the current deployment, and reverts all rings to the last changes that was deployed to all rings. You are rolling back to the last-known-good setting value.</span></span>
- <span data-ttu-id="83300-161">**验证更改**-部署完成后, 验证更改是否按预期应用。</span><span class="sxs-lookup"><span data-stu-id="83300-161">**Validate changes** - After the deployment is complete, validate the changes were applied as you expected.</span></span>  

<span data-ttu-id="83300-162">如果部署失败, 或者您无法还原更改, 请使用 Microsoft 托管桌面操作[打开支持请求](admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="83300-162">If a deployment has failed, or you can't revert a change, [open a support request](admin-support.md) with Microsoft Managed Desktop Operations.</span></span> 

<span data-ttu-id="83300-163">有关详细信息, 请参阅[部署和跟踪可配置的设置](config-setting-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="83300-163">For more information, see [Deploy and track configurable settings](config-setting-deploy.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83300-164">其他资源</span><span class="sxs-lookup"><span data-stu-id="83300-164">Additional resources</span></span>
- [<span data-ttu-id="83300-165">可配置的设置参考</span><span class="sxs-lookup"><span data-stu-id="83300-165">Configurable settings reference</span></span>](config-setting-ref.md) 
- [<span data-ttu-id="83300-166">部署可配置的设置</span><span class="sxs-lookup"><span data-stu-id="83300-166">Deploy configurable settings</span></span>](config-setting-deploy.md) 
