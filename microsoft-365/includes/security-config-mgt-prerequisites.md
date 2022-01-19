---
title: 包含文件
description: 包含文件
author: mjcaparas
ms.service: microsoft-365-enterprise
ms.author: macapara
ms.openlocfilehash: d4554596f4c33ce0536ad2c8e6092fd8fdc74033
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62079584"
---
## <a name="prerequisites"></a>先决条件

查看以下部分，查看 Microsoft Defender 终结点方案的安全管理要求：

### <a name="environment"></a>环境

当设备载入到适用于终结点的 Microsoft Defender 时：


- 设备正在接受现有Endpoint Manager状态，这是移动设备管理 (MDM) 注册到 Intune
- 没有安全Endpoint Manager设备将启用安全管理功能
- 如果不存在信任Azure Active Directory，则创建信任
- Azure Active Directory信任用于与 Intune Endpoint Manager (通信) 检索策略
- Microsoft Defender Endpoint Manager在设备上强制执行从设备检索策略

### <a name="active-directory-requirements"></a>Active Directory 要求

当加入域的设备创建与 Azure Active Directory 的信任时，此方案称为混合Azure Active Directory *加入* 方案。 Microsoft Defender for Endpoint 的安全管理完全支持此方案，并满足以下要求：

- Azure Active Directory 连接 (AAD 连接) 必须同步到从 Microsoft Defender for Endpoint 使用的租户
- 必须在Azure Active Directory环境中通过联合身份验证或同步 (配置混合AAD 连接加入) 
- AAD 连接 Sync 必须包含作用域中的设备对象，以在需要加入 Azure Active Directory (时与) 
- AAD 连接需要支持 Server 2012 R2 时，必须修改 Server 2012 R2 (同步规则) 
- 所有设备都必须在托管 Microsoft Defender for Endpoint Azure Active Directory的租户的租户中注册。 不支持跨租户方案。 

### <a name="connectivity-requirements"></a>连接要求

设备必须有权访问以下终结点：

- `enterpriseregistration.windows.net`- Azure AD注册。
- `login.microsoftonline.com`- Azure AD注册。
- `*.dm.microsoft.com` - 使用通配符支持用于注册、签入和报告以及随着服务扩展而更改的云服务终结点。

### <a name="supported-platforms"></a>支持的平台

以下设备平台支持 Microsoft Defender 终结点安全管理策略：

- Windows 10 Professional/Enterprise ([KB5006738) ](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)
- Windows Server 2012适用于移动设备[的 Microsoft Defender Down-Level R2](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2016 [Microsoft Defender for Down-Level 设备](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2019 ([KB5006744](https://support.microsoft.com/topic/october-19-2021-kb5006744-os-build-17763-2268-preview-e043a8a3-901b-4190-bb6b-f5a4137411c0)) 
- Windows Server 2022 ([KB5006745](https://support.microsoft.com/topic/october-26-2021-kb5006745-os-build-20348-320-preview-8ff9319a-19e7-40c7-bbd1-cd70fcca066c)) 

### <a name="licensing-and-subscriptions"></a>许可和订阅

若要对 Microsoft Defender for Endpoint 使用安全管理，你需要：

- 为适用于终结点的 Microsoft Defender（如 Microsoft 365）或仅针对 Microsoft Defender for Endpoint 授予独立许可证的订阅。 有关选项的当前信息，请参阅 [Microsoft Defender for Endpoint 的最低要求](/microsoft-365/security/defender-endpoint/minimum-requirements?view=o365-worldwide&preserve-view=true)。

  *任何授予* Microsoft Defender for Endpoint 许可证的订阅还授予租户对管理中心终结点Microsoft Endpoint Manager的访问权限。 终结点安全节点是配置和部署策略以管理设备的 Microsoft Defender for Endpoint 并监视设备状态的地方。

>[!NOTE]
> 目前，如果通过 Azure 安全中心/适用于云的 Defender 获取适用于终结点的 Microsoft Defender 订阅，则此 Microsoft Defender 终结点许可证不是此功能的合格许可证。 


## <a name="architecture"></a>体系结构

下图是 Microsoft Defender for Endpoint 安全配置管理解决方案的概念性表示形式。

:::image type="content" alt-text="Microsoft Defender for Endpoint 安全配置管理解决方案的概念性表示" source="../security/defender-endpoint/images/mde-architecture.png":::

1. 设备载入到 Microsoft Defender for Endpoint。

2. 在每个设备和设备之间建立信任Azure AD。 当设备具有现有信任时，即已使用。 当设备尚未注册时，将创建一个新信任。

3. 设备使用其Azure AD标识与用户Endpoint Manager。 此标识Microsoft Endpoint Manager在设备签入时分发面向这些设备的策略。

4. Defender for Endpoint 将策略的状态报告回Endpoint Manager。

## <a name="which-solution-should-i-use"></a>我应该使用哪种解决方案？

Microsoft Endpoint Manager包括几种用于管理设备上 Defender for Endpoint 的配置的方法和策略类型。

当你的设备保护需要扩展到管理 Defender for Endpoint [](/mem/intune/protect/device-protect)之外，请参阅设备保护概述，了解 Microsoft Endpoint Manager 提供的其他功能以帮助保护设备，包括设备合规性、托管的应用、应用保护策略，以及第三方合规性和移动 *威胁* 防护合作伙伴的集成。 

下表可帮助你了解由不同方案管理的设备支持哪些可以配置 MDE 设置的策略。 当你部署同时受 *MDE* 安全配置和 *Microsoft Endpoint Manager* 支持的策略时，该策略的单个实例可以由仅运行 MDE 的设备以及由 Intune 或 Configuration Manager 管理的设备进行处理。

| Microsoft Endpoint Manager  | Workload | MDE 安全配置  |  Microsoft Endpoint Manager |
|----------------|----------------|-------------------|------------|
| 终结点安全    | 防病毒                   | ![支持](../media/green-check.png)  | ![支持](../media/green-check.png)  |
|                      | 磁盘加密   |           | ![受支持](../media/green-check.png)  |
|                      | 防火墙 (配置文件和规则)                 | ![支持](../media/green-check.png) | ![支持](../media/green-check.png)  |
|                      | 终结点检测和响应        | ![支持](../media/green-check.png) | ![支持](../media/green-check.png)  |
|                      | 攻击面减少    |           | ![受支持](../media/green-check.png)  |
|                      | 帐户保护       |       | ![受支持](../media/green-check.png)  |
|                      | 设备合规性     |   | ![受支持](../media/green-check.png)  |
|                      | 条件访问    |   | ![受支持](../media/green-check.png)  |
|                      | 安全基线      |   | ![受支持](../media/green-check.png)  |

**终结点安全策略** 是一组分散的设置，旨在供侧重于保护组织中设备的安全管理员使用。

- **防病毒策略** 管理在 Microsoft Defender for Endpoint 中发现的安全配置。 请参阅  [终结点](/mem/intune/protect/endpoint-security-antivirus-policy) 安全性的防病毒策略。
- **攻击面** 减少策略侧重于最大程度地减少组织易受网络威胁和攻击的位置。 有关详细信息，[请参阅威胁防护](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)文档中的攻击面Windows概述和终结点安全的攻击面减少策略。 [](/mem/intune/protect/endpoint-security-asr-policy)
- **终结点检测和响应** (EDR) 策略管理 Defender for Endpoint 功能，这些功能提供接近实时且可操作的高级攻击检测。 根据EDR配置，安全分析师可以有效地确定警报的优先级，了解泄露的完整范围，并采取响应操作来修正威胁。 有关 [终结点安全，请参阅](/mem/intune/protect/endpoint-security-edr-policy) 终结点检测和响应策略。
- **防火墙** 策略侧重于你的设备的 Defender 防火墙。 有关 [终结点](/mem/intune/protect/endpoint-security-firewall-policy) 安全，请参阅防火墙策略。
- **防火墙规则** 配置防火墙的细化规则，包括特定端口、协议、应用程序和网络。 有关 [终结点](/mem/intune/protect/endpoint-security-firewall-policy) 安全，请参阅防火墙策略。
- **安全基线** 包括预配置的安全设置，这些设置定义不同产品（如 Defender、Edge 或 Windows）的 Microsoft 建议Windows。 默认建议来自相关产品团队，可让你快速将建议的安全配置部署到设备。 在每个基线中预配置设置时，可以创建这些设置的自定义实例，以建立组织的安全预期。 请参阅 [Intune](/mem/intune/protect/security-baselines) 的安全基线。

## <a name="configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management"></a>配置租户以支持 Microsoft Defender 进行终结点安全配置管理

若要通过管理中心支持 Microsoft Defender 终结点安全Microsoft Endpoint Manager管理，你必须在每个控制台中启用它们之间的通信。

1. 登录到 [Microsoft 365 Defender，](https://security.microsoft.com/)然后转到设置  >  **终结点** 配置管理强制范围并启用  >    >  用于安全设置管理的平台：

   :::image type="content" source="../media/enable-mde-settings-management-defender.png" alt-text="在 Defender 控制台中启用 Microsoft Defender 终结点设置管理。":::

2. 确保相关用户有权管理终结点安全设置，Microsoft Endpoint Manager在 Defender 门户中配置角色来授予这些权限。 转到设置  >  **角色**  >  **添加项**：

   :::image type="content" source="../media/add-role-in-mde.png" alt-text="在 Defender 门户中创建新角色。":::

   > [!TIP]
   > 你可以修改现有角色并添加必要的权限，而不是在 Microsoft Defender for Endpoint 中创建其他角色

3. 配置角色时，添加用户并确保选择以下选项中的"管理 **终结点安全设置Microsoft Endpoint Manager：**

   :::image type="content" source="../media/add-role.png" alt-text="授予用户管理设置的权限。":::

4. 登录到 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。

5. 选择 **终结点安全**  >  **Microsoft Defender for Endpoint，** 将允许 Microsoft Defender for Endpoint 强制实施终结点安全配置 **(预览**) **设置为"打开"。**

   :::image type="content" source="../media/enable-mde-settings-management-mem.png" alt-text="在管理中心中为终结点设置Microsoft Endpoint Manager Microsoft Defender。":::

   将此选项设置为 *"* 打开"时，Microsoft Defender for Endpoint 中平台作用域中未由 Microsoft Endpoint Manager 管理的所有设备都将有资格载入到 Microsoft Defender for Endpoint。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>将设备载入到 Microsoft Defender for Endpoint

Microsoft Defender for Endpoint 支持多种载入设备的选项。 有关当前指南[，](/microsoft-365/security/defender-endpoint/security-config-management)请参阅 Defender for Endpoint 文档中的 Windows设备的载入工具和方法。


> [!IMPORTANT]
> 在设备载入 Microsoft Defender for Endpoint 后，必须先使用 **MDE 管理** 进行标记，然后才能注册 Microsoft Defender for Endpoint 的安全管理。 有关 MDE 中的设备标记详细信息，请参阅 [*创建和管理设备标记*](/microsoft-365/security/defender-endpoint/machine-tags)。


## <a name="co-existence-with-microsoft-endpoint-configuration-manager"></a>与组织共存Microsoft Endpoint Configuration Manager
使用 Configuration Manager 时，安全策略管理的最佳路径是使用 [Configuration Manager 租户附加](/mem/configmgr/tenant-attach/endpoint-security-get-started)。 在某些环境中，可能需要对 Microsoft Defender 使用安全管理。 将 Microsoft Defender 安全管理与 Configuration Manager 一同使用时，终结点安全策略应隔离到单个控制平面。 通过这两个渠道控制策略将创造冲突和不预期结果的机会。


## <a name="create-azure-ad-groups"></a>创建Azure AD组

在设备载入到适用于终结点的 Defender 后，你需要创建设备组以支持 Microsoft Defender for Endpoint 的策略部署。

若要标识已注册 Microsoft Defender for Endpoint 但未由 Intune 或 Configuration Manager 管理的设备：

1. 登录到[ Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。

2. 转到 **"设备**""所有设备"，然后选择"托管者"列  >  以对设备视图进行排序。 

   已载入 Microsoft Defender for Endpoint 且已注册但 Intune 不管理的设备在"托管者"列中显示 **Microsoft Defender for Endpoint。** 这些设备可以接收 Microsoft Defender for Endpoint 的安全管理策略。

   对于使用 Microsoft Defender for Endpoint 安全管理的设备，你还将找到两个标签：

   - **MDEJoined** - 已添加到作为此方案的一部分加入目录的设备。
   - **MDEManaged** - 已添加到主动使用安全管理方案的设备。 如果 Defender for Endpoint 停止管理安全配置，则此标记将从设备中删除。

可以在管理中心内或[Azure AD为这些设备](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)Microsoft Endpoint Manager[组](/mem/intune/fundamentals/groups-add)。

## <a name="deploy-policy"></a>部署策略

创建一个或多个包含由 Microsoft Defender for Endpoint 管理的设备的 Azure AD 组后，你可以为 Microsoft Defender for Endpoint 的安全管理创建以下策略，并部署到这些组：

- 防病毒
- 防火墙
- 防火墙规则
- 终结点检测和响应

> [!TIP]
> 避免将管理相同设置的多个策略部署到设备。
>
> Microsoft Endpoint Manager支持将每个终结点安全策略类型的多个实例部署到同一设备，每个策略实例由设备单独接收。 因此，设备可能会从不同的策略接收相同设置的单独配置，这导致冲突。 某些设置 (如防病毒排除) 将在客户端上合并并成功应用。

1. 登录到 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。

2. 转到 **"终结点安全性**"，然后选择要配置的策略类型，即"防病毒"或"防火墙"，然后选择"创建 **策略"。**

3. 输入以下属性或所选的策略类型：

   - 对于防病毒策略，选择：
     - 平台 **：Windows 10、Windows 11 和 Windows Server (Preview)**
     - 配置文件 **：Microsoft Defender 防病毒 (预览)**

   - 对于防火墙策略，选择：
     - 平台 **：Windows 10、Windows 11 和 Windows Server (Preview)**
     - 配置文件 **：Microsoft Defender 防火墙 (预览)**

   - 对于防火墙规则策略，选择：
     - 平台 **：Windows 10、Windows 11 和 Windows Server (Preview)**
     - 配置文件 **：Microsoft Defender 防火墙规则 (预览)**

   - 对于"终结点检测和响应"策略，选择：
     - 平台 **：Windows 10、Windows 11 和 Windows Server (Preview)**
     - 配置文件： **终结点检测和响应 (预览)**

   >[!Note]
   > 这些配置文件适用于通过移动设备管理 (MDM) 与 Microsoft Intune 通信的设备，以及使用 Microsoft Defender for Endpoint 客户端进行通信的设备。
   >
   > 确保你在必要时查看你的目标市场和组。

4. 选择“**创建**”。

5. 在“**基本信息**”页上，输入配置文件的名称和说明，然后选择“**下一步**”。

6. 在 **"配置设置** "页上，选择要管理此配置文件的设置。 若要了解有关某个设置的详细信息，请展开其信息对话框并选择"了解 *详细信息* "链接以查看在线文档中设置的 CSP 信息。

   完成配置设置后，选择“**下一步**”。

7. 在"**工作** 分配"页上，Azure AD接收此配置文件的组。 有关分配配置文件的详细信息，请参阅[分配用户和设备配置文件](/mem/intune/configuration/device-profile-assign)。

   选择“**下一步**”以继续。

   > [!TIP]
   >
   > - 安全配置管理配置文件不支持分配筛选器。
   > - 只有 *设备对象* 适用于 Microsoft Defender 终结点管理。 不支持面向用户。
   > - 配置的策略将同时应用于 Microsoft Intune 和适用于终结点客户端的 Microsoft Defender

8. 完成策略创建过程，然后在"审阅 **+** 创建"页上，选择"创建 **"。** 为创建的配置文件选择策略类型时，新配置文件将显示在列表中。

9. 等待分配策略，并查看策略已应用的成功指示。

10. 可以使用 [Get-MpPreference](/powershell/module/defender/get-mppreference#examples) 命令实用工具验证设置是否在本地应用于客户端。
