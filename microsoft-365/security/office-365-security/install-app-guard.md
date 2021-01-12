---
title: Office 365 应用程序防护 (管理员) 预览版
keywords: 应用程序防护， 保护， 隔离， 隔离容器， 硬件隔离
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 获取基于硬件的最新隔离。 防止当前和新出现的攻击（如攻击或恶意链接）中断员工工作效率和企业安全。
ms.openlocfilehash: f5a5feb14db75c5baccecf0c6afafe0c42517224
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794504"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a><span data-ttu-id="3fa21-105">Office 应用程序防护 (公共) 预览版</span><span class="sxs-lookup"><span data-stu-id="3fa21-105">Application Guard for Office (public preview) for admins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3fa21-106">**适用于：** Word、Excel 和 PowerPoint for Microsoft 365、Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="3fa21-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fa21-107">某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="3fa21-107">Some information relates to a prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3fa21-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3fa21-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3fa21-109">适用于 Office 的 Microsoft Defender (应用程序防护) 有助于防止不受信任的文件访问受信任资源，确保企业安全不受新的和新出现的攻击。</span><span class="sxs-lookup"><span data-stu-id="3fa21-109">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="3fa21-110">本文将指导管理员设置设备以预览 Office 应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="3fa21-110">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="3fa21-111">它提供有关在设备上启用 Office 应用程序防护的系统要求和安装步骤的信息。</span><span class="sxs-lookup"><span data-stu-id="3fa21-111">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3fa21-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="3fa21-112">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="3fa21-113">最低硬件要求</span><span class="sxs-lookup"><span data-stu-id="3fa21-113">Minimum hardware requirements</span></span>

* <span data-ttu-id="3fa21-114">CPU：64 位、4 核 (物理或虚拟) 、虚拟化扩展 (Intel VT-x OR AMD-V) 、Core i5 等效项或更高推荐</span><span class="sxs-lookup"><span data-stu-id="3fa21-114">**CPU**: 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="3fa21-115">**物理内存**：8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="3fa21-115">**Physical memory**: 8-GB RAM</span></span>
* <span data-ttu-id="3fa21-116">**硬盘：** 系统驱动器上 10 GB 的可用空间 (建议使用 SSD) </span><span class="sxs-lookup"><span data-stu-id="3fa21-116">**Hard disk**: 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="3fa21-117">最低软件要求</span><span class="sxs-lookup"><span data-stu-id="3fa21-117">Minimum software requirements</span></span>

* <span data-ttu-id="3fa21-118">**Windows 10**：Windows 10 企业版，客户端内部版本 2004 (20H1) 版本 19041</span><span class="sxs-lookup"><span data-stu-id="3fa21-118">**Windows 10**: Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041</span></span>
* <span data-ttu-id="3fa21-119">**Office**：Office Beta 渠道版本 2008 16.0.13212 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3fa21-119">**Office**: Office Beta Channel Build version 2008 16.0.13212 or later</span></span>
* <span data-ttu-id="3fa21-120">**更新包**：Windows 10 累积每月安全更新 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="3fa21-120">**Update package**: Windows 10 cumulative monthly security updates [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span>

<span data-ttu-id="3fa21-121">有关详细的系统要求，请参阅 [Microsoft Defender 应用程序防护的系统要求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="3fa21-121">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="3fa21-122">若要了解有关 Office Insider Preview 版本的详细信息，请参阅 [部署 Office](https://insider.office.com/business/deploy)预览体验成员内部版本入门。</span><span class="sxs-lookup"><span data-stu-id="3fa21-122">To learn more about Office Insider Preview builds, refer to [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="3fa21-123">许可要求</span><span class="sxs-lookup"><span data-stu-id="3fa21-123">Licensing requirements</span></span>

* <span data-ttu-id="3fa21-124">Microsoft 365 E5 或 Microsoft 365 E5 安全</span><span class="sxs-lookup"><span data-stu-id="3fa21-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="3fa21-125">部署 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="3fa21-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="3fa21-126">启用 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="3fa21-126">Enable Application Guard for Office</span></span>

1. <span data-ttu-id="3fa21-127">下载并安装 **Windows 10 累积每月安全更新 KB4571756。**</span><span class="sxs-lookup"><span data-stu-id="3fa21-127">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span>

2. <span data-ttu-id="3fa21-128">在 **Windows 功能下选择 Microsoft Defender** 应用程序防护，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="3fa21-128">Select **Microsoft Defender Application Guard** under Windows Features and  select **OK**.</span></span> <span data-ttu-id="3fa21-129">启用应用程序防护功能将提示系统重新启动。</span><span class="sxs-lookup"><span data-stu-id="3fa21-129">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="3fa21-130">可以选择立即重启，也可以选择在步骤 3 之后重新启动。</span><span class="sxs-lookup"><span data-stu-id="3fa21-130">You can choose to reboot now or after step 3.</span></span>

   ![显示 AG 的 Windows 功能对话框](../../media/ag03-deploy.png)

   <span data-ttu-id="3fa21-132">还可以以管理员角色运行以下 PowerShell 命令来启用该功能：</span><span class="sxs-lookup"><span data-stu-id="3fa21-132">The feature can also be enabled by running the following PowerShell command as administrator:</span></span>

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. <span data-ttu-id="3fa21-133">查找位于计算机配置管理模板 Windows 组件 Microsoft Defender 应用程序防护的 **托管模式下的 Microsoft Defender \\ \\ \\ 应用程序防护组策略**。</span><span class="sxs-lookup"><span data-stu-id="3fa21-133">Look for the Microsoft Defender Application Guard in Managed Mode group policy located at **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="3fa21-134">打开此策略，方法为将选项下的值设置为 **2** 或 **3，** 然后选择 **"确定**"或"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="3fa21-134">Turn this policy on by setting the value under Options as **2** or **3** then selecting **OK** or **Apply**.</span></span>

   ![在托管模式下打开 AG](../../media/ag04-deploy.png)

   <span data-ttu-id="3fa21-136">或者，你可以设置相应的云解决方案提供商策略：</span><span class="sxs-lookup"><span data-stu-id="3fa21-136">Alternatively, you can set the corresponding CSP policy:</span></span>

   > <span data-ttu-id="3fa21-137">**OMA-URI：./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span><span class="sxs-lookup"><span data-stu-id="3fa21-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**</span></span> <br> <span data-ttu-id="3fa21-138">数据类型 **：Integer**</span><span class="sxs-lookup"><span data-stu-id="3fa21-138">Data type: **Integer**</span></span> <br> <span data-ttu-id="3fa21-139">值 **：2**</span><span class="sxs-lookup"><span data-stu-id="3fa21-139">Value: **2**</span></span>

4. <span data-ttu-id="3fa21-140">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="3fa21-140">Reboot the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="3fa21-141">设置诊断&反馈以发送完整数据</span><span class="sxs-lookup"><span data-stu-id="3fa21-141">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="3fa21-142">此步骤可确保识别和修复问题所需的数据能够到达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3fa21-142">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="3fa21-143">请按照以下步骤在 Windows 设备上启用诊断：</span><span class="sxs-lookup"><span data-stu-id="3fa21-143">Follow these steps to enable diagnostics on your Windows device:</span></span>

1. <span data-ttu-id="3fa21-144">从 **"** 开始"菜单中打开"设置"。</span><span class="sxs-lookup"><span data-stu-id="3fa21-144">Open **Settings** from the Start menu.</span></span>

   ![“开始”菜单](../../media/ag05-diagnostic.png)

2. <span data-ttu-id="3fa21-146">在 **"Windows 设置"** 上，选择 **"隐私"。**</span><span class="sxs-lookup"><span data-stu-id="3fa21-146">On **Windows Settings**, select **Privacy**.</span></span>

   ![Windows 设置菜单](../../media/ag06-diagnostic.png)

3. <span data-ttu-id="3fa21-148">Under Privacy， select **Diagnostics & feedback** and select **Optional diagnostic data.**</span><span class="sxs-lookup"><span data-stu-id="3fa21-148">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

   ![诊断和反馈菜单](../../media/ag07a-diagnostic.png)

<span data-ttu-id="3fa21-150">有关配置 Windows 诊断设置 More on configuring Windows diagnostic settings， refer to [Configuring Windows diagnostic data in your organization.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)</span><span class="sxs-lookup"><span data-stu-id="3fa21-150">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="3fa21-151">确认 Office 应用程序防护已启用且正常工作</span><span class="sxs-lookup"><span data-stu-id="3fa21-151">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="3fa21-152">在确认 Office 应用程序防护已启用之前，在已部署策略的设备上启动 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="3fa21-152">Before confirming that the Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="3fa21-153">确保 Office 已激活。</span><span class="sxs-lookup"><span data-stu-id="3fa21-153">Make sure Office is activated.</span></span> <span data-ttu-id="3fa21-154">你可能需要先使用工作标识激活 Office 产品。</span><span class="sxs-lookup"><span data-stu-id="3fa21-154">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="3fa21-155">若要确认 Office 应用程序防护现已启用，请启动 Word、Excel 或 PowerPoint 并打开不受信任的文档。</span><span class="sxs-lookup"><span data-stu-id="3fa21-155">To confirm that Application Guard for Office is now enabled, launch Word, Excel, or PowerPoint and open an untrusted document.</span></span> <span data-ttu-id="3fa21-156">例如，您可以打开从 Internet 下载的文档或组织外部人员的电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="3fa21-156">For example, you can open a document downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="3fa21-157">首次启动不受信任的文件时，你可能会看到 Office 初始屏幕，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3fa21-157">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span></span> <span data-ttu-id="3fa21-158">它可能在激活 Office 应用程序防护并打开文件时显示一段时间。</span><span class="sxs-lookup"><span data-stu-id="3fa21-158">It might show for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="3fa21-159">随后启动不受信任的文件应更快。</span><span class="sxs-lookup"><span data-stu-id="3fa21-159">Subsequent launches of untrusted files should be faster.</span></span>

![Office 应用初始屏幕](../../media/ag08-confirm.png)

<span data-ttu-id="3fa21-161">打开后，文件应显示几个可视指示器，指示文件是在 Office 应用程序防护内打开的：</span><span class="sxs-lookup"><span data-stu-id="3fa21-161">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="3fa21-162">功能区中的标注</span><span class="sxs-lookup"><span data-stu-id="3fa21-162">A callout in the ribbon</span></span>

  ![显示小 App Guard 注释的文档文件](../../media/ag09-confirm.png)

* <span data-ttu-id="3fa21-164">任务栏中带防护的应用程序图标</span><span class="sxs-lookup"><span data-stu-id="3fa21-164">The application icon with a shield in the taskbar</span></span>

  ![任务栏中的图标](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a><span data-ttu-id="3fa21-166">配置 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="3fa21-166">Configure Application Guard for Office</span></span>

<span data-ttu-id="3fa21-167">Office 支持以下策略，使您能够配置 Office 相关应用程序防护的功能。</span><span class="sxs-lookup"><span data-stu-id="3fa21-167">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="3fa21-168">可以通过组策略或 Office 云策略服务配置这些策略。</span><span class="sxs-lookup"><span data-stu-id="3fa21-168">These policies can be configured through Group policies or through the Office cloud policy service.</span></span>

> [!NOTE]
> <span data-ttu-id="3fa21-169">这些策略将很快推出。</span><span class="sxs-lookup"><span data-stu-id="3fa21-169">These policies will become available soon.</span></span>
> <span data-ttu-id="3fa21-170">此外，配置这些策略可以禁用在 Office 相关应用程序防护中打开的文件的一些功能。</span><span class="sxs-lookup"><span data-stu-id="3fa21-170">Also, configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

|<span data-ttu-id="3fa21-171">Policy</span><span class="sxs-lookup"><span data-stu-id="3fa21-171">Policy</span></span>|<span data-ttu-id="3fa21-172">说明</span><span class="sxs-lookup"><span data-stu-id="3fa21-172">Description</span></span>|
|---|---|
|<span data-ttu-id="3fa21-173">禁用 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="3fa21-173">Disable Application Guard for Office</span></span>|<span data-ttu-id="3fa21-174">启用此策略将强制 Word、Excel 和 PowerPoint 使用受保护的视图隔离容器，而不是 Office 应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="3fa21-174">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="3fa21-175">当为 Edge 启用应用程序防护时，可以使用此策略临时禁用它。</span><span class="sxs-lookup"><span data-stu-id="3fa21-175">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Edge.</span></span>|
|<span data-ttu-id="3fa21-176">在应用程序防护中打开的文档禁用复制/粘贴</span><span class="sxs-lookup"><span data-stu-id="3fa21-176">Disable copy/paste for documents opened in Application Guard</span></span>|<span data-ttu-id="3fa21-177">启用此策略将阻止用户将内容从在 Office 应用程序防护中打开的文档复制并粘贴到其外部打开的文档。</span><span class="sxs-lookup"><span data-stu-id="3fa21-177">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside it.</span></span>|
|<span data-ttu-id="3fa21-178">阻止用户删除文件上的应用程序防护保护</span><span class="sxs-lookup"><span data-stu-id="3fa21-178">Prevent users from removing Application Guard protection on files</span></span>|<span data-ttu-id="3fa21-179">启用此策略将删除 Office (体验中的选项) 禁用应用程序防护保护或打开应用程序防护外部的文件。</span><span class="sxs-lookup"><span data-stu-id="3fa21-179">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard protection or open a file outside Application Guard.</span></span> <p> <span data-ttu-id="3fa21-180">**注意：** 用户仍可以通过从文件手动删除 Web 标记属性或将文档移动到受信任位置来绕过此策略。</span><span class="sxs-lookup"><span data-stu-id="3fa21-180">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span>|
|<span data-ttu-id="3fa21-181">限制从应用程序防护中打开的文档打印</span><span class="sxs-lookup"><span data-stu-id="3fa21-181">Restrict printing from documents opened in Application Guard</span></span>|<span data-ttu-id="3fa21-182">启用此策略将限制用户可从 Office 应用程序防护中打开的文件打印到的打印机。</span><span class="sxs-lookup"><span data-stu-id="3fa21-182">Enabling this policy will limit printers a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="3fa21-183">例如，可以使用此策略将用户限制为仅打印为 PDF。</span><span class="sxs-lookup"><span data-stu-id="3fa21-183">For example, you can use this policy to restrict users to only print to PDF.</span></span>|
|<span data-ttu-id="3fa21-184">关闭应用程序防护中打开的文档的相机和麦克风访问</span><span class="sxs-lookup"><span data-stu-id="3fa21-184">Turn off camera and microphone access for documents opened in Application Guard</span></span>|<span data-ttu-id="3fa21-185">启用此策略将删除 Office 对 Office 应用程序防护内的相机和麦克风的访问。</span><span class="sxs-lookup"><span data-stu-id="3fa21-185">Enabling this policy will remove Office access to Camera and Microphone inside Application Guard for Office.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="3fa21-186">以下策略将要求用户注销并重新登录到 Windows 才能生效：</span><span class="sxs-lookup"><span data-stu-id="3fa21-186">The following policies will require the user to log off and re-login to Windows to take effect:</span></span>
>
> * <span data-ttu-id="3fa21-187">在应用程序防护中打开的文档禁用复制/粘贴</span><span class="sxs-lookup"><span data-stu-id="3fa21-187">Disable copy/paste for documents opened in Application Guard</span></span>
> * <span data-ttu-id="3fa21-188">限制在应用程序防护中打开的文档的打印</span><span class="sxs-lookup"><span data-stu-id="3fa21-188">Restrict printing for documents opened in Application Guard</span></span>
> * <span data-ttu-id="3fa21-189">关闭对应用程序防护中打开的文档的相机和麦克风访问</span><span class="sxs-lookup"><span data-stu-id="3fa21-189">Turn off camera and mic access to documents opened in Application Guard</span></span>

## <a name="submit-feedback"></a><span data-ttu-id="3fa21-190">提交反馈</span><span class="sxs-lookup"><span data-stu-id="3fa21-190">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="3fa21-191">通过反馈中心提交反馈</span><span class="sxs-lookup"><span data-stu-id="3fa21-191">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="3fa21-192">如果在启动 Office 应用程序防护时遇到任何问题，建议你通过反馈中心提交反馈：</span><span class="sxs-lookup"><span data-stu-id="3fa21-192">If you encounter any issues when launching Application Guard for Office, you are encouraged to submit your feedback via Feedback Hub:</span></span>

1. <span data-ttu-id="3fa21-193">打开 **反馈中心应用** 并登录。</span><span class="sxs-lookup"><span data-stu-id="3fa21-193">Open the **Feedback Hub app** and sign in.</span></span>

2. <span data-ttu-id="3fa21-194">如果在启动应用程序防护时看到错误对话框，请在错误对话框中选择"向 **Microsoft** 报告"以启动新的反馈提交。</span><span class="sxs-lookup"><span data-stu-id="3fa21-194">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="3fa21-195">否则，导航到为应用程序防护选择正确的类别，然后选择 + 在右上方 <https://aka.ms/mdagoffice-fb> 附近添加新反馈。 </span><span class="sxs-lookup"><span data-stu-id="3fa21-195">Otherwise, navigate to <https://aka.ms/mdagoffice-fb> to select the correct category for Application Guard, then select **+ Add new feedback** near the top right.</span></span>

3. <span data-ttu-id="3fa21-196">如果 **尚未填写反馈** 框，请填写"汇总反馈"框。</span><span class="sxs-lookup"><span data-stu-id="3fa21-196">Fill in the **Summarize your feedback** box if it isn't already filled in for you.</span></span>

4. <span data-ttu-id="3fa21-197">填写"**详细说明"框**，详细说明您遇到的问题以及所执行的步骤，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="3fa21-197">Fill in the **Explain in more detail** box with a detailed description of the issue you experienced and what steps you took, then select **Next**.</span></span>

5. <span data-ttu-id="3fa21-198">选择"问题"旁边的气泡。</span><span class="sxs-lookup"><span data-stu-id="3fa21-198">Select the bubble next to Problem.</span></span> <span data-ttu-id="3fa21-199">确保选择的类别是安全和隐私 **Microsoft \> Defender 应用程序防护 – Office，** 然后选择下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="3fa21-199">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office**, then select **Next**.</span></span>

6. <span data-ttu-id="3fa21-200">选择 **"新建反馈**"，然后选择"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="3fa21-200">Select **New feedback**, then **Next**.</span></span>

7. <span data-ttu-id="3fa21-201">收集有关问题的跟踪：</span><span class="sxs-lookup"><span data-stu-id="3fa21-201">Collect traces about the issue:</span></span>

   1. <span data-ttu-id="3fa21-202">展开 **"重新创建我的问题"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="3fa21-202">Expand the **Recreate my problem** tile.</span></span>

   2. <span data-ttu-id="3fa21-203">如果在应用程序防护运行时遇到问题，请打开应用程序防护实例。</span><span class="sxs-lookup"><span data-stu-id="3fa21-203">If the issue you're experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="3fa21-204">这样做允许从应用程序防护容器内收集其他跟踪。</span><span class="sxs-lookup"><span data-stu-id="3fa21-204">Doing this allows additional traces to be collected from within the Application Guard container.</span></span>

   3. <span data-ttu-id="3fa21-205">选择 **"开始** 录制"并等待磁贴停止旋转，并说出 *"停止录制"。*</span><span class="sxs-lookup"><span data-stu-id="3fa21-205">Select **Start recording** and wait for the tile to stop spinning and say *Stop recording*.</span></span>

   4. <span data-ttu-id="3fa21-206">使用应用程序防护完全重现该问题。</span><span class="sxs-lookup"><span data-stu-id="3fa21-206">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="3fa21-207">这可能包括尝试启动应用程序防护实例并等待它失败，或在正在运行的应用程序防护实例中重现问题。</span><span class="sxs-lookup"><span data-stu-id="3fa21-207">This might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

   5. <span data-ttu-id="3fa21-208">选择" **停止录制"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="3fa21-208">Select the **Stop recording** tile.</span></span>

   6. <span data-ttu-id="3fa21-209">使任何正在运行的应用程序防护实例保持打开状态，即使在提交后几分钟内，也可以收集容器诊断。</span><span class="sxs-lookup"><span data-stu-id="3fa21-209">Keep any running Application Guard instance/s open, even until a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8. <span data-ttu-id="3fa21-210">附加与该问题相关的任何相关屏幕截图或文件。</span><span class="sxs-lookup"><span data-stu-id="3fa21-210">Attach any relevant screenshots or files related to the problem.</span></span>

9. <span data-ttu-id="3fa21-211">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="3fa21-211">Select **Submit**.</span></span>

### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="3fa21-212">通过 Office 客户语音提交反馈</span><span class="sxs-lookup"><span data-stu-id="3fa21-212">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="3fa21-213">如果在应用程序防护中打开 Office 文档时发生问题，您还可以从 Office 内提交反馈。</span><span class="sxs-lookup"><span data-stu-id="3fa21-213">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="3fa21-214">请参阅 [Office 预览体验成员手册](https://insider.office.com/handbook) 以提交反馈。</span><span class="sxs-lookup"><span data-stu-id="3fa21-214">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="3fa21-215">与 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 集成</span><span class="sxs-lookup"><span data-stu-id="3fa21-215">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="3fa21-216">适用于 Office 的应用程序防护与 Microsoft Defender for Endpoint 集成，以提供对隔离环境中发生的恶意活动的监视和警报。</span><span class="sxs-lookup"><span data-stu-id="3fa21-216">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity happening in the isolated environment.</span></span>

<span data-ttu-id="3fa21-217">Microsoft Defender for Endpoint 是一个安全平台，旨在帮助企业网络预防、检测、调查和响应高级威胁。</span><span class="sxs-lookup"><span data-stu-id="3fa21-217">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="3fa21-218">有关此平台的更多详细信息，请访问 [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 页面。</span><span class="sxs-lookup"><span data-stu-id="3fa21-218">For more details about this platform, visit the [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) page.</span></span> <span data-ttu-id="3fa21-219">了解有关将设备载入到此平台（在 [载入设备到 Microsoft Defender for Endpoint 服务）上的信息](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="3fa21-219">Learn more about onboarding devices to this platform at [Onboard devices to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="3fa21-220">还可以将适用于 Office 365 的 Microsoft Defender 配置为与 Defender for Endpoint 一起工作。</span><span class="sxs-lookup"><span data-stu-id="3fa21-220">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="3fa21-221">请参阅[集成 Defender for Office 365 与 Microsoft Defender for Endpoint。](integrate-office-365-ti-with-wdatp.md)</span><span class="sxs-lookup"><span data-stu-id="3fa21-221">Refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="3fa21-222">限制和注意事项</span><span class="sxs-lookup"><span data-stu-id="3fa21-222">Limitations and considerations</span></span>

* <span data-ttu-id="3fa21-223">Office 相关应用程序防护是一种受限模式，可隔离不受信任的文档以访问受信任的公司资源、Intranet、用户标识和计算机上存在的任意文件。</span><span class="sxs-lookup"><span data-stu-id="3fa21-223">Application Guard for Office is a restricted mode that isolates untrusted documents from accessing trusted corporate resources, intranet, the user's identity, and arbitrary files present on the computer.</span></span> <span data-ttu-id="3fa21-224">因此，如果用户尝试访问依赖于此类访问的功能（例如，从磁盘上的本地文件插入图片）将失败并生成如下所示的提示。</span><span class="sxs-lookup"><span data-stu-id="3fa21-224">As a result, if a user tries to access a feature that has a dependency on such access, for example, inserting a picture from a local file on disk, it will fail and produce a prompt like the one below.</span></span> <span data-ttu-id="3fa21-225">若要允许不受信任的文档访问受信任的资源，用户必须从文档中删除应用程序防护保护。</span><span class="sxs-lookup"><span data-stu-id="3fa21-225">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

  ![对话框显示"为了帮助你保持安全，此功能不可用"](../../media/ag10-limitations.png)

  > [!NOTE]
  > <span data-ttu-id="3fa21-227">建议用户仅在信任文件及其源或文件来源时删除保护。</span><span class="sxs-lookup"><span data-stu-id="3fa21-227">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="3fa21-228">宏和控件等文档中的活动ActiveX在 Office 相关应用程序防护中处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="3fa21-228">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="3fa21-229">用户需要删除应用程序防护保护才能启用活动内容。</span><span class="sxs-lookup"><span data-stu-id="3fa21-229">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="3fa21-230">从网络共享打开的不受信任的文件或从不同组织的 OneDrive、OneDrive for Business 或 SharePoint Online 共享的文件在应用程序防护中以只读方式打开。</span><span class="sxs-lookup"><span data-stu-id="3fa21-230">Untrusted files opened from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="3fa21-231">用户可以保存此类文件的本地副本以在容器中继续工作，或删除保护以直接处理原始文件。</span><span class="sxs-lookup"><span data-stu-id="3fa21-231">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="3fa21-232">受信息权限管理保护的文件 (IRM) 在受保护的视图中继续打开。</span><span class="sxs-lookup"><span data-stu-id="3fa21-232">Files that are protected by Information Rights Management (IRM) continue to open in Protected View.</span></span>

* <span data-ttu-id="3fa21-233">在用户注销并重新登录或重新启动设备后，Office 应用程序防护中对 Office 应用程序的任何自定义不会保留。</span><span class="sxs-lookup"><span data-stu-id="3fa21-233">Any customizations to Office applications in Application Guard for Office will not persist after a user logs off and logs back in or reboots the device.</span></span>

* <span data-ttu-id="3fa21-234">只有使用 UIA 框架的辅助功能工具才能为在 Office 应用程序防护中打开的文件提供辅助体验。</span><span class="sxs-lookup"><span data-stu-id="3fa21-234">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="3fa21-235">安装后首次启动应用程序防护需要网络连接。</span><span class="sxs-lookup"><span data-stu-id="3fa21-235">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="3fa21-236">应用程序防护需要此权限才能验证许可证。</span><span class="sxs-lookup"><span data-stu-id="3fa21-236">This is required for Application Guard to validate the license.</span></span>

* <span data-ttu-id="3fa21-237">在文档的信息部分中 *，"上次* 修改者"属性可能会将 WDAGUtilityAccount 显示为用户。</span><span class="sxs-lookup"><span data-stu-id="3fa21-237">In the document's info section, the *Last Modified By* property may display WDAGUtilityAccount as the user.</span></span> <span data-ttu-id="3fa21-238">这是在应用程序防护中配置的匿名用户，因为桌面用户的身份未在应用程序防护容器内共享。</span><span class="sxs-lookup"><span data-stu-id="3fa21-238">This is the anonymous user configured in Application Guard given that the desktop user's identity is not shared inside the Application Guard container.</span></span>

## <a name="performance-optimizations-for-application-guard"></a><span data-ttu-id="3fa21-239">应用程序防护的性能优化</span><span class="sxs-lookup"><span data-stu-id="3fa21-239">Performance optimizations for Application Guard</span></span>

<span data-ttu-id="3fa21-240">本节概述了 Office 应用程序防护中使用的性能优化。</span><span class="sxs-lookup"><span data-stu-id="3fa21-240">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="3fa21-241">当启用应用程序防护时，此信息可以帮助管理员诊断与 Office 或整个系统的性能相关的用户报告。</span><span class="sxs-lookup"><span data-stu-id="3fa21-241">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span>

<span data-ttu-id="3fa21-242">应用程序防护使用虚拟化容器将不受信任的文档与系统隔离开。</span><span class="sxs-lookup"><span data-stu-id="3fa21-242">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="3fa21-243">创建容器和设置应用程序防护容器以打开 Office 文档的过程具有性能开销，在用户打开不受信任的文档时可能会对用户体验产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="3fa21-243">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively impact user experience when users open an  untrusted document.</span></span>

<span data-ttu-id="3fa21-244">为了为用户提供预期的文件打开体验，应用程序防护使用逻辑在系统上满足以下启发性要求时预创建容器：用户在过去 28 天内在受保护的视图或应用程序防护中打开了文件。</span><span class="sxs-lookup"><span data-stu-id="3fa21-244">To provide users with the expected file opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span>

<span data-ttu-id="3fa21-245">满足此启发后，Office 将在用户登录到 Windows 后为用户预创建应用程序防护容器。</span><span class="sxs-lookup"><span data-stu-id="3fa21-245">When this heuristic is met, Office will pre-create an Application Guard container for the user after they log in to Windows.</span></span> <span data-ttu-id="3fa21-246">进行此预创建操作时，系统可能会遇到性能缓慢的问题。</span><span class="sxs-lookup"><span data-stu-id="3fa21-246">When this pre-create operation is in progress, the system may experience slow performance.</span></span> <span data-ttu-id="3fa21-247">此操作一旦完成，就会解决。</span><span class="sxs-lookup"><span data-stu-id="3fa21-247">This will resolve as soon as the operation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="3fa21-248">用户使用它们时，Office 应用程序会生成用于预创建容器的启发式提示。</span><span class="sxs-lookup"><span data-stu-id="3fa21-248">The hints needed for the heuristic used to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="3fa21-249">如果用户在启用了应用程序防护的新系统中安装 Office，则 Office 不会预先创建容器，除非用户首次在系统上打开不受信任的文档。</span><span class="sxs-lookup"><span data-stu-id="3fa21-249">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="3fa21-250">用户将观察到，在应用程序防护中打开此第一个文件需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="3fa21-250">The user will observe that this first file takes longer to open in Application Guard.</span></span>

## <a name="known-issues-in-preview"></a><span data-ttu-id="3fa21-251">预览中的已知问题</span><span class="sxs-lookup"><span data-stu-id="3fa21-251">Known issues in preview</span></span>

* <span data-ttu-id="3fa21-252">单击 Web 链接 (`http` 或 `https`) 不会打开浏览器。</span><span class="sxs-lookup"><span data-stu-id="3fa21-252">Clicking on web links (`http` or `https`) does not open the browser.</span></span>
* <span data-ttu-id="3fa21-253">.NET 更新导致文件在应用程序防护中无法打开。</span><span class="sxs-lookup"><span data-stu-id="3fa21-253">.NET updates cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="3fa21-254">作为一种解决方法，用户可以在遇到此问题时重新启动其设备。</span><span class="sxs-lookup"><span data-stu-id="3fa21-254">As a workaround, users can reboot their device when this issue is encountered.</span></span> <span data-ttu-id="3fa21-255">了解有关尝试打开应用程序防护或 Windows 沙盒时收到错误消息 [Windows Defender的详细信息](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)。</span><span class="sxs-lookup"><span data-stu-id="3fa21-255">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
