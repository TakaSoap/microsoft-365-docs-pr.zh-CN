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
description: ''
ms.openlocfilehash: 67b4eb399b422cac032bbfcfe49079e4d55b2d02
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077109"
---
# <a name="create-a-search"></a><span data-ttu-id="31250-102">创建搜索</span><span class="sxs-lookup"><span data-stu-id="31250-102">Create a search</span></span>

<span data-ttu-id="31250-103">在您的案例的 "**搜索**" 选项卡上，您可以通过单击 "**新建搜索**" 并按照向导创建新的搜索。</span><span class="sxs-lookup"><span data-stu-id="31250-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-it-a-description"></a><span data-ttu-id="31250-104">命名搜索并为其提供说明</span><span class="sxs-lookup"><span data-stu-id="31250-104">Name your search and give it a description</span></span>

<span data-ttu-id="31250-105">每个具有事例的搜索应具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="31250-105">Each search with a case should have a unique name.</span></span> <span data-ttu-id="31250-106">您可以选择为搜索提供说明。</span><span class="sxs-lookup"><span data-stu-id="31250-106">You can optionally provide a description for your search.</span></span> 

## <a name="define-your-search-query-and-conditions"></a><span data-ttu-id="31250-107">定义您的搜索查询和条件</span><span class="sxs-lookup"><span data-stu-id="31250-107">Define your search query and conditions</span></span>

<span data-ttu-id="31250-108">您可以使用预建的条件卡或使用关键字查询语言（KQL）定义搜索的关键字查询和任何条件。</span><span class="sxs-lookup"><span data-stu-id="31250-108">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="31250-109">有关详细信息，请参阅[构建搜索查询](building-search-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="31250-109">For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="31250-110">选择要从中搜索的保管人</span><span class="sxs-lookup"><span data-stu-id="31250-110">Choose the custodians to search from</span></span>

<span data-ttu-id="31250-111">定义条件后，需要选择要搜索的位置。</span><span class="sxs-lookup"><span data-stu-id="31250-111">Once you have defined your conditions, you need to choose which locations you want to search.</span></span> <span data-ttu-id="31250-112">执行此操作的一种方法是指定您已添加到您要搜索的事例的保管人。</span><span class="sxs-lookup"><span data-stu-id="31250-112">One way to do it is by specifying which custodians you have already added to the case you want to search.</span></span> <span data-ttu-id="31250-113">通过选择管理员，你将对映射到保管人的所有数据源运行搜索。</span><span class="sxs-lookup"><span data-stu-id="31250-113">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="31250-114">有关如何将保管人添加到你的事例并管理其数据源的详细信息，请参阅[使用保管人](managing-custodians.md)。</span><span class="sxs-lookup"><span data-stu-id="31250-114">See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="31250-115">选择非 custodial 位置</span><span class="sxs-lookup"><span data-stu-id="31250-115">Choose non-custodial locations</span></span>

<span data-ttu-id="31250-116">在某些情况下，您可能希望搜索未映射到保管人的数据源。</span><span class="sxs-lookup"><span data-stu-id="31250-116">In some cases, you may wish to search data sources that are not mapped to a custodian.</span></span> <span data-ttu-id="31250-117">在这种情况下，您可以指定要搜索的位置，或选择搜索特定 Office 365 服务的所有内容位置（例如，搜索所有 Exchange 邮箱或所有 SharePoint 和 OneDrive for business 网站）。</span><span class="sxs-lookup"><span data-stu-id="31250-117">In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>
