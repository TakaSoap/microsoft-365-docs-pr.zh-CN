---
title: 通过组策略载入 Windows 10 设备
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
description: 使用组策略在 Windows 10部署配置包，以便它们可以载入服务。
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893283"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="efa80-103">使用Windows 10载入设备</span><span class="sxs-lookup"><span data-stu-id="efa80-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="efa80-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="efa80-104">**Applies to:**</span></span>

- [<span data-ttu-id="efa80-105">Microsoft 365DLP (终结点数据丢失) </span><span class="sxs-lookup"><span data-stu-id="efa80-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="efa80-106">组策略</span><span class="sxs-lookup"><span data-stu-id="efa80-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="efa80-107">若要使用组策略 (GP) 更新来部署程序包，必须在 Windows Server 2008 R2 或更高版本上。</span><span class="sxs-lookup"><span data-stu-id="efa80-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="efa80-108">对于 Windows Server 2019，您可能需要将 NT AUTHORITY\Well-Known-System-Account 替换为组策略首选项创建的 XML 文件的 NT AUTHORITY\SYSTEM。</span><span class="sxs-lookup"><span data-stu-id="efa80-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="efa80-109">使用组策略载入设备</span><span class="sxs-lookup"><span data-stu-id="efa80-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="efa80-110">打开 GP 配置包.zip文件 *(DeviceComplianceOnboardingPackage.zip)* 从服务载入向导下载的内容。</span><span class="sxs-lookup"><span data-stu-id="efa80-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="efa80-111">您还可以从 Microsoft 合规性中心 [获取程序包](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="efa80-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="efa80-112">在导航窗格中，选择 **"设置**  >  **载入"。**</span><span class="sxs-lookup"><span data-stu-id="efa80-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="efa80-113">在"**部署方法"** 字段中，选择"**组策略"。**</span><span class="sxs-lookup"><span data-stu-id="efa80-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="efa80-114">单击 **下载程序包** 并保存.zip文件。</span><span class="sxs-lookup"><span data-stu-id="efa80-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="efa80-115">将文件内容.zip到设备可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="efa80-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="efa80-116">你应该有一个称为 *OptionalParamsPolicy* 的文件夹和文件 *DeviceComplianceLocalOnboardingScript.cmd*。</span><span class="sxs-lookup"><span data-stu-id="efa80-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="efa80-117">打开组 [策略](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)管理控制台 (GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**</span><span class="sxs-lookup"><span data-stu-id="efa80-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="efa80-118">在组 **策略管理编辑器中**，转到"**计算机配置**"，然后转到"**首选项**"，然后转到"**控制面板设置"。**</span><span class="sxs-lookup"><span data-stu-id="efa80-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="efa80-119">右键单击 **计划任务**，指向 **新建**，然后单击即时任务 (**至少Windows 7)**。</span><span class="sxs-lookup"><span data-stu-id="efa80-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="efa80-120">在打开 **的任务** 窗口中，转到常规 **选项卡**。在 **"安全选项"** 下，单击 **"更改用户或组**"，然后键入"系统"，然后单击"**检查名称**"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="efa80-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="efa80-121">NT AUTHORITY\SYSTEM 显示为任务将运行的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="efa80-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="efa80-122">Select **Run whether user is logged on or not and** check the Run with highest **privileges** check box.</span><span class="sxs-lookup"><span data-stu-id="efa80-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="efa80-123">转到"操作 **"选项卡** ，然后单击" **新建..."。** 确保在 **"操作"** 字段中选择了"启动 **程序** "。</span><span class="sxs-lookup"><span data-stu-id="efa80-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="efa80-124">输入共享 *WindowsDefenderATPOnboardingScript.cmd* 文件的文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="efa80-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="efa80-125">单击 **"确定** "并关闭任何打开的 GPMC 窗口。</span><span class="sxs-lookup"><span data-stu-id="efa80-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="efa80-126">使用组策略的载出设备</span><span class="sxs-lookup"><span data-stu-id="efa80-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="efa80-127">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="efa80-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="efa80-128">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="efa80-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="efa80-129">下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="efa80-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="efa80-130">载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。</span><span class="sxs-lookup"><span data-stu-id="efa80-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="efa80-131">从 Microsoft 合规性中心获取 [载出包](https://compliance.microsoft.com/compliancesettings/deviceonboarding)。</span><span class="sxs-lookup"><span data-stu-id="efa80-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="efa80-132">在导航窗格中，**选择**  >  **"设置//设备载入**  >  **""载出"。**</span><span class="sxs-lookup"><span data-stu-id="efa80-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="efa80-133">在"**部署方法"** 字段中，选择"**组策略"。**</span><span class="sxs-lookup"><span data-stu-id="efa80-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="efa80-134">单击 **下载程序包** 并保存.zip文件。</span><span class="sxs-lookup"><span data-stu-id="efa80-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="efa80-135">将文件内容.zip到设备可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="efa80-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="efa80-136">你应该有一个名为 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="efa80-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="efa80-137">打开组 [策略](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)管理控制台 (GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**</span><span class="sxs-lookup"><span data-stu-id="efa80-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="efa80-138">在组 **策略管理编辑器中**，转到"**计算机配置"，然后** 转到"**首选项**"，然后转到"**控制面板设置"。**</span><span class="sxs-lookup"><span data-stu-id="efa80-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="efa80-139">右键单击 **"计划任务"，** 指向 **"新建**"，然后单击"**立即任务"。**</span><span class="sxs-lookup"><span data-stu-id="efa80-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="efa80-140">在打开 **的任务** 窗口中，转到常规 **选项卡** 。在"安全选项"下 (BUILTIN\SYSTEM) **本地系统用户帐户**。</span><span class="sxs-lookup"><span data-stu-id="efa80-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="efa80-141">Select **Run whether user is logged on or not and** check the Run with highest **privileges** check-box.</span><span class="sxs-lookup"><span data-stu-id="efa80-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="efa80-142">转到"操作 **"选项卡** ，然后单击"新建 **..."。** 确保在 **"操作"** 字段中选择了"启动 **程序** "。</span><span class="sxs-lookup"><span data-stu-id="efa80-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="efa80-143">输入共享文件的文件名和  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* 文件。</span><span class="sxs-lookup"><span data-stu-id="efa80-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="efa80-144">单击 **"确定** "并关闭任何打开的 GPMC 窗口。</span><span class="sxs-lookup"><span data-stu-id="efa80-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efa80-145">载出会导致设备停止向门户发送传感器数据，但从设备发送数据。</span><span class="sxs-lookup"><span data-stu-id="efa80-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="efa80-146">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="efa80-146">Monitor device configuration</span></span>
<span data-ttu-id="efa80-147">借助组策略，无法监视设备上策略的部署。</span><span class="sxs-lookup"><span data-stu-id="efa80-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="efa80-148">可以直接在门户上或使用不同的部署工具进行监视。</span><span class="sxs-lookup"><span data-stu-id="efa80-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="efa80-149">使用门户监视设备</span><span class="sxs-lookup"><span data-stu-id="efa80-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="efa80-150">转到 [Microsoft 合规中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="efa80-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="efa80-151">单击 **"设备列表** "。</span><span class="sxs-lookup"><span data-stu-id="efa80-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="efa80-152">验证设备是否显示。</span><span class="sxs-lookup"><span data-stu-id="efa80-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="efa80-153">设备可能需要几天时间才能开始在 **"设备"列表上显示**。</span><span class="sxs-lookup"><span data-stu-id="efa80-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="efa80-154">这包括将策略分发到设备所花的时间、用户登录之前所花的时间以及终结点开始报告所花的时间。</span><span class="sxs-lookup"><span data-stu-id="efa80-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="efa80-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="efa80-155">Related topics</span></span>
- [<span data-ttu-id="efa80-156">使用Windows 10载入Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="efa80-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="efa80-157">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="efa80-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="efa80-158">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="efa80-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="efa80-159">载入非永久虚拟桌面基础结构 （VDI） 设备</span><span class="sxs-lookup"><span data-stu-id="efa80-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="efa80-160">对新载入的适用于终结点的 Microsoft Defender 设备运行检测测试</span><span class="sxs-lookup"><span data-stu-id="efa80-160">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="efa80-161">载入Microsoft Defender 高级威胁防护疑难解答</span><span class="sxs-lookup"><span data-stu-id="efa80-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)