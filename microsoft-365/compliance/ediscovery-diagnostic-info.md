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
description: 了解如何收集 Microsoft 支持案例电子数据展示诊断信息。
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926552"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="392f8-103">收集电子数据展示诊断信息</span><span class="sxs-lookup"><span data-stu-id="392f8-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="392f8-104">有时，当你打开与核心电子数据展示或电子数据展示相关的支持案例时，Microsoft 支持工程师会要求提供有关Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="392f8-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="392f8-105">本文提供有关如何收集诊断信息以帮助支持工程师调查和解决问题的指南。</span><span class="sxs-lookup"><span data-stu-id="392f8-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="392f8-106">通常，在 Microsoft 支持工程师要求你收集此信息之前，你无需收集此信息。</span><span class="sxs-lookup"><span data-stu-id="392f8-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="392f8-107">本文中介绍的 cmdlet 和诊断信息的输出可能包括有关组织中诉讼或内部调查的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="392f8-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="392f8-108">在将原始诊断信息发送到 Microsoft 支持之前，您应查看该信息，并修订任何敏感信息 (例如名称或其他有关诉讼或调查各方的信息) 替换为 `XXXXXXX` 。</span><span class="sxs-lookup"><span data-stu-id="392f8-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="392f8-109">使用此方法还将向 Microsoft 支持工程师指示信息已修订。</span><span class="sxs-lookup"><span data-stu-id="392f8-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="392f8-110">收集核心电子数据展示的诊断信息</span><span class="sxs-lookup"><span data-stu-id="392f8-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="392f8-111">收集核心电子数据展示的诊断信息基于 cmdlet，因此你必须使用安全&中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="392f8-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="392f8-112">以下 PowerShell 示例将运行 cmdlet，然后将输出保存到指定的文本文件。</span><span class="sxs-lookup"><span data-stu-id="392f8-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="392f8-113">在大多数支持情况下，您只应运行这些命令之一。</span><span class="sxs-lookup"><span data-stu-id="392f8-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="392f8-114">若要运行以下 cmdlet，[请连接到安全&中心 PowerShell。 </span> ](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="392f8-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="392f8-115">连接后，运行以下一个或多个命令，并确保使用实际的对象名称替换占位符。</span><span class="sxs-lookup"><span data-stu-id="392f8-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="392f8-116">查看生成的文本文件并修订敏感信息后，将其发送给正在处理你的案例的 Microsoft 支持工程师。</span><span class="sxs-lookup"><span data-stu-id="392f8-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="392f8-117">您还可以运行本节中的命令，以收集搜索和导出的诊断信息，这些信息在合规性中心的"内容"Microsoft 365页上列出。</span><span class="sxs-lookup"><span data-stu-id="392f8-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="392f8-118">收集有关搜索的信息</span><span class="sxs-lookup"><span data-stu-id="392f8-118">Collect information about searches</span></span>

<span data-ttu-id="392f8-119">以下命令收集在调查与核心电子数据展示案例关联的内容搜索或搜索时有用的信息。</span><span class="sxs-lookup"><span data-stu-id="392f8-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="392f8-120">收集有关搜索操作的信息</span><span class="sxs-lookup"><span data-stu-id="392f8-120">Collect information about search actions</span></span>

<span data-ttu-id="392f8-121">以下命令收集信息以调查预览、导出或清除与核心电子数据展示案例关联的内容搜索或搜索的结果时存在的问题。</span><span class="sxs-lookup"><span data-stu-id="392f8-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="392f8-122">可以通过单击"导出"选项卡上列出的导出来标识搜索 **操作** 的名称。若要标识预览和清除操作的名称，可以运行 **Get-ComplianceSearchAction** cmdlet 显示所有操作的列表。</span><span class="sxs-lookup"><span data-stu-id="392f8-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="392f8-123">搜索操作名称的格式通过追加 、 或 追加到相应搜索 `_Preview` `_Export` `_Purge` 的名称来构造。</span><span class="sxs-lookup"><span data-stu-id="392f8-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="392f8-124">收集有关电子数据展示保留的信息</span><span class="sxs-lookup"><span data-stu-id="392f8-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="392f8-125">如果与核心电子数据展示案例关联的电子数据展示保留未按预期运行，请运行以下命令来收集有关电子数据展示保留的"案例保留策略"和关联案例保留规则的信息。</span><span class="sxs-lookup"><span data-stu-id="392f8-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="392f8-126">以下 *命令中的* "案例保留"策略名称与电子数据展示保留的名称相同。</span><span class="sxs-lookup"><span data-stu-id="392f8-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="392f8-127">可以在核心电子数据展示案例中的 **保留** 选项卡上标识此名称。</span><span class="sxs-lookup"><span data-stu-id="392f8-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="392f8-128">收集所有案例信息</span><span class="sxs-lookup"><span data-stu-id="392f8-128">Collect all case information</span></span>

<span data-ttu-id="392f8-129">有时，Microsoft 支持需要哪些信息来调查你的问题并不明显。</span><span class="sxs-lookup"><span data-stu-id="392f8-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="392f8-130">在这种情况下，你可以收集核心电子数据展示案例的所有诊断信息。</span><span class="sxs-lookup"><span data-stu-id="392f8-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="392f8-131">以下 *命令* 中的核心电子数据展示案例名称与在安全与合规中心的"核心电子数据展示"页上Microsoft 365名称相同。 </span><span class="sxs-lookup"><span data-stu-id="392f8-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="392f8-132">收集诊断信息Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="392f8-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="392f8-133">使用 **设置** 中的"Advanced eDiscovery"选项卡可以快速复制该案例的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="392f8-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="392f8-134">诊断信息将保存到剪贴板，以便你可以将其粘贴到文本文件并发送给 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="392f8-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="392f8-135">转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击显示 **所有>电子数据展示>高级**。</span><span class="sxs-lookup"><span data-stu-id="392f8-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="392f8-136">选择一个案例，**然后单击"设置"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="392f8-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="392f8-137">在"**案例信息"下**，单击"**选择"。**</span><span class="sxs-lookup"><span data-stu-id="392f8-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="392f8-138">在飞出页面上，单击 **复制诊断信息** 以将该信息复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="392f8-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="392f8-139">在文本框中 (文本文件记事本) ，然后将信息粘贴到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="392f8-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="392f8-140">保存文本文件并将其命名为类似 `AeD Diagnostic Info YYYY.MM.DD` (，例如 `AeD Diagnostic Info 2020.11.03`) 。</span><span class="sxs-lookup"><span data-stu-id="392f8-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="392f8-141">查看文件并修订敏感信息后，将其发送给处理你的案例的 Microsoft 支持工程师。</span><span class="sxs-lookup"><span data-stu-id="392f8-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>