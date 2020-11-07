---
title: 收集电子数据展示诊断信息
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解如何收集 Microsoft 支持案例的电子数据展示诊断信息。
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944387"
---
# <a name="collect-ediscovery-diagnostic-information"></a>收集电子数据展示诊断信息

有时，Microsoft 支持工程师在打开与核心电子数据展示或高级电子数据展示相关的支持案例时，需要了解有关您的问题的具体信息。 本文提供了有关如何收集诊断信息以帮助工程师调查和解决问题的指导。 通常情况下，在要求 Microsoft 支持工程师执行此操作之前，不需要收集此信息。

> [!IMPORTANT]
> 本文中所述的 cmdlet 和诊断信息的输出可能包含有关您组织中的诉讼或内部调查的敏感信息。 在将原始诊断信息发送给 Microsoft 支持之前，应查看信息，并通过将其替换为诉讼或调查) ，对任何敏感信息 (如名称或其他信息，对其进行密文 `XXXXXXX` 。 使用此方法还将向 Microsoft 支持工程师表明信息已编辑。

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>收集核心电子数据展示的诊断信息

若要收集核心电子数据展示的诊断信息，请基于 cmdlet，因此您必须使用 Security & 合规性中心 PowerShell。 下面的 PowerShell 示例将运行 cmdlet，然后将输出保存到指定的文本文件。 在大多数支持案例中，只需运行以下命令之一。

若要运行以下 cmdlet，请[连接到安全 & 合规性 </span> 中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。 连接后，运行以下一个或多个命令，并确保将占位符替换为实际对象名称。

检查生成的文本文件并 redacting 敏感信息之后，将其发送给 Microsoft 支持工程师，以在你的案例上工作。

> [!NOTE]
> 您还可以运行此部分中的命令，以收集 Microsoft 365 合规性中心的 **内容搜索** 页面上列出的搜索和导出的诊断信息。

### <a name="collect-information-about-searches"></a>收集有关搜索的信息

下面的命令收集在调查与核心电子数据展示案例相关的内容搜索或搜索的问题时有帮助的信息。

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>收集有关搜索操作的信息

下面的命令收集信息，以调查预览、导出或清除内容搜索结果或与核心电子数据展示事例关联的搜索的问题。 您可以通过单击 " **导出** " 选项卡上列出的导出来标识搜索操作的名称。若要确定预览和清除操作的名称，您可以运行 **new-compliancesearchaction** cmdlet 来显示所有操作的列表。 搜索操作名称的格式是通过追加 `_Preview` 、 `_Export` 或 `_Purge` 对应搜索的名称来构造的。

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>收集有关电子数据展示保留的信息

当与核心电子数据展示事例相关联的电子数据展示保留未按预期方式工作时，请运行以下命令来收集有关案例保留策略的信息，以及有关电子数据展示保留的关联事例保留规则。 以下命令中的 *事例保留策略名称* 与电子数据展示保留的名称相同。 可以在核心电子数据展示事例中的 **保留** 选项卡上标识此名称。

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>收集所有事例信息

有时，Microsoft 支持部门在调查您的问题时所需的信息并不明显。 在这种情况下，您可以收集核心电子数据展示事例的所有诊断信息。 以下命令中的 *核心电子数据展示事例名称* 与 Microsoft 365 合规性中心中 **核心电子数据展示** 页面上显示的事例的名称相同。

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>收集高级电子数据展示的诊断信息

利用高级电子数据展示事例中的 " **设置** " 选项卡，可以快速复制案例的诊断信息。 将诊断信息保存到剪贴板，以便可以将其粘贴到文本文件并发送到 Microsoft 支持。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 " **显示所有 > 电子数据展示 > 高级** 。

2. 选择一个事例，然后单击 " **设置** " 选项卡。

3. 在 " **事例信息** " 下，单击 " **选择** "。

4. 在弹出页面上，单击 " **复制诊断信息** " 以将信息复制到剪贴板。

5. 在记事本中打开一个文本文件 () 然后将该信息粘贴到文本文件中。

6. 保存文本文件并将其命名 `AeD Diagnostic Info YYYY.MM.DD` 为类似 (例如， `AeD Diagnostic Info 2020.11.03`) 。

检查文件并 redacting 敏感信息之后，将其发送给 Microsoft 支持工程师，以在你的案例上工作。
