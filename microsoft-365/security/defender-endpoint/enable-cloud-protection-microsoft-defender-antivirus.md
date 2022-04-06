---
title: 在云中打开云Microsoft Defender 防病毒
description: 启用云保护，以从快速和高级保护功能中获益。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， 云， 首次看到时阻止
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
ms.openlocfilehash: 78f992e20ee0c0c2505777295ca3ba34a5c4ea66
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470628"
---
# <a name="turn-on-cloud-protection-in-microsoft-defender-antivirus"></a>在云中打开云Microsoft Defender 防病毒

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

[云保护Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)提供准确、实时和智能的保护。 默认情况下应启用云保护;但是，你可以配置云保护以满足组织的需求。

## <a name="methods-to-configure-cloud-protection"></a>配置云保护的方法

可以使用多种Microsoft Defender 防病毒之一打开或关闭云保护：

- Microsoft Endpoint Manager，包括Microsoft Intune和配置管理器
- 组策略
- PowerShell cmdlet

还可使用应用在个别终结点上打开或关闭Windows 安全中心保护。 

有关确保终结点可以连接到云保护服务的特定网络连接要求详细信息，请参阅配置 [和验证网络连接](configure-network-connections-microsoft-defender-antivirus.md)。

> [!NOTE]
> 在Windows 10和Windows 11中，本文中介绍的基本报告选项和高级报告选项之间没有区别。 这是旧区别，选择任一设置都将产生相同级别的云保护。 共享的信息的类型或数量没有差异。 有关我们收集的信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=521839)。

## <a name="use-intune-to-turn-on-cloud-protection"></a>使用 Intune 打开云保护

1. 转到管理Microsoft Endpoint Manager中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 在" **主页"** 窗格中，选择"设备 **配置>配置文件"**。

3. 选择要 **配置的设备** 限制配置文件类型。 如果你需要创建新的设备限制配置文件类型，请参阅配置设备[限制](/intune/device-restrictions-configure)Microsoft Intune。

4. 选择 **"属性** \> **配置设置：编辑** \> **Microsoft Defender 防病毒**"。

5. 在云 **保护开关上，** 选择"启用 **"**。

6. 在" **在示例提交前提示用户"** 下拉列表中，选择" **自动发送所有数据"**。

有关 Intune 设备配置文件（包括如何创建和配置其设置）详细信息，请参阅什么是Microsoft Intune[配置文件？](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-protection"></a>使用Microsoft Endpoint Manager启用云保护

1. 转到管理Microsoft Endpoint Manager中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 选择 **"终结点安全** \> **防病毒"**。

3. 选择防病毒配置文件。  (如果还没有配置文件，或者要创建新的配置文件，请参阅配置 Microsoft Intune 中的[设备Microsoft Intune](/intune/device-restrictions-configure)。

4. 选择“属性”。 然后，在"配置 **设置"旁边，** 选择"编辑 **"**。

5. 展开 **"云** 保护"，然后在" **云提供的** 保护级别"列表中，选择下列选项之一：
   - **高**：应用强级别的检测。
   - **高加**： **使用高级别** ，并应用更多保护措施 (可能会影响客户端性能) 。
   - **零公差**：阻止所有未知可执行文件。

6. 选择 **"审阅 + 保存"**，然后选择" **保存"**。

有关配置反恶意软件Microsoft Endpoint Configuration Manager，请参阅如何创建[和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。

## <a name="use-group-policy-to-turn-on-cloud-protection"></a>使用组策略启用云保护

1. 在组策略管理设备上，打开组 [策略](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))管理控制台，右键单击要配置的组策略对象，**然后选择编辑。**

2. 在组 **策略管理编辑器中**，转到计算机 **配置**。

3. 选择 **"管理模板"**。

4. 展开树以 **Windows组件** > **Microsoft Defender 防病毒 > MAPS**

    > [!NOTE]
    > MAPS 设置等同于云提供的保护。

5. 双击加入 **Microsoft MAPS**。 确保该选项已打开，并设置为 **基本 MAPS** 或 **高级 MAPS**。 选择“**确定**”。

    你可以选择发送有关检测到的软件的基本或其他信息：

    - 基本 MAPS：基本成员身份将向 Microsoft 发送有关设备上检测到的恶意软件和可能不需要的软件的基本信息。 信息包括软件来自 (URL 和部分路径) 、为解决威胁而采取的操作，以及操作是否成功。

    - 高级 MAPS：除了基本信息之外，高级成员身份还将发送有关恶意软件和可能不需要的软件的详细信息，包括软件的完整路径，以及软件对设备的影响的详细信息。

6. 如果需要进 **一步分析，请双击"发送文件示例"**。 确保第一个选项设置为 **"已启用** "，并且其他选项设置为：

   - **发送安全示例** (1) 
   - **发送所有示例** (3) 

   >[!NOTE]
   > " **发送安全 (** 1) "选项意味着将自动发送大多数示例。 可能包含个人信息的文件仍将提示并需要其他确认。
   > 将选项设置为"始终 **提示** (0) 会降低设备的保护状态。 将其设置为"从不 **(** 2) "意味着 Microsoft Defender for Endpoint 的"首次看到时 [](configure-block-at-first-sight-microsoft-defender-antivirus.md)阻止"功能将不起作用。

7. 选择“**确定**”。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-protection"></a>使用 PowerShell cmdlet 启用云保护

以下 cmdlet 可以打开云保护：

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

有关如何使用 PowerShell 和 Microsoft Defender 防病毒，请参阅使用 [PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒 [和 Microsoft Defender 防病毒 cmdlet](/powershell/module/defender/)。 [策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender) 也具有有关 [-SubmitSamplesConsent 的专门详细信息](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)。

> [!IMPORTANT]
> 你可以将 **-SubmitSamplesConsent** `SendSafeSamples` 设置为 (推荐的默认设置) 、 `NeverSend`或 `AlwaysPrompt`。 该 `SendSafeSamples` 设置意味着将自动发送大多数示例。 可能包含个人信息的文件将导致提示继续，并且需要确认。
> 和 `NeverSend` `AlwaysPrompt` 设置会降低设备的保护级别。 此外，该`NeverSend`设置意味着 Microsoft Defender for [](configure-block-at-first-sight-microsoft-defender-antivirus.md) Endpoint 的"首次看到时阻止"功能将不起作用。

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-protection"></a>使用 Windows Management Instruction (WMI) 启用云保护

对 [以下属性MSFT_MpPreference **类的** **Set**](/previous-versions/windows/desktop/defender/set-msft-mppreference) 方法：

```WMI
MAPSReporting
SubmitSamplesConsent
```

有关允许的参数详细信息，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-protection-on-individual-clients-with-the-windows-security-app"></a>使用云保护应用在个别客户端上Windows 安全中心保护

> [!NOTE]
> 如果"**为报告 Microsoft MAPS** 组策略配置本地设置覆盖"设置为"已禁用"，则 Windows 设置  中的基于云的保护设置将灰出且不可用。 通过组策略对象进行的更改必须先部署到个别终结点，然后 Windows 设置中的相关设置才会更新。

1. 打开Windows 安全中心应用，选择任务栏中的防护图标，或搜索"开始"菜单 **Windows 安全中心。**

2. 选择病毒&**威胁** 防护磁贴 (左侧菜单栏) 上的防护图标，然后在"管理设置"下选择"病毒&**威胁防护设置"**。

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="病毒&威胁防护设置" lightbox="../../media/wdav-protection-settings-wdsc.png":::

3. 确认 **基于云的保护和****自动提交示例** 已切换到 **"开"**。

   > [!NOTE]
   > 如果已使用组策略配置自动提交示例，则设置将灰出且不可用。

## <a name="see-also"></a>另请参阅

- [在云中使用 Microsoft 云Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)

- [如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

- [使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)
