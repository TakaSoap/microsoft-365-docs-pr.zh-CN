---
title: 数据分类发行说明
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 数据分类发行说明。
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086703"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="76cd6-103">数据分类发行说明</span><span class="sxs-lookup"><span data-stu-id="76cd6-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="76cd6-104">Exchange 邮箱计数</span><span class="sxs-lookup"><span data-stu-id="76cd6-104">Exchange mailbox count</span></span>

<span data-ttu-id="76cd6-105">当你深入了解 Exchange 邮箱时，你会注意到出现一个小的工具提示。</span><span class="sxs-lookup"><span data-stu-id="76cd6-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="76cd6-106">这是为了表明以下事实：敏感信息类型，敏感度标签和保留标签显示的合计计数可能与邮箱中找到的项目数不完全匹配。</span><span class="sxs-lookup"><span data-stu-id="76cd6-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="76cd6-107">这是因为深入了解文件夹时，将提取内容的实时视图（已分类），同时会计算总计数。</span><span class="sxs-lookup"><span data-stu-id="76cd6-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="76cd6-108">加密文档的呈现</span><span class="sxs-lookup"><span data-stu-id="76cd6-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="76cd6-109">已加密的 SharePoint、Exchange 和 OneDrive 文件不会在内容资源管理器中呈现。</span><span class="sxs-lookup"><span data-stu-id="76cd6-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="76cd6-110">这是一项敏感问题，需要在内容资源管理器中查看文件内容和将内容保持加密的需求之间取得平衡。</span><span class="sxs-lookup"><span data-stu-id="76cd6-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="76cd6-111">通过 **内容资源管理器列表查看器** 和 **内容资源管理器内容查看器** 角色组授予的权限，你将看到文件的列表视图、文件元数据和可用于通过 web 客户端访问内容的链接。</span><span class="sxs-lookup"><span data-stu-id="76cd6-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="76cd6-112">SharePoint 搜索中保留标签名称的支持字符</span><span class="sxs-lookup"><span data-stu-id="76cd6-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="76cd6-113">SharePoint 搜索不支持包含 `-` 或者 `_` 的保留标签名称。</span><span class="sxs-lookup"><span data-stu-id="76cd6-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="76cd6-114">例如，`Label-MIP` 和 `Label_MIP` 不受支持。</span><span class="sxs-lookup"><span data-stu-id="76cd6-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="76cd6-115">SharePoint 搜索支持敏感性标签名称和敏感信息类型名称中的这些字符。</span><span class="sxs-lookup"><span data-stu-id="76cd6-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="76cd6-116">OneDrive 仍处于预览状态</span><span class="sxs-lookup"><span data-stu-id="76cd6-116">OneDrive remains in preview</span></span>

<span data-ttu-id="76cd6-117">感谢你在我们的预览计划期间提供有关 OneDrive 集成的宝贵反馈。</span><span class="sxs-lookup"><span data-stu-id="76cd6-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="76cd6-118">随着我们处理具体的细节，你可能会遇到不一致的数据/流。</span><span class="sxs-lookup"><span data-stu-id="76cd6-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="76cd6-119">我们将继续展示 OneDrive 预览版，直到所有修补程序均准备就绪。</span><span class="sxs-lookup"><span data-stu-id="76cd6-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="76cd6-120">非常感谢你的持续支持。</span><span class="sxs-lookup"><span data-stu-id="76cd6-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="76cd6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76cd6-121">See also</span></span>

- [<span data-ttu-id="76cd6-122">数据分类入门（预览）</span><span class="sxs-lookup"><span data-stu-id="76cd6-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="76cd6-123">查看标签活动（预览）</span><span class="sxs-lookup"><span data-stu-id="76cd6-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="76cd6-124">查看已应用标签的内容（预览）</span><span class="sxs-lookup"><span data-stu-id="76cd6-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="76cd6-125">了解敏感度标签</span><span class="sxs-lookup"><span data-stu-id="76cd6-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="76cd6-126">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="76cd6-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="76cd6-127">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="76cd6-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)