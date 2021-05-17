---
title: 创建搜索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何创建、定义和选择保管人位置和托管位置，以在Advanced eDiscovery位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035764"
---
# <a name="create-a-search"></a><span data-ttu-id="0db27-103">创建搜索</span><span class="sxs-lookup"><span data-stu-id="0db27-103">Create a search</span></span>

<span data-ttu-id="0db27-104">在 **案例的"** 搜索"选项卡上，可以通过单击"新建搜索"并遵循向导创建新搜索。</span><span class="sxs-lookup"><span data-stu-id="0db27-104">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![搜索案例中的Advanced eDiscovery向导](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="0db27-106">命名搜索并给出说明</span><span class="sxs-lookup"><span data-stu-id="0db27-106">Name the search and give it a description</span></span>

<span data-ttu-id="0db27-107">每个具有案例的搜索都应具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="0db27-107">Each search with a case should have a unique name.</span></span> <span data-ttu-id="0db27-108">可以选择提供搜索说明。</span><span class="sxs-lookup"><span data-stu-id="0db27-108">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="0db27-109">选择要搜索的保管人和位置</span><span class="sxs-lookup"><span data-stu-id="0db27-109">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="0db27-110">通过指定已添加到案例的保管人，选择要搜索的保管人内容位置。</span><span class="sxs-lookup"><span data-stu-id="0db27-110">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="0db27-111">通过选择保管人，您将针对映射到保管人的所有数据源运行搜索。</span><span class="sxs-lookup"><span data-stu-id="0db27-111">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="0db27-112">还可以选择将搜索范围缩小到每个保管人所选的数据源。</span><span class="sxs-lookup"><span data-stu-id="0db27-112">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="0db27-113">若要详细了解如何添加保管人并管理其数据源，请参阅 [使用保管人](managing-custodians.md)。</span><span class="sxs-lookup"><span data-stu-id="0db27-113">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="0db27-114">选择非地理位置</span><span class="sxs-lookup"><span data-stu-id="0db27-114">Choose non-custodial locations</span></span>

<span data-ttu-id="0db27-115">在某些情况下，您可能需要搜索不与保管人关联的数据源。</span><span class="sxs-lookup"><span data-stu-id="0db27-115">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="0db27-116">在这种情况下，您可以指定要搜索的位置，或选择搜索特定 Microsoft 服务 (（如搜索所有 Exchange 邮箱或所有 SharePoint 网站和 OneDrive 帐户）) 。</span><span class="sxs-lookup"><span data-stu-id="0db27-116">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="0db27-117">定义搜索查询和条件</span><span class="sxs-lookup"><span data-stu-id="0db27-117">Define the search query and conditions</span></span>

<span data-ttu-id="0db27-118">您可以使用预构建的条件卡或 KQL 中的关键字查询语言定义搜索的关键字查询 (条件) 。</span><span class="sxs-lookup"><span data-stu-id="0db27-118">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="0db27-119">有关详细信息，请参阅生成 [搜索查询](building-search-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="0db27-119">For more information, see [Build search queries](building-search-queries.md).</span></span>
