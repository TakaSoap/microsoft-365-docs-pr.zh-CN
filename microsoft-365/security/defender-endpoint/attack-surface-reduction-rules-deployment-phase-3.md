---
title: ASR 规则部署阶段 3 - 实现
description: 提供实现攻击面减少规则部署的指南。
keywords: 攻击面减少规则部署， ASR 部署， 启用 asr 规则， 配置 ASR， 主机入侵防护系统， 保护规则， 反攻击规则， 反攻击， 攻击规则， 感染防护规则， Microsoft Defender for Endpoint， 配置 ASR 规则
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: m365solution-scenario
ms.date: 1/18/2022
ms.openlocfilehash: 75ad1b083300d9432a18a7c7a18f010f3e727126
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322855"
---
# <a name="asr-rules-deployment-phase-3-implement"></a>ASR 规则部署阶段 3：实现

实现阶段将环从测试移动到功能状态。

> [!div class="mx-imgBorder"]
> ![ASR 规则实现步骤](images/asr-rules-implementation-steps.png)

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>步骤 1：将 ASR 规则从审核转换为阻止

1. 在审核模式下确定所有排除项后，开始将某些 ASR 规则设置为"阻止"模式，从触发事件数最小的规则开始。 请参阅" [启用攻击面减少规则"](enable-attack-surface-reduction.md)。
2. 查看报告门户中的报告Microsoft 365 Defender，请参阅 [Microsoft Defender for Endpoint 中的威胁防护报告](threat-protection-reports.md)。 此外，查看来自 ASR 冠军的反馈。
3. 精简排除项或在必要时创建新的排除项。
4. 将有问题的规则切换回审核。

  >[!Note]
  >对于有问题的规则 (规则产生过多干扰) ，最好创建排除项，而不是关闭规则或切换回审核。 您必须确定最适合您的环境。

  >[!Tip]
  >如果可用，利用规则中的警告模式设置来限制中断。 在"警告"模式下启用 ASR 规则，可以捕获触发的事件并查看其潜在的中断，而不会实际阻止最终用户的访问。 了解更多信息： [为用户发出警告模式](attack-surface-reduction.md#warn-mode-for-users)。

### <a name="how-does-warn-mode-work"></a>警告模式如何工作？

警告模式实际上是阻止指令，但用户可以选择"取消阻止"给定流或应用的后续执行。 在设备、用户、文件和进程组合上取消阻止警告模式。 警告模式信息存储在本地，持续时间为 24 小时。

### <a name="step-2-expand-deployment-to-ring-n--1"></a>步骤 2：展开部署以圈 n + 1

当你确信已正确配置圈 1 的 ASR 规则时，可以将部署范围扩大到下一个圈 (n + 1) 。

每个后续圈的部署过程步骤 1 – 3 基本相同：

1. 审核中的测试规则
2. 在管理门户中查看 ASR 触发的Microsoft 365 Defender事件
3. 创建排除项
4. 查看：根据需要优化、添加或删除排除项
5. 将规则设置为"阻止"
6. 查看报告门户中的Microsoft 365 Defender页面。
7. 创建排除项。
8. 禁用有问题的规则或将其切换回审核。

#### <a name="customize-attack-surface-reduction-rules"></a>自定义减少攻击面规则

随着你继续扩展攻击面减少规则部署，你可能会发现自定义你已启用的攻击面减少规则是必要或有益。

##### <a name="exclude-files-and-folders"></a>排除文件和文件夹

你可以选择从攻击面减少规则评估中排除文件和文件夹。 排除后，即使攻击面减少规则检测到文件包含恶意行为，也不会阻止文件运行。

例如，请考虑勒索软件规则：

勒索软件规则旨在帮助企业客户降低勒索软件攻击的风险，同时确保业务连续性。 默认情况下，勒索软件规则错误应谨慎处理，并防范尚未获得足够信誉和信任的文件。 为了重新强调一下，勒索软件规则仅针对未基于数百万客户的使用情况指标获得足够正面信誉和普遍程度的文件触发。 通常，块是自行解析的，因为每个文件的"信誉和信任"值都会随着无问题使用率的增加而递增升级。

如果无法及时解决阻止问题，客户可以使用自助服务机制或基于 IOC) 的"  允许列表"功能（自行承担风险）使用自助服务机制或泄露指示器 ("允许列表"功能来取消阻止文件本身。

> [!WARNING]
> 排除或取消阻止文件或文件夹可能会允许不安全的文件运行并感染你的设备。 排除文件或文件夹可以严重削弱攻击面减少规则提供的保护。 将允许运行规则阻止的文件，并且不会记录任何报告或事件。

排除应用于允许排除的所有规则。 可以指定单个文件、文件夹路径或资源的完全限定域名。 但是，不能将排除限制到特定规则。

仅在已排除的应用程序或服务启动时应用排除。 例如，如果为已在运行的更新服务添加排除项，则更新服务将继续触发事件，直到停止并重新启动该服务。

攻击面减少支持环境变量和通配符。 有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。
如果在检测你认为不应检测到的文件的规则方面遇到问题，请使用审核模式 [测试规则](evaluate-attack-surface-reduction.md)。

有关每个 [规则的详细信息](attack-surface-reduction-rules-reference.md) ，请参阅攻击面减少规则参考主题。

##### <a name="use-group-policy-to-exclude-files-and-folders"></a>使用组策略排除文件和文件夹

1. 在组策略管理计算机上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **编辑**。

2. 在组 **策略管理编辑器中**，转到" **计算机配置"，** 然后单击" **管理模板"**。

3. 展开树以Windows **攻击Microsoft Defender 防病毒** \> **Microsoft Defender 攻击防护** \>  \> **组件**。

4. 双击"从攻击面减少规则中 **排除文件和** 路径"设置，将该选项设置为 **"已启用"**。 选择 **"显示** "，在"值名称"列中 **输入每个文件或** 文件夹。 在 **"值** " **列中为** 每个项目输入 0。

> [!WARNING]
> 请勿使用引号，因为"值名称"列或"值"列不支持 **引号**。

##### <a name="use-powershell-to-exclude-files-and-folders"></a>使用 PowerShell 排除文件和文件夹

1. 在 **"管理"中"开始"菜单 powershell**，右键单击"Windows PowerShell并选择"**以****管理员角色运行"**。

2. 输入以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    继续使用 向 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 列表中添加更多文件夹。

    > [!IMPORTANT]
    > 用于 `Add-MpPreference` 向列表中追加或添加应用。 `Set-MpPreference`使用 cmdlet 将覆盖现有列表。

##### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>使用 MDM CSP 排除文件和文件夹

使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。

##### <a name="customize-the-notification"></a>自定义通知

你可以自定义何时触发规则并阻止应用或文件的通知。 请参阅[Windows 安全中心](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)文章。

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[ASR 规则部署概述](attack-surface-reduction-rules-deployment.md)

[第 1 阶段：规划](attack-surface-reduction-rules-deployment-phase-1.md)

[第 2 截断：测试](attack-surface-reduction-rules-deployment-phase-2.md)

[第 4 阶段：投入生产](attack-surface-reduction-rules-deployment-phase-4.md)
