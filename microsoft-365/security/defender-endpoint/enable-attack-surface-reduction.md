---
title: 启用攻击面减少规则
description: 启用攻击面 (ASR) 规则，以保护你的设备免受使用宏、脚本和常见注入技术的攻击。
keywords: 攻击面减少， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， 启用， 打开
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 7aeda679d5ce350ef64a2758359390adc4a280f0
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939238"
---
# <a name="enable-attack-surface-reduction-rules"></a>启用攻击面减少规则

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[攻击面减少规则](attack-surface-reduction.md) (ASR 规则) 有助于防止恶意软件经常滥用以损害设备和网络的操作。 你可以为运行以下任一版本的 Windows 的设备设置 ASR 规则：
- Windows 10 专业 [版版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本
- Windows 10 企业版 [版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本
- Windows Server [版本 1803 (半年 ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 频道) 或更高版本
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

**要求** 你可以为运行以下任一版本的 Windows 的设备设置攻击面减少规则：

- Windows 10 专业版版本 1709 或更高版本
- Windows 10 企业版版本 1709 或更高版本
- Windows Server 版本 1803 (半年频道) 或更高版本
- Windows Server 2019

尽管攻击面减少规则不需要 Windows E5 许可证，但如果拥有 Windows E5，则获得高级管理功能。 这些功能仅在 Windows E5 中可用，包括 Defender for Endpoint 中提供的监视、分析和工作流，以及 Microsoft 365 安全中心中的报告和配置功能。 这些高级功能不适用于 Windows Professional 或 Windows E3 许可证;但是，如果你有这些许可证，可以使用事件查看器和 Microsoft Defender 防病毒日志查看攻击面减少规则事件。

每个 ASR 规则包含四个设置之一：

- **未配置**：禁用 ASR 规则
- **阻止**：启用 ASR 规则
- **审核**：评估 ASR 规则在启用后对组织的影响
- **警告**：启用 ASR 规则，但允许最终用户绕过阻止

> [!IMPORTANT]
> 目前，在 Microsoft Endpoint Manager 和 MEM 管理器中配置 ASR 规则时，三个 ASR 规则不支持 (模式) 。 若要了解更多信息，请参阅 [不支持警告模式的情况](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。

强烈建议你将 ASR 规则与 Windows E5 许可证 (或类似的许可 SKU) 一同使用，以利用适用于 Endpoint (Defender for Endpoint) 的 [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) 中提供的高级监视和报告功能。 但是，对于无法访问高级监视和报告功能的其他许可证（如 Windows Professional 或 E3），可以在触发 AS (R 规则时在每个终结点生成的事件（如事件转发) ）上开发自己的监视和报告工具。

> [!TIP]
> 若要了解有关 Windows 许可的更多信息，请参阅 [Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 许可并获取 [适用于 Windows 10 的批量许可指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。

可以使用以下任一方法启用攻击面减少规则：

- [Microsoft Intune](#intune)
- [移动设备管理 (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [组策略](#group-policy)
- [PowerShell](#powershell)

建议使用企业级管理，如 Intune 或 Microsoft Endpoint Manager。 启动时，企业级管理将覆盖任何冲突的组策略或 PowerShell 设置。

## <a name="exclude-files-and-folders-from-asr-rules"></a>从 ASR 规则中排除文件和文件夹

你可以排除大多数攻击面减少规则评估的文件和文件夹。 这意味着，即使 ASR 规则确定文件或文件夹包含恶意行为，它将不会阻止文件运行。 这可能会允许不安全的文件运行并感染你的设备。

通过允许指定的 Defender for Endpoint 文件和证书指示器，还可以从基于证书和文件哈希触发的 ASR 规则排除。  (请参阅 [管理指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).) 

> [!IMPORTANT]
> 排除文件或文件夹会大大降低 ASR 规则所提供的保护。 将允许运行排除的文件，并且不会记录任何报告或事件。
> 如果 ASR 规则正在检测你认为不应检测的文件，应首先使用审核模式 [测试规则](evaluate-attack-surface-reduction.md)。


可以使用文件夹路径或完全限定的资源 (指定单个文件或文件夹) ，但无法指定排除项应用于的规则。 仅在已排除的应用程序或服务启动时应用排除。 例如，如果为已在运行的更新服务添加排除项，则更新服务将继续触发事件，直到停止并重新启动该服务。

ASR 规则支持环境变量和通配符。 有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。

以下用于启用 ASR 规则的过程包括有关如何排除文件和文件夹的说明。

## <a name="intune"></a>Intune

1. 选择 **设备配置文件**  >  。 选择现有的终结点保护配置文件或创建新的终结点保护配置文件。 若要创建新的配置文件，请选择" **创建配置文件** "并为此配置文件输入信息。 对于 **"配置文件类型"，** 选择"**终结点保护"。** 如果已选择现有配置文件，请选择"**属性"，** 然后选择"设置 **"。**

2. 在终结点 **保护窗格中，** 选择Windows Defender **攻击防护"，** 然后选择攻击 **面减少**。 选择每个 ASR 规则所需的设置。

3. 在 **"攻击面减少异常"** 下，输入单个文件和文件夹。 还可以选择导入 **以** 导入 CSV 文件，其中包含要从 ASR 规则中排除的文件和文件夹。 CSV 文件的每一行的格式应如下所示：

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 在 **三** 个配置窗格中选择"确定"。 然后，**如果要** 创建新的终结点保护文件，请选择"创建";如果要编辑现有终结点保护文件，请选择"保存"。

## <a name="mdm"></a>MDM

使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 配置服务提供程序 (CSP) 单独启用和设置每个规则的模式。

下面是使用 ASR 规则的 [GUID 值进行引用的示例](attack-surface-reduction.md#attack-surface-reduction-rules)。

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

在审核模式下 (阻止) 、禁用、警告或启用的值为：

- 0 ：禁用 (禁用 ASR 规则) 
- 1：阻止 (启用 ASR 规则) 
- 2：审核 (评估 ASR 规则在启用后对组织) 
- 6：警告 (启用 ASR 规则，但允许最终用户绕过阻止) 。 警告模式现在适用于大多数 ASR 规则。

使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。

示例：

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> 请务必输入不带空格的 OMA-URI 值。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. 在 Microsoft Endpoint Configuration Manager 中，转到 **"资产和** 合规性  >  **Endpoint Protection**  >  **Windows Defender攻击防护"。**

2. 选择 **"主页**  >  **创建攻击防护策略"。**

3. 输入名称和说明，选择攻击 **面** 减少，然后选择下一 **步**。

4. 选择将阻止或审核操作的规则，然后选择下一 **步**。

5. 查看设置，然后选择" **下一** 步"以创建策略。

6. 创建策略后 **，关闭**。

## <a name="group-policy"></a>组策略

> [!WARNING]
> 如果使用 Intune、Configuration Manager 或其他企业级管理平台管理计算机和设备，则管理软件将在启动时覆盖任何冲突的组策略设置。

1. 在组策略管理计算机上，打开组 [策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象， **然后选择编辑**。

2. 在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。

3. 将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒** Microsoft Defender  >  **攻击防护**  >  **攻击面减少**。

4. 选择 **配置攻击面减少规则，** 然后选择 **已启用。** 然后，您可以为选项部分的每个规则设置单个状态。

   选择 **"显示..."，** 在"值名称"列中输入规则 ID，在"值"列中输入 **所选状态**，如下所示：

   - 0 ：禁用 (禁用 ASR 规则) 
   - 1：阻止 (启用 ASR 规则) 
   - 2：审核 (评估 ASR 规则在启用后对组织) 
   - 6： (启用 ASR 规则，但允许最终用户绕过阻止) 

   :::image type="content" source="images/asr-rules-gp.png" alt-text="组策略中的 ASR 规则":::

5. 若要从 ASR 规则中排除文件和文件夹，请选择"从攻击 **面** 减少规则中排除文件和路径"设置，将选项设置为 **"已启用"。** 选择 **"显示** "，在"值名称"列中 **输入每个文件或** 文件夹。 在"值"**列中为** 每个项目输入 **0。**

   > [!WARNING]
   > 请勿使用引号，因为"值名称"列或"值"列不支持 **引号**。

## <a name="powershell"></a>PowerShell

> [!WARNING]
> 如果使用 Intune、Configuration Manager 或其他企业级管理平台管理计算机和设备，则管理软件将在启动时覆盖任何冲突的 PowerShell 设置。 若要允许用户使用 PowerShell 定义值，请使用管理平台中规则的"用户定义"选项。

1. 在 **"开始"菜单中键入 powershell，** 右 **键单击**"Windows PowerShell并选择"以 **管理员角色运行"。**

2. 键入以下 cmdlet：

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    若要在审核模式下启用 ASR 规则，请使用以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    若要在警告模式下启用 ASR 规则，请使用以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    若要关闭 ASR 规则，请使用以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > 必须单独为每个规则指定状态，但可以在逗号分隔列表中组合规则和状态。
    >
    > 在下面的示例中，将启用前两个规则，第三个规则将被禁用，第四个规则将在审核模式下启用：
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    您还可以使用 `Add-MpPreference` PowerShell 谓词将新规则添加到现有列表中。

    > [!WARNING]
    > `Set-MpPreference` 将始终覆盖现有的规则集。 如果要添加到现有集合，请改为 `Add-MpPreference` 使用 。
    > 可以使用 获取规则列表及其当前状态 `Get-MpPreference` 。

3. 若要从 ASR 规则中排除文件和文件夹，请使用以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    继续使用 向 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 列表中添加更多文件和文件夹。

    > [!IMPORTANT]
    > 用于 `Add-MpPreference` 向列表中追加或添加应用。 使用 `Set-MpPreference` cmdlet 将覆盖现有列表。

## <a name="related-articles"></a>相关文章

- [使用攻击面减少规则减少攻击面](attack-surface-reduction.md)

- [评估攻击面减少](evaluate-attack-surface-reduction.md)

- [关于减少攻击面的常见问题解答](attack-surface-reduction.md)
