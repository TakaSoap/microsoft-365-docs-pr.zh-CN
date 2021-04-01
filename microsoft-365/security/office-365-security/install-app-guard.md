---
title: Office 365 管理员应用程序防护
keywords: 应用程序防护， 保护， 隔离， 隔离容器， 硬件隔离
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 获取基于硬件的最新隔离。 防止当前和新出现的攻击（如攻击或恶意链接）干扰员工工作效率和企业安全。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0fa6ad884c6b21457c8359cf82e32e4b8c100ba
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488307"
---
# <a name="application-guard-for-office-for-admins"></a><span data-ttu-id="89b53-105">适用于管理员的 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="89b53-105">Application Guard for Office for admins</span></span>

<span data-ttu-id="89b53-106">**适用于：** Word、Excel 和 PowerPoint for Microsoft 365、Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="89b53-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

<span data-ttu-id="89b53-107">适用于 Office 的 Microsoft Defender 应用程序防护 (Office 应用程序防护) 有助于防止不受信任的文件访问受信任资源，使企业避免受到新的和新出现的攻击。</span><span class="sxs-lookup"><span data-stu-id="89b53-107">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="89b53-108">本文将指导管理员设置设备以预览 Office 应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="89b53-108">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="89b53-109">它提供有关在设备上启用 Office 应用程序防护的系统要求和安装步骤的信息。</span><span class="sxs-lookup"><span data-stu-id="89b53-109">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="89b53-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="89b53-110">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="89b53-111">最低硬件要求</span><span class="sxs-lookup"><span data-stu-id="89b53-111">Minimum hardware requirements</span></span>

* <span data-ttu-id="89b53-112">CPU：64 位、4 核 (物理或虚拟) 、虚拟化扩展 (Intel VT-x OR AMD-V) 、Core i5 等效项或更高建议</span><span class="sxs-lookup"><span data-stu-id="89b53-112">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="89b53-113">**物理内存**：8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="89b53-113">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="89b53-114">**硬盘：** 系统驱动器上 10 GB 的可用空间 (SSD) </span><span class="sxs-lookup"><span data-stu-id="89b53-114">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="89b53-115">最低软件要求</span><span class="sxs-lookup"><span data-stu-id="89b53-115">Minimum software requirements</span></span>

* <span data-ttu-id="89b53-116">**Windows 10：Windows** 10 企业版、客户端内部版本 2004 (20H1) 版本 19041 或更高版本</span><span class="sxs-lookup"><span data-stu-id="89b53-116">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041 or later</span></span>
* <span data-ttu-id="89b53-117">**Office：Office** Current Channel 和每月企业频道，内部版本 2011 16.0.13530.10000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="89b53-117">**Office**: Office Current Channel and Monthly Enterprise Channel, Build version 2011 16.0.13530.10000 or later.</span></span> <span data-ttu-id="89b53-118">支持 32 位和 64 位版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="89b53-118">Both 32-bit and 64-bit versions of Office are supported.</span></span>
* <span data-ttu-id="89b53-119">**更新程序包**：Windows 10 累积每月安全更新 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="89b53-119">**Update package**: Windows 10 cumulative monthly security update [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="89b53-120">有关详细的系统要求，请参阅 [Microsoft Defender 应用程序防护的系统要求](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="89b53-120">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="89b53-121">此外，请参阅计算机制造商的指南，了解如何启用虚拟化技术。</span><span class="sxs-lookup"><span data-stu-id="89b53-121">Also, please refer to your computer manufacturer's guides on how to enable virtualization technology.</span></span>
<span data-ttu-id="89b53-122">若要详细了解 Office 更新频道，请参阅 [Microsoft 365 更新频道概述](/deployoffice/overview-update-channels)。</span><span class="sxs-lookup"><span data-stu-id="89b53-122">To learn more about Office update channels, see [Overview of update channels for Microsoft 365](/deployoffice/overview-update-channels).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="89b53-123">许可要求</span><span class="sxs-lookup"><span data-stu-id="89b53-123">Licensing requirements</span></span>

* <span data-ttu-id="89b53-124">Microsoft 365 E5 或 Microsoft 365 E5 安全中心</span><span class="sxs-lookup"><span data-stu-id="89b53-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="89b53-125">部署 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="89b53-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="89b53-126">启用 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="89b53-126">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="89b53-127">下载并安装 **Windows 10 累积每月安全更新 KB4571756。**</span><span class="sxs-lookup"><span data-stu-id="89b53-127">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="89b53-128">在 **Windows 功能下选择 Microsoft Defender 应用程序** 防护，然后选择确定。 </span><span class="sxs-lookup"><span data-stu-id="89b53-128">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="89b53-129">启用应用程序防护功能将提示重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="89b53-129">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="89b53-130">可以选择立即重启，也可以选择在步骤 3 之后重新启动。</span><span class="sxs-lookup"><span data-stu-id="89b53-130">You can choose to reboot now or after step 3.</span></span>

   ![显示 AG 的 Windows 功能对话框](../../media/ag03-deploy.png)

   <span data-ttu-id="89b53-132">还可以以管理员角色运行以下 PowerShell 命令来启用该功能：</span><span class="sxs-lookup"><span data-stu-id="89b53-132">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="89b53-133">在托管模式下搜索 **Microsoft Defender 应用程序防护**，计算机配置 管理模板 **Windows 组件 Microsoft Defender \\ 应用程序防护 中的 \\ \\ 组策略**。</span><span class="sxs-lookup"><span data-stu-id="89b53-133">Search for **Microsoft Defender Application Guard in Managed Mode**, a group policy in **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="89b53-134">打开此策略，将选项下的值设置为 **2** 或 **3，** 然后选择确定 **或\*\*\*\*应用**。</span><span class="sxs-lookup"><span data-stu-id="89b53-134">Turn on this policy by setting the value under Options as **2** or **3**, and then selecting **OK** or **Apply**.</span></span>

   ![在托管模式下打开 AG](../../media/ag04-deploy.png)

   <span data-ttu-id="89b53-136">相反，你可以设置相应的云解决方案提供商策略：</span><span class="sxs-lookup"><span data-stu-id="89b53-136">Instead, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="89b53-137">**OMA-URI：./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="89b53-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="89b53-138">数据类型 **：Integer**</span><span class="sxs-lookup"><span data-stu-id="89b53-138">Data type: **Integer**</span></span> <br> <span data-ttu-id="89b53-139">值 **：2**</span><span class="sxs-lookup"><span data-stu-id="89b53-139">Value: **2**</span></span>

4. <span data-ttu-id="89b53-140">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="89b53-140">Restart the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="89b53-141">设置诊断&反馈以发送完整数据</span><span class="sxs-lookup"><span data-stu-id="89b53-141">Set Diagnostics & feedback to send full data</span></span>

> [!NOTE]
> <span data-ttu-id="89b53-142">但是，这不是必需的，配置可选诊断数据将有助于诊断报告的问题。</span><span class="sxs-lookup"><span data-stu-id="89b53-142">This is not required, however, configuring optional diagnostics data will help diagnose reported issues.</span></span>

<span data-ttu-id="89b53-143">此步骤确保识别并解决问题所需的数据已到达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="89b53-143">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="89b53-144">请按照以下步骤在 Windows 设备上启用诊断：</span><span class="sxs-lookup"><span data-stu-id="89b53-144">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="89b53-145">从 **"开始** "菜单中打开"设置"。</span><span class="sxs-lookup"><span data-stu-id="89b53-145">Open **Settings** from the Start menu.</span></span>

   ![“开始”菜单](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="89b53-147">在 **"Windows 设置"** 上，选择"**隐私"。**</span><span class="sxs-lookup"><span data-stu-id="89b53-147">On **Windows Settings**, select **Privacy**.</span></span>

   ![Windows 设置菜单](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="89b53-149">在"隐私"下 **，选择"诊断&反馈"，** 然后选择 **"可选诊断数据"。**</span><span class="sxs-lookup"><span data-stu-id="89b53-149">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![诊断和反馈菜单](../../media/ag07a-diagnostic.png)

<span data-ttu-id="89b53-151">有关配置 Windows 诊断设置的信息，请参阅在组织中配置 [Windows 诊断数据](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。</span><span class="sxs-lookup"><span data-stu-id="89b53-151">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="89b53-152">确认 Office 应用程序防护已启用且正常工作</span><span class="sxs-lookup"><span data-stu-id="89b53-152">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="89b53-153">在确认 Office 相关应用程序防护已启用之前，在已部署策略的设备上启动 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="89b53-153">Before confirming that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="89b53-154">确保 Office 已激活。</span><span class="sxs-lookup"><span data-stu-id="89b53-154">Make sure Office is activated.</span></span> <span data-ttu-id="89b53-155">你可能需要先使用你的工作标识激活 Office 产品。</span><span class="sxs-lookup"><span data-stu-id="89b53-155">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="89b53-156">若要确认 Office 应用程序防护已启用，请启动 Word、Excel 或 PowerPoint，然后打开不受信任的文档。</span><span class="sxs-lookup"><span data-stu-id="89b53-156">To confirm that Application Guard for Office is enabled, launch Word, Excel, or PowerPoint, and then open an untrusted document.</span></span> <span data-ttu-id="89b53-157">例如，可以打开从 Internet 下载的文档或组织外部人员的电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="89b53-157">For example, you can open a document that was downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="89b53-158">首次打开不受信任的文件时，可能会看到 Office 初始屏幕，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="89b53-158">When you first open an untrusted file, you may see an Office splash screen like the following example.</span></span> <span data-ttu-id="89b53-159">它可能在 Office 应用程序防护被激活和文件打开时显示一段时间。</span><span class="sxs-lookup"><span data-stu-id="89b53-159">It might be displayed for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="89b53-160">随后打开不受信任的文件应更快。</span><span class="sxs-lookup"><span data-stu-id="89b53-160">Subsequent openings of untrusted files should be faster.</span></span>

![Office 应用初始屏幕](../../media/ag08-confirm.png)

<span data-ttu-id="89b53-162">打开后，文件应显示几个可视指示器，指示文件是在 Office 应用程序防护内打开的：</span><span class="sxs-lookup"><span data-stu-id="89b53-162">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="89b53-163">功能区中的标注</span><span class="sxs-lookup"><span data-stu-id="89b53-163">A callout in the ribbon</span></span>

  ![显示小 App Guard 注释的文档文件](../../media/ag09-confirm.png)

* <span data-ttu-id="89b53-165">任务栏中带防护的应用程序图标</span><span class="sxs-lookup"><span data-stu-id="89b53-165">The application icon with a shield in the taskbar</span></span>

  ![任务栏中的图标](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="89b53-167">为 Office 配置应用程序防护</span><span class="sxs-lookup"><span data-stu-id="89b53-167">Configure Application Guard for Office</span></span>

<span data-ttu-id="89b53-168">Office 支持以下策略，以使您能够配置 Office 应用程序防护的功能。</span><span class="sxs-lookup"><span data-stu-id="89b53-168">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="89b53-169">可以通过组策略或 Office 云策略服务 [配置这些策略](/DeployOffice/overview-office-cloud-policy-service)。</span><span class="sxs-lookup"><span data-stu-id="89b53-169">These policies can be configured through Group policies or through the [Office cloud policy service](/DeployOffice/overview-office-cloud-policy-service).</span></span>
<span data-ttu-id="89b53-170">查看 User  **Configuration \\ Administrative Templates Microsoft Office \\ 2016 Security Settings Trust Center \\ Application \\ \\ Guard** 中的组策略设置，查看管理员设置的配置。</span><span class="sxs-lookup"><span data-stu-id="89b53-170">See configuration set by your administrator by reviewing group policy settings in  **User Configuration\\Administrative Templates\\Microsoft Office 2016\\Security Settings\\Trust Center\\Application Guard**.</span></span>


> [!NOTE]
> <span data-ttu-id="89b53-171">配置这些策略可以禁用在 Office 相关应用程序防护中打开的文件的一些功能。</span><span class="sxs-lookup"><span data-stu-id="89b53-171">Configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="89b53-172">Policy</span><span class="sxs-lookup"><span data-stu-id="89b53-172">Policy</span></span>|<span data-ttu-id="89b53-173">说明</span><span class="sxs-lookup"><span data-stu-id="89b53-173">Description</span></span>|
|---|---|
|<span data-ttu-id="89b53-174">请勿使用 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="89b53-174">Don't use Application Guard for Office</span></span>|<span data-ttu-id="89b53-175">启用此策略将强制 Word、Excel 和 PowerPoint 使用受保护的视图隔离容器，而不是 Office 应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="89b53-175">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="89b53-176">当为 Microsoft Edge 启用此策略时，当存在问题时，可以使用此策略临时禁用 Office 应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="89b53-176">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Microsoft Edge.</span></span>|
|<span data-ttu-id="89b53-177">为 Office 容器预创建配置应用程序防护</span><span class="sxs-lookup"><span data-stu-id="89b53-177">Configure Application Guard for Office container pre-creation</span></span>|<span data-ttu-id="89b53-178">此策略确定是否预先创建 Office 应用程序防护容器（用于隔离不受信任的文件）以提高运行时性能。</span><span class="sxs-lookup"><span data-stu-id="89b53-178">This policy determines if the Application Guard for Office container, for isolating untrusted files, is pre-created for improved run-time performance.</span></span> <span data-ttu-id="89b53-179">如果启用此设置，可以指定继续预创建容器的天数，或允许 Office 内置启发式预创建容器。</span><span class="sxs-lookup"><span data-stu-id="89b53-179">If you enable this setting, you can specify the number of days to continue pre-creating a container or let the Office built-in heuristic pre-create the container.</span></span>
|<span data-ttu-id="89b53-180">不允许复制/粘贴在 Office 相关应用程序防护中打开的 Office 文档</span><span class="sxs-lookup"><span data-stu-id="89b53-180">Don't allow copy/paste for Office documents opened in Application Guard for Office</span></span>|<span data-ttu-id="89b53-181">启用此策略将阻止用户将内容从在 Office 应用程序防护中打开的文档复制并粘贴到其外部打开的文档。</span><span class="sxs-lookup"><span data-stu-id="89b53-181">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside of it.</span></span>|
|<span data-ttu-id="89b53-182">在 Office 应用程序防护中禁用硬件加速</span><span class="sxs-lookup"><span data-stu-id="89b53-182">Disable hardware acceleration in Application Guard for Office</span></span>|<span data-ttu-id="89b53-183">此策略控制 Office 应用程序防护是否使用硬件加速来呈现图形。</span><span class="sxs-lookup"><span data-stu-id="89b53-183">This policy controls whether Application Guard for Office uses hardware acceleration to render graphics.</span></span> <span data-ttu-id="89b53-184">如果启用此设置，Office 应用程序防护将使用基于软件的 (CPU) 呈现，并且不会加载任何第三方图形驱动程序，也不会与任何连接的图形硬件交互。</span><span class="sxs-lookup"><span data-stu-id="89b53-184">If you enable this setting, Application Guard for Office uses software-based (CPU) rendering and won't load any third-party graphics drivers or interact with any connected graphics hardware.</span></span>
|<span data-ttu-id="89b53-185">在 Office 应用程序防护中禁用不受支持的文件类型保护</span><span class="sxs-lookup"><span data-stu-id="89b53-185">Disable unsupported file types protection in Application Guard for Office</span></span>|<span data-ttu-id="89b53-186">此策略控制 Office 应用程序防护是否阻止打开不受支持的文件类型，或者是否允许重定向到受保护的视图。</span><span class="sxs-lookup"><span data-stu-id="89b53-186">This policy controls whether Application Guard for Office will block unsupported file types from being opened or if it will enable the redirection to Protected View.</span></span>
|<span data-ttu-id="89b53-187">关闭在 Office 相关应用程序防护中打开的文档的相机和麦克风访问</span><span class="sxs-lookup"><span data-stu-id="89b53-187">Turn off camera and microphone access for documents opened in Application Guard for Office</span></span>|<span data-ttu-id="89b53-188">启用此策略将删除 Office 对 Office 应用程序防护内的相机和麦克风的 Office 访问权限。</span><span class="sxs-lookup"><span data-stu-id="89b53-188">Enabling this policy will remove Office access to the camera and microphone inside Application Guard for Office.</span></span>|
|<span data-ttu-id="89b53-189">限制打印在 Office 应用程序防护中打开的文档</span><span class="sxs-lookup"><span data-stu-id="89b53-189">Restrict printing from documents opened in Application Guard for Office</span></span>|<span data-ttu-id="89b53-190">启用此策略将限制用户可从 Office 应用程序防护中打开的文件打印到的打印机。</span><span class="sxs-lookup"><span data-stu-id="89b53-190">Enabling this policy will limit the printers that a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="89b53-191">例如，可以使用此策略将用户限制为仅打印为 PDF。</span><span class="sxs-lookup"><span data-stu-id="89b53-191">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="89b53-192">阻止用户删除应用程序防护以对文件进行 Office 保护</span><span class="sxs-lookup"><span data-stu-id="89b53-192">Prevent users from removing Application Guard for Office protection on files</span></span>|<span data-ttu-id="89b53-193">启用此策略将删除 Office 应用程序体验 (禁用 Office 保护) 或打开 Office 应用程序防护外部的文件的选项。</span><span class="sxs-lookup"><span data-stu-id="89b53-193">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard for Office protection or to open a file outside Application Guard for Office.</span></span> <p> <span data-ttu-id="89b53-194">**注意：** 用户仍可以通过手动从文件中删除 Web 标记属性或将文档移动到受信任位置来绕过此策略。</span><span class="sxs-lookup"><span data-stu-id="89b53-194">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="89b53-195">以下策略将要求用户注销并再次登录到 Windows，以生效：</span><span class="sxs-lookup"><span data-stu-id="89b53-195">The following policies will require the user to sign out and sign in again to Windows to take effect:</span></span>
>
> * <span data-ttu-id="89b53-196">针对在 Office 应用程序防护中打开的文档禁用复制/粘贴</span><span class="sxs-lookup"><span data-stu-id="89b53-196">Disable copy/paste for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="89b53-197">限制打印在 Office 相关应用程序防护中打开的文档</span><span class="sxs-lookup"><span data-stu-id="89b53-197">Restrict printing for documents opened in Application Guard for Office</span></span>
> * <span data-ttu-id="89b53-198">关闭对在 Office 相关应用程序防护中打开的文档的相机和麦克风访问</span><span class="sxs-lookup"><span data-stu-id="89b53-198">Turn off camera and mic access to documents opened in Application Guard for Office</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="89b53-199">提交反馈</span><span class="sxs-lookup"><span data-stu-id="89b53-199">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="89b53-200">通过反馈中心提交反馈</span><span class="sxs-lookup"><span data-stu-id="89b53-200">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="89b53-201">如果在启动 Office 应用程序防护时遇到任何问题，建议你通过反馈中心提交反馈：</span><span class="sxs-lookup"><span data-stu-id="89b53-201">If you encounter any issues when launching Application Guard for Office, you're encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="89b53-202">打开 **反馈中心应用** 并登录。</span><span class="sxs-lookup"><span data-stu-id="89b53-202">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="89b53-203">如果在启动应用程序防护时看到错误对话框，请选择错误对话框中的"向 **Microsoft** 报告"以启动新的反馈提交。</span><span class="sxs-lookup"><span data-stu-id="89b53-203">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="89b53-204">否则，导航到 以选择正确的应用程序防护类别，然后选择右上方 <https://aka.ms/mdagoffice-fb> **+ &nbsp; 附近** 添加新反馈。</span><span class="sxs-lookup"><span data-stu-id="89b53-204">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+&nbsp;Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="89b53-205">如果尚未填写 **汇总，** 请在"总结反馈"框中输入摘要。</span><span class="sxs-lookup"><span data-stu-id="89b53-205">Enter a summary in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="89b53-206">在"详细说明"框中输入您遇到的问题以及所执行步骤的详细说明，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="89b53-206">Enter a detailed description of the issue that you experienced and what steps you took in the **Explain in more detail** box, then select **Next**.</span></span>

5. <span data-ttu-id="89b53-207">选择"问题"旁边的 **气泡**。</span><span class="sxs-lookup"><span data-stu-id="89b53-207">Select the bubble next to **Problem**.</span></span> <span data-ttu-id="89b53-208">确保选择的类别是安全和隐私 **Microsoft \> Defender 应用程序防护 - Office，** 然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="89b53-208">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="89b53-209">选择 **"新建反馈"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="89b53-209">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="89b53-210">收集有关问题的跟踪：</span><span class="sxs-lookup"><span data-stu-id="89b53-210">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="89b53-211">展开" **重新创建我的问题"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="89b53-211">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="89b53-212">如果在应用程序防护运行时遇到问题，请打开应用程序防护实例。</span><span class="sxs-lookup"><span data-stu-id="89b53-212">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="89b53-213">打开实例允许从应用程序防护容器内收集其他跟踪。</span><span class="sxs-lookup"><span data-stu-id="89b53-213">Opening an instance allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="89b53-214">选择 **"开始** 录制"，然后等待磁贴停止旋转并说出"*停止录制"。*</span><span class="sxs-lookup"><span data-stu-id="89b53-214">Select **Start recording**, and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="89b53-215">使用应用程序防护完全重现该问题。</span><span class="sxs-lookup"><span data-stu-id="89b53-215">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="89b53-216">重现可能包括尝试启动应用程序防护实例并等待它失败，或在正在运行的应用程序防护实例中重现问题。</span><span class="sxs-lookup"><span data-stu-id="89b53-216">Reproduction might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="89b53-217">选择" **停止录制"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="89b53-217">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="89b53-218">使任何正在运行的应用程序防护 (保持) 打开状态，即使在提交后几分钟内，也可以收集容器诊断。</span><span class="sxs-lookup"><span data-stu-id="89b53-218">Keep any running Application Guard instance(s) open, even for a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="89b53-219">附加与该问题相关的任何相关屏幕截图或文件。</span><span class="sxs-lookup"><span data-stu-id="89b53-219">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="89b53-220">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="89b53-220">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="89b53-221">通过 Office 客户语音提交反馈</span><span class="sxs-lookup"><span data-stu-id="89b53-221">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="89b53-222">如果问题在应用程序防护中打开 Office 文档时发生，还可以从 Office 内提交反馈。</span><span class="sxs-lookup"><span data-stu-id="89b53-222">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="89b53-223">请参阅 [Office 预览体验成员手册](https://insider.office.com/handbook) 以提交反馈。</span><span class="sxs-lookup"><span data-stu-id="89b53-223">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="89b53-224">与 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 集成</span><span class="sxs-lookup"><span data-stu-id="89b53-224">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="89b53-225">Office 应用程序防护与 Microsoft Defender for Endpoint 集成，以提供对隔离环境中发生的恶意活动的监视和警报。</span><span class="sxs-lookup"><span data-stu-id="89b53-225">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity that happens in the isolated environment.</span></span>

<span data-ttu-id="89b53-226">[Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) 中的安全文档是一项使用 Microsoft Defender for Endpoint 扫描在 Office 应用程序防护中打开的文档的功能。</span><span class="sxs-lookup"><span data-stu-id="89b53-226">[Safe Documents in Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) is a feature that uses Microsoft Defender for Endpoint to scan documents opened in Application Guard for Office.</span></span> <span data-ttu-id="89b53-227">为了提供额外的保护层，在确定扫描结果之前，用户无法离开 Office 应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="89b53-227">For an additional layer of protection, users can't leave Application Guard for Office until the results of the scan have been determined.</span></span>

<span data-ttu-id="89b53-228">Microsoft Defender for Endpoint 是一个安全平台，旨在帮助企业网络预防、检测、调查和响应高级威胁。</span><span class="sxs-lookup"><span data-stu-id="89b53-228">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="89b53-229">有关此平台的更多详细信息，请参阅 [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)。</span><span class="sxs-lookup"><span data-stu-id="89b53-229">For more details about this platform, see [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp).</span></span> <span data-ttu-id="89b53-230">若要了解有关将设备载入此平台的信息，请参阅将设备载入 [到 Microsoft Defender for Endpoint 服务](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="89b53-230">To learn more about onboarding devices to this platform, see [Onboard devices to the Microsoft Defender for Endpoint service](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="89b53-231">还可以配置适用于 Office 365 的 Microsoft Defender 以使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="89b53-231">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="89b53-232">有关详细信息，请参阅将适用于 [Office 365](integrate-office-365-ti-with-mde.md)的 Defender 与 Microsoft Defender for Endpoint 集成。</span><span class="sxs-lookup"><span data-stu-id="89b53-232">For more info, refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="89b53-233">限制和注意事项</span><span class="sxs-lookup"><span data-stu-id="89b53-233">Limitations and considerations</span></span>

* <span data-ttu-id="89b53-234">Office 相关应用程序防护是一种受保护的模式，可隔离不受信任的文档，以便它们无法访问受信任的公司资源、Intranet、用户标识和计算机上的任意文件。</span><span class="sxs-lookup"><span data-stu-id="89b53-234">Application Guard for Office is a protected mode that isolates untrusted documents so that they can't access trusted corporate resources, an intranet, the user's identity, and arbitrary files on the computer.</span></span> <span data-ttu-id="89b53-235">因此，如果用户尝试访问依赖此类访问的功能（例如，从磁盘上的本地文件插入图片）访问将失败并生成类似以下示例的提示。</span><span class="sxs-lookup"><span data-stu-id="89b53-235">As a result, if a user tries to access a feature that has a dependency on such access—for example, inserting a picture from a local file on disk—the access will fail and produce a prompt like the following example.</span></span> <span data-ttu-id="89b53-236">若要使不受信任的文档能够访问受信任的资源，用户必须从文档中删除应用程序防护保护。</span><span class="sxs-lookup"><span data-stu-id="89b53-236">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![对话框显示"为了帮助你保持安全，此功能不可用"](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="89b53-238">建议用户仅在信任文件及其来源或来源时删除保护。</span><span class="sxs-lookup"><span data-stu-id="89b53-238">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="89b53-239">宏和控件等文档中的活动ActiveX在 Office 应用程序防护中处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="89b53-239">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="89b53-240">用户需要删除应用程序防护保护才能启用活动内容。</span><span class="sxs-lookup"><span data-stu-id="89b53-240">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="89b53-241">来自网络共享的不受信任的文件或来自不同组织的 OneDrive、OneDrive for Business 或 SharePoint Online 共享的文件在应用程序防护中以只读方式打开。</span><span class="sxs-lookup"><span data-stu-id="89b53-241">Untrusted files from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="89b53-242">用户可以保存此类文件的本地副本以在容器中继续工作，或删除保护以直接使用原始文件。</span><span class="sxs-lookup"><span data-stu-id="89b53-242">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="89b53-243">默认情况下，受信息权限管理 (IRM) 文件将被阻止。</span><span class="sxs-lookup"><span data-stu-id="89b53-243">Files that are protected by Information Rights Management (IRM) are blocked by default.</span></span> <span data-ttu-id="89b53-244">如果用户想要在受保护的视图中打开此类文件，则管理员必须为组织配置不受支持的文件类型的策略设置。</span><span class="sxs-lookup"><span data-stu-id="89b53-244">If users want to open such files in Protected View, an administrator must configure policy settings for unsupported file types for the organization.</span></span>

* <span data-ttu-id="89b53-245">用户退出并再次登录或设备重启后，Office 应用程序防护 for Office 应用程序的任何自定义不会保留。</span><span class="sxs-lookup"><span data-stu-id="89b53-245">Any customizations to Office applications in Application Guard for Office won't persist after a user signs out and signs in again or after the device restarts.</span></span>

* <span data-ttu-id="89b53-246">只有使用 UIA 框架的辅助功能工具才能为在 Office 应用程序防护中打开的文件提供辅助体验。</span><span class="sxs-lookup"><span data-stu-id="89b53-246">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="89b53-247">安装后首次启动应用程序防护需要网络连接。</span><span class="sxs-lookup"><span data-stu-id="89b53-247">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="89b53-248">应用程序防护需要连接才能验证许可证。</span><span class="sxs-lookup"><span data-stu-id="89b53-248">Connectivity is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="89b53-249">在文档的信息部分中 *，"上次修改* 者"属性可能会将 **WDAGUtilityAccount** 显示为用户。</span><span class="sxs-lookup"><span data-stu-id="89b53-249">In the document's info section, the *Last Modified By* property may display **WDAGUtilityAccount** as the user.</span></span> <span data-ttu-id="89b53-250">WDAGUtilityAccount 是在应用程序防护中配置的匿名用户。</span><span class="sxs-lookup"><span data-stu-id="89b53-250">WDAGUtilityAccount is the anonymous user configured in Application Guard.</span></span> <span data-ttu-id="89b53-251">桌面用户的身份不在应用程序防护容器内共享。</span><span class="sxs-lookup"><span data-stu-id="89b53-251">The desktop user's identity isn't shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard-for-office"></a><span data-ttu-id="89b53-252">Office 应用程序防护的性能优化</span><span class="sxs-lookup"><span data-stu-id="89b53-252">Performance optimizations for Application Guard for Office</span></span>

<span data-ttu-id="89b53-253">本部分概述了 Office 应用程序防护中使用的性能优化。</span><span class="sxs-lookup"><span data-stu-id="89b53-253">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="89b53-254">此信息可以帮助管理员在启用应用程序防护时诊断来自用户的报告，这些报告与 Office 或整个系统的性能相关。</span><span class="sxs-lookup"><span data-stu-id="89b53-254">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="89b53-255">应用程序防护使用虚拟化容器将不受信任的文档与系统隔离。</span><span class="sxs-lookup"><span data-stu-id="89b53-255">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="89b53-256">创建容器和设置应用程序防护容器以打开 Office 文档的过程具有性能开销，在用户打开不受信任的文档时可能会对用户体验产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="89b53-256">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively affect user experience when users open an untrusted document.</span></span>

<span data-ttu-id="89b53-257">为了为用户提供预期的文件打开体验，当系统满足以下启发性要求时，应用程序防护使用逻辑预创建容器：用户在过去 28 天内以受保护的视图或应用程序防护打开文件。</span><span class="sxs-lookup"><span data-stu-id="89b53-257">To provide users with the expected file-opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="89b53-258">当满足此启发性要求时，Office 将在用户登录 Windows 后为用户预先创建应用程序防护容器。</span><span class="sxs-lookup"><span data-stu-id="89b53-258">When this heuristic is met, Office will pre-create an Application Guard container for the user after they sign in to Windows.</span></span> <span data-ttu-id="89b53-259">虽然此预创建操作正在进行中，但系统可能会遇到性能缓慢的问题，但该操作完成后，该影响将立即解决。</span><span class="sxs-lookup"><span data-stu-id="89b53-259">While this pre-create operation is in progress, the system may experience slow performance, but the effect will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="89b53-260">用户使用它们时，Office 应用程序会生成预先创建容器的启发式提示。</span><span class="sxs-lookup"><span data-stu-id="89b53-260">The hints needed for the heuristic to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="89b53-261">如果用户在启用了应用程序防护的新系统中安装 Office，则 Office 不会预先创建容器，直到用户首次在系统上打开不受信任的文档。</span><span class="sxs-lookup"><span data-stu-id="89b53-261">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="89b53-262">用户将观察到，在应用程序防护中打开第一个文件需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="89b53-262">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues"></a><span data-ttu-id="89b53-263">已知问题</span><span class="sxs-lookup"><span data-stu-id="89b53-263">Known issues</span></span>

* <span data-ttu-id="89b53-264">选择 (`http` 或 `https`) Web 链接不会打开浏览器。</span><span class="sxs-lookup"><span data-stu-id="89b53-264">Selecting web links (`http` or `https`) doesn't open the browser.</span></span>
* <span data-ttu-id="89b53-265">目前不支持将 RTF 格式 (RTF) 应用程序防护打开的 Office 文档中的内容或图像。</span><span class="sxs-lookup"><span data-stu-id="89b53-265">Pasting rich text format (RTF) content or images in Office documents opened with Application Guard isn't supported at this time.</span></span>
* <span data-ttu-id="89b53-266">不受支持的文件类型保护策略的默认设置是阻止打开信息权限管理 、IRM (、CSV 或 HTML) 不受信任的文件类型。</span><span class="sxs-lookup"><span data-stu-id="89b53-266">The default setting for unsupported file types protection policy is to block opening untrusted unsupported file types of Information Rights Management (IRM), CSV, or HTML.</span></span>
* <span data-ttu-id="89b53-267">更新 .NET 可能会导致文件在应用程序防护中无法打开。</span><span class="sxs-lookup"><span data-stu-id="89b53-267">Updates to .NET might cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="89b53-268">作为一种解决方法，用户可以在遇到此故障时重新启动其设备。</span><span class="sxs-lookup"><span data-stu-id="89b53-268">As a workaround, users can restart their device when they come across this failure.</span></span> <span data-ttu-id="89b53-269">有关该问题的详细信息，请 [通过应用程序](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)防护或 Windows 沙盒Windows Defender时收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="89b53-269">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
