---
title: '如何使用 Intune 设备控制 USB 设备和其他可移动 (Windows 10) '
description: 你可以配置 Intune 设置以减少来自可移动存储（如 USB 设备）的威胁。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: eb7043451c4d80e3eca8b0703703ac6d7a459161
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302084"
---
# <a name="how-to-control-usb-devices-and-other-removable-media-using-microsoft-defender-for-endpoint"></a><span data-ttu-id="c68a9-103">如何使用 Microsoft Defender for Endpoint 控制 USB 设备和其他可移动媒体</span><span class="sxs-lookup"><span data-stu-id="c68a9-103">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="c68a9-104">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="c68a9-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="c68a9-105">Microsoft [建议使用分层](https://aka.ms/devicecontrolblog)方法来保护可移动媒体，并且 Microsoft Defender for Endpoint 提供了多个监视和控制功能，以帮助防止未经授权的外围设备中的威胁危害你的设备：</span><span class="sxs-lookup"><span data-stu-id="c68a9-105">Microsoft recommends [a layered approach to securing removable media](https://aka.ms/devicecontrolblog), and Microsoft Defender for Endpoint provides multiple monitoring and control features to help prevent threats in unauthorized peripherals from compromising your devices:</span></span>

1. <span data-ttu-id="c68a9-106">[在适用于终结点高级搜寻](#discover-plug-and-play-connected-events)的 Microsoft Defender 中发现外设的即插即用连接事件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-106">[Discover plug and play connected events for peripherals in Microsoft Defender for Endpoint advanced hunting](#discover-plug-and-play-connected-events).</span></span> <span data-ttu-id="c68a9-107">识别或调查可疑的使用活动。</span><span class="sxs-lookup"><span data-stu-id="c68a9-107">Identify or investigate suspicious usage activity.</span></span>

2. <span data-ttu-id="c68a9-108">配置为仅允许或阻止某些可移动设备并防止威胁。</span><span class="sxs-lookup"><span data-stu-id="c68a9-108">Configure to allow or block only certain removable devices and prevent threats.</span></span>
    1. <span data-ttu-id="c68a9-109">[根据粒度配置允许](#allow-or-block-removable-devices) 或阻止可移动设备，以拒绝对可移动磁盘的写入访问，以及使用 USB 设备 ID 批准或拒绝设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-109">[Allow or block removable devices](#allow-or-block-removable-devices) based on granular configuration to deny write access to removable disks and approve or deny devices by using USB device IDs.</span></span> <span data-ttu-id="c68a9-110">根据单个或一组 Azure AD 用户和设备，灵活分配Azure Active Directory (Azure AD) 设置。</span><span class="sxs-lookup"><span data-stu-id="c68a9-110">Flexible policy assignment of device installation settings based on an individual or group of Azure Active Directory (Azure AD) users and devices.</span></span>

    2. <span data-ttu-id="c68a9-111">[通过启用：防止](#prevent-threats-from-removable-storage) 由可移动存储设备引入的可移动存储的威胁：</span><span class="sxs-lookup"><span data-stu-id="c68a9-111">[Prevent threats from removable storage](#prevent-threats-from-removable-storage) introduced by removable storage devices by enabling:</span></span>  
        - <span data-ttu-id="c68a9-112">Microsoft Defender 防病毒 RTP (RTP) 扫描可移动存储中恶意软件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-112">Microsoft Defender Antivirus real-time protection (RTP) to scan removable storage for malware.</span></span>  
        - <span data-ttu-id="c68a9-113">攻击面减少 (ASR) USB 规则来阻止从 USB 运行的不受信任的和未签名的进程。</span><span class="sxs-lookup"><span data-stu-id="c68a9-113">The Attack Surface Reduction (ASR) USB rule to block untrusted and unsigned processes that run from USB.</span></span>  
        - <span data-ttu-id="c68a9-114">Direct Memory Access (DMA) DMA 保护设置来缓解 DMA 攻击，包括适用于 Thunderbolt 的内核 DMA 保护和在用户登录之前阻止 DMA。</span><span class="sxs-lookup"><span data-stu-id="c68a9-114">Direct Memory Access (DMA) protection settings to mitigate DMA attacks, including Kernel DMA Protection for Thunderbolt and blocking DMA until a user signs in.</span></span>  

3. <span data-ttu-id="c68a9-115">[创建自定义警报和响应操作](#create-customized-alerts-and-response-actions) ，以基于这些即插即用事件或其他任何具有自定义检测规则的 Microsoft Defender 终结点事件监视可移动 [设备的使用情况](/microsoft-365/security/defender-endpoint/custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-115">[Create customized alerts and response actions](#create-customized-alerts-and-response-actions) to monitor usage of removable devices based on these plug and play events or any other Microsoft Defender for Endpoint events with [custom detection rules](/microsoft-365/security/defender-endpoint/custom-detection-rules).</span></span>

4. <span data-ttu-id="c68a9-116">[根据每个](#respond-to-threats) 外设报告的属性，实时响应来自外设的威胁。</span><span class="sxs-lookup"><span data-stu-id="c68a9-116">[Respond to threats](#respond-to-threats) from peripherals in real-time based on properties reported by each peripheral.</span></span>

>[!Note]
><span data-ttu-id="c68a9-117">这些威胁减少措施有助于防止恶意软件进入你的环境。</span><span class="sxs-lookup"><span data-stu-id="c68a9-117">These threat reduction measures help prevent malware from coming into your environment.</span></span> <span data-ttu-id="c68a9-118">若要防止企业数据离开环境，还可以配置数据丢失防护措施。</span><span class="sxs-lookup"><span data-stu-id="c68a9-118">To protect enterprise data from leaving your environment, you can also configure data loss prevention measures.</span></span> <span data-ttu-id="c68a9-119">例如，在[Windows 10](/windows/security/information-protection/bitlocker/bitlocker-overview.md)设备上，你可以配置 BitLocker 和[Windows](/windows/security/information-protection/create-wip-policy-using-intune-azure.md)信息保护，这将加密公司数据，即使数据存储在个人设备上，也可以使用[存储/RemovableDiskDenyWriteAccess CSP](/windows/client-management/mdm/policy-csp-storage#storage-removablediskdenywriteaccess)拒绝对可移动磁盘的写访问。</span><span class="sxs-lookup"><span data-stu-id="c68a9-119">For example, on Windows 10 devices you can configure [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview.md) and [Windows Information Protection](/windows/security/information-protection/create-wip-policy-using-intune-azure.md), which will encrypt company data even if it is stored on a personal device, or use the [Storage/RemovableDiskDenyWriteAccess CSP](/windows/client-management/mdm/policy-csp-storage#storage-removablediskdenywriteaccess) to deny write access to removable disks.</span></span> <span data-ttu-id="c68a9-120">此外[，可以使用](/windows/security/threat-protection/windows-defender-atp/information-protection-in-windows-overview)Microsoft Defender for Endpoint 和 Azure (对 Windows 设备上的文件进行分类和保护) 包括已装载的 USB 设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-120">Additionally, you can [classify and protect files on Windows devices](/windows/security/threat-protection/windows-defender-atp/information-protection-in-windows-overview) (including their mounted USB devices) by using Microsoft Defender for Endpoint and Azure Information Protection.</span></span>

## <a name="discover-plug-and-play-connected-events"></a><span data-ttu-id="c68a9-121">发现即插即用连接事件</span><span class="sxs-lookup"><span data-stu-id="c68a9-121">Discover plug and play connected events</span></span>

<span data-ttu-id="c68a9-122">可以在 Microsoft Defender for Endpoint 高级搜寻中查看即插即用连接事件，以识别可疑的使用活动或执行内部调查。</span><span class="sxs-lookup"><span data-stu-id="c68a9-122">You can view plug and play connected events in Microsoft Defender for Endpoint advanced hunting to identify suspicious usage activity or perform internal investigations.</span></span>
<span data-ttu-id="c68a9-123">有关 Defender for Endpoint 高级搜寻查询的示例，请参阅适用于终结点的 Microsoft Defender 搜寻查询[GitHub存储库](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-123">For examples of Defender for Endpoint advanced hunting queries, see the [Microsoft Defender for Endpoint hunting queries GitHub repo](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span>

<span data-ttu-id="c68a9-124">示例Power BI模板可用于可用于高级搜寻查询的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="c68a9-124">Sample Power BI report templates are available for Microsoft Defender for Endpoint that you can use for Advanced hunting queries.</span></span> <span data-ttu-id="c68a9-125">借助这些示例模板（包括用于设备控件的模板）可以将高级搜寻功能集成到Power BI。</span><span class="sxs-lookup"><span data-stu-id="c68a9-125">With these sample templates, including one for device control, you can integrate the power of Advanced hunting into Power BI.</span></span> <span data-ttu-id="c68a9-126">有关详细信息[，GitHub PowerBI 模板的](https://github.com/microsoft/MDATP-PowerBI-Templates)存储库。</span><span class="sxs-lookup"><span data-stu-id="c68a9-126">See the [GitHub repository for PowerBI templates](https://github.com/microsoft/MDATP-PowerBI-Templates) for more information.</span></span> <span data-ttu-id="c68a9-127">请参阅[使用自定义Power BI，](/microsoft-365/security/defender-endpoint/api-power-bi)详细了解Power BI集成。</span><span class="sxs-lookup"><span data-stu-id="c68a9-127">See [Create custom reports using Power BI](/microsoft-365/security/defender-endpoint/api-power-bi) to learn more about Power BI integration.</span></span>

## <a name="allow-or-block-removable-devices"></a><span data-ttu-id="c68a9-128">允许或阻止可移动设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-128">Allow or block removable devices</span></span>
<span data-ttu-id="c68a9-129">下表介绍了 Microsoft Defender for Endpoint 根据具体配置允许或阻止可移动设备的方式。</span><span class="sxs-lookup"><span data-stu-id="c68a9-129">The following table describes the ways Microsoft Defender for Endpoint can allow or block removable devices based on granular configuration.</span></span>

| <span data-ttu-id="c68a9-130">控件</span><span class="sxs-lookup"><span data-stu-id="c68a9-130">Control</span></span>  | <span data-ttu-id="c68a9-131">说明</span><span class="sxs-lookup"><span data-stu-id="c68a9-131">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="c68a9-132">限制 USB 驱动器和其他外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-132">Restrict USB drives and other peripherals</span></span>](#restrict-usb-drives-and-other-peripherals) | <span data-ttu-id="c68a9-133">你可以允许/阻止用户仅安装已授权/未授权设备或设备类型列表中包含的 USB 驱动器和其他外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-133">You can allow/prevent users to install only the USB drives and other peripherals included on a list of authorized/unauthorized devices or device types.</span></span> |
| [<span data-ttu-id="c68a9-134">阻止安装和使用可移动存储</span><span class="sxs-lookup"><span data-stu-id="c68a9-134">Block installation and usage of removable storage</span></span>](#block-installation-and-usage-of-removable-storage) | <span data-ttu-id="c68a9-135">你无法安装或使用可移动存储。</span><span class="sxs-lookup"><span data-stu-id="c68a9-135">You can't install or use removable storage.</span></span> |
| [<span data-ttu-id="c68a9-136">允许安装和使用专门批准的外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-136">Allow installation and usage of specifically approved peripherals</span></span>](#allow-installation-and-usage-of-specifically-approved-peripherals)   | <span data-ttu-id="c68a9-137">只能安装和使用报告其固件中的特定属性的已批准外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-137">You can only install and use approved peripherals that report specific properties in their firmware.</span></span> |
| [<span data-ttu-id="c68a9-138">阻止安装专门禁止的外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-138">Prevent installation of specifically prohibited peripherals</span></span>](#prevent-installation-of-specifically-prohibited-peripherals) | <span data-ttu-id="c68a9-139">你无法安装或使用在固件中报告特定属性的禁止的外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-139">You can't install or use prohibited peripherals that report specific properties in their firmware.</span></span> |
| [<span data-ttu-id="c68a9-140">允许安装和使用具有匹配设备实例 ID 的专门批准的外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-140">Allow installation and usage of specifically approved peripherals with matching device instance IDs</span></span>](#allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids) | <span data-ttu-id="c68a9-141">只能安装和使用与这些设备实例任何一个匹配的已批准外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-141">You can only install and use approved peripherals that match any of these device instance IDs.</span></span> |
| [<span data-ttu-id="c68a9-142">使用匹配的设备实例 ID 阻止安装和使用专门禁止的外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-142">Prevent installation and usage of specifically prohibited peripherals with matching device instance IDs</span></span>](#prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids) | <span data-ttu-id="c68a9-143">你无法安装或使用与这些设备实例 ID 匹配的任何禁止的外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-143">You can't install or use prohibited peripherals that match any of these device instance IDs.</span></span> |
| [<span data-ttu-id="c68a9-144">限制使用服务蓝牙</span><span class="sxs-lookup"><span data-stu-id="c68a9-144">Limit services that use Bluetooth</span></span>](#limit-services-that-use-bluetooth) | <span data-ttu-id="c68a9-145">您可以限制可以使用此蓝牙。</span><span class="sxs-lookup"><span data-stu-id="c68a9-145">You can limit the services that can use Bluetooth.</span></span> |
| [<span data-ttu-id="c68a9-146">使用 Microsoft Defender for Endpoint 基线设置</span><span class="sxs-lookup"><span data-stu-id="c68a9-146">Use Microsoft Defender for Endpoint baseline settings</span></span>](#use-microsoft-defender-for-endpoint-baseline-settings) | <span data-ttu-id="c68a9-147">可以使用 Defender for Endpoint 安全基线设置 ATP 的建议配置。</span><span class="sxs-lookup"><span data-stu-id="c68a9-147">You can set the recommended configuration for ATP by using the Defender for Endpoint security baseline.</span></span> |

### <a name="restrict-usb-drives-and-other-peripherals"></a><span data-ttu-id="c68a9-148">限制 USB 驱动器和其他外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-148">Restrict USB drives and other peripherals</span></span>

<span data-ttu-id="c68a9-149">为了防止恶意软件感染或数据丢失，组织可能会限制 USB 驱动器和其他外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-149">To prevent malware infections or data loss, an organization may restrict USB drives and other peripherals.</span></span> <span data-ttu-id="c68a9-150">下表介绍了 Microsoft Defender for Endpoint 可帮助阻止安装和使用 USB 驱动器和其他外围设备的方法。</span><span class="sxs-lookup"><span data-stu-id="c68a9-150">The following table describes the ways Microsoft Defender for Endpoint can help prevent installation and usage of USB drives and other peripherals.</span></span>

| <span data-ttu-id="c68a9-151">控件</span><span class="sxs-lookup"><span data-stu-id="c68a9-151">Control</span></span>  | <span data-ttu-id="c68a9-152">说明</span><span class="sxs-lookup"><span data-stu-id="c68a9-152">Description</span></span>
|----------|-------------|
| [<span data-ttu-id="c68a9-153">允许安装和使用 USB 驱动器和其他外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-153">Allow installation and usage of USB drives and other peripherals</span></span>](#allow-installation-and-usage-of-usb-drives-and-other-peripherals) | <span data-ttu-id="c68a9-154">允许用户仅安装已授权设备或设备类型列表中包含的 USB 驱动器和其他外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-154">Allow users to install only the USB drives and other peripherals included on a list of authorized devices or device types</span></span> |
| [<span data-ttu-id="c68a9-155">阻止安装和使用 USB 驱动器和其他外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-155">Prevent installation and usage of USB drives and other peripherals</span></span>](#prevent-installation-and-usage-of-usb-drives-and-other-peripherals) | <span data-ttu-id="c68a9-156">阻止用户安装未经授权的设备和设备类型列表中包含的 USB 驱动器和其他外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-156">Prevent users from installing USB drives and other peripherals included on a list of unauthorized devices and device types</span></span> |

<span data-ttu-id="c68a9-157">上述所有控件都可以通过 Intune 管理 [模板进行设置](/intune/administrative-templates-windows)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-157">All of the above controls can be set through the Intune [Administrative Templates](/intune/administrative-templates-windows).</span></span> <span data-ttu-id="c68a9-158">相关策略位于 Intune 管理员模板中：</span><span class="sxs-lookup"><span data-stu-id="c68a9-158">The relevant policies are located here in the Intune Administrator Templates:</span></span>

![管理模板列表的屏幕截图](images/admintemplates.png)

>[!Note]
><span data-ttu-id="c68a9-160">使用 Intune，你可以将设备配置策略应用于 Azure AD 用户和/或设备组。</span><span class="sxs-lookup"><span data-stu-id="c68a9-160">Using Intune, you can apply device configuration policies to Azure AD user and/or device groups.</span></span>
<span data-ttu-id="c68a9-161">还可通过设备安装 CSP 设置和设备安装 [GPO](/windows/client-management/mdm/policy-csp-deviceinstallation) [设置上述策略](/previous-versions/dotnet/articles/bb530324(v=msdn.10))。</span><span class="sxs-lookup"><span data-stu-id="c68a9-161">The above policies can also be set through the [Device Installation CSP settings](/windows/client-management/mdm/policy-csp-deviceinstallation) and the [Device Installation GPOs](/previous-versions/dotnet/articles/bb530324(v=msdn.10)).</span></span>

> [!Note]
> <span data-ttu-id="c68a9-162">在生产中应用这些设置之前，请始终先使用一组试点用户和设备测试和优化这些设置。</span><span class="sxs-lookup"><span data-stu-id="c68a9-162">Always test and refine these settings with a pilot group of users and devices first before applying them in production.</span></span>
<span data-ttu-id="c68a9-163">有关控制 USB 设备的信息，请参阅 [Microsoft Defender for Endpoint 博客](https://www.microsoft.com/security/blog/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-163">For more information about controlling USB devices, see the [Microsoft Defender for Endpoint blog](https://www.microsoft.com/security/blog/2018/12/19/windows-defender-atp-has-protections-for-usb-and-removable-devices/).</span></span>

#### <a name="allow-installation-and-usage-of-usb-drives-and-other-peripherals"></a><span data-ttu-id="c68a9-164">允许安装和使用 USB 驱动器和其他外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-164">Allow installation and usage of USB drives and other peripherals</span></span>

<span data-ttu-id="c68a9-165">允许安装和使用 USB 驱动器和其他外围设备的一个方法是首先允许一切。</span><span class="sxs-lookup"><span data-stu-id="c68a9-165">One way to approach allowing installation and usage of USB drives and other peripherals is to start by allowing everything.</span></span> <span data-ttu-id="c68a9-166">之后，你可以开始减少允许的 USB 驱动程序和其他外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-166">Afterwards, you can start reducing the allowable USB drivers and other peripherals.</span></span>

>[!Note]
><span data-ttu-id="c68a9-167">由于未经授权的 USB 外围设备的固件可能会欺骗其 USB 属性，因此我们建议仅允许专门批准的 USB 外围设备并限制可以访问它们的用户。</span><span class="sxs-lookup"><span data-stu-id="c68a9-167">Because an unauthorized USB peripheral can have firmware that spoofs its USB properties, we recommend only allowing specifically approved USB peripherals and limiting the users who can access them.</span></span>

1. <span data-ttu-id="c68a9-168">Enable **Prevent installation of devices not described by other policy settings** to all users.</span><span class="sxs-lookup"><span data-stu-id="c68a9-168">Enable **Prevent installation of devices not described by other policy settings** to all users.</span></span>
2. <span data-ttu-id="c68a9-169">启用 **允许使用匹配所有设备** 设置类的这些设备设置类的 [驱动程序安装设备](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-169">Enable **Allow installation of devices using drivers that match these device setup classes** for all [device setup classes](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span>

<span data-ttu-id="c68a9-170">若要对已安装的设备强制执行策略，请应用具有此设置的阻止策略。</span><span class="sxs-lookup"><span data-stu-id="c68a9-170">To enforce the policy for already installed devices, apply the prevent policies that have this setting.</span></span>

<span data-ttu-id="c68a9-171">配置允许设备安装策略时，还必须允许所有父属性。</span><span class="sxs-lookup"><span data-stu-id="c68a9-171">When configuring the allow device installation policy, you must allow all parent attributes as well.</span></span> <span data-ttu-id="c68a9-172">可以通过打开设备管理器来查看设备的父项，并按连接查看。</span><span class="sxs-lookup"><span data-stu-id="c68a9-172">You can view the parents of a device by opening Device Manager and view by connection.</span></span>

![按连接显示的设备](images/devicesbyconnection.png)

<span data-ttu-id="c68a9-174">在此例中，需要添加以下类：HID、Keyboard 和 {36fc9e60-c465-11cf-8056-444553540000}。</span><span class="sxs-lookup"><span data-stu-id="c68a9-174">In this example, the following classes needed to be added: HID, Keyboard, and {36fc9e60-c465-11cf-8056-444553540000}.</span></span> <span data-ttu-id="c68a9-175">有关详细信息 [，请参阅 Microsoft 提供的 USB](/windows-hardware/drivers/usbcon/supported-usb-classes) 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="c68a9-175">See [Microsoft-provided USB drivers](/windows-hardware/drivers/usbcon/supported-usb-classes) for more information.</span></span>

![设备主机控制器](images/devicehostcontroller.jpg)

<span data-ttu-id="c68a9-177">如果要限制某些设备，请删除要限制的外围设备的设备设置类。</span><span class="sxs-lookup"><span data-stu-id="c68a9-177">If you want to restrict to certain devices, remove the device setup class of the peripheral that you want to limit.</span></span> <span data-ttu-id="c68a9-178">然后添加要添加的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="c68a9-178">Then add the device ID that you want to add.</span></span> <span data-ttu-id="c68a9-179">设备 ID 基于设备的供应商 ID 和产品 ID 值。</span><span class="sxs-lookup"><span data-stu-id="c68a9-179">Device ID is based on the vendor ID and product ID values for a device.</span></span> <span data-ttu-id="c68a9-180">有关设备 ID 格式的信息，请参阅标准 [USB 标识符](/windows-hardware/drivers/install/standard-usb-identifiers)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-180">For information on device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers).</span></span> 

<span data-ttu-id="c68a9-181">若要查找设备 ID，请参阅查找[设备 ID。](#look-up-device-id)</span><span class="sxs-lookup"><span data-stu-id="c68a9-181">To find the device IDs, see [Look up device ID](#look-up-device-id).</span></span> 

<span data-ttu-id="c68a9-182">例如：</span><span class="sxs-lookup"><span data-stu-id="c68a9-182">For example:</span></span>

1. <span data-ttu-id="c68a9-183">从允许使用与这些设备设置匹配的驱动程序安装 **设备中删除类** USBDevice。</span><span class="sxs-lookup"><span data-stu-id="c68a9-183">Remove class USBDevice from the **Allow installation of devices using drivers that match these device setup**.</span></span>
2. <span data-ttu-id="c68a9-184">在"允许安装与这些设备 ID 匹配的任何设备"中添加 **要允许的设备 ID。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-184">Add the device ID to allow in the **Allow installation of device that match any of these device IDs**.</span></span> 


#### <a name="prevent-installation-and-usage-of-usb-drives-and-other-peripherals"></a><span data-ttu-id="c68a9-185">阻止安装和使用 USB 驱动器和其他外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-185">Prevent installation and usage of USB drives and other peripherals</span></span>

<span data-ttu-id="c68a9-186">如果你想要阻止安装设备类或某些设备，可以使用阻止设备安装策略：</span><span class="sxs-lookup"><span data-stu-id="c68a9-186">If you want to prevent the installation of a device class or certain devices, you can use the prevent device installation policies:</span></span>

1. <span data-ttu-id="c68a9-187">启用 **"阻止安装与这些设备的任何 ID** 匹配的设备"，并将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="c68a9-187">Enable **Prevent installation of devices that match any of these device IDs** and add these devices to the list.</span></span>
2. <span data-ttu-id="c68a9-188">启用 **使用与这些设备设置类匹配的驱动程序阻止安装设备**。</span><span class="sxs-lookup"><span data-stu-id="c68a9-188">Enable **Prevent installation of devices using drivers that match these device setup classes**.</span></span>

> [!Note]
> <span data-ttu-id="c68a9-189">阻止设备安装策略优先于允许设备安装策略。</span><span class="sxs-lookup"><span data-stu-id="c68a9-189">The prevent device installation policies take precedence over the allow device installation policies.</span></span>

<span data-ttu-id="c68a9-190">通过 **阻止安装与这些设备任何一个匹配的设备策略**，你可以指定阻止安装Windows设备列表。</span><span class="sxs-lookup"><span data-stu-id="c68a9-190">The **Prevent installation of devices that match any of these device IDs** policy allows you to specify a list of devices that Windows is prevented from installing.</span></span> 

<span data-ttu-id="c68a9-191">若要阻止安装与这些设备的任何 ID 匹配的设备：</span><span class="sxs-lookup"><span data-stu-id="c68a9-191">To prevent installation of devices that match any of these device IDs:</span></span> 

1. <span data-ttu-id="c68a9-192">[查找要](#look-up-device-id)阻止安装Windows的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="c68a9-192">[Look up device ID](#look-up-device-id) for devices that you want Windows to prevent from installing.</span></span>

   ![查找供应商或产品 ID](images/lookup-vendor-product-id.png)

2. <span data-ttu-id="c68a9-194">启用 **"阻止安装与这些设备的任何 ID** 匹配的设备"，并添加供应商或产品 ID 到列表中。</span><span class="sxs-lookup"><span data-stu-id="c68a9-194">Enable **Prevent installation of devices that match any of these device IDs** and add the vendor or product IDs to the list.</span></span>

    ![添加供应商 ID 以阻止列表](images/add-vendor-id-to-prevent-list.png)

#### <a name="look-up-device-id"></a><span data-ttu-id="c68a9-196">查找设备 ID</span><span class="sxs-lookup"><span data-stu-id="c68a9-196">Look up device ID</span></span>

<span data-ttu-id="c68a9-197">可以使用设备管理器查找设备 ID。</span><span class="sxs-lookup"><span data-stu-id="c68a9-197">You can use Device Manager to look up a device ID.</span></span>

1. <span data-ttu-id="c68a9-198">打开设备管理器。</span><span class="sxs-lookup"><span data-stu-id="c68a9-198">Open Device Manager.</span></span>
2. <span data-ttu-id="c68a9-199">单击 **"查看**"，**然后按连接选择"设备"。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-199">Click **View** and select **Devices by connection**.</span></span>
3. <span data-ttu-id="c68a9-200">从树中，右键单击设备并选择"属性 **"。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-200">From the tree, right-click the device and select **Properties**.</span></span>
4. <span data-ttu-id="c68a9-201">在所选设备的对话框中，单击"详细信息 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c68a9-201">In the dialog box for the selected device, click the **Details** tab.</span></span>
5. <span data-ttu-id="c68a9-202">单击"**属性**"下拉列表，然后选择"**硬件 ID"。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-202">Click the **Property** drop-down list and select **Hardware Ids**.</span></span>
6. <span data-ttu-id="c68a9-203">右键单击顶部 ID 值， **然后选择复制**。</span><span class="sxs-lookup"><span data-stu-id="c68a9-203">Right-click the top ID value and select **Copy**.</span></span>

<span data-ttu-id="c68a9-204">有关设备 ID 格式的信息，请参阅标准 [USB 标识符](/windows-hardware/drivers/install/standard-usb-identifiers)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-204">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers).</span></span>

<span data-ttu-id="c68a9-205">有关供应商 ID 的信息，请参阅 [USB 成员](https://www.usb.org/members)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-205">For information on vendor IDs, see [USB members](https://www.usb.org/members).</span></span>

<span data-ttu-id="c68a9-206">下面是使用 PowerShell 查找设备供应商 ID 或产品 ID (，这是设备 ID) 的一部分：</span><span class="sxs-lookup"><span data-stu-id="c68a9-206">The following is an example for looking up a device vendor ID or product ID (which is part of the device ID) using PowerShell:</span></span> 

```powershell
Get-WMIObject -Class Win32_DiskDrive |
Select-Object -Property * 
```

<span data-ttu-id="c68a9-207">使用 **与这些设备设置** 类匹配的驱动程序阻止安装设备策略允许你指定阻止Windows安装类。</span><span class="sxs-lookup"><span data-stu-id="c68a9-207">The **Prevent installation of devices using drivers that match these device setup classes** policy allows you to specify device setup classes that Windows is prevented from installing.</span></span> 

<span data-ttu-id="c68a9-208">若要阻止安装特定设备类：</span><span class="sxs-lookup"><span data-stu-id="c68a9-208">To prevent installation of particular classes of devices:</span></span> 

1. <span data-ttu-id="c68a9-209">从供应商可用的系统定义的设备设置类中查找 [设备设置类的](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors)GUID。</span><span class="sxs-lookup"><span data-stu-id="c68a9-209">Find the GUID of the device setup class from [System-Defined Device Setup Classes Available to Vendors](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span>

2. <span data-ttu-id="c68a9-210">启用 **"阻止使用与这些设备** 设置类匹配的驱动程序安装设备"，然后向列表中添加类 GUID。</span><span class="sxs-lookup"><span data-stu-id="c68a9-210">Enable **Prevent installation of devices using drivers that match these device setup classes** and add the class GUID to the list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c68a9-211">![添加设备设置类以阻止列表](images/Add-device-setup-class-to-prevent-list.png)</span><span class="sxs-lookup"><span data-stu-id="c68a9-211">![Add device setup class to prevent list](images/Add-device-setup-class-to-prevent-list.png)</span></span>

### <a name="block-installation-and-usage-of-removable-storage"></a><span data-ttu-id="c68a9-212">阻止安装和使用可移动存储</span><span class="sxs-lookup"><span data-stu-id="c68a9-212">Block installation and usage of removable storage</span></span>

1. <span data-ttu-id="c68a9-213">登录到管理[Microsoft Endpoint Manager中心](https://endpoint.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-213">Sign in to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/).</span></span>

2. <span data-ttu-id="c68a9-214">单击 **"设备**  >  **配置文件**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-214">Click **Devices** > **Configuration Profiles** > **Create profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c68a9-215">![创建设备配置文件](images/create-device-configuration-profile.png)</span><span class="sxs-lookup"><span data-stu-id="c68a9-215">![Create device configuration profile](images/create-device-configuration-profile.png)</span></span>

3. <span data-ttu-id="c68a9-216">使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="c68a9-216">Use the following settings:</span></span>

   - <span data-ttu-id="c68a9-217">名称：键入配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="c68a9-217">Name: Type a name for the profile</span></span>
   - <span data-ttu-id="c68a9-218">说明：键入说明</span><span class="sxs-lookup"><span data-stu-id="c68a9-218">Description: Type a description</span></span>
   - <span data-ttu-id="c68a9-219">平台：Windows 10及更高版本</span><span class="sxs-lookup"><span data-stu-id="c68a9-219">Platform: Windows 10 and later</span></span>
   - <span data-ttu-id="c68a9-220">配置文件类型：设备限制</span><span class="sxs-lookup"><span data-stu-id="c68a9-220">Profile type: Device restrictions</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c68a9-221">![创建配置文件](images/create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="c68a9-221">![Create profile](images/create-profile.png)</span></span>

4. <span data-ttu-id="c68a9-222">单击"**配置**  >  **常规"。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-222">Click **Configure** > **General**.</span></span>  

5. <span data-ttu-id="c68a9-223">对于 **"仅移动版** (可移动存储和 **USB) ，请选择"** 阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-223">For **Removable storage** and **USB connection (mobile only)**, choose **Block**.</span></span> <span data-ttu-id="c68a9-224">**可移动存储** 包括 USB 驱动器， (移动连接) USB 充电，但仅包括移动设备上的其他 USB 连接。 </span><span class="sxs-lookup"><span data-stu-id="c68a9-224">**Removable storage** includes USB drives, whereas **USB connection (mobile only)** excludes USB charging but includes other USB connections on mobile devices only.</span></span> 

   ![常规设置](images/general-settings.png)

6. <span data-ttu-id="c68a9-226">单击 **确定** 关闭 **常规** 设置 **和设备限制**。</span><span class="sxs-lookup"><span data-stu-id="c68a9-226">Click **OK** to close **General** settings and **Device restrictions**.</span></span>

7. <span data-ttu-id="c68a9-227">单击 **"创建** "保存配置文件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-227">Click **Create** to save the profile.</span></span>

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals"></a><span data-ttu-id="c68a9-228">允许安装和使用专门批准的外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-228">Allow installation and usage of specifically approved peripherals</span></span>

<span data-ttu-id="c68a9-229">允许安装的外围设备可通过其硬件标识 [进行指定](/windows-hardware/drivers/install/device-identification-strings)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-229">Peripherals that are allowed to be installed can be specified by their [hardware identity](/windows-hardware/drivers/install/device-identification-strings).</span></span> <span data-ttu-id="c68a9-230">有关常见标识符结构的列表，请参阅 [设备标识符格式](/windows-hardware/drivers/install/device-identifier-formats)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-230">For a list of common identifier structures, see [Device Identifier Formats](/windows-hardware/drivers/install/device-identifier-formats).</span></span> <span data-ttu-id="c68a9-231">在部署配置之前测试它，以确保它阻止并允许预期的设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-231">Test the configuration prior to rolling it out to ensure it blocks and allows the devices expected.</span></span> <span data-ttu-id="c68a9-232">理想情况下，测试硬件的各种实例。</span><span class="sxs-lookup"><span data-stu-id="c68a9-232">Ideally test various instances of the hardware.</span></span> <span data-ttu-id="c68a9-233">例如，测试多个 U 盘，而不是只测试一个 U 盘。</span><span class="sxs-lookup"><span data-stu-id="c68a9-233">For example, test multiple USB keys rather than only one.</span></span>

<span data-ttu-id="c68a9-234">有关允许安装特定设备 ID 的 SyncML 示例，请参阅[DeviceInstallation/AllowInstallationOfMatchingDeviceIDs CSP。](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceids)</span><span class="sxs-lookup"><span data-stu-id="c68a9-234">For a SyncML example that allows installation of specific device IDs, see [DeviceInstallation/AllowInstallationOfMatchingDeviceIDs CSP](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceids).</span></span> <span data-ttu-id="c68a9-235">若要允许特定设备类，请参阅[DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses CSP。](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses)</span><span class="sxs-lookup"><span data-stu-id="c68a9-235">To allow specific device classes, see [DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses CSP](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses).</span></span>
<span data-ttu-id="c68a9-236">允许安装特定设备还需要启用 [DeviceInstallation/PreventInstallationOfDevicesNotDescribedByOtherPolicySettings](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofdevicesnotdescribedbyotherpolicysettings)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-236">Allowing installation of specific devices requires also enabling [DeviceInstallation/PreventInstallationOfDevicesNotDescribedByOtherPolicySettings](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofdevicesnotdescribedbyotherpolicysettings).</span></span>

### <a name="prevent-installation-of-specifically-prohibited-peripherals"></a><span data-ttu-id="c68a9-237">阻止安装专门禁止的外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-237">Prevent installation of specifically prohibited peripherals</span></span>

<span data-ttu-id="c68a9-238">Microsoft Defender for Endpoint 使用以下任一选项阻止安装和使用禁止的外围设备：</span><span class="sxs-lookup"><span data-stu-id="c68a9-238">Microsoft Defender for Endpoint blocks installation and usage of prohibited peripherals by using either of these options:</span></span>

- <span data-ttu-id="c68a9-239">[管理模板](/intune/administrative-templates-windows) 可以阻止具有匹配硬件 ID 或安装类的任何设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-239">[Administrative Templates](/intune/administrative-templates-windows) can block any device with a matching hardware ID or setup class.</span></span>  
- <span data-ttu-id="c68a9-240">[Intune 中具有](/windows/client-management/mdm/policy-csp-deviceinstallation) 自定义配置文件的设备安装 CSP 设置。</span><span class="sxs-lookup"><span data-stu-id="c68a9-240">[Device Installation CSP settings](/windows/client-management/mdm/policy-csp-deviceinstallation) with a custom profile in Intune.</span></span> <span data-ttu-id="c68a9-241">你可以[阻止安装特定设备 ID 或](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids)[阻止特定设备类](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdevicesetupclasses)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-241">You can [prevent installation of specific device IDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) or [prevent specific device classes](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdevicesetupclasses).</span></span>

### <a name="allow-installation-and-usage-of-specifically-approved-peripherals-with-matching-device-instance-ids"></a><span data-ttu-id="c68a9-242">允许安装和使用具有匹配设备实例 ID 的专门批准的外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-242">Allow installation and usage of specifically approved peripherals with matching device instance IDs</span></span>

<span data-ttu-id="c68a9-243">允许安装的外围设备可通过其设备实例 [ID 指定](/windows-hardware/drivers/install/device-instance-ids)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-243">Peripherals that are allowed to be installed can be specified by their [device instance IDs](/windows-hardware/drivers/install/device-instance-ids).</span></span> <span data-ttu-id="c68a9-244">在推出配置之前测试该配置，以确保它支持预期的设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-244">Test the configuration prior to rolling it out to ensure it allows the devices expected.</span></span> <span data-ttu-id="c68a9-245">理想情况下，测试硬件的各种实例。</span><span class="sxs-lookup"><span data-stu-id="c68a9-245">Ideally test various instances of the hardware.</span></span> <span data-ttu-id="c68a9-246">例如，测试多个 U 盘，而不是只测试一个 U 盘。</span><span class="sxs-lookup"><span data-stu-id="c68a9-246">For example, test multiple USB keys rather than only one.</span></span>

<span data-ttu-id="c68a9-247">通过 [配置 DeviceInstallation/AllowInstallationOfMatchingDeviceInstanceIDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceinstanceids) 策略设置，可以允许安装和使用具有匹配设备实例 ID 的已批准外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-247">You can allow installation and usage of approved peripherals with matching device instance IDs by configuring [DeviceInstallation/AllowInstallationOfMatchingDeviceInstanceIDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdeviceinstanceids) policy setting.</span></span>

### <a name="prevent-installation-and-usage-of-specifically-prohibited-peripherals-with-matching-device-instance-ids"></a><span data-ttu-id="c68a9-248">使用匹配的设备实例 ID 阻止安装和使用专门禁止的外围设备</span><span class="sxs-lookup"><span data-stu-id="c68a9-248">Prevent installation and usage of specifically prohibited peripherals with matching device instance IDs</span></span>

<span data-ttu-id="c68a9-249">禁止安装的外围设备可通过其设备实例 [ID 指定](/windows-hardware/drivers/install/device-instance-ids)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-249">Peripherals that are prohibited to be installed can be specified by their [device instance IDs](/windows-hardware/drivers/install/device-instance-ids).</span></span> <span data-ttu-id="c68a9-250">在推出配置之前测试该配置，以确保它支持预期的设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-250">Test the configuration prior to rolling it out to ensure it allows the devices expected.</span></span> <span data-ttu-id="c68a9-251">理想情况下，测试硬件的各种实例。</span><span class="sxs-lookup"><span data-stu-id="c68a9-251">Ideally test various instances of the hardware.</span></span> <span data-ttu-id="c68a9-252">例如，测试多个 U 盘，而不是只测试一个 U 盘。</span><span class="sxs-lookup"><span data-stu-id="c68a9-252">For example, test multiple USB keys rather than only one.</span></span>

<span data-ttu-id="c68a9-253">通过配置 [DeviceInstallation/PreventInstallationOfMatchingDeviceInstanceIDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceinstanceids) 策略设置，可以阻止使用匹配的设备实例 ID 安装禁止的外围设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-253">You can prevent installation of the prohibited peripherals with matching device instance IDs by configuring [DeviceInstallation/PreventInstallationOfMatchingDeviceInstanceIDs](/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceinstanceids) policy setting.</span></span>

### <a name="limit-services-that-use-bluetooth"></a><span data-ttu-id="c68a9-254">限制使用服务蓝牙</span><span class="sxs-lookup"><span data-stu-id="c68a9-254">Limit services that use Bluetooth</span></span>

<span data-ttu-id="c68a9-255">使用 Intune，你可以限制可通过"蓝牙服务"使用蓝牙[服务](/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-255">Using Intune, you can limit the services that can use Bluetooth through the ["Bluetooth allowed services"](/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide).</span></span> <span data-ttu-id="c68a9-256">默认状态"蓝牙允许的服务"设置意味着允许一切。</span><span class="sxs-lookup"><span data-stu-id="c68a9-256">The default state of "Bluetooth allowed services" settings means everything is allowed.</span></span>  <span data-ttu-id="c68a9-257">一旦添加服务，即成为允许列表。</span><span class="sxs-lookup"><span data-stu-id="c68a9-257">As soon as a service is added, that becomes the allowed list.</span></span> <span data-ttu-id="c68a9-258">如果客户添加了 Keyboards 和鼠标值，但未添加文件传输 GUID，应阻止文件传输。</span><span class="sxs-lookup"><span data-stu-id="c68a9-258">If the customer adds the Keyboards and Mice values, and doesn’t add the file transfer GUIDs, file transfer should be blocked.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c68a9-259">!["设置蓝牙屏幕截图](images/bluetooth.png)</span><span class="sxs-lookup"><span data-stu-id="c68a9-259">![screenshot of Bluetooth settings page](images/bluetooth.png)</span></span>

### <a name="use-microsoft-defender-for-endpoint-baseline-settings"></a><span data-ttu-id="c68a9-260">使用 Microsoft Defender for Endpoint 基线设置</span><span class="sxs-lookup"><span data-stu-id="c68a9-260">Use Microsoft Defender for Endpoint baseline settings</span></span>

<span data-ttu-id="c68a9-261">Microsoft Defender for Endpoint 基线设置表示威胁防护的建议配置。</span><span class="sxs-lookup"><span data-stu-id="c68a9-261">The Microsoft Defender for Endpoint baseline settings represent the recommended configuration for threat protection.</span></span> <span data-ttu-id="c68a9-262">基线的配置设置位于配置设置的编辑配置文件页中。</span><span class="sxs-lookup"><span data-stu-id="c68a9-262">Configuration settings for baseline are located in the edit profile page of the configuration settings.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c68a9-263">![MEM 中的基线](images/baselines.png)</span><span class="sxs-lookup"><span data-stu-id="c68a9-263">![Baselines in MEM](images/baselines.png)</span></span>

## <a name="prevent-threats-from-removable-storage"></a><span data-ttu-id="c68a9-264">防止来自可移动存储的威胁</span><span class="sxs-lookup"><span data-stu-id="c68a9-264">Prevent threats from removable storage</span></span>
  
<span data-ttu-id="c68a9-265">可移动存储设备可能会给组织带来额外的安全风险。</span><span class="sxs-lookup"><span data-stu-id="c68a9-265">Removable storage devices can introduce additional security risk to your organization.</span></span> <span data-ttu-id="c68a9-266">Microsoft Defender for Endpoint 可帮助识别和阻止可移动存储设备上的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-266">Microsoft Defender for Endpoint can help identify and block malicious files on removable storage devices.</span></span>

<span data-ttu-id="c68a9-267">Microsoft Defender for Endpoint 还可以阻止在设备上使用 USB 外围设备，以帮助防止外部威胁。</span><span class="sxs-lookup"><span data-stu-id="c68a9-267">Microsoft Defender for Endpoint can also prevent USB peripherals from being used on devices to help prevent external threats.</span></span> <span data-ttu-id="c68a9-268">它通过使用 USB 外围设备报告的属性来确定是否可以在设备上安装和使用它们来这样做。</span><span class="sxs-lookup"><span data-stu-id="c68a9-268">It does this by using the properties reported by USB peripherals to determine whether or not they can be installed and used on the device.</span></span>

<span data-ttu-id="c68a9-269">请注意，如果你使用设备安装策略阻止 USB 设备或任何其他设备类，连接的设备（如手机）仍可以收费。</span><span class="sxs-lookup"><span data-stu-id="c68a9-269">Note that if you block USB devices or any other device classes using the device installation policies, connected devices, such as phones, can still charge.</span></span>

>[!NOTE]
><span data-ttu-id="c68a9-270">在广泛分发到组织之前，请始终首先使用一组试点用户和设备测试和优化这些设置。</span><span class="sxs-lookup"><span data-stu-id="c68a9-270">Always test and refine these settings with a pilot group of users and devices first before widely distributing to your organization.</span></span> 

<span data-ttu-id="c68a9-271">下表介绍了 Microsoft Defender for Endpoint 可帮助防止来自可移动存储的威胁的方法。</span><span class="sxs-lookup"><span data-stu-id="c68a9-271">The following table describes the ways Microsoft Defender for Endpoint can help prevent threats from removable storage.</span></span>

<span data-ttu-id="c68a9-272">有关控制 USB 设备的信息，请参阅 [Microsoft Defender for Endpoint 博客](https://aka.ms/devicecontrolblog)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-272">For more information about controlling USB devices, see the [Microsoft Defender for Endpoint blog](https://aka.ms/devicecontrolblog).</span></span>

| <span data-ttu-id="c68a9-273">控件</span><span class="sxs-lookup"><span data-stu-id="c68a9-273">Control</span></span>  | <span data-ttu-id="c68a9-274">说明</span><span class="sxs-lookup"><span data-stu-id="c68a9-274">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="c68a9-275">启用Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="c68a9-275">Enable Microsoft Defender Antivirus Scanning</span></span>](#enable-microsoft-defender-antivirus-scanning) | <span data-ttu-id="c68a9-276">启用Microsoft Defender 防病毒扫描进行实时保护或计划扫描。</span><span class="sxs-lookup"><span data-stu-id="c68a9-276">Enable Microsoft Defender Antivirus scanning for real-time protection or scheduled scans.</span></span>|
| [<span data-ttu-id="c68a9-277">在 USB 外围设备上阻止不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="c68a9-277">Block untrusted and unsigned processes on USB peripherals</span></span>](#block-untrusted-and-unsigned-processes-on-usb-peripherals) | <span data-ttu-id="c68a9-278">阻止未签名或不受信任的 USB 文件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-278">Block USB files that are unsigned or untrusted.</span></span> |
| [<span data-ttu-id="c68a9-279">防止直接内存访问 (DMA) 攻击</span><span class="sxs-lookup"><span data-stu-id="c68a9-279">Protect against Direct Memory Access (DMA) attacks</span></span>](#protect-against-direct-memory-access-dma-attacks) | <span data-ttu-id="c68a9-280">配置设置以抵御 DMA 攻击。</span><span class="sxs-lookup"><span data-stu-id="c68a9-280">Configure settings to protect against DMA attacks.</span></span> |

>[!NOTE]
><span data-ttu-id="c68a9-281">由于未经授权的 USB 外围设备的固件可能会欺骗其 USB 属性，因此我们建议仅允许专门批准的 USB 外围设备并限制可以访问它们的用户。</span><span class="sxs-lookup"><span data-stu-id="c68a9-281">Because an unauthorized USB peripheral can have firmware that spoofs its USB properties, we recommend only allowing specifically approved USB peripherals and limiting the users who can access them.</span></span>

### <a name="enable-microsoft-defender-antivirus-scanning"></a><span data-ttu-id="c68a9-282">启用Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="c68a9-282">Enable Microsoft Defender Antivirus Scanning</span></span>

<span data-ttu-id="c68a9-283">使用安全机制保护Microsoft Defender 防病毒可移动[存储需要启用](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)实时保护或计划扫描，并配置可移动驱动器进行扫描。</span><span class="sxs-lookup"><span data-stu-id="c68a9-283">Protecting authorized removable storage with Microsoft Defender Antivirus requires [enabling real-time protection](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus) or scheduling scans and configuring removable drives for scans.</span></span>

- <span data-ttu-id="c68a9-284">如果启用了实时保护，则先扫描文件，然后再访问和执行这些文件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-284">If real-time protection is enabled, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="c68a9-285">扫描范围包括所有文件，包括已装载的可移动设备（如 USB 驱动器）上的文件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-285">The scanning scope includes all files, including those on mounted removable devices such as USB drives.</span></span> <span data-ttu-id="c68a9-286">可以选择运行[PowerShell](/samples/browse/?redirectedfrom=TechNet-Gallery)脚本，在安装 U 盘后执行自定义扫描，以便 Microsoft Defender 防病毒 在连接可移动设备后开始扫描可移动设备上的所有文件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-286">You can optionally [run a PowerShell script to perform a custom scan](/samples/browse/?redirectedfrom=TechNet-Gallery) of a USB drive after it is mounted, so that Microsoft Defender Antivirus starts scanning all files on a removable device once the removable device is attached.</span></span> <span data-ttu-id="c68a9-287">但是，我们建议启用实时保护以提高扫描性能，特别是对于大型存储设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-287">However, we recommend enabling real-time protection for improved scanning performance, especially for large storage devices.</span></span>

- <span data-ttu-id="c68a9-288">如果使用计划扫描，则需要禁用默认启用 (DisableRemovableDriveScanning 设置) 以在完全扫描期间扫描可移动设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-288">If scheduled scans are used, then you need to disable the DisableRemovableDriveScanning setting (enabled by default) to scan the removable device during a full scan.</span></span> <span data-ttu-id="c68a9-289">无论 DisableRemovableDriveScanning 设置如何，均可在快速或自定义扫描过程中扫描可移动设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-289">Removable devices are scanned during a quick or custom scan regardless of the DisableRemovableDriveScanning setting.</span></span>

>[!NOTE]
><span data-ttu-id="c68a9-290">我们建议为扫描启用实时监视。</span><span class="sxs-lookup"><span data-stu-id="c68a9-290">We recommend enabling real-time monitoring for scanning.</span></span> <span data-ttu-id="c68a9-291">在 Intune 中，你可以为设备限制配置Windows 10实时监视中的Microsoft Defender 防病毒  >    >    >  **实时监视**。</span><span class="sxs-lookup"><span data-stu-id="c68a9-291">In Intune, you can enable real-time monitoring for Windows 10 in **Device Restrictions** > **Configure** > **Microsoft Defender Antivirus** > **Real-time monitoring**.</span></span>

<!-- Need to build out point in the preceding note. 
-->

### <a name="block-untrusted-and-unsigned-processes-on-usb-peripherals"></a><span data-ttu-id="c68a9-292">在 USB 外围设备上阻止不受信任的和未签名的进程</span><span class="sxs-lookup"><span data-stu-id="c68a9-292">Block untrusted and unsigned processes on USB peripherals</span></span>

<span data-ttu-id="c68a9-293">最终用户可能会插入感染恶意软件的可移动设备。</span><span class="sxs-lookup"><span data-stu-id="c68a9-293">End-users might plug in removable devices that are infected with malware.</span></span>
<span data-ttu-id="c68a9-294">为了防止感染，公司可以阻止未签名或不受信任的 USB 文件。</span><span class="sxs-lookup"><span data-stu-id="c68a9-294">To prevent infections, a company can block USB files that are unsigned or untrusted.</span></span>
<span data-ttu-id="c68a9-295">或者，公司可以利用攻击面减少规则的审核功能[](/microsoft-365/security/defender-endpoint/attack-surface-reduction)来监视在 USB 外围设备上执行的不受信任的和未签名进程的活动。</span><span class="sxs-lookup"><span data-stu-id="c68a9-295">Alternatively, companies can leverage the audit feature of [attack surface reduction rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction) to monitor the activity of untrusted and unsigned processes that execute on a USB peripheral.</span></span>
<span data-ttu-id="c68a9-296">这可以通过将从 USB 运行的 **不受信任的** 和未签名的进程分别 **设置为"仅** 阻止"或" **仅审核**"来完成。</span><span class="sxs-lookup"><span data-stu-id="c68a9-296">This can be done by setting **Untrusted and unsigned processes that run from USB** to either **Block** or **Audit only**, respectively.</span></span>
<span data-ttu-id="c68a9-297">通过此规则，管理员可以阻止或审核未签名或不受信任的可执行文件从 USB 可移动驱动器（包括 SD 卡）运行。</span><span class="sxs-lookup"><span data-stu-id="c68a9-297">With this rule, admins can prevent or audit unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span>
<span data-ttu-id="c68a9-298">受影响的文件类型包括可执行文件 (（如 .exe、.dll 或 .scr) ）和脚本文件（如 PowerShell (.ps) 、VisualBasic (.vbs) 或 JavaScript (.js) 文件）。</span><span class="sxs-lookup"><span data-stu-id="c68a9-298">Affected file types include executable files (such as .exe, .dll, or .scr) and script files such as a PowerShell (.ps), VisualBasic (.vbs), or JavaScript (.js) files.</span></span>

<span data-ttu-id="c68a9-299">这些设置需要 [启用实时保护](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-299">These settings require [enabling real-time protection](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

1. <span data-ttu-id="c68a9-300">登录到[Microsoft Endpoint Manager。](https://endpoint.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="c68a9-300">Sign in to the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span>

2. <span data-ttu-id="c68a9-301">单击 **"设备**  >  **Windows**  >  **配置策略**  >  **""创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-301">Click **Devices** > **Windows** > **Configuration Policies** > **Create profile**.</span></span> 

    ![创建设备配置文件](images/create-device-configuration-profile.png)

3. <span data-ttu-id="c68a9-303">使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="c68a9-303">Use the following settings:</span></span>
   - <span data-ttu-id="c68a9-304">平台：Windows 10及更高版本</span><span class="sxs-lookup"><span data-stu-id="c68a9-304">Platform: Windows 10 and later</span></span> 
   - <span data-ttu-id="c68a9-305">配置文件类型：设备限制</span><span class="sxs-lookup"><span data-stu-id="c68a9-305">Profile type: Device restrictions</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c68a9-306">![创建终结点保护配置文件](images/create-endpoint-protection-profile.png)</span><span class="sxs-lookup"><span data-stu-id="c68a9-306">![Create endpoint protection profile](images/create-endpoint-protection-profile.png)</span></span>

4. <span data-ttu-id="c68a9-307">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="c68a9-307">Click **Create**.</span></span>  

5. <span data-ttu-id="c68a9-308">对于 **从 USB 运行的未** 签名和不受信任进程，选择"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="c68a9-308">For **Unsigned and untrusted processes that run from USB**, choose **Block**.</span></span>

   ![阻止不受信任的进程](images/block-untrusted-processes.png)

6. <span data-ttu-id="c68a9-310">单击 **"** 确定"关闭设置 **和设备限制**。</span><span class="sxs-lookup"><span data-stu-id="c68a9-310">Click **OK** to close settings and **Device restrictions**.</span></span>

### <a name="protect-against-direct-memory-access-dma-attacks"></a><span data-ttu-id="c68a9-311">防止直接内存访问 (DMA) 攻击</span><span class="sxs-lookup"><span data-stu-id="c68a9-311">Protect against Direct Memory Access (DMA) attacks</span></span>

<span data-ttu-id="c68a9-312">DMA 攻击可能会导致泄露驻留在电脑上的敏感信息，甚至导致恶意软件注入，攻击者可以绕过锁屏界面或远程控制电脑。</span><span class="sxs-lookup"><span data-stu-id="c68a9-312">DMA attacks can lead to disclosure of sensitive information residing on a PC, or even injection of malware that allows attackers to bypass the lock screen or control PCs remotely.</span></span> <span data-ttu-id="c68a9-313">以下设置有助于防止 DMA 攻击：</span><span class="sxs-lookup"><span data-stu-id="c68a9-313">The following settings help to prevent DMA attacks:</span></span>

1. <span data-ttu-id="c68a9-314">从 Windows 10版本 1803 开始，Microsoft 引入了[适用于 Thunderbolt 的内核 DMA](/windows/security/information-protection/kernel-dma-protection-for-thunderbolt.md)保护，以提供通过 Thunderbolt 端口抵御 DMA 攻击的本机保护。</span><span class="sxs-lookup"><span data-stu-id="c68a9-314">Beginning with Windows 10 version 1803, Microsoft introduced [Kernel DMA Protection for Thunderbolt](/windows/security/information-protection/kernel-dma-protection-for-thunderbolt.md) to provide native protection against DMA attacks via Thunderbolt ports.</span></span> <span data-ttu-id="c68a9-315">适用于 Thunderbolt 的内核 DMA 保护由系统制造商启用，用户无法打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="c68a9-315">Kernel DMA Protection for Thunderbolt is enabled by system manufacturers and cannot be turned on or off by users.</span></span>

   <span data-ttu-id="c68a9-316">从 Windows 10版本 1809 开始，可以通过配置 DMA Guard CSP 来调整内核[DMA 保护级别](/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-316">Beginning with Windows 10 version 1809, you can adjust the level of Kernel DMA Protection by configuring the [DMA Guard CSP](/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy).</span></span> <span data-ttu-id="c68a9-317">这是对不支持设备内存隔离的外围设备的额外 (也称为 DMA 重新映射) 。</span><span class="sxs-lookup"><span data-stu-id="c68a9-317">This is an additional control for peripherals that don't support device memory isolation (also known as DMA-remapping).</span></span> <span data-ttu-id="c68a9-318">内存隔离允许操作系统利用设备的 I/O 内存管理单元 (IOMMU) 来阻止外围设备内存沙盒 (不允许的 I/O 或内存) 。</span><span class="sxs-lookup"><span data-stu-id="c68a9-318">Memory isolation allows the OS to leverage the I/O Memory Management Unit (IOMMU) of a device to block unallowed I/O, or memory access, by the peripheral (memory sandboxing).</span></span> <span data-ttu-id="c68a9-319">换句话说，操作系统向外设分配特定内存范围。</span><span class="sxs-lookup"><span data-stu-id="c68a9-319">In other words, the OS assigns a certain memory range to the peripheral.</span></span> <span data-ttu-id="c68a9-320">如果外设尝试读取/写入指定范围之外的内存，操作系统将阻止它。</span><span class="sxs-lookup"><span data-stu-id="c68a9-320">If the peripheral attempts to read/write to memory outside of the assigned range, the OS blocks it.</span></span>

   <span data-ttu-id="c68a9-321">支持设备内存隔离的外围设备始终可以连接。</span><span class="sxs-lookup"><span data-stu-id="c68a9-321">Peripherals that support device memory isolation can always connect.</span></span> <span data-ttu-id="c68a9-322">只有在用户登录后才能阻止、允许或允许的外围设备 (默认) 。</span><span class="sxs-lookup"><span data-stu-id="c68a9-322">Peripherals that don't can be blocked, allowed, or allowed only after the user signs in (default).</span></span>

2. <span data-ttu-id="c68a9-323">在Windows 10内核 DMA 保护的系统上，你可以：</span><span class="sxs-lookup"><span data-stu-id="c68a9-323">On Windows 10 systems that do not support Kernel DMA Protection, you can:</span></span>

   - [<span data-ttu-id="c68a9-324">阻止 DMA，直到用户登录</span><span class="sxs-lookup"><span data-stu-id="c68a9-324">Block DMA until a user signs in</span></span>](/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)
   - [<span data-ttu-id="c68a9-325">通过 Thunderbolt 端口连接阻止所有 (包括 USB 设备) </span><span class="sxs-lookup"><span data-stu-id="c68a9-325">Block all connections via the Thunderbolt ports (including USB devices)</span></span>](https://support.microsoft.com/help/2516445/blocking-the-sbp-2-driver-and-thunderbolt-controllers-to-reduce-1394-d)

## <a name="create-customized-alerts-and-response-actions"></a><span data-ttu-id="c68a9-326">创建自定义警报和响应操作</span><span class="sxs-lookup"><span data-stu-id="c68a9-326">Create customized alerts and response actions</span></span>

<span data-ttu-id="c68a9-327">可以使用 WDATP 连接器和自定义检测规则创建自定义警报和响应操作：</span><span class="sxs-lookup"><span data-stu-id="c68a9-327">You can create custom alerts and response actions with the WDATP Connector and the custom detection rules:</span></span>

<span data-ttu-id="c68a9-328">**Wdatp 连接器响应操作：**</span><span class="sxs-lookup"><span data-stu-id="c68a9-328">**Wdatp Connector response Actions:**</span></span>

<span data-ttu-id="c68a9-329">**调查：** 启动调查、收集调查包并隔离计算机。</span><span class="sxs-lookup"><span data-stu-id="c68a9-329">**Investigate:** Initiate investigations, collect investigation package, and isolate a machine.</span></span>

<span data-ttu-id="c68a9-330">**USB** 设备上的威胁扫描。</span><span class="sxs-lookup"><span data-stu-id="c68a9-330">**Threat Scanning** on USB devices.</span></span>

<span data-ttu-id="c68a9-331">限制 **计算机上** 所有应用程序的执行，预定义集 MDATP 连接器是 200 多个预定义连接器之一，包括 Outlook、Teams、Slack 等。可以构建自定义连接器。</span><span class="sxs-lookup"><span data-stu-id="c68a9-331">**Restrict execution of all applications** on the machine except a predefined set MDATP connector is one of over 200 pre-defined connectors including Outlook, Teams, Slack, etc. Custom connectors can be built.</span></span>
- [<span data-ttu-id="c68a9-332">有关 WDATP 连接器响应操作的信息</span><span class="sxs-lookup"><span data-stu-id="c68a9-332">More information on WDATP Connector Response Actions</span></span>](/connectors/wdatp/)

<span data-ttu-id="c68a9-333">**自定义检测规则响应操作：** 可以同时应用计算机和文件级别操作。</span><span class="sxs-lookup"><span data-stu-id="c68a9-333">**Custom Detection Rules Response Action:** Both machine and file level actions can be applied.</span></span>
- [<span data-ttu-id="c68a9-334">有关自定义检测规则响应操作的信息</span><span class="sxs-lookup"><span data-stu-id="c68a9-334">More information on Custom Detection Rules Response Actions</span></span>](/microsoft-365/security/defender-endpoint/custom-detection-rules)

<span data-ttu-id="c68a9-335">有关与设备控制相关的高级搜寻事件和如何创建自定义警报的示例的信息，请参阅高级搜寻更新：USB 事件、计算机级操作和 [架构更改](https://techcommunity.microsoft.com/t5/Microsoft-Defender-ATP/Advanced-hunting-updates-USB-events-machine-level-actions-and/ba-p/824152)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-335">For information on device control related advance hunting events and examples on how to create custom alerts, see [Advanced hunting updates: USB events, machine-level actions, and schema changes](https://techcommunity.microsoft.com/t5/Microsoft-Defender-ATP/Advanced-hunting-updates-USB-events-machine-level-actions-and/ba-p/824152).</span></span>

## <a name="respond-to-threats"></a><span data-ttu-id="c68a9-336">响应威胁</span><span class="sxs-lookup"><span data-stu-id="c68a9-336">Respond to threats</span></span>

<span data-ttu-id="c68a9-337">可以使用 Microsoft Defender 终结点自定义检测规则创建自定义警报和 [自动响应操作](/microsoft-365/security/defender-endpoint/custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="c68a9-337">You can create custom alerts and automatic response actions with the [Microsoft Defender for Endpoint Custom Detection Rules](/microsoft-365/security/defender-endpoint/custom-detection-rules).</span></span> <span data-ttu-id="c68a9-338">自定义检测中的响应操作涵盖计算机和文件级别操作。</span><span class="sxs-lookup"><span data-stu-id="c68a9-338">Response actions within the custom detection cover both machine and file level actions.</span></span> <span data-ttu-id="c68a9-339">您还可以使用[PowerApps](https://powerapps.microsoft.com/)创建警报和自动响应操作[，Flow](https://flow.microsoft.com/) Microsoft Defender for [Endpoint 连接器。](/connectors/wdatp/)</span><span class="sxs-lookup"><span data-stu-id="c68a9-339">You can also create alerts and automatic response actions using [PowerApps](https://powerapps.microsoft.com/) and [Flow](https://flow.microsoft.com/) with the [Microsoft Defender for Endpoint connector](/connectors/wdatp/).</span></span> <span data-ttu-id="c68a9-340">连接器支持调查、威胁扫描和限制正在运行的应用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="c68a9-340">The connector supports actions for investigation, threat scanning, and restricting running applications.</span></span> <span data-ttu-id="c68a9-341">它是 200 多个预定义连接器之一，包括 Outlook、Teams、Slack 等。</span><span class="sxs-lookup"><span data-stu-id="c68a9-341">It is one of over 200 pre-defined connectors including Outlook, Teams, Slack, and more.</span></span> <span data-ttu-id="c68a9-342">还可以构建自定义连接器。</span><span class="sxs-lookup"><span data-stu-id="c68a9-342">Custom connectors can also be built.</span></span> <span data-ttu-id="c68a9-343">请参阅 [连接器](/connectors/) ，详细了解连接器。</span><span class="sxs-lookup"><span data-stu-id="c68a9-343">See [Connectors](/connectors/) to learn more about connectors.</span></span>
 
<span data-ttu-id="c68a9-344">例如，使用任一方法，你都可以在将 USB Microsoft Defender 防病毒装载到计算机上时自动运行该 U 盘。</span><span class="sxs-lookup"><span data-stu-id="c68a9-344">For example, using either approach, you can automatically have the Microsoft Defender Antivirus run when a USB device is mounted onto a machine.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c68a9-345">相关主题</span><span class="sxs-lookup"><span data-stu-id="c68a9-345">Related topics</span></span>

- [<span data-ttu-id="c68a9-346">配置实时保护Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="c68a9-346">Configure real-time protection for Microsoft Defender Antivirus</span></span>](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="c68a9-347">Defender/AllowFullScanRemovableDriveScanning</span><span class="sxs-lookup"><span data-stu-id="c68a9-347">Defender/AllowFullScanRemovableDriveScanning</span></span>](/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning)
- [<span data-ttu-id="c68a9-348">策略/DeviceInstallation CSP</span><span class="sxs-lookup"><span data-stu-id="c68a9-348">Policy/DeviceInstallation CSP</span></span>](/windows/client-management/mdm/policy-csp-deviceinstallation)
- [<span data-ttu-id="c68a9-349">对可移动设备执行自定义扫描</span><span class="sxs-lookup"><span data-stu-id="c68a9-349">Perform a custom scan of a removable device</span></span>](/samples/browse/?redirectedfrom=TechNet-Gallery)
- [<span data-ttu-id="c68a9-350">用于自定义报告的设备控制 PowerBI 模板</span><span class="sxs-lookup"><span data-stu-id="c68a9-350">Device Control PowerBI Template for custom reporting</span></span>](https://github.com/microsoft/MDATP-PowerBI-Templates)
- [<span data-ttu-id="c68a9-351">BitLocker</span><span class="sxs-lookup"><span data-stu-id="c68a9-351">BitLocker</span></span>](/windows/security/information-protection/bitlocker/bitlocker-overview.md) 
- [<span data-ttu-id="c68a9-352">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="c68a9-352">Windows Information Protection</span></span>](/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure.md)
