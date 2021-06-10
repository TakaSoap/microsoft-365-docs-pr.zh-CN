---
title: 为 Microsoft Defender 更新创建自定义逐步推出过程
description: 了解如何使用受支持的工具为更新创建自定义逐步推出过程
keywords: 更新工具， gpo， intune， mdm， microsoft 终结点管理器， 策略， powershell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ec39a47a68f98f3fad63c10e633d54fd5a091db9
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861998"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a><span data-ttu-id="c4dba-104">为 Microsoft Defender 更新创建自定义逐步推出过程</span><span class="sxs-lookup"><span data-stu-id="c4dba-104">Create a custom gradual rollout process for Microsoft Defender updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c4dba-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c4dba-105">**Applies to:**</span></span>

- [<span data-ttu-id="c4dba-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c4dba-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="c4dba-107">此功能需要Microsoft Defender 防病毒 4.18.2105.4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c4dba-107">This functionality requires Microsoft Defender Antivirus version 4.18.2105.4 or newer.</span></span>

<span data-ttu-id="c4dba-108">若要为 Defender 更新创建自己的自定义逐步推出过程，可以使用组策略、Microsoft Endpoint Manager和 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c4dba-108">To create your own custom gradual rollout process for Defender updates, you can use Group Policy, Microsoft Endpoint Manager, and PowerShell.</span></span>

<span data-ttu-id="c4dba-109">下表列出了用于配置更新通道的可用组策略设置：</span><span class="sxs-lookup"><span data-stu-id="c4dba-109">The following table lists the available group policy settings for configuring update channels:</span></span>

| <span data-ttu-id="c4dba-110">设置标题</span><span class="sxs-lookup"><span data-stu-id="c4dba-110">Setting title</span></span>  | <span data-ttu-id="c4dba-111">说明</span><span class="sxs-lookup"><span data-stu-id="c4dba-111">Description</span></span>  | <span data-ttu-id="c4dba-112">Location</span><span class="sxs-lookup"><span data-stu-id="c4dba-112">Location</span></span>  |
|-|-|-|
| <span data-ttu-id="c4dba-113">选择逐步 Microsoft Defender 每月平台更新推出通道</span><span class="sxs-lookup"><span data-stu-id="c4dba-113">Select gradual Microsoft Defender monthly platform update rollout channel</span></span>  | <span data-ttu-id="c4dba-114">启用此策略可指定设备在每月逐步推出期间何时接收 Microsoft Defender 平台更新。</span><span class="sxs-lookup"><span data-stu-id="c4dba-114">Enable this policy to specify when devices receive Microsoft Defender platform updates during the monthly gradual rollout.</span></span> <span data-ttu-id="c4dba-115">Beta 渠道：设置为此频道的设备将是第一个接收新更新的设备。</span><span class="sxs-lookup"><span data-stu-id="c4dba-115">Beta Channel: Devices set to this channel will be the first to receive new updates.</span></span> <span data-ttu-id="c4dba-116">选择 Beta 渠道以参与识别问题并报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c4dba-116">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="c4dba-117">默认情况下，Windows预览体验计划中的设备订阅到此频道。</span><span class="sxs-lookup"><span data-stu-id="c4dba-117">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="c4dba-118">仅在手动 (测试) 和有限数量的设备中使用。</span><span class="sxs-lookup"><span data-stu-id="c4dba-118">For use in (manual) test environments only and a limited number of devices.</span></span>  <br><br>  <span data-ttu-id="c4dba-119">当前频道 (预览) ：设置为此频道的设备将在每月逐步发布周期内最早提供更新。</span><span class="sxs-lookup"><span data-stu-id="c4dba-119">Current Channel (Preview): Devices set to this channel will be offered updates earliest during the monthly gradual release cycle.</span></span> <span data-ttu-id="c4dba-120">建议用于预生产/验证环境。</span><span class="sxs-lookup"><span data-stu-id="c4dba-120">Suggested for pre-production/validation environments.</span></span>  <br><br>  <span data-ttu-id="c4dba-121">Current Channel (Staged) ： Devices will be offered updates after the monthly gradual release cycle.</span><span class="sxs-lookup"><span data-stu-id="c4dba-121">Current Channel (Staged): Devices will be offered updates after the monthly gradual release cycle.</span></span> <span data-ttu-id="c4dba-122">建议应用于生产总体中具有代表性的较小部分 (约 10%) 。</span><span class="sxs-lookup"><span data-stu-id="c4dba-122">Suggested to apply to a small, representative part of your production population (~10%).</span></span>  <br><br>  <span data-ttu-id="c4dba-123">Current Channel (Broad) ： Devices will be offered updates only after the gradual release cycle completes.</span><span class="sxs-lookup"><span data-stu-id="c4dba-123">Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="c4dba-124">建议应用于生产总体中的一组广泛的设备 (大约 10-100%) 。</span><span class="sxs-lookup"><span data-stu-id="c4dba-124">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  <br><br>   <span data-ttu-id="c4dba-125">如果禁用或不配置此策略，设备将在逐步发布周期中自动保持最新。</span><span class="sxs-lookup"><span data-stu-id="c4dba-125">If you disable or do not configure this policy, the device will stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="c4dba-126">适用于大多数设备。</span><span class="sxs-lookup"><span data-stu-id="c4dba-126">Suitable for most devices.</span></span>  | <span data-ttu-id="c4dba-127">WindowsComponents\Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="c4dba-127">Windows Components\Microsoft Defender Antivirus</span></span>  |
| <span data-ttu-id="c4dba-128">选择逐步 Microsoft Defender 每月引擎更新推出频道</span><span class="sxs-lookup"><span data-stu-id="c4dba-128">Select gradual Microsoft Defender monthly engine update rollout channel</span></span>  | <span data-ttu-id="c4dba-129">启用此策略可指定设备在每月逐步推出期间何时接收 Microsoft Defender 引擎更新。</span><span class="sxs-lookup"><span data-stu-id="c4dba-129">Enable this policy to specify when devices receive Microsoft Defender engine updates during the monthly gradual rollout.</span></span>  <br><br>  <span data-ttu-id="c4dba-130">Beta 渠道：设置为此频道的设备将是第一个接收新更新的设备。</span><span class="sxs-lookup"><span data-stu-id="c4dba-130">Beta Channel: Devices set to this channel will be the first to receive new updates.</span></span> <span data-ttu-id="c4dba-131">选择 Beta 渠道以参与识别问题并报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c4dba-131">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="c4dba-132">默认情况下，Windows预览体验计划中的设备订阅到此频道。</span><span class="sxs-lookup"><span data-stu-id="c4dba-132">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="c4dba-133">仅在手动 (测试) 和有限数量的设备中使用。</span><span class="sxs-lookup"><span data-stu-id="c4dba-133">For use in (manual) test environments only and a limited number of devices.</span></span>  <br><br>  <span data-ttu-id="c4dba-134">当前频道 (预览) ：设置为此频道的设备将在每月逐步发布周期内最早提供更新。</span><span class="sxs-lookup"><span data-stu-id="c4dba-134">Current Channel (Preview): Devices set to this channel will be offered updates earliest during the monthly gradual release cycle.</span></span> <span data-ttu-id="c4dba-135">建议用于预生产/验证环境。</span><span class="sxs-lookup"><span data-stu-id="c4dba-135">Suggested for pre-production/validation environments.</span></span>  <br><br>  <span data-ttu-id="c4dba-136">Current Channel (Staged) ： Devices will be offered updates after the monthly gradual release cycle.</span><span class="sxs-lookup"><span data-stu-id="c4dba-136">Current Channel (Staged): Devices will be offered updates after the monthly gradual release cycle.</span></span> <span data-ttu-id="c4dba-137">建议应用于生产总体中具有代表性的较小部分 (约 10%) 。</span><span class="sxs-lookup"><span data-stu-id="c4dba-137">Suggested to apply to a small, representative part of your production population (~10%).</span></span>  <br><br>  <span data-ttu-id="c4dba-138">Current Channel (Broad) ： Devices will be offered updates only after the gradual release cycle completes.</span><span class="sxs-lookup"><span data-stu-id="c4dba-138">Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="c4dba-139">建议应用于生产总体中的一组广泛的设备 (大约 10-100%) 。</span><span class="sxs-lookup"><span data-stu-id="c4dba-139">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  <br><br>  <span data-ttu-id="c4dba-140">如果禁用或不配置此策略，设备将在逐步发布周期中自动保持最新。</span><span class="sxs-lookup"><span data-stu-id="c4dba-140">If you disable or do not configure this policy, the device will stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="c4dba-141">适用于大多数设备。</span><span class="sxs-lookup"><span data-stu-id="c4dba-141">Suitable for most devices.</span></span>  | <span data-ttu-id="c4dba-142">WindowsComponents\Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="c4dba-142">Windows Components\Microsoft Defender Antivirus</span></span>  |
| <span data-ttu-id="c4dba-143">选择逐步 Microsoft Defender 每日定义更新推出通道</span><span class="sxs-lookup"><span data-stu-id="c4dba-143">Select gradual Microsoft Defender daily definition updates rollout channel</span></span>  | <span data-ttu-id="c4dba-144">启用此策略可指定设备在每日逐步推出期间何时接收 Microsoft Defender 定义更新。</span><span class="sxs-lookup"><span data-stu-id="c4dba-144">Enable this policy to specify when devices receive Microsoft Defender definition updates during the daily gradual rollout.</span></span> <br><br> <span data-ttu-id="c4dba-145">Current Channel (Staged) ： Devices will be offered updates after the release cycle.</span><span class="sxs-lookup"><span data-stu-id="c4dba-145">Current Channel (Staged): Devices will be offered updates after the release cycle.</span></span> <span data-ttu-id="c4dba-146">建议应用于生产总体中具有代表性的较小部分 (约 10%) 。</span><span class="sxs-lookup"><span data-stu-id="c4dba-146">Suggested to apply to a small, representative part of production population (~10%).</span></span> <br><br>   <span data-ttu-id="c4dba-147">Current Channel (Broad) ： Devices will be offered updates only after the gradual release cycle completes.</span><span class="sxs-lookup"><span data-stu-id="c4dba-147">Current Channel (Broad): Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="c4dba-148">建议应用于生产总体中的一组广泛的设备 (大约 10-100%) 。</span><span class="sxs-lookup"><span data-stu-id="c4dba-148">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span> <br><br>   <span data-ttu-id="c4dba-149">如果禁用或不配置此策略，设备将在每日发布周期内自动保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="c4dba-149">If you disable or do not configure this policy, the device will stay up to date automatically during the daily release cycle.</span></span> <span data-ttu-id="c4dba-150">适用于大多数设备。</span><span class="sxs-lookup"><span data-stu-id="c4dba-150">Suitable for most devices.</span></span>  | <span data-ttu-id="c4dba-151">WindowsComponents\Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="c4dba-151">Windows Components\Microsoft Defender Antivirus</span></span>  |
| <span data-ttu-id="c4dba-152">禁用 Microsoft Defender 更新的逐步推出</span><span class="sxs-lookup"><span data-stu-id="c4dba-152">Disable gradual rollout of Microsoft Defender updates</span></span>  | <span data-ttu-id="c4dba-153">启用此策略可禁用 Defender 更新的逐步推出。</span><span class="sxs-lookup"><span data-stu-id="c4dba-153">Enable this policy to disable gradual rollout of Defender updates.</span></span> <br><br> <span data-ttu-id="c4dba-154">Current Channel (Broad) ： Devices set to this channel will be offered updates last during the gradual release cycle.</span><span class="sxs-lookup"><span data-stu-id="c4dba-154">Current Channel (Broad): Devices set to this channel will be offered updates last during the gradual release cycle.</span></span> <span data-ttu-id="c4dba-155">最适合仅接收有限更新的数据中心计算机。</span><span class="sxs-lookup"><span data-stu-id="c4dba-155">Best for datacenter machines that only receive limited updates.</span></span> <br><br> <span data-ttu-id="c4dba-156">注意：此设置适用于每月和每日 Defender 更新，将覆盖之前为平台和引擎更新配置的任何频道选择。</span><span class="sxs-lookup"><span data-stu-id="c4dba-156">Note: This setting applies to both monthly as well as daily Defender updates and will override any previously configured channel selections for platform and engine updates.</span></span> <br><br> <span data-ttu-id="c4dba-157">如果禁用或不配置此策略，设备将保留在当前频道 (默认) 除非在平台和引擎更新的特定通道中另行指定。</span><span class="sxs-lookup"><span data-stu-id="c4dba-157">If you disable or do not configure this policy, the device will remain in Current Channel (Default) unless specified otherwise in specific channels for platform and engine updates.</span></span> <span data-ttu-id="c4dba-158">在逐步发布周期中自动保持最新。</span><span class="sxs-lookup"><span data-stu-id="c4dba-158">Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="c4dba-159">适用于大多数设备。</span><span class="sxs-lookup"><span data-stu-id="c4dba-159">Suitable for most devices.</span></span>  | <span data-ttu-id="c4dba-160">WindowsComponents\Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="c4dba-160">Windows Components\Microsoft Defender Antivirus</span></span>  |

## <a name="group-policy"></a><span data-ttu-id="c4dba-161">组策略</span><span class="sxs-lookup"><span data-stu-id="c4dba-161">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="c4dba-162">更新后的 Defender ADMX 模板将随 21H2 版本发布Windows 10。</span><span class="sxs-lookup"><span data-stu-id="c4dba-162">An updated Defender ADMX template will be published together with the 21H2 release of Windows 10.</span></span> <span data-ttu-id="c4dba-163">可在 下载非本地化版本 https://github.com/microsoft/defender-updatecontrols 。</span><span class="sxs-lookup"><span data-stu-id="c4dba-163">A non-localized version is available for download at https://github.com/microsoft/defender-updatecontrols.</span></span>

<span data-ttu-id="c4dba-164">可以使用组 [策略](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)   在终结点上配置Microsoft Defender 防病毒管理策略。</span><span class="sxs-lookup"><span data-stu-id="c4dba-164">You can use [Group Policy](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN) to configure and manage Microsoft Defender Antivirus on your endpoints.</span></span>

<span data-ttu-id="c4dba-165">通常，可以使用以下过程配置或更改Microsoft Defender 防病毒策略设置：</span><span class="sxs-lookup"><span data-stu-id="c4dba-165">In general, you can use the following procedure to configure or change Microsoft Defender Antivirus group policy settings:</span></span>

1. <span data-ttu-id="c4dba-166">在组策略管理计算机上，打开组策略  \*\*\*\* 管理控制台，右键单击要配置的组策略对象 **(** GPO) 然后单击  **编辑。**</span><span class="sxs-lookup"><span data-stu-id="c4dba-166">On your Group Policy management machine, open the  **Group Policy Management Console**, right-click the **Group Policy Object** (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="c4dba-167">使用组策略管理编辑器转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="c4dba-167">Using the Group Policy Management Editor go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c4dba-168">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="c4dba-168">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="c4dba-169">展开树以Windows **组件> Microsoft Defender 防病毒。**</span><span class="sxs-lookup"><span data-stu-id="c4dba-169">Expand the tree to **Windows components > Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="c4dba-170">展开本主题 (表中称为"位置"的部分)  \*\*\*\* 其中包含要配置的设置，双击该设置将其打开，然后   进行配置更改。</span><span class="sxs-lookup"><span data-stu-id="c4dba-170">Expand the section (referred to as **Location** in the table in this topic) that contains the setting you want to configure, double-click the setting to open it, and make configuration changes.</span></span>

6. <span data-ttu-id="c4dba-171">[像平常一样部署更新的 GPO。](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="c4dba-171">[Deploy the updated GPO as you normally do](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx).</span></span>

## <a name="intune"></a><span data-ttu-id="c4dba-172">Intune</span><span class="sxs-lookup"><span data-stu-id="c4dba-172">Intune</span></span>

<span data-ttu-id="c4dba-173">按照以下链接中的说明在 Intune 中创建自定义策略：</span><span class="sxs-lookup"><span data-stu-id="c4dba-173">Follow the instructions in below link to create a custom policy in Intune:</span></span>

[<span data-ttu-id="c4dba-174">在 Windows 10 中添加 Microsoft Intune 设备的自定义设置 - Azure \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="c4dba-174">Add custom settings for Windows 10 devices in Microsoft Intune - Azure \| Microsoft Docs</span></span>](/mem/intune/configuration/custom-settings-windows-10)

## <a name="powershell"></a><span data-ttu-id="c4dba-175">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4dba-175">PowerShell</span></span>

<span data-ttu-id="c4dba-176">使用 `Set-MpPreference` cmdlet 配置逐步更新的推出。</span><span class="sxs-lookup"><span data-stu-id="c4dba-176">Use the `Set-MpPreference` cmdlet to configure roll out of the gradual updates.</span></span>

<span data-ttu-id="c4dba-177">使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="c4dba-177">Use the following parameters:</span></span>

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

<span data-ttu-id="c4dba-178">示例：</span><span class="sxs-lookup"><span data-stu-id="c4dba-178">Example:</span></span>

<span data-ttu-id="c4dba-179">用于 `Set-MpPreference -PlatformUpdatesChannel Beta` 配置平台更新以从 Beta 渠道到达。</span><span class="sxs-lookup"><span data-stu-id="c4dba-179">Use `Set-MpPreference -PlatformUpdatesChannel Beta` to configure platform updates to arrive from the Beta Channel.</span></span>

<span data-ttu-id="c4dba-180">有关参数以及如何配置参数的信息，请参阅 [Set-MpPreference (Defender) |Microsoft Docs](/powershell/module/defender/set-mppreference?view=windowsserver2019-ps)。</span><span class="sxs-lookup"><span data-stu-id="c4dba-180">For more information on the parameters and how to configure them, see [Set-MpPreference (Defender) | Microsoft Docs](/powershell/module/defender/set-mppreference?view=windowsserver2019-ps).</span></span>
