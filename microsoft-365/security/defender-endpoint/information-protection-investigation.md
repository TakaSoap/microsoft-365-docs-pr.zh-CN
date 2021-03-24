---
title: 使用敏感度标签确定事件响应的优先级
description: 了解如何使用敏感度标签确定事件的优先级并调查事件
keywords: 信息， 保护， 数据， 丢失， 防护， 标签， dlp， 事件， 调查， 调查
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: d0c27ab2c6af8706e5e06a3c87b44e49c9185766
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055846"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="977c8-104">使用敏感度标签确定事件响应的优先级</span><span class="sxs-lookup"><span data-stu-id="977c8-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="977c8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="977c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="977c8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="977c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="977c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="977c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="977c8-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="977c8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="977c8-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="977c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="977c8-110">典型的高级永久性威胁生命周期涉及数据外接。</span><span class="sxs-lookup"><span data-stu-id="977c8-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="977c8-111">在安全事件中，必须能够优先考虑敏感文件可能受到威胁的调查，以便保护公司数据和信息。</span><span class="sxs-lookup"><span data-stu-id="977c8-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="977c8-112">Defender for Endpoint 使用敏感度标签可帮助简化安全事件的优先顺序。</span><span class="sxs-lookup"><span data-stu-id="977c8-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="977c8-113">敏感度标签可快速识别可能涉及包含敏感信息（如机密信息）的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="977c8-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="977c8-114">调查涉及敏感数据的事件</span><span class="sxs-lookup"><span data-stu-id="977c8-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="977c8-115">了解如何使用数据敏感度标签确定事件调查的优先级。</span><span class="sxs-lookup"><span data-stu-id="977c8-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="977c8-116">检测到 Windows 10 版本 1809 或更高版本的标签。</span><span class="sxs-lookup"><span data-stu-id="977c8-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="977c8-117">在 Microsoft Defender 安全中心中，选择 **"事件"。**</span><span class="sxs-lookup"><span data-stu-id="977c8-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="977c8-118">滚动到右侧以查看" **数据敏感度"** 列。</span><span class="sxs-lookup"><span data-stu-id="977c8-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="977c8-119">此列反映与事件相关的设备上观察到的敏感度标签，用于指示敏感文件是否受事件影响。</span><span class="sxs-lookup"><span data-stu-id="977c8-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![数据敏感度列的图像](images/data-sensitivity-column.png)

    <span data-ttu-id="977c8-121">还可以根据数据敏感度 **进行筛选**</span><span class="sxs-lookup"><span data-stu-id="977c8-121">You can also filter based on **Data sensitivity**</span></span> 

    ![数据敏感度筛选器的图像](images/data-sensitivity-filter.png)

3. <span data-ttu-id="977c8-123">打开事件页面以进一步调查。</span><span class="sxs-lookup"><span data-stu-id="977c8-123">Open the incident page to further investigate.</span></span>

    ![事件页面详细信息的图像](images/incident-page.png)

4. <span data-ttu-id="977c8-125">选择 **"设备"** 选项卡以标识使用敏感度标签存储文件的设备。</span><span class="sxs-lookup"><span data-stu-id="977c8-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![设备选项卡的图像](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="977c8-127">选择存储敏感数据的设备，并搜索时间线以确定哪些文件可能会受到影响，然后采取相应的措施以确保数据受到保护。</span><span class="sxs-lookup"><span data-stu-id="977c8-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="977c8-128">可以通过搜索数据敏感度标签来缩小设备时间线上显示的事件范围。</span><span class="sxs-lookup"><span data-stu-id="977c8-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="977c8-129">执行此操作将只显示与已说出标签名称的文件关联的事件。</span><span class="sxs-lookup"><span data-stu-id="977c8-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![根据标签缩小搜索结果范围的设备时间线图像](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="977c8-131">这些数据点还通过高级搜寻中的"DeviceFileEvents"公开，从而允许高级查询和计划检测考虑敏感度标签和文件保护状态。</span><span class="sxs-lookup"><span data-stu-id="977c8-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
