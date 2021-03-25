---
title: 自定义受控文件夹访问权限
description: 添加应受受控文件夹访问权限保护的其他文件夹，或允许错误阻止对重要文件更改的应用。
keywords: 受控文件夹访问权限， windows 10， windows defender， 勒索软件， 保护， 文件， 文件夹， 自定义， 添加文件夹， 添加应用， 允许， 添加可执行文件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199897"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="c3d29-104">自定义受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="c3d29-104">Customize controlled folder access</span></span>

<span data-ttu-id="c3d29-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c3d29-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3d29-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3d29-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3d29-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3d29-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c3d29-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="c3d29-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3d29-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c3d29-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="c3d29-110">受控文件夹访问权限可帮助你保护重要数据免受恶意应用和威胁（如勒索软件）的侵害。</span><span class="sxs-lookup"><span data-stu-id="c3d29-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="c3d29-111">受控文件夹访问权限在 Windows Server 2019 和 Windows 10 客户端上受支持。</span><span class="sxs-lookup"><span data-stu-id="c3d29-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="c3d29-112">本文介绍如何自定义受控文件夹访问权限，并包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="c3d29-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="c3d29-113">保护其他文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="c3d29-114">添加应允许访问受保护文件夹的应用</span><span class="sxs-lookup"><span data-stu-id="c3d29-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="c3d29-115">允许已签名的可执行文件访问受保护的文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="c3d29-116">自定义通知</span><span class="sxs-lookup"><span data-stu-id="c3d29-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="c3d29-117">受控文件夹访问权限监视应用是否被检测为恶意活动。</span><span class="sxs-lookup"><span data-stu-id="c3d29-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="c3d29-118">有时，合法应用会阻止对文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="c3d29-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="c3d29-119">如果受控文件夹访问权限影响组织的工作效率，可以考虑在审核模式下运行此功能，以全面评估影响。 [](audit-windows-defender.md)</span><span class="sxs-lookup"><span data-stu-id="c3d29-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="c3d29-120">保护其他文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-120">Protect additional folders</span></span>

<span data-ttu-id="c3d29-121">受控文件夹访问权限适用于许多系统文件夹和默认位置，包括 **文档、\*\*\*\*图片** 和 **电影等文件夹**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="c3d29-122">可以添加要保护的其他文件夹，但不能删除默认列表中的默认文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d29-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="c3d29-123">当你不将文件存储在默认 Windows 库中，或者你已更改库的默认位置时，向受控文件夹访问权限添加其他文件夹可能会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="c3d29-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="c3d29-124">还可以指定网络共享和映射驱动器。</span><span class="sxs-lookup"><span data-stu-id="c3d29-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="c3d29-125">支持环境变量和通配符。</span><span class="sxs-lookup"><span data-stu-id="c3d29-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="c3d29-126">有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="c3d29-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="c3d29-127">可以使用 Windows 安全应用、组策略、PowerShell cmdlet 或移动设备管理配置服务提供程序添加和删除其他受保护的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d29-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="c3d29-128">使用 Windows 安全应用保护其他文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="c3d29-129">通过选择任务栏中的防护图标或搜索"安全"的"开始"菜单打开 Windows 安全 **应用**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="c3d29-130">选择 **病毒&威胁防护**，然后向下滚动到 **勒索软件保护** 部分。</span><span class="sxs-lookup"><span data-stu-id="c3d29-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="c3d29-131">选择 **管理勒索软件保护** 以打开 **勒索软件保护** 窗格。</span><span class="sxs-lookup"><span data-stu-id="c3d29-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="c3d29-132">在"**受控文件夹访问权限"** 部分下，选择 **"受保护的文件夹"。**</span><span class="sxs-lookup"><span data-stu-id="c3d29-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="c3d29-133">在 **"用户访问\*\*\*\*控制"提示符上选择"是**"。</span><span class="sxs-lookup"><span data-stu-id="c3d29-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="c3d29-134">将显示 **"受保护的文件夹** "窗格。</span><span class="sxs-lookup"><span data-stu-id="c3d29-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="c3d29-135">选择 **"添加受保护的文件夹"，** 然后按照提示添加文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d29-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="c3d29-136">使用组策略保护其他文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="c3d29-137">在组策略管理计算机上，打开组 [策略](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)管理控制台，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="c3d29-138">在组 **策略管理编辑器中**，转到计算机 **配置，** 然后选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="c3d29-139">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **Windows Defender攻击防护**  >  **受控文件夹访问权限**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="c3d29-140">双击"**已配置的受保护文件夹"，** 将选项设置为"**已启用"。**</span><span class="sxs-lookup"><span data-stu-id="c3d29-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="c3d29-141">选择 **"显示** "并输入每个文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d29-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="c3d29-142">使用 PowerShell 保护其他文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="c3d29-143">在 **"开始"菜单中键入 PowerShell，** 右 **键单击** "Windows PowerShell并选择"以 **管理员角色运行"**</span><span class="sxs-lookup"><span data-stu-id="c3d29-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="c3d29-144">输入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c3d29-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="c3d29-145">重复步骤 2，直到添加了要保护的所有文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d29-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="c3d29-146">添加的文件夹在 Windows 安全应用中可见。</span><span class="sxs-lookup"><span data-stu-id="c3d29-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![输入上述 cmdlet 的 PowerShell 窗口屏幕截图](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="c3d29-148">用于 `Add-MpPreference` 向列表中追加或添加应用。</span><span class="sxs-lookup"><span data-stu-id="c3d29-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="c3d29-149">使用 `Set-MpPreference` cmdlet 将覆盖现有列表。</span><span class="sxs-lookup"><span data-stu-id="c3d29-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="c3d29-150">使用 MDM CSP 保护其他文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="c3d29-151">使用 [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) 配置服务提供程序 (CSP) 允许应用对受保护的文件夹进行更改。</span><span class="sxs-lookup"><span data-stu-id="c3d29-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="c3d29-152">允许特定应用对受控文件夹进行更改</span><span class="sxs-lookup"><span data-stu-id="c3d29-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="c3d29-153">你可以指定某些应用是否始终被视为安全应用，并授予对受保护文件夹中文件的写访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3d29-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="c3d29-154">如果你知道和信任的特定应用被受控文件夹访问权限功能阻止，则允许应用非常有用。</span><span class="sxs-lookup"><span data-stu-id="c3d29-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3d29-155">默认情况下，Windows 会将视为友好的应用添加到允许列表中。</span><span class="sxs-lookup"><span data-stu-id="c3d29-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="c3d29-156">自动添加的此类应用不会记录在 Windows 安全应用中显示的列表中，也不使用关联的 PowerShell cmdlet 记录。</span><span class="sxs-lookup"><span data-stu-id="c3d29-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="c3d29-157">你无需添加大多数应用。</span><span class="sxs-lookup"><span data-stu-id="c3d29-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="c3d29-158">仅在应用被阻止时添加应用，你可以验证其可信度。</span><span class="sxs-lookup"><span data-stu-id="c3d29-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="c3d29-159">添加应用时，必须指定应用的位置。</span><span class="sxs-lookup"><span data-stu-id="c3d29-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="c3d29-160">仅允许位于该位置的应用访问受保护的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d29-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="c3d29-161">如果应用 (同名) 位于不同的位置，它将不会添加到允许列表中，并且可能会受到受控文件夹访问权限的阻止。</span><span class="sxs-lookup"><span data-stu-id="c3d29-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="c3d29-162">允许的应用程序或服务在启动后仅对受控文件夹具有写访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3d29-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="c3d29-163">例如，在允许更新服务停止并重新启动之前，该服务将继续触发事件。</span><span class="sxs-lookup"><span data-stu-id="c3d29-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="c3d29-164">使用 Windows Defender 安全应用允许特定应用</span><span class="sxs-lookup"><span data-stu-id="c3d29-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="c3d29-165">通过搜索"安全"的"开始"菜单打开 Windows 安全 **应用**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="c3d29-166">选择病毒 **&威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后选择管理 **勒索软件保护**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="c3d29-167">在受控 **文件夹访问权限** 部分下，选择 **允许应用通过受控文件夹访问权限**</span><span class="sxs-lookup"><span data-stu-id="c3d29-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="c3d29-168">选择 **添加允许的应用** 并按照提示添加应用。</span><span class="sxs-lookup"><span data-stu-id="c3d29-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="添加允许的应用按钮":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="c3d29-170">使用组策略允许特定应用</span><span class="sxs-lookup"><span data-stu-id="c3d29-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="c3d29-171">在组策略管理设备上，打开组 [策略管理控制台](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c3d29-172">在组 **策略管理编辑器中**，转到计算机 **配置，** 然后选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="c3d29-173">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **Windows Defender攻击防护**  >  **受控文件夹访问权限**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="c3d29-174">双击配置允许 **的应用程序** 设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="c3d29-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="c3d29-175">选择 **"显示** "并输入每个应用。</span><span class="sxs-lookup"><span data-stu-id="c3d29-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="c3d29-176">使用 PowerShell 允许特定应用</span><span class="sxs-lookup"><span data-stu-id="c3d29-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="c3d29-177">在 **"开始"菜单中键入 PowerShell，** 右 **键单击** "Windows PowerShell并选择"以 **管理员角色运行"**</span><span class="sxs-lookup"><span data-stu-id="c3d29-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="c3d29-178">输入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c3d29-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="c3d29-179">例如，若要添加位于 *C：\apps* *test.exe* 可执行文件，cmdlet 将如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3d29-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="c3d29-180">继续使用 向 `Add-MpPreference -ControlledFolderAccessAllowedApplications` 列表中添加更多应用。</span><span class="sxs-lookup"><span data-stu-id="c3d29-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="c3d29-181">使用此 cmdlet 添加的应用将显示在 Windows 安全应用中。</span><span class="sxs-lookup"><span data-stu-id="c3d29-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="允许应用的 PowerShell cmdlet":::

> [!IMPORTANT]
> <span data-ttu-id="c3d29-183">用于 `Add-MpPreference` 向列表中追加或添加应用。</span><span class="sxs-lookup"><span data-stu-id="c3d29-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="c3d29-184">使用 `Set-MpPreference` cmdlet 将覆盖现有列表。</span><span class="sxs-lookup"><span data-stu-id="c3d29-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="c3d29-185">使用 MDM CSP 允许特定应用</span><span class="sxs-lookup"><span data-stu-id="c3d29-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="c3d29-186">使用 [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) 配置服务提供程序 (CSP) 以允许应用对受保护的文件夹进行更改。</span><span class="sxs-lookup"><span data-stu-id="c3d29-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="c3d29-187">允许已签名的可执行文件访问受保护的文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="c3d29-188">Microsoft Defender for Endpoint 证书和文件指示器可以允许已签名的可执行文件访问受保护的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d29-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="c3d29-189">有关实现的详细信息，请参阅 [创建基于证书的指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)。</span><span class="sxs-lookup"><span data-stu-id="c3d29-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="c3d29-190">这不适用于脚本引擎，包括 Powershell</span><span class="sxs-lookup"><span data-stu-id="c3d29-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="c3d29-191">自定义通知</span><span class="sxs-lookup"><span data-stu-id="c3d29-191">Customize the notification</span></span>

<span data-ttu-id="c3d29-192">有关在触发规则并阻止应用或文件时自定义通知的信息，请参阅在 [Microsoft Defender for Endpoint 中配置警报通知](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)。</span><span class="sxs-lookup"><span data-stu-id="c3d29-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3d29-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3d29-193">See also</span></span>

- [<span data-ttu-id="c3d29-194">使用受控文件夹访问权限保护重要文件夹</span><span class="sxs-lookup"><span data-stu-id="c3d29-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="c3d29-195">启用受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="c3d29-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="c3d29-196">评估攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="c3d29-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
