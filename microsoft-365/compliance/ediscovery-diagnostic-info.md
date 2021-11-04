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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解如何收集 Microsoft 支持案例电子数据展示诊断信息。
ms.openlocfilehash: 65a54a1d4567d536c19363ad0834e2cdd74078ab
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754819"
---
# <a name="collect-ediscovery-diagnostic-information"></a>收集电子数据展示诊断信息

有时，当你打开与核心电子数据展示或电子数据展示相关的支持案例时，Microsoft 支持工程师需要有关Advanced eDiscovery。 本文提供有关如何收集诊断信息以帮助支持工程师调查和解决问题的指南。 通常，在 Microsoft 支持工程师要求你收集此信息之前，你无需收集此信息。

> [!IMPORTANT]
> 本文中所述的 cmdlet 和诊断信息的输出可能包括有关组织中诉讼或内部调查的敏感信息。 在将原始诊断信息发送到 Microsoft 支持之前，您应查看该信息，并修订任何敏感信息 (例如名称或其他有关诉讼或调查各方的信息，) 替换为 `XXXXXXX` 。 使用此方法还将向 Microsoft 支持工程师指示信息已修订。

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>收集核心电子数据展示的诊断信息

收集核心电子数据展示的诊断信息基于 cmdlet，因此你必须使用安全&中心 PowerShell。 以下 PowerShell 示例将运行 cmdlet，然后将输出保存到指定的文本文件。 在大多数支持情况下，你只应运行这些命令之一。

若要运行以下 cmdlet，[请连接到安全&中心 </span> PowerShell。](/powershell/exchange/connect-to-scc-powershell) 连接后，运行以下一个或多个命令，并确保使用实际的对象名称替换占位符。

查看生成的文本文件并修订敏感信息后，将其发送给处理你的案例的 Microsoft 支持工程师。

> [!NOTE]
> 您还可以运行本节中的命令，以收集搜索和导出内容搜索页中列出的搜索和导出的诊断Microsoft 365 合规中心。 

### <a name="collect-information-about-searches"></a>收集有关搜索的信息

以下命令收集在调查与核心电子数据展示案例关联的内容搜索或搜索时有用的信息。

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>收集有关搜索操作的信息

以下命令收集信息以调查预览、导出或清除与核心电子数据展示案例关联的内容搜索或搜索的结果时存在的问题。 可以通过单击"导出"选项卡上列出的导出来标识搜索 **操作** 的名称。若要标识预览和清除操作的名称，可以运行 **Get-ComplianceSearchAction** cmdlet 显示所有操作的列表。 搜索操作名称的格式通过追加 、 或 追加到相应搜索 `_Preview` `_Export` `_Purge` 的名称来构造。

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>收集有关电子数据展示保留的信息

如果与核心电子数据展示案例关联的电子数据展示保留未按预期运行，请运行以下命令来收集有关电子数据展示保留的"案例保留策略"和关联案例保留规则的信息。 以下 *命令中的* "案例保留"策略名称与电子数据展示保留的名称相同。 可以在核心电子数据展示案例中的 **保留** 选项卡上标识此名称。

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>收集所有案例信息

有时，Microsoft 支持需要哪些信息来调查你的问题并不明显。 在这种情况下，你可以收集核心电子数据展示案例的所有诊断信息。 以下 *命令* 中的核心电子数据展示案例名称与在"核心电子数据展示"页上显示Microsoft 365 合规中心。 

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>收集诊断信息Advanced eDiscovery

使用 **设置** 中的"Advanced eDiscovery"选项卡可以快速复制该案例的诊断信息。 诊断信息将保存到剪贴板，以便你可以将其粘贴到文本文件并发送给 Microsoft 支持。

1. 转到"Microsoft 365 合规中心"，然后选择"**电子数据展示高级**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2174006" target="_blank">**"。**</a>

2. 选择一个案例，**然后单击"设置"** 选项卡。

3. 在"**案例信息"下**，单击"**选择"。**

4. 在飞出页面上，单击"**操作**  >  **复制支持信息**"以将信息复制到剪贴板。

5. 在文本框中 (文本文件记事本) ，然后将信息粘贴到文本文件中。

6. 保存文本文件，并将其名称 (`AeD Diagnostic Info YYYY.MM.DD` 例如 `AeD Diagnostic Info 2020.11.03` ，) 。

查看文件并修订敏感信息后，将其发送给处理你的案例的 Microsoft 支持工程师。
