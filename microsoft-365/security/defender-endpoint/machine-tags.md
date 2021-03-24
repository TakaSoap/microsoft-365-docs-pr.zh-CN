---
title: 创建和管理设备标记
description: 使用设备标记对设备进行分组以捕获上下文，并启用动态列表创建作为事件的一部分
keywords: 标记， 设备标记， 设备组， 组， 修正， 级别， 规则， aad 组， 角色， 分配， 排名
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4a64d3242a34ec8bf6d5646513170aa35dd3a94c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056615"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="49961-104">创建和管理设备标记</span><span class="sxs-lookup"><span data-stu-id="49961-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="49961-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="49961-105">**Applies to:**</span></span>
- [<span data-ttu-id="49961-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="49961-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="49961-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49961-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="49961-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="49961-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="49961-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="49961-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="49961-110">在设备上添加标记以创建逻辑组附属关系。</span><span class="sxs-lookup"><span data-stu-id="49961-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="49961-111">设备标记支持网络的正确映射，使您能够附加不同的标记以捕获上下文，并启用动态列表创建作为事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="49961-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="49961-112">标记可在"设备" **列表视图中用作** 筛选器，或用于对设备进行分组。</span><span class="sxs-lookup"><span data-stu-id="49961-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="49961-113">有关设备分组详细信息，请参阅创建 [和管理设备组](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="49961-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="49961-114">可以使用以下方法在设备上添加标记：</span><span class="sxs-lookup"><span data-stu-id="49961-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="49961-115">使用门户</span><span class="sxs-lookup"><span data-stu-id="49961-115">Using the portal</span></span>
- <span data-ttu-id="49961-116">设置注册表项值</span><span class="sxs-lookup"><span data-stu-id="49961-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="49961-117">将标记添加到设备的时间与标记在设备列表和设备页面中的可用性之间可能有一些延迟。</span><span class="sxs-lookup"><span data-stu-id="49961-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="49961-118">若要使用 API 添加设备标记，请参阅[添加或删除设备标记 API。](add-or-remove-machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="49961-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="49961-119">使用门户添加和管理设备标记</span><span class="sxs-lookup"><span data-stu-id="49961-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="49961-120">选择要管理标记的设备。</span><span class="sxs-lookup"><span data-stu-id="49961-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="49961-121">可以从以下任一视图选择或搜索设备：</span><span class="sxs-lookup"><span data-stu-id="49961-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="49961-122">**安全操作仪表板** - 从具有活动警报的热门设备部分选择设备名称。</span><span class="sxs-lookup"><span data-stu-id="49961-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="49961-123">**警报队列** - 从警报队列中选择设备图标旁边的设备名称。</span><span class="sxs-lookup"><span data-stu-id="49961-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="49961-124">**设备列表** - 从设备列表中选择设备名称。</span><span class="sxs-lookup"><span data-stu-id="49961-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="49961-125">**搜索框** - 从下拉菜单中选择设备，然后输入设备名称。</span><span class="sxs-lookup"><span data-stu-id="49961-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="49961-126">您还可以通过文件和 IP 视图访问警报页面。</span><span class="sxs-lookup"><span data-stu-id="49961-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="49961-127">从 **"响应操作** "行中选择"管理标记"。</span><span class="sxs-lookup"><span data-stu-id="49961-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![管理标记按钮的图像](images/manage-tags.png)

3. <span data-ttu-id="49961-129">键入 以查找或创建标记</span><span class="sxs-lookup"><span data-stu-id="49961-129">Type to find or create tags</span></span>

    ![在设备上添加标记的图像1](images/new-tags.png)

<span data-ttu-id="49961-131">标记将添加到设备视图，并且也会反映在 **"设备"列表** 视图中。</span><span class="sxs-lookup"><span data-stu-id="49961-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="49961-132">然后，可以使用 **标记** 筛选器查看相关设备列表。</span><span class="sxs-lookup"><span data-stu-id="49961-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="49961-133">筛选可能对包含括号的标记名称不起作用。</span><span class="sxs-lookup"><span data-stu-id="49961-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="49961-134">创建新标记时，将显示现有标记的列表。</span><span class="sxs-lookup"><span data-stu-id="49961-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="49961-135">该列表只显示通过门户创建的标记。</span><span class="sxs-lookup"><span data-stu-id="49961-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="49961-136">不会显示从客户端设备创建的现有标记。</span><span class="sxs-lookup"><span data-stu-id="49961-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="49961-137">您还可以从此视图中删除标记。</span><span class="sxs-lookup"><span data-stu-id="49961-137">You can also delete tags from this view.</span></span>

![在设备上添加标记的图像2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="49961-139">通过设置注册表项值添加设备标记</span><span class="sxs-lookup"><span data-stu-id="49961-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="49961-140">仅适用于以下设备：</span><span class="sxs-lookup"><span data-stu-id="49961-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="49961-141">Windows 10 版本 1709 或更高版本</span><span class="sxs-lookup"><span data-stu-id="49961-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="49961-142">Windows Server 版本 1803 或更高版本</span><span class="sxs-lookup"><span data-stu-id="49961-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="49961-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="49961-143">Windows Server 2016</span></span>
>- <span data-ttu-id="49961-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="49961-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="49961-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="49961-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="49961-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="49961-146">Windows 8.1</span></span>
>- <span data-ttu-id="49961-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="49961-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="49961-148">标记中可以设置的最大字符数为 200。</span><span class="sxs-lookup"><span data-stu-id="49961-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="49961-149">当你需要对特定设备列表应用上下文操作时，具有类似标记的设备可能很方便。</span><span class="sxs-lookup"><span data-stu-id="49961-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="49961-150">使用以下注册表项在设备上添加标记：</span><span class="sxs-lookup"><span data-stu-id="49961-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="49961-151">注册表项： `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="49961-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="49961-152">注册表项值 (REG_SZ) ： `Group`</span><span class="sxs-lookup"><span data-stu-id="49961-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="49961-153">注册表项数据： `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="49961-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="49961-154">设备标记是每天生成的设备信息报告的一部分。</span><span class="sxs-lookup"><span data-stu-id="49961-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="49961-155">或者，你可以选择重新启动将传输新设备信息报告的终结点。</span><span class="sxs-lookup"><span data-stu-id="49961-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="49961-156">如果需要删除使用上述注册表项添加的标记，请清除注册表项数据的内容，而不是删除"Group"项。</span><span class="sxs-lookup"><span data-stu-id="49961-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
