---
title: 使用数据分类内容资源管理器（预览版）
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 内容资源管理器可用于在本机查看标记的项目。
ms.openlocfilehash: 8a795e0582599dc3160f896a6361b773caa6c4e4
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823794"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="9887c-103">使用数据分类内容资源管理器（预览版）</span><span class="sxs-lookup"><span data-stu-id="9887c-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="9887c-104">数据分类内容资源管理器可以在本机查看“概述”页上汇总的项目。</span><span class="sxs-lookup"><span data-stu-id="9887c-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="9887c-105">内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="9887c-105">Content explorer</span></span>

<span data-ttu-id="9887c-106">内容资源管理器可显示具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目的当前快照。</span><span class="sxs-lookup"><span data-stu-id="9887c-106">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="9887c-107">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="9887c-107">Sensitive information types</span></span>

<span data-ttu-id="9887c-108">[DLP 策略](data-loss-prevention-policies.md)可帮助保护定义为**敏感信息类型**的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="9887c-108">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="9887c-109">Microsoft 365 在多个不同区域包含[适用于众多常用敏感信息类型的定义](what-the-sensitive-information-types-look-for.md)它们已准备就绪可供使用。</span><span class="sxs-lookup"><span data-stu-id="9887c-109">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="9887c-110">例如，信用卡号、银行帐号、国民身份证号码和 Windows Live ID 服务编号。</span><span class="sxs-lookup"><span data-stu-id="9887c-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="9887c-111">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="9887c-111">Sensitivity labels</span></span>

<span data-ttu-id="9887c-112">[灵敏度标签](sensitivity-labels.md)只是一个标记，指出项目对你的组织的价值。</span><span class="sxs-lookup"><span data-stu-id="9887c-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="9887c-113">该标签可手动应用，也可自动应用。</span><span class="sxs-lookup"><span data-stu-id="9887c-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="9887c-114">应用后，它将嵌入到文档中并始终保留在文档上。</span><span class="sxs-lookup"><span data-stu-id="9887c-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="9887c-115">可通过敏感度标签实现各种保护行为，例如强制水印或加密。</span><span class="sxs-lookup"><span data-stu-id="9887c-115">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="9887c-116">如果启用了终结点保护，你甚至还可阻止项目脱离组织控制。</span><span class="sxs-lookup"><span data-stu-id="9887c-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="9887c-117">必须为 SharePoint 和 OneDrive 中的文件启用灵敏度标签，以使相应的数据出现在数据分类页面中。</span><span class="sxs-lookup"><span data-stu-id="9887c-117">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="9887c-118">有关详细信息，请参阅[启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签（公共预览版）](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="9887c-118">[Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md)</span></span>

### <a name="retention-labels"></a><span data-ttu-id="9887c-119">保留标签</span><span class="sxs-lookup"><span data-stu-id="9887c-119">Retention labels</span></span>

<span data-ttu-id="9887c-120">[保留标签](labels.md)可用于定义带标记的项目将保留多长时间以及删除项目前要采取哪些操作。</span><span class="sxs-lookup"><span data-stu-id="9887c-120">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="9887c-121">这些标签可手动应用，也可通过策略自动应用。</span><span class="sxs-lookup"><span data-stu-id="9887c-121">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="9887c-122">它们在帮助组织持续遵守法律法规要求方面发挥着作用。</span><span class="sxs-lookup"><span data-stu-id="9887c-122">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![内容资源管理器折叠的屏幕截图](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="9887c-124">权限</span><span class="sxs-lookup"><span data-stu-id="9887c-124">Permissions</span></span>

<span data-ttu-id="9887c-125">有两个角色可授予对内容资源管理器的访问权限：</span><span class="sxs-lookup"><span data-stu-id="9887c-125">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="9887c-126">**内容资源管理器列表查看器**：此角色的成员资格允许你查看每个项目及其位置。</span><span class="sxs-lookup"><span data-stu-id="9887c-126">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="9887c-127">**内容资源管理器内容查看器**：此角色的成员资格允许你查看列表中每个项目的内容。</span><span class="sxs-lookup"><span data-stu-id="9887c-127">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="9887c-128">用于访问内容资源管理器的帐户必须具有其中一个或两个角色。</span><span class="sxs-lookup"><span data-stu-id="9887c-128">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="9887c-129">这些角色是独立角色，不具有累积性。</span><span class="sxs-lookup"><span data-stu-id="9887c-129">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="9887c-130">例如，如果要向帐户授予仅查看项目及其位置的权限，则授予内容资源管理器列表查看器的权限。</span><span class="sxs-lookup"><span data-stu-id="9887c-130">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="9887c-131">如果你希望同一帐户也能够查看列表中项目的内容，另请授予内容资源管理器内容查看器权限。</span><span class="sxs-lookup"><span data-stu-id="9887c-131">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="9887c-132">如何使用内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="9887c-132">How to use content explorer</span></span>

1. <span data-ttu-id="9887c-133">打开“**Microsoft 365 合规中心**”  > “**数据分类**” > “**内容资源管理器**”。</span><span class="sxs-lookup"><span data-stu-id="9887c-133">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="9887c-134">如果知道标签的名称或敏感信息类型，可将其键入“搜索” 框。</span><span class="sxs-lookup"><span data-stu-id="9887c-134">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="9887c-135">或者，你可以通过展开标签类型并从列表中选择标签来浏览该项目，下面显示了列表的保留标签部分中的项目。</span><span class="sxs-lookup"><span data-stu-id="9887c-135">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="9887c-136">选择“**所有**”位置下的某个位置，然后向下钻取文件夹结构到该项目。</span><span class="sxs-lookup"><span data-stu-id="9887c-136">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="9887c-137">双击以在本机上打开内容资源管理器中的项目。</span><span class="sxs-lookup"><span data-stu-id="9887c-137">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="9887c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9887c-138">See also</span></span>

- [<span data-ttu-id="9887c-139">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="9887c-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="9887c-140">保留标签</span><span class="sxs-lookup"><span data-stu-id="9887c-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="9887c-141">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="9887c-141">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="9887c-142">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="9887c-142">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="9887c-143">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="9887c-143">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
