---
title: 自定义减少攻击面规则
description: 在审核、阻止或禁用模式中单独设置规则，并添加应从攻击面减少规则中排除的文件和文件夹
keywords: 攻击面减少， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， 自定义， 配置， 排除
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 992c8802f3a4f44b1558004e2ee27ddbedf70a1a
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531167"
---
# <a name="customize-attack-surface-reduction-rules"></a>自定义减少攻击面规则

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

[攻击面减少规则](enable-attack-surface-reduction.md) 有助于防止经常滥用以损害设备或网络的软件行为。 例如，攻击者可能尝试从 USB 驱动器运行未签名的脚本，或者让 Office 文档中的宏直接调用 Win32 API。 攻击面减少规则可以限制这些类型的风险行为，并改进组织的防御状态。

了解如何通过排除文件和文件夹或向用户计算机上[](#exclude-files-and-folders)显示的通知警报添加自定义文本[](#customize-the-notification)来自定义攻击面减少规则。

你可以为运行以下任一版本和版本的设备设置攻击面减少规则Windows：

- Windows 10 专业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本
- Windows 10 企业版版本[1709](/windows/whats-new/whats-new-windows-10-version-1709)或更高版本
- Windows Server 版本[1803 (半年](/windows-server/get-started/whats-new-in-windows-server-1803)频道) 或更高版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
-  [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2) 
- Windows Server 2022

可以使用组策略、PowerShell 和移动设备管理 (MDM) CSP (配置) 配置这些设置。

有关 [受支持的](enable-attack-surface-reduction.md#requirements) 操作系统和其他要求信息的信息，请参阅"启用攻击面减少规则"文章中的要求。

## <a name="exclude-files-and-folders"></a>排除文件和文件夹

你可以选择从攻击面减少规则评估中排除文件和文件夹。 排除后，即使攻击面减少规则检测到文件包含恶意行为，也不会阻止文件运行。

例如，请考虑勒索软件规则：

勒索软件规则旨在帮助企业客户降低勒索软件攻击的风险，同时确保业务连续性。 默认情况下，勒索软件规则错误应谨慎处理，并防范尚未获得足够信誉和信任的文件。 为了重新强调一下，勒索软件规则仅针对未基于数百万客户的使用情况指标获得足够正面信誉和普遍程度的文件触发。 通常，块是自行解析的，因为每个文件的"信誉和信任"值都会随着无问题使用率的增加而递增升级。

如果无法及时解决阻止问题，客户可以自行承担风险，使用自助服务机制或基于IOC (IOC) 的"允许列表"功能来取消阻止文件本身。

> [!WARNING]
> 排除或取消阻止文件或文件夹可能会允许不安全的文件运行并感染你的设备。 排除文件或文件夹可以严重削弱攻击面减少规则提供的保护。 将允许运行规则阻止的文件，并且不会记录任何报告或事件。

排除应用于允许排除的所有规则。 可以指定单个文件、文件夹路径或资源的完全限定域名。 但是，不能将排除限制到特定规则。

仅在已排除的应用程序或服务启动时应用排除。 例如，如果为已在运行的更新服务添加排除项，则更新服务将继续触发事件，直到停止并重新启动该服务。

攻击面减少支持环境变量和通配符。 有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 。
如果在检测你认为不应检测到的文件的规则方面遇到问题，请使用审核模式 [测试规则](evaluate-attack-surface-reduction.md)。

有关每个 [规则的详细信息](attack-surface-reduction-rules-reference.md) ，请参阅攻击面减少规则参考主题。

### <a name="use-group-policy-to-exclude-files-and-folders"></a>使用组策略排除文件和文件夹

1. 在组策略管理计算机上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **编辑**。

2. 在组 **策略管理编辑器中**，转到计算机 **配置，** 然后单击 **管理模板**。

3. 展开树以 **Windows攻击** \>  \> **Microsoft Defender 防病毒Microsoft Defender 攻击防护** \> **减少的组件**。

4. 双击从攻击 **面减少规则中排除** 文件和路径设置，将选项设置为 **已启用**。 选择 **"显示** "，在"值名称"列中 **输入每个文件或** 文件夹。 在"值"**列中为** 每个项目输入 **0。**

> [!WARNING]
> 请勿使用引号，因为"值名称"列或"值"列不支持 **引号**。

### <a name="use-powershell-to-exclude-files-and-folders"></a>使用 PowerShell 排除文件和文件夹

1. 在"管理"中"开始"菜单 **powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"。**

2. 输入以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    继续使用 向 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 列表中添加更多文件夹。
    
    > [!IMPORTANT]
    > 用于 `Add-MpPreference` 向列表中追加或添加应用。 使用 `Set-MpPreference` cmdlet 将覆盖现有列表。

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>使用 MDM CSP 排除文件和文件夹

使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。

## <a name="customize-the-notification"></a>自定义通知

你可以自定义何时触发规则并阻止应用或文件的通知。 请参阅[Windows 安全中心](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)文章。

## <a name="related-topics"></a>相关主题

- [使用攻击面减少规则减少攻击面](attack-surface-reduction.md)
- [启用攻击面减少规则](enable-attack-surface-reduction.md)
- [评估攻击面减少规则](evaluate-attack-surface-reduction.md)
- [关于攻击面减少的常见问题解答](attack-surface-reduction.md)
