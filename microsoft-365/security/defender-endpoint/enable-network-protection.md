---
title: 启用网络保护功能
description: 使用组策略、PowerShell 或移动设备管理和配置管理器启用网络保护。
keywords: 网络保护， 攻击， 恶意网站， ip， 域， 启用， 打开
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.date: ''
ms.openlocfilehash: acf474f472450456014a581366c8860d87607a79
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322641"
---
# <a name="turn-on-network-protection"></a>启用网络保护功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

[网络](network-protection.md) 保护有助于防止员工使用任何应用程序访问可能承载网络钓鱼欺诈、攻击和 Internet 上的其他恶意内容危险域。 可以在 [测试环境中](evaluate-network-protection.md) 审核网络保护，以查看在启用应用之前将阻止哪些应用。

[了解有关网络筛选配置选项的详细信息。](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>检查网络保护是否已启用

使用注册表编辑器检查是否在本地设备上启用了网络保护。

1. 选择任务栏 **中的** "开始"按钮，然后键入 **regedit** 以打开注册表编辑器。

2. 从 **HKEY_LOCAL_MACHINE** 菜单中选择"选项"。

3. 在嵌套菜单中导航到 **软件** \>  \>策略 **Microsoft** \> **Windows Defender Windows Defender** \> **Exploit Guard** \> **网络保护**。

如果密钥缺失，请导航到 **软件** \> **Microsoft** \> **Windows Defender** \> **Windows Defender Exploit Guard** \> **网络保护**。

4. 选择 **EnableNetworkProtection** 以查看设备上网络保护的当前状态：

   - 0 或 **Off**
   - 1 或 **On**
   - 2 或 **审核** 模式

    :::image type="content" alt-text="网络保护注册表项。" source="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png" lightbox="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png":::

## <a name="enable-network-protection"></a>启用网络保护

使用以下任一方法启用网络保护：

- [PowerShell](#powershell)
- [移动设备管理 (MDM)](#mobile-device-management-mdm)
- [Microsoft Endpoint Manager](#microsoft-endpoint-manager)
- [组策略](#group-policy)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)

### <a name="powershell"></a>PowerShell

1. 在 **"管理"中"开始"菜单 powershell**，右 **键单击"** Windows PowerShell并选择"以 **管理员角色运行"**。

2. 输入以下 cmdlet：

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. 可选：使用下列 cmdlet 在审核模式下启用该功能：

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    使用 `Disabled` 而不是 `AuditMode` 或 `Enabled` 来关闭该功能。

### <a name="mobile-device-management-mdm"></a>移动设备管理(MDM)

使用 [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) 配置服务提供程序 (CSP) 启用或禁用网络保护或启用审核模式。

### <a name="microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

1. 登录到管理Microsoft Endpoint Manager中心 (https://endpoint.microsoft.com)。

2. 转到 **DevicesConfiguration** >  **配置文件** > **创建配置文件**。

3. 在" **创建配置文件"飞** 出控件中，选择" **平台** "，然后选择" **配置文件类型** 为 **模板"**。

4. 在"**模板名称"****中，** 从模板列表中选择"终结点保护"，然后选择"创建 **"**。

4. 转到 **Endpoint** **protectionBasics** > ，为配置文件提供名称，然后选择"下一步 **"**。

5. 在"**配置设置"** 部分，**转到"** > Microsoft Defender 攻击防护 **网络筛选** > **""网络保护** > **""可更新"或**"**审核"**。 选择“**下一步**”。

6. 根据组织 **需要****，选择** 适当的 **范围** 标记、分配和适用性规则。 管理员可以设置更多要求。

7. 查看所有信息，然后选择"创建 **"**。

### <a name="group-policy"></a>组策略

使用以下过程在加入域的计算机或独立计算机上启用网络保护。

1. 在独立计算机上，转到"开始 **"** ，然后键入并选择" **编辑组策略"**。

    *-Or-*

    在加入域的组策略管理计算机上，打开组策略 [](https://technet.microsoft.com/library/cc731212.aspx)管理控制台，右键单击要配置的组策略对象，然后选择"编辑 **"**。

2. 在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。

3. 展开树以 **Windows Exploit** \> **Guard** \> **网络Microsoft Defender 防病毒Windows Defender** \> **组件**。

   > [!NOTE]
   > 在早期版本的 Windows 中，组策略路径可能Windows Defender 防病毒"而不是"Microsoft Defender 防病毒"。

4. 双击阻止用户和应用 **访问** 危险网站设置，并设置该选项为 **已启用**。 在选项部分中，必须指定以下选项之一：
    - **阻止** - 用户无法访问恶意 IP 地址和域。
    - **禁用 (默认)** - 网络保护功能不起作用。 不会阻止用户访问恶意域。
    - **审核模式** - 如果用户访问恶意 IP 地址或域，事件将记录在Windows日志中。 但是，不会阻止用户访问地址。

   > [!IMPORTANT]
   > 若要完全启用网络保护，必须将组策略选项设置为 **已启用**，还要在选项下拉菜单中选择阻止。

使用注册表编辑器确认在本地计算机上启用网络保护：

1. 选择 **"开始** " **并键入 regedit** 以 **打开注册表编辑器**。

2. 导航到 **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. 选择 **EnableNetworkProtection** 并确认值：
   - 0=Off
   - 1=打开
   - 2=审核

### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. 打开 Configuration Manager 控制台。

2. 转到"**资产和合规性** >  > **Endpoint Protection** **Windows Defender攻击防护"**。 

3. 从 **功能区选择** "创建攻击防护策略"以创建新策略。
   - 若要编辑现有策略，请选择该策略，然后从功能区或右键单击菜单中选择"属性"。 编辑" **网络保护"选项卡** 中的"配置 **网络保护"** 选项。  

4. 在 **"常规** "页上，指定新策略的名称并验证 **"网络保护** "选项是否已启用。 

5. 在 **"网络保护** "页上，为"配置网络保护"选项选择以下 **设置之** 一：
   - **阻止**
   - **审核**
   - **Disabled**
   
6. 完成其余步骤，并保存策略。 

7. 从功能区中， **选择"部署** "以将策略部署到集合。

> [!IMPORTANT]
> 从 Configuration Manager 部署攻击防护策略后，如果你删除部署，将不会从客户端中删除攻击防护设置。 `Delete not supported` 如果你删除客户端的 Exploit Guard 部署，则记录在 Configuration Manager 客户端的 ExploitGuardHandler.log 中。 <!--CMADO8538577-->
> 以下 PowerShell 脚本可以在系统上下文下运行，以删除这些设置：<!--CMADO9907132-->
>
> ```powershell
> $defenderObject = Get-WmiObject -Namespace "root/cimv2/mdm/dmmap" -Class "MDM_Policy_Config01_Defender02" -Filter "InstanceID='Defender' and ParentID='./Vendor/MSFT/Policy/Config'"
> $defenderObject.AttackSurfaceReductionRules = $null
> $defenderObject.AttackSurfaceReductionOnlyExclusions = $null
> $defenderObject.EnableControlledFolderAccess = $null
> $defenderObject.ControlledFolderAccessAllowedApplications = $null
> $defenderObject.ControlledFolderAccessProtectedFolders = $null
> $defenderObject.EnableNetworkProtection = $null
> $defenderObject.Put()
>
> $exploitGuardObject = Get-WmiObject -Namespace "root/cimv2/mdm/dmmap" -Class "MDM_Policy_Config01_ExploitGuard02" -Filter "InstanceID='ExploitGuard' and ParentID='./Vendor/MSFT/Policy/Config'"
> $exploitGuardObject.ExploitProtectionSettings = $null
> $exploitGuardObject.Put()
>```  

## <a name="see-also"></a>另请参阅

- [网络保护功能](network-protection.md)

- [网络保护和 TCP 三向握手](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [网络保护功能评估](evaluate-network-protection.md)

- [网络保护疑难解答](troubleshoot-np.md)
