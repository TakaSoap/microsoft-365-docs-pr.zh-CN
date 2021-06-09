---
title: 启用网络保护功能
description: 使用组策略、PowerShell 或移动设备管理和配置管理器启用网络保护。
keywords: 网络保护， 攻击， 恶意网站， ip， 域， 启用， 打开
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6afdcc16493839e83771ac831831fdbb121663a1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841770"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="3ed3b-104">启用网络保护功能</span><span class="sxs-lookup"><span data-stu-id="3ed3b-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ed3b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3ed3b-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ed3b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ed3b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3ed3b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ed3b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="3ed3b-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="3ed3b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3ed3b-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="3ed3b-110">[网络](network-protection.md) 保护有助于防止员工使用任何应用程序访问可能承载网络钓鱼欺诈、攻击和 Internet 上的其他恶意内容危险域。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="3ed3b-111">可以在 [测试环境中](evaluate-network-protection.md) 审核网络保护，以查看在启用应用之前将阻止哪些应用。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="3ed3b-112">了解有关网络筛选配置选项的详细信息</span><span class="sxs-lookup"><span data-stu-id="3ed3b-112">Learn more about network filtering configuration options</span></span>](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="3ed3b-113">检查网络保护是否已启用</span><span class="sxs-lookup"><span data-stu-id="3ed3b-113">Check if network protection is enabled</span></span>

<span data-ttu-id="3ed3b-114">使用注册表编辑器检查是否在本地设备上启用了网络保护。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="3ed3b-115">选择 **任务栏中的** "开始"按钮并键入 **regedit** 以打开注册表编辑器</span><span class="sxs-lookup"><span data-stu-id="3ed3b-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>

2. <span data-ttu-id="3ed3b-116">从 **HKEY_LOCAL_MACHINE** 菜单中选择"选项"</span><span class="sxs-lookup"><span data-stu-id="3ed3b-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>

3. <span data-ttu-id="3ed3b-117">在嵌套菜单中导航到 **SOFTWARE**  >  **Policies**  >  **Microsoft**  >  **Windows Defender**  >  **Policy Manager**</span><span class="sxs-lookup"><span data-stu-id="3ed3b-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Policy Manager**</span></span> 

4. <span data-ttu-id="3ed3b-118">选择 **EnableNetworkProtection** 以查看设备上网络保护的当前状态</span><span class="sxs-lookup"><span data-stu-id="3ed3b-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="3ed3b-119">0 或 **Off**</span><span class="sxs-lookup"><span data-stu-id="3ed3b-119">0, or **Off**</span></span>
    * <span data-ttu-id="3ed3b-120">1 或 **On**</span><span class="sxs-lookup"><span data-stu-id="3ed3b-120">1, or **On**</span></span>
    * <span data-ttu-id="3ed3b-121">2 或 **审核** 模式</span><span class="sxs-lookup"><span data-stu-id="3ed3b-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="3ed3b-123">启用网络保护</span><span class="sxs-lookup"><span data-stu-id="3ed3b-123">Enable network protection</span></span>

<span data-ttu-id="3ed3b-124">使用以下任一方法启用网络保护：</span><span class="sxs-lookup"><span data-stu-id="3ed3b-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="3ed3b-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ed3b-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="3ed3b-126">移动设备管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="3ed3b-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="3ed3b-127">Microsoft Endpoint Manager /Intune</span><span class="sxs-lookup"><span data-stu-id="3ed3b-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="3ed3b-128">组策略</span><span class="sxs-lookup"><span data-stu-id="3ed3b-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="3ed3b-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ed3b-129">PowerShell</span></span>

1. <span data-ttu-id="3ed3b-130">在 **"开始"菜单中键入 powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"**</span><span class="sxs-lookup"><span data-stu-id="3ed3b-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="3ed3b-131">输入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3ed3b-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="3ed3b-132">可选：使用下列 cmdlet 在审核模式下启用该功能：</span><span class="sxs-lookup"><span data-stu-id="3ed3b-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="3ed3b-133">使用 `Disabled` 而不是 `AuditMode` 或 `Enabled` 来关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="3ed3b-134">移动设备管理(MDM)</span><span class="sxs-lookup"><span data-stu-id="3ed3b-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="3ed3b-135">使用 [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) 配置服务提供程序 (CSP) 启用或禁用网络保护或启用审核模式。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="3ed3b-136">Microsoft Endpoint Manager (以前为 Intune) </span><span class="sxs-lookup"><span data-stu-id="3ed3b-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="3ed3b-137">登录到管理Microsoft Endpoint Manager中心 (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="3ed3b-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="3ed3b-138">创建或编辑 [终结点保护配置文件](/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="3ed3b-138">Create or edit an [endpoint protection configuration profile](/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="3ed3b-139">在 **配置文件设置** 配置策略"下，转到"Microsoft Defender 攻击防护  >  **网络** 筛选  >  **""** 仅启用或  >  审核 **"**</span><span class="sxs-lookup"><span data-stu-id="3ed3b-139">Under **Configuration Settings** in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="3ed3b-140">组策略</span><span class="sxs-lookup"><span data-stu-id="3ed3b-140">Group Policy</span></span>

<span data-ttu-id="3ed3b-141">使用以下过程在加入域的计算机或独立计算机上启用网络保护。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="3ed3b-142">在独立计算机上，**转到"开始**"，然后键入并选择"**编辑组策略"。**</span><span class="sxs-lookup"><span data-stu-id="3ed3b-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="3ed3b-143">*-Or-*</span><span class="sxs-lookup"><span data-stu-id="3ed3b-143">*-Or-*</span></span>

    <span data-ttu-id="3ed3b-144">在加入域的组策略管理计算机上，打开组策略 [](https://technet.microsoft.com/library/cc731212.aspx)管理控制台，右键单击要配置的组策略对象，**然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="3ed3b-145">在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="3ed3b-146">展开树以 **Windows Exploit** Guard  >  **网络Microsoft Defender 防病毒Windows Defender**  >    >  **的组件**。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="3ed3b-147">在早期版本的 Windows 中，组策略路径可能Windows Defender 防病毒"而不是"Microsoft Defender 防病毒"。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="3ed3b-148">双击阻止用户和应用 **访问** 危险网站设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="3ed3b-149">在选项部分中，必须指定以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="3ed3b-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="3ed3b-150">**阻止** - 用户无法访问恶意 IP 地址和域</span><span class="sxs-lookup"><span data-stu-id="3ed3b-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="3ed3b-151">**禁用 (默认)** - 网络保护功能不起作用。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="3ed3b-152">不会阻止用户访问恶意域</span><span class="sxs-lookup"><span data-stu-id="3ed3b-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="3ed3b-153">**审核模式**- 如果用户访问恶意 IP 地址或域，事件将记录在Windows日志中。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="3ed3b-154">但是，不会阻止用户访问地址。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ed3b-155">若要完全启用网络保护，必须将组策略选项设置为 **已启用**，还要在选项下拉菜单中选择阻止。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="3ed3b-156">使用注册表编辑器确认在本地计算机上启用网络保护：</span><span class="sxs-lookup"><span data-stu-id="3ed3b-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="3ed3b-157">选择 **"开始** " **并键入 regedit** 以 **打开注册表编辑器**。</span><span class="sxs-lookup"><span data-stu-id="3ed3b-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="3ed3b-158">导航到 **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span><span class="sxs-lookup"><span data-stu-id="3ed3b-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span></span>

3. <span data-ttu-id="3ed3b-159">选择 **EnableNetworkProtection** 并确认值：</span><span class="sxs-lookup"><span data-stu-id="3ed3b-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="3ed3b-160">0=Off</span><span class="sxs-lookup"><span data-stu-id="3ed3b-160">0=Off</span></span>
   * <span data-ttu-id="3ed3b-161">1=打开</span><span class="sxs-lookup"><span data-stu-id="3ed3b-161">1=On</span></span>
   * <span data-ttu-id="3ed3b-162">2=审核</span><span class="sxs-lookup"><span data-stu-id="3ed3b-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="3ed3b-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ed3b-163">See also</span></span>

* [<span data-ttu-id="3ed3b-164">网络保护</span><span class="sxs-lookup"><span data-stu-id="3ed3b-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="3ed3b-165">网络保护功能评估</span><span class="sxs-lookup"><span data-stu-id="3ed3b-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="3ed3b-166">网络保护疑难解答</span><span class="sxs-lookup"><span data-stu-id="3ed3b-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
