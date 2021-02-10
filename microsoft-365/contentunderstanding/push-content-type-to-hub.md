---
title: 将内容类型推送到中心
description: 了解如何将内容类型推送到中心
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 22d146b1d376bab134e82ad7d1313cb7881ca45b
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144967"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="290c9-103">将内容类型推送到中心</span><span class="sxs-lookup"><span data-stu-id="290c9-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="290c9-104">若要使重要内容类型与 SharePoint 库和列表更为一致，可将其推送到选择的中心。</span><span class="sxs-lookup"><span data-stu-id="290c9-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="290c9-105">推送内容类型操作会自动将内容类型添加到在与中心相关联的网站上创建的所有新列表和库中，以及中心的任何新增网站中。</span><span class="sxs-lookup"><span data-stu-id="290c9-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span> <span data-ttu-id="290c9-106">此功能需要 [SharePoint Syntex](index.md) 许可证。</span><span class="sxs-lookup"><span data-stu-id="290c9-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="290c9-107">若要使用此功能，必须已发布正在推送的内容类型。</span><span class="sxs-lookup"><span data-stu-id="290c9-107">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="290c9-108">将内容类型推送到中心</span><span class="sxs-lookup"><span data-stu-id="290c9-108">To push content types to hubs</span></span>

1. <span data-ttu-id="290c9-109">在 SharePoint 管理中心中，展开“**内容服务**”，然后选择“**内容类型库**”。</span><span class="sxs-lookup"><span data-stu-id="290c9-109">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="290c9-110">选择要推送到中心的内容类型。</span><span class="sxs-lookup"><span data-stu-id="290c9-110">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="290c9-111">单击命令栏中的“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="290c9-111">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="290c9-112">单击“**选择中心网站**”。</span><span class="sxs-lookup"><span data-stu-id="290c9-112">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="290c9-113">选择所需的中心网站，然后选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="290c9-113">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="290c9-114">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="290c9-114">Choose **Save**.</span></span>

<span data-ttu-id="290c9-115">首次将内容类型推送到现有中心及其现有关联网站时，从访问中心或关联网站开始，最多可能需要一个小时才能更新网站中的设置。</span><span class="sxs-lookup"><span data-stu-id="290c9-115">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="290c9-116">中心的新增关联网站则无需等待这样一段时间，相应设置会在几分钟内体现出来。</span><span class="sxs-lookup"><span data-stu-id="290c9-116">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="290c9-117">更新设置后，具有这些设置的内容类型将在几分钟内在任何与中心新关联的网站中变得可用。</span><span class="sxs-lookup"><span data-stu-id="290c9-117">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="290c9-118">然后，任何新创建的列表或库都将在创建后几分钟内自动添加该内容类型。</span><span class="sxs-lookup"><span data-stu-id="290c9-118">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="290c9-119">仅当推送的内容类型从文档内容类型直接或间接派生时，才会将其添加到文档库，并且仅在它不直接或间接从文档内容类型派生的情况下，才会将内容类型添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="290c9-119">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="290c9-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="290c9-120">See also</span></span>
