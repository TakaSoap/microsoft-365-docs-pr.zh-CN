---
title: Windows 安全应用中的 Microsoft Defender 防病毒
description: 借助 Windows 安全中心应用现在包含的 Microsoft Defender 防病毒，你可以查看、比较和执行常见任务。
keywords: wdav， 防病毒， 防火墙， 安全， windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 042bb67c223631ae1759b62a32c2f5713b4d62e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689922"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Windows 安全应用中的 Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

在 Windows 10 版本 1703 及更高版本中，Windows Defender应用是 Windows 安全性的一部分。

之前属于 Windows Defender 客户端和主 Windows 设置的设置已组合并移动到新应用，该应用默认作为 Windows 10 版本 1703 的一部分安装。

> [!IMPORTANT]
> 禁用 Windows 安全中心服务不会禁用 Microsoft Defender 防病毒或 [Windows Defender防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。 当安装第三方防病毒或防火墙产品并保持最新时，将自动禁用这些功能。
>
> 如果禁用 Windows 安全中心服务，或配置其关联的组策略设置以防止其启动或运行，Windows 安全应用可能会显示有关设备上安装的任何防病毒或防火墙产品的过时或不准确信息。
> 如果你拥有旧的或过时的第三方防病毒程序，或者如果你卸载之前可能安装的任何第三方防病毒产品，它也可能阻止 Microsoft Defender 防病毒自行启用。
> 这将显著降低设备的保护，并可能导致恶意软件感染。

有关 [可在应用中监视](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) 的其他 Windows 安全功能详细信息，请参阅 Windows 安全文章。

Windows 安全应用是 Windows 10 版本 1703 及更高版本上的客户端接口。 这不是用于查看和管理 Microsoft Defender for Endpoint 的 Microsoft [Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)安全中心 Web 门户。

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>查看 Windows 安全应用中的病毒和威胁防护设置

![Windows 安全应用中的病毒&威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

1. 通过单击任务栏中的防护图标或搜索 Defender 的开始菜单打开 Windows 安全 **应用**。

2. 选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。
   
以下各节介绍如何在查看或与 Windows 安全应用中的 Microsoft Defender 防病毒提供的威胁防护进行交互时执行一些最常见的任务。

> [!NOTE]
> 如果使用组策略配置和部署这些设置，本部分中所述的设置将灰出，并且无法用于各个终结点。 必须先通过组策略对象所做的更改部署到个别终结点，然后才能在 Windows 设置中更新设置。 配置 [最终用户与 Microsoft Defender 防病毒](configure-end-user-interaction-microsoft-defender-antivirus.md) 的交互主题介绍了如何配置本地策略覆盖设置。

## <a name="run-a-scan-with-the-windows-security-app"></a>使用 Windows 安全应用运行扫描

1. 通过搜索"安全"的"开始"菜单，然后选择"Windows 安全"，打开 **Windows 安全应用**。

2. 选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。

3. 选择 **快速扫描**。 或者，若要运行完全扫描，请选择"扫描选项"，然后选择一个选项，例如"**完全扫描"。**

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>查看安全智能更新版本，并下载 Windows 安全中心应用中的最新更新

![安全智能版本号信息](images/defender/wdav-wdsc-defs.png)

1. 通过搜索"安全"的"开始"菜单，然后选择"Windows 安全"，打开 **Windows 安全应用**。

2. 选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。

3. 选择 **病毒&威胁防护更新**。 将显示当前安装的版本以及一些有关下载时间的信息。 你可以根据可供手动下载的最新版本检查当前版本，或查看该版本的更改日志。 请参阅 [Microsoft Defender 防病毒和其他 Microsoft 反恶意软件的安全智能更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。

4. 选择 **"检查更新"，** 以下载 (保护更新（如果有) ）。

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>确保 Windows 安全中心应用中已启用 Microsoft Defender 防病毒

1. 通过搜索"安全"的"开始"菜单，然后选择"Windows 安全"，打开 **Windows 安全应用**。

2. 选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。

3. 选择 **病毒&威胁防护设置**。

4. 将 **"实时保护"开关切换** 为 **"开"。**

    > [!NOTE]
    > 如果关闭 **实时保护，** 它将在短暂延迟后自动重新启用。 这是为了确保你免受恶意软件和威胁的侵害。
    > 如果安装另一个防病毒产品，Microsoft Defender 防病毒将自动禁用自身，并且 Windows 安全中心应用中会进行此类指示。 将显示一个设置，允许您启用 [有限定期扫描](limited-periodic-scanning-microsoft-defender-antivirus.md)。

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>在 Windows 安全中心应用中添加 Microsoft Defender 防病毒的排除项

1. 通过搜索"安全"的"开始"菜单，然后选择"Windows 安全"，打开 **Windows 安全应用**。

2. 选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。

3. 在"**管理设置"下**，选择 **"病毒&威胁防护设置"。**

4. 在"**排除项"** 设置下，选择 **"添加或删除排除项"。** 

5. Select the plus icon () **+** to choose the type and set the options for each exclusion. 

下表汇总了排除类型以及发生的情况：

|排除类型  |定义者  |发生的情况  |
|---------|---------|---------|
|**File** |位置 <br/>示例：`c:\sample\sample.test` |Microsoft Defender 防病毒将跳过特定文件。 |
|**Folder**    |位置 <br/>示例：`c:\test\sample`       |Microsoft Defender 防病毒将跳过指定文件夹中的所有项目。         |
|**文件类型**   |文件扩展名 <br/>示例：`.test` |Microsoft Defender 防病毒将跳过设备上任意位置具有扩展 `.test` 名的所有文件。         |
|**进程**     |可执行文件路径 <br>示例：`c:\test\process.exe`         |Microsoft Defender 防病毒将跳过特定进程以及该进程打开的任何文件。         |

若要了解详细信息，请参阅以下资源：
- [根据文件扩展名和文件夹位置配置和验证排除项](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [为进程打开的文件配置排除项](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>查看安全中心应用中Windows Defender检测历史记录

1. 通过搜索"安全"的"开始"菜单，然后选择"Windows 安全"，打开 **Windows 安全应用**。

2. 选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。

3. 选择 **"保护历史记录"。** 将列出任何最近的项目。

## <a name="set-ransomware-protection-and-recovery-options"></a>设置勒索软件保护和恢复选项

1. 通过搜索"安全"的"开始"菜单，然后选择"Windows 安全"，打开 **Windows 安全应用**。

2. 选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。

3. 在 **勒索软件保护下**，选择 **管理勒索软件保护**。

4. 若要更改 **受控文件夹访问权限** 设置，请参阅使用受控 [文件夹访问权限保护重要文件夹](/microsoft-365/security/defender-endpoint/controlled-folders)。

5. 若要设置勒索软件恢复选项，请选择勒索软件数据恢复下的"设置"，并按照链接或设置 OneDrive 帐户的说明操作，以便你可以轻松从勒索软件攻击中恢复。

## <a name="see-also"></a>另请参阅
- [Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)