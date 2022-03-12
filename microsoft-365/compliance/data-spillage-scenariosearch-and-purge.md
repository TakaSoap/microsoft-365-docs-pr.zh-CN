---
title: 电子数据展示解决方案系列数据泄漏方案 - 搜索和清除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 使用电子数据展示和搜索工具管理和响应组织中发生的数据泄漏事件。
ms.openlocfilehash: 98dbb4ec36b7fb8166732aa855eefe3db6c5bbdc
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2022
ms.locfileid: "63449550"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>电子数据展示解决方案系列：数据泄漏方案 - 搜索和清除

 **什么是数据泄漏？为什么需要关注？** 数据泄漏是在机密文档释放到不受信任的环境中时。 检测到数据泄漏事件时，必须快速评估泄漏的大小和位置，检查其周围的用户活动，然后从系统中永久清除溢出的数据。 
  
## <a name="data-spillage-scenario"></a>数据泄漏方案

你是 Contoso 首席信息安全官。 你收到数据泄漏情况通知，即员工在不知情的情况下通过电子邮件与多个人共享了高度机密文档。 您希望快速评估在内部和外部接收此文档的人。 确定后，你要与其他调查人员共享案例结果进行审阅，然后从调查组永久Office 365。 调查完成后，您需要生成一份包含永久删除证据和其他案例详细信息的报告，供将来参考。
  
### <a name="scope-of-this-article"></a>本文的范围

本文档提供了有关如何从邮件中永久删除邮件Microsoft 365以便邮件不可访问或恢复的说明列表。 若要删除邮件并使其可恢复，直到已删除项目的保留期过期，请参阅搜索并删除 [您组织的电子邮件](search-for-and-delete-messages-in-your-organization.md)。
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>用于管理数据泄漏事件的工作流

下面将了解如何管理数据泄漏事件：

![用于管理数据泄漏事件的 8 步工作流。](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[ (可选) 步骤 1：管理谁可以访问案例并设置合规性边界](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[步骤 2：创建电子数据展示案例](#step-2-create-an-ediscovery-case)<br/>
[步骤 3：搜索溢出的数据](#step-3-search-for-the-spilled-data)<br/>
[步骤 4：查看并验证案例发现](#step-4-review-and-validate-case-findings)<br/>
[步骤 5：使用邮件跟踪日志检查如何共享溢出的数据](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[步骤 6：准备邮箱](#step-6-prepare-the-mailboxes)<br/>
[步骤 7：永久删除溢出的数据](#step-7-permanently-delete-the-spilled-data)<br/>
[步骤 8：验证、提供删除证明和审核](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>在启动之前需要知道的一些内容

- 当邮箱处于保留状态时，已删除邮件将保留在"可恢复的项目"文件夹中，直到保留期过期或保留解除。 [步骤 6](#step-6-prepare-the-mailboxes) 介绍如何从邮箱中删除保留。 在删除保留之前，请与记录管理或法律部门核实。 您的组织可能拥有一个策略，用于定义邮箱是置于保留状态还是数据泄漏事件优先。 
    
- 若要控制数据泄漏调查人员可以搜索和管理哪些用户邮箱可以访问该案例，可以设置合规性边界并创建自定义角色组，如步骤 [1 中所述](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)。 为此，您必须是组织管理角色组的成员或分配有角色管理角色。 如果您或贵组织的管理员已设置合规性边界，您可以跳过步骤 1。
    
- 若要创建案例，您必须是电子数据展示管理员角色组的成员，或者是分配了案例管理角色的自定义角色组的成员。 如果您不是成员，请Microsoft 365管理员[将您添加到电子数据展示管理员角色组](assign-ediscovery-permissions.md)。
    
- 若要创建并运行内容搜索，您必须是电子数据展示管理员角色组的成员，或者分配有“合规性搜索”管理角色。 若要删除邮件，您必须是组织管理角色组的成员或分配有“搜索并清除”管理角色。 有关向角色组添加用户的信息，请参阅分配 [电子数据展示权限](./assign-ediscovery-permissions.md)。
    
- 若要搜索审核日志 8 中的电子数据展示活动，必须为组织启用审核。 可以搜索最近 90 天内执行的活动。 若要详细了解如何启用和使用审核，请参阅步骤 8 中的审核 [数据](#auditing-the-data-spillage-investigation-process) 泄漏调查过程部分。 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a> (可选) 步骤 1：管理谁可以访问案例并设置合规性边界

根据组织实践，需要控制谁可以访问用于调查数据泄漏事件和设置合规性边界的电子数据展示案例。 执行此操作的最简单方法是将调查人员添加为 Microsoft 365 合规中心 中现有角色组的成员，然后将该角色组添加为电子数据展示案例的成员。 有关内置电子数据展示角色组以及如何向电子数据展示案例添加成员的信息，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。
  
还可以创建一个符合组织需求的新角色组。 例如，你可能希望组织中一组数据泄漏调查人员访问所有数据泄漏案例并展开协作。 为此，你可以创建"数据泄漏调查人员"角色组，分配适当的角色 (Export、RMS Decrypt、Review、Preview、Compliance Search 和 Case Management) ，将数据泄漏研究人员添加到角色组，然后将该角色组添加为数据泄漏电子数据展示案例的成员。 有关如何[进行此操作的](set-up-compliance-boundaries.md)详细说明，请参阅在 Office 365 中设置电子数据展示调查的合规性边界。 
  
## <a name="step-2-create-an-ediscovery-case"></a>步骤 2：创建电子数据展示案例

电子数据展示案例提供了一种管理数据泄漏调查的有效方法。 您可以将成员添加到在步骤 1 中创建的角色组，将角色组添加为新电子数据展示案例的成员，执行迭代搜索以查找溢出的数据，导出要共享的报告，跟踪案例的状态，然后根据需要重新引用案例的详细信息。 请考虑为用于数据泄漏事件电子数据展示事例建立命名约定，并提供在事例名称和说明中尽可能多的信息，以便将来能够查找和参考（如有必要）。
  
若要创建新案例，可以在安全与合规中心使用电子数据展示。 请参阅核心电子数据展示入门中的" [创建新案例"](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)。
  
## <a name="step-3-search-for-the-spilled-data"></a>步骤 3：搜索溢出的数据

现在，你已经创建了一个案例和管理访问，可以使用该案例反复搜索以查找溢出的数据并标识包含泄漏数据的邮箱。 您将使用与用于查找电子邮件相同的搜索查询来删除步骤 7 中的相同 [邮件](#step-7-permanently-delete-the-spilled-data)。
  
若要创建与电子数据展示案例关联的内容搜索，请参阅在核心电子数据展示案例中 [搜索内容](search-for-content-in-core-ediscovery.md)。
  
> [!IMPORTANT]
> 搜索查询中使用的关键字可能包含要搜索的实际溢出数据。 例如，如果您搜索包含社会保险号的文档，并且将其用作搜索关键字，则必须在以后删除查询以避免进一步泄漏。 请参阅 [步骤 8 中的](#deleting-the-search-query) 删除搜索查询。
  
## <a name="step-4-review-and-validate-case-findings"></a>步骤 4：查看并验证案例发现

创建内容搜索后，您需要检查并验证搜索结果，并验证它们是否仅包含必须删除的电子邮件。 在内容搜索中，可以预览 1，000 封电子邮件的随机采样，而无需导出搜索结果，以避免进一步数据泄漏。 有关预览限制的详细信息，请参阅 [内容搜索限制](limits-for-content-search.md)。
  
如果每个邮箱超过 1，000 个邮箱或 100 多封电子邮件要审阅，可以使用其他关键字或条件（如日期范围或发件人/收件人）将初始搜索划分为多个搜索，并单独查看每个搜索的结果。 请务必记下在步骤 7 中删除邮件时将使用的所有 [搜索查询](#step-7-permanently-delete-the-spilled-data)。

当您找到包含溢出数据的电子邮件时，请检查邮件的收件人以确定该邮件是否与外部共享。 若要进一步跟踪邮件，可以收集发件人信息和日期范围，以便可以使用邮件跟踪日志。 此过程在步骤 [5 中介绍](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)。

验证搜索结果后，您可能需要与他人共享您的结果，进行二级审阅。 在步骤 1 中分配给该案例的用户可以查看电子数据展示和网站中Advanced eDiscovery并批准案例结果。 还可以生成报表，而不导出实际内容。 您还可以使用此相同报告作为删除证明，步骤 [8 中对此进行了介绍](#step-8-verify-provide-a-proof-of-deletion-and-audit)。
  
 **生成统计报告：**
  
1. 转到电子 **数据** 展示案例中的"搜索"页面，然后单击要生成报告的搜索。 
    
2. 在飞出页面上，单击"更多> **导出报告"**。
 
      将显示"导出报告"页。

    ![选择搜索，然后单击>页上的"更多内容导出报告"。](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. 选择 **"所有项目"** ，包括由于其他原因已加密或未编制索引的项目，然后单击"生成 **报告"**。

4. 在电子数据展示案例中，单击 **"导出** "以显示导出作业的列表。 您可能必须 **单击"刷新** "以更新列表以显示您创建的导出作业。

5. 单击导出作业，然后单击飞 **出页上** 的"下载报告"。
 
    ![在"导出"页上，单击"导出"，然后单击"下载报告"。](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

" **导出摘要** "报告包含与结果一起找到的位置数和搜索结果的大小。 您可以使用此代码与删除后生成的报告进行比较，并提供作为删除证明。 **结果报告** 包含搜索结果的更详细的摘要，包括主题、发件人、收件人（如果已阅读电子邮件、日期和每封邮件的大小）。 如果此报告中的任何详细信息包含实际泄漏的数据，请务必在调查完成后永久Results.csv文件。

有关导出报告的信息，请参阅导出 [内容搜索报告](export-a-content-search-report.md)。
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>步骤 5：使用邮件跟踪日志检查如何共享溢出的数据

若要进一步调查是否共享了包含泄漏数据的电子邮件，您可以选择使用你在步骤 4 中收集的发件人信息和日期范围信息查询邮件跟踪日志。 对于实时数据，邮件跟踪的保留期为 30 天，历史数据的保留期为 90 天。
  
可以在安全与合规中心内使用邮件跟踪，或在 PowerShell 中Exchange Online cmdlet。 需要注意的是，邮件跟踪无法完全保证返回的数据的完整性。 有关使用邮件跟踪的信息，请参阅： 
  
- [安全与合规中心内的消息跟踪](../security/office-365-security/message-trace-scc.md)
    
- [安全与合规中心&邮件跟踪](https://techcommunity.microsoft.com/t5/exchange-team-blog/new-message-trace-in-office-365-security-038-compliance-center/ba-p/607893)
    
## <a name="step-6-prepare-the-mailboxes"></a>步骤 6：准备邮箱

检查并验证搜索结果是否仅包含必须删除的邮件后，您需要收集在删除泄漏数据时在步骤 7 中要使用的受影响邮箱的电子邮件地址列表。 您可能还必须准备邮箱，然后才能永久删除电子邮件，具体取决于是否对包含溢出数据的邮箱启用单个项目恢复，或者其中任何邮箱是否置于保留状态。
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>获取包含溢出数据的邮箱地址列表

有两种方法可以收集包含溢出数据的邮箱的电子邮件地址列表。

**选项 1：获取包含溢出数据的邮箱地址列表**

1. 打开电子数据展示案例，转到"搜索 **"** 页面并选择相应的内容搜索。 
    
2. 在飞出页面上，单击" **查看结果"**。
    
3. 在“**单独的结果**”下拉列表中，单击“**搜索统计信息**”。
    
4. 在" **类型"** 下拉列表中，单击" **顶部位置"**。
    
    ![在"搜索统计信息"的"首要位置"页面上获取包含搜索结果的邮箱列表。](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    将显示包含搜索结果的邮箱列表。 还会显示每个邮箱中与搜索查询匹配的项目数。
    
5. 复制列表中的信息并将其保存到文件中，或单击"下载"将信息下载到 CSV 文件。 
    
**选项 2：从导出报告中获取邮箱位置**

打开在步骤 4 中下载的"导出摘要 ["报告](#step-4-review-and-validate-case-findings)。 在报告的第一列中，每个邮箱的电子邮件地址列在"位置 **"下**。
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>准备邮箱，以便可以删除溢出的数据

如果启用单个项目恢复或将邮箱置于保留状态，则 (已清除) 邮件将保留在"可恢复的项目"文件夹中。 因此，在可以清除溢出的数据之前，您需要检查现有邮箱配置并禁用单个项目恢复并删除任何保留或保留策略。 请记住，您可以一次准备一个邮箱，然后对不同的邮箱运行相同的命令或创建 PowerShell 脚本以同时准备多个邮箱。

- 有关如何检查单个项目恢复是否已启用或邮箱是否处于保留状态[](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)或是否分配到保留策略的说明，请参阅删除基于云的邮箱的"可恢复的项目"文件夹中的"步骤 1：收集有关邮箱的信息"。 

- 有关禁用单个项目恢复的说明，请参阅删除基于云的邮箱[](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)的保留的"可恢复的项目"文件夹中的"步骤 2：准备邮箱"。 

- 有关如何从邮箱中删除保留或保留策略的说明，请参阅删除基于云的邮箱[](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)的保留的"可恢复的项目"文件夹中的"步骤 3：从邮箱中删除所有保留"。 

- 请参阅删除基于云的邮箱的"可恢复的项目"文件夹中的"步骤 4[](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox)：从邮箱中删除延迟保留"，了解在删除任何类型的保留后删除邮箱上放置的延迟保留的说明。

> [!IMPORTANT]
> 在删除保留或保留策略之前，请与记录管理或法律部门核实。 你的组织可能拥有一个策略，用于定义保留的邮箱或数据泄漏事件是否具有优先级。 
  
请确保在验证溢出的数据已永久删除后将邮箱还原到以前的配置。 请参阅步骤 [7 中的详细信息](#step-7-permanently-delete-the-spilled-data)。

## <a name="step-7-permanently-delete-the-spilled-data"></a>步骤 7：永久删除溢出的数据

使用在步骤 6 中收集和准备的邮箱位置以及步骤 3 中创建和优化的搜索查询来查找包含泄漏数据的电子邮件，现在可以永久删除溢出的数据。  如前所述，若要删除邮件，您必须是组织管理角色组的成员或分配有"搜索和清除"管理角色。 有关向角色组添加用户的信息，请参阅分配 [电子数据展示权限](./assign-ediscovery-permissions.md)。

若要删除溢出的邮件，请参阅搜索 [和删除电子邮件](search-for-and-delete-messages-in-your-organization.md)。

删除溢出的数据时，请记住以下限制：

- 搜索中可用于通过执行搜索和清除操作删除项目的最大邮箱数为 50，000。 如果在步骤 3 中创建的搜索搜索超过 50，000 个邮箱，则清除操作将失败。 如果将搜索配置为包括组织内的所有邮箱，则单次搜索中一般有可能搜索到超过 50,000 个邮箱。 即使包含匹配搜索查询项目的邮箱数量少于 50,000 个，这一限制仍然适用。

- 每个邮箱一次最多可以删除 10 个项目。因为搜索和删除邮件的功能是用作事件响应工具，此限制有助于确保从邮箱中快速删除邮件。此功能并不是为了清理用户邮箱。

> [!IMPORTANT]
> 使用本文中的程序，无法删除高级电子数据展示案例中的审阅集中的电子邮件项目。 这是因为审阅集内的项目是实时服务中项目的副本，这些项被复制并存储在Azure 存储位置。 这意味着在步骤 3 中创建的内容搜索不会返回它们。 若要删除某个审阅集中的项目，必须删除包含该审阅集的高级电子数据展示案例。 有关详细信息，请参阅[关闭或删除高级电子数据展示案例](close-or-delete-case.md)。
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>步骤 8：验证、提供删除证明和审核

工作流中用于管理数据泄漏事件的最后一步是，通过访问电子数据展示案例并重新运行用于删除该数据的相同搜索查询来验证是否从邮箱中永久删除了溢出的数据，以确认未返回任何结果。 确认已永久删除溢出的数据后，可以导出报告， (连同原始报告一) 作为删除证明。 然后， [如果将来必须](close-reopen-delete-core-ediscovery-cases.md) 引用案例，可以关闭允许重新打开该案例。 此外，您还可以将邮箱恢复为以前的状态，删除用于查找溢出数据的搜索查询，并搜索管理数据泄漏事件时所执行任务的审核记录。
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>将邮箱恢复为以前的状态

如果在步骤 6 中更改了任何邮箱配置，以在删除泄漏数据之前准备邮箱，则需要将其恢复为以前的状态。 请参阅删除保留的基于云的邮箱的"可恢复的项目"文件夹中的"步骤 6：将邮箱恢复 [为以前的状态"](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)。
  
### <a name="deleting-the-search-query"></a>删除搜索查询

如果在步骤 3 中创建和使用的搜索查询中的关键字包含所有实际溢出的数据，您应该删除搜索查询以防止进一步的数据泄漏。
  
1. 在安全与合规中心，打开电子数据展示案例，转到"搜索"页面，然后选择适当的内容搜索。

2. 在飞出页面上，单击"删除 **"**。

    ![选择搜索，然后单击飞出页面上的"删除"。](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)

### <a name="auditing-the-data-spillage-investigation-process"></a>审核数据泄漏调查过程

你可以搜索审核日志调查期间执行电子数据展示活动。 您还可以搜索该审核日志返回在步骤 7 中运行以删除溢出数据的 **New-ComplianceSearchAction -Purge** 命令的审核记录。 有关详细信息，请参阅：

- [搜索审核日志](search-the-audit-log-in-security-and-compliance.md)

- [在审核日志中搜索电子数据展示活动](search-for-ediscovery-activities-in-the-audit-log.md)
