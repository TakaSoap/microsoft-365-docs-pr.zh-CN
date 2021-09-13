---
title: 在云中打开云Microsoft Defender 防病毒
description: 启用云保护，以从快速和高级保护功能中获益。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， 云， 首次看到时阻止
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 08/31/2021
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 82b773488fffb5b37390cc72043c1b011c5c6685
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222252"
---
# <a name="turn-on-cloud-protection-in-microsoft-defender-antivirus"></a>在云中打开云Microsoft Defender 防病毒

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防病毒

[云保护Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)提供准确、实时和智能的保护。 默认情况下应启用云保护;但是，你可以配置云保护以满足组织的需求。

## <a name="methods-to-configure-cloud-protection"></a>配置云保护的方法

可以通过使用Microsoft Defender 防病毒之一打开或关闭云保护：

- Microsoft Endpoint Manager，包括Microsoft Intune和配置管理器
- 组策略
- PowerShell cmdlet

还可使用应用在个别终结点上打开或关闭Windows 安全中心保护。 

有关确保终结点可以连接到云保护服务的特定网络连接要求详细信息，请参阅配置 [和验证网络连接](configure-network-connections-microsoft-defender-antivirus.md)。

> [!NOTE]
> 在Windows 10中，本主题中介绍的基本报告选项和高级报告选项之间没有区别。 这是旧区别，选择任一设置都将产生相同级别的云保护。 共享的信息的类型或数量没有差异。 有关我们收集的信息，请参阅 [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?linkid=521839)。

## <a name="use-intune-to-turn-on-cloud-protection"></a>使用 Intune 打开云保护

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。

2. 在"**主页"** 窗格中，选择"设备 **配置>配置文件"。**

3. 选择要 **配置的设备** 限制配置文件类型。 如果你需要创建新的设备限制配置文件类型，请参阅配置设备[限制Microsoft Intune。](/intune/device-restrictions-configure)

4. 选择 **"属性** \> **配置设置：编辑** \> **Microsoft Defender 防病毒"。**

5. 在云 **保护开关上，****选择启用**。

6. 在"**在示例提交前提示用户"** 下拉列表中，选择"**自动发送所有数据"。**

有关 Intune 设备配置文件（包括如何创建和配置其设置）的信息，请参阅什么是Microsoft Intune[配置文件？](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-protection"></a>使用Microsoft Endpoint Manager启用云保护

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。

2. 选择 **终结点安全** \> **防病毒**。

3. 选择防病毒配置文件。  (如果还没有配置文件，或者要创建新的配置文件，请参阅配置[Microsoft Intune。](/intune/device-restrictions-configure)

4. 选择 **"属性"。** 然后，在"配置 **设置"旁边，选择**"编辑 **"。**

5. 展开 **"云** 保护"，然后在" **云提供的** 保护级别"列表中，选择下列选项之一：
   - **高**：应用强级别的检测。
   - **高加**：使用 **高级别** ，并应用其他保护措施 (可能会影响客户端性能) 。
   - **零容** 限：阻止所有未知可执行文件。

6. 选择 **"审阅 + 保存"，** 然后选择"**保存"。**

有关配置反恶意软件Microsoft Endpoint Configuration Manager，请参阅如何创建和部署[反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。

## <a name="use-group-policy-to-turn-on-cloud-protection"></a>使用组策略启用云保护

1. 在组策略管理设备上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。

2. 在组 **策略管理编辑器中**，转到计算机 **配置**。

3. 选择 **"管理模板"。**

4. 展开树以Windows   >  **MAPS Microsoft Defender 防病毒 >组件**

5. 双击加入 **Microsoft MAPS**。 确保该选项已打开，并设置为 **基本 MAPS** 或 **高级 MAPS。** 选择“**确定**”。

6. 双击需要进 **一步分析时发送文件示例**。 确保第一个选项设置为 **"已启用** "，并且其他选项设置为：

   - **发送安全示例** (1) 
   - **发送所有示例 (** 3) 

   >[!NOTE]
   > " **发送安全 (** 1) "选项意味着将自动发送大多数示例。 可能包含个人信息的文件仍将提示并需要其他确认。
   > 将选项设置为"始终 **提示** (0) 会降低设备的保护状态。 将其设置为"从不 **(** 2) "意味着 Microsoft Defender [](configure-block-at-first-sight-microsoft-defender-antivirus.md) for Endpoint 的"首次看到时阻止"功能将不起作用。

7. 选择“**确定**”。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-protection"></a>使用 PowerShell cmdlet 启用云保护

以下 cmdlet 可以打开云保护：

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和 Defender [cmdlet。](/powershell/module/defender/) [策略 CSP - Defender](/windows/client-management/mdm/policy-csp-defender) 还专门提供 [-SubmitSamplesConsent 上的信息](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)。

> [!NOTE]
> 还可以将 **-SubmitSamplesConsent** 设置为 (`SendSafeSamples` 默认设置) 、 `NeverSend` 或 `AlwaysPrompt` 。 `SendSafeSamples`该设置意味着将自动发送大多数示例。 可能包含个人信息的文件仍将提示并需要其他确认。

> [!WARNING]
> 将 **-SubmitSamplesConsent** 设置为 `NeverSend` 或 `AlwaysPrompt` 会降低设备的保护级别。 此外，设置它意味着 Microsoft Defender for Endpoint 的"首次 `NeverSend` [看到](configure-block-at-first-sight-microsoft-defender-antivirus.md) 时阻止"功能将不起作用。

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-protection"></a>使用 Windows Management Instruction (WMI) 启用云保护

对 [以下属性MSFT_MpPreference类的 **Set**](/previous-versions/windows/desktop/defender/set-msft-mppreference)方法：

```WMI
MAPSReporting
SubmitSamplesConsent
```

有关允许的参数详细信息，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-protection-on-individual-clients-with-the-windows-security-app"></a>使用应用在个别客户端上Windows 安全中心保护

> [!NOTE]
> 如果"**为** 报告 Microsoft MAPS 组策略配置本地设置覆盖"设置为"已禁用"，则 Windows 设置 中的基于云的保护设置将灰出且不可用。  通过组策略对象进行的更改必须先部署到个别终结点，然后 Windows 设置中的相关设置才会更新。

1. 打开Windows 安全中心应用，选择任务栏中的防护图标，或搜索 Defender 的"开始"**菜单**。

2. 选择病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后选择病毒防护威胁防护 **&标签：**

    :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="病毒防护威胁&屏幕截图":::

3. 确认 **基于云的保护和****自动提交示例** 已切换到 **开**。

> [!NOTE]
> 如果已使用组策略配置自动提交示例，则设置将灰出且不可用。

## <a name="see-also"></a>另请参阅

- [在云中使用 Microsoft 云Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)

- [如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

- [使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)
