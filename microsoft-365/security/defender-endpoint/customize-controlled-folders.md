---
title: 自定义受控文件夹访问
description: 添加应受控文件夹访问保护的其他文件夹，或允许错误地阻止对重要文件的更改的应用。
keywords: 受控文件夹访问， windows 10， windows 11， windows defender， 勒索软件， 保护， 文件， 文件夹， 自定义， 添加文件夹， 添加应用， 允许， 添加可执行文件
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
ms.collection: M365-security-compliance
ms.date: ''
ms.openlocfilehash: 5b941cf40a220f2d9298a4918d334349f784dd13
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789879"
---
# <a name="customize-controlled-folder-access"></a>自定义受控文件夹访问

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

> [!TIP]
> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

受控文件夹访问有助于保护有价值的数据免受恶意应用和威胁（如勒索软件）的侵害。 Windows Server 2019、Windows Server 2022、Windows 10 和Windows 11 客户端支持受控文件夹访问权限。 本文介绍如何自定义受控文件夹访问功能，并包括以下部分：

- [保护其他文件夹](#protect-additional-folders)
- [添加应允许访问受保护文件夹的应用](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [允许已签名的可执行文件访问受保护的文件夹](#allow-signed-executable-files-to-access-protected-folders)
- [自定义通知](#customize-the-notification)

> [!IMPORTANT]
> 受控文件夹访问会监视检测到为恶意活动的应用。 有时，合法应用会被阻止对文件进行更改。 如果受控文件夹访问会影响组织的工作效率，则可以考虑在 [审核模式](audit-windows-defender.md) 下运行此功能，以充分评估其影响。

## <a name="protect-additional-folders"></a>保护其他文件夹

受控文件夹访问权限适用于许多系统文件夹和默认位置，包括文 **档**、 **图片** 和 **电影** 等文件夹。 可以添加要保护的其他文件夹，但不能删除默认列表中的默认文件夹。

如果未将文件存储在默认Windows库中，或者更改了库的默认位置，则将其他文件夹添加到受控文件夹访问可能会有所帮助。

还可以指定网络共享和映射驱动器。 支持环境变量和通配符。 有关使用通配符的信息，请参阅 [文件名和文件夹路径或扩展排除列表中的使用通配符](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

可以使用Windows 安全中心应用、组策略、PowerShell cmdlet 或移动设备管理配置服务提供程序来添加和删除受保护的文件夹。

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>使用Windows 安全中心应用保护其他文件夹

1. 通过选择任务栏中的盾牌图标或在"开始"菜单中搜索 *安全* 性来打开Windows 安全中心应用。

2. 选择 **病毒&威胁防护**，然后向下滚动到 **勒索软件保护** 部分。

3. 选择 **“管理勒索软件保护** ”以打开 **“勒索软件保护** ”窗格。

4. 在“ **受控文件夹访问** ”部分下，选择 **“受保护”文件夹**。

5. 在 **用户访问控制** 提示中选择 **“是**”。 显示 **“受保护的文件夹** ”窗格。

6. 选择 **“添加受保护的文件夹** ”，然后按照提示添加文件夹。

### <a name="use-group-policy-to-protect-additional-folders"></a>使用组策略保护其他文件夹

1. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)。 

2. 右键单击要配置的组策略对象，然后选择 **“编辑**”。

3. 在 **组策略管理编辑器** 中，转到 **计算机配置** \> **策略** \> **管理模板**。

4. 展开树以 **Windows组件** \> **Microsoft Defender 防病毒Windows Defender** \> **攻击防护** \> **控制文件夹访问权限**。 <br/>**注意**：在较旧版本的Windows上，你可能会看到 **Windows Defender 防病毒**，而不是 **Microsoft Defender 防病毒**。

5. 双击 **“配置的受保护文件夹**”，然后将选项设置为 **“已启用**”。 选择 **“显示”**，并指定要保护的每个文件夹。

6. 像平时一样部署组策略对象。

### <a name="use-powershell-to-protect-additional-folders"></a>使用 PowerShell 保护其他文件夹

1. 在"开始"菜单中键入 **PowerShell**，右键 **单击Windows PowerShell**，然后选择 **“以管理员身份运行”**

2. 键入以下 PowerShell cmdlet，替换 `<the folder to be protected>` 为文件夹的路径 (，例如 `"c:\apps\"`) ：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. 对要保护的每个文件夹重复步骤 2。 受保护的文件夹在Windows 安全中心应用中可见。

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="显示 cmdlet 的 PowerShell 窗口" lightbox="images/cfa-allow-folder-ps.png":::

> [!IMPORTANT]
> 用于 `Add-MpPreference` 将应用追加或添加到列表，而不是 `Set-MpPreference`添加应用。 `Set-MpPreference`使用 cmdlet 将覆盖现有列表。

### <a name="use-mdm-csps-to-protect-additional-folders"></a>使用 MDM CSP 保护其他文件夹

使用 [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) 配置服务提供程序 (CSP) 允许应用对受保护的文件夹进行更改。

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>允许特定应用对受控文件夹进行更改

可以指定某些应用是否始终被视为安全应用，并授予对受保护文件夹中文件的写入访问权限。 如果受控文件夹访问功能阻止了特定应用并信任，则允许应用可能很有用。

> [!IMPORTANT]
> 默认情况下，Windows向允许的列表添加被视为友好的应用。 自动添加的此类应用不会记录在Windows 安全中心应用中显示的列表中或使用关联的 PowerShell cmdlet。 不需要添加大多数应用。 仅当应用被阻止时才添加应用，并且可以验证其可信度。

添加应用时，必须指定应用的位置。 仅允许该位置中的应用访问受保护的文件夹。 如果应用 (同名) 位于其他位置，则不会将其添加到允许列表中，并且可能会被受控文件夹访问阻止。

允许的应用程序或服务仅在启动受控文件夹后具有写入访问权限。 例如，更新服务在允许后将继续触发事件，直到停止并重新启动。

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>使用Windows Defender安全应用允许特定应用

1. 通过搜索“安全性”的“开始”菜单打开Windows 安全中心 **应用。**

2. ) 选择 **“病毒&威胁防护** ”磁贴 (或左侧菜单栏上的“防护”图标，然后选择 **“管理勒索软件保护**”。

3. 在“**受控文件夹访问**”部分下，选择 **“允许应用通过受控文件夹访问**”

4. 选择 **“添加允许的应用** ”，然后按照提示添加应用。

   :::image type="content" source="images/cfa-allow-app.png" alt-text="“添加允许的应用”按钮" lightbox="images/cfa-allow-app.png":::

### <a name="use-group-policy-to-allow-specific-apps"></a>使用组策略允许特定应用

1. 在组策略管理设备上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)，右键单击要配置的组策略对象，然后选择 **“编辑**”。

2. 在 **策略管理编辑器** 中， **计算机配置** 并选择 **管理模板**。

3. 展开树以 **Windows组件** \> **Microsoft Defender 防病毒Windows Defender** \> **攻击防护** \> **控制文件夹访问权限**。

4. 双击“ **配置允许的应用程序** ”设置，并将选项设置为 **“已启用**”。 选择 **“显示** ”并输入每个应用。

### <a name="use-powershell-to-allow-specific-apps"></a>使用 PowerShell 允许特定应用

1. 在"开始"菜单中键入 **PowerShell**，右键 **单击Windows PowerShell**，然后选择 **“以管理员身份运行”**
2. 输入以下 cmdlet：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    例如，若要添加位于 *文件夹 C：\apps* 中的可执行 *文件test.exe*，cmdlet 如下所示：

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   继续使用 `Add-MpPreference -ControlledFolderAccessAllowedApplications` 以将更多应用添加到列表。 使用此 cmdlet 添加的应用将显示在Windows 安全中心应用中。

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="用于允许应用程序的 PowerShell cmdlet" lightbox="images/cfa-allow-app-ps.png":::

> [!IMPORTANT]
> 用于 `Add-MpPreference` 将应用追加或添加到列表。 `Set-MpPreference`使用 cmdlet 将覆盖现有列表。

### <a name="use-mdm-csps-to-allow-specific-apps"></a>使用 MDM CSP 允许特定应用

使用 [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) 配置服务提供程序 (CSP) 允许应用对受保护的文件夹进行更改。

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>允许已签名的可执行文件访问受保护的文件夹

Microsoft Defender for Endpoint证书和文件指示器可以允许已签名的可执行文件访问受保护的文件夹。 有关实现详细信息，请参阅 [基于证书创建指示器](indicator-certificates.md)。

> [!Note]
> 这不适用于脚本引擎，包括 Powershell

## <a name="customize-the-notification"></a>自定义通知

有关在触发规则并阻止应用或文件时自定义通知的详细信息，请参阅[Microsoft Defender for Endpoint中配置警报通知](configure-email-notifications.md)。

## <a name="see-also"></a>另请参阅

- [使用受控文件夹访问保护文重要件夹](controlled-folders.md)
- [启用受控文件夹访问](enable-controlled-folders.md)
- [评估攻击面减少规则](evaluate-attack-surface-reduction.md)
