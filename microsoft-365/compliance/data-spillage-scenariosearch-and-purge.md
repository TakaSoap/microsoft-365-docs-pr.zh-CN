---
title: 电子数据展示解决方案系列数据溢出方案 - 搜索和清除
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
description: 使用电子数据展示和搜索工具来管理和响应组织中的数据溢出事件。
ms.openlocfilehash: 55bed2461d48d77e7dbb756402439f394ac55270
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760902"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>电子数据展示解决方案系列：数据溢出方案 - 搜索和清除

 **什么是数据溢出，你为什么要关心？** 数据泄漏是在机密文档发布到不受信任的环境中时。 检测到数据溢出事件时，请务必快速评估溢出的大小和位置，检查其周围的用户活动，然后从系统中永久清除溢出的数据。
  
## <a name="data-spillage-scenario"></a>数据溢出方案

你是 Contoso 的首席信息安全官。 你将了解数据溢出情况，其中员工在不知不觉中通过电子邮件与多人共享了一份高度机密的文档。 你希望快速评估在内部和外部接收此文档的人员。 确定后，你希望与其他调查人员共享案件调查结果以进行审查，然后从Office 365中永久删除数据。 调查完成后，你希望生成一份包含永久删除证据的报告和其他案例详细信息，供将来参考。
  
### <a name="scope-of-this-article"></a>本文的范围

本文档提供有关如何从Microsoft 365永久删除消息的说明列表，使其无法访问或恢复。 若要删除邮件并使其可恢复，直到已删除的项目保留期到期，请参阅 [搜索和删除组织中的电子邮件](search-for-and-delete-messages-in-your-organization.md)。
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>用于管理数据溢出事件的工作流

下面介绍如何管理数据溢出事件：

![用于管理数据溢出事件的 8 步工作流。](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[ (可选) 步骤 1：管理谁可以访问案例并设置合规性边界](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[步骤 2：创建电子数据展示案例](#step-2-create-an-ediscovery-case)<br/>
[步骤 3：搜索溢出的数据](#step-3-search-for-the-spilled-data)<br/>
[步骤 4：审查和验证案例调查结果](#step-4-review-and-validate-case-findings)<br/>
[步骤 5：使用消息跟踪日志检查如何共享溢出的数据](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[步骤 6：准备邮箱](#step-6-prepare-the-mailboxes)<br/>
[步骤 7：永久删除溢出的数据](#step-7-permanently-delete-the-spilled-data)<br/>
[步骤 8：验证、提供删除证明和审核](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>开始之前要了解的事项

- 当邮箱处于保留状态时，已删除的邮件将保留在“可恢复邮件”文件夹中，直到保留期过期或解除保留。 [步骤 6](#step-6-prepare-the-mailboxes) 介绍如何从邮箱中删除保留。 在删除保留之前，请与记录管理部门或法律部门联系。 你的组织可能有一个策略，用于定义邮箱是否处于保留状态或数据溢出事件优先级。 
    
- 若要控制数据溢出调查员可以搜索和管理谁可以访问案例的用户邮箱，可以设置合规性边界并创建自定义角色组，步骤 [1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries) 中对此进行了介绍。 为此，必须是组织管理角色组的成员或分配角色管理角色。 如果你或组织中的管理员已设置合规性边界，则可以跳过步骤 1。
    
- 若要创建案例，必须是电子数据展示管理器角色组的成员，或者是分配了 Case Management 角色的自定义角色组的成员。 如果你不是成员，请要求Microsoft 365管理员[将你添加到电子数据展示管理器角色组](assign-ediscovery-permissions.md)。
    
- 若要创建并运行内容搜索，您必须是电子数据展示管理员角色组的成员，或者分配有“合规性搜索”管理角色。 若要删除邮件，您必须是组织管理角色组的成员或分配有“搜索并清除”管理角色。 有关将用户添加到角色组的信息，请参 [阅分配电子数据展示权限](./assign-ediscovery-permissions.md)。
    
- 若要在步骤 8 中搜索审核日志电子数据展示活动，必须为组织启用审核。 可以搜索过去 90 天内执行的活动。 若要详细了解如何启用和使用审核，请参阅步骤 8 中的 [“审核数据溢出调查过程](#auditing-the-data-spillage-investigation-process) ”部分。 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a> (可选) 步骤 1：管理谁可以访问案例并设置合规性边界

根据组织实践，你需要控制谁可以访问电子数据展示案例，该案例用于调查数据溢出事件并设置合规性边界。 执行此操作的最简单方法是将调查人员添加为Microsoft 365 合规中心中现有角色组的成员，然后将该角色组添加为电子数据展示案例的成员。 有关内置电子数据展示角色组以及如何将成员添加到电子数据展示案例的信息，请参阅 [分配电子数据展示权限](assign-ediscovery-permissions.md)。
  
还可以创建符合组织需求的新角色组。 例如，你可能希望组织中的一组数据溢出调查员访问并协作处理所有数据溢出案例。 为此，可以创建“数据溢出调查员”角色组， (导出、RMS 解密、审阅、预览、合规性搜索和案例管理) 分配适当的角色，将数据溢出调查员添加到角色组，然后将该角色组添加为数据溢出电子数据展示案例的成员。 有关如何执行此操作的详细说明，请参阅[为Office 365中的电子数据展示调查设置合规性边界](set-up-compliance-boundaries.md)。 
  
## <a name="step-2-create-an-ediscovery-case"></a>步骤 2：创建电子数据展示案例

电子数据展示案例提供了管理数据溢出调查的有效方法。 可以将成员添加到在步骤 1 中创建的角色组，将角色组添加为电子数据展示案例的新成员，执行迭代搜索以查找溢出的数据，导出报表以共享，跟踪案例的状态，然后根据需要参考案例的详细信息。 请考虑为用于数据溢出事件的电子数据展示事例建立命名约定，并在案例名称和说明中提供尽可能多的信息，以便你可以在将来找到并参考（如有必要）。
  
若要创建新案例，可以在安全和合规中心使用电子数据展示。 请参阅[核心电子数据展示开始](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)中的“创建新案例”。
  
## <a name="step-3-search-for-the-spilled-data"></a>步骤 3：搜索溢出的数据

创建案例和管理访问权限后，可以使用该案例进行迭代搜索，以查找溢出的数据并标识包含溢出数据的邮箱。 你将使用用于查找电子邮件的相同搜索查询在 [步骤 7](#step-7-permanently-delete-the-spilled-data) 中删除这些相同的邮件。
  
若要创建与电子数据展示案例相关联的内容搜索，请参阅 [“搜索核心电子数据展示”案例中的内容](search-for-content-in-core-ediscovery.md)。
  
> [!IMPORTANT]
> 在搜索查询中使用的关键字可能包含要搜索的实际溢出数据。 例如，如果搜索包含社保号码的文档，并使用该文档作为搜索关键字，则必须事后删除查询以避免进一步溢出。 请参阅步骤 8 中的 [“删除搜索查询](#deleting-the-search-query) ”。
  
## <a name="step-4-review-and-validate-case-findings"></a>步骤 4：审查和验证案例调查结果

创建内容搜索后，需要查看和验证搜索结果，并验证它们是否仅包含必须删除的电子邮件。 在内容搜索中，可以预览 1，000 封电子邮件的随机采样，而无需导出搜索结果以避免进一步的数据溢出。 可以在 [内容搜索](limits-for-content-search.md)限制处阅读有关预览限制的详细信息。
  
如果每个邮箱有超过 1，000 个邮箱或超过 100 封电子邮件要审阅，则可以使用其他关键字或条件（如日期范围或发件人/收件人）将初始搜索划分为多个搜索，并单独查看每个搜索的结果。 请务必记下删除 [步骤 7](#step-7-permanently-delete-the-spilled-data) 中的消息时要使用的所有搜索查询。

找到包含溢出数据的电子邮件时，请检查邮件的收件人以确定邮件是否在外部共享。 若要进一步跟踪邮件，可以收集发件人信息和日期范围，以便可以使用消息跟踪日志。 [步骤 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared) 中介绍了此过程。

验证搜索结果后，可能需要与其他人共享你的发现，以便进行辅助评审。 在步骤 1 中分配到案例的人员可以在电子数据展示和Advanced eDiscovery中查看案例内容，并批准案件调查结果。 还可以生成报表，而无需导出实际内容。 还可以将此报表用作删除证明，如 [步骤 8](#step-8-verify-provide-a-proof-of-deletion-and-audit) 中所述。
  
 **若要生成统计报告，**
  
1. 转到电子数据展示案例中的 **“搜索** ”页，然后单击要为其生成报表的搜索。 
    
2. 在浮出控件页上，单击 **“更多>导出报表**。
 
      将显示“导出报表”页。

    ![选择搜索，然后单击浮出页上的“更多>导出报表”。](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. 选择 **所有项（包括那些具有未识别格式的项目）都已加密或因其他原因未编制索引** ，然后单击“ **生成报表**”。

4. 在电子数据展示案例中，单击“ **导** 出”以显示导出作业的列表。 可能需要单击 **“刷新** ”以更新列表以显示创建的导出作业。

5. 单击导出作业，然后单击浮出控件页上的 **“下载** ”报表。
 
    ![在“导出”页上，单击“导出”，然后单击“下载报表”。](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

导 **出摘要** 报表包含结果找到的位置数和搜索结果的大小。 可以使用此功能与删除后生成的报表进行比较，并提供删除证明。 “ **结果** ”报告包含搜索结果的更详细摘要，包括主题、发件人、收件人（如果读取电子邮件、日期和每封邮件的大小）。 如果此报告中的任何详细信息包含实际溢出的数据，请务必在调查完成后永久删除Results.csv文件。

有关导出报表的详细信息，请参阅 [“导出内容搜索”报表](export-a-content-search-report.md)。
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>步骤 5：使用消息跟踪日志检查如何共享溢出的数据

若要进一步调查是否共享了包含溢出数据的电子邮件，可以选择使用在步骤 4 中收集的发件人信息和日期范围信息查询邮件跟踪日志。 实时数据的消息跟踪保留期为 30 天，历史数据保留期为 90 天。
  
可以在安全性和合规中心中使用消息跟踪，或在 Exchange Online PowerShell 中使用相应的 cmdlet。 请务必注意，消息跟踪不会对返回的数据的完整性提供完全保证。 有关使用消息跟踪的详细信息，请参阅： 
  
- [安全与合规中心内的消息跟踪](../security/office-365-security/message-trace-scc.md)
    
- [安全&合规中心中的新消息跟踪](https://techcommunity.microsoft.com/t5/exchange-team-blog/new-message-trace-in-office-365-security-038-compliance-center/ba-p/607893)
    
## <a name="step-6-prepare-the-mailboxes"></a>步骤 6：准备邮箱

查看并验证搜索结果是否仅包含必须删除的消息后，需要收集受影响邮箱的电子邮件地址列表，以便在删除溢出的数据时在步骤 7 中使用。 您可能还必须准备邮箱，然后才能永久删除电子邮件，具体取决于是否在包含溢出数据的邮箱上启用了单项恢复，或者这些邮箱中是否有任何一个处于保留状态。
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>获取包含溢出数据的邮箱地址列表

可通过两种方法收集包含溢出数据的邮箱的电子邮件地址列表。

**选项 1：获取包含溢出数据的邮箱地址列表**

1. 打开电子数据展示案例，转到 **“搜索** ”页，然后选择相应的内容搜索。 
    
2. 在浮出控件页上，单击 **“查看结果**”。
    
3. 在“**单独的结果**”下拉列表中，单击“**搜索统计信息**”。
    
4. 在 **“类型** ”下拉列表中，单击 **“顶部位置**”。
    
    ![获取在搜索统计信息的“顶部位置”页上包含搜索结果的邮箱列表。](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    将显示包含搜索结果的邮箱列表。 还会显示与搜索查询匹配的每个邮箱中的项数。
    
5. 复制列表中的信息并将其保存到文件中，或单击“ **下载** ”将信息下载到 CSV 文件。 
    
**选项 2：从导出报表获取邮箱位置**

打开在 [步骤 4](#step-4-review-and-validate-case-findings) 中下载的导出摘要报表。 在报表的第一列中，每个邮箱的电子邮件地址都列在 **“位置”** 下。
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>准备邮箱，以便可以删除溢出的数据

如果启用了单个项目恢复，或者邮箱被搁置，则永久删除的 (清除) 邮件将保留在“可恢复邮件”文件夹中。 因此，在清除溢出的数据之前，需要检查现有邮箱配置并禁用单项恢复并删除任何保留或保留策略。 请记住，可以一次准备一个邮箱，然后在不同的邮箱上运行相同的命令，或创建 PowerShell 脚本以同时准备多个邮箱。

- 请参阅“步骤 1：收集 [基于云的邮箱的”可恢复邮件“文件夹中的](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) ”删除邮件“中的”步骤 1：收集有关邮箱的信息“，了解有关如何检查是否启用单个项目恢复或邮箱是否处于保留状态或是否已分配给保留策略的说明。 

- 有关禁用单个项目恢复的说明，请参阅“步骤 2：准备邮箱”中的“删除 [基于云的邮箱的”可恢复邮件“文件夹](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) 中的项目。 

- 有关如何从邮箱中删除保留或保留策略的说明，请参阅“删除 [基于云的邮箱的”可恢复邮件“文件夹中的](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) ”步骤 3：从邮箱中删除所有保留项”。 

- 请参阅“步骤 4：从邮箱中删除邮件中的延迟保留”，在 [保留的基于云的邮箱的“可恢复邮件”文件夹中](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) ，了解有关删除任何类型的保留后放置在邮箱上的延迟保留的说明。

> [!IMPORTANT]
> 在删除保留或保留策略之前，请咨询记录管理或法律部门。 你的组织可能具有一个策略，用于定义邮箱是否处于保留状态或数据溢出事件优先级。 
  
确认已永久删除溢出的数据后，请务必将邮箱还原到以前的配置。 请参阅 [步骤 7](#step-7-permanently-delete-the-spilled-data) 中的详细信息。

## <a name="step-7-permanently-delete-the-spilled-data"></a>步骤 7：永久删除溢出的数据

使用在步骤 6 中收集和准备的邮箱位置以及在步骤 3 中创建和优化的搜索查询来查找包含溢出数据的电子邮件，现在可以永久删除溢出的数据。  如前所述，若要删除消息，必须是组织管理角色组的成员或分配搜索和清除管理角色。 有关将用户添加到角色组的信息，请参 [阅分配电子数据展示权限](./assign-ediscovery-permissions.md)。

若要删除溢出的消息，请参阅 [搜索和删除电子邮件](search-for-and-delete-messages-in-your-organization.md)。

删除溢出的数据时，请注意以下限制：

- 搜索中可用于通过执行搜索和清除操作删除项目的最大邮箱数为 50，000。 如果在步骤 3 中创建的搜索搜索搜索超过 50，000 个邮箱，则清除操作将失败。 如果将搜索配置为包括组织内的所有邮箱，则单次搜索中一般有可能搜索到超过 50,000 个邮箱。 即使包含匹配搜索查询项目的邮箱数量少于 50,000 个，这一限制仍然适用。

- 每个邮箱一次最多可以删除 10 个项目。因为搜索和删除邮件的功能是用作事件响应工具，此限制有助于确保从邮箱中快速删除邮件。此功能并不是为了清理用户邮箱。

> [!IMPORTANT]
> 使用本文中的程序，无法删除高级电子数据展示案例中的审阅集中的电子邮件项目。 这是因为审阅集中的项目是实时服务中复制并存储在Azure 存储位置的项目副本。 这意味着，在步骤 3 中创建的内容搜索不会返回这些内容。 若要删除某个审阅集中的项目，必须删除包含该审阅集的高级电子数据展示案例。 有关详细信息，请参阅[关闭或删除高级电子数据展示案例](close-or-delete-case.md)。
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>步骤 8：验证、提供删除证明和审核

在工作流中管理数据溢出事件的最后一步是，通过转到电子数据展示案例并重新运行用于删除该数据以确认未返回结果的同一搜索查询，验证是否已从邮箱中永久删除溢出数据。 确认已永久删除溢出的数据后，可以导出报表并将其与原始报表一起 () 作为删除证明。 然后，如果将来必须引用它，则可以关闭允许重新打开它 [的情况](close-reopen-delete-core-ediscovery-cases.md) 。 此外，还可以将邮箱还原到以前的状态，删除用于查找溢出数据的搜索查询，以及搜索管理数据溢出事件时执行的任务的审核记录。
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>将邮箱还原到以前的状态

如果在删除溢出的数据之前更改了步骤 6 中的任何邮箱配置来准备邮箱，则需要将它们还原为以前的状态。 请参阅“步骤 6：将邮箱还原到以前的状态”，请参阅 [保留的基于云的邮箱的“可恢复邮件”文件夹中的“删除项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)”。
  
### <a name="deleting-the-search-query"></a>删除搜索查询

如果在步骤 3 中创建和使用的搜索查询中的关键字包含一些实际溢出的数据，则应删除搜索查询以防止进一步的数据溢出。
  
1. 在安全和合规中心中，打开电子数据展示案例，转到 **“搜索** ”页，然后选择相应的内容搜索。

2. 在浮出控件页上，单击 **“删除**”。

    ![选择搜索，然后单击浮出控件页上的“删除”。](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)

### <a name="auditing-the-data-spillage-investigation-process"></a>审核数据溢出调查过程

可以在审核日志中搜索调查期间执行的电子数据展示活动。 还可以搜索审核日志，以返回在步骤 7 中运行 **的 New-ComplianceSearchAction -Purge** 命令的审核记录，以删除溢出的数据。 有关详细信息，请参阅：

- [搜索审核日志](search-the-audit-log-in-security-and-compliance.md)

- [在审核日志中搜索电子数据展示活动](search-for-ediscovery-activities-in-the-audit-log.md)
