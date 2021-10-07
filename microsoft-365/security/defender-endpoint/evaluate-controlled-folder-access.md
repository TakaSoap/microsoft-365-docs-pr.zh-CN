---
title: 受控文件夹访问评估
description: 了解受控文件夹访问权限如何有助于防止文件被恶意应用更改。
keywords: Exploit Protection， windows 10， windows defender， 勒索软件， 保护， 评估， 测试， 演示， 尝试
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: d4c029ee825299202b3d1a128c9fbee5986bf5cc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166524"
---
# <a name="evaluate-controlled-folder-access"></a>受控文件夹访问评估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。


[受控文件夹](controlled-folders.md) 访问权限是一项有助于保护文档和文件免受可疑或恶意应用修改的功能。 受控文件夹访问权限在 Windows Server 2019、Windows Server 2022 和 Windows 10 客户端上受支持。

它尤其有助于防范尝试加密文件并[](https://www.microsoft.com/wdsi/threats/ransomware)阻止其成为勒索软件。

本文帮助你评估受控文件夹访问权限。 它介绍了如何启用审核模式，以便可以直接在组织中测试该功能。

> [!TIP]
> 还可以访问 Microsoft Defender for Endpoint 演示方案[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 以确认功能是否正常工作并查看其工作方式。

## <a name="use-audit-mode-to-measure-impact"></a>使用审核模式衡量影响

在审核模式下启用受控文件夹访问权限，查看完全启用后将发生的情况记录。 测试此功能在组织中如何工作，以确保它不会影响你的业务线应用。 您还可以了解在特定时段内通常发生多少可疑文件修改尝试。

若要启用审核模式，请使用以下 PowerShell cmdlet：

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> 如果你想要完全审核受控文件夹访问权限在组织中如何工作，你将需要使用管理工具将此设置部署到网络 (设备) 。
您还可以使用组策略、Intune、移动设备管理 (MDM) 或 Microsoft Endpoint Manager 配置和部署设置，如主要的受控文件夹[访问权限主题中所述](controlled-folders.md)。

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>在事件查看器中查看受控Windows访问事件

以下受控文件夹访问权限事件显示在 microsoft/Windows/Windows/Windows Defender/Operational 文件夹下的事件查看器中。

事件 ID | 描述
-|-
 5007 | 更改设置时的事件
 1124 | 已审核的受控文件夹访问事件
 1123 | 阻止的受控文件夹访问事件

> [!TIP]
> 你可以配置Windows[转发订阅](/windows/win32/wec/setting-up-a-source-initiated-subscription)以集中收集日志。 

## <a name="customize-protected-folders-and-apps"></a>自定义受保护的文件夹和应用

在评估期间，你可能希望添加到受保护的文件夹列表，或允许某些应用修改文件。

请参阅 [使用](controlled-folders.md) 受控文件夹访问权限保护重要文件夹，以使用管理工具（包括组策略、PowerShell 和 MDM 配置服务提供程序 (CSP) ）。

## <a name="see-also"></a>另请参阅

* [使用受控文件夹访问保护文重要件夹](controlled-folders.md)
* [评估 Microsoft Defender for Endpoint](evaluate-mde.md)
* [使用审核模式](audit-windows-defender.md)
