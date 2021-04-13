---
title: 指定 Microsoft Defender 防病毒的云保护级别
description: 为 Microsoft Defender 防病毒设置云保护级别。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， Defender， 云， 攻击性， 保护级别
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: a6678811ca83c4ddefae3dcbe9ab6de79391da4b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690273"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="ce1f4-104">指定云提供的保护级别</span><span class="sxs-lookup"><span data-stu-id="ce1f4-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ce1f4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ce1f4-105">**Applies to:**</span></span>

- [<span data-ttu-id="ce1f4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ce1f4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ce1f4-107">可以使用 Microsoft Endpoint Manager 或建议 (或组策略，指定由 Microsoft Defender 防病毒提供的) 保护级别。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="ce1f4-108">云保护不仅仅是对存储在云中的文件的保护。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="ce1f4-109">Microsoft Defender 防病毒云服务是一种向网络和设备提供更新保护的机制 (也称为终结点) 。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="ce1f4-110">Microsoft Defender 防病毒的云保护使用分布式资源和机器学习以比传统安全智能更新快得多的速度为终结点提供保护。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="ce1f4-111">Microsoft Intune 和 Microsoft Endpoint Manager 现在是 [Microsoft Endpoint Manager 的一部分](/mem/endpoint-manager-overview)。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="ce1f4-112">使用 Microsoft Endpoint Manager 指定云提供的保护级别</span><span class="sxs-lookup"><span data-stu-id="ce1f4-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="ce1f4-113">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="ce1f4-114">选择 **终结点安全**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="ce1f4-115">选择防病毒配置文件。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-115">Select an antivirus profile.</span></span> <span data-ttu-id="ce1f4-116"> (如果你还没有配置文件，或者如果你想要创建新的配置文件，请参阅在 [Microsoft Intune](/intune/device-restrictions-configure)中配置设备限制设置。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="ce1f4-117">选择 **"属性"。**</span><span class="sxs-lookup"><span data-stu-id="ce1f4-117">Select **Properties**.</span></span> <span data-ttu-id="ce1f4-118">然后，在"配置 **设置"旁边，选择**"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="ce1f4-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="ce1f4-119">展开 **"云** 保护"，然后在" **云提供的** 保护级别"列表中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="ce1f4-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="ce1f4-120">**高**：应用强级别的检测。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="ce1f4-121">**高加**： **使用高级别** ，并应用其他保护措施 (可能会影响客户端性能) 。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="ce1f4-122">**零容** 限：阻止所有未知可执行文件。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="ce1f4-123">选择 **"审阅 + 保存"，** 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="ce1f4-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="ce1f4-124">需要一些帮助？</span><span class="sxs-lookup"><span data-stu-id="ce1f4-124">Need some help?</span></span> <span data-ttu-id="ce1f4-125">参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="ce1f4-125">See the following resources:</span></span>
> - [<span data-ttu-id="ce1f4-126">配置 Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="ce1f4-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="ce1f4-127">在 Intune 中添加终结点保护设置</span><span class="sxs-lookup"><span data-stu-id="ce1f4-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="ce1f4-128">使用组策略指定云提供的保护级别</span><span class="sxs-lookup"><span data-stu-id="ce1f4-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="ce1f4-129">在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="ce1f4-130">右键单击要配置的组策略对象，然后单击编辑 **。**</span><span class="sxs-lookup"><span data-stu-id="ce1f4-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="ce1f4-131">在组 **策略管理编辑器中**，转到计算机 **配置**  >  **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="ce1f4-132">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **MpEngine**。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="ce1f4-133">双击选择云 **保护级别** 设置，将其设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="ce1f4-134">选择保护级别：</span><span class="sxs-lookup"><span data-stu-id="ce1f4-134">Select the level of protection:</span></span>
    - <span data-ttu-id="ce1f4-135">**默认阻止级别** 提供强检测，而不会增加检测合法文件的风险。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="ce1f4-136">**中等阻止级别** 仅为高可信度检测提供中等</span><span class="sxs-lookup"><span data-stu-id="ce1f4-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="ce1f4-137">**高阻止级别** 可在优化客户端性能 (同时应用强大的检测级别，但也可以为您提供更大的误报) 。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="ce1f4-138">**高 +** 阻止级别会应用其他保护措施 (可能会影响客户端性能并增加误报的可能性) 。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="ce1f4-139">**零容限阻止级别** 可阻止所有未知可执行文件。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="ce1f4-140">虽然不太可能，但将此开关设置为"高"或"高 **+"** 可能会导致检测到一些合法 (尽管你可选择取消阻止或争议该检测) 。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="ce1f4-141">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-141">Click **OK**.</span></span>

7. <span data-ttu-id="ce1f4-142">部署更新的组策略对象。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="ce1f4-143">请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="ce1f4-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="ce1f4-144">是否在本地使用组策略对象？</span><span class="sxs-lookup"><span data-stu-id="ce1f4-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="ce1f4-145">查看它们在云中如何转换。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-145">See how they translate in the cloud.</span></span> <span data-ttu-id="ce1f4-146">使用 Microsoft Endpoint [Manager 中的组策略](/mem/intune/configuration/group-policy-analytics)分析分析本地组策略对象 - 预览 。</span><span class="sxs-lookup"><span data-stu-id="ce1f4-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="ce1f4-147">相关文章</span><span class="sxs-lookup"><span data-stu-id="ce1f4-147">Related articles</span></span>

- [<span data-ttu-id="ce1f4-148">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ce1f4-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="ce1f4-149">启用云保护</span><span class="sxs-lookup"><span data-stu-id="ce1f4-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ce1f4-150">如何创建和部署反恶意软件策略：云保护服务</span><span class="sxs-lookup"><span data-stu-id="ce1f4-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)