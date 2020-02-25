---
title: 自行注册现有设备
description: 注册重新使用的设备你可能已经有了你自己的设备，以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a971d8dc413e7794aa48c0b39cc0f42e511739ed
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250442"
---
# <a name="register-existing-devices-yourself"></a>自行注册现有设备

>[!NOTE]
>本主题介绍了重新使用已拥有的设备的步骤，并将其注册到 Microsoft 托管桌面。 如果您正在使用全新的设备，请按照在[Microsoft 托管桌面中注册新设备](register-devices-self.md)中的步骤操作。

合作伙伴的过程记录在[合作伙伴注册设备的步骤](register-devices-partner.md)中。

Microsoft 托管桌面可以与全新设备配合使用，也可以重新使用可能已有的设备（这将需要您对其进行重新映像）。 您可以使用 Azure 门户上的 Microsoft 托管桌面注册设备。

## <a name="prepare-to-register-existing-devices"></a>准备注册现有设备


若要注册现有设备，请按照下列步骤操作：

1. [获取每个设备的硬件哈希。](#obtain-the-hardware-hash)
2. [合并哈希数据](#merge-hash-data)
3. [在 Microsoft 托管桌面中注册设备](#register-devices)。
4. [请仔细检查图像是否正确。](#check-the-image)
5. [传递设备](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>获取硬件哈希

Microsoft 托管桌面通过引用其硬件哈希来唯一标识每个设备。 你可以通过四个选项从已在使用的设备中获取此信息：

- 向 OEM 提供商咨询 AutoPilot 注册文件，其中将包含硬件哈希值。
- 在[配置管理器](#configuration-manager)中创建自定义报表。
- 在每台设备上使用[Active Directory](#active-directory-powershell-script-method)或[手动](#manual-powershell-script-method)运行 Windows PowerShell 脚本--并在文件中收集结果。
- 启动每个设备--但不完成 Windows 安装程序体验，并[收集可移动闪存驱动器上的哈希值](#flash-drive-method)。

#### <a name="configuration-manager"></a>Configuration Manager

您可以使用 Microsoft 终结点配置管理器收集要使用 Microsoft 托管桌面注册的现有设备的硬件哈希值。

> [!IMPORTANT]
> 要获取此信息的任何设备都必须运行 Windows 10 版本1703或更高版本。 此外，还需要一个设备，该设备是连接到配置管理器（"当前分支"）网站的 Configuration Manager 客户端。 您还需要在启用了 SQL Server Reporting Services 的环境中设置报告点站点系统角色。 

如果你已满足所有这些先决条件，则可以按照以下步骤收集信息：

1. 在 Configuration Manager 控制台中，选择 "**监控**"。 
2. 在 "监控" 工作区中，展开 "**报告**"，然后选择 "**报告**"。 
3. 在 "**开始**" 选项卡上的 "**创建**" 部分，选择 "**创建报告**" 以打开 "创建报告向导"。 
4. 在 "**信息**" 页面上，设置以下设置： 
    - **名称：** 指定报表的名称。 
    - **说明：** 指定报表的说明。 
    - **服务器：** 显示要在其上创建此报告的报表服务器的名称。 
    - **路径：** 选择 "**浏览**" 以指定要在其中存储报告的文件夹。 
5. 选择“下一步”****。 
6. 在 "**摘要**" 页上，查看设置。 选择 "**上一**步" 更改设置，或选择 "**下一步**" 在配置管理器中创建报表。 
7. 在 "**完成**" 页上，选择 "**关闭**" 退出向导，并打开 "**报告生成器**" 以输入报告设置。 如果出现提示，请输入您的用户帐户和密码，然后选择 **"确定"。** 如果设备上未安装报表生成器，则系统会提示您安装它。 选择 "**运行" 以安装 "报告生成器**"，这是修改和创建报告所必需的。 


**在 Microsoft Report Builder 中**，提供报表的 SQL 语句，并执行以下步骤：

1. 在左窗格中，选择 "**数据集**"，然后右键单击以**添加数据集**。
2. 转到 "**查询**" 选项卡，然后输入名称为*DataSet0*。 
3. 选择 **"使用嵌入到我的报表中的数据集"**;将打开 "报告生成器"。
4. 在**报表生成器**中，选择 "**数据源：**"。 选择应以 "AutoGen" 开头的默认数据源。 
5. 选择 "**查询类型" 作为文本**，然后输入以下查询：




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. 导航到 "**字段**" 选项卡，应已填充**字段名称**和**字段源**的 wehre 值。 如果不是，请选择 "**添加**"，然后选择 "**查询字段**"。 输入**字段名称**和**字段源**。
6. 对以下每个值重复上述操作： 
    - 负责 
    - 模型 
    - Serial_Number 
    - HardwareHash
7. 选择“**确定**”。

接下来，通过执行以下步骤来**定义报告显示和创建报告**：

1. 选择**表或矩阵**;将打开一个新的向导。
2. 在 "**选择数据集**" 中，选择 "**选择此报告中的现有数据集" 或 "共享数据集**"。  
3. 选择 " **DataSet0** " （默认值），然后选择 "**下一步**"。
4. 将 "**制造商**"、"**模型**" 和 "**序列号**" 拖到 "**行组**" 框中。 将**HardwareHash**拖到 "**值**" 框中，然后选择 "**下一步**"。
5. 清除 "**显示分类汇总和**总计" 和 "**展开/折叠组**" 复选框。 选择“下一步”****。
6. 选择“完成”****。
7. 选择 "**运行**" 运行报告。 验证报告是否提供了您所需的信息。 如有必要，选择 "**设计**" 以返回到 "设计" 视图以修改报告。
8. 选择 "**保存**" 将报告保存到报告服务器。 您可以在 "监控" 工作区的 "报告" 节点中运行新报告。 

**最后，按以下步骤导出报告并使用它来注册设备**。 （如果您在前面的步骤中导航掉了，则只需遵循本节中的步骤1和步骤2。）：

1. 在 Configuration Manager 控制台中，选择 "**监控**"。
2. 在 "**监视**" 中，展开 "**报告**"，然后选择 "**报告**"。
3. 使用之前创建的名称查找报告。
4. 右键单击此报告，然后选择 "**运行**"。
5. 在打开的对话框中，选择 "**导出**"，然后选择 "**另存为 CSV**"。
6. 此版本的报告将从配置管理器与之通信的所有 Windows 10 设备中提取哈希。 你将需要筛选结果，使其仅包含计划注册到 Microsoft 托管桌面的那些设备。


> [!IMPORTANT]
> Configuration Manager 中的查询不允许导出的列名称中包含空格;这就是为什么这些步骤输入 "Serial_Number" 和 "HardwareHash" 的原因所在。 现在，您已导出了 CSV 文件，您必须编辑报告标头，以便阅读此处所示的*序列号*和*硬件哈希*，然后再继续执行设备注册。

现在，你可以继续[使用 Azure 门户注册设备](#register-devices-by-using-the-azure-portal)。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell 脚本方法

在 Active Directory 环境中，您可以使用`Get-MMDRegistrationInfo` PowerShell Cmdlet 从 Active directory 组中的设备远程收集信息，方法是使用 WinRM。 您还可以使用`Get-AD Computer` cmdlet 并获取目录中包含的特定硬件模型名称的筛选结果。 为此，请首先确认这些先决条件，然后继续执行以下步骤：

- 启用 WinRM。
- 要注册的设备在网络上是活动的（即，它们未断开连接或已关闭）。
- 请确保您有一个具有在设备上远程执行的权限的域凭据参数。
- 请确保 Windows 防火墙允许访问 WMI。 为此，请按照以下步骤操作：
    1. 打开**Windows Defender 防火墙**控制面板，然后选择 "**允许通过 Windows defender 防火墙的应用程序或功能**"。
    2. 在列表中查找**Windows Management Instrumentation （WMI）** ，启用 "**专用" 和 "公用**"，然后选择 **"确定"**。

1.  打开具有管理权限的 PowerShell 提示。
2.  运行以下*任意一个*脚本：
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. 访问可能包含设备条目的任何目录。 从*所有*目录中删除每个设备的条目，包括 Windows Server Active Directory 域服务和 Azure Active directory。 请注意，此删除操作可能需要几个小时才能完成。
4. 可能包含设备条目的 Access management services。 从*所有*管理服务（包括 Microsoft 终结点配置管理器、microsoft Intune 和 Windows Autopilot）中删除每个设备的条目。 请注意，此删除操作可能需要几个小时才能完成。

现在，你可以继续[注册设备](#register-devices)。

#### <a name="manual-powershell-script-method"></a>手动 PowerShell 脚本方法

1.  打开具有管理权限的 PowerShell 提示。
2.  以`Install-Script -Name Get-MMDRegistrationInfo`
3.  以`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [合并哈希数据。](#merge-hash-data)

#### <a name="flash-drive-method"></a>闪存驱动器方法

1. 在要注册的设备以外的其他设备上，插入 u 盘。
2. 打开具有管理权限的 PowerShell 提示。
3. 以`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. 打开要注册的设备，但*不要启动安装程序体验*。 如果您意外启动了设置体验，则必须重置或重新映像设备。
5. 插入 u 盘，然后按 SHIFT + F10。
6. 打开具有管理权限的 PowerShell 提示符，然后运行`cd <pathToUsb>`。
7. 以`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. 以`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. 删除 USB 驱动器，然后通过运行来关闭设备`shutdown -s -t 0`
10. [合并哈希数据。](#merge-hash-data)

>[!IMPORTANT]
>在完成注册后，请不要再打开要注册的设备。 



### <a name="merge-hash-data"></a>合并哈希数据

如果您通过手动 PowerShell 或闪存驱动器方法收集了硬件哈希数据，则您现在需要将 CSV 文件中的数据组合到单个文件中才能完成注册。 下面是一个示例 PowerShell 脚本，可轻松实现此操作：

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

将哈希数据合并到一个 CSV 文件中，现在就可以继续[注册设备了](#register-devices)。

### <a name="register-devices"></a>注册设备

CSV 文件必须为注册的特定格式。 如果您在前面的步骤中收集数据，则该文件应具有正确的格式;如果从供应商获取文件，则可能需要调整格式。

>[!NOTE]
>为方便起见，可以下载此 CSV 文件的[模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。

您的文件需要包含与示例1（制造商、模型等）**完全相同的列标题**，但您自己的数据用于其他行。 如果使用模板，请在文本编辑工具（如记事本）中打开它，并考虑仅保留第1行中的所有数据，仅在第2行和更低的行中输入数据。 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>如果您忘记更改任何示例数据，则注册将失败。

#### <a name="register-devices-by-using-the-azure-portal"></a>使用 Azure 门户注册设备

在 Microsoft 托管桌面[Azure 门户](https://aka.ms/mmdportal)中，在左侧导航窗格中选择 "**设备**"。 选择 **+ 注册设备**;将打开 "飞入"：

[![选择注册设备后飞入，列出分配的用户的列设备、序列号、状态、上次查看日期和期限](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (遗憾的是这不成立。我们可以删除此注释-但现在将其保留，直到我们有机会聊天它。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


请按以下步骤操作：

1. 在 "**文件上载**" 中，提供以前创建的 CSV 文件的路径。
2. （可选）可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。 这些值没有格式要求。
3. 选择 "**注册设备**"。 系统会将设备添加到**设备边栏**上的设备列表中，并标记为 "**注册挂起**"。 注册通常需要不到10分钟的时间，如果成功，设备将显示为 "已**准备就绪**，以供用户使用"，表示它已准备就绪，正在等待最终用户开始使用。


你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。 可能报告的状态包括：

| 状态 | 说明 |
|---------------|-------------|
| 注册挂起 | 注册尚未完成。 稍后再次查看。 |
| 注册失败 | 无法完成注册。 有关详细信息，请参阅[设备注册故障排除](#troubleshooting-device-registration)。 |
| 为用户准备就绪 | 注册成功，现在设备已准备好传递给最终用户。 Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。 |
| 活动 | 设备已传递给最终用户，并且已向其注册了你的租户。 这也表明它们是定期使用设备的。 |
| 不再 | 设备已传递给最终用户，并且已向其注册了你的租户。 但是，他们最近未使用设备（最近7天）。  | 

#### <a name="troubleshooting-device-registration"></a>设备注册故障排除

| 错误消息 | 详细信息 |
|---------------|-------------|
| 找不到设备 | 无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。 请与设备供应商确认这些值。 |
| 硬件哈希无效 | 为此设备提供的硬件哈希格式不正确。 仔细检查硬件哈希，然后重新提交。 |
| 已注册设备 | 此设备已注册到你的组织。 无需执行进一步操作。 |
| 其他组织声明的设备 | 此设备已由其他组织声明。 请与设备供应商联系。 |
| 意外错误 | 无法自动处理你的请求。 联系支持人员并提供请求 ID：<requestId> |

### <a name="check-the-image"></a>检查图像

如果你的设备来自 Microsoft 托管桌面合作伙伴提供商，则该映像应正确。

如果你愿意，也可以在自己自己应用图像。 若要开始，请联系你正在使用的 Microsoft 代表，他们将为你提供应用此图像的位置和步骤。

### <a name="deliver-the-device"></a>传递设备

> [!IMPORTANT]
> 在将设备交给用户之前，请确保已为该用户获取并应用了[相应的许可证](../get-ready/prerequisites.md)。

如果应用了所有许可证，则可以[让用户准备好使用设备](get-started-devices.md)，然后你的用户可以启动设备并继续执行 Windows 安装体验。









