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
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295803"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="b906c-103">将内容类型推送到中心</span><span class="sxs-lookup"><span data-stu-id="b906c-103">Push content types to a hub</span></span>

<span data-ttu-id="b906c-104">若要使重要的内容类型对 SharePoint 库和列表更加一致，可以将它们推送到您选择的中心。</span><span class="sxs-lookup"><span data-stu-id="b906c-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="b906c-105">这会自动将其添加到在与中心关联的网站上创建的任何新列表和库以及添加到中心的任何新网站。</span><span class="sxs-lookup"><span data-stu-id="b906c-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="b906c-106">若要使此功能正常运行，必须已发布要推送的内容类型。</span><span class="sxs-lookup"><span data-stu-id="b906c-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="b906c-107">将内容类型推送到集线器</span><span class="sxs-lookup"><span data-stu-id="b906c-107">To push content types to hubs</span></span>

1. <span data-ttu-id="b906c-108">在 SharePoint 管理中心中，展开 " **内容服务**"，然后单击 " **内容类型库**"。</span><span class="sxs-lookup"><span data-stu-id="b906c-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="b906c-109">单击要推送到集线器的内容类型。</span><span class="sxs-lookup"><span data-stu-id="b906c-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="b906c-110">在命令栏中单击 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="b906c-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="b906c-111">单击 " **选择中心站点**"。</span><span class="sxs-lookup"><span data-stu-id="b906c-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="b906c-112">选择所需的中心网站，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b906c-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="b906c-113">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b906c-113">Click **Save**.</span></span>

<span data-ttu-id="b906c-114">首次将内容类型推送到现有中心 & 它的现有关联网站时，在访问中心或关联的网站时，可能需要一小时的时间，以供在网站中更新的设置。</span><span class="sxs-lookup"><span data-stu-id="b906c-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="b906c-115">任何新的中心关联都不需要此等待，并将在几分钟后反映这些设置。</span><span class="sxs-lookup"><span data-stu-id="b906c-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="b906c-116">配置此配置后，具有这些设置的内容类型将在几分钟内与中心在任何新关联的网站中可用。</span><span class="sxs-lookup"><span data-stu-id="b906c-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="b906c-117">一旦可用，创建的任何新列表或库都会在几分钟内自动将其添加到该内容类型。</span><span class="sxs-lookup"><span data-stu-id="b906c-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="b906c-118">仅当推送的内容类型从文档内容类型直接或间接派生时，才会添加到文档库中，并且仅当它不直接或间接从文档内容类型派生时，才会将该内容类型添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="b906c-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="b906c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b906c-119">See also</span></span>



  






