---
title: 为终结点计划 1 设置和配置 Microsoft Defender
description: 了解如何为终结点计划 1 设置和配置 Defender。 查看要求、规划推出和设置环境。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/03/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: a156b7232c20703c0f2eb320592a596e671d16f9
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61942724"
---
# <a name="set-up-and-configure-microsoft-defender-for-endpoint-plan-1"></a>为终结点计划 1 设置和配置 Microsoft Defender

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

本文介绍如何为终结点计划 1 设置和配置 Defender。 无论你是否获得帮助，都可以将本文用作整个部署的指南。  

## <a name="the-setup-and-configuration-process"></a>安装和配置过程

:::image type="content" source="images/mde-p1-deploymentflow.png" alt-text="适用于 Endpoint Plan 1 的 Microsoft Defender 的安装和部署流":::

适用于 Endpoint Plan 1 的 Defender 的常规安装和配置过程如下所示： <br/><br/>


| 数字  | 步骤  | 说明  |
|:---------:|:---------|:---------|
| 1 | [查看要求](#review-the-requirements)  | 列出许可、浏览器、操作系统和数据中心要求   |
| 2 | [规划部署](#plan-your-deployment) | 列出要考虑的几种部署方法，并包括指向更多资源的链接，以帮助您决定使用哪种方法  |
| 3 | [设置租户环境](#set-up-your-tenant-environment) | 列出设置租户环境的任务 |
| 4 | [分配角色和权限](#assign-roles-and-permissions) | 列出要考虑的安全团队的角色和权限 <br/><br/>**提示**：分配角色和权限后，安全团队就可以开始使用 Microsoft 365 Defender 门户。 若要了解更多信息，请参阅 [入门](mde-plan1-getting-started.md)。 |
| 5 | [载入到适用于终结点的 Defender](#onboard-to-defender-for-endpoint) | 列出操作系统载入到 Defender for Endpoint Plan 1 的几种方法，并包括指向每个方法的更多详细信息的链接  |
| 6  | [配置下一代保护](#configure-next-generation-protection) | 介绍如何在环境中配置下一代保护Microsoft Endpoint Manager  |
| 7  | [配置攻击面减少功能](#configure-your-attack-surface-reduction-capabilities)        | 列出你可以配置的攻击面减少功能类型，并包括包含指向更多资源的链接的过程  |
 
## <a name="review-the-requirements"></a>查看要求

下表列出了 Defender for Endpoint Plan 1 的基本要求：<br/><br/>

| 要求 | 说明 |
|:---|:---|
| 许可要求 | Defender for Endpoint 计划 1 |
| 浏览器要求 | Microsoft Edge <br/> Internet Explorer版本 11 <br/> Google Chrome |
| 操作系统 | Windows 10版本 1709 或更高版本 <br/>macOS：11.5 (Big Sur) 、10.15.7 (加泰罗尼亚语) 或 10.14.6 (Mojave)  <br/>iOS <br/>Android OS  |
| 数据中心版 | 以下数据中心位置之一： <br/>- 欧盟 <br/>- 英国 <br/>- 美国 |


## <a name="plan-your-deployment"></a>规划部署

规划部署时，可以从几种不同的体系结构和部署方法中选择。 每个组织都是唯一的，因此有几个选项需要考虑，如下表所列： <br/><br/>

| 方法 | 说明 |
|:---|:---|
| [Microsoft Intune (](/mem/intune/fundamentals/what-is-intune)中包含的Microsoft Endpoint Manager)  | 使用 Intune 在云本机环境中管理终结点 |
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和 Configuration [Manager](/mem/configmgr/core/understand/introduction) (包含在Microsoft Endpoint Manager)  | 使用 Intune 和 Configuration Manager 管理跨本地和云环境的终结点和工作负载 |
| [配置管理器](/mem/configmgr/core/understand/introduction) | 使用 Configuration Manager 通过 Defender for Endpoint 的基于云的功能保护本地终结点 |
| 从应用程序门户下载的本地Microsoft 365 Defender脚本 | 在终结点上使用本地脚本运行试点或载入几台设备 |

若要了解有关部署选项的详细信息，请参阅规划 [Defender for Endpoint 部署](deployment-strategy.md)。 此外，下载以下海报： 

[:::image type="content" source="../../media/defender-endpoint/mde-deployment-strategy.png" alt-text="部署策略海报缩略图":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)

**[获取部署海报](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)**

> [!TIP]
> 有关规划部署的更多详细信息，请参阅规划 Microsoft [Defender for Endpoint 部署](deployment-strategy.md)。

## <a name="set-up-your-tenant-environment"></a>设置租户环境

设置租户环境包括以下任务：

- 验证许可证
- 配置租户
- 仅在必要时配置 (设置) 
- 确保传感器正常工作，并报告数据到 Defender for Endpoint 

这些任务包含在 Defender for Endpoint 的安装阶段中。 请参阅[为终结点设置 Defender。](production-deployment.md)

## <a name="assign-roles-and-permissions"></a>分配角色和权限

若要访问安全Microsoft 365 Defender、配置 Defender for Endpoint 的设置或执行任务（如对检测到的威胁采取响应操作）。必须分配适当的权限。 Defender for Endpoint 使用[Azure Active Directory 中的内置角色](/azure/active-directory/roles/permissions-reference)。 

Microsoft 建议仅向用户分配执行其任务所需的权限级别。 可以使用基本权限管理或基于角色的访问控制来分配权限， ([](rbac.md) RBAC) 。 

- 通过基本权限管理，全局管理员和安全管理员具有完全访问权限，而安全读者则具有只读访问权限。
- 使用 RBAC，可以通过更多角色设置更精细的权限。 例如，你可以拥有安全读者、安全操作员、安全管理员、终结点管理员等。


下表介绍了组织中 Defender for Endpoint 要考虑的关键角色： <br/><br/>

| Role | 说明 |
|:---|:---|
| 全局管理员 (也称为全局管理员)  <br/><br/> *最佳做法是限制全局管理员的数量。* | 全局管理员可以执行所有类型的任务。 默认情况下，注册你的公司Microsoft 365 Microsoft Defender for Endpoint Plan 1 的人是全局管理员。 <br/><br/> 全局管理员能够跨所有门户访问/Microsoft 365设置，例如： <br/>- [https://admin.microsoft.com](https://admin.microsoft.com) Microsoft 365 管理中心 ()  <br/>- Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) ()  <br/>- Microsoft Endpoint Manager管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ()   |
| 安全管理员 (也称为安全管理员)  | 安全管理员可以执行安全操作员任务以及以下任务： <br/>- 监视与安全相关的策略 <br/>- 管理安全威胁和警报 <br/>- 查看报告 |
| 安全操作员 | 安全操作员可以执行安全读者任务以及以下任务： <br/>- 查看有关检测到的威胁的信息 <br/>- 调查和响应检测到的威胁  |
| 安全读者 | 安全读者可以执行以下任务： <br/>- 查看跨服务的安全Microsoft 365策略 <br/>- 查看安全威胁和警报 <br/>- 查看报告  |


> [!TIP]
> 若要了解有关用户角色Azure Active Directory，请参阅向具有管理员角色的用户分配管理员[和非](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)Azure Active Directory。 有关 Defender for Endpoint 的角色详细信息，请参阅 [基于角色的访问控制](prepare-deployment.md#role-based-access-control)。

## <a name="onboard-to-defender-for-endpoint"></a>载入到适用于终结点的 Defender

准备好载入组织的终结点后，可以从多种方法中选择，如下表所列： <br/><br/>

|终结点操作系统 | 载入方法|
|---|---|
| Windows 10 | [本地脚本 (最多 10 台设备) ](configure-endpoints-script.md) <br>  [组策略](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/移动设备管理器](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 脚本](configure-endpoints-vdi.md)  |
| macOS | [本地脚本](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [移动设备管理](mac-install-with-other-mdm.md) |
| iOS |[基于应用](ios-install.md) |
| Android | [Microsoft Endpoint Manager](android-intune.md) |

然后，继续配置下一代保护和攻击面减少功能。

## <a name="configure-next-generation-protection"></a>配置下一代保护

我们建议[Microsoft Endpoint Manager管理](/mem)组织的设备和安全设置，如下图所示：
 
:::image type="content" source="../../media/mde-p1/endpoint-policies.png" alt-text="MEM 中的终结点安全策略":::

若要在部署中配置下一代Microsoft Endpoint Manager，请按照以下步骤操作：

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。

2. 选择 **"终结点**  >  **安全防病毒"，** 然后选择现有策略。  (如果没有现有策略，请创建新策略。) 

3. 设置或更改防病毒配置设置。 需要帮助？ 请参阅以下资源： <br/>

   - [设置中Windows 10 Microsoft Defender 防病毒策略Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)
   - [在 iOS 功能上为终结点配置 Defender](ios-configure-features.md)

4. 指定完设置后，选择"审阅 **+ 保存"。**

## <a name="configure-your-attack-surface-reduction-capabilities"></a>配置攻击面减少功能

攻击面减少就是减少组织开放攻击的位置和方式。 Defender for Endpoint Plan 1 包括多个特性和功能，可帮助你减少跨终结点的攻击面。 下表列出了这些功能： <br/><br/>

| 功能 | 说明 |
|:---|:---|
| [攻击面减少规则](#attack-surface-reduction-rules) | 配置攻击面减少规则，以限制基于软件的风险行为并帮助确保组织安全。 攻击面减少规则针对某些软件行为，例如<br/>- 启动尝试下载或运行文件的可执行文件和脚本 <br/>- 运行模糊处理或其他可疑脚本 <br/>- 执行应用在正常日常工作期间通常不启动的行为 <br/><br/>此类软件行为有时在合法应用程序中可见。 但是，这些行为通常被视为有风险，因为它们通常被攻击者通过恶意软件滥用。  |
| [勒索软件缓解](#ransomware-mitigation) | 通过配置受控文件夹访问权限来设置勒索软件缓解功能，这有助于保护组织有价值的数据免受恶意应用和威胁（如勒索软件）的侵害。 | 
| [设备控制](#device-control) | 为组织配置设备控制设置，以允许或阻止可移动设备 (如 USB 驱动器) 。 | 
| [网络保护](#network-protection) | 设置网络保护以防止组织成员使用访问 Internet 上危险域或恶意内容的应用程序。 |
| [Web 保护功能](#web-protection) | 设置 Web 威胁防护来保护组织设备免受网络钓鱼网站、攻击站点和其他不受信任的或低信誉网站的威胁。 设置 Web 内容筛选，以根据网站的内容类别（如 (、高带宽、成人内容或法律责任等）跟踪和) 。 |
| [网络防火墙](#network-firewall) | 使用规则配置网络防火墙，这些规则确定允许哪些网络流量进入或来自组织的设备。 |
| [应用程序控制](#application-control)  | 如果希望仅允许受信任的应用程序和进程在受信任的设备上运行，请配置Windows规则。    |

### <a name="attack-surface-reduction-rules"></a>攻击面减少规则

攻击面减少规则适用于运行攻击Windows。 我们建议使用Microsoft Endpoint Manager，如下图所示：

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="攻击面减少规则Microsoft Endpoint Manager":::

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。

2. 选择 **终结点安全**  >  **攻击面减少**  >  **+ 创建策略**。

3. 对于 **平台**，请选择 **Windows 10 和更高版本**。

4. 对于 **配置文件**，选择 **攻击面减少规则**， **然后选择创建**。

5. 在"**基本信息"** 选项卡上，指定策略的名称和说明，然后选择"下一步 **"。**

6. 在配置 **设置选项卡上** ，展开 **攻击面减少规则**。

7. 指定每个规则的设置，然后选择"下一 **步"。**  (有关每个规则执行哪些功能的信息，请参阅攻击面减少 [规则](attack-surface-reduction.md).)  

8. 在" **范围标记** "选项卡上，如果组织正在使用范围标记，请选择 **"+ 选择** 范围标记"，然后选择想要使用的标记。 然后，选择"下 **一步"。** 
   
   若要了解有关范围标记的信息，请参阅使用基于角色的访问控制 ([RBAC](/mem/intune/fundamentals/scope-tags)) 分配 IT 的范围标记。

9. 在"**分配**"选项卡上，指定应应用策略的用户和组，然后选择"下一步 **"。**  (若要了解有关分配的信息，请参阅在 .Microsoft Intune [.) ](/mem/intune/configuration/device-profile-assign)

10. 在"**查看 + 创建"** 选项卡上，查看设置，然后选择"创建 **"。**

> [!TIP]
> 若要详细了解攻击面减少规则，请参阅以下资源：
> - [使用攻击面减少规则来避免感染恶意软件](attack-surface-reduction.md)
> - [查看攻击面减少规则列表](attack-surface-reduction-rules-reference.md)
> - [攻击面减少规则部署阶段 3：实施](attack-surface-reduction-rules-deployment-phase-3.md)

### <a name="ransomware-mitigation"></a>勒索软件缓解

通过受控文件夹访问权限获取勒索软件缓解 [，](controlled-folders.md#what-is-controlled-folder-access)这仅允许受信任的应用访问终结点上的受保护文件夹。 

我们建议使用 Microsoft Endpoint Manager配置受控文件夹访问权限。

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Microsoft Endpoint Manager 中的 ASR 策略":::

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。 

2. 选择 **"终结点安全性**"，然后选择"**攻击面减少"。**

3. 选择 **+ 创建策略**。 

4. 对于 **"平台****"，Windows 10** 和更高版本 **，对于配置文件**，选择攻击 **面减少规则**。 然后选择" **创建**"。 

5. 在 **"基本信息"** 选项卡上，为策略命名并添加说明。 选择 **下一步**。 

6. 在" **配置设置"** 选项卡上的" **攻击面** 减少规则"部分，向下滚动到底部。 在"**启用文件夹保护**"下拉列表中，选择"启用 **"。** 可以选择指定以下其他设置：

   - 在 **"需要保护的其他** 文件夹的列表"旁边，选择下拉菜单，然后添加需要保护的文件夹。
   - 在 **"有权访问** 受保护文件夹的应用列表"旁边，选择下拉菜单，然后添加应有权访问受保护文件夹的应用。
   - 在" **从** 攻击面减少规则中排除文件和路径"旁边，选择下拉菜单，然后添加需要从攻击面减少规则中排除的文件和路径。

   然后选择“**下一步**”。

7. 在" **范围标记** "选项卡上，如果组织正在使用范围标记，请选择 **"+ 选择** 范围标记"，然后选择想要使用的标记。 然后，选择"下 **一步"。** 
   
   若要了解有关范围标记的信息，请参阅使用基于角色的访问控制 ([RBAC](/mem/intune/fundamentals/scope-tags)) 分配 IT 的范围标记。

8. 在"**分配"** 选项卡上 **，选择"添加所有用户"和****"+ 添加所有设备**"，然后选择"下一 **步"。**  (你可以交替指定特定用户组或设备组。) 

9. 在"**查看 + 创建**"选项卡上，查看策略的设置，然后选择"创建 **"。** 该策略将应用于不久后载入到 Defender for Endpoint 的任何终结点。

### <a name="device-control"></a>设备控件

你可以将 Defender for Endpoint 配置为阻止或允许可移动设备上可移动设备和文件。 我们建议使用Microsoft Endpoint Manager配置设备控制设置。

:::image type="content" source="../../media/mde-p1/mem-admintemplates.png" alt-text="Microsoft Endpoint Manager管理模板":::

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。 

2. 选择“**设备**” > “**配置文件**” > “**创建配置文件**”。

3. 对于 **"** 平台 **"，Windows 10** 和更高版本，对于 **"配置文件类型**"，选择"**模板"。** 

   在 **"模板名称"** 下，**选择"管理模板"，** 然后选择"创建 **"。** 

4. 在 **"基本信息"** 选项卡上，为策略命名并添加说明。 选择 **下一步**。 

5. 在"**配置设置"** 选项卡上，选择"**所有设置"。** 然后在搜索框中， `Removable` 键入 以查看与可移动设备相关的所有设置。

6. 选择列表中的某个项，如"所有可移动存储 **类：拒绝** 所有访问"，以打开其飞出窗格。 每个设置的飞出图说明了启用、禁用或不配置此设置时会发生什么情况。 选择一个设置，然后选择"确定 **"。** 

7. 对要配置的每个设置重复步骤 6。 然后选择“**下一步**”。

8. 在" **范围标记** "选项卡上，如果组织正在使用范围标记，请选择 **"+ 选择** 范围标记"，然后选择想要使用的标记。 然后，选择"下 **一步"。** 
   
   若要了解有关范围标记的信息，请参阅使用基于角色的访问控制 ([RBAC](/mem/intune/fundamentals/scope-tags)) 分配 IT 的范围标记。

9. 在"**分配"** 选项卡上 **，选择"添加所有用户"和****"+ 添加所有设备**"，然后选择"下一 **步"。**  (你可以交替指定特定用户组或设备组。) 

10. 在"**查看 + 创建**"选项卡上，查看策略的设置，然后选择"创建 **"。** 该策略将应用于不久后载入到 Defender for Endpoint 的任何终结点。

> [!TIP]
> 有关详细信息，请参阅如何使用 Microsoft Defender for Endpoint 控制 [USB 设备和其他可移动媒体](control-usb-devices-using-intune.md)。

### <a name="network-protection"></a>网络保护

借助网络保护，可帮助保护组织免受可能承载 Internet 上欺诈邮件、攻击和其他恶意内容危险域的攻击。 我们建议使用Microsoft Endpoint Manager启用网络保护。

:::image type="content" source="../../media/mde-p1/mem-endpointprotectionprofile.png" alt-text="终结点保护配置文件Microsoft Endpoint Manager":::

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。 

2. 选择“**设备**” > “**配置文件**” > “**创建配置文件**”。

3. 对于 **"** 平台 **"，Windows 10** 和更高版本，对于 **"配置文件类型**"，选择"**模板"。** 

   在 **"模板名称"** 下，选择 **"终结点保护**"，然后选择"创建 **"。** 

4. 在 **"基本信息"** 选项卡上，为策略命名并添加说明。 选择 **下一步**。 

5. 在"**配置设置"** 选项卡上，展开 **"Microsoft Defender 攻击防护"，** 然后展开"网络 **筛选"。**

   将 **"网络保护"** 设置为 **"启用"。**  (可以选择"审核"，以首先查看网络保护在环境中) 

   然后选择“**下一步**”。

6. 在"**分配"** 选项卡上 **，选择"添加所有用户"和****"+ 添加所有设备**"，然后选择"下一 **步"。**  (你可以交替指定特定用户组或设备组。) 

7. 在" **适用性规则"** 选项卡上，设置规则。 你配置的配置文件将仅应用于符合你指定的组合条件的设备。 

   例如，你可以选择将策略分配给仅运行特定操作系统版本的终结点。

   然后选择“**下一步**”。 

8. 在"**查看 + 创建**"选项卡上，查看策略的设置，然后选择"创建 **"。** 该策略将应用于不久后载入到 Defender for Endpoint 的任何终结点。

> [!TIP]
> 可以使用其他方法（如Windows PowerShell组策略）启用网络保护。 若要了解更多信息，请参阅 [打开网络保护](enable-network-protection.md)。

### <a name="web-protection"></a>Web 保护

借助 Web 保护，你可以保护组织设备免受 Web 威胁和不需要的内容。 Web 保护包括 [Web 威胁防护](#configure-web-threat-protection) 和 [Web 内容筛选](#configure-web-content-filtering)。 配置这两组功能。 我们建议使用 Microsoft Endpoint Manager配置 Web 保护设置。

#### <a name="configure-web-threat-protection"></a>配置 Web 威胁防护

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，然后登录。
 
2. 选择 **"终结点安全**  >  **攻击面减少"，** 然后选择 **"+ 创建策略"。**

3. 选择平台（如 Windows 10 **及更高版本**）选择 **Web 保护** 配置文件，然后选择"创建 **"。** 

4. 在"**基本信息"** 选项卡上，指定名称和说明，然后选择"下一步 **"。**

5. 在"**配置设置"** 选项卡上，展开 **"Web 保护"，** 指定下表中的设置，然后选择"下一步 **"。** <br/><br/>

   | 设置 | 建议 |
   |:---|:---|
   | **启用网络保护** | 设置为已启用。 阻止用户访问恶意网站或域。 <br/><br/>或者，你可以将网络保护设置为 **审核模式** 以查看它在环境中如何工作。 在审核模式下，网络保护不会阻止用户访问网站或域，但会作为事件跟踪检测。 |
   | **需要 SmartScreen Microsoft Edge 旧版** | 设置为 **"是"。** 帮助保护用户免受潜在网络钓鱼欺诈和恶意软件的攻击。 |
   | **阻止恶意网站访问** | 设置为 **"是"。** 防止用户绕过有关潜在恶意网站的警告。 |
   | **阻止未经验证的文件下载** | 设置为 **"是"。** 防止用户绕过警告并下载未经验证的文件。 |

6. 在" **范围标记** "选项卡上，如果组织正在使用范围标记，请选择 **"+ 选择** 范围标记"，然后选择想要使用的标记。 然后，选择"下 **一步"。** 
   
   若要了解有关范围标记的信息，请参阅使用基于角色的访问控制 ([RBAC](/mem/intune/fundamentals/scope-tags)) 分配 IT 的范围标记。

7. 在"**分配**"选项卡上，指定要接收 Web 保护策略的用户和设备，然后选择"下一步 **"。**

8. 在"**查看 + 创建"** 选项卡上，查看策略设置，然后选择"创建 **"。**

> [!TIP]
> 若要了解有关 Web 威胁防护的信息，请参阅 [保护你的组织免受 Web 威胁](web-threat-protection.md)。

#### <a name="configure-web-content-filtering"></a>配置 Web 内容筛选

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com/](https://security.microsoft.com/) () 并登录。

2. 选择 **设置**  >  **终结点"。**

3. 在 **"规则**"下，**选择"Web 内容筛选**"，然后选择 **"+ 添加策略"。**

4. 在"**添加策略**"飞出控件中的 **"常规"** 选项卡上，指定策略的名称，然后选择"下一步 **"。**

5. 在"**被阻止的类别**"上，选择要阻止的一个或多个类别，然后选择"下一步 **"。**

6. 在"**范围**"选项卡上，选择要接收此策略的设备组，然后选择"下一步 **"。**

7. 在"**摘要"选项卡** 上，查看策略设置，然后选择"保存 **"。**

> [!TIP]
> 若要了解有关配置 Web 内容筛选的信息，请参阅 [Web 内容筛选](web-content-filtering.md)。

### <a name="network-firewall"></a>网络防火墙

网络防火墙有助于降低网络安全威胁的风险。 安全团队可以设置规则，以确定允许哪些流量流入或流出组织设备。 我们建议使用Microsoft Endpoint Manager配置网络防火墙。 

:::image type="content" source="../../media/mde-p1/mem-firewallpolicy.png" alt-text="防火墙策略Microsoft Endpoint Manager":::

若要配置基本防火墙设置，请按照以下步骤操作：

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，然后登录。

2. 选择 **"终结点安全**  >  **防火墙"，** 然后选择 **"+ 创建策略"。**

3. 选择平台（如 Windows 10 **及更高版本**）选择 **Microsoft Defender 防火墙** 配置文件，然后选择"创建 **"。** 

4. 在"**基本信息"** 选项卡上，指定名称和说明，然后选择"下一步 **"。**

5. 展开 **"Microsoft Defender 防火墙**"，然后向下滚动到列表底部。

6. 将以下每个设置都设置为 **"是"：**

   - **为域网络打开 Microsoft Defender 防火墙** 
   - **为专用网络打开 Microsoft Defender 防火墙**
   - **为公共网络打开 Microsoft Defender 防火墙**
   
   查看每个域网络、专用网络和公共网络下的设置列表。 你可以将其设置为"未 **配置"，** 也可以更改它们以满足组织的需求。

   然后选择“**下一步**”。

7. 在" **范围标记** "选项卡上，如果组织正在使用范围标记，请选择 **"+ 选择** 范围标记"，然后选择想要使用的标记。 然后，选择"下 **一步"。** 
   
   若要了解有关范围标记的信息，请参阅使用基于角色的访问控制 ([RBAC](/mem/intune/fundamentals/scope-tags)) 分配 IT 的范围标记。

8. 在"**分配"** 选项卡上 **，选择"添加所有用户"和****"+ 添加所有设备**"，然后选择"下一 **步"。**  (你可以交替指定特定用户组或设备组。) 

9. 在"**查看 + 创建"** 选项卡上，查看策略设置，然后选择"创建 **"。**

> [!TIP]
> 防火墙设置很详细，可能看起来很复杂。 请参阅[Best practices for configuring Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/best-practices-configuring)。

### <a name="application-control"></a>应用程序控制

Windows Defender应用程序控制 (WDAC) 仅允许运行受信任的应用程序和进程，帮助保护 Windows 终结点。 大多数组织都使用 WDAC 的分阶段部署。 也就是说，大多数组织最初不会在所有 Windows中推出 WDAC。 实际上，根据组织的 Windows 终结点是完全托管、轻型托管还是"自带设备"终结点，你可以在所有或某些终结点上部署 WDAC。

若要帮助规划 WDAC 部署，请参阅以下资源：

- [Windows 应用程序控制](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender应用程序控制策略设计决策](/windows/security/threat-protection/windows-defender-application-control/understand-windows-defender-application-control-policy-design-decisions)

- [Windows Defender方案（设备类型）中部署应用程序控制](/windows/security/threat-protection/windows-defender-application-control/types-of-devices)

## <a name="next-steps"></a>后续步骤

现在，你已完成安装和配置过程，下一步是开始使用 Defender for Endpoint。 

- [适用于终结点计划 1 的 Defender 入门](mde-plan1-getting-started.md)