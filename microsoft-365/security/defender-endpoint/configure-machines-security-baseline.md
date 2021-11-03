---
title: 提高 Microsoft Defender 终结点安全基线的合规性
description: Microsoft Defender for Endpoint 安全基线设置安全控件以提供最佳保护。
keywords: Intune 管理， Microsoft Defender for Endpoint， Microsoft Defender， Microsoft Defender for Endpoint ASR， 安全基线
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3149f453886f72fd300f2961a7ef2ea1defce7a5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60673239"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a>提高 Microsoft Defender 终结点安全基线的合规性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

安全基线确保安全功能根据安全专家和系统管理员和系统管理员Windows配置。 部署后，Defender for Endpoint 安全基线将设置 Defender for Endpoint 安全控件以提供最佳保护。

若要了解安全基线以及如何使用配置文件在 Intune 上分配这些基线， [请阅读此常见问题解答](/intune/security-baselines#q--a)。

在部署和跟踪安全基线的合规性之前：

- [将设备注册到 Intune 管理](configure-machines.md#enroll-devices-to-intune-management)
- [确保您具有必要的权限](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a>比较 Microsoft Defender for Endpoint 和 Windows Intune 安全基线

Intune Windows 安全基线提供了一组全面的建议设置，用于安全配置运行 Windows 的设备，包括浏览器设置、PowerShell 设置以及某些安全功能（如 Microsoft Defender 防病毒）的设置。 相比之下，Defender for Endpoint 基线提供可优化 Defender for Endpoint 堆栈中所有安全控件的设置，包括终结点检测和响应 (EDR) 的设置以及 Windows Intune 安全基线中的设置。 有关每个基线详细信息，请参阅：

- [Windows Intune 的安全基线设置](/intune/security-baseline-settings-windows)
- [Intune 的 Microsoft Defender for Endpoint 基线设置](/intune/security-baseline-settings-defender-atp)

理想情况下，已载入 Defender for Endpoint 的设备同时部署两个基线：最初用于保护 Windows 的 Windows Intune 安全基线，然后是分层的 Defender for Endpoint 安全基线，以以最佳方式配置 Defender for Endpoint 安全控件。 若要从风险与威胁的最新数据中获益，并随着基线的不断发展最大程度地减少冲突，请始终在发布所有产品后对所有产品应用基线的最新版本。

> [!NOTE]
> Defender for Endpoint 安全基线已针对物理设备进行了优化，当前不建议在虚拟机 (VM 或 VDI) 使用。 某些基线设置可能会影响虚拟化环境的远程交互式会话。

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a>监视对 Defender for Endpoint 安全基线的合规性

设备 **配置** 管理上的安全基线 [卡](configure-machines.md)提供了已分配 Defender for Endpoint 安全基线Windows 10设备合规性的概述。

![安全基线卡。](images/secconmgmt_baseline_card.png)

*显示 Defender for Endpoint 安全基线合规性的卡片*

每台设备都给定以下状态类型之一：

- **匹配比较基准**：设备设置与基线中的所有设置匹配。
- **与基线不匹配**：至少有一个设备设置与基线不匹配。
- **错误配置**：设备上未正确配置至少一个基线设置，并且处于冲突、错误或挂起状态。
- **不适用**：设备上至少有一个基线设置不适用。

若要查看特定设备，请选择 **"在卡上** 配置安全基线"。 这会将你带去 Intune 设备管理。 从其中， **为设备的** 名称和状态选择设备状态。

> [!NOTE]
> 在设备配置管理页面上显示的聚合数据以及 Intune 中的概述屏幕上显示的聚合数据中，你可能会遇到差异。

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a>查看并分配 Microsoft Defender for Endpoint 安全基线

设备配置管理仅监视已Windows 10 Microsoft Defender 终结点安全基线的设备的基本合规性。 你可以方便地查看基线并将其分配给 Intune 设备管理上的设备。

1. 选择 **安全基线卡** 上的配置 **安全基线** 以转到 Intune 设备管理。 显示比较基准合规性的类似概述。

   > [!TIP]
   > 或者，你可以从所有服务 > Intune > 设备安全 > 安全基线 > **Microsoft Defender ATP** 基线导航到 Microsoft Azure 门户中的 Defender for Endpoint 安全基线。

2. 创建新的配置文件。

   ![Intune 上的 Microsoft Defender for Endpoint 安全基线概述。](images/secconmgmt_baseline_intuneprofile1.png)<br>
   *Intune 上的 Microsoft Defender for Endpoint 安全基线概述*

3. 创建配置文件期间，你可以查看和调整基线上的特定设置。

   ![在 Intune 上创建配置文件期间的安全基线选项。](images/secconmgmt_baseline_intuneprofile2.png)<br>
   *在 Intune 上创建配置文件期间的安全基线选项*

4. 将配置文件分配给相应的设备组。

   ![Intune 上的安全基线配置文件。](images/secconmgmt_baseline_intuneprofile3.png)<br>
   *在 Intune 上分配安全基线配置文件*

5. 创建配置文件以保存它并将其部署到分配的设备组。

   ![在 Intune 上分配安全基线。](images/secconmgmt_baseline_intuneprofile4.png)<br>
   *在 Intune 上创建安全基线配置文件*

> [!TIP]
> Intune 上的安全基线提供了一种全面保护设备的便捷方式。 [详细了解 Intune 上的安全基线](/intune/security-baselines)。

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)。

## <a name="related-topics"></a>相关主题

- [确保设备配置正确](configure-machines.md)
- [获取载入到 Microsoft Defender for Endpoint 的设备](configure-machines-onboarding.md)
- [优化 ASR 规则部署和检测](configure-machines-asr.md)
