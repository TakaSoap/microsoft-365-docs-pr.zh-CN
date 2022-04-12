---
title: 解决 Microsoft Defender for Endpoint 中的误报/漏报
description: 了解如何处理Microsoft Defender for Endpoint中的误报或误报。
keywords: 防病毒、异常、排除、Microsoft Defender for Endpoint、误报、假负、阻止文件、阻止 URL
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.date: 12/02/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom:
- FPFN
- admindeeplinkDEFENDER
ms.openlocfilehash: d7477c2006acd04008e6cb56cb22261a4db4a92b
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789901"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a>解决 Microsoft Defender for Endpoint 中的误报/漏报

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

在终结点保护解决方案中，误报是检测到并标识为恶意的实体（例如文件或进程），即使实体实际上不是威胁。 假负值是未检测为威胁的实体，即使它实际上是恶意的。 任何威胁防护解决方案（包括[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)）都可能发生误报/负。

:::image type="content" source="images/false-positives-overview.png" alt-text="Microsoft Defender for Endpoint门户中误报和负数的定义" lightbox="images/false-positives-overview.png":::

幸运的是，可以采取措施来解决和减少此类问题。 如果在[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)中看到误报/负数，则安全操作可以使用以下过程采取措施来解决它们：

1. [查看和分类警报](#part-1-review-and-classify-alerts)
2. [查看已采取的补救措施](#part-2-review-remediation-actions)
3. [查看和定义排除项](#part-3-review-or-define-exclusions)
4. [提交实体进行分析](#part-4-submit-a-file-for-analysis)
5. [查看和调整威胁防护设置](#part-5-review-and-adjust-your-threat-protection-settings)

如果执行本文中所述的任务后仍存在误报/负数问题，则可以获得帮助。 是否 [仍需要帮助？](#still-need-help)

:::image type="content" source="images/false-positives-step-diagram.png" alt-text="解决误报和负数的步骤" lightbox="images/false-positives-step-diagram.png":::

> [!NOTE]
> 本文旨在为使用[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)的安全操作员和安全管理员提供指导。

## <a name="part-1-review-and-classify-alerts"></a>第 1 部分：查看和分类警报

如果看到由于检测到某些内容为恶意或可疑内容而触发的 [警报](alerts.md) ，则可以取消该实体的警报。 还可以抑制不一定是误报但不重要的警报。 我们建议你对警报进行分类。

管理警报并分类真/假正有助于训练威胁防护解决方案，并可随着时间的推移减少误报或误报数。 执行这些步骤还有助于降低安全操作仪表板中的噪音，以便安全团队可以专注于优先级较高的工作项。

### <a name="determine-whether-an-alert-is-accurate"></a>确定警报是否准确

对警报进行分类或取消之前，请确定警报是准确的、误报的还是良性的。

1. 转到Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中，选择 **“警报”队列**。

3. 选择警报以获取有关警报的更多详细信息。  (请参阅Microsoft Defender for Endpoint.) [中的“查看”警报](review-alerts.md)

4. 根据警报状态，执行下表中所述的步骤：

   |警报状态|需执行的操作|
   |---|---|
   |警报准确|分配警报，然后进一步[调查。](investigate-alerts.md)|
   |警报为误报|1. [将警报分类](#classify-an-alert) 为误报。<br/><br/>2. [取消警报](#suppress-an-alert)。<br/><br/>3. [为Microsoft Defender for Endpoint创建指示器](#indicators-for-microsoft-defender-for-endpoint)。<br/><br/>4. [将文件提交给 Microsoft 进行分析](#part-4-submit-a-file-for-analysis)。|
   |警报是准确的，但良性 (不重要的) |[将警报分类](#classify-an-alert) 为真正的正值，然后 [取消该警报](#suppress-an-alert)。|

### <a name="classify-an-alert"></a>对警报进行分类

警报可在Microsoft 365 Defender中归类为误报或正误报。 分类警报有助于训练Microsoft Defender for Endpoint，以便随着时间的推移，你将看到更多真实警报和更少的虚假警报。

1. 转到Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 选择 **“警报”队列**，然后选择警报。

3. 对于所选警报，请选择 **“操作** \> **管理”警报**。 随即打开浮出窗格。

4. 在 **“管理警报** ”部分中，选择 **“True 警报** ”或 **“False 警报**”。  (使用 **False 警报** 对误报进行分类。) 

> [!TIP]
> 有关禁止警报的详细信息，请参阅[管理Microsoft Defender for Endpoint警报](/microsoft-365/security/defender-endpoint/manage-alerts)。 而且，如果你的组织使用安全信息和事件管理 (SIEM) 服务器，请确保也在此处定义抑制规则。

### <a name="suppress-an-alert"></a>取消警报

如果警报要么为误报，要么是正误报，但对于不重要的事件，可以在Microsoft 365 Defender中抑制这些警报。 取消警报有助于降低安全操作仪表板中的噪音。

1. 转到Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中，选择 **“警报”队列**。

3. 选择要取消的警报以打开其 **“详细信息”** 窗格。

4. 在 **“详细信息** ”窗格中，选择省略号 (**...**) ，然后 **创建抑制规则**。

5. 指定抑制规则的所有设置，然后选择 **“保存**”。

> [!TIP]
> 需要有关抑制规则的帮助？ 请参阅 [“取消警报”并创建新的抑制规则](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)。

## <a name="part-2-review-remediation-actions"></a>第 2 部分：查看修正操作

[修正操作](manage-auto-investigation.md#remediation-actions)（例如将文件发送到隔离或停止进程）针对 (实体（例如检测为威胁的文件) ）执行。 通过自动调查和Microsoft Defender 防病毒自动执行多种类型的修正操作：

- 隔离文件
- 删除注册表项
- 终止进程
- 停止服务
- 禁用驱动程序
- 删除计划的任务

其他操作（例如启动防病毒扫描或收集调查包）会手动或通过 [实时响应](live-response.md)进行。 无法撤消通过实时响应执行的操作。

查看警报后，下一步是 [查看修正操作](manage-auto-investigation.md)。 如果由于误报而执行任何操作，则可以撤消大多数类型的修正操作。 具体而言，你可以：

- [从操作中心还原隔离的文件](#restore-a-quarantined-file-from-the-action-center)
- [一次撤消多个操作](#undo-multiple-actions-at-one-time)
- [跨多个设备从隔离区中删除文件](#remove-a-file-from-quarantine-across-multiple-devices)。 和
- [从隔离区还原文件](#restore-file-from-quarantine)

查看并撤消由于误报而执行的操作后，请继续 [查看或定义排除项](#part-3-review-or-define-exclusions)。

### <a name="review-completed-actions"></a>查看已完成的操作

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>的左侧导航窗格中，单击 **“操作中心**”。

2. 选择 **“历史记录** ”选项卡可查看已执行的操作列表。

3. 选择一个项目以查看有关所采取的修正操作的更多详细信息。

### <a name="restore-a-quarantined-file-from-the-action-center"></a>从操作中心还原隔离的文件

1. 在Microsoft 365 Defender门户的左侧导航窗格中，单击 **“操作中心**”。

2. 在“ **历史记录** ”选项卡上，选择要撤消的操作。

3. 在浮出窗格中，选择 **“撤消**”。 如果此方法无法撤消该操作，则将看不到 **“撤消”** 按钮。  (若要了解详细信息，请参阅 [撤消已完成的操作](manage-auto-investigation.md#undo-completed-actions)。) 

### <a name="undo-multiple-actions-at-one-time"></a>一次撤消多个操作

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>的左侧导航窗格中，单击 **“操作中心**”。

2. 在 **“历史记录** ”选项卡上，选择要撤消的操作。

3. 在屏幕右侧的窗格中，选择 **“撤消**”。

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a>跨多个设备从隔离区中删除文件

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/autoir-quarantine-file-1.png" alt-text="隔离文件" lightbox="images/autoir-quarantine-file-1.png":::

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>的左侧导航窗格中，单击 **“操作中心**”。

2. 在“ **历史记录** ”选项卡上，选择一个具有“操作类型 **隔离”文件的文件**。

3. 在屏幕右侧的窗格中，选择 **“应用到此文件的 X 更多实例**”，然后选择 **“撤消**”。

### <a name="restore-file-from-quarantine"></a>从隔离区还原文件

如果在调查后确定文件是干净的，则可以回滚并从隔离区中删除文件。 在隔离文件的每个设备上运行以下命令。

1. 在设备上打开提升的命令行提示符：

   1. 转到“**开始**”并键入“_cmd_”。
   2. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，然后按 **Enter**：

    ```console
    "%ProgramFiles%\Windows Defender\MpCmdRun.exe" -Restore -Name EUS:Win32/CustomEnterpriseBlock -All
    ```

    > [!IMPORTANT]
    > 在某些情况下， **ThreatName** 可能显示为 `EUS:Win32/CustomEnterpriseBlock!cl`. Defender for Endpoint 将还原过去 30 天内在此设备上隔离的所有自定义阻止文件。
    >
    > 被隔离为潜在网络威胁的文件可能无法恢复。 如果用户尝试在隔离后还原文件，则该文件可能无法访问。 这可能是由于系统不再具有访问该文件的网络凭据。 通常，这是临时登录到系统或共享文件夹的结果，并且访问令牌已过期。

3. 在屏幕右侧的窗格中，选择 **“应用到此文件的 X 更多实例**”，然后选择 **“撤消**”。

## <a name="part-3-review-or-define-exclusions"></a>第 3 部分：查看或定义排除项

排除项是指定为修正操作异常的实体，例如文件或 URL。 仍可检测到已排除的实体，但不会对该实体执行修正操作。 也就是说，检测到的文件或进程不会停止、发送到隔离区、删除或以其他方式更改Microsoft Defender for Endpoint。

若要跨Microsoft Defender for Endpoint定义排除项，请执行以下任务：

- [定义Microsoft Defender 防病毒的排除项](#exclusions-for-microsoft-defender-antivirus)
- [为Microsoft Defender for Endpoint创建“allow”指示器](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> Microsoft Defender 防病毒排除项仅适用于防病毒保护，而不适用于其他Microsoft Defender for Endpoint功能。 若要广泛排除文件，请对Microsoft Defender 防病毒使用排除项，对Microsoft Defender for Endpoint使用[自定义指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。

本部分中的过程介绍如何定义排除项和指示器。

### <a name="exclusions-for-microsoft-defender-antivirus"></a>Microsoft Defender 防病毒的排除项

通常，不应为Microsoft Defender 防病毒定义排除项。 请确保谨慎定义排除项，并且仅包含导致误报的文件、文件夹、进程和进程打开的文件。 此外，请确保定期查看定义的排除项。 建议使用[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)定义或编辑防病毒排除项;但是，可以使用其他方法，如[组策略](/azure/active-directory-domain-services/manage-group-policy) (请参阅[“管理Microsoft Defender for Endpoint](manage-mde-post-migration.md)”。

> [!TIP]
> 需要防病毒排除的帮助？ 请参阅[配置和验证Microsoft Defender 防病毒扫描的排除项](configure-exclusions-microsoft-defender-antivirus.md)。

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a>使用Microsoft Endpoint Manager管理现有策略的防病毒排除 () 

1. 转到Microsoft Endpoint Manager管理中心 () <https://endpoint.microsoft.com> 并登录。

2. 选择 **Endpoint Security** \> **防病毒**，然后选择现有策略。  (如果没有现有策略或想要创建新策略，请跳到 [下一过程](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)) 。

3. 选择 **“属性**”，选择 **“配置设置**”旁边的“ **编辑**”。

4. 展开 **Microsoft Defender 防病毒排除项**，然后指定排除项。

5. 选择 **“审阅 + 保存**”，然后选择 **“保存**”。

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a>使用Microsoft Endpoint Manager创建具有排除项的新防病毒策略

1. 转到Microsoft Endpoint Manager管理中心 () <https://endpoint.microsoft.com> 并登录。

2. 选择 **终结点安全** \> **防病毒** \> **+ 创建策略**。

3. 选择平台 (，例如 **Windows 10及更高版本**、**macOS**、**Windows 10和Windows服务器**) 。

4. 对于 **配置文件**，选择 **Microsoft Defender 防病毒排除** 项，然后选择 **“创建**”。

5. 指定配置文件的名称和说明，然后选择 **“下一步**”。

6. 在 **“配置设置”** 选项卡上，指定防病毒排除项，然后选择 **“下一步**”。

7. 在“ **作用域标记”** 选项卡上，如果在组织中使用范围标记，请为要创建的策略指定范围标记。  (查看 [Scope 标记](/mem/intune/fundamentals/scope-tags).) 

8. 在 **“分配”** 选项卡上，指定应向其应用策略的用户和组，然后选择 **“下一步**”。  (如果需要有关分配的帮助，请参阅 Microsoft Intune.[) 中分配用户和设备配置文件](/mem/intune/configuration/device-profile-assign)

9. 在 **“审阅 + 创建** ”选项卡上，查看设置，然后选择 **“创建**”。

### <a name="indicators-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint指示器

[具体](/microsoft-365/security/defender-endpoint/manage-indicators) (指标、入侵指标或 IoC) 使安全运营团队能够定义实体的检测、预防和排除。 例如，可以在Microsoft Defender for Endpoint中指定要从扫描和修正操作中省略的某些文件。 或者，指示器可用于为某些文件、IP 地址或 URL 生成警报。

若要将实体指定为Microsoft Defender for Endpoint的排除项，请为这些实体创建“allow”指示器。 Microsoft Defender for Endpoint中的这种“允许”指标适用于[下一代保护](microsoft-defender-antivirus-in-windows-10.md)、[终结点检测和响应](overview-endpoint-detection-response.md)和[自动调查&修正](/microsoft-365/security/defender-endpoint/automated-investigations)。

可以为以下项创建“允许”指示器：

- [Files](#indicators-for-files)
- [IP 地址、URL 和域](#indicators-for-ip-addresses-urls-or-domains)
- [应用程序证书](#indicators-for-application-certificates)

:::image type="content" source="images/false-positives-indicators.png" alt-text="指示器类型" lightbox="images/false-positives-indicators.png":::

#### <a name="indicators-for-files"></a>文件指示器

[为文件（如可执行文件）创建“允许”指示器](/microsoft-365/security/defender-endpoint/indicator-file)时，它有助于防止组织正在使用的文件被阻止。 文件可以包括可移植的可执行文件 (PE) 文件，例如`.exe`文件。`.dll`

在为文件创建指示器之前，请确保满足以下要求：

- Microsoft Defender 防病毒配置了启用了基于云的保护 (请参阅[管理基于云的保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)) 
- 反恶意软件客户端版本为 4.18.1901.x 或更高版本
- 设备运行Windows 10版本 1703 或更高版本，或Windows 11;Windows Server 2016或 Windows Server 2019 或 Windows Server 2022
- [启用“阻止”或“允许”功能](/microsoft-365/security/defender-endpoint/advanced-features)

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a>IP 地址、URL 或域的指示器

[为 IP 地址、URL 或域创建“允许”指示器时，](/microsoft-365/security/defender-endpoint/indicator-ip-domain)它有助于防止组织使用的网站或 IP 地址被阻止。

在为 IP 地址、URL 或域创建指示器之前，请确保满足以下要求：

- Defender for Endpoint 中的网络保护在阻止模式下启用， (请参阅 [“启用网络保护](/microsoft-365/security/defender-endpoint/enable-network-protection)) 
- 反恶意软件客户端版本为 4.18.1906.x 或更高版本
- 设备运行Windows 10版本 1709 或更高版本，或Windows 11

自定义网络指示器在[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)中打开。 若要了解详细信息，请参阅 [高级功能](/microsoft-365/security/defender-endpoint/advanced-features)。

#### <a name="indicators-for-application-certificates"></a>应用程序证书的指示器

[为应用程序证书创建“允许”指示器](/microsoft-365/security/defender-endpoint/indicator-certificates)时，它有助于防止组织使用的应用程序（例如内部开发的应用程序）被阻止。 `.CER` 支持或 `.PEM` 支持文件扩展名。

在为应用程序证书创建指示器之前，请确保满足以下要求：

- Microsoft Defender 防病毒配置了启用了基于云的保护 (请参阅[管理基于云的保护](deploy-manage-report-microsoft-defender-antivirus.md)
- 反恶意软件客户端版本为 4.18.1901.x 或更高版本
- 设备运行Windows 10版本 1703 或更高版本，或Windows 11;Windows Server 2016或 Windows Server 2019 或 Windows Server 2022
- 病毒和威胁防护定义是最新的

> [!TIP]
> 创建指示器时，可以逐个定义指示器，也可以一次性导入多个项。 请记住，单个租户的限制为 15，000 个指标。 并且，可能需要先收集某些详细信息，例如文件哈希信息。 在 [创建指示器](manage-indicators.md)之前，请务必查看先决条件。

## <a name="part-4-submit-a-file-for-analysis"></a>第 4 部分：提交文件进行分析

可以将实体（如文件和无文件检测）提交给 Microsoft 进行分析。 Microsoft 安全研究人员分析所有提交，其结果有助于告知Microsoft Defender for Endpoint威胁防护功能。 在提交网站登录时，可以跟踪提交。

### <a name="submit-a-file-for-analysis"></a>提交文件进行分析

如果文件被错误地检测为恶意或丢失，请按照以下步骤提交文件进行分析。

1. 请查看此处的准则： [提交文件进行分析](/windows/security/threat-protection/intelligence/submission-guide)。

2. [请访问Microsoft 安全智能提交网站](https://www.microsoft.com/wdsi/filesubmission) (https://www.microsoft.com/wdsi/filesubmission)，并提交文件 () 。

### <a name="submit-a-fileless-detection-for-analysis"></a>提交无文件检测以进行分析

如果检测到某些内容是基于行为的恶意软件，而你没有文件，则可以提交 `Mpsupport.cab` 文件进行分析。 可以在 *Windows 10或Windows 11* 上使用 Microsoft 恶意软件保护Command-Line实用工具 (MPCmdRun.exe) 工具获取.cab文件。

1. 转到 ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`，然后以管理员身份运行 `MpCmdRun.exe` 。

2. 键 `mpcmdrun.exe -GetFiles`入，然后按 **Enter**。

   将生成包含各种诊断日志的.cab文件。 文件的位置在命令提示符的输出中指定。 默认情况下，位置为 `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.

3. 请查看此处的准则： [提交文件进行分析](/windows/security/threat-protection/intelligence/submission-guide)。

4. [请访问Microsoft 安全智能提交网站](https://www.microsoft.com/wdsi/filesubmission) (https://www.microsoft.com/wdsi/filesubmission)，并提交.cab文件。

### <a name="what-happens-after-a-file-is-submitted"></a>提交文件后会发生什么情况？

甚至在分析师开始处理你的案例之前，系统会立即扫描你的提交，以便你做出最新决定。 一个文件可能已经由分析师提交和处理。 在这些情况下，可以快速做出决定。

对于尚未处理的提交，将按如下所示对它们进行分析的优先级：

- 可能会影响大量计算机的常见文件的优先级更高。
- 经过身份验证的客户，尤其是具有有效 [软件保障 ID (SAID) ](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)的企业客户，优先级更高。
- 被 SAID 持有者标记为高优先级的提交会立即得到关注。

若要检查有关提交的更新，请在[Microsoft 安全智能提交站点](https://www.microsoft.com/wdsi/filesubmission)登录。

> [!TIP]
> 若要了解详细信息，请参阅 [“提交文件”进行分析](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)。

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a>第 5 部分：查看和调整威胁防护设置

Microsoft Defender for Endpoint提供了各种选项，包括能够微调各种功能的设置。 如果收到大量误报，请务必查看组织的威胁防护设置。 可能需要对以下项进行一些调整：

- [云传递的保护](#cloud-delivered-protection)
- [针对可能不需要的应用程序的修正](#remediation-for-potentially-unwanted-applications)
- [自动调查和修正](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a>云端保护

检查云提供的保护级别以获取Microsoft Defender 防病毒。 默认情况下，云传递的保护设置为 **“未配置**”，这与大多数组织的正常保护级别相对应。 如果云提供的保护设置为 **“高**”、“ **高 +**”或 **“零”容错**，则可能会遇到较高的误报数。

> [!TIP]
> 若要详细了解如何配置云提供的保护，请 [参阅指定云提供的保护级别](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)。

建议使用[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)编辑或设置云提供的保护设置;但是，可以使用其他方法，如[组策略](/azure/active-directory-domain-services/manage-group-policy) (请参阅[“管理Microsoft Defender for Endpoint](manage-mde-post-migration.md)”。

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a>使用Microsoft Endpoint Manager查看和编辑现有策略的云提供的保护设置 () 

1. 转到Microsoft Endpoint Manager管理中心 () <https://endpoint.microsoft.com> 并登录。

2. 选择 **终结点安全** \> **防病毒，** 然后选择现有策略。  (如果没有现有策略或想要创建新策略，请跳到 [下一过程](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)) 。

3. 在 **“管理”** 下，选择 **“属性**”。 然后，在 **“配置设置”** 旁边选择 **“编辑**”。

4. 展开 **云保护**，并查看 **云提供的保护级别** 行中的当前设置。 建议将云提供的保护设置为 **“未配置**”，这可提供强大的保护，同时减少误报的可能性。

5. 选择 **“审阅 + 保存**”，然后 **保存**。

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a>使用Microsoft Endpoint Manager为新策略设置云提供的保护设置 () 

1. 转到Microsoft Endpoint Manager管理中心 () <https://endpoint.microsoft.com> 并登录。

2. 选择 **终结点安全** \> **防病毒** \> **+ 创建策略**。

3. 对于 **平台**，请选择一个选项，然后选择 **“配置文件**”，选择 **“防病毒**”或 **“Microsoft Defender 防病毒** (特定选项取决于你为 **Platform**.) 选择”**创建**“的内容。

4. 在 **“基本信息** ”选项卡上，指定策略的名称和说明。 然后选择“**下一步**”。

5. 在“ **配置设置”** 选项卡上，展开 **云保护**，并指定以下设置：

   - 将 **启用云提供的保护** 设置为 **“是**”。
   - 将“**云端保护级别**”设为“**未配置**”。  (默认情况下，此级别提供很强的保护级别，同时减少了误报的可能性。) 

6. 在“ **作用域标记”** 选项卡上，如果在组织中使用范围标记，请为策略指定范围标记。  (查看 [Scope 标记](/mem/intune/fundamentals/scope-tags).) 

7. 在 **“分配”** 选项卡上，指定应向其应用策略的用户和组，然后选择 **“下一步**”。  (如果需要有关分配的帮助，请参阅 Microsoft Intune.[) 中分配用户和设备配置文件](/mem/intune/configuration/device-profile-assign)

8. 在 **“审阅 + 创建** ”选项卡上，查看设置，然后选择 **“创建**”。

### <a name="remediation-for-potentially-unwanted-applications"></a>针对可能不需要的应用程序的修正

PUA)  (可能不需要的应用程序是一类软件，可能导致设备运行缓慢、显示意外广告或安装其他可能意外或不需要的软件。 PUA 的示例包括广告软件、捆绑软件以及规避与安全产品行为不同的软件。 虽然 PUA 不被视为恶意软件，但某些类型的软件是基于其行为和信誉的 PUA。

> [!TIP]
> 若要了解有关 PUA 的详细信息，请 [参阅“检测”并阻止可能不需要的应用程序](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。

根据组织使用的应用，由于 PUA 保护设置，可能会出现误报。 如有必要，请考虑在审核模式下运行 PUA 保护一段时间，或将 PUA 保护应用到组织中的一部分设备。 可以为Microsoft Edge浏览器和Microsoft Defender 防病毒配置 PUA 保护。

建议使用[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)编辑或设置 PUA 保护设置;但是，可以使用其他方法，如[组策略](/azure/active-directory-domain-services/manage-group-policy) (请参阅[“管理Microsoft Defender for Endpoint](manage-mde-post-migration.md)”。

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a>使用Microsoft Endpoint Manager编辑现有配置文件的 PUA 保护 () 

1. 转到Microsoft Endpoint Manager管理中心 () <https://endpoint.microsoft.com> 并登录。

2. 选择 **“设备** \> **配置文件**”，然后选择现有策略。  (如果没有现有策略或想要创建新策略，请跳到 [下一个过程](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile)。) 

3. 在 **“管理”** 下，选择 **“属性**”，然后在 **“配置设置**”旁边选择 **“编辑**”。

4. 在“**配置设置”** 选项卡上，向下滚动并展开 **Microsoft Defender 防病毒**。

5. 将 **检测可能不需要的应用程序** 设置为 **审核**。  (你可以将其关闭，但通过使用审核模式，你将能够看到检测。) 

6. 选择 **“审阅 + 保存**”，然后选择 **“保存**”。

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a>使用Microsoft Endpoint Manager为新的配置文件设置 PUA 保护 () 

1. 转到Microsoft Endpoint Manager管理中心 () <https://endpoint.microsoft.com> 并登录。

2. 选择 **“设备** \> **配置文件** \> **+ 创建配置文件**”。

3. 对于 **平台**，请选择 **Windows 10和更高版本**，对于 **配置文件**，请选择 **“设备限制**”。

4. 在 **“基本信息”** 选项卡上，指定策略的名称和说明。 然后选择“**下一步**”。

5. 在“**配置设置”** 选项卡上，向下滚动并展开 **Microsoft Defender 防病毒**。

6. 将 **检测可能不需要的应用程序** 设置为 **审核**，然后选择 **“下一步**”。  (可以关闭 PUA 保护，但通过使用审核模式，你将能够看到检测。) 

7. 在 **“分配”** 选项卡上，指定应向其应用策略的用户和组，然后选择 **“下一步**”。  (如果需要有关分配的帮助，请参阅 Microsoft Intune.[) 中分配用户和设备配置文件](/mem/intune/configuration/device-profile-assign)

8. 在 **“适用性规则”** 选项卡上，指定要包括或排除在策略中的 OS 版本或版本。 例如，可以将策略设置为应用于特定版本Windows 10的所有设备。 然后选择“**下一步**”。

9. 在 **“审阅 + 创建** ”选项卡上，查看设置，然后选择 **“创建**”。

### <a name="automated-investigation-and-remediation"></a>自动调查和修复

[自动调查和修正](automated-investigations.md) (AIR) 功能旨在检查警报并立即采取措施解决违规问题。 触发警报并运行自动调查时，将为所调查的每一份证据生成一个判决。 判决可能为 *恶意*、 *可疑* 或 *未发现任何威胁*。

根据组织的 [自动化设置级别](/microsoft-365/security/defender-endpoint/automation-levels) 和其他安全设置，对被视为 *恶意* 或 *可疑* 的项目执行修正操作。 在某些情况下，会自动执行修正操作;在其他情况下，补救措施是手动或仅在安全运营团队批准后才执行的。

- [详细了解自动化级别](/microsoft-365/security/defender-endpoint/automation-levels);然后
- [在 Defender for Endpoint 中配置 AIR 功能](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation)。

> [!IMPORTANT]
> 建议使用 *完全自动化* 进行自动调查和修正。 不要因为误报而关闭这些功能。 相反，使用 [“允许”指示器定义异常](#indicators-for-microsoft-defender-for-endpoint)，并使自动调查和修正设置为自动执行适当的操作。 遵循 [本指南](automation-levels.md#levels-of-automation) 有助于减少安全操作团队必须处理的警报数。

## <a name="still-need-help"></a>仍然需要帮助？

如果已完成本文中的所有步骤，但仍需要帮助，请联系技术支持人员。

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>并登录。

2. 在右上角，选择问号 (**？**) ，然后选择 **Microsoft 支持**。

3. 在 **“支持助手** ”窗口中，描述你的问题，然后发送消息。 可以从那里打开服务请求。

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

[管理Microsoft Defender for Endpoint](manage-mde-post-migration.md)

[Microsoft 365 Defender门户概述](/microsoft-365/security/defender-endpoint/use)
