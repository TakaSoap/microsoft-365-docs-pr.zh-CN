---
title: 设备名称
description: 如何Microsoft 托管桌面设备名称
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893714"
---
# <a name="device-names"></a><span data-ttu-id="013c9-103">设备名称</span><span class="sxs-lookup"><span data-stu-id="013c9-103">Device names</span></span>

<span data-ttu-id="013c9-104">Microsoft 托管桌面使用 Windows Autopilot、Azure Active Directory 和 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="013c9-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="013c9-105">若要使这些服务无缝协作，设备需要一致的标准化名称。</span><span class="sxs-lookup"><span data-stu-id="013c9-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="013c9-106">Microsoft 托管桌面注册设备时 (*MMD-%RAND11*) 格式应用标准化名称格式。</span><span class="sxs-lookup"><span data-stu-id="013c9-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="013c9-107">WindowsAutopilot 分配这些名称。</span><span class="sxs-lookup"><span data-stu-id="013c9-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="013c9-108">有关 Autopilot 详细信息，请参阅 [Autopilot 首次运行体验和注册状态页面](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="013c9-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="013c9-109">自动更改名称</span><span class="sxs-lookup"><span data-stu-id="013c9-109">Automated name changes</span></span>

<span data-ttu-id="013c9-110">如果设备稍后重命名，Microsoft 托管桌面自动将其重命名为标准化格式的新名称。</span><span class="sxs-lookup"><span data-stu-id="013c9-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="013c9-111">此过程每四小时执行一次。</span><span class="sxs-lookup"><span data-stu-id="013c9-111">This process occurs every four hours.</span></span> <span data-ttu-id="013c9-112">在用户下次重新启动设备时，将发生名称更改。</span><span class="sxs-lookup"><span data-stu-id="013c9-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="013c9-113">如果你的环境依赖于特定设备 (例如，为了支持特定的网络配置) ，你应该调查在注册到 Microsoft 托管桌面 之前删除该依赖关系的选项。</span><span class="sxs-lookup"><span data-stu-id="013c9-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="013c9-114">如果必须保留名称依赖项，可以通过管理门户提交请求以禁用重命名功能并使用[](../working-with-managed-desktop/admin-support.md)所需的名称格式。</span><span class="sxs-lookup"><span data-stu-id="013c9-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>