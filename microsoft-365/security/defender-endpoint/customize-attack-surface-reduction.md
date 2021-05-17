---
title: 自定义减少攻击面规则
description: 在审核、阻止或禁用模式中单独设置规则，并添加应从攻击面减少规则中排除的文件和文件夹
keywords: 攻击面减少， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， 自定义， 配置， 排除
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 52a51b1035f1aa0fb152cf17dc9561cce378d59d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570347"
---
# <a name="customize-attack-surface-reduction-rules"></a>自定义减少攻击面规则

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

[攻击面减少规则](enable-attack-surface-reduction.md) 有助于防止经常滥用以损害设备或网络的软件行为。 例如，攻击者可能会尝试从 USB 驱动器运行未签名的脚本，或者让 Office 文档中的宏直接调用 Win32 API。 攻击面减少规则可以限制这些类型的风险行为，并改进组织的防御状态。

了解如何通过排除文件和文件夹或向用户计算机上[](#exclude-files-and-folders)显示的通知警报添加自定义文本[](#customize-the-notification)来自定义攻击面减少规则。

你可以为运行以下任一版本和版本的设备设置攻击面减少规则Windows：
- Windows 10 专业版版本[1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)或更高版本
- Windows 10 企业版版本[1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)或更高版本
- Windows服务器版本[1803 (半年频道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)可以使用组策略、PowerShell 和移动设备管理 (MDM) CSP (配置) 配置这些设置。

## <a name="exclude-files-and-folders"></a>排除文件和文件夹

你可以选择从攻击面减少规则评估中排除文件和文件夹。 排除后，即使攻击面减少规则检测到文件包含恶意行为，也不会阻止文件运行。

> [!WARNING]
> 这可能会允许不安全的文件运行并感染你的设备。 排除文件或文件夹会大大降低攻击面减少规则所提供的保护。 将允许运行规则阻止的文件，并且不会记录任何报告或事件。

排除适用于允许排除的所有规则。 您可以为资源指定单个文件、文件夹路径或完全限定的域名。 但是，不能将排除限制到特定规则。

仅在已排除的应用程序或服务启动时应用排除。 例如，如果为已在运行的更新服务添加排除项，则更新服务将继续触发事件，直到停止并重新启动该服务。

攻击面减少支持环境变量和通配符。 有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。
如果在检测你认为不应检测到的文件的规则方面遇到问题，请使用审核模式 [测试规则](evaluate-attack-surface-reduction.md)。

规则说明 | GUID
-|-|-
阻止所有Office应用程序创建子进程 | D4F940AB-401B-4EFC-AADC-AD5F3C50688A
阻止执行可能混淆的脚本 | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC
从宏中阻止 Win32 API Office调用 | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B
阻止Office应用程序创建可执行内容 | 3B576869-A4EC-4529-8536-B80A7769E899
阻止Office代码注入其他进程 | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84
阻止 JavaScript 或 VBScript 启动下载的可执行内容 | D3E037E1-3EB8-44C8-A917-57927947596D
阻止来自电子邮件客户端和 Webmail 的可执行内容 | BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550
阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件 | 01443614-cd74-433a-b99e-2ecdc07bfc25
使用高级防护抵御勒索软件 | c1db55ab-c21a-4637-bb3f-a12568109d35
阻止本地安全机构子系统Windows窃取凭据 (lsass.exe)  | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2
阻止源自 PSExec 和 WMI 命令的进程创建 | d1e49aac-8f56-4280-b9ba-993a6d77406c
阻止从 USB 运行的不受信任的和未签名的进程 | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4
阻止Office应用程序创建子进程 | 26190899-1602-49e8-8b27-eb1d0a1ce869
阻止 Adobe Reader 创建子进程 | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c
通过 WMI 事件订阅阻止持久性 | e6db77e5-3df2-4cf1-b95a-636979351e5b

有关 [每个规则的详细信息](attack-surface-reduction.md) ，请参阅攻击面减少主题。

### <a name="use-group-policy-to-exclude-files-and-folders"></a>使用组策略排除文件和文件夹

1. 在组策略管理计算机上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **编辑**。

2. 在组 **策略管理编辑器中**，转到计算机 **配置，** 然后单击 **管理模板**。

3. 展开树以 **Windows攻击**  >  **Microsoft Defender 防病毒Windows Defender**  >  **攻击**  >  **面减少的组件**。

4. 双击从攻击 **面减少规则中排除** 文件和路径设置，将选项设置为 **已启用**。 选择 **"显示** "，在"值名称"列中 **输入每个文件或** 文件夹。 在"值"**列中为** 每个项目输入 **0。**

> [!WARNING]
> 请勿使用引号，因为"值名称"列或"值"列不支持 **引号**。

### <a name="use-powershell-to-exclude-files-and-folders"></a>使用 PowerShell 排除文件和文件夹

1. 在 **"开始"菜单中键入 powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"**
2. 输入以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

继续使用 向 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 列表中添加更多文件夹。

> [!IMPORTANT]
> 用于 `Add-MpPreference` 向列表中追加或添加应用。 使用 `Set-MpPreference` cmdlet 将覆盖现有列表。

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>使用 MDM CSP 排除文件和文件夹

使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。

## <a name="customize-the-notification"></a>自定义通知

你可以自定义何时触发规则并阻止应用或文件的通知。 请参阅[Windows 安全中心](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)文章。

## <a name="related-topics"></a>相关主题

* [使用攻击面减少规则减少攻击面](attack-surface-reduction.md)
* [启用攻击面减少规则](enable-attack-surface-reduction.md)
* [评估减少攻击面规则](evaluate-attack-surface-reduction.md)
* [关于减少攻击面的常见问题解答](attack-surface-reduction.md)
