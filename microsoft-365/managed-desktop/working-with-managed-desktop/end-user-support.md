---
title: 获取用户对 Microsoft 托管桌面
description: 用户如何获取有关服务和设备的帮助
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362602"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="78987-104">获取针对用户的帮助</span><span class="sxs-lookup"><span data-stu-id="78987-104">Getting help for users</span></span>

<span data-ttu-id="78987-105">如果已达到工作流中需要请求提升的设备访问权限或[](../service-description/user-support.md)向 Microsoft 升级的点，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="78987-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="78987-106">这些支持选项不适用于"测试"组中设备。</span><span class="sxs-lookup"><span data-stu-id="78987-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="78987-107">提升请求</span><span class="sxs-lookup"><span data-stu-id="78987-107">Elevation requests</span></span>

<span data-ttu-id="78987-108">在请求提升对设备的访问权限之前，最好查看最适合的操作。</span><span class="sxs-lookup"><span data-stu-id="78987-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="78987-109">**典型** 操作是此过程的目的，在解决设备问题时，将定期Microsoft 托管桌面操作。</span><span class="sxs-lookup"><span data-stu-id="78987-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="78987-110">示例包括：</span><span class="sxs-lookup"><span data-stu-id="78987-110">Examples include:</span></span>
    - <span data-ttu-id="78987-111">提升内置系统疑难解答程序、命令提示符或Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78987-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="78987-112">业务线应用程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="78987-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="78987-113">使用解决方法更正应按设计正常运行 (如 BitLocker 激活或系统时间不更新) </span><span class="sxs-lookup"><span data-stu-id="78987-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="78987-114">提升设备管理器以执行更新驱动程序、卸载设备或扫描新更改等操作</span><span class="sxs-lookup"><span data-stu-id="78987-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="78987-115">**不建议的操作** 包括：</span><span class="sxs-lookup"><span data-stu-id="78987-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="78987-116">安装软件或浏览器</span><span class="sxs-lookup"><span data-stu-id="78987-116">Installing software or browsers</span></span>
    - <span data-ttu-id="78987-117">在外部安装驱动程序Windows设置，包括适用于外围设备的驱动程序</span><span class="sxs-lookup"><span data-stu-id="78987-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="78987-118">安装.msi或.exe文件</span><span class="sxs-lookup"><span data-stu-id="78987-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="78987-119">安装Windows功能</span><span class="sxs-lookup"><span data-stu-id="78987-119">Installing Windows features</span></span>

- <span data-ttu-id="78987-120">**不支持的操作** 包括：</span><span class="sxs-lookup"><span data-stu-id="78987-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="78987-121">安装与安全或管理功能Microsoft 托管桌面或操作相冲突的软件或功能</span><span class="sxs-lookup"><span data-stu-id="78987-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="78987-122">禁用Windows所需的功能，Microsoft 托管桌面 BitLocker</span><span class="sxs-lookup"><span data-stu-id="78987-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="78987-123">修改组织管理的设置</span><span class="sxs-lookup"><span data-stu-id="78987-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="78987-124">请求提升</span><span class="sxs-lookup"><span data-stu-id="78987-124">To request elevation</span></span>

1. <span data-ttu-id="78987-125">转到 的门户 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) ，然后使用你的 Azure Active Directory 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="78987-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="78987-126">选择 **"新建提升请求"。**</span><span class="sxs-lookup"><span data-stu-id="78987-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="78987-127">提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="78987-127">Provide these details:</span></span>
    - <span data-ttu-id="78987-128">**从你自己的** 支持票证系统支持票证 ID。</span><span class="sxs-lookup"><span data-stu-id="78987-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="78987-129">**设备名称**：输入设备序列号，然后从菜单中选择设备。</span><span class="sxs-lookup"><span data-stu-id="78987-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="78987-130">**类别**：选择最适合你的问题的类别。</span><span class="sxs-lookup"><span data-stu-id="78987-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="78987-131">如果似乎没有任何选项关闭，请选择"**其他**"，然后在"标题"和"操作计划"**字段中提供** 详细信息。</span><span class="sxs-lookup"><span data-stu-id="78987-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="78987-132">最好尽可能选择类别。</span><span class="sxs-lookup"><span data-stu-id="78987-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="78987-133">**子类别**：选择最适合该问题的类别。</span><span class="sxs-lookup"><span data-stu-id="78987-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="78987-134">如果没有选项看起来接近，请选择" **其他** "，然后在"标题"中提供 **简短说明**。</span><span class="sxs-lookup"><span data-stu-id="78987-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="78987-135">在 **"操作计划**"中，提供授予提升权限后计划采取疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="78987-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="78987-136">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="78987-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="78987-137">升级请求</span><span class="sxs-lookup"><span data-stu-id="78987-137">Escalation requests</span></span>


<span data-ttu-id="78987-138">如果需要将 [问题上报](../service-description/user-support.md#escalation-portal) 给 Microsoft，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="78987-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="78987-139">转到 的门户 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) ，然后使用你的 Azure Active Directory 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="78987-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="78987-140">选择 **"升级请求"，** 然后选择"**新建升级请求"。**</span><span class="sxs-lookup"><span data-stu-id="78987-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="78987-141">提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="78987-141">Provide these details:</span></span>
    - <span data-ttu-id="78987-142">**类别**：选择最适合你的问题的类别。</span><span class="sxs-lookup"><span data-stu-id="78987-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="78987-143">**标题**：提供一个非常简短的说明。</span><span class="sxs-lookup"><span data-stu-id="78987-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="78987-144">**说明**：添加可帮助团队了解此问题的其他任何详细信息。</span><span class="sxs-lookup"><span data-stu-id="78987-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="78987-145">如果需要附加文件，可以在提交后返回请求以完成这一操作。</span><span class="sxs-lookup"><span data-stu-id="78987-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="78987-146">**主要联系人信息**：提供有关如何联系负责与团队合作的主要人员的信息。</span><span class="sxs-lookup"><span data-stu-id="78987-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="78987-147">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="78987-147">Select **Submit**.</span></span>
5. <span data-ttu-id="78987-148">重新访问同一门户中的票证以与团队交互。</span><span class="sxs-lookup"><span data-stu-id="78987-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="78987-149">只有严重性 C 问题可以通过此路径进行升级。</span><span class="sxs-lookup"><span data-stu-id="78987-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="78987-150">对于其他问题，请与 IT 管理员联系，以通过管理门户提出请求。</span><span class="sxs-lookup"><span data-stu-id="78987-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>