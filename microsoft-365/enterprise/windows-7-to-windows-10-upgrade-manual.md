---
title: Windows 7 到 Windows 10 手动升级指南
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows 7 到 Windows 10 手动升级指南。
ms.openlocfilehash: f148815a72c9315db2a6d55f7b8433cc9dddf448
ms.sourcegitcommit: 12c4d5444d6e0e8825fc85e3e8453fa376746495
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2019
ms.locfileid: "35395244"
---
# <a name="windows-7-to-windows-10-manual-upgrade-step-by-step-guide"></a><span data-ttu-id="b9568-103">Windows 7 到 Windows 10 手动升级分步指南</span><span class="sxs-lookup"><span data-stu-id="b9568-103">Windows 7 to Windows 10 manual upgrade step-by-step guide</span></span>

<span data-ttu-id="b9568-104">本文介绍将 Windows 7 企业版电脑手动升级到 Windows 10 企业版的过程。</span><span class="sxs-lookup"><span data-stu-id="b9568-104">This article describes the process to manually upgrade a Windows 7 Enterprise PC to Windows 10 Enterprise.</span></span> <span data-ttu-id="b9568-105">对于其他 Windows 7 版本（如家庭版和专业版），该过程非常类似，但你也可以选择直接使用媒体创建工具进行升级。</span><span class="sxs-lookup"><span data-stu-id="b9568-105">For other Windows 7 editions, such as Home and Professional, the process is very similar, but you also have the option to upgrade directly using the media creation tool.</span></span> <span data-ttu-id="b9568-106">将 Windows 7 的任何版本升级到 Windows 10 将需要有效的产品密钥以及匹配的或更高版本的 Windows，例如 Windows 7 专业版可以升级到 Windows 10 专业版，但无法升级到 Windows 10 家庭版。</span><span class="sxs-lookup"><span data-stu-id="b9568-106">Upgrades for any edition of Windows 7 to Windows 10 will require a valid product key and matching or higher edition of Windows, for example Windows 7 Professional can upgrade to Windows 10 Pro, but cannot be upgraded to Windows 10 Home.</span></span> <span data-ttu-id="b9568-107">Windows 7 旗舰版将需要升级到 Windows 10 专业版。</span><span class="sxs-lookup"><span data-stu-id="b9568-107">Windows 7 Ultimate will need to be upgraded to Windows 10 Pro.</span></span>

## <a name="windows-10-upgrades-using-the-media-creation-tool-or-iso-files"></a><span data-ttu-id="b9568-108">使用媒体创建工具或 ISO 文件进行的 Windows 10 升级</span><span class="sxs-lookup"><span data-stu-id="b9568-108">Windows 10 upgrades using the media creation tool or ISO files</span></span>

<span data-ttu-id="b9568-109">可使用[媒体创建工具](https://www.microsoft.com/en-us/software-download/windows10ISO)直接升级到 Windows 10，或使用该工具将 Windows 10 下载为 ISO 文件。</span><span class="sxs-lookup"><span data-stu-id="b9568-109">You can upgrade to Windows 10 directly using the [media creation tool](https://www.microsoft.com/en-us/software-download/windows10ISO) or use it to download Windows 10 as an ISO file.</span></span> <span data-ttu-id="b9568-110">需要注意当前系统是 32 位还是 64 位、系统的默认语言以及 Windows 7 版本（例如家庭版、专业版还是企业版）。</span><span class="sxs-lookup"><span data-stu-id="b9568-110">You’ll need to note whether your current system is 32 or 64-bit, your system’s default language and edition of Windows 7 (e.g. Home, Professional, or Enterprise).</span></span> <span data-ttu-id="b9568-111">在 Windows 7 中，此信息位于“控制面板”\>“系统和安全”\>“系统”中。</span><span class="sxs-lookup"><span data-stu-id="b9568-111">In Windows 7, this information is located in the Control Panel \> System and Security \> System.</span></span> <span data-ttu-id="b9568-112">媒体创建工具不支持 Windows 10 企业版的升级、创建安装媒体和下载 ISO 文件。</span><span class="sxs-lookup"><span data-stu-id="b9568-112">The media creation tool does not support Windows 10 Enterprise for upgrades, creating installation media or downloading ISO files.</span></span> <span data-ttu-id="b9568-113">如果要从 Windows 7 企业版升级，则需要 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="b9568-113">Windows 10 Enterprise is required if you are upgrading from Windows 7 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-1.png)

<span data-ttu-id="b9568-114">从 Windows 7 企业版升级到 Windows 10 企业版时，需要从[批量许可服务中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)下载你的语言和体系结构（32 位或 64 位）所对应的 ISO 文件。</span><span class="sxs-lookup"><span data-stu-id="b9568-114">When upgrading from Windows 7 Enterprise to Windows 10 Enterprise, you’ll need to download the ISO file for your language and architecture (32-bit or 64-bit) from the [Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

<span data-ttu-id="b9568-115">如果计划使用 ISO 文件执行升级，则需要将 ISO 中的文件提取到本地文件系统、可移动驱动器或者也可将 ISO 文件刻录到 DVD。</span><span class="sxs-lookup"><span data-stu-id="b9568-115">If you plan to perform the upgrade using an ISO file, you will need to extract the files within the ISO to either your local file system, to a removable drive, or you can burn the ISO file to a DVD.</span></span> <span data-ttu-id="b9568-116">可使用 Windows 8 或更高版本的电脑提取 ISO 中的安装文件，并将这些文件保存到可移动 USB 存储设备，或使用应用程序（例如 [7zip](https://www.7-zip.org/)）将 ISO 文件的内容提取到 Windows 7 系统本地驱动器上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b9568-116">You can extract the installation files within the ISO using a Windows 8 or newer PC and save these files to removable USB storage or use an application such as [7zip](https://www.7-zip.org/) to extract the contents of your ISO file to a folder on your local drive within Windows 7.</span></span>

<span data-ttu-id="b9568-117">安装媒体在 Windows 7 中可用后，可通过如下所示的方式运行 setup.exe 来启动升级。</span><span class="sxs-lookup"><span data-stu-id="b9568-117">Once you have the install media available in Windows 7, you can initiate the upgrade by running setup.exe as shown below.</span></span>

<span data-ttu-id="b9568-118">**重要提示：对于就地升级（将应用程序和数据迁移到 Window 10），需要从正在运行的 Windows 7 会话中启动该过程。从 DVD 或 USB 驱动器启动到安装媒体不会提供保留应用和文件的选项，而是执行 Windows 10 的全新安装。**</span><span class="sxs-lookup"><span data-stu-id="b9568-118">**Important tip: For an in-place upgrade where applications and your data are migrated to Window 10, you’ll need to initiate the process from within a running Windows 7 session. Booting to install media from a DVD or USB drive will not give you the option to keep your apps and files, instead it will perform a clean install of Windows 10.**</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-2.png)

<span data-ttu-id="b9568-119">在 Windows 10 安装程序中将引导你完成安装过程，第一个屏幕会提供下载更新、驱动程序和可选功能的选项。</span><span class="sxs-lookup"><span data-stu-id="b9568-119">Within Windows 10 Setup, you will be guided through the installation process and the first screen provides an option to download updates, drivers and optional features.</span></span> <span data-ttu-id="b9568-120">为帮助确保升级成功，建议执行此操作</span><span class="sxs-lookup"><span data-stu-id="b9568-120">This is recommended to help ensure success with the upgrade</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-3.png)

<span data-ttu-id="b9568-121">应用更新后，Windows 10 安装程序将进入下一阶段：选择映像。</span><span class="sxs-lookup"><span data-stu-id="b9568-121">Once updates have been applied, Windows 10 Setup will move to the next phase, Select Image.</span></span> <span data-ttu-id="b9568-122">在阶段，你需要选择 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="b9568-122">Here, you will need to select your edition of Windows.</span></span> <span data-ttu-id="b9568-123">在此情况下，由于电脑安装了 Windows 7 企业版，因此应选择 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="b9568-123">In this case, since the PC has Windows 7 Enterprise installed, you would select Windows 10 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-4.png)

<span data-ttu-id="b9568-124">在 Windows 10 程序的下一个屏幕中将显示适用的通知和许可条款。</span><span class="sxs-lookup"><span data-stu-id="b9568-124">In the next screen in Windows 10 Setup, you’re presented with applicable notices and license terms.</span></span> <span data-ttu-id="b9568-125">阅读并理解通知和条款后，单击“接受”继续，或单击“拒绝”取消。</span><span class="sxs-lookup"><span data-stu-id="b9568-125">Once you have read and understand the notices and terms, click “Accept” to continue or “Decline” to cancel.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-5.png)

<span data-ttu-id="b9568-126">现在，Windows 10 安装程序将查找其他更新。</span><span class="sxs-lookup"><span data-stu-id="b9568-126">Now Windows 10 Setup will look for additional updates.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-6.png)

<span data-ttu-id="b9568-127">完成后，Windows 10 安装程序即准备好执行安装，默认情况下配置为安装 Windows 10 并保留你的个人文件和应用。</span><span class="sxs-lookup"><span data-stu-id="b9568-127">Once complete, Windows 10 Setup is ready to install and by default is configured to install Windows 10 and keep your personal files and apps installed.</span></span> <span data-ttu-id="b9568-128">这是推荐的选项。</span><span class="sxs-lookup"><span data-stu-id="b9568-128">This is the recommended option.</span></span> <span data-ttu-id="b9568-129">单击“更改要保留的内容”可发现其他选项。</span><span class="sxs-lookup"><span data-stu-id="b9568-129">By clicking, “Change what to keep,” you’ll find additional options.</span></span> <span data-ttu-id="b9568-130">否则，单击“安装”。</span><span class="sxs-lookup"><span data-stu-id="b9568-130">Otherwise, click “Install.”</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-7.png)

<span data-ttu-id="b9568-131">如果选择“更改要保留的内容”，则会显示以下选项：</span><span class="sxs-lookup"><span data-stu-id="b9568-131">If you select “Change what to keep”, you’ll be presented with these options:</span></span>

<span data-ttu-id="b9568-132">“仅保留个人文件”不会将已安装的应用或设置从 Windows 7 移动到 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="b9568-132">“Keep personal files only” will not move your installed apps or settings from Windows 7 to Windows 10.</span></span> <span data-ttu-id="b9568-133">只会将文件和用户帐户移动到 Windows。</span><span class="sxs-lookup"><span data-stu-id="b9568-133">Instead it will only move your files and user accounts to Windows.</span></span> <span data-ttu-id="b9568-134">如果使用此选项，稍后将需要重新安装应用。</span><span class="sxs-lookup"><span data-stu-id="b9568-134">Apps will need to be reinstalled later with this option.</span></span> <span data-ttu-id="b9568-135">仅当你确信自己可以在安装 Windows 后重新安装和配置所需的应用程序，才应使用此选项，否则请保留默认的“保留个人文件和应用”选项。</span><span class="sxs-lookup"><span data-stu-id="b9568-135">Only use this option if you are confident you can reinstall and configure the apps you will need after Windows is installed, otherwise stick with the default “Keep personal files and apps” option.</span></span>

<span data-ttu-id="b9568-136">“无”将删除文件、应用和设置，并执行 Windows 全新安装。</span><span class="sxs-lookup"><span data-stu-id="b9568-136">“Nothing” will delete your files, apps and settings and perform a clean install of Windows.</span></span> <span data-ttu-id="b9568-137">仅当你事先备份了想要保留的数据并能重新安装应用时，才应使用此选项。</span><span class="sxs-lookup"><span data-stu-id="b9568-137">Use this option only if you have previously backed up the data you want to keep and you are able to reinstall your apps.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-8.png)

<span data-ttu-id="b9568-138">现在，Windows 10 安装程序将根据上一个屏幕中的选择再次获取更新。</span><span class="sxs-lookup"><span data-stu-id="b9568-138">Now Windows 10 Setup will get updates again based on what you selected in the previous screen.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-9.png)

<span data-ttu-id="b9568-139">现在，Windows 10 将安装几分钟时间，如果你选择了保留你的个人文件和应用，则所有内容都将位于相同的文件位置，并且你的应用现在将在 Windows 10 中可用。</span><span class="sxs-lookup"><span data-stu-id="b9568-139">Now Windows 10 will install for several minutes and if you chose to keep your personal files and apps, everything will be in the same file locations and your apps will now be available in Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-10.png)

## 

## <a name="recovery-in-windows-10"></a><span data-ttu-id="b9568-140">Windows 10 中的恢复</span><span class="sxs-lookup"><span data-stu-id="b9568-140">Recovery in Windows 10</span></span>

<span data-ttu-id="b9568-141">安装 Windows 10 之后，Windows 10 中的恢复选项为你提供长达 10 天的时间，在这段时间内允许你恢复到 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="b9568-141">After Windows 10 is installed, the Recovery option in Windows 10 gives you up to 10 days to go back to Windows 7.</span></span> <span data-ttu-id="b9568-142">如果系统上的设备或应用无法正常工作，而需要回退到以前的 Windows 7 安装，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="b9568-142">This is useful if a device or app on your system does not function properly and you need to go back to your previous Windows 7 installation.</span></span> <span data-ttu-id="b9568-143">10 天过后，默认情况下，Windows 10 将释放硬盘上由 Windows 7 恢复文件所占用的空间，并从以前的安装中删除文件。</span><span class="sxs-lookup"><span data-stu-id="b9568-143">After 10 days, by default Windows 10 will free up the space consumed by your Windows 7 recovery files on your hard drive and delete files from the previous installation.</span></span> <span data-ttu-id="b9568-144">虽然此时间过后会删除 Windows 7，并且不能还原 Windows 7，但你的应用和个人文件将保留在 Windows 10 中。</span><span class="sxs-lookup"><span data-stu-id="b9568-144">Although Windows 7 after this time is deleted and you won’t be able to revert Windows 7, your apps and personal files will remain in Windows 10.</span></span>

<span data-ttu-id="b9568-145">若要启动“回退到 Windows 7”过程，请导航到“设置”\>“更新和安全”\>“恢复”。</span><span class="sxs-lookup"><span data-stu-id="b9568-145">To start the Go back to Windows 7 process, navigate to Settings \> Update & Security \> Recovery.</span></span> <span data-ttu-id="b9568-146">在“回退到 Windows 7”下，选择“开始”。</span><span class="sxs-lookup"><span data-stu-id="b9568-146">Under Go back to Windows 7, select “Get started.”</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-11.png)

<span data-ttu-id="b9568-147">现在，Windows 10 将询问你回退的原因。</span><span class="sxs-lookup"><span data-stu-id="b9568-147">Now, Windows 10 will ask why you are going back.</span></span> <span data-ttu-id="b9568-148">如果有技术方面的原因，为了帮助推动该问题的解决并确保其他人可以从你的体验中获益，填写此信息会很有用。</span><span class="sxs-lookup"><span data-stu-id="b9568-148">If there is a technical reason, this is useful to fill out in order to help drive resolution and ensure others can benefit from your experience.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-12.png)

<span data-ttu-id="b9568-149">在许多情况下，你的 Windows 10 版本已发布更新，这可能会解决技术问题。</span><span class="sxs-lookup"><span data-stu-id="b9568-149">In many cases, your version of Windows 10 will have had updates issued, which may resolve technical issues.</span></span> <span data-ttu-id="b9568-150">建议检查更新，如果找到并安装更新，请检查是否修复了所遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="b9568-150">It is encouraged that you check for updates and if found and installed, then check if that fixes the problems you have experienced.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-13.png)

<span data-ttu-id="b9568-151">如果更新未能解决问题，并确实需要还原到以前的 Windows 7 安装，则有可能需要重新安装某些应用（例如在运行 Windows 10 的时间内安装的任何应用），且某些设置可能丢失。</span><span class="sxs-lookup"><span data-stu-id="b9568-151">If the updates do not resolve issues and you do need to revert to your previous installation of Windows 7, there is a chance that some apps will need to be reinstalled – such as any app that installed during the time you were running Windows 10 – and some settings may be lost.</span></span> <span data-ttu-id="b9568-152">重要的是，你在使用 Windows 10 时保存在本地的文件和文档将保留，并在回退到 Windows 7 后可供你使用。</span><span class="sxs-lookup"><span data-stu-id="b9568-152">Importantly, files and docs you’ve saved locally while using Windows 10 will remain and be available for you once you’re back in Windows 7.</span></span> 

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-14.png)

<span data-ttu-id="b9568-153">在开始之前，请确保已准备好先前 Windows 7 安装中的本地或域帐户和密码。</span><span class="sxs-lookup"><span data-stu-id="b9568-153">Before you get started, make sure you have a local or domain account and password ready from the previous Windows 7 installation.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-15.png)

<span data-ttu-id="b9568-154">此后即可启动回退到 Windows 7 的过程。</span><span class="sxs-lookup"><span data-stu-id="b9568-154">From here you can initiate the process to go back to Windows 7.</span></span> <span data-ttu-id="b9568-155">几分钟后，电脑将启动到恢复后的 Windows 7，并拥有升级到 Windows 10 之前的相同体验。</span><span class="sxs-lookup"><span data-stu-id="b9568-155">After a few minutes, your PC will boot back into Windows 7 with the same experience prior to upgrading to Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-manual-media/windows-7-to-windows-10-upgrade-manual-media-16.png)

## <a name="moving-to-windows-10-on-a-new-pc"></a><span data-ttu-id="b9568-156">移动到新电脑上的 Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9568-156">Moving to Windows 10 on a new PC</span></span>

<span data-ttu-id="b9568-157">另一个建议的选择是移动新电脑上的 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="b9568-157">Another recommended option is to move to Windows 10 on a new PC.</span></span> <span data-ttu-id="b9568-158">如果这是你的首选项，你可以使用 [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10) 备份、[Windows 中内置的“备份和还原”](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10)、使用[外部存储设备](https://support.microsoft.com/en-us/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10)以手动操作方式或类似 [Laplink 的 PCmover Express](https://www.microsoft.com/en-us/windows/transfer-your-data) 之类的工具从旧计算机传送文件。</span><span class="sxs-lookup"><span data-stu-id="b9568-158">If this is your preference, you can transfer your files from your old computer using [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10) backup, [Backup and Restore built into Windows](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10), manually using an [external storage device](https://support.microsoft.com/en-us/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10), or tools like [Laplink’s PCmover Express](https://www.microsoft.com/en-us/windows/transfer-your-data).</span></span> <span data-ttu-id="b9568-159">无论使用哪种方法，仍然需要重新安装未包含在 Windows 10 中的任何所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9568-159">With any of these options, you will still need to re-install any required applications not included with Windows 10.</span></span> <span data-ttu-id="b9568-160">若要深入了解以手动方式从运行 Windows 7 的现有电脑移动到运行 Windows 10 的新电脑时可用的选项，请参阅 Windows 支持中的[移动到 Windows 10 电脑](https://support.microsoft.com/en-us/help/4229823?ocid=MoveToWindows10)。</span><span class="sxs-lookup"><span data-stu-id="b9568-160">To learn more about your options for manually moving from an existing PC running Windows 7 to a new PC with Windows 10, see [Moving to a Windows 10 PC](https://support.microsoft.com/en-us/help/4229823?ocid=MoveToWindows10) in Windows Support.</span></span>

## <a name="desktop-deployment-centerhttpsakamshowtoshift"></a>[<span data-ttu-id="b9568-161">桌面部署中心</span><span class="sxs-lookup"><span data-stu-id="b9568-161">Desktop Deployment Center</span></span>](https://aka.ms/howtoshift)