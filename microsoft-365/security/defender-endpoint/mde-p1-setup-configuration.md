---
title: 设置和配置Microsoft Defender for Endpoint计划 1
description: 了解如何设置和配置 Defender for Endpoint Plan 1。 查看要求、计划推出和设置环境。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/14/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 774139aa6ccbf0562d5f6a9bf14eb89550e865a8
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665945"
---
# <a name="set-up-and-configure-microsoft-defender-for-endpoint-plan-1"></a>设置和配置Microsoft Defender for Endpoint计划 1

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

本文介绍如何设置和配置 Defender for Endpoint Plan 1。 无论你是获得帮助还是自己执行此操作，都可以在整个部署过程中使用本文作为指南。  

## <a name="the-setup-and-configuration-process"></a>设置和配置过程

:::image type="content" source="images/mde-p1-deploymentflow.png" alt-text="Microsoft Defender for Endpoint计划 1 的设置和部署流" lightbox="images/mde-p1-deploymentflow.png":::

Defender for Endpoint Plan 1 的常规设置和配置过程如下所示： <br/><br/>


| 数字  | 步骤  | 说明  |
|:---------:|:---------|:---------|
| 1 | [查看要求](#review-the-requirements)  | 列出许可、浏览器、操作系统和数据中心要求   |
| 2 | [规划部署](#plan-your-deployment) | 列出几个要考虑的部署方法，并包含指向更多资源的链接，以帮助你确定要使用哪种方法  |
| 3 | [设置租户环境](#set-up-your-tenant-environment) | 列出用于设置租户环境的任务 |
| 4 | [分配角色和权限](#assign-roles-and-permissions) | 列出安全团队要考虑的角色和权限 <br/><br/>**提示**：一旦分配了角色和权限，安全团队就可以开始使用Microsoft 365 Defender门户。 若要了解详细信息，请参阅 [入门](mde-plan1-getting-started.md)。 |
| 5 | [载入到 Defender for Endpoint](#onboard-to-defender-for-endpoint) | 列出了操作系统加入 Defender for Endpoint Plan 1 的几种方法，并包含指向每个方法的更详细信息的链接  |
| 6  | [配置下一代保护](#configure-next-generation-protection) | 介绍如何在Microsoft Endpoint Manager中配置下一代保护设置  |
| 7  | [配置攻击面减少功能](#configure-your-attack-surface-reduction-capabilities)        | 列出可配置的攻击面减少功能的类型，并包含链接到更多资源的过程  |
 
## <a name="review-the-requirements"></a>查看要求

下表列出了 Defender for Endpoint Plan 1 的基本要求：<br/><br/>

| 要求 | 说明 |
|:---|:---|
| 许可要求 | Defender for Endpoint 计划 1 |
| 浏览器要求 | Microsoft Edge <br/> Internet Explorer 版本 11 <br/> Google Chrome |
| 操作系统 | Windows 10版本 1709 或更高版本 <br/>macOS： 11.5 (Big Sur) ， 10.15.7 (Catalina) ， 或 10.14.6 (Mojave)  <br/>iOS <br/>Android OS  |
| 数据中心版 | 以下数据中心位置之一： <br/>- 欧盟 <br/>- 英国 <br/>- 美国 |


## <a name="plan-your-deployment"></a>规划部署

规划部署时，可以从多种不同的体系结构和部署方法中进行选择。 每个组织都是唯一的，因此需要考虑几个选项，如下表所示： <br/><br/>

| 方法 | 说明 |
|:---|:---|
| [Microsoft Endpoint Manager) ](/mem/intune/fundamentals/what-is-intune)中包含的Microsoft Intune ( | 使用Intune管理云本机环境中的终结点 |
| [Microsoft Endpoint Manager) ](/mem/intune/fundamentals/what-is-intune)中包含[的](/mem/configmgr/core/understand/introduction)Microsoft Intune和Configuration Manager ( | 使用Intune和Configuration Manager管理跨本地和云环境的终结点和工作负荷 |
| [配置管理器](/mem/configmgr/core/understand/introduction) | 使用 Configuration Manager 使用 Defender for Endpoint 的基于云的功能保护本地终结点 |
| 从 Microsoft 365 Defender 门户下载的本地脚本 | 在终结点上使用本地脚本运行试点或仅载入几个设备 |

若要了解有关部署选项的详细信息，请参阅 [规划 Defender for Endpoint 部署](deployment-strategy.md)。 然后，下载以下海报： 

[:::image type="content" source="../../media/defender-endpoint/mde-deployment-strategy.png" alt-text="部署策略海报缩略图":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)

**[获取部署海报](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)**

> [!TIP]
> 有关规划部署的更多详细信息，请参阅[规划Microsoft Defender for Endpoint部署](deployment-strategy.md)。

## <a name="set-up-your-tenant-environment"></a>设置租户环境

设置租户环境包括以下任务：

- 验证许可证
- 配置租户
- 仅在必要时才 (配置代理设置) 
- 确保传感器正常工作并向 Defender for Endpoint 报告数据 

这些任务包含在 Defender for Endpoint 的设置阶段中。 请参阅 ["设置 Defender for Endpoint](production-deployment.md)"。

## <a name="assign-roles-and-permissions"></a>分配角色和权限

若要访问Microsoft 365 Defender门户、为 Defender for Endpoint 配置设置或执行任务（例如对检测到的威胁执行响应操作），必须分配适当的权限。 Defender for Endpoint 在[Azure Active Directory中使用内置角色](/azure/active-directory/roles/permissions-reference)。 

Microsoft 建议仅向用户分配执行任务所需的权限级别。 可以通过使用基本权限管理或使用 [基于角色的访问控制](rbac.md) (RBAC) 来分配权限。 

- 使用基本权限管理，全局管理员和安全管理员具有完全访问权限，而安全读取者则具有只读访问权限。
- 使用 RBAC，可以通过更多角色设置更精细的权限。 例如，可以有安全读取器、安全操作员、安全管理员、终结点管理员等。


下表介绍了组织中 Defender for Endpoint 需要考虑的关键角色： <br/><br/>

| Role | 说明 |
|:---|:---|
| 全局管理员 (也称为全局管理员)  <br/><br/> *最佳做法是限制全局管理员的数量。* | 全局管理员可以执行各种任务。 默认情况下，为公司注册Microsoft 365或Microsoft Defender for Endpoint计划 1 的人员是全局管理员。 <br/><br/> 全局管理员能够跨所有Microsoft 365门户访问/更改设置，例如： <br/>- Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com))  <br/>- Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com))  <br/>- Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com)  |
| 安全管理员 (也称为安全管理员)  | 安全管理员可以执行安全操作员任务以及以下任务： <br/>- 监视与安全相关的策略 <br/>- 管理安全威胁和警报 <br/>- 查看报表 |
| 安全操作员 | 安全操作员可以执行安全读取器任务以及以下任务： <br/>- 查看有关检测到的威胁的信息 <br/>- 调查并响应检测到的威胁  |
| 安全读者 | 安全读取器可以执行以下任务： <br/>- 查看跨Microsoft 365服务的安全相关策略 <br/>- 查看安全威胁和警报 <br/>- 查看报表  |


> [!TIP]
> 若要详细了解Azure Active Directory中的角色，请参阅[为具有Azure Active Directory的用户分配管理员和非管理员角色](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。 有关 Defender for Endpoint 角色的详细信息，请参阅 [基于角色的访问控制](prepare-deployment.md#role-based-access-control)。

## <a name="onboard-to-defender-for-endpoint"></a>载入到 Defender for Endpoint

准备好加入组织的终结点后，可以从几种方法中进行选择，如下表所示： <br/><br/>

|终结点操作系统 | 载入方法|
|---|---|
| Windows 10 | [本地脚本 (多达 10 台设备) ](configure-endpoints-script.md) <br>  [组策略](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/移动设备管理器](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 脚本](configure-endpoints-vdi.md)  |
| macOS | [本地脚本](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [移动设备管理](mac-install-with-other-mdm.md) |
| iOS |[基于应用](ios-install.md) |
| Android | [Microsoft Endpoint Manager](android-intune.md) |

然后，继续配置下一代保护和攻击面减少功能。

## <a name="configure-next-generation-protection"></a>配置下一代保护

建议使用[Microsoft Endpoint Manager](/mem)管理组织的设备和安全设置，如下图所示：
 
:::image type="content" source="../../media/mde-p1/endpoint-policies.png" alt-text="Micorosft Endpoint Manager 门户中的终结点安全策略" lightbox="../../media/mde-p1/endpoint-policies.png":::

若要在Microsoft Endpoint Manager中配置下一代保护，请执行以下步骤：

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 选择 **Endpoint** **securityAntivirus** > ，然后选择现有策略。  (如果没有现有策略，请创建新的策略。) 

3. 设置或更改防病毒配置设置。 需要帮助？ 请参阅以下资源： <br/>

   - [Microsoft Intune中Windows 10 Microsoft Defender 防病毒策略的设置](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)
   - [在 iOS 功能上配置 Defender for Endpoint](ios-configure-features.md)

4. 指定完设置后，选择 **"查看 + 保存**"。

## <a name="configure-your-attack-surface-reduction-capabilities"></a>配置攻击面减少功能

减少攻击面就是减少组织开放攻击的位置和方式。 Defender for Endpoint Plan 1 包括多个功能和功能，可帮助你减少整个终结点的攻击面。 下表列出了这些功能和功能： <br/><br/>

| 功能/功能 | 说明 |
|:---|:---|
| [攻击面减少规则](#attack-surface-reduction-rules) | 配置攻击面减少规则，以限制基于软件的风险行为，并帮助确保组织的安全。 攻击面减少规则针对某些软件行为，例如<br/>- 启动尝试下载或运行文件的可执行文件和脚本 <br/>- 运行模糊或以其他方式可疑的脚本 <br/>- 执行应用通常不会在正常日常工作中启动的行为 <br/><br/>此类软件行为有时会在合法的应用程序中出现。 但是，这些行为通常被认为是有风险的，因为它们通常通过恶意软件被攻击者滥用。  |
| [勒索软件缓解](#ransomware-mitigation) | 通过配置受控文件夹访问来设置勒索软件缓解措施，这有助于保护组织的宝贵数据免受恶意应用和威胁（如勒索软件）的侵害。 | 
| [设备控制](#device-control) | 为组织配置设备控制设置，以允许或阻止可移动设备 (如 USB 驱动器) 。 | 
| [网络保护](#network-protection) | 设置网络保护以防止组织中的人员使用在 Internet 上访问危险域或恶意内容的应用程序。 |
| [Web 保护功能](#web-protection) | 设置 Web 威胁防护，以保护组织的设备免受网络钓鱼网站、攻击网站和其他不受信任或信誉低下的网站的侵扰。 设置 Web 内容筛选，根据网站的内容类别跟踪和规范对网站的访问， (如休闲、高带宽、成人内容或法律责任) 。 |
| [网络防火墙](#network-firewall) | 使用规则配置网络防火墙，这些规则确定允许哪些网络流量进入或从组织的设备流出。 |
| [应用程序控制](#application-control)  | 如果希望仅允许受信任的应用程序和进程在Windows设备上运行，请配置应用程序控制规则。    |

### <a name="attack-surface-reduction-rules"></a>攻击面减少规则

在运行Windows的设备上提供攻击面减少规则。 建议使用Microsoft Endpoint Manager，如下图所示：

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Microsoft Endpoint Manager门户中的攻击面减少规则" lightbox="../../media/mde-p1/mem-asrpolicies.png":::

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 选择 **Endpoint securityAttack** >  **surface reduction** > **+ Create 策略**。

3. 对于 **平台**，请选择 **Windows 10 和更高版本**。

4. 对于 **配置文件**，选择 **"攻击面减少规则**"，然后选择 **"创建**"。

5. 在 **"基本信息"** 选项卡上，指定策略的名称和说明，然后选择 **"下一步**"。

6. 在 **"配置设置"** 选项卡上，展开 **"攻击面减少规则**"。

7. 为每个规则指定设置，然后选择 **"下一步**"。  (有关每个规则的作用的详细信息，请参阅 [攻击面减少规则](attack-surface-reduction.md)。)  

8. 在 **"作用域标记"** 选项卡上，如果你的组织正在使用范围标记，请选择 **"+ 选择范围标记**"，然后选择要使用的标记。 然后，选择 **"下一步**"。 
   
   若要详细了解范围标记，请参阅 [使用基于角色的访问控制 (RBAC) 和分布式 IT 的范围标记](/mem/intune/fundamentals/scope-tags)。

9. 在 **"分配"** 选项卡上，指定应向其应用策略的用户和组，然后选择 **"下一步**"。  (若要了解有关分配的详细信息，请参阅 [Microsoft Intune.) 中分配用户和设备配置文件](/mem/intune/configuration/device-profile-assign)

10. 在 **"审阅 + 创建** "选项卡上，查看设置，然后选择 **"创建**"。

> [!TIP]
> 若要详细了解攻击面减少规则，请参阅以下资源：
> - [使用攻击面减少规则来避免感染恶意软件](attack-surface-reduction.md)
> - [查看攻击面减少规则列表](attack-surface-reduction-rules-reference.md)
> - [攻击面减少规则部署步骤 3：实现 ASR 规则](attack-surface-reduction-rules-deployment-implement.md)

### <a name="ransomware-mitigation"></a>勒索软件缓解

可以通过 [受控文件夹访问](controlled-folders.md#what-is-controlled-folder-access)获取勒索软件缓解，这仅允许受信任的应用访问终结点上受保护的文件夹。 

建议使用Microsoft Endpoint Manager配置受控文件夹访问权限。

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Microsoft Endpoint Manager门户中的 ASR 策略" lightbox="../../media/mde-p1/mem-asrpolicies.png":::

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 

2. 选择 **"终结点安全** 性"，然后选择 **"攻击面减少**"。

3. 选择 **+创建策略**。 

4. 对于 **平台**，请选择 **Windows 10和更高版本**，对于 **配置文件**，选择 **"攻击面减少"规则**。 然后选择" **创建**"。 

5. 在 **"基本信息"** 选项卡上，命名策略并添加说明。 选择 **下一步**。 

6. 在 **"配置设置"** 选项卡上的 **"攻击面减少规则"** 部分中，向下滚动到底部。 在 **"启用"文件夹保护** 下拉列表中，选择 **"启用**"。 可以选择性地指定以下其他设置：

   - 在 **需要保护的其他文件夹列表** 旁边，选择下拉菜单，然后添加需要保护的文件夹。
   - 在 **有权访问受保护文件夹的应用列表** 旁边，选择下拉菜单，然后添加应有权访问受保护文件夹的应用。
   - 在 **"从攻击面减少规则中排除文件和路径**"旁边，选择下拉菜单，然后添加需要从攻击面减少规则中排除的文件和路径。

   然后选择“**下一步**”。

7. 在 **"作用域标记"** 选项卡上，如果你的组织正在使用范围标记，请选择 **"+ 选择范围标记**"，然后选择要使用的标记。 然后，选择 **"下一步**"。 
   
   若要详细了解范围标记，请参阅 [使用基于角色的访问控制 (RBAC) 和分布式 IT 的范围标记](/mem/intune/fundamentals/scope-tags)。

8. 在 **"分配"** 选项卡上，选择 **"添加所有用户** "和 **"+ 添加所有设备**"，然后选择 **"下一步**"。  (可以交替指定特定的用户组或设备组。) 

9. 在 **"审阅 + 创建** "选项卡上，查看策略的设置，然后选择 **"创建**"。 该策略将应用于很快载入 Defender for Endpoint 的任何终结点。

### <a name="device-control"></a>设备控件

可以将 Defender for Endpoint 配置为阻止或允许可移动设备和可移动设备上的文件。 建议使用Microsoft Endpoint Manager配置设备控件设置。

:::image type="content" source="../../media/mde-p1/mem-admintemplates.png" alt-text="Microsoft Endpoint Manager管理模板" lightbox="../../media/mde-p1/mem-admintemplates.png":::

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 

2. 选择 **“设备”** > **“配置文件”** > **“创建配置文件”**。

3. 对于 **平台**，请选择 **Windows 10和更高版本**，对于 **配置文件类型**，请选择 **模板**。 

   在 **"模板名称"** 下，选择 **"管理模板**"，然后选择 **"创建**"。 

4. 在 **"基本信息"** 选项卡上，命名策略并添加说明。 选择 **下一步**。 

5. 在"**配置设置"** 选项卡上，选择 **"所有设置**"。 然后，在搜索框中键入 `Removable` 以查看与可移动设备相关的所有设置。

6. 在列表中选择一个项目，例如 **"所有可移动存储类：拒绝所有访问权限**"，以打开其浮出窗格。 每个设置的浮出控件说明了启用、禁用或未配置时会发生什么情况。 选择一个设置，然后选择 **"确定**"。 

7. 针对要配置的每个设置重复步骤 6。 然后选择“**下一步**”。

8. 在 **"作用域标记"** 选项卡上，如果你的组织正在使用范围标记，请选择 **"+ 选择范围标记**"，然后选择要使用的标记。 然后，选择 **"下一步**"。 
   
   若要详细了解范围标记，请参阅 [使用基于角色的访问控制 (RBAC) 和分布式 IT 的范围标记](/mem/intune/fundamentals/scope-tags)。

9. 在 **"分配"** 选项卡上，选择 **"添加所有用户** "和 **"+ 添加所有设备**"，然后选择 **"下一步**"。  (可以交替指定特定的用户组或设备组。) 

10. 在 **"审阅 + 创建** "选项卡上，查看策略的设置，然后选择 **"创建**"。 该策略将应用于很快载入 Defender for Endpoint 的任何终结点。

> [!TIP]
> 有关详细信息，请参阅[如何使用Microsoft Defender for Endpoint控制 USB 设备和其他可移动媒体](control-usb-devices-using-intune.md)。

### <a name="network-protection"></a>网络保护

通过网络保护，你可以帮助保护组织免受可能在 Internet 上托管网络钓鱼诈骗、攻击和其他恶意内容的危险域的侵害。 建议使用Microsoft Endpoint Manager启用网络保护。

:::image type="content" source="../../media/mde-p1/mem-endpointprotectionprofile.png" alt-text="Microsoft Endpoint Manager门户中的终结点保护配置文件" lightbox="../../media/mde-p1/mem-endpointprotectionprofile.png":::

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。 

2. 选择 **“设备”** > **“配置文件”** > **“创建配置文件”**。

3. 对于 **平台**，请选择 **Windows 10和更高版本**，对于 **配置文件类型**，请选择 **模板**。 

   在 **"模板名称"** 下，选择 **"终结点保护**"，然后选择 **"创建**"。 

4. 在 **"基本信息"** 选项卡上，命名策略并添加说明。 选择 **下一步**。 

5. 在 **"配置设置"** 选项卡上，展开 **Microsoft Defender 攻击防护**，然后展开 **网络筛选**。

   将 **网络保护** 设置为 **"启用**"。  (你可以选择 **"审核** "来查看网络保护最初在环境中的工作原理。) 

   然后选择“**下一步**”。

6. 在 **"分配"** 选项卡上，选择 **"添加所有用户** "和 **"+ 添加所有设备**"，然后选择 **"下一步**"。  (可以交替指定特定的用户组或设备组。) 

7. 在 **"适用性规则"** 选项卡上，设置一个规则。 要配置的配置文件将仅应用于满足你指定的组合条件的设备。 

   例如，可以选择将策略分配给仅运行特定 OS 版本的终结点。

   然后选择“**下一步**”。 

8. 在 **"审阅 + 创建** "选项卡上，查看策略的设置，然后选择 **"创建**"。 该策略将应用于很快载入 Defender for Endpoint 的任何终结点。

> [!TIP]
> 可以使用其他方法（例如Windows PowerShell或组策略）来启用网络保护。 若要了解详细信息，请参阅 ["启用网络保护](enable-network-protection.md)"。

### <a name="web-protection"></a>Web 保护

通过 Web 保护，可以保护组织的设备免受 Web 威胁和不需要的内容。 Web 保护包括 [Web 威胁防护](#configure-web-threat-protection) 和 [Web 内容筛选](#configure-web-content-filtering)。 配置这两组功能。 建议使用Microsoft Endpoint Manager配置 Web 保护设置。

#### <a name="configure-web-threat-protection"></a>配置 Web 威胁防护

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ，然后登录。
 
2. 选择 **Endpoint securityAttack** >  **surface reduction**，然后选择 **+ 创建策略**。

3. 选择一个平台，例如 **Windows 10及更高版本**，选择 **Web 保护** 配置文件，然后选择 **"创建**"。 

4. 在 **"基本信息"** 选项卡上，指定名称和说明，然后选择 **"下一步**"。

5. 在 **"配置设置"** 选项卡上，展开 **Web 保护**，在下表中指定设置，然后选择 **"下一步**"。 <br/><br/>

   | 设置 | 建议 |
   |:---|:---|
   | **启用网络保护** | 设置为 **"已启用**"。 阻止用户访问恶意网站或域。 <br/><br/>或者，可以将网络保护设置为 **审核模式** ，以了解其在环境中的工作原理。 在审核模式下，网络保护不会阻止用户访问站点或域，但它会将检测跟踪为事件。 |
   | **需要 SmartScreen Microsoft Edge 旧版** | 设置为 **"是**"。 帮助保护用户免受潜在的网络钓鱼诈骗和恶意软件的侵害。 |
   | **阻止恶意网站访问** | 设置为 **"是**"。 防止用户绕过有关潜在恶意网站的警告。 |
   | **阻止未经验证的文件下载** | 设置为 **"是**"。 防止用户绕过警告并下载未经验证的文件。 |

6. 在 **"作用域标记"** 选项卡上，如果你的组织正在使用范围标记，请选择 **"+ 选择范围标记**"，然后选择要使用的标记。 然后，选择 **"下一步**"。 
   
   若要详细了解范围标记，请参阅 [使用基于角色的访问控制 (RBAC) 和分布式 IT 的范围标记](/mem/intune/fundamentals/scope-tags)。

7. 在 **"分配"** 选项卡上，指定要接收 Web 保护策略的用户和设备，然后选择 **"下一步**"。

8. 在 **"审阅 + 创建** "选项卡上，查看策略设置，然后选择 **"创建**"。

> [!TIP]
> 若要了解有关 Web 威胁防护的详细信息，请参阅[保护组织免受 Web 威胁。](web-threat-protection.md)

#### <a name="configure-web-content-filtering"></a>配置 Web 内容筛选

1. 转到Microsoft 365 Defender门户 () [https://security.microsoft.com/](https://security.microsoft.com/) 并登录。

2. 选择 **设置** > **终结点**。

3. 在 **"规则"** 下，选择 **"Web 内容筛选**"，然后选择 **"+ 添加策略**"。

4. 在 **"添加策略** "浮出控件的" **常规** "选项卡上，为策略指定名称，然后选择 **"下一步**"。

5. 在 **"阻止"类别** 中，选择要阻止的一个或多个类别，然后选择 **"下一步**"。

6. 在" **作用域** "选项卡上，选择要接收此策略的设备组，然后选择 **"下一步**"。

7. 在 **"摘要** "选项卡上，查看策略设置，然后选择 **"保存**"。

> [!TIP]
> 若要详细了解如何配置 Web 内容筛选，请参阅 [Web 内容筛选](web-content-filtering.md)。

### <a name="network-firewall"></a>网络防火墙

网络防火墙有助于降低网络安全威胁的风险。 安全团队可以设置规则，确定允许哪些流量流向或流出组织的设备。 建议使用Microsoft Endpoint Manager配置网络防火墙。 

:::image type="content" source="../../media/mde-p1/mem-firewallpolicy.png" alt-text="Microsoft Endpoint Manager门户中的防火墙策略" lightbox="../../media/mde-p1/mem-firewallpolicy.png":::

若要配置基本防火墙设置，请执行以下步骤：

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ，然后登录。

2. 选择 **Endpoint** **securityFirewall** > ，然后选择 **+创建策略**。

3. 选择一个平台，例如 **Windows 10和更高版本**，选择 **Microsoft Defender 防火墙** 配置文件，然后选择 **"创建**"。 

4. 在 **"基本信息"** 选项卡上，指定名称和说明，然后选择 **"下一步**"。

5. 展开 **Microsoft Defender 防火墙**，然后向下滚动到列表底部。

6. 将以下每个设置设置设置为 **"是**"：

   - **为域网络启用 Microsoft Defender 防火墙** 
   - **为专用网络启用 Microsoft Defender 防火墙**
   - **为公共网络启用 Microsoft Defender 防火墙**
   
   查看每个域网络、专用网络和公共网络下的设置列表。 可以将其设置为 **"未配置**"，或根据组织的需求更改它们。

   然后选择“**下一步**”。

7. 在 **"作用域标记"** 选项卡上，如果你的组织正在使用范围标记，请选择 **"+ 选择范围标记**"，然后选择要使用的标记。 然后，选择 **"下一步**"。 
   
   若要详细了解范围标记，请参阅 [使用基于角色的访问控制 (RBAC) 和分布式 IT 的范围标记](/mem/intune/fundamentals/scope-tags)。

8. 在 **"分配"** 选项卡上，选择 **"添加所有用户** "和 **"+ 添加所有设备**"，然后选择 **"下一步**"。  (可以交替指定特定的用户组或设备组。) 

9. 在 **"审阅 + 创建** "选项卡上，查看策略设置，然后选择 **"创建**"。

> [!TIP]
> 防火墙设置是详细的，看起来可能很复杂。 请参阅有关[配置Windows Defender防火墙的最佳做法](/windows/security/threat-protection/windows-firewall/best-practices-configuring)。

### <a name="application-control"></a>应用程序控制

Windows Defender应用程序控制 (WDAC) 仅允许受信任的应用程序和进程运行，有助于保护Windows终结点。 大多数组织使用 WDAC 的分阶段部署。 也就是说，大多数组织一开始不会跨所有Windows终结点推出 WDAC。 事实上，根据组织Windows终结点是完全托管、轻松管理还是"自带设备"终结点，你可以在所有或某些终结点上部署 WDAC。

若要帮助规划 WDAC 部署，请参阅以下资源：

- [Windows 应用程序控制](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender应用程序控制策略设计决策](/windows/security/threat-protection/windows-defender-application-control/understand-windows-defender-application-control-policy-design-decisions)

- [Windows Defender不同方案中的应用程序控制部署：设备类型](/windows/security/threat-protection/windows-defender-application-control/types-of-devices)

## <a name="next-steps"></a>后续步骤

完成设置和配置过程后，下一步是开始使用 Defender for Endpoint。 

- [使用 Defender for Endpoint Plan 1 开始](mde-plan1-getting-started.md)
