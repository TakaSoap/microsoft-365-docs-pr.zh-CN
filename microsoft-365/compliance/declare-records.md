---
title: 使用保留标签声明记录
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 使用保留标签声明记录。
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695234"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="dea56-103">使用保留标签声明记录</span><span class="sxs-lookup"><span data-stu-id="dea56-103">Declare records by using retention labels</span></span>

><span data-ttu-id="dea56-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="dea56-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dea56-105">使用[保留标签](retention.md#retention-labels)将内容标记为记录。</span><span class="sxs-lookup"><span data-stu-id="dea56-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="dea56-106">你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="dea56-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="dea56-107">配置保留标签以声明记录</span><span class="sxs-lookup"><span data-stu-id="dea56-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="dea56-108">创建[保留标签](retention.md#retention-labels)时，请选择将内容标记为记录的选项。</span><span class="sxs-lookup"><span data-stu-id="dea56-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="dea56-109">从 Microsoft 365 合规中心的“**信息管理**”创建或配置保留标签时，将内容标记为记录的选项不可用。</span><span class="sxs-lookup"><span data-stu-id="dea56-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dea56-110">此时，反而是必须使用“**记录管理**”。</span><span class="sxs-lookup"><span data-stu-id="dea56-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="dea56-111">在 [Microsoft 365 合规中心](https://compliance.microsoft.com)中，转到“**记录管理**”\>“**文件计划**”。</span><span class="sxs-lookup"><span data-stu-id="dea56-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="dea56-112">在“文件计划”\*\*\*\* 页面上，选择“创建标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dea56-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="dea56-113">在向导的“**标签设置**”页面上，选择将内容分类为记录的选项。</span><span class="sxs-lookup"><span data-stu-id="dea56-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![选中“使用标签将内容分类为‘记录’”复选框](../media/recordversioning6.png)

3. <span data-ttu-id="dea56-115">根据需要，将保留标签应用于 SharePoint 或 OneDrive 文档和 Exchange 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dea56-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="dea56-116">有关说明，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="dea56-116">For instructions:</span></span>
    
    - [<span data-ttu-id="dea56-117">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="dea56-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="dea56-118">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="dea56-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="dea56-119">对内容应用已配置保留标签</span><span class="sxs-lookup"><span data-stu-id="dea56-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="dea56-120">当用户可对应用中的内容应用将内容标记为记录的保留标签时：</span><span class="sxs-lookup"><span data-stu-id="dea56-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="dea56-121">对于 Exchange，任何拥有邮箱写入权限的用户均可应用这些标签。</span><span class="sxs-lookup"><span data-stu-id="dea56-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="dea56-122">对于 SharePoint 和 OneDrive，默认“成员”组（“参与”权限级别）中的任何用户均可应用这些标签。</span><span class="sxs-lookup"><span data-stu-id="dea56-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="dea56-123">使用保留标签标记为记录的文档示例：</span><span class="sxs-lookup"><span data-stu-id="dea56-123">Example of a document marked as record by using a retention label:</span></span>

![标记为记录的文档的详细信息窗格](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="dea56-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dea56-125">Next steps</span></span>

<span data-ttu-id="dea56-126">如果需要更新作为记录的文档，请参阅[使用记录版本控制来更新存储在 SharePoint 或 OneDrive 中的记录](record-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="dea56-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="dea56-127">若要了解记录的处置，请参阅[处置内容](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="dea56-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
