---
title: 将设备分配到部署组
description: 如何指定希望设备在哪个部署组中
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985525"
---
# <a name="assign-devices-to-a-deployment-group"></a><span data-ttu-id="85322-104">将设备分配到部署组</span><span class="sxs-lookup"><span data-stu-id="85322-104">Assign devices to a deployment group</span></span>

<span data-ttu-id="85322-105">Microsoft 托管桌面将设备分配给各种部署组，但可以使用管理门户指定或更改分配给设备的组。</span><span class="sxs-lookup"><span data-stu-id="85322-105">Microsoft Managed Desktop will assign devices to the various deployment groups, but you can specify or change group a device is assigned to a device by using the Admin portal.</span></span> <span data-ttu-id="85322-106">在设备注册或用户注册后更改分配。</span><span class="sxs-lookup"><span data-stu-id="85322-106">You change the assignment after a device is registered or after a user has enrolled.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85322-107">如果更改分配，特定于该组的策略将应用于设备。</span><span class="sxs-lookup"><span data-stu-id="85322-107">If you change the assignment, policies that are specific to that group will be applied to the device.</span></span> <span data-ttu-id="85322-108">更改可能会安装最新版本的 Windows 10 (包括任何新功能或质量) 。</span><span class="sxs-lookup"><span data-stu-id="85322-108">The change might install the latest version of Windows 10 (including any new feature or quality updates).</span></span> <span data-ttu-id="85322-109">最好首先仅移动几台设备，然后检查生成的用户体验。</span><span class="sxs-lookup"><span data-stu-id="85322-109">It's best to move just a few devices at first and then check the resulting user experience.</span></span> <span data-ttu-id="85322-110">请注意，某些更新将重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="85322-110">Be aware that certain updates will restart the device.</span></span> <span data-ttu-id="85322-111">仔细检查是否选择了正确的设备进行分配。</span><span class="sxs-lookup"><span data-stu-id="85322-111">Double-check that you've selected the right devices to assign.</span></span> <span data-ttu-id="85322-112">工作分配最多可能需要 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="85322-112">It can take up to 24 hours for the assignment to take effect.</span></span>

<span data-ttu-id="85322-113">若要将设备分配给部署组，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="85322-113">To assign devices to a deployment group, follow these steps.</span></span> <span data-ttu-id="85322-114">如果你想要将单独的设备移动到不同的组，请对每个组重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="85322-114">If you want to move separate devices to different groups, repeat these steps for each group.</span></span>

1. <span data-ttu-id="85322-115">In Microsoft Endpoint Manager， select **Devices** in the left pane.</span><span class="sxs-lookup"><span data-stu-id="85322-115">In Microsoft Endpoint Manager, select **Devices** in the left pane.</span></span> <span data-ttu-id="85322-116">在 **"Microsoft 托管桌面"** 部分，选择 **"设备"。**</span><span class="sxs-lookup"><span data-stu-id="85322-116">In the **Microsoft Managed Desktop** section, select **Devices**.</span></span>
2. <span data-ttu-id="85322-117">选择要分配的设备。</span><span class="sxs-lookup"><span data-stu-id="85322-117">Select the devices you want to assign.</span></span> <span data-ttu-id="85322-118">所有选定的设备都将分配给你指定的组。</span><span class="sxs-lookup"><span data-stu-id="85322-118">All selected devices will be assigned to the group you specify.</span></span>
3. <span data-ttu-id="85322-119">从 **菜单中选择设备** 操作。</span><span class="sxs-lookup"><span data-stu-id="85322-119">Select **Device actions** from the menu.</span></span>
4. <span data-ttu-id="85322-120">选择 **"将设备分配到组"。**</span><span class="sxs-lookup"><span data-stu-id="85322-120">Select **Assign device to group**.</span></span> <span data-ttu-id="85322-121">将打开一个飞入。</span><span class="sxs-lookup"><span data-stu-id="85322-121">A fly-in opens.</span></span>
5. <span data-ttu-id="85322-122">使用下拉菜单选择要将设备移动到的组，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="85322-122">Use the drop-down menu to select the group to move devices to, and then select **Save**.</span></span> <span data-ttu-id="85322-123">分配 **了 的组** 将更改为"挂起 **"。**</span><span class="sxs-lookup"><span data-stu-id="85322-123">The **Group assigned by** will change to **Pending**.</span></span>

<span data-ttu-id="85322-124">工作分配完成后，"分配者"将更改为"管理员" (表明您进行了更改) "组"列将显示新的组分配。  </span><span class="sxs-lookup"><span data-stu-id="85322-124">When the assignment is complete, **Group assigned by** will change to **Admin** (indicated that you made the change) and the **Group** column will show the new group assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="85322-125">如果设备在"错误"或"挂起"注册状态，则不能将设备移动到其他组。</span><span class="sxs-lookup"><span data-stu-id="85322-125">You can't move devices to other groups if they're in the "error" or "pending" registration state.</span></span>
>
><span data-ttu-id="85322-126">如果设备尚未正确删除，它可能会显示"就绪"状态。</span><span class="sxs-lookup"><span data-stu-id="85322-126">If a device hasn't been properly removed, it could show a status of "ready."</span></span> <span data-ttu-id="85322-127">如果你移动此类设备，移动可能会无法完成。</span><span class="sxs-lookup"><span data-stu-id="85322-127">If you move such a device, it's possible that the move won't complete.</span></span> <span data-ttu-id="85322-128">如果在步骤 5中未看到"由更改为待处理分配组"，请在 Intune 中搜索设备，检查设备是否可用。</span><span class="sxs-lookup"><span data-stu-id="85322-128">If you don't see **Group assigned by** change to **Pending** in Step 5, check that the device is available by searching for it in Intune.</span></span> <span data-ttu-id="85322-129">有关详细信息，请参阅[查看 Intune 中的设备详细信息](/mem/intune/remote-actions/device-inventory)。</span><span class="sxs-lookup"><span data-stu-id="85322-129">For more information, see [See device details in Intune](/mem/intune/remote-actions/device-inventory).</span></span>