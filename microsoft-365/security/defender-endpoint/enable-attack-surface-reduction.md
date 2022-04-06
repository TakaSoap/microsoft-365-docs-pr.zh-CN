---
title: 启用攻击面减少规则
description: 启用攻击面减少 (ASR) 规则，以保护设备免受使用宏、脚本和常见注入技术的攻击。
keywords: 攻击面减少， 臀部， 主机入侵预防系统， 保护规则， 反开发， 反开发， 开发， 感染预防， 启用， 打开
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.date: 1/18/2022
ms.openlocfilehash: f8f6865bc65662cbbfd5a9276d95abc405f5a64b
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664229"
---
# <a name="enable-attack-surface-reduction-rules"></a>启用攻击面减少规则

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

[攻击面减少规则](attack-surface-reduction.md) (ASR 规则) 有助于防止恶意软件经常滥用以危害设备和网络的操作。

## <a name="requirements"></a>Requirements

跨Windows版本的攻击面减少功能

可以为运行以下任一版本和版本Windows的设备设置攻击面减少规则：

- Windows 10 专业版[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本
- Windows 10 企业版[版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) 或更高版本
- Windows服务器版本 [1803 (半年频道) ](/windows-server/get-started/whats-new-in-windows-server-1803)或更高版本
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2012 R2](/windows/win32/srvnodes/what-s-new-for-windows-server-2012-r2)
- Windows Server 2022

若要使用整个功能集的攻击面减少规则，需要：

- Windows Defender 防病毒作为主 AV () 的实时保护
- 云[传送保护](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) (某些规则要求) 
- Windows 10 企业版 E5 或 E3 许可证

尽管攻击面减少规则不需要[Windows E5 许可证](/windows/deployment/deploy-enterprise-licenses)，但具有 Windows E5 许可证，你可获得高级管理功能，包括 Defender for Endpoint 中提供的监视、分析和工作流，以及<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>中的报表和配置功能。 这些高级功能不适用于 E3 许可证，但你仍然可以使用事件查看器来查看攻击面减少规则事件。

每个 ASR 规则包含四个设置之一：

- **未配置** | **已禁** 用：禁用 ASR 规则
- **阻止**：启用 ASR 规则
- **审核**：评估 ASR 规则在启用后对组织的影响
- **警告**：启用 ASR 规则，但允许最终用户绕过块

> [!IMPORTANT]
> 当前，在 MICROSOFT ENDPOINT MANAGER (MEM) 中配置 ASR 规则时，三个 ASR 规则不支持警告模式。 若要了解详细信息，请参阅 [不支持警告模式的情况](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。

建议将 ASR 规则与 Windows E5 许可证 (或类似的许可 SKU) 配合使用，以利用 [Microsoft Defender for Endpoint (](microsoft-defender-endpoint.md) Defender for Endpoint) 中提供的高级监视和报告功能。 但是，如果你有另一个许可证（例如Windows Professional或Windows E3，但不包括高级监视和报告功能，则可以根据触发 ASR 规则时在每个终结点上生成的事件（例如事件转发 () ）开发自己的监视和报告工具。

> [!TIP]
> 若要详细了解Windows许可，请[参阅Windows 10许可](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5)并获取[Windows 10批量许可指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。

可以使用以下任一方法启用攻击面减少规则：

- [Microsoft Intune](#intune)
- [移动设备管理 (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [组策略](#group-policy)
- [PowerShell](#powershell)

建议Enterprise级管理，例如Intune或Microsoft Endpoint Manager。 Enterprise级管理将覆盖启动时任何冲突组策略或 PowerShell 设置。

## <a name="exclude-files-and-folders-from-asr-rules"></a>从 ASR 规则中排除文件和文件夹

可以排除大多数攻击面减少规则评估的文件和文件夹。 这意味着，即使 ASR 规则确定文件或文件夹包含恶意行为，也不会阻止文件运行。 这可能会允许不安全文件运行并感染设备。

还可以通过允许指定的 Defender for Endpoint 文件和证书指示器，从基于证书和文件哈希的触发中排除 ASR 规则。  (请参阅 [管理指示器](manage-indicators.md).) 

> [!IMPORTANT]
> 排除文件或文件夹可能会严重减少 ASR 规则提供的保护。 将允许运行排除的文件，并且不会记录任何报表或事件。
> 如果 ASR 规则检测到你认为不应检测到的文件，则应 [先使用审核模式来测试规则](evaluate-attack-surface-reduction.md)。

可以使用文件夹路径或完全限定的资源名称) 指定单个文件或文件夹 (，但不能指定排除项适用的规则。 仅当已排除的应用程序或服务启动时才应用排除项。 例如，如果为已运行的更新服务添加排除项，更新服务将继续触发事件，直到服务停止并重新启动。

ASR 规则支持环境变量和通配符。 有关使用通配符的信息，请参阅 [文件名和文件夹路径或扩展排除列表中的使用通配符](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。

## <a name="policy-conflict"></a>策略冲突

1. 如果通过 MDM 和 GP 应用冲突策略，则从 MDM 应用的设置优先。

2. MEM 托管设备的攻击面减少规则现在支持从不同策略合并设置的行为，以便为每个设备创建策略的超集。 仅合并不冲突的设置，而冲突的设置不会添加到规则的超集。 以前，如果两个策略包含单个设置的冲突，则两个策略都标记为处于冲突状态，并且不会部署任一配置文件中的设置。 攻击面减少规则合并行为如下所示：
   - 针对应用规则的每个设备评估以下配置文件中的攻击面减少规则：
     - 设备>配置策略> Endpoint protection 配置文件> **Microsoft Defender 攻击防护** > [Attack Surface Reduction](/mem/intune/protect/endpoint-protection-windows-10#attack-surface-reduction-rules)。
     - 终结点安全> **攻击面减少策略** > [Attack 表面减少规则](/mem/intune/protect/endpoint-security-asr-policy#devices-managed-by-intune)。
     - Microsoft **Defender ATP BaselineAttack** >  [Surface Reduction Rules](/mem/intune/protect/security-baseline-settings-defender-atp#attack-surface-reduction-rules) >终结点安全>安全基线。
   - 没有冲突的设置会添加到设备的超集策略中。
   - 当两个或多个策略具有冲突设置时，冲突设置不会添加到合并的策略中，而不冲突的设置将添加到适用于设备的超集策略中。
   - 只有冲突设置的配置才会被搁置。

## <a name="configuration-methods"></a>配置方法

本部分提供以下配置方法的配置详细信息：

- [Intune](#intune)
- [MEM](#mem)
- [MDM](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [组策略](#group-policy)
- [PowerShell](#powershell)

以下启用 ASR 规则的过程包括有关如何排除文件和文件夹的说明。

### <a name="intune"></a>Intune

#### <a name="device-configuration-profiles"></a>设备配置文件

1. 选择 **设备配置** \> **文件**。 选择现有的终结点保护配置文件或创建新的终结点保护配置文件。 若要创建新配置文件，请选择 **"创建配置文件** "并输入此配置文件的信息。 对于 **配置文件类型**，请选择 **"终结点保护**"。 如果已选择现有配置文件，请选择 **"属性**"，然后选择 **设置**。

2. 在 **"终结点保护**"窗格中，选择 **Windows Defender攻击防护**，然后选择 **"攻击面减少**"。 为每个 ASR 规则选择所需的设置。

3. 在 **攻击面减少异常** 下，输入单个文件和文件夹。 还可以选择" **导** 入"以导入包含要从 ASR 规则中排除的文件和文件夹的 CSV 文件。 CSV 文件中的每个行的格式应如下所示：

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 在三个配置窗格中选择 **"确定** "。 如果要创建新的终结点保护文件，请选择 **"创建** "，如果正在编辑现有终结点保护文件，请 **选择"保存** "。

#### <a name="endpoint-security-policy"></a>终结点安全策略**

1. 选择 **"终结点安全** \> **攻击面减少**"。 选择现有的 ASR 规则或创建新的 ASR 规则。 若要创建新策略，请选择 **"创建** 策略"并输入此配置文件的信息。 对于 **配置文件类型**，请选择 **攻击面减少规则**。 如果已选择现有配置文件，请选择 **"属性**"，然后选择 **设置**。

2. 在 **"配置设置"** 窗格中，选择 **"攻击面减少** "，然后为每个 ASR 规则选择所需的设置。

3. 在 **需要保护的其他文件夹列表** 下， **列出有权访问受保护文件夹的应用**， **以及从攻击面减少规则中排除文件和路径**，输入单个文件和文件夹。 还可以选择" **导** 入"以导入包含要从 ASR 规则中排除的文件和文件夹的 CSV 文件。 CSV 文件中的每个行的格式应如下所示：

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 在三个配置窗格中选择 **"下一步** "，然后在创建新策略时选择 **"创建** "，如果正在编辑现有策略，则选择 **"保存** "。

### <a name="mem"></a>MEM

可以使用 Microsoft Endpoint Manager (MEM) OMA-URI 来配置自定义 ASR 规则。 以下过程使用规则 [阻止滥用被利用的易受攻击的签名驱动程序](attack-surface-reduction-rules-reference.md#block-abuse-of-exploited-vulnerable-signed-drivers) 作为示例。

1. 打开 Microsoft Endpoint Manager (MEM) 管理中心。 在 **"主页** "菜单中，单击  **"设备**"，选择 **"配置文件**"，然后单击 **"创建配置文件**"。

   > [!div class="mx-imgBorder"]
   >  :::image type="content" source="images/mem01-create-profile.png" alt-text="Microsoft Endpoint Manager管理中心门户中的&quot;创建配置文件&quot;页" lightbox="images/mem01-create-profile.png":::

2. 在 **"创建配置文件**"中，在以下两个下拉列表中，选择以下内容：

   - 在 **平台** 中，选择 **Windows 10及更高版本**
   - 在 **配置文件类型** 中，选择 **模板**
   - 如果已通过终结点安全性设置 ASR 规则，请在 **配置文件类型** 中选择 **设置目录**。

   选择 **"自定义**"，然后选择 **"创建**"。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem02-profile-attributes.png" alt-text="Microsoft Endpoint Manager管理中心门户中的规则配置文件属性" lightbox="images/mem02-profile-attributes.png":::

3. 自定义模板工具将打开到步骤 **1 基础知识**。 在 **1 个基本信息** 中，在 **"名称**"中，键入模板的名称，在 **"说明** "中，可以键入说明 (可选) 。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem03-1-basics.png" alt-text="Microsoft Endpoint Manager管理中心门户中的基本属性" lightbox="images/mem03-1-basics.png":::

4. 单击“**下一步**”。 将打开步骤 **2 配置设置** 。 对于 OMA-URI 设置，请单击 **"添加**"。 现在将显示两个选项： **添加** 和 **导出**。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem04-2-configuration-settings.png" alt-text="Microsoft Endpoint Manager管理中心门户中的配置设置" lightbox="images/mem04-2-configuration-settings.png":::

5. 再次单击 **"添加** "。 **"添加行 OMA-URI"设置** 打开。 在 **"添加行**"中，执行以下操作：

   - 在 **"名称"** 中，键入规则的名称。
   - 在 **"说明"** 中，键入简要说明。
   - 在 **OMA-URI** 中，键入或粘贴要添加的规则的特定 OMA-URI 链接。 请参阅本文中的 MDM 部分，了解要用于此示例规则的 OMA-URI。 有关攻击面减少规则 GUIDS，请参阅主题中的 [按规则说明](attack-surface-reduction-rules-reference.md#per-rule-descriptions) ：攻击面减少规则。
   - 在 **"数据"类型** 中，选择 **"字符串**"。
   - 在 **Value** 中，键入或粘贴 GUID 值、 \= 符号和无空格的状态值 (_GUID=StateValue_) 。 其中：

     - 0：禁用 (禁用 ASR 规则) 
     - 1：阻止 (启用 ASR 规则) 
     - 2：审核 (评估 ASR 规则在启用) 时对组织的影响
     - 6：警告 (启用 ASR 规则，但允许最终用户绕过块) 

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem05-add-row-oma-uri.png" alt-text="Microsoft Endpoint Manager管理中心门户中的 OMA URI 配置" lightbox="images/mem05-add-row-oma-uri.png":::

6. 选择 **“保存”**。 **添加行** 关闭。 在 **"自定义**"中，选择 **"下一步**"。 在步骤 **3 作用域标记中**，范围标记是可选的。 执行下列操作之一：

   - 选择 **"选择作用域"标记**，选择范围标记 (可选) ，然后选择 **"下一步**"。
   - 或选择 **"下一步**"

7. 在步骤 **4"分配**"中， **对于** 要应用此规则的组，请从以下选项中进行选择：

   - **添加组**
   - **添加所有用户**
   - **添加所有设备**

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem06-4-assignments.png" alt-text="Microsoft Endpoint Manager管理中心门户中的分配" lightbox="images/mem06-4-assignments.png":::

8. 在 **"已排除的组"** 中，选择要从此规则中排除的任何组，然后选择 **"下一步**"。

9. 在以下设置的步骤 **5 适用性规则** 中，执行以下操作：

   - 在 **"规则**"中，**如果选择"分配配置文件**"，则 **选择"如果"不分配配置文件"，则选择"不分配配置文件**"
   - 在 **"属性**"中，选择要将此规则应用到的属性
   - 在 **Value** 中，输入适用的值或值范围

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem07-5-applicability-rules.png" alt-text="Microsoft Endpoint Manager管理中心门户中的适用性规则" lightbox="images/mem07-5-applicability-rules.png":::

10. 选择 **下一步**。 在步骤 **6"查看 + 创建**"中，查看所选和输入的设置和信息，然后选择 **"创建**"。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mem08-6-review-create.png" alt-text="Microsoft Endpoint Manager管理中心门户中的&quot;审阅和创建&quot;选项" lightbox="images/mem08-6-review-create.png":::

    > [!NOTE]
    > 规则处于活动状态，并在数分钟内生存。

> [!NOTE]
> 冲突处理：
>
> 如果为设备分配两个不同的 ASR 策略，则处理冲突的方式是分配了不同状态的规则，没有就地进行冲突管理，结果为错误。
>
> 非冲突规则不会导致错误，并且规则将正确应用。 结果是应用了第一个规则，随后的非冲突规则合并到策略中。

### <a name="mdm"></a>MDM

使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 配置服务提供程序 (CSP) 单独启用和设置每个规则的模式。

下面是一个参考示例，使用 GUID 值进行 [攻击面减少规则引用](attack-surface-reduction-rules-reference.md)。

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84=2|3b576869-a4ec-4529-8536-b80a7769e899=1|d4f940ab-401b-4efc-aadc-ad5f3c50688a=2|d3e037e1-3eb8-44c8-a917-57927947596d=1|5beb7efe-fd9a-4556-801d-275e5ffc04cc=0|be9ba2d9-53ea-4cdc-84e5-9b1eeee46550=1`

在审核模式下启用 (阻止) 、禁用、警告或启用的值包括：

- 0：禁用 (禁用 ASR 规则) 
- 1：阻止 (启用 ASR 规则) 
- 2：审核 (评估 ASR 规则在启用) 时对组织的影响
- 6：警告 (启用 ASR 规则，但允许最终用户绕过块) 。 警告模式适用于大多数 ASR 规则。

使用 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 配置服务提供程序 (CSP) 添加排除项。

示例：

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> 请务必输入不带空格的 OMA-URI 值。

### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. 在Microsoft Endpoint Configuration Manager中，转到 **资产和合规性** \> **Endpoint Protection Windows Defender** \> **攻击防护**。

2. 选择 **"主** \> **创建攻击防护策略**"。

3. 输入名称和说明，选择 **"攻击面减少**"，然后选择 **"下一步**"。

4. 选择哪些规则将阻止或审核操作，然后选择 **"下一步**"。

5. 查看设置，然后选择 **"下一步** "以创建策略。

6. 创建策略后，选择 **"关闭**"。

### <a name="group-policy"></a>组策略

> [!WARNING]
> 如果使用Intune、Configuration Manager或其他企业级管理平台管理计算机和设备，则管理软件将覆盖启动时任何冲突的组策略设置。

1. 在组策略管理计算机上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **编辑**。

2. 在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。

3. 展开树以 **Windows组件** \> **Microsoft Defender 防病毒Microsoft Defender 攻击防护** \>  \> **攻击面减少**。

4. 选择 **"配置攻击面减少规则** "，然后选择 **"已启用**"。 然后，可以为选项部分中的每个规则设置单个状态。 选择 **"显示...** "，然后在 **"值名称** "列和 **"值** "列中输入所选状态中的规则 ID，如下所示：

   - 0：禁用 (禁用 ASR 规则) 
   - 1：阻止 (启用 ASR 规则) 
   - 2：审核 (评估 ASR 规则在启用) 时对组织的影响
   - 6：警告 (启用 ASR 规则，但允许最终用户绕过块) 

   :::image type="content" source="images/asr-rules-gp.png" alt-text="组策略中的 ASR 规则" lightbox="images/asr-rules-gp.png":::

5. 若要从 ASR 规则中排除文件和文件夹，请 **从攻击面减少规则设置中选择"排除文件和路径** "，并将选项设置为 **"已启用**"。 选择 **"显示"** ，然后在 **"值名称** "列中输入每个文件或文件夹。 在每个项的 **"值**"列中输入 **0**。

   > [!WARNING]
   > 请勿使用引号，因为值 **名称** 列或 **值** 列不支持引号。

### <a name="powershell"></a>PowerShell

> [!WARNING]
> 如果使用Intune、Configuration Manager或其他企业级管理平台管理计算机和设备，则管理软件将在启动时覆盖任何冲突的 PowerShell 设置。 若要允许用户使用 PowerShell 定义值，请在管理平台中使用规则的"用户定义"选项。
> "用户定义"允许本地管理员用户配置规则。
> 下图显示了"用户定义"选项设置。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-user-defined.png" alt-text="用于凭据安全性的&quot;启用&quot;选项" lightbox="images/asr-user-defined.png":::

1. 在"开始"菜单中键入 **powershell**，右键单击 **Windows PowerShell**，然后选择 **"以管理员身份运行**"。

2. 键入以下 cmdlet 之一。  (有关更多详细信息（如规则 ID.) ），请参阅[攻击面减少规则参考](attack-surface-reduction-rules-reference.md)

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

    若要启用 ASR 阻止滥用受攻击的易受攻击的签名驱动程序，请使用以下 cmdlet：

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    若要关闭 ASR 规则，请使用以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > 必须为每个规则单独指定状态，但可以组合逗号分隔列表中的规则和状态。
    >
    > 在以下示例中，将启用前两个规则，禁用第三个规则，并在审核模式下启用第四个规则：
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    还可以使用 `Add-MpPreference` PowerShell 谓词将新规则添加到现有列表。

    > [!WARNING]
    > `Set-MpPreference` 将始终覆盖现有规则集。 如果要添加到现有集，请改用 `Add-MpPreference` 。
    > 可以使用 `Get-MpPreference`>a0/> 获取规则及其当前状态的列表。

3. 若要从 ASR 规则中排除文件和文件夹，请使用以下 cmdlet：

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    继续使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 以向列表添加更多文件和文件夹。

    > [!IMPORTANT]
    > 用于 `Add-MpPreference` 将应用追加或添加到列表。 `Set-MpPreference`使用 cmdlet 将覆盖现有列表。

## <a name="related-articles"></a>相关文章

- [攻击面减少规则参考](attack-surface-reduction-rules-reference.md)
- [评估攻击面减少](evaluate-attack-surface-reduction.md)
- [关于攻击面减少的常见问题解答](attack-surface-reduction.md)
