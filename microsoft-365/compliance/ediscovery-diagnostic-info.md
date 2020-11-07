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
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="ce82c-103">收集电子数据展示诊断信息</span><span class="sxs-lookup"><span data-stu-id="ce82c-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="ce82c-104">有时，Microsoft 支持工程师在打开与核心电子数据展示或高级电子数据展示相关的支持案例时，需要了解有关您的问题的具体信息。</span><span class="sxs-lookup"><span data-stu-id="ce82c-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="ce82c-105">本文提供了有关如何收集诊断信息以帮助工程师调查和解决问题的指导。</span><span class="sxs-lookup"><span data-stu-id="ce82c-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="ce82c-106">通常情况下，在要求 Microsoft 支持工程师执行此操作之前，不需要收集此信息。</span><span class="sxs-lookup"><span data-stu-id="ce82c-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce82c-107">本文中所述的 cmdlet 和诊断信息的输出可能包含有关您组织中的诉讼或内部调查的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="ce82c-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="ce82c-108">在将原始诊断信息发送给 Microsoft 支持之前，应查看信息，并通过将其替换为诉讼或调查) ，对任何敏感信息 (如名称或其他信息，对其进行密文 `XXXXXXX` 。</span><span class="sxs-lookup"><span data-stu-id="ce82c-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="ce82c-109">使用此方法还将向 Microsoft 支持工程师表明信息已编辑。</span><span class="sxs-lookup"><span data-stu-id="ce82c-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="ce82c-110">收集核心电子数据展示的诊断信息</span><span class="sxs-lookup"><span data-stu-id="ce82c-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="ce82c-111">若要收集核心电子数据展示的诊断信息，请基于 cmdlet，因此您必须使用 Security & 合规性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ce82c-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="ce82c-112">下面的 PowerShell 示例将运行 cmdlet，然后将输出保存到指定的文本文件。</span><span class="sxs-lookup"><span data-stu-id="ce82c-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="ce82c-113">在大多数支持案例中，只需运行以下命令之一。</span><span class="sxs-lookup"><span data-stu-id="ce82c-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="ce82c-114">若要运行以下 cmdlet，请[连接到安全 & 合规性 </span> 中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ce82c-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="ce82c-115">连接后，运行以下一个或多个命令，并确保将占位符替换为实际对象名称。</span><span class="sxs-lookup"><span data-stu-id="ce82c-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="ce82c-116">检查生成的文本文件并 redacting 敏感信息之后，将其发送给 Microsoft 支持工程师，以在你的案例上工作。</span><span class="sxs-lookup"><span data-stu-id="ce82c-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="ce82c-117">您还可以运行此部分中的命令，以收集 Microsoft 365 合规性中心的 **内容搜索** 页面上列出的搜索和导出的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="ce82c-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="ce82c-118">收集有关搜索的信息</span><span class="sxs-lookup"><span data-stu-id="ce82c-118">Collect information about searches</span></span>

<span data-ttu-id="ce82c-119">下面的命令收集在调查与核心电子数据展示案例相关的内容搜索或搜索的问题时有帮助的信息。</span><span class="sxs-lookup"><span data-stu-id="ce82c-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="ce82c-120">收集有关搜索操作的信息</span><span class="sxs-lookup"><span data-stu-id="ce82c-120">Collect information about search actions</span></span>

<span data-ttu-id="ce82c-121">下面的命令收集信息，以调查预览、导出或清除内容搜索结果或与核心电子数据展示事例关联的搜索的问题。</span><span class="sxs-lookup"><span data-stu-id="ce82c-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="ce82c-122">您可以通过单击 " **导出** " 选项卡上列出的导出来标识搜索操作的名称。若要确定预览和清除操作的名称，您可以运行 **new-compliancesearchaction** cmdlet 来显示所有操作的列表。</span><span class="sxs-lookup"><span data-stu-id="ce82c-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="ce82c-123">搜索操作名称的格式是通过追加 `_Preview` 、 `_Export` 或 `_Purge` 对应搜索的名称来构造的。</span><span class="sxs-lookup"><span data-stu-id="ce82c-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="ce82c-124">收集有关电子数据展示保留的信息</span><span class="sxs-lookup"><span data-stu-id="ce82c-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="ce82c-125">当与核心电子数据展示事例相关联的电子数据展示保留未按预期方式工作时，请运行以下命令来收集有关案例保留策略的信息，以及有关电子数据展示保留的关联事例保留规则。</span><span class="sxs-lookup"><span data-stu-id="ce82c-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="ce82c-126">以下命令中的 *事例保留策略名称* 与电子数据展示保留的名称相同。</span><span class="sxs-lookup"><span data-stu-id="ce82c-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="ce82c-127">可以在核心电子数据展示事例中的 **保留** 选项卡上标识此名称。</span><span class="sxs-lookup"><span data-stu-id="ce82c-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="ce82c-128">收集所有事例信息</span><span class="sxs-lookup"><span data-stu-id="ce82c-128">Collect all case information</span></span>

<span data-ttu-id="ce82c-129">有时，Microsoft 支持部门在调查您的问题时所需的信息并不明显。</span><span class="sxs-lookup"><span data-stu-id="ce82c-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="ce82c-130">在这种情况下，您可以收集核心电子数据展示事例的所有诊断信息。</span><span class="sxs-lookup"><span data-stu-id="ce82c-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="ce82c-131">以下命令中的 *核心电子数据展示事例名称* 与 Microsoft 365 合规性中心中 **核心电子数据展示** 页面上显示的事例的名称相同。</span><span class="sxs-lookup"><span data-stu-id="ce82c-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="ce82c-132">收集高级电子数据展示的诊断信息</span><span class="sxs-lookup"><span data-stu-id="ce82c-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="ce82c-133">利用高级电子数据展示事例中的 " **设置** " 选项卡，可以快速复制案例的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="ce82c-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="ce82c-134">将诊断信息保存到剪贴板，以便可以将其粘贴到文本文件并发送到 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="ce82c-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="ce82c-135">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击 " **显示所有 > 电子数据展示 > 高级** 。</span><span class="sxs-lookup"><span data-stu-id="ce82c-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="ce82c-136">选择一个事例，然后单击 " **设置** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ce82c-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="ce82c-137">在 " **事例信息** " 下，单击 " **选择** "。</span><span class="sxs-lookup"><span data-stu-id="ce82c-137">Under **Case Information** , click **Select**.</span></span>

4. <span data-ttu-id="ce82c-138">在弹出页面上，单击 " **复制诊断信息** " 以将信息复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="ce82c-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="ce82c-139">在记事本中打开一个文本文件 () 然后将该信息粘贴到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="ce82c-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="ce82c-140">保存文本文件并将其命名 `AeD Diagnostic Info YYYY.MM.DD` 为类似 (例如， `AeD Diagnostic Info 2020.11.03`) 。</span><span class="sxs-lookup"><span data-stu-id="ce82c-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="ce82c-141">检查文件并 redacting 敏感信息之后，将其发送给 Microsoft 支持工程师，以在你的案例上工作。</span><span class="sxs-lookup"><span data-stu-id="ce82c-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
