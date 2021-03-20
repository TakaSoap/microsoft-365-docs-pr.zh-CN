---
title: 使用移动设备管理工具载入 Windows 10 设备
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
description: 使用移动设备管理工具在设备上部署配置包，以便它们可以载入到服务。
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917988"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="514a3-103">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="514a3-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="514a3-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="514a3-104">**Applies to:**</span></span>

- [<span data-ttu-id="514a3-105">Microsoft 365 终结点数据丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="514a3-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="514a3-106">可以使用移动设备管理 (MDM) 解决方案配置设备。</span><span class="sxs-lookup"><span data-stu-id="514a3-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="514a3-107">Microsoft 365 终结点数据丢失防护通过提供用于创建OMA-URIs管理设备的策略来支持 MDM。</span><span class="sxs-lookup"><span data-stu-id="514a3-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="514a3-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="514a3-108">Before you begin</span></span>
<span data-ttu-id="514a3-109">如果你使用的是 Microsoft Intune，则必须注册设备 MDM。</span><span class="sxs-lookup"><span data-stu-id="514a3-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="514a3-110">否则，设置将不会成功应用。</span><span class="sxs-lookup"><span data-stu-id="514a3-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="514a3-111">有关使用 Microsoft Intune 启用 MDM 的信息，请参阅 Microsoft [Intune (设备) 。 ](/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="514a3-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="514a3-112">使用 Microsoft Intune 载入设备</span><span class="sxs-lookup"><span data-stu-id="514a3-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="514a3-113">按照 [Intune 中的说明操作](/intune/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="514a3-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="514a3-114">载入 **设备的运行状况策略使用** 只读属性，并且无法修正。</span><span class="sxs-lookup"><span data-stu-id="514a3-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="514a3-115">使用移动设备管理工具离开并监视设备</span><span class="sxs-lookup"><span data-stu-id="514a3-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="514a3-116">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="514a3-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="514a3-117">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="514a3-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="514a3-118">下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="514a3-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="514a3-119">载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。</span><span class="sxs-lookup"><span data-stu-id="514a3-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="514a3-120">从 Microsoft 合规性中心获取 [载出包](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="514a3-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="514a3-121">在导航窗格中，选择"**设置**  >  **""设备载入**  >  **""载出"。**</span><span class="sxs-lookup"><span data-stu-id="514a3-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="514a3-122">在"**部署方法"** 字段中，选择 **"移动设备管理/Microsoft Intune"。**</span><span class="sxs-lookup"><span data-stu-id="514a3-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="514a3-123">单击 **"下载程序包**"，然后保存 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="514a3-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="514a3-124">将 .zip 文件的内容提取到将部署包的网络管理员可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="514a3-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="514a3-125">你应该有一个名为 *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding 的文件*。</span><span class="sxs-lookup"><span data-stu-id="514a3-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="514a3-126">使用 Microsoft Intune 自定义配置策略部署以下受支持的 OMA-URI 设置。</span><span class="sxs-lookup"><span data-stu-id="514a3-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="514a3-127">OMA-URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="514a3-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="514a3-128">日期类型：String</span><span class="sxs-lookup"><span data-stu-id="514a3-128">Date type: String</span></span>      
      <span data-ttu-id="514a3-129">值：[复制并粘贴 DeviceCompliance_valid_until_YYYY-MM-DD.offboarding 文件的内容中的值]</span><span class="sxs-lookup"><span data-stu-id="514a3-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="514a3-130">有关 Microsoft Intune 策略设置详细信息，请参阅 Microsoft Intune 中的 [Windows 10 策略设置](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="514a3-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="514a3-131">" **载出设备的运行状况状态"策略** 使用只读属性，并且无法修正。</span><span class="sxs-lookup"><span data-stu-id="514a3-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="514a3-132">"载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。</span><span class="sxs-lookup"><span data-stu-id="514a3-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="514a3-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="514a3-133">Related topics</span></span>
- [<span data-ttu-id="514a3-134">使用组策略载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="514a3-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="514a3-135">使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="514a3-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="514a3-136">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="514a3-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="514a3-137">载入非持久性虚拟桌面基础结构 (VDI) 设备。</span><span class="sxs-lookup"><span data-stu-id="514a3-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="514a3-138">Microsoft Defender 高级威胁防护载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="514a3-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)