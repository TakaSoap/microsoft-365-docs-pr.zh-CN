---
title: 使用移动设备管理工具载入 Windows 10 设备
description: 使用移动设备管理工具在设备上部署配置包，以便它们可以载入到服务。
keywords: 使用 mdm 载入设备， 设备管理， 载入 Microsoft Defender for Endpoint 设备， mdm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 951b0f33356ab99485f09ccc4147691e13ed3c6e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935001"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="28c12-104">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="28c12-104">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28c12-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="28c12-105">**Applies to:**</span></span>
- [<span data-ttu-id="28c12-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28c12-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28c12-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28c12-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="28c12-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="28c12-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="28c12-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="28c12-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="28c12-110">可以使用移动设备管理 (MDM) 解决方案配置设备。</span><span class="sxs-lookup"><span data-stu-id="28c12-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="28c12-111">Defender for Endpoint 通过提供创建OMA-URIs管理设备的策略来支持 MDM。</span><span class="sxs-lookup"><span data-stu-id="28c12-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="28c12-112">有关使用 Defender for Endpoint CSP 有关详细信息，请参阅 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF 文件](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="28c12-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="28c12-113">准备工作</span><span class="sxs-lookup"><span data-stu-id="28c12-113">Before you begin</span></span>
<span data-ttu-id="28c12-114">如果你使用的是 Microsoft Intune，则必须注册设备 MDM。</span><span class="sxs-lookup"><span data-stu-id="28c12-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="28c12-115">否则，设置将不会成功应用。</span><span class="sxs-lookup"><span data-stu-id="28c12-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="28c12-116">有关使用 Microsoft Intune 启用 MDM 的信息，请参阅 Microsoft [Intune (设备) 。 ](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="28c12-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="28c12-117">使用 Microsoft Intune 载入设备</span><span class="sxs-lookup"><span data-stu-id="28c12-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="28c12-118">[![显示使用 Microsoft Intune 将设备载入到 Defender for Endpoint 的 PDF 的图像 ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="28c12-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="28c12-119">请查看 [PDF 或](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 以查看部署 Defender for Endpoint 中的各个路径。</span><span class="sxs-lookup"><span data-stu-id="28c12-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="28c12-120">按照 [Intune 中的说明操作](https://docs.microsoft.com/intune/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="28c12-120">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="28c12-121">有关使用 Defender for Endpoint CSP 有关详细信息，请参阅 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF 文件](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="28c12-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="28c12-122">载入 **设备的运行状况策略使用** 只读属性，并且无法修正。</span><span class="sxs-lookup"><span data-stu-id="28c12-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="28c12-123">诊断数据报告频率的配置仅适用于 Windows 10 版本 1703 上的设备。</span><span class="sxs-lookup"><span data-stu-id="28c12-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="28c12-124">载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="28c12-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="28c12-125">有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="28c12-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="28c12-126">请查看 [PDF 或](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 以查看部署 Microsoft Defender for Endpoint 的各种路径。</span><span class="sxs-lookup"><span data-stu-id="28c12-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="28c12-127">使用移动设备管理工具离开并监视设备</span><span class="sxs-lookup"><span data-stu-id="28c12-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="28c12-128">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="28c12-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="28c12-129">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="28c12-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="28c12-130">下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="28c12-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="28c12-131">载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。</span><span class="sxs-lookup"><span data-stu-id="28c12-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="28c12-132">从 Microsoft Defender 安全中心获取载 [出程序包](https://securitycenter.windows.com/)：</span><span class="sxs-lookup"><span data-stu-id="28c12-132">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

   1. <span data-ttu-id="28c12-133">在导航窗格中，选择"**设置**  >  **""载出"。**</span><span class="sxs-lookup"><span data-stu-id="28c12-133">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

   1. <span data-ttu-id="28c12-134">选择 Windows 10 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="28c12-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="28c12-135">在"**部署方法"** 字段中，选择 **"移动设备管理/Microsoft Intune"。**</span><span class="sxs-lookup"><span data-stu-id="28c12-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="28c12-136">单击 **"下载程序包**"，然后保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="28c12-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="28c12-137">将 .zip 文件的内容提取到将部署包的网络管理员可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="28c12-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="28c12-138">你应该有一个名为 *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 的文件*。</span><span class="sxs-lookup"><span data-stu-id="28c12-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="28c12-139">使用 Microsoft Intune 自定义配置策略部署以下受支持的 OMA-URI 设置。</span><span class="sxs-lookup"><span data-stu-id="28c12-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="28c12-140">OMA-URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="28c12-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="28c12-141">日期类型：String</span><span class="sxs-lookup"><span data-stu-id="28c12-141">Date type: String</span></span><br/>
      <span data-ttu-id="28c12-142">值：[复制并粘贴 WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 文件的内容中的值]</span><span class="sxs-lookup"><span data-stu-id="28c12-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="28c12-143">有关 Microsoft Intune 策略设置详细信息，请参阅 Microsoft Intune 中的 [Windows 10 策略设置](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="28c12-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="28c12-144">" **载出设备的运行状况状态"策略** 使用只读属性，并且无法修正。</span><span class="sxs-lookup"><span data-stu-id="28c12-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28c12-145">"载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。</span><span class="sxs-lookup"><span data-stu-id="28c12-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="28c12-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="28c12-146">Related topics</span></span>
- [<span data-ttu-id="28c12-147">使用组策略载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="28c12-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="28c12-148">使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="28c12-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="28c12-149">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="28c12-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="28c12-150">载入非永久虚拟桌面基础结构 （VDI） 设备</span><span class="sxs-lookup"><span data-stu-id="28c12-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="28c12-151">在新载入的 Microsoft Defender 终结点设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="28c12-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="28c12-152">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="28c12-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
