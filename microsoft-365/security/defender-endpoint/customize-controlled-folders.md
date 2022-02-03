---
title: 自定义受控文件夹访问
description: 添加应受受控文件夹访问权限保护的其他文件夹，或允许错误阻止对重要文件更改的应用。
keywords: 受控文件夹访问权限， windows 10， windows 11， windows defender， 勒索软件， 保护， 文件， 文件夹， 自定义， 添加文件夹， 添加应用， 允许， 添加可执行文件
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: m365initiative-m365-defender
ms.date: ''
ms.openlocfilehash: c290ad42702ddcb815880fedfe72d9de73065b8d
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322477"
---
# <a name="customize-controlled-folder-access"></a>自定义受控文件夹访问

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

受控文件夹访问权限可帮助你保护重要数据免受恶意应用和威胁（如勒索软件）的侵害。 受控文件夹访问权限在 Windows Server 2019、Windows Server 2022、Windows 10 和 Windows 11 客户端上受支持。 本文介绍如何自定义受控文件夹访问权限，并包括以下部分：

- [保护其他文件夹](#protect-additional-folders)
- [添加应允许访问受保护文件夹的应用](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [允许已签名的可执行文件访问受保护的文件夹](#allow-signed-executable-files-to-access-protected-folders)
- [自定义通知](#customize-the-notification)

> [!IMPORTANT]
> 受控文件夹访问权限监视应用是否检测到恶意活动。 有时，合法应用会阻止对文件进行更改。 如果受控文件夹访问权限影响组织的工作效率，可以考虑在审核模式下运行此功能，以全面评估影响。[](audit-windows-defender.md)

## <a name="protect-additional-folders"></a>保护其他文件夹

受控文件夹访问权限适用于许多系统文件夹和默认位置，包括文档、图片和 **电影等文件夹**。  可以添加要保护的其他文件夹，但不能删除默认列表中的默认文件夹。

当你不将文件存储在默认 Windows 库中，或者你已更改库的默认位置时，向受控文件夹访问权限添加其他文件夹可能会很有帮助。

还可以指定网络共享和映射驱动器。 支持环境变量和通配符。 有关使用通配符的信息，请参阅在文件名和文件夹路径或扩展名排除列表中 [使用通配符](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

可以使用 Windows 安全中心、组策略、PowerShell cmdlet 或移动设备管理配置服务提供程序添加和删除受保护的文件夹。

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>使用 Windows 安全中心 应用保护其他文件夹

1. 打开Windows 安全中心应用，选择任务栏中的防护图标，或搜索安全"开始"菜单。

2. 选择 **病毒&威胁防护**，然后向下滚动到 **勒索软件保护** 部分。

3. 选择 **管理勒索软件保护** 以打开 **勒索软件保护** 窗格。

4. 在" **受控文件夹访问权限"** 部分下，选择 **"受保护的文件夹"**。

5. 在 **"用户访问****控制"提示符上选择"是**"。 将显示 **"受保护的文件夹** "窗格。

6. 选择 **"添加受保护的文件夹"** ，然后按照提示添加文件夹。

### <a name="use-group-policy-to-protect-additional-folders"></a>使用组策略保护其他文件夹

1. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)。 

2. 右键单击要配置的组策略对象，然后选择"编辑 **"**。

3. 在组 **策略管理编辑器中**，转到计算机 **配置策略** \> **管理** \> **模板**。

4. 展开树以 **Windows攻击Microsoft Defender 防病毒** \> **Windows Defender** \> **受控**\>文件夹 **访问权限的组件**。 <br/>**注意**：在旧版 Windows，你可能会看到 **Windows Defender 防病毒而不是****Microsoft Defender 防病毒**。

5. 双击" **已配置的受保护文件夹**"，然后将该选项设置为 **"已启用"**。 选择 **"** 显示"，并指定要保护的每个文件夹。

6. 像通常一样部署组策略对象。

### <a name="use-powershell-to-protect-additional-folders"></a>使用 PowerShell 保护其他文件夹

1. 在 **"管理**"中"开始"菜单 PowerShell，右 **键单击"** Windows PowerShell并选择"以 **管理员角色运行"**

2. 键入以下 PowerShell cmdlet `<the folder to be protected>` ，将 替换为文件夹的路径 (例如) `"c:\apps\"` ：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. 对要保护的每个文件夹重复步骤 2。 受保护的文件夹在应用Windows 安全中心可见。

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="显示 cmdlet 的 PowerShell 窗口。":::

> [!IMPORTANT]
> 用于 `Add-MpPreference` 向列表追加或添加应用，而不是 `Set-MpPreference`。 `Set-MpPreference`使用 cmdlet 将覆盖现有列表。

### <a name="use-mdm-csps-to-protect-additional-folders"></a>使用 MDM CSP 保护其他文件夹

使用 [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) 配置服务提供程序 (CSP) 允许应用对受保护的文件夹进行更改。

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>允许特定应用对受控文件夹进行更改

你可以指定某些应用是否始终被视为安全应用，并授予对受保护文件夹中文件的写访问权限。 如果你知道和信任的特定应用被受控文件夹访问权限功能阻止，则允许应用非常有用。

> [!IMPORTANT]
> 默认情况下，Windows将视为友好的应用添加到允许列表中。 自动添加的此类应用不会记录在 Windows 安全中心 或关联的 PowerShell cmdlet 中显示的列表中。 你无需添加大多数应用。 仅在应用被阻止时添加应用，你可以验证其可信度。

添加应用时，必须指定应用的位置。 仅允许位于该位置的应用访问受保护的文件夹。 如果应用 (同名) 位于不同位置，它将不会添加到允许列表中，并且可能会受到受控文件夹访问权限的阻止。

允许的应用程序或服务在启动后仅对受控文件夹具有写访问权限。 例如，在允许更新服务停止并重新启动之前，该服务将继续触发事件。

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>使用 Windows Defender 安全应用允许特定应用

1. 通过Windows 安全中心"安全"的"开始"菜单打开"开始"**菜单**。

2. 选择病毒& **威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后选择管理 **勒索软件保护**。

3. 在受控 **文件夹访问权限** 部分下，选择 **允许应用通过受控文件夹访问权限**

4. 选择 **添加允许的应用** 并按照提示添加应用。

   :::image type="content" source="images/cfa-allow-app.png" alt-text="添加允许的应用按钮。":::

### <a name="use-group-policy-to-allow-specific-apps"></a>使用组策略允许特定应用

1. 在组策略管理设备上，打开组 [策略](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)管理控制台，右键单击要配置的组策略对象，**然后选择编辑。**

2. 在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。

3. 展开树以 **Windows攻击Microsoft Defender 防病毒** \> **Windows Defender** \> **受控**\>文件夹 **访问权限的组件**。

4. 双击"配置允许 **的应用程序"** 设置，将该选项设置为 **"已启用"**。 选择 **"显示** "并输入每个应用。

### <a name="use-powershell-to-allow-specific-apps"></a>使用 PowerShell 允许特定应用

1. 在 **"管理**"中"开始"菜单 PowerShell，右 **键单击"** Windows PowerShell并选择"以 **管理员角色运行"**
2. 输入以下 cmdlet：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    例如，若要添加位于 *C：\apps**test.exe* 可执行文件，cmdlet 将如下所示：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   继续使用 向 `Add-MpPreference -ControlledFolderAccessAllowedApplications` 列表中添加更多应用。 使用此 cmdlet 添加的应用将显示在Windows 安全中心应用中。

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="允许应用的 PowerShell cmdlet。":::

> [!IMPORTANT]
> 用于 `Add-MpPreference` 向列表中追加或添加应用。 `Set-MpPreference`使用 cmdlet 将覆盖现有列表。

### <a name="use-mdm-csps-to-allow-specific-apps"></a>使用 MDM CSP 允许特定应用

使用 [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) 配置服务提供程序 (CSP) 以允许应用对受保护的文件夹进行更改。

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>允许已签名的可执行文件访问受保护的文件夹

Microsoft Defender for Endpoint 证书和文件指示器可以允许已签名的可执行文件访问受保护的文件夹。 有关实现的详细信息，请参阅 [创建基于证书的指示器](indicator-certificates.md)。

> [!Note]
> 这不适用于脚本引擎，包括 Powershell

## <a name="customize-the-notification"></a>自定义通知

有关在触发规则并阻止应用或文件时自定义通知的信息，请参阅在 [Microsoft Defender for Endpoint 中配置警报通知](configure-email-notifications.md)。

## <a name="see-also"></a>另请参阅

- [使用受控文件夹访问保护文重要件夹](controlled-folders.md)
- [启用受控文件夹访问](enable-controlled-folders.md)
- [评估攻击面减少规则](evaluate-attack-surface-reduction.md)
