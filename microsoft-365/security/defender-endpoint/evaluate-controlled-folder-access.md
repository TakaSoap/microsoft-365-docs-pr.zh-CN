---
title: 受控文件夹访问评估
description: 了解受控文件夹访问如何帮助保护文件免受恶意应用的更改。
keywords: 攻击保护， windows 10， windows 11， windows defender， 勒索软件， 保护， 评估， 测试， 演示， 尝试
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.date: ''
ms.openlocfilehash: 4ccb91f0a8c181697eb525dd8f5576e6f6cdc0d1
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789813"
---
# <a name="evaluate-controlled-folder-access"></a>受控文件夹访问评估

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。


[受控文件夹访问](controlled-folders.md) 是一项功能，可帮助保护文档和文件免受可疑或恶意应用的修改。 Windows Server 2019、Windows Server 2022、Windows 10 和Windows 11 客户端支持受控文件夹访问权限。

它在帮助防止试图加密文件并将其扣为人质的 [勒索软件](https://www.microsoft.com/wdsi/threats/ransomware) 方面特别有用。

本文可帮助你评估受控文件夹访问权限。 它介绍了如何启用审核模式，以便你可以直接在组织中测试该功能。

> [!TIP]
> 还可以在 demo.wd.microsoft.com 访问Microsoft Defender for Endpoint演示方案[网站，确认](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)该功能是否正常工作，并了解其工作原理。

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

## <a name="use-audit-mode-to-measure-impact"></a>使用审核模式测量影响

在审核模式下启用受控文件夹访问，以查看如果完全启用， *将会* 发生的情况的记录。 测试该功能在组织中的工作原理，以确保它不会影响业务线应用。 还可以了解在一定时间段内通常会发生多少次可疑的文件修改尝试。

若要启用审核模式，请使用以下 PowerShell cmdlet：

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> 如果想要完全审核受控文件夹访问在组织中的工作原理，则需要使用管理工具将此设置部署到网络 () 中的设备。
还可以使用组策略、Intune、移动设备管理 (MDM) 或Microsoft Endpoint Manager来配置和部署设置，如主[控制文件夹访问主题](controlled-folders.md)中所述。

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>查看Windows 事件查看器中的受控文件夹访问事件

以下受控文件夹访问事件显示在 Microsoft/Windows 事件查看器/Windows/Windows Defender/Operational 文件夹下。

事件 ID | 描述
-|-
 5007 | 更改设置时的事件
 1124 | 已审核的受控文件夹访问事件
 1123 | 阻止的受控文件夹访问事件

> [!TIP]
> 可以配置[Windows事件转发订阅](/windows/win32/wec/setting-up-a-source-initiated-subscription)以集中收集日志。 

## <a name="customize-protected-folders-and-apps"></a>自定义受保护的文件夹和应用

在评估期间，你可能希望添加到受保护文件夹列表，或允许某些应用修改文件。

请参阅[具有受控文件夹访问权限的保护重要文件夹](controlled-folders.md)，以便使用管理工具（包括 组策略、PowerShell 和 MDM 配置服务提供程序） (CSP) 配置功能。

## <a name="see-also"></a>另请参阅

* [使用受控文件夹访问保护文重要件夹](controlled-folders.md)
* [评估 Microsoft Defender for Endpoint](evaluate-mde.md)
* [使用审核模式](audit-windows-defender.md)
