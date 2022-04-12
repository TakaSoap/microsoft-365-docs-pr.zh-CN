---
title: 保护重要文件夹免受勒索软件的侵害，防止使用受控文件夹访问加密文件
description: 默认文件夹中的文件可以防止被恶意应用更改。 防止勒索软件加密文件。
keywords: 受控文件夹访问， windows 10， windows defender， 勒索软件， 保护， 文件， 文件夹
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.collection: m365-security-compliance
ms.date: ''
ms.openlocfilehash: 84304d120f5822d91adc99c86e2c22c0cfb6790c
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789909"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>使用受控文件夹访问保护文重要件夹

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**适用对象**
- Windows


> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="what-is-controlled-folder-access"></a>什么是受控文件夹访问权限？

受控文件夹访问有助于保护贵重数据免受恶意应用和威胁（如勒索软件）的侵害。 受控文件夹访问通过针对已知受信任的应用列表检查应用来保护数据。 在 Windows Server 2019、Windows Server 2022、Windows 10 和Windows 11客户端上支持，可使用Windows 安全中心应用启用受控文件夹访问权限，) 托管设备的Microsoft Endpoint Configuration Manager或Intune (。

> [!NOTE]
> 脚本引擎不受信任，不能允许它们访问受控保护的文件夹。 例如，即使允许使用 [证书和文件指示器](/microsoft-365/security/defender-endpoint/indicator-certificates)，受控文件夹访问也不会信任 PowerShell。

受控文件夹访问最适用于[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，这为你提供了有关受控文件夹访问事件和块的详细报告，作为通常[警报调查方案](investigate-alerts.md)的一部分。

> [!TIP]
> 受控文件夹访问块不会在 [警报队列](alerts-queue.md)中生成警报。 但是，可以使用[高级搜寻](advanced-hunting-overview.md)或[自定义检测规则](custom-detection-rules.md)在[设备时间线视图](investigate-machines.md)中查看有关受控文件夹访问块的信息。

## <a name="how-does-controlled-folder-access-work"></a>受控文件夹访问如何工作？

受控文件夹访问仅允许受信任的应用访问受保护的文件夹。 在配置受控文件夹访问权限时指定受保护的文件夹。 通常，常用的文件夹（例如用于文档、图片、下载等的文件夹）包含在受控文件夹列表中。

受控文件夹访问适用于受信任应用的列表。 包含在受信任软件列表中的应用按预期工作。 禁止未包含在列表中的应用对受保护文件夹中的文件进行任何更改。

应用会根据应用的流行程度和信誉添加到列表中。 在整个组织中非常普遍且从未显示任何被视为恶意的行为的应用被视为值得信任。 这些应用会自动添加到列表中。

也可以使用Configuration Manager或Intune手动将应用添加到受信任的列表中。 可以从Microsoft 365 Defender门户执行其他操作。

## <a name="why-controlled-folder-access-is-important"></a>为什么受控文件夹访问很重要

受控文件夹访问在帮助保护文档和信息免受 [勒索软件侵害](https://www.microsoft.com/wdsi/threats/ransomware)方面特别有用。 在勒索软件攻击中，文件可能会被加密并扣为人质。 有了受控文件夹访问权限，应用尝试对受保护文件夹中的文件进行更改的计算机上会显示一条通知。 你可以使用公司的详细信息和联系人信息[自定义通知](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules)。 还可以单独启用规则以自定义功能所监视的技术。

受 [保护的文件夹](#review-controlled-folder-access-events-in-windows-event-viewer) 包括常见系统文件夹 (包括启动扇区) ，你可以 [添加更多文件夹](customize-controlled-folders.md#protect-additional-folders)。 还可以 [允许应用](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) 向其授予对受保护文件夹的访问权限。

可以使用 [审核模式](audit-windows-defender.md) 来评估受控文件夹访问在启用后对组织的影响。 你还可以访问 [demo.wd.microsoft.com 的Windows Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)测试场网站，确认该功能是否正常工作，并查看其工作原理。

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

以下版本的Windows支持受控文件夹访问：

- [Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709) 及更高版本
- Windows 11
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- Windows Server 2022

## <a name="windows-system-folders-are-protected-by-default"></a>默认情况下，Windows系统文件夹受保护

默认情况下，Windows系统文件夹以及其他几个文件夹受到保护：

受保护的文件夹包括常见系统文件夹 (包括启动扇区) ，你可以添加其他文件夹。 还可以允许应用向其授予对受保护文件夹的访问权限。  默认情况下受保护的Windows系统文件夹为：

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

默认文件夹显示在此 **电脑** 下的用户配置文件中。
   > [!div class="mx-imgBorder"]
   > ![受保护Windows默认系统文件夹](images/defaultfolders.png)

> [!NOTE]
> 可以将其他文件夹配置为受保护，但不能删除默认情况下受保护的Windows系统文件夹。

## <a name="requirements-for-controlled-folder-access"></a>受控文件夹访问要求

受控文件夹访问需要启用[Microsoft Defender 防病毒实时保护](configure-real-time-protection-microsoft-defender-antivirus.md)。

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中查看受控文件夹访问事件

Defender for Endpoint 在 Microsoft 365 Defender 门户的[警报调查方案](investigate-alerts.md)中提供事件和块的详细报告;请参阅[Microsoft 365 Defender中的Microsoft Defender for Endpoint](../defender/microsoft-365-security-center-mde.md)。

可以使用[高级搜寻](advanced-hunting-overview.md)查询Microsoft Defender for Endpoint数据。 如果使用的是 [审核模式](audit-windows-defender.md)，则可以使用 [高级搜寻](advanced-hunting-overview.md) 来查看受控文件夹访问设置在启用时对环境的影响。

示例查询：

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>查看Windows 事件查看器中的受控文件夹访问事件

可以查看Windows事件日志，查看在受控文件夹访问块 (或审核) 应用时创建的事件：

1. 下载 [评估包](https://aka.ms/mp7z2w) 并将文件 *cfa-events.xml* 提取到设备上易于访问的位置。
2. 在"开始"菜单中键入 **事件查看器** 以打开Windows 事件查看器。
3. 在左侧面板的 **“操作”** 下，选择 **“导入自定义视图...**”。
4. 导航到提取 *cfa-events.xml* 的位置，然后选择它。 或者， [直接复制 XML](event-views.md)。
5. 选择“确定”。

下表显示了与受控文件夹访问相关的事件：

<br/><br/>

|事件 ID|描述|
|---|---|
|5007|更改设置时的事件|
|1124|已审核的受控文件夹访问事件|
|1123|阻止的受控文件夹访问事件|

## <a name="view-or-change-the-list-of-protected-folders"></a>查看或更改受保护文件夹的列表

可以使用Windows 安全中心应用查看受受控文件夹访问保护的文件夹列表。

1. 在Windows 10或Windows 11设备上，打开Windows 安全中心应用。
2. 选择“**病毒和威胁防护**”。
3. 在 **勒索软件保护** 下，选择 **“管理勒索软件保护**”。
4. 如果已关闭受控文件夹访问权限，则需要将其打开。 选择 **受保护的文件夹**。
5. 请按照以下步骤之一操作：
   - 若要添加文件夹，请选择 **“+ 添加受保护的文件夹**”。
   - 若要删除文件夹，请选择它，然后选择 **“删除**”。

> [!NOTE]
> [默认情况下，Windows系统文件夹](#windows-system-folders-are-protected-by-default)受到保护，并且无法从列表中删除它们。
