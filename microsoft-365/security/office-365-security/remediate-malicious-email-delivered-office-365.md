---
title: 修正在Office 365中传递的恶意电子邮件
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.collection: M365-security-compliance
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection: ''
search.appverid: MET150
description: 威胁修正
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98b425c39cd12aea55714e9ade192e2e770b26cd
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714829"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>修正在 Office 365 中传递的恶意电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)

修正意味着对威胁采取规定措施。 系统可以通过零小时自动清除 (ZAP) 或安全团队通过修正操作（例如 *移动到收件箱*、 *移动到垃圾* 邮件、 *移动到已删除的项*、 *软删除* 或 *硬删除*）来清理发送给组织的恶意电子邮件。 Microsoft Defender for Office 365计划 2/E5 使安全团队能够通过手动和自动调查来修正电子邮件和协作功能中的威胁。

> [!NOTE]
> 若要修正恶意电子邮件，安全团队需要分配给他们的 *搜索和清除* 角色。 角色分配是通过[Microsoft 365 Defender门户中的权限完成的](permissions-microsoft-365-security-center.md)。

## <a name="what-you-need-to-know-before-you-begin"></a>开始之前需要了解的内容

管理员可以对电子邮件执行所需的操作，但若要批准这些操作，他们必须在 **电子邮件&** Microsoft 365 Defender门户中的协作权限中分配搜索 *和清除* 角色。 如果没有将 *"搜索和清除"* 角色添加到其中一个角色组，他们将无法执行该操作。

## <a name="manual-and-automated-remediation"></a>手动和自动修正

当安全团队使用资源管理器中的搜索和筛选功能手动识别威胁时，会进行 *手动搜寻*。 识别一组需要修正的电子邮件后，可以通过任何电子邮件视图 (*恶意软件*、 *网络钓鱼* 或 *所有电子邮件*) 触发手动电子邮件修正。

:::image type="content" source="../../media/microsoft-365-defender-threat-explorer-manual-remediation.png" alt-text="按日期在Office 365资源管理器中手动搜寻的屏幕截图。":::

安全团队可以通过多种方式使用资源管理器选择电子邮件：

- 手动选择电子邮件：在各种视图中使用筛选器。 选择最多 100 封电子邮件进行修正。

- 查询选择：使用顶部 **选择"所有** "按钮选择整个查询。 同一查询也显示在操作中心邮件提交详细信息中。 客户最多可以从威胁资源管理器提交 200，000 封电子邮件。  

- 排除查询选择：有时安全操作团队可能需要通过选择整个查询并手动排除查询中的某些电子邮件来修正电子邮件。 为此，管理员可以使用" **选择所有** "复选框并向下滚动以手动排除电子邮件。 查询最多可以保存 1，000 封电子邮件。 最大排除数为 100。

通过资源管理器选择电子邮件后，可以通过采取直接操作或排队发送电子邮件来开始修正操作：

- 直接审批：当具有适当权限的安全人员选择" *移动到收件箱*"、" *移动到垃圾* 邮件"、" *移动到已删除的物品*"、" *软删除*"或" *硬删除* "等操作，并遵循后续修正步骤时，修正过程将开始执行所选操作。
> [!NOTE]
>在修正开始时，它会同时生成警报和调查。 警报显示在警报队列中，名为"管理员提交的管理操作"，表明安全人员采取了修正实体的行动。 它提供详细信息，例如执行操作的人员的姓名、支持调查链接、时间等。每次对实体执行修正等严厉操作时，都非常了解这一点。 所有这些操作都可以在" **操作&提交** \> **操作中心**  -> **"选项卡** 下进行 (公共预览) 。

- 双重批准：没有适当权限或需要等待执行操作的管理员可以执行"添加到修正"操作。 在这种情况下，目标电子邮件将添加到修正容器中。 在执行修正之前，需要审批。

**自动调查和响应** 操作由警报或资源管理器中的安全操作团队触发。 这些操作可能包括必须由安全运营团队批准的建议修正操作。 这些操作包含在自动调查的 **"操作"** 选项卡上。

> [!div class="mx-imgBorder"]
> [!["Zapped"页中包含恶意软件的邮件显示 Zap 执行时间。](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

在资源管理器、高级搜寻或自动调查中创建的所有修正 (直接审批) 显示在操作中心中。 通过"**操作"&"提交****操作中心**  -> **"选项卡** 下的左侧导航面板访问这些\>内容。

在资源管理器或高级搜寻中创建或通过自动调查创建的所有修正 (直接批准) 都显示在操作中心中。 通过"**操作"&"提交****操作中心**  -> **"选项卡** 下的左侧导航面板访问这些\>内容。 

使用双重审批过程等待审批的手动操作 (1。 添加到由一名安全操作团队成员修正，2。 由另一个安全操作团队成员审查和批准) 仅在旧的Defender for Office 365操作中心 **审查** \> **操作中心** 中可见，而不是在事件/调查和统一行动中心中可见。

> [!NOTE]
> 双重审批：仅在办公室操作中心  **查看** \> **操作中心中可用的操作**

:::image type="content" source="../../media/microsoft-365-defender-action-center-history.png" alt-text="统一的操作中心显示 30 天的修正操作。":::

统一操作中心显示过去 30 天的修正操作。 通过资源管理器执行的操作按创建修正时安全操作团队提供的名称以及审批 ID、调查 ID 列出。通过自动调查执行的操作具有以触发调查的相关警报开头的标题，例如 *Zap 电子邮件群集*。

打开任何修正项目以查看有关它的详细信息，包括其修正名称、审批 ID、调查 ID、创建日期、说明、状态、操作源、操作类型、由状态决定。 它还打开一个侧窗格，其中包含操作详细信息、电子邮件群集详细信息、警报和事件详细信息。

- *打开"调查"页* ，这将打开管理员调查，其中包含较少的详细信息和选项卡。 它显示了以下详细信息：相关警报、选择用于修正的实体、执行的操作、修正状态、实体计数、日志、操作审批者。 此调查跟踪管理员手动完成的调查，并包含管理员所选内容的详细信息，因此称为管理员操作调查。 无需对调查采取行动，并提醒其已处于批准状态。
- *电子邮件计数* 显示通过威胁资源管理器提交的电子邮件数。 这些电子邮件可以是可操作的或不可操作的。
- *操作日志* 显示修正状态的详细信息，例如成功、失败且已在目标中。

:::image type="content" source="../../media/microsoft-365-defender-action-center-history-panel.png" alt-text="打开&quot;移动到收件箱&quot;选项的操作中心。":::

  - **可操作**：可以在以下云邮箱位置处理和移动以下云邮箱位置中的电子邮件：
    - Inbox
    - 垃圾
    - 已删除文件夹
    - 软删除的文件夹

      > [!NOTE]
      > 目前，只有有权访问邮箱的用户才能从软删除的文件夹中恢复项目。

  - **不可操作**：以下位置中的电子邮件无法在修正操作中执行或移动：
    - Quarantine
    - 硬删除的文件夹
    - 本地/外部
    - 失败/删除

  可疑消息被归类为可修正或不可修正。 在大多数情况下，可修正和不可修正的消息合并等于提交的邮件总数。 但在极少数情况下，这可能不是真的。 这可能会由于系统延迟、超时或消息过期而发生。 消息会根据组织的资源管理器保留期过期。

  除非在组织的资源管理器保留期后修正旧邮件，否则如果看到数字不一致，建议重试修正项目。 对于系统延迟，修正更新通常会在几小时内刷新。

  如果组织在资源管理器中的电子邮件保留期为 30 天，并且你正在修正回 29-30 天的电子邮件，则邮件提交计数可能并不总是加起来。 电子邮件可能已开始从保留期移出。

  如果修正停滞在"正在进行"状态一段时间，则可能是由于系统延迟。 修正可能需要长达几个小时的时间。 你可能会看到邮件提交计数的变化，因为某些电子邮件可能由于系统延迟而在修正开始时未包含查询。 在这种情况下重试修正是一个好主意。

  > [!NOTE]
  > 为了获得最佳结果，应按 50，000 个或更少的批处理进行修正。

  只有修正期间才会处理可修正的电子邮件。 无法通过Office 365电子邮件系统修正不可修正的电子邮件，因为它们不存储在云邮箱中。

  管理员可以根据需要对隔离中的电子邮件采取措施，但如果这些电子邮件未手动清除，则这些电子邮件将过期隔离。 默认情况下，用户无法访问因恶意内容而隔离的电子邮件，因此安全人员无需采取任何措施来消除隔离中的威胁。 如果电子邮件位于本地或外部，则可以联系用户来处理可疑电子邮件。 或者，管理员可以使用单独的电子邮件服务器/安全工具进行删除。 可以通过在资源管理器中应用 *传递位置 = 本地* 外部筛选器来识别这些电子邮件。 对于失败或删除的电子邮件或用户无法访问的电子邮件，将没有任何电子邮件可以缓解，因为这些邮件无法访问邮箱。

 
- **操作日志**：显示已在目标中修正、成功、失败的消息。

  状态可以是：

  - **已启动**：已触发修正。
    - **排队**：修正已排队以缓解电子邮件。
    - **正在进行**：正在进行缓解。
    - **已完成**：已成功完成或出现某些故障的所有可修正电子邮件的缓解措施。
    - **失败**：未成功修正。

  由于只能处理可修正的电子邮件，因此每个电子邮件的清理显示为成功或失败。 从可修正的电子邮件总数中，报告成功和失败的缓解措施。

  - **成功**：已完成对可修正电子邮件的所需操作。 例如：管理员希望从邮箱中删除电子邮件，因此管理员会执行软删除电子邮件的操作。 如果在执行操作后未在原始文件夹中找到可修正的电子邮件，则状态将显示为成功。

  - **失败**：针对可修正电子邮件的所需操作失败。 例如：管理员希望从邮箱中删除电子邮件，因此管理员会执行软删除电子邮件的操作。 如果在执行操作后邮箱中仍找到可修正的电子邮件，状态将显示为失败。
  
  - **已在目标中**：已对电子邮件执行所需的操作，或者电子邮件已存在于目标位置。 例如：第一天，管理员通过资源管理器软删除了一封电子邮件。 然后，类似的电子邮件将显示在管理员再次软删除的第 2 天。选择这些电子邮件时，管理员最终会从第一天起选取一些已软删除的电子邮件。 现在，这些电子邮件不再被处理，它们只会显示为"已在目标中"，因为没有对它们采取任何操作，因为它们存在于目标位置。

  - **新增** 功能：已 *在操作* 日志中添加了目标列。 此功能使用威胁资源管理器中的最新传递位置来指示是否已修正邮件。 *已在目标中* 可帮助安全团队了解仍需要解决的消息总数。

只能对威胁资源管理器的收件箱、垃圾邮件、已删除文件夹和软删除文件夹中的消息执行操作。 下面是新列的工作原理示例。 在收件箱中显示的消息上执行 *软删除操作* ，然后将根据策略处理该消息。 下次执行软删除时，此消息将显示在列"已在目标中"下，表示无需再次解决。

选择操作日志中的任何项以显示修正详细信息。 如果详细信息显示"成功"或"在邮箱中找不到"，则该项已从邮箱中删除。 在修正期间有时会出现系统错误。 在这些情况下，最好重试修正操作。

若要修正大量电子邮件，请导出通过邮件提交发送以进行修正的消息，以及通过操作日志修正的消息。 导出限制增加到 100，000 条记录。

 管理员可以采取补救措施，例如将电子邮件移动到"垃圾邮件"、"收件箱"或"已删除邮件"文件夹，以及从高级搜寻页面中删除软删除或硬删除等操作。

:::image type="content" source="../../media/microsoft-365-defender-advanced-hunting-actions-pane.png" alt-text="&quot;高级搜寻，采取操作&quot;面板，其中包含你选择的操作。":::

修正可缓解威胁、解决可疑电子邮件，并有助于确保组织安全。
