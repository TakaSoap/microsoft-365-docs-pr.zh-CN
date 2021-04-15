---
title: 在 Microsoft Defender 防病毒中打开云保护
description: 启用云保护，以从快速和高级保护功能中获益。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， 云， 首次看到时阻止
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9f949a4cb54ca5dd64a2648bb05a5cb9ad50e44d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764959"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="5546d-104">打开云传递保护</span><span class="sxs-lookup"><span data-stu-id="5546d-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5546d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5546d-105">**Applies to:**</span></span>

- [<span data-ttu-id="5546d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5546d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="5546d-107">Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。</span><span class="sxs-lookup"><span data-stu-id="5546d-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="5546d-108">尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护;相反，它使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。</span><span class="sxs-lookup"><span data-stu-id="5546d-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="5546d-109">Microsoft Defender 防病毒使用多个检测和防护技术提供准确、实时和智能的保护。</span><span class="sxs-lookup"><span data-stu-id="5546d-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="5546d-110">了解 Microsoft Defender for Endpoint 下一代保护[的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="5546d-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="5546d-111">![Microsoft Defender AV 引擎列表](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="5546d-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="5546d-112">可以通过多种方式打开或关闭 Microsoft Defender 防病毒云保护：</span><span class="sxs-lookup"><span data-stu-id="5546d-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="5546d-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5546d-113">Microsoft Intune</span></span>
- <span data-ttu-id="5546d-114">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5546d-114">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="5546d-115">组策略</span><span class="sxs-lookup"><span data-stu-id="5546d-115">Group Policy</span></span>
- <span data-ttu-id="5546d-116">PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5546d-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="5546d-117">还可使用 Windows 安全应用在个别客户端中打开或关闭它。</span><span class="sxs-lookup"><span data-stu-id="5546d-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="5546d-118">有关 Microsoft Defender 防病毒 [云保护](cloud-protection-microsoft-defender-antivirus.md) 的概述，请参阅使用 Microsoft 云保护。</span><span class="sxs-lookup"><span data-stu-id="5546d-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="5546d-119">有关确保终结点可以连接到云保护服务的特定网络连接要求详细信息，请参阅配置和 [验证网络连接](configure-network-connections-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="5546d-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5546d-120">在 Windows 10 中，本主题中介绍的基本报告选项和 **高级** 报告选项之间没有区别。</span><span class="sxs-lookup"><span data-stu-id="5546d-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="5546d-121">这是旧区别，选择任一设置都将产生相同级别的云保护。</span><span class="sxs-lookup"><span data-stu-id="5546d-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="5546d-122">共享的信息的类型或数量没有差异。</span><span class="sxs-lookup"><span data-stu-id="5546d-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="5546d-123">有关我们收集的信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=521839)。</span><span class="sxs-lookup"><span data-stu-id="5546d-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="5546d-124">使用 Intune 打开云提供的保护</span><span class="sxs-lookup"><span data-stu-id="5546d-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="5546d-125">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="5546d-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="5546d-126">在"**主页"** 窗格中，选择"设备 **配置>配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="5546d-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>
3. <span data-ttu-id="5546d-127">选择要 **配置的设备** 限制配置文件类型。</span><span class="sxs-lookup"><span data-stu-id="5546d-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="5546d-128">如果你需要创建新的设备限制配置文件类型，请参阅在 Microsoft Intune 中配置[设备限制设置](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="5546d-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="5546d-129">选择 **属性**  >  **配置设置：编辑**  >  **Microsoft Defender 防病毒**。</span><span class="sxs-lookup"><span data-stu-id="5546d-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>
5. <span data-ttu-id="5546d-130">在云 **保护开关上，\*\*\*\*选择启用**。</span><span class="sxs-lookup"><span data-stu-id="5546d-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>
6. <span data-ttu-id="5546d-131">在"**在示例提交前提示用户"** 下拉列表中，选择"**自动发送所有数据"。**</span><span class="sxs-lookup"><span data-stu-id="5546d-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="5546d-132">有关 Intune 设备配置文件（包括如何创建和配置其设置）的信息，请参阅 [什么是 Microsoft Intune 设备配置文件？](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="5546d-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="5546d-133">使用 Microsoft Endpoint Manager 打开云保护</span><span class="sxs-lookup"><span data-stu-id="5546d-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="5546d-134">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="5546d-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="5546d-135">选择 **终结点安全**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="5546d-135">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="5546d-136">选择防病毒配置文件。</span><span class="sxs-lookup"><span data-stu-id="5546d-136">Select an antivirus profile.</span></span> <span data-ttu-id="5546d-137"> (如果你还没有配置文件，或者如果你想要创建新的配置文件，请参阅在 [Microsoft Intune](/intune/device-restrictions-configure)中配置设备限制设置。</span><span class="sxs-lookup"><span data-stu-id="5546d-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="5546d-138">选择 **"属性"。**</span><span class="sxs-lookup"><span data-stu-id="5546d-138">Select **Properties**.</span></span> <span data-ttu-id="5546d-139">然后，在"配置 **设置"旁边，选择**"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="5546d-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>
5. <span data-ttu-id="5546d-140">展开 **"云** 保护"，然后在" **云提供的** 保护级别"列表中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="5546d-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
    1. <span data-ttu-id="5546d-141">**高**：应用强级别的检测。</span><span class="sxs-lookup"><span data-stu-id="5546d-141">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="5546d-142">**高加**： **使用高级别** ，并应用其他保护措施 (可能会影响客户端性能) 。</span><span class="sxs-lookup"><span data-stu-id="5546d-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="5546d-143">**零容** 限：阻止所有未知可执行文件。</span><span class="sxs-lookup"><span data-stu-id="5546d-143">**Zero tolerance**: Blocks all unknown executables.</span></span>
6. <span data-ttu-id="5546d-144">选择 **"审阅 + 保存"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="5546d-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="5546d-145">有关配置 Microsoft Endpoint Configuration Manager 的信息，请参阅如何创建和部署 [反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。</span><span class="sxs-lookup"><span data-stu-id="5546d-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="5546d-146">使用组策略启用云保护</span><span class="sxs-lookup"><span data-stu-id="5546d-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="5546d-147">在组策略管理设备上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="5546d-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="5546d-148">在组 **策略管理编辑器中**，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="5546d-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5546d-149">选择 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="5546d-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="5546d-150">将树展开到 **Microsoft Defender 防病毒> MAPS 中的 Windows >组件**</span><span class="sxs-lookup"><span data-stu-id="5546d-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="5546d-151">双击加入 **Microsoft MAPS**。</span><span class="sxs-lookup"><span data-stu-id="5546d-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="5546d-152">确保该选项已打开，并设置为 **基本 MAPS** 或 **高级 MAPS。**</span><span class="sxs-lookup"><span data-stu-id="5546d-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="5546d-153">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="5546d-153">Select **OK**.</span></span>

6. <span data-ttu-id="5546d-154">双击需要进 **一步分析时发送文件示例**。</span><span class="sxs-lookup"><span data-stu-id="5546d-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="5546d-155">确保第一个选项设置为 **"已启用** "，并且其他选项设置为：</span><span class="sxs-lookup"><span data-stu-id="5546d-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="5546d-156">**发送安全示例** (1) </span><span class="sxs-lookup"><span data-stu-id="5546d-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="5546d-157">**发送所有示例 (** 3) </span><span class="sxs-lookup"><span data-stu-id="5546d-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="5546d-158">" **发送安全 (** 1) "选项意味着将自动发送大多数示例。</span><span class="sxs-lookup"><span data-stu-id="5546d-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="5546d-159">可能包含个人信息的文件仍将提示并需要其他确认。</span><span class="sxs-lookup"><span data-stu-id="5546d-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

        > [!WARNING]
        > <span data-ttu-id="5546d-160">将选项设置为"始终 **提示** (0) 会降低设备的保护状态。</span><span class="sxs-lookup"><span data-stu-id="5546d-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="5546d-161">将其设置为"从不 **(** 2) "意味着 Microsoft Defender for [](configure-block-at-first-sight-microsoft-defender-antivirus.md) Endpoint 的"首次看到时阻止"功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="5546d-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="5546d-162">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="5546d-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="5546d-163">使用 PowerShell cmdlet 启用云保护</span><span class="sxs-lookup"><span data-stu-id="5546d-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="5546d-164">以下 cmdlet 可以启用云保护：</span><span class="sxs-lookup"><span data-stu-id="5546d-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="5546d-165">若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒和[Defender cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="5546d-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="5546d-166">[策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender) 也具有有关 [-SubmitSamplesConsent 的专门详细信息](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)。</span><span class="sxs-lookup"><span data-stu-id="5546d-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="5546d-167">还可以将 **-SubmitSamplesConsent** 设置为 `SendSafeSamples` (、或) `NeverSend` 默认设置 `AlwaysPrompt` 。</span><span class="sxs-lookup"><span data-stu-id="5546d-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="5546d-168">`SendSafeSamples`该设置意味着将自动发送大多数示例。</span><span class="sxs-lookup"><span data-stu-id="5546d-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="5546d-169">可能包含个人信息的文件仍将提示并需要其他确认。</span><span class="sxs-lookup"><span data-stu-id="5546d-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="5546d-170">将 **-SubmitSamplesConsent** 设置为 `NeverSend` 或 `AlwaysPrompt` 会降低设备的保护级别。</span><span class="sxs-lookup"><span data-stu-id="5546d-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="5546d-171">此外，设置它意味着 Microsoft Defender for Endpoint 的"首次 `NeverSend` [看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 时阻止"功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="5546d-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="5546d-172">使用 Windows Management Instruction (WMI) 启用云保护</span><span class="sxs-lookup"><span data-stu-id="5546d-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="5546d-173">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/defender/set-msft-mppreference)类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="5546d-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="5546d-174">有关允许的参数详细信息，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="5546d-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="5546d-175">使用 Windows 安全应用在个别客户端上启用云保护</span><span class="sxs-lookup"><span data-stu-id="5546d-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="5546d-176">如果"**为** 报告 Microsoft MAPS 组策略配置本地设置覆盖"设置为"已禁用"，则 Windows 设置中的基于云的保护设置将灰出且不可用。 </span><span class="sxs-lookup"><span data-stu-id="5546d-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="5546d-177">必须先通过组策略对象所做的更改部署到个别终结点，然后才能在 Windows 设置中更新设置。</span><span class="sxs-lookup"><span data-stu-id="5546d-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="5546d-178">通过选择任务栏中的防护图标或搜索 Defender 的"开始"菜单打开 Windows 安全 **应用**。</span><span class="sxs-lookup"><span data-stu-id="5546d-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="5546d-179">选择病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后选择病毒防护威胁防护 **&标签：**</span><span class="sxs-lookup"><span data-stu-id="5546d-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows 安全应用中的病毒&威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="5546d-181">确认 **基于云的保护和\*\*\*\*自动提交示例** 已切换到 **开**。</span><span class="sxs-lookup"><span data-stu-id="5546d-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="5546d-182">如果已使用组策略配置自动提交示例，则设置将灰出且不可用。</span><span class="sxs-lookup"><span data-stu-id="5546d-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5546d-183">相关文章</span><span class="sxs-lookup"><span data-stu-id="5546d-183">Related articles</span></span>

- [<span data-ttu-id="5546d-184">配置云块超时时间段</span><span class="sxs-lookup"><span data-stu-id="5546d-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5546d-185">配置首次看到时阻止</span><span class="sxs-lookup"><span data-stu-id="5546d-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5546d-186">使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒软件</span><span class="sxs-lookup"><span data-stu-id="5546d-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="5546d-187">[使用适用于 Microsoft Intune 的 Endpoint Protection 帮助](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)保护 Windows 电脑 ]</span><span class="sxs-lookup"><span data-stu-id="5546d-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="5546d-188">Defender cmdlet</span><span class="sxs-lookup"><span data-stu-id="5546d-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="5546d-189">在 Microsoft Defender 防病毒中使用 Microsoft 云提供的保护</span><span class="sxs-lookup"><span data-stu-id="5546d-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5546d-190">如何创建和部署反恶意软件策略：云保护服务</span><span class="sxs-lookup"><span data-stu-id="5546d-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="5546d-191">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="5546d-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)