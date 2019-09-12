---
title: 步骤 3 - Office 和 LOB 应用交付
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/27/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何交付 Office 和 LOB 应用。
ms.openlocfilehash: 15a3b1730f5e2a62f067f7615d873ad34fa18d9e
ms.sourcegitcommit: 7e806db3d44ec223754efe1e9613b2c7117c4788
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "34814603"
---
# <a name="step-3-office-and-lob-app-delivery"></a><span data-ttu-id="d1d2e-103">步骤 3：Office 和 LOB 应用交付</span><span class="sxs-lookup"><span data-stu-id="d1d2e-103">Step 3: Office and LOB App Delivery</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><span data-ttu-id="d1d2e-104"><strong>步骤 3：Office 和 LOB 应用交付</strong></span><span class="sxs-lookup"><span data-stu-id="d1d2e-104"><strong>Step 3: Office and LOB App Delivery</strong></span></span></p>
<p><span data-ttu-id="d1d2e-p101">确保应用已打包，且可进行自动安装。了解如何使用 Office 365 专业增强版的即点即用打包，通过新方法来配置、交付和持续更新 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-p101">Ensure your apps are packaged and ready for automated installation. Learn how Click-to-Run packaging with Office 365 ProPlus gives you new options to configure, deliver and keep your Office apps up-to-date.</span></span></p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="d1d2e-107">Office 和 LOB 应用交付是我们推荐的部署过程轮中的第三步，其中包括安装和管理 Office 和 LOB 的选项。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-107">Office and LOB App Delivery is the third step in our recommended deployment process wheel covering the options to install and manage Office and LOB.</span></span> <span data-ttu-id="d1d2e-108">为了成功部署，请不要跳过前两个步骤。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-108">For successful deployment do not skip the first two steps.</span></span>  <span data-ttu-id="d1d2e-109">若要查看的完整桌面部署过程，请访问[桌面部署中心](https://aka.ms/HowToShift)。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-109">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="d1d2e-110">现在可以准备好交付 Office 和业务线应用了，可以通过很多方法执行此操作，包括一些令人欣喜不已的新选项。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-110">You are now ready to deliver Office and your Line of Business Apps and there are a number of ways to do this, including some exciting new options.</span></span> <span data-ttu-id="d1d2e-111">尽管某些应用程序仅提供 32 位或 64 位编译版本，但其他应用程序（如 Office 365 专业增强版）提供 32 位和 64 位本机编译代码，你要做出的最大决策就是选择要部署的版本。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-111">While some applications are only available as either a 32-bit or 64-bit compiled version, others such as Office 365 ProPlus, offer both as 32-bit and 64-bit native compiled code, and one of biggest decisions you will make is which version to deploy.</span></span> <span data-ttu-id="d1d2e-112">若要在新设备上利用额外的计算能力和 RAM，Microsoft 建议在没有 32 位依赖项时使用 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-112">To take advantage of additional compute power and RAM on new devices Microsoft recommends using the 64-bit version when there are no 32-bit dependencies.</span></span> <span data-ttu-id="d1d2e-113">若要确定任何与加载项或文件相关的兼容性挑战，建议在继续前重新访问步骤 1 设备和应用程序就绪情况。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-113">To determine any add-in or file-related compatibility challenges you may have it is recommended to revisit Step 1 Device and App Readiness before you continue.</span></span>

<span data-ttu-id="d1d2e-p104">如果没有任何障碍，我们建议部署 64 位版本的所有应用，包括 Microsoft Office。64 位本机编译应用提供最佳性能，并且是最经得起未来考验的选择。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-p104">If nothing is blocking you, we recommend you deploy 64-bit versions of all apps, including Microsoft Office. 64-bit native compiled apps offer the best performance and is the most future-proof choice.</span></span>

<span data-ttu-id="d1d2e-116">在 Windows 上安装应用有很多方法和模型，让我们看看你的交付选项。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-116">There are many methods and models for installing apps on Windows, so let’s look at your delivery options.</span></span>

[<span data-ttu-id="d1d2e-117">Windows 10 应用程序管理</span><span class="sxs-lookup"><span data-stu-id="d1d2e-117">Windows 10 application management</span></span>](https://docs.microsoft.com/zh-CN/windows/application-management/)

## <a name="msi-based-deployments"></a><span data-ttu-id="d1d2e-118">基于 MSI 的部署</span><span class="sxs-lookup"><span data-stu-id="d1d2e-118">MSI-based Deployments</span></span>

<span data-ttu-id="d1d2e-119">对于业务线应用，你可能会使用基于 MSI 的包或可执行文件，并将应用程序安装为 OS 部署任务序列的一部分。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-119">For your line of business apps, you’ll probably use MSI-based packages or executable  and install apps as part of an OS deployment task sequence.</span></span> <span data-ttu-id="d1d2e-120">Windows 10 会继续使用这些包。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-120">Windows 10 continues to work with these packages.</span></span>

<span data-ttu-id="d1d2e-p106">像 System Center Configuration Manager 和 Microsoft Intune 这样的软件部署工具也会被优化以交付 MSI 打包的应用。一旦在 Windows 10 上验证了应用，就可以使用 System Center Configuration Manager (Current Branch) 来交付应用。如果使用 Microsoft Intune 的公司门户，可以扩展可供组织使用的 IT 认可的应用选择，以包括最新应用程序，并且用户可以自行选择他们需要的应用。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-p106">Software deployment tools like System Center Configuration Manager and Microsoft Intune are also optimized to deliver MSI-packaged apps. Once you have validated your apps on Windows 10, you can use System Center Configuration Manager (current branch) for app delivery. If you use the Company Portal in Microsoft Intune you can extend the choice of IT sanctioned apps available to your organization to include the latest applications, and users to self-select what they need.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a><span data-ttu-id="d1d2e-124">电脑成像</span><span class="sxs-lookup"><span data-stu-id="d1d2e-124">PC Imaging</span></span>

<span data-ttu-id="d1d2e-125">应用交付另一个热门方法是电脑成像。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-125">Another popular method of app delivery is PC imaging.</span></span> <span data-ttu-id="d1d2e-126">在这种情况下，应用程序可以通过任务序列安装或在样本 PC 上手动安装，然后在预先安装必选应用程序的情况下捕获系统映像。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-126">In this case, applications are either installed via task sequence or manually on a sample PC, then a system image is captured with the required applications pre-installed.</span></span> <span data-ttu-id="d1d2e-127">构建和捕获的成像方法可以在配置新 PC 时节省时间，但请记住图像中的操作系统和应用程序可能会很快变得陈旧。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-127">The imaging approach to build and capture can save time when provisioning new PCs but remember operating systems and apps within the image can become stale quickly.</span></span> <span data-ttu-id="d1d2e-128">Windows 10 和 Office 365 专业增强版中的累积更新模型可帮助解决此问题，但并未完全消除此问题。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-128">The Cumulative Update model in Windows 10 and Office 365 ProPlus help with this problem, but doesn’t eliminate it completely.</span></span> <span data-ttu-id="d1d2e-129">这就是为什么我们建议使用精简映像方法，这样可以在部署时间从映像外部安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-129">This is why we recommend a thin image approach, where your applications are installed from outside the image at deploy time.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

<span data-ttu-id="d1d2e-130">如果你想在映像中包含 Office 365 专业增强版，请记住，此操作使用基于用户的激活；系统管理员不能预先将其激活。使用 Office 部署工具在正在成像的设备上预安装 Office，并跳过用户登录。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-130">If you do want to include Office 365 ProPlus in your image, remember that this uses a user-based activation; it cannot be pre-activated by the system admin. Use the Office Deployment Tool to pre-install Office on the device you are imaging and skip the user sign-in.</span></span> <span data-ttu-id="d1d2e-131">部署映像后，最终用户可以使用其 Office 365 凭据登录并激活 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-131">Once the image is deployed end users can sign-in using their Office 365 credentials and activate Office 365 ProPlus.</span></span>

[<span data-ttu-id="d1d2e-132">创建安装操作系统的任务序列</span><span class="sxs-lookup"><span data-stu-id="d1d2e-132">Create a Task Sequence to Install an Operating System</span></span>](https://docs.microsoft.com/zh-CN/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

[<span data-ttu-id="d1d2e-133">将 Office 365 专业增强版部署为操作系统映像的一部分</span><span class="sxs-lookup"><span data-stu-id="d1d2e-133">Deploy Office 365 ProPlus as part of an operating system image</span></span>](https://docs.microsoft.com/zh-CN/deployoffice/deploy-office-365-proplus-as-part-of-an-operating-system-image)

## <a name="office-click-to-run"></a><span data-ttu-id="d1d2e-134">Office 即点即用</span><span class="sxs-lookup"><span data-stu-id="d1d2e-134">Office Click-to-Run</span></span> 

<span data-ttu-id="d1d2e-135">使用即点即用安装 Office 365 专业增强版，在即将推出的 Office 2019 for Windows 发行版的每个版本中，即点即用会替换基于 MSI 的打包。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-135">Office 365 ProPlus is installed using Click-to-Run, and Click-to-Run replaces MSI-based packaging in every version of the upcoming Office 2019 release for Windows.</span></span> <span data-ttu-id="d1d2e-136">它带来了许多优点，包括更快的安装、更快且更有效的更新以及更清晰的卸载。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-136">It brings with it a number of advantages, including faster installations, faster and more efficient updating, and cleaner uninstallation.</span></span> 

<span data-ttu-id="d1d2e-137">通过即点即用提供的程序在计算机上的虚拟应用程序环境中执行，因此可以与其他应用程序共存而不会发生冲突；它们作为基于 MSI 的软件包也占用了大约一半的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-137">Programs delivered via Click-to-Run execute in a virtual application environment on your computer and so co-exist with other applications without conflict; they also take about half the disk space they would as an MSI-based package.</span></span> <span data-ttu-id="d1d2e-138">Office 应用程序通过 [Office 部署工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)进行交付和管理，该工具是下载、配置和自定义 Office 应用程序所需的 Office 安装引擎。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-138">Office applications are delivered and managed via the [Office Deployment Tool](https://www.microsoft.com/en-us/download/details.aspx?id=49117) which is the Office setup engine needed to download, configure, and customize your Office apps.</span></span> <span data-ttu-id="d1d2e-139">Office 部署工具读取配置 XML 文件，该文件提供有关如何配置和自定义 Office 安装的元数据说明。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-139">The Office Deployment Tool reads a configuration XML file which provides the metadata instructions on how to configure and customization your Office installation.</span></span>

<span data-ttu-id="d1d2e-140">Microsoft 建议使用 [Office 自定义工具](https://config.office.com/)自定义部署设置并创建配置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-140">Microsoft recommends using the [Office Customization Tool](https://config.office.com/) to customize your deployment settings and create your configuration XML file.</span></span> <span data-ttu-id="d1d2e-141">通过 Office 自定义工具，你可以设置要安装的应用程序和语言、应用程序的更新方式、应用程序首选项以及安装体验设置。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-141">Through the Office Customization Tool you can set which applications and languages will be installed, how the applications will be updated, application preferences, and installation expereince settings.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-7.png)

<span data-ttu-id="d1d2e-p112">如果使用 System Center Configuration Manager，仍然可以使用它来广泛部署 Office 365 专业增强版。System Center Configuration Manager (Current Branch) 为更新的 Office 自定义工具、安装时的即点即用包自定义，以及软件更新管理后安装提供本机支持。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-p112">If you use System Center Configuration Manager, you can still use it for broad deployment of Office 365 ProPlus. System Center Configuration Manager (current branch) has native support for the updated Office Customization Tool, package customization for Click-to-Run at install time, and native support for software update management post installation.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-6.png)

[<span data-ttu-id="d1d2e-144">Office 365 专业增强版部署指南</span><span class="sxs-lookup"><span data-stu-id="d1d2e-144">Deployment Guide for Office 365 ProPlus</span></span>](https://docs.microsoft.com/zh-CN/deployoffice/deployment-guide-for-office-365-proplus)

[<span data-ttu-id="d1d2e-145">在升级到 Office 365 专业增强版时删除 Office 的现有 MSI 版本</span><span class="sxs-lookup"><span data-stu-id="d1d2e-145">Remove existing MSI versions of Office when upgrading to Office 365 ProPlus</span></span>](https://docs.microsoft.com/zh-CN/deployoffice/upgrade-from-msi-version)

[<span data-ttu-id="d1d2e-146">使用 Configuration Manager 管理 Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="d1d2e-146">Manage Office 365 ProPlus with Configuration Manager</span></span>](https://docs.microsoft.com/zh-CN/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[<span data-ttu-id="d1d2e-147">使用 Microsoft Intune 将 Office 365 应用分配到 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d1d2e-147">Assign Office 365 apps to Windows 10 devices with Microsoft Intune</span></span>](https://docs.microsoft.com/zh-CN/intune/apps-add-office365)

## <a name="browser-based-apps"></a><span data-ttu-id="d1d2e-148">基于浏览器的应用程序</span><span class="sxs-lookup"><span data-stu-id="d1d2e-148">Browser-based Apps</span></span>

<span data-ttu-id="d1d2e-p113">为了确保基于浏览器的应用程序能够像预期那样继续工作，需注意一些事项。如果你有特定的网站和应用，你知道它们与 Microsoft Edge 存在兼容性问题，则可以使用企业模式网站列表，这样网站就会使用 Internet Explorer 11 自动打开。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-p113">There are a few things to consider in order to make sure that your browser-based applications continue to work as expected. If you have specific web sites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the web sites will automatically open using Internet Explorer 11.</span></span>

<span data-ttu-id="d1d2e-p114">此外，如果你知道内部网站不能正常使用 Microsoft Edge，则可以设置所有内部网站自动使用 Internet Explorer 11 打开。该过程使用 XML 文件来管理 IE11 是否用于每个网站，使用组策略来强制实施设置。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-p114">Additionally, if you know that your intranet sites aren't going to work properly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. This process uses an XML file to govern whether IE11 is used for each site, using Group Policy to enforce settings.</span></span>

[<span data-ttu-id="d1d2e-153">什么是企业模式</span><span class="sxs-lookup"><span data-stu-id="d1d2e-153">What is Enterprise Mode</span></span>](https://docs.microsoft.com/zh-CN/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

<span data-ttu-id="d1d2e-154">到目前为止，我们已经介绍了众所周知的部署方法。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-154">So far, we have covered well known deployment methods.</span></span> <span data-ttu-id="d1d2e-155">但是，你可能希望考虑两种新的应用程序部署方法。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-155">But there are two new approaches to app deployment you may wish to consider.</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="d1d2e-156">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="d1d2e-156">Microsoft Store for Business</span></span> 

<span data-ttu-id="d1d2e-157">Microsoft Store for Business 提供了一种灵活的方式，可以大规模地发现、获取、管理和分发 Windows 10 设备的免费和付费应用程序。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-157">Microsoft Store for Business provides a flexible way discover, acquire, manage, and distribute free and paid apps to Windows 10 devices at scale.</span></span> <span data-ttu-id="d1d2e-158">作为 IT 管理员，你可以根据需要分配和重新使用许可证的同时，将所选的 Microsoft Store 应用程序以及自定义的应用程序发布到自己的私人商店。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-158">As an IT admin, you can publish selected Microsoft Store apps, along with your custom own apps, to your own private store while assigning and re-using licenses as needed.</span></span> <span data-ttu-id="d1d2e-159">你的用户仅定向到此商店，因此只能查找和安装已批准的应用。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-159">Your users are directed to this store only, and so can only find and install approved apps.</span></span>

<span data-ttu-id="d1d2e-p117">应用商店应用可以在本机构建为 UWP 应用，也可以使用桌面桥重新打包应用商店的现有应用，并为 Windows 10 添加新式体验。除了你用来增强 Windows 10 体验的代码之外，应用程序保持不变，并继续以完全信任的用户模式运行。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-p117">Store apps can be natively built as UWP apps or you can use the Desktop Bridge to repackage your existing apps for the Store and add modern experiences for Windows 10. Aside from the code that you use to light up Windows 10 experiences, your app remains unchanged and continues to run in full-trust user mode.</span></span>

## <a name="msix-containerization"></a><span data-ttu-id="d1d2e-162">MSIX 集装化</span><span class="sxs-lookup"><span data-stu-id="d1d2e-162">MSIX Containerization</span></span>

<span data-ttu-id="d1d2e-163">应用程序包装新选项是 MSIX。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-163">A new option for application packaging is MSIX.</span></span> <span data-ttu-id="d1d2e-164">MSIX 使用 Windows 中提供的集装化技术，汇集了即点即用、UWP 和 MSI 包装的最佳方面。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-164">MSIX uses the containerization technology available in Windows, bringing together the best aspects of Click-to-Run, UWP and MSI packaging.</span></span> <span data-ttu-id="d1d2e-165">借助工具将现有安装程序（如 EXE、MSI、APPV 和 APPX）直接迁移到 MSIX，我们可以看到 MSIX 集装化为当今使用的众多安装技术提供了统一的路径。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-165">With tools to migrate existing installers like EXE, MSI, APPV and APPX directly to MSIX we see MSIX Containerization provides a unifed path for the many installation technologies in use today.</span></span> <span data-ttu-id="d1d2e-166">MSIX 支持包含在当前版本的 Windows 中：运行 Windows 10 RS5 或更新版本的任何设备都包含安装和运行 MSIX 打包应用程序所需的一切。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-166">MSIX support is included in current versions of Windows: any device running Windows 10 RS5 or newer includes everything you need to install and run MSIX packaged apps.</span></span> <span data-ttu-id="d1d2e-167">Windows 10 动态集成了它接收的 MSIX 容器，同时使应用程序与操作系统分离。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-167">Windows 10 dynamically integrates MSIX containers it receives, while keeping the applications separate from the operating system.</span></span>

<span data-ttu-id="d1d2e-p119">集装化指的是完全卸载和删除包，不像今天的许多 MSI 和基于 EXE 的包，它们可能会在系统上有残留项。它还意味着只需要标准的用户凭证即可安装应用程序 - 不需要使用管理员凭证来安装 MSIX 容器。此外，MSIX 容器的更新效率更高。当更新发布时，使用块级别差异意味着只应用新的二进制文件，从而减少更新有效负载，以便实现更快部署而减少网络带宽的使用。</span><span class="sxs-lookup"><span data-stu-id="d1d2e-p119">Containerization means clean uninstall and removal of packages, unlike a lot of MSI and EXE-based packages today that may leave items on the system. It also means only needing Standard User credentials to install applications – you do not have to have Administrator credentials to install MSIX containers. MSIX containers are more efficient to update too. When an update is published, use of block level differentials means only net new binaries are applied, reducing the update payload, for faster deployments consuming less network bandwidth.</span></span>

<span data-ttu-id="d1d2e-172">有关 MSIX 的详细信息，请访问 [MSIX 技术社区网站](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)</span><span class="sxs-lookup"><span data-stu-id="d1d2e-172">You can find more information on MSIX via the [MSIX Tech Community site](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)</span></span>

## <a name="next-step"></a><span data-ttu-id="d1d2e-173">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d1d2e-173">Next Step</span></span>

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[<span data-ttu-id="d1d2e-174">步骤 4：用户文件和设置</span><span class="sxs-lookup"><span data-stu-id="d1d2e-174">Step 4: User Files and Settings</span></span>](https://aka.ms/mdd4)

## <a name="previous-step"></a><span data-ttu-id="d1d2e-175">上一步</span><span class="sxs-lookup"><span data-stu-id="d1d2e-175">Previous Step</span></span>

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="d1d2e-176">步骤 2：目录和网络就绪情况</span><span class="sxs-lookup"><span data-stu-id="d1d2e-176">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2) 