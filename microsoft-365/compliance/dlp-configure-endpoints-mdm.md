---
title: 使用移动设备管理工具的板载 Windows 10 设备
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用移动设备管理工具在设备上部署配置包，以使其载入服务。
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769408"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="29b79-103">使用移动设备管理工具的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="29b79-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="29b79-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="29b79-104">**Applies to:**</span></span>

- [<span data-ttu-id="29b79-105">Microsoft 365 Endpoint data 丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="29b79-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="29b79-106">您可以使用 (MDM) 解决方案的移动设备管理来配置设备。</span><span class="sxs-lookup"><span data-stu-id="29b79-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="29b79-107">Microsoft 365 终结点数据丢失防护通过提供 OMA-URIs 来创建用于管理设备的策略，从而支持 MDMs。</span><span class="sxs-lookup"><span data-stu-id="29b79-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="29b79-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="29b79-108">Before you begin</span></span>
<span data-ttu-id="29b79-109">如果使用的是 Microsoft Intune，则必须注册设备 MDM。</span><span class="sxs-lookup"><span data-stu-id="29b79-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="29b79-110">否则，将无法成功应用设置。</span><span class="sxs-lookup"><span data-stu-id="29b79-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="29b79-111">有关使用 Microsoft Intune 启用 MDM 的详细信息，请参阅 [Device 注册 (Microsoft intune) ](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="29b79-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="29b79-112">使用 Microsoft Intune 的板载设备</span><span class="sxs-lookup"><span data-stu-id="29b79-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="29b79-113">按照 [Intune](https://docs.microsoft.com/intune/advanced-threat-protection)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="29b79-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="29b79-114">**载入设备策略的运行状况状态** 使用只读属性，不能修正。</span><span class="sxs-lookup"><span data-stu-id="29b79-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="29b79-115">使用移动设备管理工具分离和监控设备</span><span class="sxs-lookup"><span data-stu-id="29b79-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="29b79-116">出于安全考虑，用于分离设备的包将在下载后的30天后过期。</span><span class="sxs-lookup"><span data-stu-id="29b79-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="29b79-117">发送到设备的已过期的脱离程序包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="29b79-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="29b79-118">下载一个脱离程序包时，系统会通知你提供程序包到期日期，并且它也将包含在包名称中。</span><span class="sxs-lookup"><span data-stu-id="29b79-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="29b79-119">无法同时在同一设备上部署载入和脱离策略，否则会导致不可预测的冲突。</span><span class="sxs-lookup"><span data-stu-id="29b79-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="29b79-120">从 [Microsoft 合规性中心](https://compliance.microsoft.com/)获取脱离程序包。</span><span class="sxs-lookup"><span data-stu-id="29b79-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="29b79-121">在导航窗格中，选择 " **设置**  >  **设备加入**  >  **脱离** "。</span><span class="sxs-lookup"><span data-stu-id="29b79-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="29b79-122">在 " **部署方法** " 字段中，选择 " **移动设备管理/Microsoft Intune** "。</span><span class="sxs-lookup"><span data-stu-id="29b79-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune** .</span></span>
    
4. <span data-ttu-id="29b79-123">单击 " **下载包** "，并保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="29b79-123">Click **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="29b79-124">将 .zip 文件的内容提取到一个共享的只读位置，该位置可供将部署该包的网络管理员访问。</span><span class="sxs-lookup"><span data-stu-id="29b79-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="29b79-125">应具有一个名为 *DEVICECOMPLIANCE_VALID_UNTIL_YYYY MM 的* 文件。</span><span class="sxs-lookup"><span data-stu-id="29b79-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding* .</span></span>

6. <span data-ttu-id="29b79-126">使用 Microsoft Intune 自定义配置策略部署以下受支持的 OMA URI 设置。</span><span class="sxs-lookup"><span data-stu-id="29b79-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="29b79-127">OMA-URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="29b79-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="29b79-128">日期类型： String</span><span class="sxs-lookup"><span data-stu-id="29b79-128">Date type: String</span></span>      
      <span data-ttu-id="29b79-129">值： [从 DeviceCompliance_valid_until_YYYY-DD 文件的内容复制并粘贴值]</span><span class="sxs-lookup"><span data-stu-id="29b79-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="29b79-130">有关 Microsoft Intune 策略设置的详细信息，请参阅 [Microsoft intune 中的 Windows 10 策略设置](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="29b79-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="29b79-131">**Offboarded 设备策略的运行状况状态** 使用只读属性，不能修正。</span><span class="sxs-lookup"><span data-stu-id="29b79-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29b79-132">脱离将导致设备停止向门户发送传感器数据，但设备中的数据（包括对其已有的任何警报的引用）将保留最长6个月。</span><span class="sxs-lookup"><span data-stu-id="29b79-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="29b79-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="29b79-133">Related topics</span></span>
- [<span data-ttu-id="29b79-134">使用组策略的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="29b79-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="29b79-135">使用 Microsoft 终结点配置管理器的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="29b79-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="29b79-136">使用本地脚本的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="29b79-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="29b79-137"> (VDI) 设备的板载非永久性虚拟桌面基础结构</span><span class="sxs-lookup"><span data-stu-id="29b79-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="29b79-138">解决 Microsoft Defender 高级威胁防护载入问题</span><span class="sxs-lookup"><span data-stu-id="29b79-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
