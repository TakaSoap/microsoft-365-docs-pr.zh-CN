---
title: 数据分类发行说明
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
description: 数据分类发行说明。
ms.openlocfilehash: bbef6729680db2c9a6aec4caa9036ec23fad6949
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327597"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="dcf33-103">数据分类发行说明</span><span class="sxs-lookup"><span data-stu-id="dcf33-103">Data classification release notes</span></span>

<span data-ttu-id="dcf33-104">请查看这些发行说明，以便获得最佳的数据分类体验。</span><span class="sxs-lookup"><span data-stu-id="dcf33-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="dcf33-105">Exchange 邮箱计数</span><span class="sxs-lookup"><span data-stu-id="dcf33-105">Exchange mailbox count</span></span>

<span data-ttu-id="dcf33-106">当你深入了解 Exchange 邮箱时，你会注意到出现一个小的工具提示。</span><span class="sxs-lookup"><span data-stu-id="dcf33-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="dcf33-107">这是为了表明以下事实：敏感信息类型，敏感度标签和保留标签显示的合计计数可能与邮箱中找到的项目数不完全匹配。</span><span class="sxs-lookup"><span data-stu-id="dcf33-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="dcf33-108">这是因为深入了解文件夹时，将提取内容的实时视图（已分类），同时会计算总计数。</span><span class="sxs-lookup"><span data-stu-id="dcf33-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="dcf33-109">加密文档的呈现</span><span class="sxs-lookup"><span data-stu-id="dcf33-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="dcf33-110">已加密的 SharePoint、Exchange 和 OneDrive 文件将不会在内容资源管理器中呈现。</span><span class="sxs-lookup"><span data-stu-id="dcf33-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="dcf33-111">这是一项敏感问题，需要在内容资源管理器中查看文件内容和将内容保持加密的需求之间取得平衡。</span><span class="sxs-lookup"><span data-stu-id="dcf33-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="dcf33-112">通过 \*\* 内容资源管理器列表查看器 \*\* 和 \*\* 内容资源管理器内容查看器 \*\* 角色组授予的权限，你将看到文件的列表视图、文件元数据和可用于通过 web 客户端访问内容的链接。</span><span class="sxs-lookup"><span data-stu-id="dcf33-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="dcf33-113">SharePoint 搜索中保留标签名称的支持字符</span><span class="sxs-lookup"><span data-stu-id="dcf33-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="dcf33-114">SharePoint 搜索不支持包含 `-` 或者 `_` 的保留标签名称。</span><span class="sxs-lookup"><span data-stu-id="dcf33-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="dcf33-115">例如 `Label-MIP` 和 `Label_MIP` 不受支持。</span><span class="sxs-lookup"><span data-stu-id="dcf33-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="dcf33-116">SharePoint 搜索支持敏感性标签名称和敏感信息类型名称中的这些字符。</span><span class="sxs-lookup"><span data-stu-id="dcf33-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="dcf33-117">OneDrive 仍处于预览状态</span><span class="sxs-lookup"><span data-stu-id="dcf33-117">OneDrive remains in preview</span></span>

<span data-ttu-id="dcf33-118">我们在预览计划中听取了有关 OneDrive 集成的宝贵反馈。</span><span class="sxs-lookup"><span data-stu-id="dcf33-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="dcf33-119">随着我们处理具体的细节，你可能会遇到不一致的数据/流。</span><span class="sxs-lookup"><span data-stu-id="dcf33-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="dcf33-120">我们将继续展示 OneDrive 预览版，直到所有修补程序均准备就绪。</span><span class="sxs-lookup"><span data-stu-id="dcf33-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="dcf33-121">非常感谢你在这方面的持续支持。</span><span class="sxs-lookup"><span data-stu-id="dcf33-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="dcf33-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcf33-122">See also</span></span>

- [<span data-ttu-id="dcf33-123">数据分类入门（预览）</span><span class="sxs-lookup"><span data-stu-id="dcf33-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="dcf33-124">查看标签活动（预览）</span><span class="sxs-lookup"><span data-stu-id="dcf33-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="dcf33-125">查看已应用标签的内容（预览）</span><span class="sxs-lookup"><span data-stu-id="dcf33-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="dcf33-126">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="dcf33-126">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="dcf33-127">保留标签</span><span class="sxs-lookup"><span data-stu-id="dcf33-127">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="dcf33-128">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="dcf33-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)