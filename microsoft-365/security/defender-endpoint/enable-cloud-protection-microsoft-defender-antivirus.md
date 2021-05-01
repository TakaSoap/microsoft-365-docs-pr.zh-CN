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
# <a name="turn-on-cloud-delivered-protection"></a>打开云传递保护

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Microsoft Defender 防病毒云服务是一种向网络和终结点提供更新保护的机制。 尽管它称为云服务，但它并不仅仅是对存储在云中的文件的保护;相反，它使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。

Microsoft Defender 防病毒使用多个检测和防护技术提供准确、实时和智能的保护。 了解 Microsoft Defender for Endpoint 下一代保护[的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。
![Microsoft Defender AV 引擎列表](images/microsoft-defender-atp-next-generation-protection-engines.png)  

可以通过多种方式Microsoft Defender 防病毒或关闭云保护：

- Microsoft Intune
- Microsoft Endpoint Manager
- 组策略
- PowerShell cmdlet。

 此外，还可使用应用在个别客户端中Windows 安全中心它。

请参阅[使用 Microsoft 云保护](cloud-protection-microsoft-defender-antivirus.md)，了解云Microsoft Defender 防病毒保护的概述。

有关确保终结点可以连接到云保护服务的特定网络连接要求详细信息，请参阅配置和 [验证网络连接](configure-network-connections-microsoft-defender-antivirus.md)。

> [!NOTE]
> 在Windows 10中，本主题中介绍的基本报告选项和 **高级** 报告选项之间没有区别。  这是旧区别，选择任一设置都将产生相同级别的云保护。 共享的信息的类型或数量没有差异。 有关我们收集的信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=521839)。

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>使用 Intune 打开云提供的保护

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。

2. 在"**主页"** 窗格中，选择"设备 **配置>配置文件"。**

3. 选择要 **配置的设备** 限制配置文件类型。 如果需要创建新的设备限制配置文件类型，请参阅配置设备[限制Microsoft Intune。](/intune/device-restrictions-configure)

4. 选择 **"属性**  >  **""配置设置："**  >  **编辑Microsoft Defender 防病毒"。**

5. 在云 **保护开关上，****选择启用**。

6. 在"**在示例提交前提示用户"** 下拉列表中，选择"**自动发送所有数据"。**

有关 Intune 设备配置文件（包括如何创建和配置其设置）详细信息，请参阅什么是Microsoft Intune[配置文件？](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>使用Microsoft Endpoint Manager启用云保护

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。

2. 选择 **终结点安全**  >  **防病毒**。

3. 选择防病毒配置文件。  (如果还没有配置文件，或者要创建新的配置文件，请参阅配置 Microsoft Intune 中的[设备限制设置](/intune/device-restrictions-configure)。

4. 选择 **"属性"。** 然后，在"配置 **设置"旁边，选择**"编辑 **"。**

5. 展开 **"云** 保护"，然后在" **云提供的** 保护级别"列表中，选择下列选项之一：
   - **高**：应用强级别的检测。
   - **高加**： **使用高级别** ，并应用其他保护措施 (可能会影响客户端性能) 。
   - **零容** 限：阻止所有未知可执行文件。

6. 选择 **"审阅 + 保存"，** 然后选择"**保存"。**

有关配置反恶意软件Microsoft Endpoint Configuration Manager，请参阅如何创建和部署[反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>使用组策略启用云保护

1. 在组策略管理设备上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。

2. 在组 **策略管理编辑器中**，转到计算机 **配置**。

3. 选择 **"管理模板"。**

4. 展开树以 **Windows MAPS > Microsoft Defender 防病毒 >组件**

5. 双击加入 **Microsoft MAPS**。 确保该选项已打开，并设置为 **基本 MAPS** 或 **高级 MAPS。** 选择“**确定**”。

6. 双击需要进 **一步分析时发送文件示例**。 确保第一个选项设置为 **"已启用** "，并且其他选项设置为：

    1. **发送安全示例** (1) 
    2. **发送所有示例 (** 3) 

        >[!NOTE]
        > " **发送安全 (** 1) "选项意味着将自动发送大多数示例。 可能包含个人信息的文件仍将提示并需要其他确认。
        > 将选项设置为"始终 **提示** (0) 会降低设备的保护状态。 将其设置为"从不 **(** 2) "意味着 Microsoft Defender for [](configure-block-at-first-sight-microsoft-defender-antivirus.md) Endpoint 的"首次看到时阻止"功能将不起作用。

7. 选择“**确定**”。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>使用 PowerShell cmdlet 启用云保护

以下 cmdlet 可以启用云保护：

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender cmdlet。](/powershell/module/defender/) [策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender) 也具有有关 [-SubmitSamplesConsent 的专门详细信息](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)。

>[!NOTE]
> 还可以将 **-SubmitSamplesConsent** 设置为 `SendSafeSamples` (、或) `NeverSend` 默认设置 `AlwaysPrompt` 。 `SendSafeSamples`该设置意味着将自动发送大多数示例。 可能包含个人信息的文件仍将提示并需要其他确认。

>[!WARNING]
> 将 **-SubmitSamplesConsent** 设置为 `NeverSend` 或 `AlwaysPrompt` 会降低设备的保护级别。 此外，设置它意味着 Microsoft Defender for Endpoint 的"首次 `NeverSend` [看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 时阻止"功能将不起作用。

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>使用 Windows Management Instruction (WMI) 启用云保护

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/defender/set-msft-mppreference)类的 Set 方法：

```WMI
MAPSReporting
SubmitSamplesConsent
```

有关允许的参数详细信息，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>使用云保护应用在个别客户端上Windows 安全中心保护

> [!NOTE]
> 如果"**为** 报告 Microsoft MAPS 组策略配置本地设置覆盖"设置为"已禁用"，则 Windows 设置 中的基于云的保护设置将灰出且不可用。  必须先通过组策略对象所做的更改部署到各个终结点，然后才能在 Windows 设置 中更新设置。

1. 打开Windows 安全中心应用，选择任务栏中的防护图标，或搜索 Defender 的"开始"**菜单**。

2. 选择病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后选择病毒防护威胁防护 **&标签：**

    ![Screenshot of the Virus & threat protection settings label in the Windows 安全中心 app](images/defender/wdav-protection-settings-wdsc.png)

3. 确认 **基于云的保护和****自动提交示例** 已切换到 **开**。

> [!NOTE]
> 如果已使用组策略配置自动提交示例，则设置将灰出且不可用。

## <a name="related-articles"></a>相关文章

- [配置云块超时时间段](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [配置首次看到时阻止](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [使用 Windows for Endpoint Protection 保护](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)Microsoft Intune ]
- [Defender cmdlet](/powershell/module/defender/)
- [在云中使用 Microsoft 云提供的Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)
- [如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender 防病毒Windows 10](microsoft-defender-antivirus-in-windows-10.md)
