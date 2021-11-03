---
title: 收集云附件Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用 Advanced eDiscovery 中的集合收集云附件，以在调查或案例中进行审阅。
ms.openlocfilehash: 22986c8f844f035f4da57ccdfa3ee523e39118ec
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717433"
---
# <a name="collect-cloud-attachments-in-advanced-ediscovery-preview"></a>在预览版中Advanced eDiscovery (云) 

云附件是通常存储在网站和网站SharePoint文档OneDrive。 因此，可以选择共享指向文件的链接，而不是在电子邮件或聊天对话Teams文档的实际副本。 云附件是共享文档和与组织中其他人协作的有效方式。 但是，云附件在电子数据展示工作流期间带来了挑战，因为电子数据展示搜索中仅返回云附件链接，而不是共享文档中的实际内容。 为了应对这一挑战，Advanced eDiscovery两种用于收集云附件的解决方案：  

- 收集链接到云附件中的文档实时版本。

- 收集在云附件中共享文档时的文档版本。

## <a name="collecting-cloud-attachments"></a>收集云附件

创建草稿集合且搜索结果包含包含云附件的项目时，在将草稿集合提交到审阅集时，必须选择收集云附件的目标。 选择此选项后，Advanced eDiscovery将链接到云附件中的文档添加到审阅集。 这允许您查看目标文档，并确定文档是否与案例或调查相关。

以下屏幕截图显示了将集合提交到审阅集时包含云附件目标的选项。

![将集合提交到审阅集时包含云附件的选项](../media/CollectCloudAttachments1.png)

> [!NOTE]
>- 如果在邮件[中](advanced-ediscovery-large-cases.md)采用大Advanced eDiscovery格式，则默认情况下选择在审阅集中添加云附件的选项，且无法取消选择。<br/>
>- 除了在审阅集内共享云附件 (，还可以选择包含) 的所有版本。  
有关将集合提交到审阅集的说明，请参阅 [将草稿集合提交到审阅集](commit-draft-collection.md)。

## <a name="collecting-the-version-shared-in-a-cloud-attachment"></a>收集云附件中共享的版本

用于Advanced eDiscovery云附件的工作流仅包括将最新版本的云附件添加到审阅集。 这意味着收集并添加到审阅集的版本可能不同于最初在云附件中共享的版本。 因此，共享时存在于云附件中的内容可能已删除，并且在当前版本（已添加到审阅集）中不存在。

组织现在可以选择使用Microsoft 365保留标签，以在作为云附件共享文档时保留文档版本。 为此，你的组织可以创建保留标签，选择将标签应用于云附件的选项，然后自动将标签应用于存储在 SharePoint 和 OneDrive。 设置此配置后，在共享文件时将创建一个文档副本。 此外，如果文档被修改并再次作为云附件共享，也会保留修改后的版本。 如果文件被修改并再次共享，将保留该文件的新副本作为新版本。

保留云附件的共享版本可帮助组织将潜在相关内容的保留和集合范围缩小到共享的特定文档版本，而不是当前实时版本。 实施此保留解决方案后，将收集云附件的当前实时版本和云附件中共享的版本，并添加到审阅集。

有关设置保留标签并自动应用于云附件的说明，请参阅自动将标签应用于 [云附件](apply-retention-labels-automatically.md#auto-apply-labels-to-cloud-attachments)。

以下屏幕截图显示了添加到审阅集的名为 *XYZ Research.docx* 的云附件文档。 文档作为云附件共享在Teams对话中。 审阅集还包含最初在云附件中共享的版本。 请注意，此版本的云附件的名称由系统生成，作者被标识为 **SharePoint。**

![在审阅集中显示的共享云附件的版本](../media/CollectCloudAttachments2.png)

此外，当前实时版本和共享的版本具有相同的 **FamilyId** 属性值，该值与父对象 (如电子邮件或 Teams 聊天对话) 的 **FamilyId** 相同。 这允许你将云附件与共享附件的项进行分组。

实施保留标签并自动将标签应用于 SharePoint 文档后，在将草稿集合提交到审阅集时，仍可以选择收集云附件的选项。 收集云附件后，当前实时版本和最初共享的版本都将被添加到审阅集。
