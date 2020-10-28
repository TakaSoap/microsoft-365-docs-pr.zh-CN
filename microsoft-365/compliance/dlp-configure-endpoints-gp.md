---
title: 通过组策略的板载 Windows 10 设备
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用组策略在 Windows 10 设备上部署配置包，以使其载入服务。
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769398"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="5fca0-103">使用组策略的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="5fca0-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="5fca0-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5fca0-104">**Applies to:**</span></span>

- [<span data-ttu-id="5fca0-105">Microsoft 365 Endpoint data 丢失防护 (DLP) </span><span class="sxs-lookup"><span data-stu-id="5fca0-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="5fca0-106">组策略</span><span class="sxs-lookup"><span data-stu-id="5fca0-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="5fca0-107">若要使用组策略 (GP) 部署程序包的更新，您必须在 Windows Server 2008 R2 或更高版本上。</span><span class="sxs-lookup"><span data-stu-id="5fca0-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="5fca0-108">对于 Windows Server 2019，您可能需要将 NT AUTHORITY\Well-Known-System-Account 替换为组策略首选项所创建的 XML 文件的 NT AUTHORITY\SYSTEM。</span><span class="sxs-lookup"><span data-stu-id="5fca0-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="5fca0-109">使用组策略的板载设备</span><span class="sxs-lookup"><span data-stu-id="5fca0-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="5fca0-110">打开您从 "服务载入" 向导下载 *DeviceComplianceOnboardingPackage.zip* )  (的 GP configuration 包 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="5fca0-110">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="5fca0-111">你也可以从[Microsoft 合规性中心](https://compliance.microsoft.com/compliancesettings/deviceonboarding)获取程序包</span><span class="sxs-lookup"><span data-stu-id="5fca0-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="5fca0-112">在导航窗格中，选择 " **设置**  >  **设备载入** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-112">In the navigation pane, select **Settings** > **Device Onboarding** .</span></span>

3. <span data-ttu-id="5fca0-113">在 " **部署方法** " 字段中，选择 " **组策略** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-113">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="5fca0-114">单击 " **下载包** " 并保存该 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="5fca0-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="5fca0-115">将 .zip 文件的内容提取到可由设备访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="5fca0-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="5fca0-116">您应该具有一个名为 *OptionalParamsPolicy* 的文件夹和文件 *DeviceComplianceLocalOnboardingScript* 。</span><span class="sxs-lookup"><span data-stu-id="5fca0-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="5fca0-117">打开 [组策略管理控制台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) ，右键单击要配置的组策略对象 (GPO) ，然后单击 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="5fca0-118">在 " **组策略管理编辑器** " 中，依次转到 " **计算机配置** "、" **首选项** " 和 **"控制面板设置"** 。</span><span class="sxs-lookup"><span data-stu-id="5fca0-118">In the **Group Policy Management Editor** , go to **Computer configuration** , then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="5fca0-119">右键单击 " **计划的任务** "，指向 " **新建** "，然后单击 " **即时任务 (至少是 Windows 7)** 。</span><span class="sxs-lookup"><span data-stu-id="5fca0-119">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate Task (At least Windows 7)** .</span></span>

9. <span data-ttu-id="5fca0-120">在打开的 **任务** 窗口中，转到 " **常规** " 选项卡。在 " **安全选项** " 下，依次单击 " **更改用户或组** 和类型系统 **"** ，然后单击 " **检查名称** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK** .</span></span> <span data-ttu-id="5fca0-121">NT AUTHORITY\SYSTEM 显示为作为任务运行方式的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5fca0-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="5fca0-122">选择 " **不管用户是否登录都要运行"** ，然后选中 " **使用最高特权运行** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="5fca0-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="5fca0-123">转到 " **操作** " 选项卡，然后单击 " **新建 ...** "。确保在 " **操作** " 字段中选择 " **启动程序** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="5fca0-124">输入共享 *WindowsDefenderATPOnboardingScript* 文件的文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="5fca0-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="5fca0-125">单击 **"确定"** ，然后关闭任何打开的 GPMC 窗口。</span><span class="sxs-lookup"><span data-stu-id="5fca0-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="5fca0-126">使用组策略的分离设备</span><span class="sxs-lookup"><span data-stu-id="5fca0-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="5fca0-127">出于安全考虑，用于分离设备的包将在下载后的30天后过期。</span><span class="sxs-lookup"><span data-stu-id="5fca0-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="5fca0-128">发送到设备的已过期的脱离程序包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="5fca0-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="5fca0-129">下载一个脱离程序包时，系统会通知你提供程序包到期日期，并且它也将包含在包名称中。</span><span class="sxs-lookup"><span data-stu-id="5fca0-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="5fca0-130">无法同时在同一设备上部署载入和脱离策略，否则会导致不可预测的冲突。</span><span class="sxs-lookup"><span data-stu-id="5fca0-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="5fca0-131">从 [Microsoft 合规性中心](https://compliance.microsoft.com/compliancesettings/deviceonboarding)获取脱离程序包。</span><span class="sxs-lookup"><span data-stu-id="5fca0-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="5fca0-132">在导航窗格中，选择 " **设置** "  >  **//Device "加入**  >  **脱离** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="5fca0-133">在 " **部署方法** " 字段中，选择 " **组策略** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-133">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="5fca0-134">单击 " **下载包** " 并保存该 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="5fca0-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="5fca0-135">将 .zip 文件的内容提取到可由设备访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="5fca0-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="5fca0-136">您应具有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 的文件。</span><span class="sxs-lookup"><span data-stu-id="5fca0-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6. <span data-ttu-id="5fca0-137">打开 [组策略管理控制台](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) ，右键单击要配置的组策略对象 (GPO) ，然后单击 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="5fca0-138">在 " **组策略管理编辑器** " 中，依次转到 " **计算机配置"、** " **首选项** " 和 **"控制面板设置"** 。</span><span class="sxs-lookup"><span data-stu-id="5fca0-138">In the **Group Policy Management Editor** , go to **Computer configuration,** then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="5fca0-139">右键单击 " **任务计划** "，指向 " **新建** "，然后单击 " **即时任务** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-139">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate task** .</span></span>

9. <span data-ttu-id="5fca0-140">在打开的 **任务** 窗口中，转到 " **常规** " 选项卡。在 " **安全选项** " 下的 " (BUILTIN\SYSTEM) 中选择" 本地系统 "用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5fca0-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options** .</span></span>

10. <span data-ttu-id="5fca0-141">选择 " **不管用户是否登录都要运行** "，然后选中 " **使用最高权限运行** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="5fca0-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="5fca0-142">转到 " **操作** " 选项卡，然后单击 " **新建 ...** "。确保在 " **操作** " 字段中选择 " **启动程序** "。</span><span class="sxs-lookup"><span data-stu-id="5fca0-142">Go to the **Actions** tab and click **New...** . Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="5fca0-143">输入共享  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd* 文件的文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="5fca0-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="5fca0-144">单击 **"确定"** ，然后关闭任何打开的 GPMC 窗口。</span><span class="sxs-lookup"><span data-stu-id="5fca0-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fca0-145">脱离将导致设备停止将传感器数据发送到门户，而不是来自设备的数据。</span><span class="sxs-lookup"><span data-stu-id="5fca0-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="5fca0-146">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="5fca0-146">Monitor device configuration</span></span>
<span data-ttu-id="5fca0-147">使用组策略时，没有选项可监视设备上的策略部署。</span><span class="sxs-lookup"><span data-stu-id="5fca0-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="5fca0-148">可以直接在门户或使用不同的部署工具进行监视。</span><span class="sxs-lookup"><span data-stu-id="5fca0-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="5fca0-149">使用门户监视设备</span><span class="sxs-lookup"><span data-stu-id="5fca0-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="5fca0-150">转到 [Microsoft 合规性中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="5fca0-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="5fca0-151">单击 " **设备** 列表"。</span><span class="sxs-lookup"><span data-stu-id="5fca0-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="5fca0-152">验证设备是否显示。</span><span class="sxs-lookup"><span data-stu-id="5fca0-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="5fca0-153">可能需要几天的时间才能在 " **设备" 列表** 中显示设备。</span><span class="sxs-lookup"><span data-stu-id="5fca0-153">It can take several days for devices to start showing on the **Devices list** .</span></span> <span data-ttu-id="5fca0-154">这包括将策略分发给设备所需的时间、用户登录前所需的时间以及终结点开始报告所需的时间。</span><span class="sxs-lookup"><span data-stu-id="5fca0-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5fca0-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="5fca0-155">Related topics</span></span>
- [<span data-ttu-id="5fca0-156">使用 Microsoft 终结点配置管理器的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="5fca0-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="5fca0-157">使用移动设备管理工具的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="5fca0-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="5fca0-158">使用本地脚本的板载 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="5fca0-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="5fca0-159"> (VDI) 设备的板载非永久性虚拟桌面基础结构</span><span class="sxs-lookup"><span data-stu-id="5fca0-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="5fca0-160">在新载入上运行检测测试 Microsoft Defender ATP 设备</span><span class="sxs-lookup"><span data-stu-id="5fca0-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="5fca0-161">解决 Microsoft Defender 高级威胁防护载入问题</span><span class="sxs-lookup"><span data-stu-id="5fca0-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
