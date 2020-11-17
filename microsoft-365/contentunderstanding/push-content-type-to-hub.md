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
ms.collection: enabler-strategic
localization_priority: Priority
ms.openlocfilehash: d64dd5ab49d371df075f1044024c12fbf78e265c
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087603"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="4d581-103">将内容类型推送到中心</span><span class="sxs-lookup"><span data-stu-id="4d581-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="4d581-104">若要使重要内容类型与 SharePoint 库和列表更为一致，可将其推送到选择的中心。</span><span class="sxs-lookup"><span data-stu-id="4d581-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="4d581-105">这会自动将其添加到与中心相关联的网站上创建的所有新列表和库，以及添加到中心的任何新网站。</span><span class="sxs-lookup"><span data-stu-id="4d581-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="4d581-106">若要使用此功能，必须已发布正在推送的内容类型。</span><span class="sxs-lookup"><span data-stu-id="4d581-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="4d581-107">将内容类型推送到中心</span><span class="sxs-lookup"><span data-stu-id="4d581-107">To push content types to hubs</span></span>

1. <span data-ttu-id="4d581-108">在 SharePoint 管理中心中，展开“**内容服务**”，然后单击“**内容类型库**”。</span><span class="sxs-lookup"><span data-stu-id="4d581-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="4d581-109">单击要推送到中枢的内容类型。</span><span class="sxs-lookup"><span data-stu-id="4d581-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="4d581-110">单击命令栏中的 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="4d581-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="4d581-111">单击 **“选择中心网站”**。</span><span class="sxs-lookup"><span data-stu-id="4d581-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="4d581-112">选择所需中心网站，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="4d581-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="4d581-113">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4d581-113">Click **Save**.</span></span>

<span data-ttu-id="4d581-114">第一次将内容类型推送到现有中心和它现有的关联网站时，可能需要长达一小时的时间来访问中心或关联的网站，以获得网站中更新的设置。</span><span class="sxs-lookup"><span data-stu-id="4d581-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="4d581-115">任何与中心的新关联都不需要等待，并且会在几分钟内反映这些设置。</span><span class="sxs-lookup"><span data-stu-id="4d581-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="4d581-116">配置此项后，这些设置的内容类型将在几分钟内在任何与中心关联的新站点中可用。</span><span class="sxs-lookup"><span data-stu-id="4d581-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="4d581-117">新建的列表或库一经提供，在创建的几分钟内，将自动添加该内容类型。</span><span class="sxs-lookup"><span data-stu-id="4d581-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="4d581-118">仅当推送的内容类型从文档内容类型直接或间接派生时，才会将其添加到文档库，并且仅在它不直接或间接从文档内容类型派生的情况下，才会将内容类型添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="4d581-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d581-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d581-119">See also</span></span>



  






