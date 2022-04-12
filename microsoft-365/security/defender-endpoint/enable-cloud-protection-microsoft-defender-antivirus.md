---
title: 在Microsoft Defender 防病毒中启用云保护
description: 启用云保护以受益于快速和高级的保护功能。
keywords: Microsoft Defender 防病毒、反恶意软件、安全性、云、首次看到时阻止
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 02/03/2022
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 95269837e4ad26b4928a2ff82df65a259c707290
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790649"
---
# <a name="turn-on-cloud-protection-in-microsoft-defender-antivirus"></a>在Microsoft Defender 防病毒中启用云保护

**适用于：**

- Microsoft Defender 防病毒
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**平台**
- Windows

[Microsoft Defender 防病毒中的云保护](cloud-protection-microsoft-defender-antivirus.md)提供准确、实时和智能的保护。 默认情况下应启用云保护;但是，可以配置云保护以满足组织的需求。

## <a name="methods-to-configure-cloud-protection"></a>配置云保护的方法

可以使用以下几种方法之一打开或关闭Microsoft Defender 防病毒云保护：

- Microsoft Endpoint Manager，其中包括Microsoft Intune和Configuration Manager
- 组策略
- PowerShell cmdlet

还可以使用Windows 安全中心应用在单个终结点上启用或关闭云保护。 

有关确保终结点可以连接到云保护服务的特定网络连接要求的详细信息，请参阅 [配置和验证网络连接](configure-network-connections-microsoft-defender-antivirus.md)。

> [!NOTE]
> 在Windows 10和Windows 11中，本文中所述 **的基本** 报告选项和 **高级** 报告选项之间没有区别。 这是传统区别，选择任一设置将导致相同的云保护级别。 共享的信息类型或数量没有差异。 有关收集内容的详细信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=521839)。

## <a name="use-intune-to-turn-on-cloud-protection"></a>使用Intune启用云保护

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 在 **“主页** ”窗格中，选择 **“设备配置>配置文件**。

3. 选择要配置的 **设备限制** 配置文件类型。 如果需要创建新的 **设备限制** 配置文件类型，请参阅 [Microsoft Intune中配置设备限制设置](/intune/device-restrictions-configure)。

4. 选择 **“属性** \> **配置”设置：编辑** \> **Microsoft Defender 防病毒**。

5. 在 **云提供的保护** 开关上，选择 **“启用**”。

6. 在 **示例提交下拉列表前的提示用户** 中，选择 **“自动发送所有数据**”。

有关Intune设备配置文件的详细信息，包括如何创建和配置其设置，请参阅[Microsoft Intune设备配置文件？](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-protection"></a>使用Microsoft Endpoint Manager启用云保护

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 选择 **终结点安全** \> **防病毒**。

3. 选择防病毒配置文件。  (如果还没有配置文件，或者要创建新配置文件，请参阅[Microsoft Intune中配置设备限制设置](/intune/device-restrictions-configure)。

4. 选择“属性”。 然后，在 **“配置设置”** 旁边选择 **“编辑**”。

5. 展开 **云保护**，然后在 **云提供的保护级别** 列表中，选择下列选项之一：
   - **高**：应用强级别的检测。
   - **高加**：使用 **高级** 和应用更多的保护措施 (可能会影响客户端性能) 。
   - **零容错**：阻止所有未知的可执行文件。

6. 选择 **“审阅 + 保存**”，然后选择 **“保存**”。

有关配置Microsoft Endpoint Configuration Manager的详细信息，[请参阅如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。

## <a name="use-group-policy-to-turn-on-cloud-protection"></a>使用组策略启用云保护

1. 在组策略管理设备上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后选择 **“编辑**”。

2. 在 **组策略管理编辑器** 中，转到 **计算机配置**。

3. 选择 **管理模板**。

4. 将树展开为 **Windows组件** > **Microsoft Defender 防病毒 > MAPS**

    > [!NOTE]
    > MAPS 设置等于云提供的保护。

5. 双击 **“加入 Microsoft MAPS**”。 确保该选项已启用并设置为 **基本 MAPS** 或 **高级 MAPS**。 选择“确定”。

    可以选择发送有关检测到的软件的基本或附加信息：

    - 基本 MAPS：基本成员身份将向 Microsoft 发送有关设备上检测到的恶意软件和可能不需要的软件的基本信息。 信息包括软件的来源 (（如 URL）和部分路径) 、为解决威胁而采取的操作，以及操作是否成功。

    - 高级 MAPS：除了基本信息外，高级成员身份还会发送有关恶意软件和可能不需要的软件的详细信息，包括软件的完整路径，以及有关软件如何影响设备的详细信息。

6. **需要进一步分析时，双击“发送文件示例**”。 确保第一个选项设置为 **“已启用** ”，并将其他选项设置为以下任一选项：

   - **发送安全示例** (1) 
   - **将所有示例发送** (3) 

   >[!NOTE]
   > **“发送安全示例** (1) 选项意味着将自动发送大多数示例。 可能包含个人信息的文件仍会提示并需要其他确认。
   > 将选项设置为 **Always Prompt** (0) 将降低设备的保护状态。 将其设置为 **“从不发送**” (2) 意味着Microsoft Defender for Endpoint的 [“一见钟情](configure-block-at-first-sight-microsoft-defender-antivirus.md)”功能将不起作用。

7. 选择“确定”。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-protection"></a>使用 PowerShell cmdlet 启用云保护

以下 cmdlet 可以启用云保护：

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Microsoft Defender 防病毒 cmdlet](/powershell/module/defender/)。 [策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender) 还提供有关 [-SubmitSamplesConsent 的](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)详细信息。

> [!IMPORTANT]
> 可以将 **-SubmitSamplesConsent** 设置为 `SendSafeSamples` (默认的、建议的设置) `NeverSend`或 `AlwaysPrompt`。 此 `SendSafeSamples` 设置意味着将自动发送大多数示例。 可能包含个人信息的文件将导致提示继续，并且需要确认。
> 和`NeverSend``AlwaysPrompt`设置降低了设备的保护级别。 此外，该`NeverSend`设置意味着Microsoft Defender for Endpoint的[“一见钟情](configure-block-at-first-sight-microsoft-defender-antivirus.md)”功能将不起作用。

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-protection"></a>使用 Windows 管理指令 (WMI) 启用云保护

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/defender/set-msft-mppreference)：

```WMI
MAPSReporting
SubmitSamplesConsent
```

有关允许的参数的详细信息，请[参阅 Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-protection-on-individual-clients-with-the-windows-security-app"></a>使用Windows 安全中心应用对单个客户端启用云保护

> [!NOTE]
> 如果针对 **报告 Microsoft MAPS 组策略设置的配置本地设置重写** 设置设置为 **“已禁** 用”，则Windows 设置中 **基于云的保护** 设置将灰显且不可用。 通过组策略对象进行的更改必须先部署到个别终结点，然后 Windows 设置中的相关设置才会更新。

1. 通过在任务栏中选择盾牌图标，或者通过搜索开始菜单来Windows 安全中心，打开 **Windows 安全中心** 应用。

2. 选择 **“病毒&威胁防护** ”磁贴 (或左侧菜单栏) 上的“防护”图标，然后在 **“管理”设置** 下选择 **“病毒&威胁防护设置**”。

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="病毒&威胁防护设置" lightbox="../../media/wdav-protection-settings-wdsc.png":::

3. 确认 **已将基于云的保护** 和 **自动示例提交** 切换到 **On**。

   > [!NOTE]
   > 如果已使用组策略配置了自动示例提交，则设置将灰显且不可用。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [在 Microsoft Defender 防病毒 中使用 Microsoft 云保护](cloud-protection-microsoft-defender-antivirus.md)

- [如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

- [使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)
