---
title: 管理指示器
ms.reviewer: ''
description: 管理定义实体检测、防护和排除的文件哈希、IP 地址、URL 或域的指示器。
keywords: import， indicator， list， ioc， csv， manage， allowed， blocked， clean， malicious， file hash， ip address， urls， domain
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
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185941"
---
# <a name="manage-indicators"></a><span data-ttu-id="85e24-104">管理指示器</span><span class="sxs-lookup"><span data-stu-id="85e24-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="85e24-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="85e24-105">**Applies to:**</span></span>
- [<span data-ttu-id="85e24-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="85e24-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="85e24-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="85e24-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="85e24-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="85e24-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="85e24-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="85e24-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="85e24-110">在导航窗格中，选择"**设置**  >  **""指示器"。**</span><span class="sxs-lookup"><span data-stu-id="85e24-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="85e24-111">选择要管理的实体类型的选项卡。</span><span class="sxs-lookup"><span data-stu-id="85e24-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="85e24-112">更新指示器的详细信息，并单击"保存"或单击"删除"按钮（如果要从列表中删除该实体）。</span><span class="sxs-lookup"><span data-stu-id="85e24-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="85e24-113">导入 IoCs 列表</span><span class="sxs-lookup"><span data-stu-id="85e24-113">Import a list of IoCs</span></span>

<span data-ttu-id="85e24-114">还可以选择上传定义指示器属性、要采取的操作和其他详细信息的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="85e24-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="85e24-115">下载示例 CSV，了解受支持的列属性。</span><span class="sxs-lookup"><span data-stu-id="85e24-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="85e24-116">在导航窗格中，选择"**设置**  >  **""指示器"。**</span><span class="sxs-lookup"><span data-stu-id="85e24-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="85e24-117">选择要导入其指示器的实体类型的选项卡。</span><span class="sxs-lookup"><span data-stu-id="85e24-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="85e24-118">选择 **导入**  >  **选择文件**。</span><span class="sxs-lookup"><span data-stu-id="85e24-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="85e24-119">选择“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="85e24-119">Select **Import**.</span></span> <span data-ttu-id="85e24-120">为要导入的所有文件执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="85e24-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="85e24-121">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="85e24-121">Select **Done**.</span></span>

<span data-ttu-id="85e24-122">下表显示了受支持的参数。</span><span class="sxs-lookup"><span data-stu-id="85e24-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="85e24-123">参数</span><span class="sxs-lookup"><span data-stu-id="85e24-123">Parameter</span></span> | <span data-ttu-id="85e24-124">类型</span><span class="sxs-lookup"><span data-stu-id="85e24-124">Type</span></span>    |   <span data-ttu-id="85e24-125">说明</span><span class="sxs-lookup"><span data-stu-id="85e24-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="85e24-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="85e24-126">indicatorType</span></span> | <span data-ttu-id="85e24-127">枚举</span><span class="sxs-lookup"><span data-stu-id="85e24-127">Enum</span></span> | <span data-ttu-id="85e24-128">指示器的类型。</span><span class="sxs-lookup"><span data-stu-id="85e24-128">Type of the indicator.</span></span> <span data-ttu-id="85e24-129">可能的值是："FileSha1"、"FileSha256"、"IpAddress"、"DomainName"和"Url"。</span><span class="sxs-lookup"><span data-stu-id="85e24-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="85e24-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="85e24-130">**Required**</span></span>
<span data-ttu-id="85e24-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="85e24-131">indicatorValue</span></span> | <span data-ttu-id="85e24-132">String</span><span class="sxs-lookup"><span data-stu-id="85e24-132">String</span></span> | <span data-ttu-id="85e24-133">Indicator [实体的](ti-indicator.md) 标识。</span><span class="sxs-lookup"><span data-stu-id="85e24-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="85e24-134">**必需**</span><span class="sxs-lookup"><span data-stu-id="85e24-134">**Required**</span></span>
<span data-ttu-id="85e24-135">action</span><span class="sxs-lookup"><span data-stu-id="85e24-135">action</span></span> | <span data-ttu-id="85e24-136">枚举</span><span class="sxs-lookup"><span data-stu-id="85e24-136">Enum</span></span> | <span data-ttu-id="85e24-137">如果在组织中发现指示器，将采取的操作。</span><span class="sxs-lookup"><span data-stu-id="85e24-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="85e24-138">可能的值是："Alert"、"AlertAndBlock"和"Allowed"。</span><span class="sxs-lookup"><span data-stu-id="85e24-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="85e24-139">**必需**</span><span class="sxs-lookup"><span data-stu-id="85e24-139">**Required**</span></span>
<span data-ttu-id="85e24-140">title</span><span class="sxs-lookup"><span data-stu-id="85e24-140">title</span></span> | <span data-ttu-id="85e24-141">String</span><span class="sxs-lookup"><span data-stu-id="85e24-141">String</span></span> | <span data-ttu-id="85e24-142">指示器警报标题。</span><span class="sxs-lookup"><span data-stu-id="85e24-142">Indicator alert title.</span></span> <span data-ttu-id="85e24-143">**必需**</span><span class="sxs-lookup"><span data-stu-id="85e24-143">**Required**</span></span>
<span data-ttu-id="85e24-144">说明</span><span class="sxs-lookup"><span data-stu-id="85e24-144">description</span></span> | <span data-ttu-id="85e24-145">String</span><span class="sxs-lookup"><span data-stu-id="85e24-145">String</span></span> |  <span data-ttu-id="85e24-146">指示器的说明。</span><span class="sxs-lookup"><span data-stu-id="85e24-146">Description of the indicator.</span></span> <span data-ttu-id="85e24-147">**必需**</span><span class="sxs-lookup"><span data-stu-id="85e24-147">**Required**</span></span>
<span data-ttu-id="85e24-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="85e24-148">expirationTime</span></span> | <span data-ttu-id="85e24-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="85e24-149">DateTimeOffset</span></span> | <span data-ttu-id="85e24-150">指示器的过期时间，格式为 YYYY-MM-DDTHH：MM：SS.0Z。</span><span class="sxs-lookup"><span data-stu-id="85e24-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="85e24-151">**可选**</span><span class="sxs-lookup"><span data-stu-id="85e24-151">**Optional**</span></span>
<span data-ttu-id="85e24-152">severity</span><span class="sxs-lookup"><span data-stu-id="85e24-152">severity</span></span> | <span data-ttu-id="85e24-153">枚举</span><span class="sxs-lookup"><span data-stu-id="85e24-153">Enum</span></span> | <span data-ttu-id="85e24-154">指示器的严重性。</span><span class="sxs-lookup"><span data-stu-id="85e24-154">The severity of the indicator.</span></span> <span data-ttu-id="85e24-155">可能的值包括："Informational"、"Low"、"Medium"和"High"。</span><span class="sxs-lookup"><span data-stu-id="85e24-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="85e24-156">**可选**</span><span class="sxs-lookup"><span data-stu-id="85e24-156">**Optional**</span></span>
<span data-ttu-id="85e24-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="85e24-157">recommendedActions</span></span> | <span data-ttu-id="85e24-158">String</span><span class="sxs-lookup"><span data-stu-id="85e24-158">String</span></span> | <span data-ttu-id="85e24-159">TI 指示器警报建议操作。</span><span class="sxs-lookup"><span data-stu-id="85e24-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="85e24-160">**可选**</span><span class="sxs-lookup"><span data-stu-id="85e24-160">**Optional**</span></span>
<span data-ttu-id="85e24-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="85e24-161">rbacGroupNames</span></span> | <span data-ttu-id="85e24-162">String</span><span class="sxs-lookup"><span data-stu-id="85e24-162">String</span></span> | <span data-ttu-id="85e24-163">将应用指示器的 RBAC 组名称的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="85e24-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="85e24-164">**可选**</span><span class="sxs-lookup"><span data-stu-id="85e24-164">**Optional**</span></span>
<span data-ttu-id="85e24-165">“类别”</span><span class="sxs-lookup"><span data-stu-id="85e24-165">category</span></span> | <span data-ttu-id="85e24-166">String</span><span class="sxs-lookup"><span data-stu-id="85e24-166">String</span></span> | <span data-ttu-id="85e24-167">警报的类别。</span><span class="sxs-lookup"><span data-stu-id="85e24-167">Category of the alert.</span></span> <span data-ttu-id="85e24-168">示例包括：执行和凭据访问。</span><span class="sxs-lookup"><span data-stu-id="85e24-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="85e24-169">**可选**</span><span class="sxs-lookup"><span data-stu-id="85e24-169">**Optional**</span></span>
<span data-ttu-id="85e24-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="85e24-170">mitretechniques</span></span>| <span data-ttu-id="85e24-171">String</span><span class="sxs-lookup"><span data-stu-id="85e24-171">String</span></span> | <span data-ttu-id="85e24-172">MITRE 技术代码/id (逗号分隔) 。</span><span class="sxs-lookup"><span data-stu-id="85e24-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="85e24-173">有关详细信息，请参阅企业 [策略](https://attack.mitre.org/tactics/enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="85e24-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="85e24-174">**可选** 建议在 MITRE 技术时在类别中添加值。</span><span class="sxs-lookup"><span data-stu-id="85e24-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="85e24-175">有关详细信息，请参阅 [Microsoft Defender for Endpoint 警报类别现在与 MITRE ATT&CK！](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)一致。</span><span class="sxs-lookup"><span data-stu-id="85e24-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="85e24-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85e24-176">See also</span></span>
- [<span data-ttu-id="85e24-177">创建指示器</span><span class="sxs-lookup"><span data-stu-id="85e24-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="85e24-178">创建文件指示器</span><span class="sxs-lookup"><span data-stu-id="85e24-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="85e24-179">为 IP 和 URL/域创建指示器</span><span class="sxs-lookup"><span data-stu-id="85e24-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="85e24-180">创建基于证书的指示器</span><span class="sxs-lookup"><span data-stu-id="85e24-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
