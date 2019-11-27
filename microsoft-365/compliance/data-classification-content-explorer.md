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
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268442"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="c2d48-103">使用数据分类内容资源管理器（预览版）</span><span class="sxs-lookup"><span data-stu-id="c2d48-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="c2d48-104">数据分类内容资源管理器可以在本机查看“概述”页上汇总的项目。</span><span class="sxs-lookup"><span data-stu-id="c2d48-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="c2d48-105">内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="c2d48-105">Content explorer</span></span>

<span data-ttu-id="c2d48-106">内容资源管理器是具有敏感度标签、保留标签或在你的组织中被归类为敏感信息类型的项目的当前快照。</span><span class="sxs-lookup"><span data-stu-id="c2d48-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![内容资源管理器折叠的屏幕截图](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="c2d48-108">权限</span><span class="sxs-lookup"><span data-stu-id="c2d48-108">Permissions</span></span>

<span data-ttu-id="c2d48-109">有两个角色可授予对内容资源管理器的访问权限：</span><span class="sxs-lookup"><span data-stu-id="c2d48-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="c2d48-110">**内容资源管理器列表查看器**：此角色的成员资格允许你查看每个项目及其位置。</span><span class="sxs-lookup"><span data-stu-id="c2d48-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="c2d48-111">**内容资源管理器内容查看器**：此角色的成员资格允许你查看列表中每个项目的内容。</span><span class="sxs-lookup"><span data-stu-id="c2d48-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="c2d48-112">用于访问内容资源管理器的帐户必须具有其中一个或两个角色。</span><span class="sxs-lookup"><span data-stu-id="c2d48-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="c2d48-113">这些角色是独立角色，不具有累积性。</span><span class="sxs-lookup"><span data-stu-id="c2d48-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="c2d48-114">例如，如果要向帐户授予仅查看项目及其位置的权限，则授予内容资源管理器列表查看器的权限。</span><span class="sxs-lookup"><span data-stu-id="c2d48-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="c2d48-115">如果你希望同一帐户也能够查看列表中项目的内容，另请授予内容资源管理器内容查看器权限。</span><span class="sxs-lookup"><span data-stu-id="c2d48-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="c2d48-116">如何使用内容资源管理器</span><span class="sxs-lookup"><span data-stu-id="c2d48-116">How to use content explorer</span></span>

1. <span data-ttu-id="c2d48-117">打开“**Microsoft 365 合规中心**”  > “**数据分类**” > “**内容资源管理器**”。</span><span class="sxs-lookup"><span data-stu-id="c2d48-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="c2d48-118">如果知道标签的名称或敏感信息类型，可将其键入“搜索” 框。</span><span class="sxs-lookup"><span data-stu-id="c2d48-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="c2d48-119">或者，你可以通过展开标签类型并从列表中选择标签来浏览该项目，下面显示了列表的保留标签部分中的项目。</span><span class="sxs-lookup"><span data-stu-id="c2d48-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="c2d48-120">选择“**所有**”位置下的某个位置，然后向下钻取文件夹结构到该项目。</span><span class="sxs-lookup"><span data-stu-id="c2d48-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="c2d48-121">双击以在本机上打开内容资源管理器中的项目。</span><span class="sxs-lookup"><span data-stu-id="c2d48-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2d48-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2d48-122">See also</span></span>

- [<span data-ttu-id="c2d48-123">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="c2d48-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="c2d48-124">保留标签</span><span class="sxs-lookup"><span data-stu-id="c2d48-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="c2d48-125">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="c2d48-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="c2d48-126">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="c2d48-126">Overview of retention policies</span></span>](retention-policies.md)
