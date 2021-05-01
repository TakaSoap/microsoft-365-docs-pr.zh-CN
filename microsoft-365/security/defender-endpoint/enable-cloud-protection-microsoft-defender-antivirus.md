---
title: 在云中打开云保护Microsoft Defender 防病毒
description: 启用云保护，以从快速和高级保护功能中获益。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， 云， 首次看到时阻止
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 04/30/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 5fcbd30eca3a6d0965fe65e13d2623ff54d1ff5f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114244"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="e2abc-104">打开云传递保护</span><span class="sxs-lookup"><span data-stu-id="e2abc-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2abc-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e2abc-105">**Applies to:**</span></span>

- [<span data-ttu-id="e2abc-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e2abc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="e2abc-107">Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。</span><span class="sxs-lookup"><span data-stu-id="e2abc-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="e2abc-108">尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护;相反，它使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。</span><span class="sxs-lookup"><span data-stu-id="e2abc-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="e2abc-109">Microsoft Defender 防病毒使用多个检测和防护技术提供准确、实时和智能的保护。</span><span class="sxs-lookup"><span data-stu-id="e2abc-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="e2abc-110">了解 Microsoft Defender for Endpoint 下一代保护[的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="e2abc-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="e2abc-111">![Microsoft Defender AV 引擎列表](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="e2abc-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="e2abc-112">可以通过多种方式Microsoft Defender 防病毒或关闭云保护：</span><span class="sxs-lookup"><span data-stu-id="e2abc-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="e2abc-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e2abc-113">Microsoft Intune</span></span>
- <span data-ttu-id="e2abc-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e2abc-114">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="e2abc-115">组策略</span><span class="sxs-lookup"><span data-stu-id="e2abc-115">Group Policy</span></span>
- <span data-ttu-id="e2abc-116">PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e2abc-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="e2abc-117">此外，还可使用应用在个别客户端中Windows 安全中心它。</span><span class="sxs-lookup"><span data-stu-id="e2abc-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="e2abc-118">请参阅[使用 Microsoft 云保护](cloud-protection-microsoft-defender-antivirus.md)，了解云Microsoft Defender 防病毒保护的概述。</span><span class="sxs-lookup"><span data-stu-id="e2abc-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="e2abc-119">有关确保终结点可以连接到云保护服务的特定网络连接要求详细信息，请参阅配置和 [验证网络连接](configure-network-connections-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e2abc-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e2abc-120">在Windows 10中，本主题中介绍的基本报告选项和 **高级** 报告选项之间没有区别。 </span><span class="sxs-lookup"><span data-stu-id="e2abc-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="e2abc-121">这是旧区别，选择任一设置都将产生相同级别的云保护。</span><span class="sxs-lookup"><span data-stu-id="e2abc-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="e2abc-122">共享的信息的类型或数量没有差异。</span><span class="sxs-lookup"><span data-stu-id="e2abc-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="e2abc-123">有关我们收集的信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=521839)。</span><span class="sxs-lookup"><span data-stu-id="e2abc-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e2abc-124">使用 Intune 打开云提供的保护</span><span class="sxs-lookup"><span data-stu-id="e2abc-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="e2abc-125">转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="e2abc-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="e2abc-126">在"**主页"** 窗格中，选择"设备 **配置>配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="e2abc-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="e2abc-127">选择要 **配置的设备** 限制配置文件类型。</span><span class="sxs-lookup"><span data-stu-id="e2abc-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="e2abc-128">如果需要创建新的设备限制配置文件类型，请参阅配置设备[限制Microsoft Intune。](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="e2abc-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="e2abc-129">选择 **"属性**  >  **""配置设置："**  >  **编辑Microsoft Defender 防病毒"。**</span><span class="sxs-lookup"><span data-stu-id="e2abc-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="e2abc-130">在云 **保护开关上，\*\*\*\*选择启用**。</span><span class="sxs-lookup"><span data-stu-id="e2abc-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="e2abc-131">在"**在示例提交前提示用户"** 下拉列表中，选择"**自动发送所有数据"。**</span><span class="sxs-lookup"><span data-stu-id="e2abc-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="e2abc-132">有关 Intune 设备配置文件（包括如何创建和配置其设置）详细信息，请参阅什么是Microsoft Intune[配置文件？](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="e2abc-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e2abc-133">使用Microsoft Endpoint Manager启用云保护</span><span class="sxs-lookup"><span data-stu-id="e2abc-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="e2abc-134">转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="e2abc-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="e2abc-135">选择 **终结点安全**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="e2abc-135">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="e2abc-136">选择防病毒配置文件。</span><span class="sxs-lookup"><span data-stu-id="e2abc-136">Select an antivirus profile.</span></span> <span data-ttu-id="e2abc-137"> (如果还没有配置文件，或者要创建新的配置文件，请参阅配置 Microsoft Intune 中的[设备限制设置](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="e2abc-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="e2abc-138">选择 **"属性"。**</span><span class="sxs-lookup"><span data-stu-id="e2abc-138">Select **Properties**.</span></span> <span data-ttu-id="e2abc-139">然后，在"配置 **设置"旁边，选择**"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="e2abc-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="e2abc-140">展开 **"云** 保护"，然后在" **云提供的** 保护级别"列表中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e2abc-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="e2abc-141">**高**：应用强级别的检测。</span><span class="sxs-lookup"><span data-stu-id="e2abc-141">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="e2abc-142">**高加**： **使用高级别** ，并应用其他保护措施 (可能会影响客户端性能) 。</span><span class="sxs-lookup"><span data-stu-id="e2abc-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="e2abc-143">**零容** 限：阻止所有未知可执行文件。</span><span class="sxs-lookup"><span data-stu-id="e2abc-143">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="e2abc-144">选择 **"审阅 + 保存"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="e2abc-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="e2abc-145">有关配置反恶意软件Microsoft Endpoint Configuration Manager，请参阅如何创建和部署[反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。</span><span class="sxs-lookup"><span data-stu-id="e2abc-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e2abc-146">使用组策略启用云保护</span><span class="sxs-lookup"><span data-stu-id="e2abc-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="e2abc-147">在组策略管理设备上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="e2abc-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="e2abc-148">在组 **策略管理编辑器中**，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="e2abc-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e2abc-149">选择 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="e2abc-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="e2abc-150">展开树以 **Windows MAPS > Microsoft Defender 防病毒 >组件**</span><span class="sxs-lookup"><span data-stu-id="e2abc-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="e2abc-151">双击加入 **Microsoft MAPS**。</span><span class="sxs-lookup"><span data-stu-id="e2abc-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="e2abc-152">确保该选项已打开，并设置为 **基本 MAPS** 或 **高级 MAPS。**</span><span class="sxs-lookup"><span data-stu-id="e2abc-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="e2abc-153">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="e2abc-153">Select **OK**.</span></span>

6. <span data-ttu-id="e2abc-154">双击需要进 **一步分析时发送文件示例**。</span><span class="sxs-lookup"><span data-stu-id="e2abc-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="e2abc-155">确保第一个选项设置为 **"已启用** "，并且其他选项设置为：</span><span class="sxs-lookup"><span data-stu-id="e2abc-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="e2abc-156">**发送安全示例** (1) </span><span class="sxs-lookup"><span data-stu-id="e2abc-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="e2abc-157">**发送所有示例 (** 3) </span><span class="sxs-lookup"><span data-stu-id="e2abc-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="e2abc-158">" **发送安全 (** 1) "选项意味着将自动发送大多数示例。</span><span class="sxs-lookup"><span data-stu-id="e2abc-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="e2abc-159">可能包含个人信息的文件仍将提示并需要其他确认。</span><span class="sxs-lookup"><span data-stu-id="e2abc-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="e2abc-160">将选项设置为"始终 **提示** (0) 会降低设备的保护状态。</span><span class="sxs-lookup"><span data-stu-id="e2abc-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="e2abc-161">将其设置为"从不 **(** 2) "意味着 Microsoft Defender for [](configure-block-at-first-sight-microsoft-defender-antivirus.md) Endpoint 的"首次看到时阻止"功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="e2abc-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="e2abc-162">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="e2abc-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e2abc-163">使用 PowerShell cmdlet 启用云保护</span><span class="sxs-lookup"><span data-stu-id="e2abc-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="e2abc-164">以下 cmdlet 可以启用云保护：</span><span class="sxs-lookup"><span data-stu-id="e2abc-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="e2abc-165">若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="e2abc-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="e2abc-166">[策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender) 也具有有关 [-SubmitSamplesConsent 的专门详细信息](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)。</span><span class="sxs-lookup"><span data-stu-id="e2abc-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="e2abc-167">还可以将 **-SubmitSamplesConsent** 设置为 `SendSafeSamples` (、或) `NeverSend` 默认设置 `AlwaysPrompt` 。</span><span class="sxs-lookup"><span data-stu-id="e2abc-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="e2abc-168">`SendSafeSamples`该设置意味着将自动发送大多数示例。</span><span class="sxs-lookup"><span data-stu-id="e2abc-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="e2abc-169">可能包含个人信息的文件仍将提示并需要其他确认。</span><span class="sxs-lookup"><span data-stu-id="e2abc-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="e2abc-170">将 **-SubmitSamplesConsent** 设置为 `NeverSend` 或 `AlwaysPrompt` 会降低设备的保护级别。</span><span class="sxs-lookup"><span data-stu-id="e2abc-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="e2abc-171">此外，设置它意味着 Microsoft Defender for Endpoint 的"首次 `NeverSend` [看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 时阻止"功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="e2abc-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e2abc-172">使用 Windows Management Instruction (WMI) 启用云保护</span><span class="sxs-lookup"><span data-stu-id="e2abc-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="e2abc-173">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/defender/set-msft-mppreference)类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="e2abc-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="e2abc-174">有关允许的参数详细信息，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="e2abc-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="e2abc-175">使用云保护应用在个别客户端上Windows 安全中心保护</span><span class="sxs-lookup"><span data-stu-id="e2abc-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="e2abc-176">如果"**为** 报告 Microsoft MAPS 组策略配置本地设置覆盖"设置为"已禁用"，则 Windows 设置 中的基于云的保护设置将灰出且不可用。 </span><span class="sxs-lookup"><span data-stu-id="e2abc-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="e2abc-177">必须先通过组策略对象所做的更改部署到各个终结点，然后才能在 Windows 设置 中更新设置。</span><span class="sxs-lookup"><span data-stu-id="e2abc-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="e2abc-178">打开Windows 安全中心应用，选择任务栏中的防护图标，或搜索 Defender 的"开始"**菜单**。</span><span class="sxs-lookup"><span data-stu-id="e2abc-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="e2abc-179">选择病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后选择病毒防护威胁防护 **&标签：**</span><span class="sxs-lookup"><span data-stu-id="e2abc-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot of the Virus & threat protection settings label in the Windows 安全中心 app](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="e2abc-181">确认 **基于云的保护和\*\*\*\*自动提交示例** 已切换到 **开**。</span><span class="sxs-lookup"><span data-stu-id="e2abc-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="e2abc-182">如果已使用组策略配置自动提交示例，则设置将灰出且不可用。</span><span class="sxs-lookup"><span data-stu-id="e2abc-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e2abc-183">相关文章</span><span class="sxs-lookup"><span data-stu-id="e2abc-183">Related articles</span></span>

- [<span data-ttu-id="e2abc-184">配置云块超时时间段</span><span class="sxs-lookup"><span data-stu-id="e2abc-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e2abc-185">配置首次看到时阻止</span><span class="sxs-lookup"><span data-stu-id="e2abc-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e2abc-186">使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒软件</span><span class="sxs-lookup"><span data-stu-id="e2abc-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="e2abc-187">[使用 Windows for Endpoint Protection 保护](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)Microsoft Intune ]</span><span class="sxs-lookup"><span data-stu-id="e2abc-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="e2abc-188">Defender cmdlet</span><span class="sxs-lookup"><span data-stu-id="e2abc-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="e2abc-189">在云中使用 Microsoft 云提供的Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="e2abc-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e2abc-190">如何创建和部署反恶意软件策略：云保护服务</span><span class="sxs-lookup"><span data-stu-id="e2abc-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="e2abc-191">Microsoft Defender 防病毒Windows 10</span><span class="sxs-lookup"><span data-stu-id="e2abc-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
