---
title: '适用于 Office 365 的应用程序防护 (针对管理员的公共预览版) '
keywords: 应用程序防护、保护、隔离、独立容器、硬件隔离
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
description: 获取最新的基于硬件的隔离。 阻止目前和新兴攻击（如入侵或恶意链接）中断员工工作效率和企业安全性。
ms.openlocfilehash: 3b31ef639667c7ef761d1d5fa0295f5d767e0c48
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843002"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a><span data-ttu-id="5feb9-105">Office 的应用程序防护 (公共预览版) 的管理员</span><span class="sxs-lookup"><span data-stu-id="5feb9-105">Application Guard for Office (public preview) for admins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]



<span data-ttu-id="5feb9-106">**适用于：** 适用于 Microsoft 365 的 Word、Excel 和 PowerPoint，Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="5feb9-106">**Applies to:** Word, Excel, and PowerPoint for Microsoft 365, Windows 10 Enterprise</span></span>

>[!IMPORTANT]
><span data-ttu-id="5feb9-107">一些信息与 prereleased 产品相关，在正式发布之前，可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="5feb9-107">Some information relates to a prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5feb9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="5feb9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="5feb9-109">适用于 Office 的 Microsoft Defender 应用程序防护 (Office) 的应用程序防护可帮助防止不受信任的文件访问受信任的资源，从而使您的企业免受新的和新兴的攻击。</span><span class="sxs-lookup"><span data-stu-id="5feb9-109">Microsoft Defender Application Guard for Office (Application Guard for Office) helps prevent untrusted files from accessing trusted resources, keeping your enterprise safe from new and emerging attacks.</span></span> <span data-ttu-id="5feb9-110">本文将指导管理员为 Office 的应用程序防护的预览设置设备。</span><span class="sxs-lookup"><span data-stu-id="5feb9-110">This article walks admins through setting up devices for a preview of Application Guard for Office.</span></span> <span data-ttu-id="5feb9-111">它提供了有关系统要求和安装步骤的信息，以在设备上启用 Office 的应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="5feb9-111">It provides information about system requirements and installation steps to enable Application Guard for Office on a device.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5feb9-112">必备条件</span><span class="sxs-lookup"><span data-stu-id="5feb9-112">Prerequisites</span></span>

### <a name="minimum-hardware-requirements"></a><span data-ttu-id="5feb9-113">最低硬件要求</span><span class="sxs-lookup"><span data-stu-id="5feb9-113">Minimum hardware requirements</span></span>

* <span data-ttu-id="5feb9-114">**CPU** ： 64-位、4核 (物理或虚拟) 、虚拟化扩展 (Intel VT-x 或 AMD-V) 、Core i5 等效项或更高版本建议</span><span class="sxs-lookup"><span data-stu-id="5feb9-114">**CPU** : 64-bit, 4 cores (physical or virtual), virtualization extensions   (Intel VT-x OR AMD-V), Core i5 equivalent or higher recommended</span></span>
* <span data-ttu-id="5feb9-115">**物理内存** ： 8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="5feb9-115">**Physical memory** : 8-GB RAM</span></span>
* <span data-ttu-id="5feb9-116">**硬盘** ：系统驱动器上有 10 GB 的可用空间 (SSD 建议) </span><span class="sxs-lookup"><span data-stu-id="5feb9-116">**Hard disk** : 10 GB of free space on the system drive (SSD recommended)</span></span>

### <a name="minimum-software-requirements"></a><span data-ttu-id="5feb9-117">最低软件要求</span><span class="sxs-lookup"><span data-stu-id="5feb9-117">Minimum software requirements</span></span>

* <span data-ttu-id="5feb9-118">**Windows 10** ： Windows 10 企业版，客户端内部版本 2004 (20H1) 内部版本19041</span><span class="sxs-lookup"><span data-stu-id="5feb9-118">**Windows 10** : Windows 10 Enterprise edition, Client Build version 2004 (20H1) build 19041</span></span>
* <span data-ttu-id="5feb9-119">**Office** ： Office Beta 频道内部版本 2008 16.0.13212 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5feb9-119">**Office** : Office Beta Channel Build version 2008 16.0.13212 or later</span></span>
* <span data-ttu-id="5feb9-120">**更新包** ： Windows 10 累积的每月安全更新 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span><span class="sxs-lookup"><span data-stu-id="5feb9-120">**Update package** : Windows 10 cumulative monthly security updates [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)</span></span> 

<span data-ttu-id="5feb9-121">有关系统要求的详细信息，请参阅 [Microsoft Defender 应用程序防护的系统要求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。</span><span class="sxs-lookup"><span data-stu-id="5feb9-121">For detailed system requirements, refer to [System requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard).</span></span> <span data-ttu-id="5feb9-122">若要了解有关 Office 预览体验成员预览版的详细信息，请参阅 [部署 Office 预览体验成员内部版本](https://insider.office.com/business/deploy)入门。</span><span class="sxs-lookup"><span data-stu-id="5feb9-122">To learn more about Office Insider Preview builds, refer to [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="5feb9-123">许可要求</span><span class="sxs-lookup"><span data-stu-id="5feb9-123">Licensing requirements</span></span>
* <span data-ttu-id="5feb9-124">Microsoft 365 E5 或 Microsoft 365 E5 安全</span><span class="sxs-lookup"><span data-stu-id="5feb9-124">Microsoft 365 E5 or Microsoft 365 E5 Security</span></span>

## <a name="deploy-application-guard-for-office"></a><span data-ttu-id="5feb9-125">部署适用于 Office 的应用程序防护</span><span class="sxs-lookup"><span data-stu-id="5feb9-125">Deploy Application Guard for Office</span></span>

### <a name="enable-application-guard-for-office"></a><span data-ttu-id="5feb9-126">启用 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="5feb9-126">Enable Application Guard for Office</span></span>

1.  <span data-ttu-id="5feb9-127">下载并安装 **Windows 10 累积的每月安全更新 KB4571756** 。</span><span class="sxs-lookup"><span data-stu-id="5feb9-127">Download and install **Windows 10 cumulative monthly security updates KB4571756**.</span></span> 

2.  <span data-ttu-id="5feb9-128">在 Windows 功能下选择 " **Microsoft Defender 应用程序防护** "，然后选择 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="5feb9-128">Select **Microsoft Defender Application Guard** under Windows Features and select **OK**.</span></span> <span data-ttu-id="5feb9-129">启用应用程序防护功能将提示系统重新启动。</span><span class="sxs-lookup"><span data-stu-id="5feb9-129">Enabling the Application Guard feature will prompt a system reboot.</span></span> <span data-ttu-id="5feb9-130">可以选择立即重新启动，也可以选择在步骤3之后重新启动。</span><span class="sxs-lookup"><span data-stu-id="5feb9-130">You can choose to reboot now or after step 3.</span></span>

    ![显示 AG 的 "Windows 功能" 对话框](../../media/ag03-deploy.png)
    
    <span data-ttu-id="5feb9-132">还可以通过以管理员身份运行以下 PowerShell 命令来启用此功能：</span><span class="sxs-lookup"><span data-stu-id="5feb9-132">The feature can also be enabled by running the following PowerShell command as administrator:</span></span> 

    ```powershell
    Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard 
    ```

3.  <span data-ttu-id="5feb9-133">在 " **计算机配置 \\ 管理模板" \\ Windows 组件 " \\ Microsoft defender 应用程序防护** " 中，查找位于托管模式组策略中的 Microsoft defender 应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="5feb9-133">Look for the Microsoft Defender Application Guard in Managed Mode group policy located at **Computer Configuration\\Administrative Templates\\Windows Components\\Microsoft Defender Application Guard**.</span></span> <span data-ttu-id="5feb9-134">通过将 "选项" 下的值设置为 **2** 或 **3** ，然后选择 **"确定" 或 "** **应用** "，打开此策略。</span><span class="sxs-lookup"><span data-stu-id="5feb9-134">Turn this policy on by setting the value under Options as **2** or **3** then selecting **OK** or **Apply**.</span></span>

    ![在托管模式下打开 AG](../../media/ag04-deploy.png)
  
    <span data-ttu-id="5feb9-136">或者，您可以设置相应的 CSP 策略：</span><span class="sxs-lookup"><span data-stu-id="5feb9-136">Alternatively, you can set the corresponding CSP policy:</span></span> 

    <span data-ttu-id="5feb9-137">OMA-URI： **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    </span><span class="sxs-lookup"><span data-stu-id="5feb9-137">OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    </span></span><br><span data-ttu-id="5feb9-138">数据类型： **Integer** 
</span><span class="sxs-lookup"><span data-stu-id="5feb9-138">Data type: **Integer** 
</span></span><br><span data-ttu-id="5feb9-139">值： **2**</span><span class="sxs-lookup"><span data-stu-id="5feb9-139">Value: **2**</span></span>


4.  <span data-ttu-id="5feb9-140">重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="5feb9-140">Reboot the system.</span></span>

### <a name="set-diagnostics--feedback-to-send-full-data"></a><span data-ttu-id="5feb9-141">设置诊断 & 反馈以发送完整数据</span><span class="sxs-lookup"><span data-stu-id="5feb9-141">Set Diagnostics & feedback to send full data</span></span>

<span data-ttu-id="5feb9-142">此步骤可确保确定和修复问题所需的数据正在到达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="5feb9-142">This step ensures that the data necessary to identify and fix problems is reaching Microsoft.</span></span> <span data-ttu-id="5feb9-143">按照以下步骤在你的 Windows 设备上启用诊断：</span><span class="sxs-lookup"><span data-stu-id="5feb9-143">Follow these steps to enable diagnostics on your Windows device:</span></span>

1.  <span data-ttu-id="5feb9-144">打开 "开始" 菜单中的 " **设置** "。</span><span class="sxs-lookup"><span data-stu-id="5feb9-144">Open **Settings** from the Start menu.</span></span>

    ![“开始”菜单](../../media/ag05-diagnostic.png)

2.  <span data-ttu-id="5feb9-146">在 " **Windows 设置** " 中，选择 " **隐私** "。</span><span class="sxs-lookup"><span data-stu-id="5feb9-146">On **Windows Settings** , select **Privacy**.</span></span>

    ![Windows 设置菜单](../../media/ag06-diagnostic.png)

3.  <span data-ttu-id="5feb9-148">在 "隐私" 下，选择 " **诊断 & 反馈** " 并选择 " **可选诊断数据** "。</span><span class="sxs-lookup"><span data-stu-id="5feb9-148">Under Privacy, select **Diagnostics & feedback** and select **Optional diagnostic data**.</span></span>

    ![诊断和反馈菜单](../../media/ag07a-diagnostic.png)

<span data-ttu-id="5feb9-150">有关配置 Windows 诊断设置的详细信息，请参阅 [在组织中配置 windows 诊断数据](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。</span><span class="sxs-lookup"><span data-stu-id="5feb9-150">For more on configuring Windows diagnostic settings, refer to [Configuring Windows diagnostic data in your organization](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).</span></span>

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a><span data-ttu-id="5feb9-151">确认 Office 相关应用程序防护已启用且正常工作</span><span class="sxs-lookup"><span data-stu-id="5feb9-151">Confirm that Application Guard for Office is enabled and working</span></span>

<span data-ttu-id="5feb9-152">在确认已启用 Office 的应用程序防护功能之前，请在已部署策略的设备上启动 Word、Excel 或 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="5feb9-152">Before confirming that the Application Guard for Office is enabled, launch Word, Excel, or PowerPoint on a device where the policies have been deployed.</span></span> <span data-ttu-id="5feb9-153">请确保 Office 已激活。</span><span class="sxs-lookup"><span data-stu-id="5feb9-153">Make sure Office is activated.</span></span> <span data-ttu-id="5feb9-154">您可能需要使用您的工作标识，以便先激活 Office 产品。</span><span class="sxs-lookup"><span data-stu-id="5feb9-154">You may need to use your work identity to activate the Office product first.</span></span>

<span data-ttu-id="5feb9-155">若要确认 Office 的应用程序防护功能现已启用，请启动 Word、Excel 或 PowerPoint 并打开不受信任的文档。</span><span class="sxs-lookup"><span data-stu-id="5feb9-155">To confirm that Application Guard for Office is now enabled, launch Word, Excel, or PowerPoint and open an untrusted document.</span></span> <span data-ttu-id="5feb9-156">例如，您可以打开从 internet 下载的文档或从组织外部的某个人的电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="5feb9-156">For example, you can open a document downloaded from the internet or an email attachment from someone outside your organization.</span></span>

<span data-ttu-id="5feb9-157">在第一次启动不受信任的文件时，您可能会看到如下所示的 Office 初始屏幕。</span><span class="sxs-lookup"><span data-stu-id="5feb9-157">On the first launch of an untrusted file, you may see an Office splash screen like the one below.</span></span> <span data-ttu-id="5feb9-158">它可能会在激活 Office 的应用程序防护和打开文件时显示一段时间。</span><span class="sxs-lookup"><span data-stu-id="5feb9-158">It might show for some time while Application Guard for Office is being activated and the file is being opened.</span></span> <span data-ttu-id="5feb9-159">随后启动不受信任的文件的速度应更快。</span><span class="sxs-lookup"><span data-stu-id="5feb9-159">Subsequent launches of untrusted files should be faster.</span></span>

![Office 应用程序初始屏幕](../../media/ag08-confirm.png)


<span data-ttu-id="5feb9-161">打开文件时，该文件应显示文件在 Office 应用程序防护中打开的一些可视指示器：</span><span class="sxs-lookup"><span data-stu-id="5feb9-161">Upon being opened, the file should display a few visual indicators that the file was opened inside Application Guard for Office:</span></span>

* <span data-ttu-id="5feb9-162">功能区中的标注</span><span class="sxs-lookup"><span data-stu-id="5feb9-162">A callout in the ribbon</span></span>

    ![显示小型应用程序防护注释的文档文件](../../media/ag09-confirm.png)
* <span data-ttu-id="5feb9-164">在任务栏中带有屏蔽的应用程序图标</span><span class="sxs-lookup"><span data-stu-id="5feb9-164">The application icon with a shield in the taskbar</span></span> 

    ![任务栏中的图标](../../media/ag12-limitations.png)



## <a name="configure-application-guard-for-office"></a><span data-ttu-id="5feb9-166">配置适用于 Office 的应用程序防护</span><span class="sxs-lookup"><span data-stu-id="5feb9-166">Configure Application Guard for Office</span></span>
<span data-ttu-id="5feb9-167">Office 支持以下策略，以使您能够配置适用于 Office 的应用程序防护功能。</span><span class="sxs-lookup"><span data-stu-id="5feb9-167">Office supports the following policies to enable you to configure the capabilities of Application Guard for Office.</span></span> <span data-ttu-id="5feb9-168">可以通过组策略或 Office 云策略服务配置这些策略。</span><span class="sxs-lookup"><span data-stu-id="5feb9-168">These policies can be configured through Group policies or through the Office cloud policy service.</span></span> 

>[!NOTE] 
> <span data-ttu-id="5feb9-169">这些策略很快就会推出。</span><span class="sxs-lookup"><span data-stu-id="5feb9-169">These policies will become available soon.</span></span>
><span data-ttu-id="5feb9-170">此外，配置这些策略可以对在 Office 应用程序防护中打开的文件禁用某些功能。</span><span class="sxs-lookup"><span data-stu-id="5feb9-170">Also, configuring these policies can disable some functionalities for files opened in Application Guard for Office.</span></span>

| <span data-ttu-id="5feb9-171">Policy</span><span class="sxs-lookup"><span data-stu-id="5feb9-171">Policy</span></span>                                                                          | <span data-ttu-id="5feb9-172">说明</span><span class="sxs-lookup"><span data-stu-id="5feb9-172">Description</span></span>                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5feb9-173">禁用 Office 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="5feb9-173">Disable Application Guard for Office</span></span>                                            | <span data-ttu-id="5feb9-174">启用此策略将强制 Word、Excel 和 PowerPoint 使用受保护的视图隔离容器，而不是应用程序防护 Office。</span><span class="sxs-lookup"><span data-stu-id="5feb9-174">Enabling this policy will force Word, Excel, and PowerPoint to use the Protected View isolation container instead of Application Guard for Office.</span></span> <span data-ttu-id="5feb9-175">此策略可用于临时禁用 Office 的应用程序防护（如果在使其处于启用状态时出现问题）。</span><span class="sxs-lookup"><span data-stu-id="5feb9-175">This policy can be used to temporarily disable Application Guard for Office when there are issues in leaving it enabled for Edge.</span></span>                                  |
| <span data-ttu-id="5feb9-176">对在应用程序防护中打开的文档禁用复制/粘贴</span><span class="sxs-lookup"><span data-stu-id="5feb9-176">Disable copy/paste for documents opened in Application Guard</span></span>                    | <span data-ttu-id="5feb9-177">启用此策略将阻止用户从 Office 应用程序防护中打开的文档中复制和粘贴内容，并将其粘贴到在其外部打开的文档中。</span><span class="sxs-lookup"><span data-stu-id="5feb9-177">Enabling this policy will prevent a user from copying and pasting content from a document opened in Application Guard for Office to a document opened outside it.</span></span>                                                                                                                                   |
| <span data-ttu-id="5feb9-178">阻止用户删除文件上的应用程序防护保护</span><span class="sxs-lookup"><span data-stu-id="5feb9-178">Prevent users from removing Application Guard protection on files</span></span>               | <span data-ttu-id="5feb9-179">启用此策略将删除 Office 应用程序体验) 中的选项 (，以禁用应用程序防护保护或在应用程序防护外部打开文件。</span><span class="sxs-lookup"><span data-stu-id="5feb9-179">Enabling this policy will remove the option (within the Office application experience) to disable Application Guard protection or open a file outside Application Guard.</span></span> <br><br><span data-ttu-id="5feb9-180">**注意：** 用户仍然可以通过手动删除文件中的标记 web 属性或将文档移到受信任位置来绕过此策略。</span><span class="sxs-lookup"><span data-stu-id="5feb9-180">**Note:** Users can still bypass this policy by manually removing the mark-of-the-web property from the file or by moving a document to a Trusted location.</span></span> |
| <span data-ttu-id="5feb9-181">限制在应用程序防护中打开的文档打印</span><span class="sxs-lookup"><span data-stu-id="5feb9-181">Restrict printing from documents opened in Application Guard</span></span>                    | <span data-ttu-id="5feb9-182">启用此策略将限制用户可以从在 Office 的应用程序防护中打开的文件打印到的打印机。</span><span class="sxs-lookup"><span data-stu-id="5feb9-182">Enabling this policy will limit printers a user can print to from a file opened in Application Guard for Office.</span></span> <span data-ttu-id="5feb9-183">例如，可以使用此策略将用户限制为仅打印到 PDF。</span><span class="sxs-lookup"><span data-stu-id="5feb9-183">For example, you can use this policy to restrict users to only print to PDF.</span></span>                              |
| <span data-ttu-id="5feb9-184">对在应用程序防护中打开的文档关闭相机和麦克风访问</span><span class="sxs-lookup"><span data-stu-id="5feb9-184">Turn off camera and microphone access for documents opened in Application Guard</span></span> | <span data-ttu-id="5feb9-185">启用此策略将删除 Office 的应用程序防护中对相机和麦克风的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5feb9-185">Enabling this policy will remove Office access to Camera and Microphone inside Application Guard for Office.</span></span>                                                                                                                                                                                                     |
>[!NOTE] 
><span data-ttu-id="5feb9-186">以下策略将要求用户注销并重新登录到 Windows 以使其生效：</span><span class="sxs-lookup"><span data-stu-id="5feb9-186">The following policies will require the user to log off and re-login to Windows to take effect:</span></span>
> 
> *  <span data-ttu-id="5feb9-187">对在应用程序防护中打开的文档禁用复制/粘贴</span><span class="sxs-lookup"><span data-stu-id="5feb9-187">Disable copy/paste for documents opened in Application Guard</span></span>
>*  <span data-ttu-id="5feb9-188">限制对在应用程序防护中打开的文档的打印</span><span class="sxs-lookup"><span data-stu-id="5feb9-188">Restrict printing for documents opened in Application Guard</span></span>
> *  <span data-ttu-id="5feb9-189">关闭在应用程序防护中打开的对文档的摄像头和麦克风访问</span><span class="sxs-lookup"><span data-stu-id="5feb9-189">Turn off camera and mic access to documents opened in Application Guard</span></span>


## <a name="submit-feedback"></a><span data-ttu-id="5feb9-190">提交反馈</span><span class="sxs-lookup"><span data-stu-id="5feb9-190">Submit feedback</span></span>

### <a name="submit-feedback-via-feedback-hub"></a><span data-ttu-id="5feb9-191">通过反馈中心提交反馈</span><span class="sxs-lookup"><span data-stu-id="5feb9-191">Submit feedback via Feedback Hub</span></span>

<span data-ttu-id="5feb9-192">如果您在启动 Office 的应用程序防护时遇到任何问题，则建议您通过反馈中心提交反馈：</span><span class="sxs-lookup"><span data-stu-id="5feb9-192">If you encounter any issues when launching Application Guard for Office, you are encouraged to submit your feedback via Feedback Hub:</span></span>

1.  <span data-ttu-id="5feb9-193">打开 " **反馈中心" 应用** 并登录。</span><span class="sxs-lookup"><span data-stu-id="5feb9-193">Open the **Feedback Hub app** and sign in.</span></span>

2.  <span data-ttu-id="5feb9-194">如果在启动应用程序防护时收到错误对话框，请在错误对话框中选择 " **报告给 Microsoft** " 以启动新的反馈提交。</span><span class="sxs-lookup"><span data-stu-id="5feb9-194">If you get an error dialog while launching Application Guard, select **Report to Microsoft** in the error dialog to start a new feedback submission.</span></span> <span data-ttu-id="5feb9-195">否则，导航到 <https://aka.ms/wdagoffice-fb> 以选择 "应用程序防护" 的正确类别，然后选择 "+ 在右上角 **添加新反馈** "。</span><span class="sxs-lookup"><span data-stu-id="5feb9-195">Otherwise, navigate to <https://aka.ms/wdagoffice-fb> to select the correct category for Application Guard, then select **+ Add new feedback** near the top right.</span></span>

3.  <span data-ttu-id="5feb9-196">如果尚未填写您的反馈框，请填写 " **汇总您的反馈** " 框。</span><span class="sxs-lookup"><span data-stu-id="5feb9-196">Fill in the **Summarize your feedback** box if it isn’t already filled in for you.</span></span>

4.  <span data-ttu-id="5feb9-197">在 " **详细** 说明" 框中填写你遇到的问题的详细说明和所需的步骤，然后选择 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="5feb9-197">Fill in the **Explain in more detail** box with a detailed description of the issue you experienced and what steps you took, then select **Next**.</span></span>

5.  <span data-ttu-id="5feb9-198">选择 "问题" 旁边的气泡。</span><span class="sxs-lookup"><span data-stu-id="5feb9-198">Select the bubble next to Problem.</span></span> <span data-ttu-id="5feb9-199">确保选择的类别是 **安全和隐私 \> Microsoft Defender 应用程序防护– Office** ，然后选择 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="5feb9-199">Make sure the category selected is **Security and Privacy \> Microsoft Defender Application Guard – Office** , then select **Next**.</span></span>

6.  <span data-ttu-id="5feb9-200">依次选择 " **新反馈** " 和 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="5feb9-200">Select **New feedback** , then **Next**.</span></span>

7.  <span data-ttu-id="5feb9-201">收集有关此问题的跟踪：</span><span class="sxs-lookup"><span data-stu-id="5feb9-201">Collect traces about the issue:</span></span>

    1. <span data-ttu-id="5feb9-202">展开 " **重新创建我的问题** " 磁贴。</span><span class="sxs-lookup"><span data-stu-id="5feb9-202">Expand the **Recreate my problem** tile.</span></span>

    2.  <span data-ttu-id="5feb9-203">如果在运行应用程序防护时遇到问题，请打开应用程序防护实例。</span><span class="sxs-lookup"><span data-stu-id="5feb9-203">If the issue you’re experiencing occurs while Application Guard is running, open an Application Guard instance.</span></span> <span data-ttu-id="5feb9-204">执行此操作后，将从应用程序防护容器中收集其他跟踪。</span><span class="sxs-lookup"><span data-stu-id="5feb9-204">Doing this allows additional traces to be collected from within the Application Guard container.</span></span>

    3.  <span data-ttu-id="5feb9-205">选择 " **开始录制** " 并等待磁贴停止旋转并说出 " *停止录制* "。</span><span class="sxs-lookup"><span data-stu-id="5feb9-205">Select **Start recording** and wait for the tile to stop spinning and say *Stop recording*.</span></span>

    4.  <span data-ttu-id="5feb9-206">使用应用程序防护完全重现问题。</span><span class="sxs-lookup"><span data-stu-id="5feb9-206">Fully reproduce the issue with Application Guard.</span></span> <span data-ttu-id="5feb9-207">这可能包括尝试启动应用程序防护实例并等待它失败，或在正在运行的应用程序防护实例中再现问题。</span><span class="sxs-lookup"><span data-stu-id="5feb9-207">This might include attempting to launch an Application Guard instance and waiting until it fails, or reproducing an issue in a running Application Guard instance.</span></span>

    5.  <span data-ttu-id="5feb9-208">选择 " **停止录制** " 磁贴。</span><span class="sxs-lookup"><span data-stu-id="5feb9-208">Select the **Stop recording** tile.</span></span>

    6.  <span data-ttu-id="5feb9-209">保持任何正在运行的应用程序防护实例/s 处于打开状态，即使在提交之后几分钟，也可以收集容器诊断。</span><span class="sxs-lookup"><span data-stu-id="5feb9-209">Keep any running Application Guard instance/s open, even until a few minutes after submission, so that container diagnostics can also be collected.</span></span>

8.  <span data-ttu-id="5feb9-210">附加与问题相关的任何相关的屏幕截图或文件。</span><span class="sxs-lookup"><span data-stu-id="5feb9-210">Attach any relevant screenshots or files related to the problem.</span></span>

9.  <span data-ttu-id="5feb9-211">选择“ **提交** ”。</span><span class="sxs-lookup"><span data-stu-id="5feb9-211">Select **Submit**.</span></span>



### <a name="submit-feedback-via-office-customer-voice"></a><span data-ttu-id="5feb9-212">通过 Office 客户语音提交反馈</span><span class="sxs-lookup"><span data-stu-id="5feb9-212">Submit feedback via Office Customer Voice</span></span>

<span data-ttu-id="5feb9-213">如果在应用程序防护中打开 Office 文档时出现问题，则还可以从 Office 中提交反馈。</span><span class="sxs-lookup"><span data-stu-id="5feb9-213">You may also submit feedback from within Office if the issue happens when Office documents are opened in Application Guard.</span></span> <span data-ttu-id="5feb9-214">有关提交反馈的信息，请参阅 [Office 预览体验手册](https://insider.office.com/handbook) 。</span><span class="sxs-lookup"><span data-stu-id="5feb9-214">Refer to the [Office Insider Handbook](https://insider.office.com/handbook) for submitting feedback.</span></span>

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a><span data-ttu-id="5feb9-215">与 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 的集成</span><span class="sxs-lookup"><span data-stu-id="5feb9-215">Integration with Microsoft Defender for Endpoint and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="5feb9-216">适用于 Office 的应用程序防护将与 Microsoft Defender for Endpoint 集成，以提供有关隔离环境中发生的恶意活动的监视和警报。</span><span class="sxs-lookup"><span data-stu-id="5feb9-216">Application Guard for Office is integrated with Microsoft Defender for Endpoint to provide monitoring and alerting on malicious activity happening in the isolated environment.</span></span>

<span data-ttu-id="5feb9-217">Microsoft Defender for Endpoint 是一种安全平台，旨在帮助企业网络阻止、检测、调查和响应高级威胁。</span><span class="sxs-lookup"><span data-stu-id="5feb9-217">Microsoft Defender for Endpoint is a security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span> <span data-ttu-id="5feb9-218">有关此平台的更多详细信息，请访问 [Microsoft Defender For Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 页。</span><span class="sxs-lookup"><span data-stu-id="5feb9-218">For more details about this platform, visit the [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) page.</span></span> <span data-ttu-id="5feb9-219">有关将设备加入到此平台的详细信息，请参阅 [Microsoft Defender For Endpoint service 的板载设备](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="5feb9-219">Learn more about onboarding devices to this platform at [Onboard devices to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span>

<span data-ttu-id="5feb9-220">您还可以配置 Microsoft Defender for Office 365 以使用适用于终结点的 Defender。</span><span class="sxs-lookup"><span data-stu-id="5feb9-220">You can also configure Microsoft Defender for Office 365 to work with Defender for Endpoint.</span></span> <span data-ttu-id="5feb9-221">请参阅将 [适用于 Office 365 的 defender 与 Microsoft Defender For Endpoint 集成](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="5feb9-221">Refer to [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide).</span></span>

## <a name="limitations-and-considerations"></a><span data-ttu-id="5feb9-222">限制和注意事项</span><span class="sxs-lookup"><span data-stu-id="5feb9-222">Limitations and considerations</span></span>

* <span data-ttu-id="5feb9-223">适用于 Office 的应用程序防护是一种限制模式，它将不受信任的文档与访问受信任的公司资源、intranet、用户标识和计算机上的任意文件隔离。</span><span class="sxs-lookup"><span data-stu-id="5feb9-223">Application Guard for Office is a restricted mode that isolates untrusted documents from accessing trusted corporate resources, intranet, the user's identity, and arbitrary files present on the computer.</span></span> <span data-ttu-id="5feb9-224">因此，如果用户尝试访问依赖于此类访问的功能（例如，从磁盘上的本地文件中插入图片），它将会失败，并生成如下所示的提示。</span><span class="sxs-lookup"><span data-stu-id="5feb9-224">As a result, if a user tries to access a feature that has a dependency on such access, for example, inserting a picture from a local file on disk, it will fail and produce a prompt like the one below.</span></span> <span data-ttu-id="5feb9-225">若要使不受信任的文档能够访问受信任的资源，用户必须从文档中删除应用程序防护保护。</span><span class="sxs-lookup"><span data-stu-id="5feb9-225">To enable an untrusted document to access trusted resources, users must remove Application Guard protection from the document.</span></span>

    ![对话框说为帮助您保持安全，此功能不可用](../../media/ag10-limitations.png)

    >[!NOTE]    
    ><span data-ttu-id="5feb9-227">建议仅当用户信任文件及其来源或来自何处时才删除保护。</span><span class="sxs-lookup"><span data-stu-id="5feb9-227">Advise users to only remove protection if they trust the file and its source or where it came from.</span></span>

* <span data-ttu-id="5feb9-228">在 Office 相关应用程序防护中禁用了宏和 ActiveX 控件等文档中的活动内容。</span><span class="sxs-lookup"><span data-stu-id="5feb9-228">Active content in documents like macros and ActiveX controls are disabled in Application Guard for Office.</span></span> <span data-ttu-id="5feb9-229">用户需要删除应用程序防护保护以启用活动内容。</span><span class="sxs-lookup"><span data-stu-id="5feb9-229">Users need to remove Application Guard protection to enable active content.</span></span>

* <span data-ttu-id="5feb9-230">从其他组织以只读方式在应用程序防护中打开的网络共享或从 OneDrive、OneDrive for business 或 SharePoint Online 共享的文件中打开的不受信任文件。</span><span class="sxs-lookup"><span data-stu-id="5feb9-230">Untrusted files opened from network shares or files shared from OneDrive, OneDrive for Business, or SharePoint Online from a different organization open as read-only in Application Guard.</span></span> <span data-ttu-id="5feb9-231">用户可以保存此类文件的本地副本，以继续在容器中工作或取消保护以直接使用原始文件。</span><span class="sxs-lookup"><span data-stu-id="5feb9-231">Users can save a local copy of such files to continue working in the container or remove protection to directly work with the original file.</span></span>

* <span data-ttu-id="5feb9-232">受信息权限管理 (IRM 保护的文件) 继续在受保护的视图中打开。</span><span class="sxs-lookup"><span data-stu-id="5feb9-232">Files that are protected by Information Rights Management (IRM) continue to   open in Protected View.</span></span>
* <span data-ttu-id="5feb9-233">在用户注销并重新登录或重新启动设备后，Office 应用程序防护中 Office 应用程序的任何自定义设置都不会保留。</span><span class="sxs-lookup"><span data-stu-id="5feb9-233">Any customizations to Office applications in Application Guard for Office will not persist after a user logs off and logs back in or reboots the device.</span></span> 

* <span data-ttu-id="5feb9-234">只有使用 UIA 框架的辅助功能工具才能为在 Office 应用程序防护中打开的文件提供可访问的体验。</span><span class="sxs-lookup"><span data-stu-id="5feb9-234">Only Accessibility tools that use the UIA framework can provide an accessible experience for files opened in Application Guard for Office.</span></span>

* <span data-ttu-id="5feb9-235">安装后首次启动应用程序防护时，需要网络连接。</span><span class="sxs-lookup"><span data-stu-id="5feb9-235">Network connectivity is required for the first launch of Application Guard after installation.</span></span> <span data-ttu-id="5feb9-236">这是应用程序防护验证许可证所必需的。</span><span class="sxs-lookup"><span data-stu-id="5feb9-236">This is required for Application Guard to validate the license.</span></span>
* <span data-ttu-id="5feb9-237">在文档的 "信息" 部分中，" *上次修改者* " 属性可能会显示 "WDAGUtilityAccount" 作为用户。</span><span class="sxs-lookup"><span data-stu-id="5feb9-237">In the document's info section, the *Last Modified By* property may display WDAGUtilityAccount as the user.</span></span> <span data-ttu-id="5feb9-238">这是在应用程序防护中配置的匿名用户，在应用程序防护容器中不共享桌面用户的标识。</span><span class="sxs-lookup"><span data-stu-id="5feb9-238">This is the anonymous user configured in Application Guard given that the desktop user's identity is not shared inside the Application Guard container.</span></span> 

## <a name="performance-optimizations-for-application-guard"></a><span data-ttu-id="5feb9-239">应用程序防护的性能优化</span><span class="sxs-lookup"><span data-stu-id="5feb9-239">Performance optimizations for Application Guard</span></span> 

<span data-ttu-id="5feb9-240">本节概述了在 Office 相关应用程序防护中使用的性能优化。</span><span class="sxs-lookup"><span data-stu-id="5feb9-240">This section provides an overview of the performance optimizations used in Application Guard for Office.</span></span> <span data-ttu-id="5feb9-241">此信息可帮助管理员在启用应用程序防护时，诊断与 Office 性能或整个系统相关的用户的报告。</span><span class="sxs-lookup"><span data-stu-id="5feb9-241">This information can help administrators diagnose reports from users related to the performance of Office or the overall system when Application Guard is enabled.</span></span> 

<span data-ttu-id="5feb9-242">应用程序防护使用虚拟化容器将不受信任的文档隔离在系统之外。</span><span class="sxs-lookup"><span data-stu-id="5feb9-242">Application Guard uses a virtualized container to isolate untrusted documents away from the system.</span></span> <span data-ttu-id="5feb9-243">在用户打开不受信任的文档时，创建容器并将应用程序防护容器设置为打开 Office 文档的过程可能会对用户体验产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="5feb9-243">The process of creating a container and setting up the Application Guard container to open Office documents has a performance overhead that might negatively impact user experience when users open an  untrusted document.</span></span> 


<span data-ttu-id="5feb9-244">若要向用户提供预期的文件打开体验，应用程序防护在系统上满足以下试探法时使用逻辑来预创建容器：用户在过去28天内打开了受保护的视图或应用程序防护中的文件。</span><span class="sxs-lookup"><span data-stu-id="5feb9-244">To provide users with the expected file opening experience, Application Guard uses logic to pre-create a container when the following heuristic is met on a system: A user has opened a file in either Protected View or Application Guard in the past 28 days.</span></span> 

<span data-ttu-id="5feb9-245">当满足此启发时，Office 将在用户登录到 Windows 之后预先为该用户创建应用程序防护容器。</span><span class="sxs-lookup"><span data-stu-id="5feb9-245">When this heuristic is met, Office will pre-create an Application Guard container for the user after they log in to Windows.</span></span> <span data-ttu-id="5feb9-246">在此预创建操作进行过程中，系统可能会遇到性能降低的情况。</span><span class="sxs-lookup"><span data-stu-id="5feb9-246">When this pre-create operation is in progress, the system may experience slow performance.</span></span> <span data-ttu-id="5feb9-247">此操作将在操作完成后立即解决。</span><span class="sxs-lookup"><span data-stu-id="5feb9-247">This will resolve as soon as the operation completes.</span></span> 


>[!NOTE] 
><span data-ttu-id="5feb9-248">用于预创建容器的启发所需的提示是由 Office 应用程序在用户使用时生成的。</span><span class="sxs-lookup"><span data-stu-id="5feb9-248">The hints needed for the heuristic used to pre-create the container are generated by Office applications as a user uses them.</span></span> <span data-ttu-id="5feb9-249">如果用户在启用了应用程序防护的新系统上安装 Office，则在用户第一次在系统上打开不受信任的文档之前，Office 将不会预先创建该容器。</span><span class="sxs-lookup"><span data-stu-id="5feb9-249">If a user installs Office on a new system where Application Guard is enabled, Office will not pre-create the container until after the first time a user opens an untrusted document on the system.</span></span> <span data-ttu-id="5feb9-250">用户将会发现，在应用程序防护中打开第一个文件需要的时间较长。</span><span class="sxs-lookup"><span data-stu-id="5feb9-250">The user will observe that this first file takes longer to open in Application Guard.</span></span> 

## <a name="known-issues-in-preview"></a><span data-ttu-id="5feb9-251">预览中的已知问题</span><span class="sxs-lookup"><span data-stu-id="5feb9-251">Known issues in preview</span></span>

* <span data-ttu-id="5feb9-252">单击 "web 链接" (```http``` 或 ```https```) 不会打开浏览器。</span><span class="sxs-lookup"><span data-stu-id="5feb9-252">Clicking on web links (```http``` or ```https```) does not open the browser.</span></span> 
* <span data-ttu-id="5feb9-253">.NET 更新会导致文件无法在应用程序防护中打开。</span><span class="sxs-lookup"><span data-stu-id="5feb9-253">.NET updates cause files to fail to open in Application Guard.</span></span> <span data-ttu-id="5feb9-254">作为一种解决方法，当遇到此问题时，用户可以重新启动其设备。</span><span class="sxs-lookup"><span data-stu-id="5feb9-254">As a workaround, users can reboot their device when this issue is encountered.</span></span>
    <span data-ttu-id="5feb9-255">了解有关在 [尝试打开 Windows Defender 应用程序防护或 Windows 沙盒时收到错误消息时](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)的问题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5feb9-255">Learn more about the issue at [Receiving an error message when attempting to open Windows Defender Application Guard or Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).</span></span>
