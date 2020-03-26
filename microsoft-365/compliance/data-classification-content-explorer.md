---
title: 内容资源管理器（预览版）入门
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 91246a701e1c5a030f4c9c53e25e56c137e7569b
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929404"
---
# <a name="get-started-with-content-explorer-preview"></a><span data-ttu-id="a1029-103">内容资源管理器（预览版）入门</span><span class="sxs-lookup"><span data-stu-id="a1029-103">Get started with content explorer (preview)</span></span>

<span data-ttu-id="a1029-104">数据分类内容资源管理器可以在本机查看“概述”页上汇总的项目。</span><span class="sxs-lookup"><span data-stu-id="a1029-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1029-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="a1029-105">Prerequisites</span></span>

<span data-ttu-id="a1029-106">访问和使用活动资源管理器的每个帐户，都必须拥有从以下之一订阅向其分配的许可证：</span><span class="sxs-lookup"><span data-stu-id="a1029-106">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="a1029-107">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a1029-107">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="a1029-108">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="a1029-108">Office 365 (E5)</span></span>
- <span data-ttu-id="a1029-109">高级合规性（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="a1029-109">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="a1029-110">高级威胁智能（E5）加载项</span><span class="sxs-lookup"><span data-stu-id="a1029-110">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="content-explorer"></a><span data-ttu-id="a1029-111">内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="a1029-111">Content explorer</span></span>

<span data-ttu-id="a1029-112">内容资源管理器可显示具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目的当前快照。</span><span class="sxs-lookup"><span data-stu-id="a1029-112">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="a1029-113">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a1029-113">Sensitive information types</span></span>

<span data-ttu-id="a1029-114">[DLP 策略](data-loss-prevention-policies.md)可帮助保护定义为**敏感信息类型**的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="a1029-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="a1029-115">Microsoft 365 在多个不同区域包含[适用于众多常用敏感信息类型的定义](what-the-sensitive-information-types-look-for.md)它们已准备就绪可供使用。</span><span class="sxs-lookup"><span data-stu-id="a1029-115">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="a1029-116">例如，信用卡号、银行帐号、国民身份证号码和 Windows Live ID 服务编号。</span><span class="sxs-lookup"><span data-stu-id="a1029-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="a1029-117">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="a1029-117">Sensitivity labels</span></span>

<span data-ttu-id="a1029-118">[灵敏度标签](sensitivity-labels.md)只是一个标记，指出项目对你的组织的价值。</span><span class="sxs-lookup"><span data-stu-id="a1029-118">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="a1029-119">该标签可手动应用，也可自动应用。</span><span class="sxs-lookup"><span data-stu-id="a1029-119">It can be applied manually, or automatically.</span></span> <span data-ttu-id="a1029-120">应用后，它将嵌入到文档中并始终保留在文档上。</span><span class="sxs-lookup"><span data-stu-id="a1029-120">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="a1029-121">可通过敏感度标签实现各种保护行为，例如强制水印或加密。</span><span class="sxs-lookup"><span data-stu-id="a1029-121">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="a1029-122">如果启用了终结点保护，你甚至还可阻止项目脱离组织控制。</span><span class="sxs-lookup"><span data-stu-id="a1029-122">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="a1029-123">必须为 SharePoint 和 OneDrive 中的文件启用灵敏度标签，以使相应的数据出现在数据分类页面中。</span><span class="sxs-lookup"><span data-stu-id="a1029-123">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="a1029-124">有关详细信息，请参阅[启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签（公共预览版）](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="a1029-124">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="a1029-125">保留标签</span><span class="sxs-lookup"><span data-stu-id="a1029-125">Retention labels</span></span>

<span data-ttu-id="a1029-126">[保留标签](labels.md)可用于定义带标记的项目将保留多长时间以及删除项目前要采取哪些操作。</span><span class="sxs-lookup"><span data-stu-id="a1029-126">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="a1029-127">这些标签可手动应用，也可通过策略自动应用。</span><span class="sxs-lookup"><span data-stu-id="a1029-127">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="a1029-128">它们在帮助组织持续遵守法律法规要求方面发挥着作用。</span><span class="sxs-lookup"><span data-stu-id="a1029-128">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![内容资源管理器折叠的屏幕截图](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="a1029-130">权限</span><span class="sxs-lookup"><span data-stu-id="a1029-130">Permissions</span></span>

<span data-ttu-id="a1029-131">有两个角色可授予对内容资源管理器的访问权限：</span><span class="sxs-lookup"><span data-stu-id="a1029-131">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="a1029-132">**内容资源管理器列表查看器**：此角色组的成员资格允许你查看每个项目及其位置。</span><span class="sxs-lookup"><span data-stu-id="a1029-132">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="a1029-133">已为此角色组预分配 `data classification list viewer` 角色。</span><span class="sxs-lookup"><span data-stu-id="a1029-133">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="a1029-134">**内容资源管理器内容查看器**：此角色组的成员资格允许你查看列表中每个项目的内容。</span><span class="sxs-lookup"><span data-stu-id="a1029-134">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="a1029-135">已为此角色组预分配 `data classification content viewer` 角色。</span><span class="sxs-lookup"><span data-stu-id="a1029-135">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="a1029-136">用于访问内容资源管理器的帐户必须具有其中一个或两个角色组。</span><span class="sxs-lookup"><span data-stu-id="a1029-136">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="a1029-137">这些角色组是独立角色组，不具有累积性。</span><span class="sxs-lookup"><span data-stu-id="a1029-137">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="a1029-138">例如，如果要向帐户授予仅查看项目及其位置的权限，则授予内容资源管理器列表查看器的权限。</span><span class="sxs-lookup"><span data-stu-id="a1029-138">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="a1029-139">如果你希望同一帐户也能够查看列表中项目的内容，另请授予内容资源管理器内容查看器权限。</span><span class="sxs-lookup"><span data-stu-id="a1029-139">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="a1029-140">你还可以将任一个角色或全部两个角色都分配到自定义角色组，以便对内容资源管理器的访问权限进行量身定制。</span><span class="sxs-lookup"><span data-stu-id="a1029-140">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="a1029-141">全局管理员、合规性管理员或数据管理员可以分配必要的  内容资源管理器列表查看器  和  内容资源管理器内容查看器  角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="a1029-141">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="a1029-142">如何使用内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="a1029-142">How to use content explorer</span></span>

1. <span data-ttu-id="a1029-143">打开“**Microsoft 365 合规中心**”  > “**数据分类**” > “**内容资源管理器**”。</span><span class="sxs-lookup"><span data-stu-id="a1029-143">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="a1029-144">如果知道标签的名称或敏感信息类型，可将其键入“搜索” 框。</span><span class="sxs-lookup"><span data-stu-id="a1029-144">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="a1029-145">或者，你可以通过展开标签类型并从列表中选择标签来浏览该项目，下面显示了列表的保留标签部分中的项目。</span><span class="sxs-lookup"><span data-stu-id="a1029-145">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="a1029-146">选择“**所有**”位置下的某个位置，然后向下钻取文件夹结构到该项目。</span><span class="sxs-lookup"><span data-stu-id="a1029-146">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="a1029-147">双击以在本机上打开内容资源管理器中的项目。</span><span class="sxs-lookup"><span data-stu-id="a1029-147">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1029-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1029-148">See also</span></span>

- [<span data-ttu-id="a1029-149">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="a1029-149">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a1029-150">保留标签</span><span class="sxs-lookup"><span data-stu-id="a1029-150">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="a1029-151">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="a1029-151">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="a1029-152">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="a1029-152">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="a1029-153">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="a1029-153">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
