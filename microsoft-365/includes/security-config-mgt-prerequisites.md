---
title: 包含文件
description: 包含文件
author: mjcaparas
ms.service: microsoft-365-enterprise
ms.author: macapara
ms.openlocfilehash: e8d19f8ab5423ccc0441d29efab2ecdb3eb27a04
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60676954"
---
## <a name="prerequisites"></a>先决条件

查看以下部分，查看 Microsoft Defender 终结点方案的安全管理要求：

### <a name="environment"></a>环境

当设备载入到适用于终结点的 Microsoft Defender 时：

- 设备正在等待现有Endpoint Manager状态，包括 Configuration Manager 或 Intune
- 没有安全状态Endpoint Manager启用安全管理功能
- 如果不存在信任Azure Active Directory，则创建信任
- Azure Active Directory信任用于与 Intune Endpoint Manager (通信) 检索策略
- Microsoft Defender Endpoint Manager终结点在设备上强制执行从策略检索策略

### <a name="active-directory-requirements"></a>Active Directory 要求

当加入域的设备创建与 Azure Active Directory 的信任时，此方案称为混合Azure Active Directory *加入* 方案。 Microsoft Defender for Endpoint 的安全管理完全支持此方案，并满足以下要求：

- Azure Active Directory 连接 (AAD 连接) 必须同步到从 Microsoft Defender for Endpoint 使用的租户
- 必须在Azure Active Directory通过联合身份验证或同步 (配置混合AAD 连接加入) 
- AAD 连接 Sync 必须包含作用域中的设备对象，以在需要加入 Azure Active Directory (时与) 
- AAD 连接需要支持 Server 2012 R2 时，必须针对 Server 2012 R2 (修改同步规则) 

### <a name="connectivity-requirements"></a>连接要求

设备必须有权访问以下终结点：

- `enterpriseregistration.windows.net`- 对于Azure AD注册。
- `login.microsoftonline.com`- 对于Azure AD注册。
- `*.dm.microsoft.com` - 使用通配符支持用于注册、签入和报告以及随着服务扩展而更改的云服务终结点。

### <a name="supported-platforms"></a>支持的平台

以下设备平台支持 Microsoft Defender 终结点安全管理策略：

- Windows 10 Professional/Enterprise ([KB5006738) ](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)
- Windows Server 2012R2 与[适用于 Down-Level 设备的 Microsoft Defender](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2016 [Microsoft Defender for Down-Level 设备](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- WindowsServer 2019 ([KB5006744](https://support.microsoft.com/topic/october-19-2021-kb5006744-os-build-17763-2268-preview-e043a8a3-901b-4190-bb6b-f5a4137411c0)) 
- Windows Server 2022


### <a name="licensing-and-subscriptions"></a>许可和订阅

若要对 Microsoft Defender for Endpoint 使用安全管理，你需要：

- 为适用于终结点的 Microsoft Defender（如 Microsoft 365）或仅针对 Microsoft Defender for Endpoint 授予独立许可证的订阅。 有关选项的当前信息，请参阅 [Microsoft Defender for Endpoint 的最低要求](/microsoft-365/security/defender-endpoint/minimum-requirements)。

  *任何授予* Microsoft Defender for Endpoint 许可证的订阅还授予租户对 Microsoft Endpoint Manager 安全节点的访问权限。 终结点安全节点是配置和部署策略以管理设备的 Microsoft Defender for Endpoint 并监视设备状态的地方。

## <a name="architecture"></a>体系结构

下图是 Microsoft Defender for Endpoint 安全配置管理解决方案的概念性表示形式。


:::image type="content" alt-text="Microsoft Defender for Endpoint 安全配置管理解决方案的概念性表示" source="../security/defender-endpoint/images/mde-architecture.png":::


1. 设备载入到 Microsoft Defender for Endpoint。

2. 在每个设备和设备之间建立信任Azure AD。 当设备具有现有信任时，即已使用。 当设备尚未注册时，将创建一个新信任。


3. 设备使用其Azure AD标识与用户Endpoint Manager。 此标识Microsoft Endpoint Manager在设备签入时分发面向这些设备的策略。

4. Defender for Endpoint 将策略的状态报告回Endpoint Manager。

## <a name="configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management"></a>配置租户以支持 Microsoft Defender 进行终结点安全配置管理

若要通过管理中心支持 Microsoft Defender 的终结点Microsoft Endpoint Manager管理，你必须在每个控制台中启用它们之间的通信。

1. 登录到[Microsoft 365 Defender，](https://security.microsoft.com/)然后转到设置终结点配置管理强制范围，并启用  >    >    >  用于安全设置管理的平台：

   :::image type="content" source="../media/enable-mde-settings-management-defender.png" alt-text="在 Defender 控制台中启用 Microsoft Defender 终结点设置管理。":::

2. 确保相关用户有权管理 Microsoft Endpoint Manager或通过配置 Defender 门户中的角色授予这些权限。 转到设置  >  **角色**  >  **添加项**：

   :::image type="content" source="../media/add-role-in-mde.png" alt-text="在 Defender 门户中创建新角色。":::

   > [!TIP]
   > 你可以修改现有角色并添加必要的权限，而不是在 Microsoft Defender for Endpoint 中创建其他角色

3. 配置角色时，添加用户并确保选择以下选项中的"管理 **终结点安全设置Microsoft Endpoint Manager：**

   :::image type="content" source="../media/add-role.png" alt-text="授予用户管理设置的权限。":::

4. 登录到 [Microsoft 终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。

5. 选择 **终结点安全**  >  **Microsoft Defender for Endpoint，** 将允许 Microsoft **Defender for Endpoint 强制实施** 终结点安全配置 (预览) 设置为 **"打开"。**

   :::image type="content" source="../media/enable-mde-settings-management-mem.png" alt-text="在管理中心中为终结点设置Microsoft Endpoint Manager Microsoft Defender。":::

   将此选项设置为 *"* 打开"时，Microsoft Defender for Endpoint 中平台作用域中未由 Microsoft Endpoint Manager 管理的所有设备都将有资格载入到 Microsoft Defender for Endpoint。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>将设备载入到 Microsoft Defender for Endpoint

Microsoft Defender for Endpoint 支持多种载入设备的选项。 有关当前指南，请参阅[](/microsoft-365/security/defender-endpoint/security-config-management)Defender for Endpoint 文档中的 Windows设备的载入工具和方法。

此方案不支持使用 Intune 或 Configuration Manager 管理的设备。

## <a name="create-azure-ad-groups"></a>创建Azure AD组

在设备载入到适用于终结点的 Defender 后，你需要创建设备组以支持 Microsoft Defender for Endpoint 的策略部署。

若要标识已注册 Microsoft Defender for Endpoint 但未由 Intune 或 Configuration Manager 管理的设备：

1. 登录到[ Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。

2. 转到 **"设备**""所有设备"，然后选择"托管  >  **者**"列以对设备视图进行排序。

   载入 Microsoft Defender for Endpoint 并且已注册但由 Intune 或 Configuration Manager 管理的设备在"托管者"列中显示 **Microsoft Defender for Endpoint。** 这些设备可以接收 Microsoft Defender for Endpoint 的安全管理策略。

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

1. 登录到 [Microsoft 终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。

2. 转到 **"终结点安全性**"，然后选择要配置的策略类型，即"防病毒"或"防火墙"，然后选择"创建 **策略"。**

3. 输入以下属性或所选的策略类型：

   - 对于防病毒策略，选择：
     - 平台 **：Windows 10、Windows 11 和 Windows Server (Preview)**
     - 配置文件 **：Microsoft Defender 防病毒 (预览)**

   - 对于防火墙策略，选择：
     - 平台 **：Windows 10、Windows 11 和 Windows Server (Preview)**
     - 配置文件 **：Microsoft Defender 防火墙 (预览版)**

   - 对于防火墙规则策略，选择：
     - 平台 **：Windows 10、Windows 11 和 Windows Server (Preview)**
     - 配置文件 **：Microsoft Defender 防火墙规则 (预览版)**

   - 对于"终结点检测和响应"策略，选择：
     - 平台 **：Windows 10、Windows 11 和 Windows Server (Preview)**
     - 配置文件： **终结点检测和响应 (预览)**

4. 选择“**创建**”。

5. 在"**基本信息"** 页上，输入配置文件的名称和说明，然后选择"下一步 **"。**

6. 在 **"配置设置** "页上，选择要管理此配置文件的设置。 若要了解有关某个设置的详细信息，请展开其信息对话框并选择"了解 *详细信息* "链接以查看在线文档中设置的 CSP 信息。

   完成配置设置后，选择"下一 **步"。**

7. 在"**工作** 分配"页上，Azure AD接收此配置文件的组。 有关分配配置文件的详细信息，请参阅[分配用户和设备配置文件](/mem/intune/configuration/device-profile-assign)。

   选择“**下一步**”以继续。

   > [!TIP]
   >
   > - 安全配置管理配置文件不支持分配筛选器。
   > - 只有 *设备对象* 适用于 Microsoft Defender 终结点管理。 不支持用户目标。
   > - 配置的策略将同时应用于 Microsoft Intune 和 Microsoft Defender for Endpoint 客户端

8. 完成策略创建过程，然后在"审阅 **+** 创建"页上，选择"创建 **"。** 为创建的配置文件选择策略类型时，新配置文件将显示在列表中。

9. 等待分配策略，并查看策略已应用的成功指示。

10. 可以使用 [Get-MpPreference](/powershell/module/defender/get-mppreference#examples) 命令实用工具验证设置是否在本地应用于客户端。

