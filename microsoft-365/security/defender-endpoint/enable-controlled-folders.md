---
title: 启用受控文件夹访问
keywords: 受控文件夹访问， windows 10， windows 11， windows defender， 勒索软件， 保护， 文件， 文件夹， 启用， 打开， 使用
description: 了解如何通过启用受控文件夹访问来保护重要文件
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.date: ''
ms.openlocfilehash: 4854ca235790cc8400f3f5a962e4bff203f86f98
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788119"
---
# <a name="enable-controlled-folder-access"></a>启用受控文件夹访问

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

[受控文件夹访问](controlled-folders.md) 有助于保护有价值的数据免受恶意应用和威胁（如勒索软件）的侵害。 受控文件夹访问权限包含在 Windows 10、Windows 11 和 Windows Server 2019 中。 受控文件夹访问也包含[在 Windows Server 2012R2 和 2016 的新式统一解决方案](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)中。

可以使用以下任一方法启用受控文件夹访问：

- [Windows 安全中心应用 *](#windows-security-app)
- [Microsoft Endpoint Manager](#endpoint-manager)
- [移动设备管理 (MDM)](#mobile-device-management-mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [组策略](#group-policy)
- [PowerShell](#powershell)

[审核模式](evaluate-controlled-folder-access.md) 允许测试该功能的工作原理 (和查看事件) ，而不会影响设备的正常使用。

禁用本地管理员列表合并的组策略设置将替代受控文件夹访问设置。 它们还会重写受保护的文件夹，并允许本地管理员通过受控文件夹访问设置的应用。 这些策略包括：

- Microsoft Defender 防病毒 **为列表配置本地管理员合并行为**
- System Center Endpoint Protection **允许用户添加排除项和替代**

有关禁用本地列表合并的详细信息，请参阅 [“阻止”或“允许用户在本地修改 Microsoft Defender AV 策略设置](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)”。

## <a name="windows-security-app"></a>Windows 安全中心应用

1. 通过选择任务栏中的盾牌图标打开Windows 安全中心应用。 还可以在“开始”菜单中搜索 **Windows 安全中心**。

2. 选择 **“病毒&威胁防护** ”磁贴 (或左侧菜单栏) 上的“防护”图标，然后选择 **“勒索软件保护**”。

3. 将 **受控文件夹访问权限** 的开关设置为 **“打开**”。

> [!NOTE]
> *此方法在 Windows Server 2012R2 或 2016 上不可用。
> 
> 如果使用 组策略、PowerShell 或 MDM CSP 配置了受控文件夹访问权限，则重启设备后，Windows 安全中心应用中的状态将发生更改。
> 如果使用上述任何工具将该功能设置为 **审核模式**，则Windows 安全中心应用将状态显示为 **“关闭**”。
> 如果要保护用户配置文件数据，建议用户配置文件应位于默认Windows安装驱动器上。

## <a name="endpoint-manager"></a>Endpoint Manager

1. 登录到 [Endpoint Manager](https://endpoint.microsoft.com)并打开 **Endpoint Security**。

2. 转到 **攻击面减少** \> **策略**。

3. 选择 **“平台**”，选择 **Windows 10和更高版本**，然后选择 **“创建** 配置文件 **攻击面减少规则**\>”。

4. 命名策略并添加说明。 选择 **下一步**。

5. 向下滚动到底部，选择 **“启用文件夹保护** ”下拉列表，然后选择 **“启用**”。

6. 选择 **需要保护的其他文件夹列表，** 并添加需要保护的文件夹。

7. 选择 **有权访问受保护文件夹的应用列表** ，并添加有权访问受保护文件夹的应用。

8. **从攻击面减少规则中选择“排除文件和路径**”，并添加需要从攻击面减少规则中排除的文件和路径。

9. 选择配置文件 **分配**，& **所有设备分配给所有用户**，然后选择 **“保存**”。

10. 选择 **“下一步** ”以保存每个打开的边栏选项卡，然后 **创建**。

    > [!NOTE]
    > 应用程序支持通配符，但不支持文件夹。 子文件夹不受保护。 允许的应用将继续触发事件，直到重新启动。

## <a name="mobile-device-management-mdm"></a>移动设备管理 (MDM)

使用 [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) 配置服务提供程序 (CSP) 允许应用对受保护的文件夹进行更改。

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. 在Microsoft Endpoint Configuration Manager中，转到 **资产和合规性** \> **Endpoint Protection Windows Defender** \> **攻击防护**。

2. 选择 **“主** \> **创建攻击防护策略**”。

3. 输入名称和说明，选择 **受控文件夹访问权限**，然后选择 **“下一步**”。

4. 选择是阻止还是审核更改、允许其他应用或添加其他文件夹，然后选择 **“下一步**”。

   > [!NOTE]
   > 应用程序支持通配符，但不支持文件夹。 子文件夹不受保护。 允许的应用将继续触发事件，直到重新启动。

5. 查看设置，然后选择 **“下一步** ”以创建策略。

6. 创建策略后， **关闭**。

## <a name="group-policy"></a>组策略

1. 在组策略管理设备上，打开 [组策略管理控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象，然后选择 **“编辑**”。

2. 在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。

3. 展开树以 **Windows组件> Microsoft Defender 防病毒 > Windows Defender Exploit Guard >受控文件夹访问权限**。

4. 双击“ **配置受控文件夹访问** 设置”，并将选项设置为 **“已启用**”。 在“选项”部分中，必须指定以下选项之一：
   - **启用** - 不允许恶意应用和可疑应用对受保护文件夹中的文件进行更改。 将在Windows事件日志中提供通知。
   - **禁用 (默认)** - 受控文件夹访问功能将不起作用。 所有应用都可以对受保护文件夹中的文件进行更改。
   - **审核模式** - 如果恶意或可疑应用尝试更改受保护文件夹中的文件，则允许更改。 但是，它将记录在Windows事件日志中，你可以在其中评估对组织的影响。
   - **仅阻止磁盘修改** - 不受信任的应用向磁盘扇区写入的尝试将记录在Windows事件日志中。 可在 **应用程序和服务日志** \> Microsoft \> Windows Windows Defender \> \>操作 \> ID 1123 中找到这些日志。
   - **仅审核磁盘修改** - 只会在应用程序 **和服务日**\>志 **Microsoft** \>  \> Windows下Windows事件日志 (**Windows Defender** \> **操作** \> **ID 1124**) 中记录写入受保护磁盘扇段的尝试。 不会记录修改或删除受保护文件夹中的文件的尝试。

    :::image type="content" source="../../media/cfa-gp-enable.png" alt-text="选择“组策略”选项“已启用”和“审核模式”" lightbox="../../media/cfa-gp-enable.png":::

> [!IMPORTANT]
> 若要完全启用受控文件夹访问权限，必须将组策略选项设置为 **“已启用”**，并在选项下拉菜单中选择 **“阻止**”。

## <a name="powershell"></a>PowerShell

1. 在"开始"菜单中键入 **powershell**，右键单击 **Windows PowerShell**，然后选择 **“以管理员身份运行**”。

2. 输入以下 cmdlet：

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

可以通过指定而不是`Enabled`指定来在审核模式下启用`AuditMode`该功能。

用于 `Disabled` 关闭该功能。

## <a name="see-also"></a>另请参阅

- [使用受控文件夹访问保护文重要件夹](controlled-folders.md)
- [自定义受控文件夹访问](customize-controlled-folders.md)
- [评估 Microsoft Defender for Endpoint](evaluate-mde.md)
