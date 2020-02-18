---
title: 数据分类预览版的发行说明（预览版）
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
description: 数据分类公共预览版的发行说明。
ms.openlocfilehash: 1beae92089833327cedf6090690530d9e5457a37
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076359"
---
# <a name="data-classification-public-preview-release-notes-preview"></a><span data-ttu-id="8c8bc-103">数据分类公共预览版的发行说明（预览版）</span><span class="sxs-lookup"><span data-stu-id="8c8bc-103">Data classification public preview release notes (preview)</span></span>

<span data-ttu-id="8c8bc-104">此公共预览版引入了新功能：在你创建任何策略*前*，开始扫描你的敏感内容和标记的内容。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-104">This public preview introduces new functionality where scanning of your sensitive content and labeled content starts *before* you create any policies.</span></span> <span data-ttu-id="8c8bc-105">这称为 \*\* 零变更管理 \*\*。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-105">This is called **zero change management**.</span></span> <span data-ttu-id="8c8bc-106">这样，你就可以看到你环境中所有保留和灵敏度标签的影响，并使你能够开始评估你的保护和治理策略需求。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-106">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

<span data-ttu-id="8c8bc-107">请查看这些发行说明，以便在此公共预览版中获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-107">Please review these release notes so that you have the best experience with this public preview.</span></span> <span data-ttu-id="8c8bc-108">从现在到正式发布 (GA) 期间，我们将致力于解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-108">We will be working on addressing these points between now and general availability (GA).</span></span>

## <a name="permissions-for-accessing-content-explorer"></a><span data-ttu-id="8c8bc-109">访问内容资源管理器的权限</span><span class="sxs-lookup"><span data-stu-id="8c8bc-109">Permissions for accessing content explorer</span></span>

<span data-ttu-id="8c8bc-110">对内容资源管理器的访问权限受到高度限制，因为它允许你读取已扫描文件的内容。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-110">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span> <span data-ttu-id="8c8bc-111">对内容资源管理器的访问需要 **内容资源管理器列表查看器**以及**内容资源管理器内容查看器**角色组中的成员身份。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-111">Access to content explorer requires membership in the **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups.</span></span> <span data-ttu-id="8c8bc-112">默认情况下，没有帐户可访问内容资源管理器。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-112">No account has access to content explorer by default.</span></span> <span data-ttu-id="8c8bc-113">请参阅[使用数据分类内容资源管理器（预览版）](data-classification-content-explorer.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-113">See, [Using data classification content explorer (preview)](data-classification-content-explorer.md#permissions).</span></span> <span data-ttu-id="8c8bc-114">全局管理员、合规性管理员或数据管理员可以分配必要的 \*\* 内容资源管理器列表查看器 \*\* 和 \*\* 内容资源管理器内容查看器 \*\* 角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-114">A Global admin, Compliance admin, or Data admin can assign the necessary **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role group membership.</span></span>

> [!TIP]
> <span data-ttu-id="8c8bc-115">在全球范围内部署基于角色的访问控制 (RBAC) 时，\*\* 内容资源管理器列表查看器 \*\* 和 \*\* 内容资源管理器内容查看器 \*\* 角色组可能不会显示在 "权限" 页面上。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-115">The **Content Explorer List Viewer**, and the **Content Explorer Content Viewer** role groups may not appear on the permissions page while the Role Based Access Controls (RBAC) are being deployed worldwide.</span></span> <span data-ttu-id="8c8bc-116">如果它们未出现在 "权限" 页面上，则必须创建一个自定义角色组，并将 `data classification list viewer` 角色和或 `data classification content viewer` 角色（复数）分配到你的自定义角色组。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-116">If they aren't appearing on the permissions page, you must create a custom role group and assign the `data classification list viewer` role and or the `data classification content viewer` roles to your custom role group.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="8c8bc-117">Exchange 邮箱计数</span><span class="sxs-lookup"><span data-stu-id="8c8bc-117">Exchange mailbox count</span></span>

<span data-ttu-id="8c8bc-118">当你深入了解 Exchange 邮箱时，你会注意到出现一个小的工具提示。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-118">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="8c8bc-119">这是为了表明以下事实：敏感信息类型，敏感度标签和保留标签显示的合计计数可能与邮箱中找到的项目数不完全匹配。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-119">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="8c8bc-120">这是因为深入了解文件夹时，将提取内容的实时视图（已分类），同时会计算总计数。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-120">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>

## <a name="seeing-guids-instead-of-label-names"></a><span data-ttu-id="8c8bc-121">查看 GUID 而不是标签名称</span><span class="sxs-lookup"><span data-stu-id="8c8bc-121">Seeing GUIDs instead of label names</span></span>

<span data-ttu-id="8c8bc-122">私人预览版客户遇到过的一些情况是，已迁移的标签或者在删除内容中带有内容标记的标签时，会导致标签名称在内容资源管理器和活动资源管理器中解析为 32 位 GUID，而不是标签名称。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-122">Private preview customers have seen instances where the migrated labels or deletion of a label that content has already been stamped with results in label names resolving to a 32-bit GUID in content explorer and activity explorer instead of the label name.</span></span> 

## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="8c8bc-123">加密文档的呈现</span><span class="sxs-lookup"><span data-stu-id="8c8bc-123">Rendering of encrypted documents</span></span>

<span data-ttu-id="8c8bc-124">已加密的 SharePoint、Exchange 和 OneDrive 文件将不会在内容资源管理器中呈现。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-124">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="8c8bc-125">这是一项敏感问题，需要在内容资源管理器中查看文件内容和将内容保持加密的需求之间取得平衡。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-125">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="8c8bc-126">通过 \*\* 内容资源管理器列表查看器 \*\* 和 \*\* 内容资源管理器内容查看器 \*\* 角色组授予的权限，你将看到文件的列表视图、文件元数据和可用于通过 web 客户端访问内容的链接。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-126">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="8c8bc-127">SharePoint 搜索中保留标签名称的支持字符</span><span class="sxs-lookup"><span data-stu-id="8c8bc-127">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="8c8bc-128">SharePoint 搜索不支持包含 `-` 或者 `_` 的保留标签名称。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-128">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="8c8bc-129">例如 `Label-MIP` 和 `Label_MIP` 不受支持。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-129">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="8c8bc-130">SharePoint 搜索支持敏感性标签名称和敏感信息类型名称中的这些字符。</span><span class="sxs-lookup"><span data-stu-id="8c8bc-130">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c8bc-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c8bc-131">See also</span></span>

- [<span data-ttu-id="8c8bc-132">数据分类入门（预览）</span><span class="sxs-lookup"><span data-stu-id="8c8bc-132">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="8c8bc-133">查看标签活动（预览）</span><span class="sxs-lookup"><span data-stu-id="8c8bc-133">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="8c8bc-134">查看已应用标签的内容（预览）</span><span class="sxs-lookup"><span data-stu-id="8c8bc-134">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="8c8bc-135">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="8c8bc-135">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="8c8bc-136">保留标签</span><span class="sxs-lookup"><span data-stu-id="8c8bc-136">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="8c8bc-137">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="8c8bc-137">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

